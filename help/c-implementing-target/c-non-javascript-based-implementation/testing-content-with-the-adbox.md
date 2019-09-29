---
description: adbox を使用してオフサイト実装で画像を配信します。
keywords: 実装;mbox.js 非 JavaScript;mbox;adbox
seo-description: adbox を使用してオフサイト実装で画像を配信します。
seo-title: 画像用 adbox の作成
solution: 'Target '
subtopic: 導入
title: 画像用 adbox の作成
topic: Standard
uuid: 6b1763f7-08de-4bde-9e20-e79b92b02f20
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 画像用 adbox の作成{#create-an-adbox-for-an-image}

adbox を使用してオフサイト実装で画像を配信します。

adbox は mbox と似ていますが、JavaScript ではなく URL によって制御されます。adbox は、「広告」mbox（adbox）をアカウントに読み込む特殊な adbox 用の URL を使用して作成されます。アクティビティでは、この adbox を mbox の代わりに使用します。電子メールなどの JavaScript を使用しない実装では、画像の直接参照ではなく adbox URL を使用します。

適切な設定の判断方法については、[JavaScript ベース以外の実装](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

1. 次の adbox URL を作成します。

   ```
   https://myClientCode.tt.omtrdc.net/m2/myClientCode/ubox/
   image?mbox=emailHeroImage123_320x200
   mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif
   ```

   * `myClientCode` はお客様のクライアントコードです。クライアントコードはすべて小文字で、特殊文字は含まれません。

      * **at.js**： クライアントコードは、[!UICONTROL  インターフェイスの「]セットアップ」／「実装」／「at.js 設定を編集[!DNL Target]」ページの最上部にあります。

      * **mbox.js**： クライアントコードは、「[!UICONTROL セットアップ」／「実装」／「mbox.js 設定を編集」ページの最上部にあります。]
   * `image` は呼び出しのタイプです。この場合は画像です。

   * `emailHeroImage123_320x200` は adbox の名前です。

   * `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif` は mbox のデフォルトコンテンツです。画像にする必要があります。

      URL エンコードをおこない、絶対参照にする必要があります。You can use the [HTML URL Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp) to quickly encode your URLs.


1. 各代替画像の[リダイレクトオファー](../../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)を作成します。

   >[!NOTE] {class="- topic/note "}
   >
   >adbox は、リダイレクトオファーまたはデフォルトコンテンツオファーを使用して読み込む必要があります。その他のオファータイプは使用できません。adbox は URL なので、受け取った URL しか表示できません。つまり、リダイレクトオファーのみが機能します。

1. アクティビティを作成します。

   目的に合わせた適切な設定については、「[JavaScript ベース以外の実装](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)」を参照してください。
1. アクティビティで QA を完了します。

   ダミーページを作成し、あらゆる環境のすべてのタイプのブラウザーで、エクスペリエンス、デフォルトコンテンツおよびレポートがすべて適切に機能するか確認することをお勧めします。1. アクティビティを開始します。
