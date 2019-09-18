---
description: mbox.js から at.js への移行は、簡単なプロセスです。
keywords: Target;at.js;at.js への移行;準備;at.js の監査;at.js の統合
seo-description: mbox.js から at.js への移行は、簡単なプロセスです。
seo-title: mbox.js から at.js に移行する方法
solution: 'Target '
title: mbox.js から at.js に移行する方法
topic: Standard
uuid: 45f81fe8-7b04-4a36-931d-bbf03ed6cbb3
translation-type: tm+mt
source-git-commit: 2aa63623b4d2ca38ec96c51402ee483a918dd3ae

---


# mbox.js から at.js に移行する方法{#how-to-migrate-to-at-js-from-mbox-js}

[!DNL Adobe Target] での mbox.js から at.js への移行は簡単なプロセスです。

次の手順に従って、[!DNL mbox.js] から [!DNL at.js] に移行し、移行をチェックしてください。

1. 組織の[ブラウザーサポート要件](../../../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)を決定します。
1. [!DNL mbox.js] でサポートされない機能について、Web サイトの現在の [!DNL at.js] 実装をチェックします。

   実装を検証する際に、以下を確認します。

   **現在使用している mbox のタイプは何か。**

   | タイプ | 詳細 |
   |--- |--- |
   | 自動作成されたグローバル mbox | 自動作成されたグローバル mbox は、サイト上の Target コードの行だけが mbox.js ファイルである場合に作成されます。このファイルが mbox 呼び出しを自動的に生成します。 |
   | グローバルで空の mboxCreate | 自動作成されたグローバル mbox に切り替えることをお勧めします。 |
   | ラッピングされた mboxCreate | `mboxCreate()` の前に `<div class="mboxDefault"></div>` がある限り、簡単に移行できます。 |
   | mboxUpdate | `mboxUpdate()` が、`mboxDefine()` または `mboxCreate()` と共に使用されている場合、簡単に移行できます。`mboxUpdate()` は、自動作成されたグローバル mbox または元々 `getOffer()` によって作成された mbox を更新しません。こうした状況では、at.js の移行時に `getOffer()` と `applyOffer()` を組み合わせて使用して、`mboxUpdate()` を置き換える必要があります。 |
   | カスタムクリック追跡 mbox（mboxTrack を含む） | コードを更新して `trackEvent()` を使用することをお勧めします。 |

   >[!NOTE]
   >
   >上記の表に記載されているさまざまな関数に関する詳細については、「[at.js 関数](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md)」を参照してください。

   **[!DNL mbox.js]ファイルをカスタマイズしているかどうか。**

   * mboxParameters()
   * mboxSupported()
   * mboxCookieDomain()
   * 追加の JavaScript
   * 他の場所
   [mbox.js オブジェクトおよびメソッド](../../../../c-target/c-visitor-profile/variables-profiles-parameters-methods.md#section_8C78059D15D9452F95636A5640188537)のほとんど（`mbox`、`mboxCurrent`、`mboxFactoryDefault`、`mboxFactories` など）はサポートされません。やろうとしていることを達成するための方法が他にもある可能性があります。

   **すべての Web ページに[!DNL mbox.js]があるかどうか。**

   同じ Web ページに [!DNL at.js] と [!DNL mbox.js] の両方を使用することはできません。ただし、同じ Web サイトの 2 つの異なるページで 2 つの JavaScript ライブラリを使用することはできます。

   mbox cookie は、アドビがページからページへ訪問者を追跡するのに使用する主要な方法です。QA プロセスの一部として、cookie が保持されていて、訪問者が [!DNL at.js] を使用したページと [!DNL mbox.js] を使用したページの間を行き来するのに合わせて適切に読み込まれることを確認する必要があります。訪問者が最初に読み込むのがサイトのどのセクションか（`mboxPC` または `mboxSession`）、および元々どのセクションに cookie が設定されていたかにかかわらず、同じ [!DNL at.js] および [!DNL mbox.js] の値が mbox 呼び出しで渡されていることを確認します。実装でサードパーティの cookie を使用する場合、サイトを閲覧する際にそれらの値が同じままであることを確認します。

   **[!DNL Target]を他のアドビソリューションと統合しているかどうか。**

   * Analytics（A4T）
   * Analytics（従来の統合）
   * AAM（バックエンド）
   * AAM（従来のフロントエンド）
   * AEM
   * Data Workbench
   一部の従来の統合は、[!DNL at.js] ではサポートされません。詳しくは、[統合](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)ページを参照してください。

   **[!DNL Target]をサードパーティツールと統合しているかどうか。**

   * 他の解析ツール
   * その他の DMP
   * Demandbase
   * クリックテール
   * その他
   これらの統合を [!DNL at.js] と連携させるには調整が必要となる場合があります。詳しくは、[統合](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)ページを参照してください。

   **タグマネージャーを使用するかどうか。**

   * Dynamic Tag Management
   * Ensighten
   * Tealium
   * Signal／BrightTag
   詳細については、「[at.js の統合](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)」を参照してください。

   >[!NOTE]
   >
   >現在、[!DNL Target] のデプロイにタグマネージャーを使用していない場合は、この機会に使用を検討してみてください。アドビの [Dynamic Tag Management](https://dtm.adobe.com) は、[!DNL Target] のお客様は無料で利用でき、[!DNL Target] のデプロイにお勧めの方法です。詳しくは、[Dynamic Tag Management を使用した Adobe Target の実装のベストプラクティス](https://docs.adobe.com/content/help/en/dtm/implementing/overview.html)を参照してください。

1. 現在のすべてのアクティビティおよび統合が期待どおりに動作していることを検証します。

   次に、[!DNL at.js] が期待どおりに動作していることを確認するためのテスト中にできることを示します。

   * 現在のすべてのアクティビティが新しい JavaScript ライブラリで動作することを確認する。
   * すべての[統合](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md#concept_C100BC4F073C4B57A608B309D0157B39)および[プラグイン](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-plugins.md#concept_F5D4C0A4DACF41409CC42FDD93B13FAF)が期待どおりに動作することを確認する。
   * [デバッグ](../../../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F)が（[!DNL at.js]で利用可能な方法で）問題なくおこなえることを確認する。

**at.js への移行時に発生する可能性のある問題** at.js への移行の実施後に、次の問題が発生する場合があります。

* [!DNL mbox.js] を使用してページに作成した一部の VEC アクティビティは、[!DNL at.js] で動作するように更新することが必要な場合があります。

   この問題は、HTML 要素に多くの ID 属性またはクラス属性を使用していない Web サイトで最も頻繁に発生します。この問題が発生しているかどうかを確認するには、ページを読み込みます。次に、`?mboxDebug=true` を使用してページを読み込み、コンソールステートメントを確認して、エクスペリエンスが期待どおりに配信されているかどうかを判断します。

   ![](assets/mboxdebug.png)そうした場合、要素セレクターは先頭が次のようになっており、

   ```
   HTML > BODY > DIV:nth-of-type(2)
   ```

   [!DNL mbox.js] によって `<div>` 要素がページの上部に追加されることを前提として作成されていることがあります。[!DNL at.js] では `<div>` 要素がページの上部に追加されないので、このセレクターは [!DNL at.js] では動作しなくなります。

   この問題に対処するには、VEC で [!DNL at.js] を使用してその URL に対するアクティビティを再作成するか、VEC の **[!UICONTROL &lt;/&gt; コード]**／「**[!UICONTROL 変更]**」オプションの順に使用してセレクターを手動で更新します。

   この問題を修正するには、BODY の後の最初の DIV 要素にある nth-of-type の数から 1 を引く必要があります。上述の例では、編集したコードは次のようになります。

   ```
   HTML > BODY > DIV:nth-of-type(1)
   ```

   これをおこなうためのコードエディターの使用方法について詳しくは、[コードエディター](../../../../c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5).

* 現在すべての mbox は非同期なので、ページレンダリングをブロックせず、実行された順番で返されます。詳しくは、[at.js の制限](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#concept_FA99E4D6EC274552BF45E01AFB76CCAE)を参照してください。
