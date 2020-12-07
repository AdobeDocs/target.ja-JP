---
keywords: Profile script;profile script attributes;mutually exclusive activities
description: プロファイル属性を使用すると、同じ訪問者を各アクティビティに参加させずに、複数のアクティビティを比較するテストを設定することができます。
title: 相互に排他的なアクティビティをテストするプロファイルスクリプトを使用する
feature: visitor profiles
translation-type: tm+mt
source-git-commit: 6704ac2ec73361ad95e110e9182485537d0de642
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 81%

---


# Use profile scripts to test mutually exclusive activities {#section_FEFE50ACA6694DE7BF1893F2EFA96C01}

プロファイル属性を使用すると、同じ訪問者を各アクティビティに参加させずに、複数のアクティビティを比較するテストを設定することができます。

相互に排他的なアクティビティのテストを実行すると、1 つのアクティビティの訪問者が他のアクティビティのテスト結果に影響するのを防ぐことができます。訪問者を複数のアクティビティに参加させると、1 つのアクティビティの訪問者のエクスペリエンスから積極的上昇率と消極的上昇率のどちらがもたらされたのか、または複数のアクティビティ間の相互作用がアクティビティの結果に影響しているのかどうかを見極めることが難しくなります。

例えば、e コマースシステムの 2 つの領域をテストするとします。「カートへ」ボタンが青色ではなく追加赤色になることをテストします。 また、手順の数を 5 つから 2 つに減らす新しいチェックアウトプロセスをテストすることもできます。両方のアクティビティの成功イベント（購入が完了したもの）が同じ場合、赤いボタンでコンバージョンが向上するか、またはチェックアウトプロセスが改善されたために同じコンバージョンが増加したかを判断するのは困難です。 相互に排他的なアクティビティにテストを分けることで、個々の変更を個別にテストすることができます。

以下のいずれかのプロファイルスクリプトを使用する際は、次の点にご注意ください。

* プロファイルスクリプトは、アクティビティの開始前に実行する必要があります。また、アクティビティの実行中は変更しないでください。
* この方法により、アクティビティ内のトラフィック量が減り、アクティビティの実行時間が長くなる可能性があります。 アクティビティの期間を推定する際は、この点を考慮に入れてください。

## 2 つのアクティビティの設定

異なるアクティビティを閲覧するそれぞれのグループに訪問者を分けるには、プロファイル属性を作成する必要があります。プロファイル属性によって、訪問者を複数のグループのいずれかに分類することができます。「twogroups」というプロファイル属性を設定するには、次のスクリプトを作成します。

```javascript
if (!user.get('twogroups')) { 
    var ran_number = Math.floor(Math.random() * 99); 
    if (ran_number <= 49) { 
        return 'GroupA'; 
    } else { 
        return 'GroupB'; 
    } 
}
```

* `if (!user.get('twogroups'))` は、現在の訪問者に対して *twogroups* プロファイル属性を設定するかどうかを指定します。設定されている場合は、それ以上のアクションは必要ありません。

* `var ran_number=Math.floor(Math.random() *99)` new変数を宣言し、runran_ numberという値を定義し、その値を0~1の乱数に設定し、その値を99で乗算し、その値を切り捨てて100（0~99）の範囲を作成すると、アクティビティを見た訪問者の割合を指定するのに役立ちます。

* `if (ran_number <= 49)` は、訪問者が属するグループを決定するルーチンを開始します。0 から 49 の範囲の数値が返された場合、訪問者は GroupA に割り当てられます。50 から 99 の範囲の数値が返された場合、訪問者は GroupB に割り当てられます。グループは、訪問者がどのアクティビティを閲覧するかを決定します。

After you create the profile attribute, set up the first activity to target the desired population by requiring that the user profile parameter `user.twogroups` matches the value specified for GroupA.

>[!NOTE]
>
>ページの最初のmboxを選択します。このコードは、訪問者がアクティビティを体験するかどうかを決定します。 ブラウザーで最初に検出される mbox である限り、その mbox を使用して値を設定できます。

ユーザープロファイルパラメーター `user.twogroups` が GroupB に指定した値と一致するように 2 番目のキャンペーンを設定します。

## 3 つ以上のアクティビティの設定

相互に排他的なアクティビティを 3 つ以上設定する方法は、2 つのアクティビティの場合と同様ですが、アクティビティごとにグループが作成されるようにプロファイル属性 JavaScript を変更して、各アクティビティを閲覧する訪問者を決める必要があります。乱数の生成は、作成するグループの数が奇数か偶数かによって異なります。

例えば、4 つのグループを作成する場合は、次の JavaScript を使用します。

```javascript
if (!user.get('fourgroups')) { 
    var ran_number = Math.floor​(Math.random() * 99); 
    if (ran_number <= 24) { 
        return 'GroupA'; 
    } else if (ran_number <= 49) { 
        return 'GroupB'; 
    } else if (ran_number <= 74) { 
        return 'GroupC'; 
    } else { 
        return 'GroupD'; 
    } 
}
```

この例では、訪問者をグループに割り当てる乱数の生成に使用する計算は、2 つのグループを作成する場合の計算と同じです。小数の乱数は、生成された後、丸められて整数となります。

奇数のグループまたは 100 を均等に分割できない数のグループを作成する場合は、小数点以下を丸めて整数にはしないでください。小数点以下を丸めなければ、整数以外の範囲も指定することができます。これを行うには、

`var ran_number=Math.floor(Math.random()*99);`

の行を次のように変更します。

`var ran_number=Math.random()*99;`

例えば、訪問者を 3 つのグループに均等に配分するには、次のコードを使用します。

```javascript
if (!user.get('threegroups')) { 
    var ran_number = Math.random() * 99; 
    if (ran_number <= 32.33) { 
        return 'GroupA'; 
    } else if (ran_number <= 65.66) { 
        return 'GroupB'; 
    } else { 
        return 'GroupC'; 
    } 
}
```
