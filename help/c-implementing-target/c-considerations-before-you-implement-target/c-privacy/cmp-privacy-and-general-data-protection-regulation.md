---
description: 欧州連合のGeneral Data Protection規制（GGPR）とカリフォルニア消費者プライバシー法（CCCPA）に関する情報、およびこれらの規制における組織およびAdobe Targetの影響について説明します。
keywords: dgpr;eu;European union;privacy;faq;よくある質問、カリフォルニア消費者プライバシー行為、cppa
seo-description: 欧州連合のGeneral Data Protection規制（GGPR）とカリフォルニア消費者プライバシー法（CCCPA）に関する情報、およびこれらの規制における組織およびAdobe Targetの影響について説明します。
seo-title: 一般的なデータ保護規則（GGPR）、カリフォルニア消費者プライバシー法（CCPA）、およびAdobe Target
solution: 'Target '
title: プライバシーとデータ保護規則
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: 222fb66f58ea5bcecabfaa2ab966ad9a686dc9ef

---


# プライバシーとデータ保護規則 {#privacy-and-general-data-protection-regulation-gdpr}

欧州連合の一般的なデータ保護規制（GGPR）およびカリフォルニア消費者プライバシー法（CCCPA）およびこれらの規制における組織への影響について説明 [!DNL Adobe Target]します。

## プライバシーと一般データ保護規則（GDPR）の概要{#topic_DE567ECB6C944695AEE5073889F1AEA9}

欧州連合の一般データ保護規則（GDPR）に対応するためのアドビによるお客様との連携についての情報。

### GDPR の概要 {#section_8C99434A431B4494998B01B869E7EA5D}

2018年5月26日、欧州連合のGDPRが有効になりました。これにはどのような意味があるのか、詳細は、[GDPR とビジネス](https://www.adobe.com/privacy/general-data-protection-regulation.html)を参照してください。

アドビが企業に対してソフトウェアやサービスを提供する場合、アドビはサービス提供の一環として同社が処理または保管する個人データのデータ処理事業者に該当します。アドビはデータ処理者として、お客様の許可と指示（お客様とアドビとの間で締結された契約の内容など）に従って個人データを処理します。

データ管理者であるお客様は、アドビに処理および保管を委任する個人データを決めます。Adobe Experience Cloud ソリューションをご利用のお客様の場合は、お客様が使用しているソリューションと、お客様が Adobe Experience Cloud アカウントに送信するよう設定した情報に基づいて、アドビは個人データをホストします。詳細な例については、[Adobe Experience Cloud のプライバシー](https://www.adobe.com/privacy/marketing-cloud.html#collect)を参照してください。

Adobe Experience Cloud は データ管理者に GDPR に準拠した API を提供し、GDPR 規則の発行日までに次のタスクを完了することを可能にします。

* Target に保存されているデータサブジェクト情報へのアクセス
* Target に保存されているデータサブジェクト情報の削除

### アドビ一般データ保護規則 API Web サイト {#section_51B8FA3CBE234E9592BDA7083B5CE4CD}

詳しくは、次を参照してください。

* [アドビ一般データ保護規則 API Web サイト](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [GDPR のドキュメント](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## カリフォルニア消費者プライバシー法（CCCPA）の概要

カリフォルニア消費者プライバシー法（CCCPA）は、2020年1月1日に有効です。デザインによって、カリフォルニア州の管理者による調整を行い、詳細を明確にし、自然に多くの質問を持つことがあるということを意味します。お客様の質問がある場合、これだけではないだけでなく、法律上の不信頼性を活用し、法的要件、運用要件、技術的要件に対処するためのアプローチを理解および開発しようとしています。

CCCPAは、カリフォルニア州の消費者に個人情報に関する新しい権利を提供し、カリフォルニアでビジネスを実行する特定エンティティに関するデータ保護の責任を提供します。高レベルでは、法律には、以下の権利を含む、カリフォルニア州のいくつかの主要な権限があります。（1）リクエスト情報（データアクセス）、（2）個人情報（第3者との情報の共有をオプトアウトします）、（3）個人情報の販売をオプトアウトし、（3）個人情報が開示または販売されていることを通知する（4）個人情報を削除すること。

昨年、ヨーロッパのプライバシー法（GGPR）の準備ができていて、これらの権限の一部が使い慣れている可能性があるので、行った作業の多くは、再利用できる可能性があります。

## Adobe Target と Adobe Launch のオプトイン {#section_6F7B53F5E40C4425934627B653E831B0}

Target では、お客様の同意管理戦略を支援できるように、Adobe Launch を介してオプトイン機能がサポートされています。オプトイン機能を使用すると、Target タグを実行する方法とタイミングを制御できます。また、Adobe Launch を介して Target タグを事前に承認するオプションも提供されています。Target の at.js でオプトインを使用する機能を有効にするには、`targetGlobalSettings` を使用し、`optinEnabled=true` 設定を追加する必要があります。Launch では、Target Launch 拡張機能インストール表示の GDPR オプトインドロップダウンリストから「有効」を選択する必要があります。詳しくは、「[Launch のドキュメント](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)」を参照してください。

次のコードスニペットに、`optinEnabled=true` 設定を有効にする方法を示します。

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>オプトイン機能は、at. jsバージョン1.7.0およびat. js2.1.0以降でサポートされています。オプトインは、at. jsバージョン2.0.0および2.0.1ではサポートされていません。
>
>オプトインの管理には、Adobe Launch を使用することをお勧めします。Adobe Launch ではオプトインをきめ細かく制御でき、Target による処理が許可されるまでページ内の特定の要素を非表示にすることができるので、お客様の同意戦略の一環として役立ちます。

オプトインを使用する場合に検討すべきシナリオには、以下の 3 つがあります。

1. **Target タグが Adobe Launch を介して事前に承認されている（またはデータ主体が Target を事前に承認している）：**&#x200B;同意を得られるまで Target タグが保留されることはなく、期待どおりに機能します。
1. **Target タグが事前に承認されていない状態で、`bodyHidingEnabled`が FALSE に設定されている：** Target タグは、お客様から同意が得られるまで実行されません。同意が得られるまでは、デフォルトコンテンツのみを使用できます。同意が得られると Target が呼び出されて、パーソナライズされたコンテンツがデータ主体（訪問者）に対して提供されるようになります。同意が得られるまではデフォルトコンテンツしか使用できないので、適切な戦略を採用することが重要です。例えば、スプラッシュページを使用してページの一部やパーソナライズされる可能性があるコンテンツを覆い隠すことなどを検討してください。これにより、データ主体（訪問者）のエクスペリエンスの一貫性を維持することができます。
1. **Target タグが事前に承認されていない状態で、`bodyHidingEnabled`が TRUE に設定されている：** Target タグは、お客様から同意が得られるまで実行されません。同意が得られるまでは、デフォルトコンテンツのみを使用できます。ただし、`bodyHidingEnabled` が true に設定されているので、Target タグが実行されるまで（またはデータ主体がオプトインを拒否するまで）ページ上で非表示になるコンテンツは `bodyHiddenStyle` によって決定されます。データ主体がオプトインを拒否した場合は、デフォルトコンテンツが表示されます。デフォルトでは、`bodyHiddenStyle` が `body { opacity:0;`} に設定されているので、HTML body タグは非表示になります。以下に、推奨されるページ設定を示します。この設定では、ページのコンテンツを 1 つのコンテナに配置し、同意管理ダイアログを別のコンテナに配置することで、同意管理ダイアログ以外のページ本文全体を非表示にしています。このように Target を設定すると、ページコンテンツのコンテナのみが非表示になります。[これらの設定をおこなう方法については、Adobe Launch のドキュメント](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html)を参照してください。

   次に、3 つ目のシナリオで推奨されるページ設定を示します。

   ```
   <html> 
   <head> 
   //visitor, at.js 
   </head> 
   
   <body> 
   <div id = "consentManagerDialog"> 
   
   //consent manager html dialog goes here 
   </div> 
   
   <div id="pageContent"> 
   // page content goes here 
   </div> 
   
   </body> 
   </html> 
   ```

   `bodyHiddenStyle` は次のように設定されているものとします。

   ```
   #pageContent { opacity:0;}
   ```

## プライバシーおよびデータ保護規則に関するFAQ {#concept_41F88DE95D2943178BEC382736B5C038}

Adobe Targetに固有の一般的なデータ保護規制（GGPR）およびカリフォルニア消費者プライバシー法（CCCPA）に関するよくある質問（FAQ）です。

### これらの規制に関するアドビのポリシーは何ですか。 {#section_A6849628D6524C80A6E16946DC5D25A9}

アドビはデータ処理者としての義務をすでに果たしているかあるいは実施しているところです。アドビは、認定済みのセキュリティとプライバシー制御の確固とした基盤を特に意図して保持しており、2018 年 5 月の期限に先立ち、製品の機能強化を継続していきます。大規模法人のお客様には、これらの機能強化を実装し、必要な方針や手順を更新するという責任があります。

### Will my company, the Data Controller, need to submit a GDPR or CCPA request to each Adobe Experience Cloud solution that it uses? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

いいえ。アドビは、データコントローラーのDGPRおよびCCCPA要件を満たすための一元的な方法を提供しています。データ管理者は、各ソリューションで直接作業する必要はありません。

Targetを含む、Experience Cloudソリューション全体のDGPRおよびCCCPAリクエストは、現在GGPR APIと呼ばれる中央のAdobe APIを通じておこなわれます。この API は、データ管理者の Experience Cloud ソリューションスイートを介して要請を完了します。

### データサブジェクト／ユーザーの要請に応える形で、アドビを利用して顧客が削除できる情報には何がありますか？ {#section_4B51D00924EC4166B2442218B69214F0}

個々の訪問者に関する Target 内の情報は、Target 訪問者プロファイルに格納されています。お客様は、Adobe Target を使用して訪問者プロファイル内の特定 ID に関連づけられたすべてのデータを削除することができます。Adobe Target が保存するプロファイルデータの例については、[訪問者プロファイル](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)を参照してください。

個人を特定しない集約化されたあるいは匿名化されたデータ（レポートデータなど）または特定の個人に関連しないデータ（コンテンツデータなど）は、ユーザーからの削除要請の範疇外となります。

90 日間非アクティブであった Target の訪問者プロファイルは、特に作業をおこなわなくてもデフォルト設定で削除されます。

### What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for Target? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

顧客プロファイルを見つけるために Target がサポートするのは次の ID タイプです。

| ユーザー ID | 名前空間 ID タイプ | 名前空間 ID | 定義 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Adobe Experience Cloud ID（旧名では訪問者 ID または Marketing Cloud ID）。JavaScript API を利用して ID を見つけることができます（詳細は下記を参照してください）。 |
| TnT ID／Cookie ID（TNTID） | Standard | 9 | 訪問者のブラウザーで cookie として設定される Target 識別子。JavaScript API を利用して ID を見つけることができます（詳細は下記を参照してください）。 |
| サードパーティ ID／CRM ID（THIRDPARTYID） | Target-Specific | 該当なし | 顧客の CRM やその他の一意識別子を Target に提供している場合。 |

>[!NOTE]
>
>Adobe Targetはファーストパーティとサードパーティのクロスドメインcookieの両方をサポートしていますが、ファーストパーティのAdobe Target cookieはGGPRおよびCCCPAにのみ推奨されます。

### Adobe Target はどのように同意の管理をおこないますか？{#section_C86BF5EE4FAA47039659850E7594A6BA}

DGPRおよびCCCPAは、同意する必要がある場合に変更されませんが、その取得方法については変更されません。それぞれのお客様の同意戦略は、データ収集と利用の手法およびプライバシーポリシーに左右されます。同意管理は、GGPRおよびCCCPAのTarget経由ではサポートされません。

アドビは現在、同意管理ソリューションは提供していませんが、市場では新たな要件のいくつかに対処するための様々なツールが開発されています。同意管理を含む、プライバシーツール全般に関する詳細については、International Association of Privacy Professionals (iaap) Web サイトの [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) を参照してください。

Adobe Target では、お客様の同意管理戦略を支援できるように、Adobe Launch を介してオプトイン機能がサポートされています。オプトイン機能を使用すると、Adobe Target タグを実行する方法とタイミングを制御できます。また、Adobe Launch を介して Adobe Target タグを事前に承認するオプションも提供されています。オプトインの管理には、Adobe Launch を使用することをお勧めします。Adobe Launch ではオプトインをきめ細かく制御でき、Adobe Target による処理が許可されるまでページ内の特定の要素を非表示にすることができるので、お客様の同意戦略の一環として役立ちます。

For more information on GDPR, CCPA and Adobe Launch, see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). また、上記の「Adobe Target と Adobe Launch のオプトイン」セクションも参照してください。

### AdobePrivacy.js は情報を GDPR API に送信しますか？{#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] は API に情報を&#x200B;*送信しません*。これは、お客様がおこなう必要があります。このライブラリは、特定の訪問者のブラウザーに保存されている ID のみを提供します。

### removeIdentities は何を削除するのですか？{#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities] が削除するのは、ブラウザーからの識別子&#x200B;*のみ*&#x200B;で、Adobe ソリューションが実装したものかどうかによって決まります。

例えば、Target は Target の ID を保存した Cookie を削除しますが、Adobe Audience Manager（AAM）はサードパーティ Cookie に保存された demdex ID は削除しません。

### What information needs to be included in a Target GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

Central Privacy Serviceの要件に加えて、Target向けの有効なGGPRまたはCCCPAメッセージには次のものがあります。

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            "namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            "namespace":"TNTID", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"THIRDPARTYID", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
}
```

### GDPR API を介した Target からの想定される応答には、どのような種類がありますか？{#section_F67263D2A72B4641A47CE36729CCAE8F}

| リクエストのステータス | Target の応答メッセージ | シナリオ |
|--- |--- |--- |
| 処理中 | 処理中 | TargetはGGPRまたはCCCPAリクエストを受け取り、処理中です。 |
| 完了 | 該当なし - 会社のコンテキストは適用できません | GGPRまたはCCCPAリクエストのIMS IDは、Targetクライアントにマッピングされません。<br>一部の会社には複数の IMS ID があることに注意してください。Target がプロビジョニングされた IMS ID を送信する必要があります。 |
| 完了 | 該当なし - ユーザーのコンテキストがありません | 特定の訪問者またはデータの件名に対するGGPRまたはCCCPAリクエストで指定されたIDは、Targetプロファイルストアに存在しません。<br>この結果は、Target でサポートされていない名前空間 ID タイプを送信しようとした場合も返されます（サポートされている ID については、上記を参照してください）。 |
| エラー | エラーメッセージ（詳細はエラーのタイプによって異なります） | 要求されたデータサブジェクトのプロファイルの取得または削除中にエラーが発生しました。<br>アクセス要請のために Azure にアップロード中にエラーが発生しました。 |

### Target は、アクセスの要請に対して GDPR API にどのような応答を送信しますか？{#section_D96D8FBEAF9C4BDAA638215FAFE00763}

データアクセスの要請への応答には、該当する訪問者の Target プロファイルの概要が含まれます。この返信は Experience Cloud GDPR API に送られ、GDPR API がデータ管理者に応答を送信することに注意してください。

Target のアクセス API 応答は次の例のようになります。

```
{ 
    "jobId":"12345AD43E", 
    ... 
    "products":["Target",...], 
    "companyContexts":[ 
        { 
            "namespace":"imsOrgID", 
            "value":"123456789@AdobeOrg" 
        }, 
        ... 
    ], 
    "userContexts":[ 
        { 
            ~"namespace":"ECID", 
            "namespaceId":4, 
            "type":"standard", 
            "value":"53792210477379708453829363835595041181" 
        } 
        And/OR: 
        { 
            ~"namespace":"tntId", 
            "namespaceId":9, 
            "type":"standard", 
            "value":"1234567890" 
        } 
        And/OR: 
        { 
            "namespace":"thirdPartyId", 
            "type":"target", 
            "value":"thirdPartyIdName" 
        }, 
        ... 
    ] 
} 
```

| フィールド | 説明 |
|--- |--- |
| jobId | Central GGPR APIからGGPRまたはCCCPAジョブIDを示します。 |
| imsOrgID | お客様の会社の一意識別子を提供します。 |
| namespace | データソースとも呼ばれます。「顧客がGGPRまたはCCCPAへのアクセスと削除のリクエストを完了するためにサポートされているIDは何ですか?"を参照してください。を参照してください。 |
| type | GGPRまたはCCCPAデータアクセスを要求したIDのタイプ。Target はいくつかの ID タイプを受け付けます。一部は標準的なものですが、その他は Target に特化したものです。「顧客がGGPRまたはCCCPAへのアクセスと削除のリクエストを完了するためにサポートされているIDは何ですか?"を参照してください。を参照してください。 |
| value | 名前空間／データソースの ID。「顧客がGGPRまたはCCCPAへのアクセスと削除のリクエストを完了するためにサポートされているIDは何ですか?"を参照してください。（許容値について） |
| 統合コード | Integration code は、データソースの分かりやすい名前で、データソース ID を使用するより簡単にデータソースの追跡をおこなうことができます。 |

プロファイルを識別するために複数の値が提示される場合、有効な識別子それぞれに 1 つのプロファイルのファイルがあるということです。プロファイルのファイルは、Target プロファイル JSON 応答の形で GDPR Central API を介して中枢 GDPR Azure Blob に送られます。

サンプルの Target プロファイル JSON は次の例のようになります。

```
{"profileAttributes": 
 
"Sample_Parameter":{"value":"Gold Loyalty Status","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"user.ReturnTimeOfDay":{"value":"44.0","modifiedAt":"2018-04-11T21:44:14.000-04:00"}, 
 
"firstSessionStart":{"value":"1523497450602","modifiedAt":"2018-04-11T21:44:10.000-04:00"}, 
 
"user.sessionCountScript":{"value":"1","modifiedAt":"2018-04-11T21:44:14.000-04:00"} 
   } 
} 
```

下の表は、上の例のプロファイル JSON フィールドの説明を含みます。

| フィールド | 説明 |
|--- |--- |
| Sample_Parameter | Target プロファイル内の多数の情報が、データ管理者によってアップロードされるか、直接提供されます。この例では、プロファイル更新 API を利用して Target プロファイルにパラメーターがアップロードされました。詳しくは、[データを Target に送信する方法](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md)を参照してください。 |
| user.ReturnTimeOfDay | この標準的なフィールドには、ユーザーの最後の再訪問の日時が含まれています。 |
| firstSessionStart | この標準的なフィールドには、ユーザーの初めてのセッションが開始された日時が含まれています。 |
| user.sessionCountScript | Target プロファイル内の多数の情報が、データ管理者によってアップロードされるか、直接提供されます。この例では、プロファイルスクリプトが、この訪問者がデータ管理者のサイトで作ったセッション数を増分しています。詳しくは、[プロファイルスクリプト属性](/help/c-target/c-visitor-profile/profile-parameters.md)を参照してください。 |

>[!NOTE]
>
>これは、説明目的で Target プロファイル JSON を短くしたものです。Target プロファイル内の多くのフィールドは標準的なものではありません。何が返ってくるかは、その特定の訪問者のプロファイルに含まれる情報に左右されます。

## Target は IP の不明化に対応していますか？ {#section_428907B0CD9842D9B245B38C66A53C6A}

Targetは、GGPRまたはCCCPAの実装方法の一部として使用する場合、TargetのIPの不明化をサポートします。For more information, see [Privacy](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
