---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Visual Experience Composer(VEC) で一部の Web サイトを確実に開けない可能性がある理由を発見します。 VEC ヘルパーブラウザー拡張機能を使用すると、VEC 内で確実に Web サイトを読み込むことができます。
title: Visual Experience Composer(VEC) ヘルパー拡張の使用方法を教えてください。
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 52%

---

# Visual Experience Composer ヘルパー拡張機能

この [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC)Google Chrome 用ヘルパーブラウザー拡張機能を使用すると、VEC 内で確実に Web サイトを読み込み、作成と QA Web エクスペリエンスをすばやくできます。

>[!NOTE]
>
>VEC ヘルパーブラウザーは、Chrome 拡張機能です。 Mozilla Firefox を使用する場合、この拡張機能は不要です。

## VEC で一部の Web サイトを確実に開けない理由

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* Web サイトに at.js ライブラリがまだ実装されていません。
* お客様の QA またはステージサイトは、外部では利用できません（サイトは内部）。
* Google Chrome 80 以降を、強化された SameSite cookie 実施ポリシーと共に使用している。 詳しくは、 [最近発表されたGoogle Chrome SameSite cookie の実施ポリシーが VEC と EEC にどのように影響するか](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

Chrome 用の VEC ヘルパーブラウザー拡張機能は、お客様が現在 [!DNL Target] [拡張 Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) または Requestly などのサードパーティの拡張機能を使用できます。

## VEC ヘルパー拡張機能を使用するメリット

* すべての iframe バスティングヘッダー（X-Frame-Options や Content-Security-Policy など）は、Web サイトから暗黙的に削除されます。複雑な Requestly ルールを作成する必要はありません。
* Web ページに [!DNL Target]at.js JavaScript ライブラリがまだ含まれていない場合は、拡張機能を使用してライブラリを挿入することにより、Web サイトのエクスペリエンスを作成できます。その後に、プレビューリンクを使用してアクティビティを作成し、QA を実行できます。

   拡張 Experience Composer(EEC) を使用すると、拡張機能は at.js を挿入しませんが、SameSite Cookie 機能は引き続き存在します。 Web ページに at.js を挿入するには、EEC をオフにします。

* [モバイルビューポート](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) が [!UICONTROL 拡張 Experience Composer] (EEC)。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## VEC ヘルパーブラウザー拡張の取得とインストール

1. 次に移動： [Chrome Web Store のAdobe Target VEC ヘルパーブラウザー拡張機能](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. **[!UICONTROL Chrome に追加 / 拡張機能を追加]**&#x200B;をクリックします。
1. で VEC を開きます。 [!DNL Target].
1. 拡張機能を使用するには、VEC または [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)で、Chrome ブラウザーのツールバーにある「VEC ヘルパーブラウザー拡張」アイコン（ ![「VEC ヘルパー」アイコン](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ）をクリックします。
1. （条件付き） **[!UICONTROL Target ライブラリを挿入]** ウェブページにまだ [!DNL Target] at.js JavaScript ライブラリ。

   「[!UICONTROL Target ライブラリを挿入]」設定が有効になっている VEC ヘルパーを次の図に示します。

   ![VEC ヘルパー 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   オーサリングを有効にするためにページに[!DNL Target]ライブラリを挿入するかどうかを VEC ヘルパーが確認している様子を次の図に示します。

   ![VEC ヘルパー 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. （条件付き） **[!UICONTROL Cookie]** 自動的に `SameSite=None` 属性ブラウザの修正。

   ![VEC ヘルパー拡張機能での cookie の切り替え](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   詳しくは、 `SameSite=None` 属性ブラウザーの修正については、「最近発表されたGoogle Chrome SameSite cookie の実施ポリシーが VEC および EEC に与える影響」を参照してください。 [Visual Experience Composer と拡張 Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)。

## メモ

* デフォルトでは、拡張機能の「 [!UICONTROL Target ライブラリを挿入] 」フラグがオフになっています。[!DNL Target]向けにまだ実装されていないサイトで VEC を使用する場合は、このフラグを有効にすることができます。

   このフラグはグローバル設定です。 このフラグは、VEC で開かれているすべての Web サイトに対して有効または無効になります。例えば、このフラグを「on」に設定し、at.js で既に実装されている Web サイトを開くと、at.js が既に読み込まれていることを示すメッセージが表示されます。 Adobeでは、ほとんどのお客様は既にページに at.js が実装されており、デフォルト設定の「off」を使用していると予想されます。

* 拡張機能は、 [!DNL Target UI] in [!UICONTROL 管理/実装].
* 拡張機能を使用して [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md)で at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは、アクティビティを作成したのと同じ[!DNL Adobe Experience Cloud]組織に対して認証される必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * VEC を使用した Web サイトの読み込みに失敗した場合、VEC ヘルパーブラウザー拡張機能のインストールを勧めるメッセージが表示されます。
   * at.js が Web サイトにまだ実装されていない場合、拡張機能のインストールを勧めるメッセージが VEC に表示されます。
   * 拡張機能を有効にして読み込みを実行している場合は、拡張機能により at.js ライブラリが挿入（必要に応じて）されるか、または VEC 内で Web サイトが確実に開かれることを示すメッセージが表示されます。