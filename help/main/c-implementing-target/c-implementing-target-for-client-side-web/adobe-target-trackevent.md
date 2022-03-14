---
keywords: adobe.target.trackEvent;trackEvent;trackevent;track event;at.js;関数;preventDefault;preventdefault;prevent default
description: Adobeに対して adobe.target.trackEvent() 関数を使用します [!DNL Target] at.js JavaScript ライブラリを使用して、サイト上でのクリック数やコンバージョン数などのユーザーのアクションをレポートするリクエストを実行します。
title: adobe.target.trackEvent() 関数の使用方法を教えてください。
feature: at.js
role: Developer
exl-id: 36005236-ce18-4845-b4fb-e52056018bc7
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 69%

---

# adobe.target.trackEvent(options)

この関数は、クリックやコンバージョンなどのユーザーアクションを報告するリクエストを実行します。応答でアクティビティを配信することはありません。

そのため、これらのイベント追跡 mbox 呼び出しは、アクティビティで指標を定義するのに使用できます。詳細については、「[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」および「[コンバージョンの追跡](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)」を参照してください。

API の詳細を次に示します。

| キー | タイプ | 必須 | 説明 |
|--- |--- |--- |--- |
| mbox | 文字列 | ○ | mbox 名&#x200B;<br>**注意**:ページで既に実行されている mbox 名で trackEvent() 呼び出しが実行されると、trackEvent() の SDID はリセットされ、ページ上の Target 呼び出しとは異なります。 ただし、異なる mbox 名で trackEvent() 呼び出しを実行すると、trackEvent() 呼び出しの SDID がページ上のページ読み込み要求/triggerView() 呼び出しと一致するようになります。 |
| selector | 文字列 | × | CSS セレクターは HTML 要素を見つけるために使用されます。イベントリスナーが、見つけた要素に添付されます  |
| type | 文字列 | × | 登録されたイベントタイプを表します。クリック、マウスダウンなどの HTML の既知のイベントとカスタム HTML イベントの両方が可能です。 |
| preventDefault | ブール値 | × | イベントリスナーコールバックで `event.preventDefault()` を使用するかどうかを示します。デフォルトは false です。<br>**注意**:のみ `form[submit]` および `a[click]` はサポートされています。 サポートすべきシナリオの複雑さと量の膨大さにより、その他のシナリオはサポートされません。 |
| params | オブジェクト | × | mbox パラメーター。次の構造を持つキーと値のペアのオブジェクト。<br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | 数値 | × | タイムアウト（ミリ秒）。<br>指定しない場合は、次のデフォルト値が使用されます。<br>`...timeoutInSeconds: 0.15...}` |
| success | 関数 | × | イベントが繰り返されたことを伝えるために使用されるコールバック関数。 |
| error | 関数 | × | イベントを繰り返せなかったことを伝えるために使用されるコールバック関数。 |

## 例

```javascript
<a href="https://asite.com">click me!</a> 
```

さらに、`trackEvent` を割り当てるための JavaScript コード：

```javascript
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

または

```javascript
adobe.target.trackEvent({ 
    "mbox": "clicked-cta", 
    "params": { 
        "param1": "value1" 
    } 
});
```

>[!NOTE]
>
>必須フィールドが設定されていない場合、リクエストは実行されず、エラーがスローされます。
