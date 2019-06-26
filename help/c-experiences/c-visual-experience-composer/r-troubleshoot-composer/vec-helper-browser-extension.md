---
description: Target Visual Experience Composer（VEC）ヘルパーブラウザー拡張を使用して、VEC 内で確実に Web サイトを読み込み、エクスペリエンスを迅速に作成および QA する方法について説明します。
keywords: vec;visual experience composer; vec;iframe;extension;browser
seo-description: Adobe Target Visual Experience Composer（VEC）ヘルパーブラウザー拡張を使用して、VEC 内で確実に Web サイトを読み込み、エクスペリエンスを迅速に作成および QA する方法について説明します。
seo-title: Adobe Target Visual Experience Composer（VEC）ヘルパー拡張
solution: 'Target '
title: Visual Experience Composer ヘルパー拡張機能
topic: Standard
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Visual Experience Composer ヘルパー拡張機能

Google Chrome 用 [!DNL Adobe Target]Visual Experience Composer（VEC）ヘルパーブラウザー拡張機能では、VEC 内で確実に Web サイトを読み込み、Web エクスペリエンスを迅速に作成および QA できます。

VEC で一部の Web サイトを確実に開くことができない理由：

* Web サイトには厳格なセキュリティポリシーがあります。
* Web サイトで iframe が使用されています。
* Web サイトに at.js ライブラリがまだ実装されていません。
* お客様の QA またはステージサイトは、外部では利用できません（サイトは内部）。

Chrome 用の VEC ヘルパーブラウザー拡張機能は、お客様が[!DNL Target][!UICONTROL 拡張 Experience Composer] またはサードパーティ拡張機能（Requestly など）に依存するようになったサイトの読み込みの問題を解決します。

VEC ヘルパー拡張機能を使用する利点：

* すべての iframe バスティングヘッダー（X-Frame-Options や Content-Security-Policy など）は、Web サイトから暗黙的に削除されます。そのための複雑な Requestly ルールを作成する必要はありません。
* Web ページに [!DNL Target]at.js JavaScript ライブラリがまだ含まれていない場合は、拡張機能を使用してライブラリを挿入することにより、Web サイトのエクスペリエンスを作成できます。その後に、プレビューリンクを使用してアクティビティを作成し、QA を実行できます。
* モバイルビューポートは、[!UICONTROL 拡張 Experience Composer] （EEC）がなくてもサポートされます。
* [!DNL Target]が初めてのお客様は、自社の IT 開発者がまだ Web サイトに[!DNL Target]を実装していない場合でも、拡張機能を使用して[!DNL Target]を試すことができます。
* 複数のお客様の Web サイトおよび[!DNL Target]アカウントにサービスを提供するパートナーは、サードパーティツールで複数のルールを管理するのではなく、VEC 読み込みをサポートする 1 つのシンプルなメカニズムを利用できるようになりました。

## VEC ヘルパーブラウザー拡張の取得とインストール

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. [!UICONTROL Chrome に追加 / 拡張機能を追加]をクリックします。
1. 拡張機能を使用するには、VEC または [QA モード](/help/c-activities/c-activity-qa/activity-qa.md)で、Chrome ブラウザーのツールバーにある「VEC ヘルパーブラウザー拡張」アイコン（ ![「VEC ヘルパー」アイコン](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png) ）をクリックします。

「[!UICONTROL Target ライブラリを挿入]」設定が有効になっている VEC ヘルパーを次の図に示します。

![VEC ヘルパー 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

オーサリングを有効にするためにページに[!DNL Target]ライブラリを挿入するかどうかを VEC ヘルパーが確認している様子を次の図に示します。

![VEC ヘルパー 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

## メモ

* 実装するには [!DNL Target]at.js ライブラリを使用する必要があります。拡張機能では、mbox.js の実装を使用できません。
* デフォルトでは、拡張機能の「 [!UICONTROL Target ライブラリを挿入] 」フラグがオフになっています。[!DNL Target]向けにまだ実装されていないサイトで VEC を使用する場合は、このフラグを有効にすることができます。

   このフラグはグローバル設定であることに注意してください。このフラグは、VEC で開かれているすべての Web サイトに対して有効または無効になります。したがって、このフラグをオンにして at.js で既に実装されている Web サイトを開くと、at.js が既に読み込まれていることを示すメッセージが表示されます。ほとんどのお客様は既にページに at.js を実装しており、デフォルト設定であるオフを使用することが予想されます。

* 拡張機能は、[!DNL Target UI]の[!UICONTROL セットアップ / 実装]から利用できる最新バージョンの at.js を読み込みます。
* 拡張機能を使用して [QA モード](/help/c-activities/c-activity-qa/activity-qa.md)で at.js を挿入する場合は、別の Chrome タブを開く必要があります。この Chrome タブは、アクティビティを作成したのと同じ[!DNL Adobe Experience Cloud]組織に対して認証される必要があります。
* 次のメッセージにより、さらに情報が提供されます。

   * VEC を使用した Web サイトの読み込みに失敗した場合、VEC ヘルパーブラウザー拡張機能のインストールを勧めるメッセージが表示されます。
   * at.js が Web サイトにまだ実装されていない場合、拡張機能のインストールを勧めるメッセージが VEC に表示されます。
   * 拡張機能を有効にして読み込みを実行している場合は、拡張機能により at.js ライブラリが挿入（必要に応じて）されるか、または VEC 内で Web サイトが確実に開かれることを示すメッセージが表示されます。