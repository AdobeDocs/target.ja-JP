---
keywords: ちらつき，事前非表示，事前非表示，パーソナライゼーション，実装，ちらつき防止，VEC,visual experience composer
description: コンテンツの事前非表示で、アカウントレベルの設定、軽量ページライブラリ、アクティビティごとの制御を使用して、アクティブなAdobe Target パーソナライゼーションが変更されるリージョンのみを非表示にすることで、ちらつきを軽減する方法を説明します。
title: パーソナライズされた体験を実現するためのコンテンツの事前非表示
feature: Administration & Configuration
role: Admin
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
source-git-commit: 77741253fdfb007d0eda0c57fe293df2f9c638a2
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 3%

---

# パーソナライズされた体験を実現するためのコンテンツの事前非表示

>[!AVAILABILITY]
>
>パーソナライズされたコンテンツのコンテンツの事前非表示は、**ベータ**&#x200B;機能として利用できます。

訪問者がページを読み込むと、デフォルトのコンテンツが簡単に表示され、次に[!DNL Adobe Target]からパーソナライズされたコンテンツに置き換えられます。 この表示スイッチは&#x200B;**フリッカー**&#x200B;と呼ばれることが多く、パーソナライゼーションプログラムの一般的なエクスペリエンスの問題です。

コンテンツを事前に非表示にすることで、ページの読み込み中にアクティビティがパーソナライズするページの一部のみを非表示にすることで、ちらつきを管理できます。これにより、顧客のちらつきの軽減と空き画面の時間の削減を実現できます。

ここでは、アカウントのデフォルトからページの実装、アクティビティごとの選択まで、コンテンツの事前非表示がどのように機能するかをご紹介します。

1. アカウントのコンテンツの事前非表示を有効にして、グローバルデフォルトを設定します。 デフォルトではオフになっています。 [詳細情報](#content-pre-hiding-enable-account)

1. パーソナライゼーションアクティビティを実行するすべてのページの`<head>`にコンテンツ事前非表示ライブラリを追加します。

1. [!DNL Target]は、ライブ [!UICONTROL Visual Experience Composer]および[!UICONTROL Enhanced Experience Composer]のアクティビティからルールセットを構築します。 ルールセットには、配信が変更される可能性のあるセレクターと地域が一覧表示されます。

   [!UICONTROL Form-Based Composer] アクティビティはサポートされていません。

1. ライブラリは、Adobe CDNからルールセットを取得し、パーソナライズされたコンテンツの読み込み中にのみ一致する要素を事前に非表示にします。

1. **[!UICONTROL Goals & Settings]**&#x200B;では、個々のアクティビティに対して&#x200B;**[!UICONTROL Content pre-hiding]**&#x200B;を無効にできますが、これはアカウントレベルで有効になっている場合に限られます。 [詳細情報](#content-pre-hiding-activity)

## インスタンスのコンテンツの事前非表示を有効にする {#content-pre-hiding-enable-account}

>[!IMPORTANT]
>
>インスタンスのコンテンツ事前非表示を有効にするには、**管理者**&#x200B;である必要があります。

コンテンツの事前非表示は、有効にするまでインスタンスに対してオフになっています。 **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**&#x200B;を使用して、機能を有効にし、デフォルトを設定し、実装チームのダウンロードにアクセスします。

1. [!DNL Target]で、**[!UICONTROL Administration]** > **[!UICONTROL Implementation]**&#x200B;をクリックします。

1. **[!UICONTROL Content pre-hiding]** メニューで、「コンテンツの事前非表示」オプションを有効にします。

   ![](assets/content-pre-hiding-1.png)

1. 必要に応じて、**[!UICONTROL Pre-hiding timeout]**&#x200B;を秒単位で更新します。

1. **[!UICONTROL Save]** をクリックします。 これにより、ちらつき管理設定がインスタンスに適用されます。

1. 有効になったら、**[!UICONTROL Download]**&#x200B;をクリックし、ページ `<head>`にファイルを追加して、[!DNL at.js]または[!DNL Web SDK]の前に読み込みます。 実装の手順について詳しくは、「[SDKのコンテンツの事前非表示](https://experienceleague.adobe.com/ja/docs/target-dev/developer/client-side/prehide-sdk)」を参照してください。

   ![](assets/content-pre-hiding-2.png)

これで、保存されたコンテンツの事前非表示とタイムアウト設定を、オプトインするアクティビティのデフォルトとして使用できるようになりました。

## アクティビティのコンテンツの事前非表示を有効にする {#content-pre-hiding-activity}

インスタンスの事前非表示を有効にして、各アクティビティが&#x200B;**[!UICONTROL Goals & Settings]**&#x200B;でインスタンスを使用するかどうかを選択します。 事前非表示を有効にしたアクティビティは、公開時にターゲットとなる動作に含まれます。

次に、[!DNL Target]は、[!UICONTROL Visual Experience Composer] （VEC）および[!UICONTROL Form-Based Composer]で作成されたライブアクティビティから軽量ルールセットを作成し、配信が変更できるセレクターと領域を説明します。

アクティビティを作成または編集する場合：

1. 事前非表示オプションを有効にするアクティビティにアクセスします。

1. **[!UICONTROL Edit activity]** ドロップダウンにアクセスし、**[!UICONTROL Edit Goals & Settings]**&#x200B;を選択します。

   ![](assets/content-pre-hiding-3.png)

1. **[!UICONTROL Content pre-hiding]** メニューから、**[!UICONTROL Enable content pre-hiding]** オプションを切り替えて、このアクティビティを事前非表示にするか非表示にするかを選択します。

   ![](assets/content-pre-hiding-4.png)

1. 完了したら、**[!UICONTROL Save & Close]**&#x200B;をクリックします。

アクティビティの公開時または非アクティブ化が完了すると、ルールセットが更新され、事前非表示が維持され、ローンチごとにページコードが編集されることなく、実際に配信されるものと一致します。

訪問者側では、ライブラリはページが読み込まれるたびにAdobe CDNからルールセットを取得し、パーソナライズされたコンテンツの準備が整うまで、必要な場合にのみ一致する要素を事前に非表示にします。
