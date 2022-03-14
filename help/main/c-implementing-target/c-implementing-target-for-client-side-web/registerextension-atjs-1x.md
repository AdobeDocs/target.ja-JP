---
keywords: registerExtension;registerextension;register extension;at.js;関数;clientCode;serverDomain;globalMboxName;globalMboxAutoCreate;timeout
description: Adobeに対して registerExtension() 関数を使用する [!DNL Target] at.js JavaScript ライブラリを使用して、特定の拡張機能を登録します。 (at.js 1.x)
title: registerExtension() 関数の使用方法を教えてください。
feature: at.js
role: Developer
exl-id: 7f0898b4-ddd5-425c-99dc-94f9b30f8ba7
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 90%

---

# registerExtension() - at.js 1.x

特定の拡張を登録するための標準的な方法を提供します。

>[!NOTE]
>
>この関数は at.js バージョン 1.*x* のみで使用できます。この関数は at.js 2.x のリリースで廃止されました。at.js 2.x で使用する場合、この関数はデフォルトコンテンツを返します。

options パラメーターは必須で、以下の構造を持ちます。

| キー | タイプ | 必須 | 説明 |
|--- |--- |--- |--- |
| name | 文字列 | ○ | 拡張名です。 |
| モジュール | Array[String] | ○ | リクエストしたモジュール名を示す文字列の配列です。 |
| 登録 | 関数 | ○ | 拡張の初期化および構築に使用される関数です。この関数では、モジュール配列に基づいた引数を受け取ります。 |

メモ:

* パラメーターのいずれかが指定されていない場合は、例外が発生します。
* モジュール配列が空白の場合は、例外が発生します。

`registerExtension` の使用方法に関するその他の情報および例の詳細については、GitHub 上の「[Adobe Experience Cloud Target atjs Extensions](https://github.com/Adobe-Marketing-Cloud/target-atjs-extensions)」ページを参照してください。

## モジュールメソッドの設定 {#section_8501CDD4B0624FA2B10532C98C5F4328}

| キー | タイプ | 説明 |
|--- |--- |--- |
| clientCode | 文字列 | クライアントコード |
| serverDomain | 文字列 | Edge サーバードメイン |
| globalMboxName | 文字列 | Target のグローバル mbox 名 |
| globalMboxAutoCreate | ブール値 | 自動作成が有効化されているかどうかを示します。 |
| timeout | 数値 | リクエストのタイムアウト |

## Logger Module メソッド {#section_10AF62B49AEF48F981E950D26E176138}

| キー | タイプ | 説明 |
|--- |--- |--- |
| log | 関数 | ブラウザーコンソールに対する引数の変数リストを記録します（存在する場合）。`mboxDebug=true` が URL に渡される場合にのみアクティブ化されます。 |
| error | 関数 | ブラウザーコンソールに対する引数の変数リストを記録します。ネットワークのタイムアウトや、HTML ノードが見つからない場合など、重大なエラーが発生した場合にのみアクティブ化されます。 |
