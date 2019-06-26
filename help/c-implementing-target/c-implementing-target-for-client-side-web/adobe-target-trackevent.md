---
description: 'at.js の adobe.target.trackEvent(options) 関数について説明します。 '
keywords: adobe.target.notification;要素;セレクター;通知;拡張子
seo-description: Adobe Target at.js JavaScript ライブラリの adobe.target.trackEvent(options) 関数について説明します。
seo-title: Adobe Target at.js JavaScript ライブラリの adobe.target.trackEvent(options) 関数について説明します。
solution: 'Target '
subtopic: 導入
title: adobe.target.trackEvent(options)
topic: Standard
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# adobe.target.trackEvent(options)

この関数は、クリックやコンバージョンなどのユーザーアクションを報告するリクエストを実行します。応答でアクティビティを配信することはありません。

そのため、これらのイベント追跡 mbox 呼び出しは、アクティビティで指標を定義するのに使用できます。詳細については、「[成功指標](../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924)」および「[コンバージョンの追跡](../../c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)」を参照してください。

API の詳細を次に示します。

| キー | タイプ | 必須 | 説明 |
|--- |--- |--- |--- |
| mbox | 文字列 | ○ | mbox 名 |
| selector | 文字列 | × | CSS セレクターは HTML 要素を見つけるために使用されます。イベントリスナーが、見つけた要素に添付されますを参照してください。 |
| type | 文字列 | × | 登録されたイベントタイプを表します。クリック、マウスダウンなどの HTML の既知のイベントとカスタム HTML イベントの両方が可能です。 |
| preventDefault | ブール値 | × | イベントリスナーコールバックで `event.preventDefault()` を使用するかどうかを示します。デフォルトは false です。<br>**注意**： `form[submit] and ` と [クリック]のみがサポートされています。サポートすべきシナリオの複雑さと量の膨大さにより、その他のシナリオはサポートされません。 |
| params | オブジェクト | × | mbox パラメーター。次の構造を持つキーと値のペアのオブジェクト。<br>`{ "param1": "value1", "param2": "value2"}` |
| timeout | 数値 | × | タイムアウト（ミリ秒）。<br>指定しない場合は、次のデフォルト値が使用されます。<br>`...timeoutInSeconds: 0.15...}` |
| success | 関数 | × | イベントが繰り返されたことを伝えるために使用されるコールバック関数。 |
| error | 関数 | × | イベントを繰り返せなかったことを伝えるために使用されるコールバック関数。 |

## 例

```
<a href="https://asite.com">click me!</a> 
```

さらに、`trackEvent` を割り当てるための JavaScript コード：

```
<script> 
$('a').click(function(event){ 
  adobe.target.trackEvent({'mbox':'homePageHero'}) 
}); 
</script> 
```

または

```
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