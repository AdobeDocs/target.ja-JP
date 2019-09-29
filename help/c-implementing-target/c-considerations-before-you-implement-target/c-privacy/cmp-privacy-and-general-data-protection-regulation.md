---
description: EUのGDPR(General Data Protection Regulation)、California Consumer Privacy Act(CCPA)、その他の国際プライバシー要件、およびこれらの規制がお客様の組織とAdobe targetに与える影響に関する情報です。
keywords: gdpr;eu;european union;privacy;faq;faq;california consumer privacy act;ccpa;privacy;data protection;opt-out;opt-out;government;regulation
seo-description: EUのGDPR(General Data Protection Regulation)、California Consumer Privacy Act(CCPA)、その他の国際プライバシー要件、およびこれらの規制がお客様の組織とAdobe targetに与える影響に関する情報です。
seo-title: EUのGDPR(General Data Protection Regulation)、California Consumer Privacy Act(CCPA)、その他の国際プライバシー要件、およびこれらの規制がお客様の組織とAdobe targetに与える影響に関する情報です。
solution: Target
title: プライバシーとデータ保護に関する規制
topic: Standard
uuid: 5e67adcf-464c-495f-9ba5-15152d9a6a41
translation-type: tm+mt
source-git-commit: d21838bdf17327b394f6e3106ea5ce4bc72605e6

---


# プライバシーとデータ保護に関する規制 {#privacy-and-general-data-protection-regulation-gdpr}

EUのGDPR(General Data Protection Regulation)、California Consumer Privacy Act(CCPA)、その他の国際プライバシー要件、およびこれらの規制がお客様の組織とAdobe targetに与える影響に関する情報です。

## Privacy and General Data Protection Regulation (GDPR) overview {#topic_DE567ECB6C944695AEE5073889F1AEA9}

2018年5月25日、欧州連合(EU)のGDPRが施行された。 これにはどのような意味があるのか、詳細は、[GDPR とビジネス](https://www.adobe.com/privacy/general-data-protection-regulation.html)を参照してください。

When [!DNL Adobe] is providing software and services to an enterprise, [!DNL Adobe] is acting as a Data Processor for any personal data it processes and stores as part of providing these services. As a Data Processor, [!DNL Adobe] processes personal data in accordance with your company's permission and instructions (for example, as set out in your agreement with [!DNL Adobe]).

As the Data Controller, you determine the personal data that [!DNL Adobe] processes and stores on your behalf. If you use [!DNL Adobe Experience Cloud] solutions, [!DNL Adobe] might host personal data for you, depending on the solutions you use and the information you choose to send to your [!DNL Adobe Experience Cloud] account. 詳細な例については、[Adobe Experience Cloud のプライバシー](https://www.adobe.com/privacy/marketing-cloud.html#collect)を参照してください。

[!DNL Adobe Experience Cloud] 以下のタスクを完了できるGDPR対応のデータ・コントローラ用APIを提供：

*  に保存されているデータサブジェクト情報へのアクセス[!DNL Target]
*  に保存されているデータサブジェクト情報の削除[!DNL Target]

詳しくは、次を参照してください。

* [アドビ一般データ保護規則 API Web サイト](https://www.adobe.io/apis/cloudplatform/gdpr.html)
* [GDPR のドキュメント](https://www.adobe.io/apis/cloudplatform/gdpr/docs.html)

## カリフォルニア消費者プライバシー法(CCPA)の概要

カリフォルニア州消費者プライバシー法(CCPA)は、カリフォルニア州の消費者に対し、個人情報に関する新しい権利を提供し、カリフォルニア州でビジネスを行う特定の事業者に対するデータ保護責任を課します。 2020年1月1日から施行。

高いレベルでは、法律はカリフォルニア州に対して、以下の権利を含むいくつかの主要な権利を与える。

* 情報の要求（データアクセス）
* 個人情報の販売を停止する（第三者との情報の共有を停止する非常に広く定義された権利）
* 個人情報を削除する
* 個人情報が開示または販売されていることを知らせる

昨年ヨーロッパのプライバシー法(GDPR)の準備に忙しかったら、これらの権利の一部は身近なもので、あなたが行った作業の多くは転用できるかもしれません。

## Adobe Target and [!DNL Experience Platform Launch] opt-in {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] は、同意管理戦略をサポートするために、オ [!DNL Launch] プトイン機能をサポートしています。 Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. To enable the ability to use Opt-In in the [!DNL Target] at.js library, you should use `targetGlobalSettings` and add the `optinEnabled=true` setting. In [!DNL Launch] you'll need to select "enable" from the [!UICONTROL GDPR Opt-In] drop-down list in the [!DNL Launch] extension installation view. 詳しくは、「[Launch のドキュメント](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)」を参照してください。

次のコードスニペットに、`optinEnabled=true` 設定を有効にする方法を示します。

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>オプトイン機能は、at.jsバージョン1.7.0およびat.js 2.1.0以降でサポートされています。 オプトインは、at.jsバージョン2.0.0および2.0.1ではサポートされていません。
>
>Using [!DNL Experience Platform Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide selected elements of your page prior to [!DNL Target] firing that are helpful to leverage as part of your consent strategy.

オプトインを使用する場合に検討すべきシナリオには、以下の 3 つがあります。

1. **[!DNL Target]タグ[!DNL Launch]は次を介して事前に承認され[!DNL Target]ています(または、以前に承認されたデータサブジェ**&#x200B;クト)。タグは [!DNL Target] 同意を得るために保持されず、期待どおりに機能します。
1. **[!DNL Target]タグが事前に承認されていない状態で、`bodyHidingEnabled`が FALSE に設定されている：** タグは、お客様から同意が得られるまで実行されません。[!DNL Target]同意が得られるまでは、デフォルトコンテンツのみを使用できます。After consent is received, [!DNL Target] is called and personalized content is available to the data subject (visitor). 同意が得られるまではデフォルトコンテンツしか使用できないので、適切な戦略を採用することが重要です。例えば、スプラッシュページを使用してページの一部やパーソナライズされる可能性があるコンテンツを覆い隠すことなどを検討してください。これにより、データ主体（訪問者）のエクスペリエンスの一貫性を維持することができます。
1. **[!DNL Target]タグが事前に承認されていない状態で、`bodyHidingEnabled`が TRUE に設定されている：** タグは、お客様から同意が得られるまで実行されません。[!DNL Target]同意が得られるまでは、デフォルトコンテンツのみを使用できます。ただし、`bodyHidingEnabled` が true に設定されているので、 タグが実行されるまで（またはデータ主体がオプトインを拒否するまで）ページ上で非表示になるコンテンツは `bodyHiddenStyle` によって決定されます。データ主体がオプトインを拒否した場合は、デフォルトコンテンツが表示されます。[!DNL Target]デフォルトでは、`bodyHiddenStyle` が `body { opacity:0;`} に設定されているので、HTML body タグは非表示になります。以下に、推奨されるページ設定を示します。この設定では、ページのコンテンツを 1 つのコンテナに配置し、同意管理ダイアログを別のコンテナに配置することで、同意管理ダイアログ以外のページ本文全体を非表示にしています。This setup configures [!DNL Target] so that it hides the page content container only. [これらの設定をおこなう方法については、 Launch のドキュメント](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html)を参照してください。

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

## プライバシーとデータ保護に関する規制FAQ {#concept_41F88DE95D2943178BEC382736B5C038}

EUのGDPR(General Data Protection Regulation)、CCPA(California Consumer Privacy Act)、およびTargetに固有のその他の国際プライバシー要件に関するFAQです。

### これらの規制に対するアドビのポリシーは何ですか。 {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] データプロセッサとしての義務を既に満たしているか、実装中であるかのいずれかです。 デルは、設計上、セキュリティおよびプライバシーに関する認定コントロールの強力な基盤を持ち、2018年5月の締め切りに先立って製品の機能を強化しました。 大規模法人のお客様には、これらの機能強化を実装し、必要な方針や手順を更新するという責任があります。

### Will my company, the Data Controller, need to submit a GDPR or CCPA request to each [!DNL Adobe Experience Cloud] solution that it uses? {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

No, [!DNL Adobe] is providing a central way to help Data Controllers meet their GDPR and CCPA requirements. データ管理者は、各ソリューションで直接作業する必要はありません。

All GDPR and CCPA requests across [!DNL Experience Cloud] solutions, including [!DNL Target], will be made through a central Adobe API, currently called the GDPR API. The API will then complete the request across the Data Controller's [!DNL Experience Cloud] solution suite.

### What information will [!DNL Adobe] enable our customers to delete in response to a data subject/user request? {#section_4B51D00924EC4166B2442218B69214F0}

The information related to an individual visitor within [!DNL Target] is contained within the [!DNL Target] Visitor Profile. [!DNL Target]お客様は、 を使用して訪問者プロファイル内の特定 ID に関連づけられたすべてのデータを削除することができます。プロファイルデータストアの例については、「訪 [!DNL Target] 問者プロファイル」を [参照してくださ](../../../c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)い。

個人を特定しない集約化されたあるいは匿名化されたデータ（レポートデータなど）または特定の個人に関連しないデータ（コンテンツデータなど）は、ユーザーからの削除要請の範疇外となります。

[!DNL Target]90 日間非アクティブであった の訪問者プロファイルは、特に作業をおこなわなくてもデフォルト設定で削除されます。

### What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for [!DNL Target]? {#section_F7D0EE4E6A28490FB20056A0D26118BC}

[!DNL Target]顧客プロファイルを見つけるために がサポートするのは次の ID タイプです。

| ユーザー ID | 名前空間 ID タイプ | 名前空間 ID | 定義 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | Adobe Experience Cloud ID（旧名では訪問者 ID または Marketing Cloud ID）。JavaScript API を利用して ID を見つけることができます（詳細は下記を参照してください）。 |
| TnT ID／Cookie ID（TNTID） | Standard | 9 | 訪問者のブラウザーで cookie として設定される Target 識別子。JavaScript API を利用して ID を見つけることができます（詳細は下記を参照してください）。 |
| サードパーティ ID／CRM ID（THIRDPARTYID） | Target-Specific | 該当なし | 顧客の CRM やその他の一意識別子を Target に提供している場合。 |

>[!NOTE]
>
>Although [!DNL Target] supports both first-party and third-party cross-domain cookies, first-party [!DNL Target] cookies only are recommended for GDPR and CCPA.

### How does [!DNL Target] handle consent management? {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR and CCPA do not change when you need to get consent, but how you get it. それぞれのお客様の同意戦略は、データ収集と利用の手法およびプライバシーポリシーに左右されます。Consent management isn’t supported by and shouldn’t be achieved via [!DNL Target] for GDPR and CCPA.

[!DNL Adobe] does not currently offer a Consent Management Solution, but there are various tools developing in the market to address some of the new requirements. For more information on privacy tools in general, including consent managers, see the [2017 Privacy Tech Vendor Report](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) on the *International Association of Privacy Professionals (iaap)* website.

[!DNL Target] は、同意管理戦略のサポートを提供す [!DNL Launch] るために、オプトイン機能をサポートします。 Opt-in functionality lets customers control how and when the [!DNL Target] tag is fired. There is also an option via [!DNL Launch] to pre-approve the [!DNL Target] tag. Using [!DNL Launch] to manage opt-in is the recommended approach. Further granular control exists in [!DNL Launch] to hide select elements of your page prior to the [!DNL Target] firing that might be helpful to leverage as part of your consent strategy.

For more information on GDPR, CCPA, and [!DNL Launch], see [The Adobe Privacy JavaScript Library and GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.html). Also, see the *Adobe Target and Experience Platform Launch opt-in* section above.

### AdobePrivacy.js は情報を GDPR API に送信しますか？{#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] は API に情報を&#x200B;*送信しません*。これは、お客様がおこなう必要があります。このライブラリは、特定の訪問者のブラウザーに保存されている ID のみを提供します。

### removeIdentities は何を削除するのですか？{#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL removeIdentities] が削除するのは、ブラウザーからの識別子&#x200B;*のみ*[!DNL Adobe]で、 ソリューションが実装したものかどうかによって決まります。

For example, [!DNL Target] deletes the cookies storing its IDs, but [!DNL Adobe Audience Manager] (AAM) does not delete the demdex ID that is stored in a third-party cookie.

### What information needs to be included in a Target GDPR or CCPA request? {#section_D29A4744AE6344E68AD7710B185FD6D0}

In addition to the requirements from Central Privacy Service, a valid GDPR or CCPA message for [!DNL Target] contains:

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
| 処理中 | 処理中 | TargetはGDPRまたはCCPA要求を受け取り、処理中です。 |
| 完了 | 該当なし - 会社のコンテキストは適用できません | GDPRまたはCCPA要求内のIMS IDは、どのTargetクライアントにもマッピングされません。<br>一部の会社には複数の IMS ID があることに注意してください。Target がプロビジョニングされた IMS ID を送信する必要があります。 |
| 完了 | 該当なし - ユーザーのコンテキストがありません | 特定の訪問者またはデータサブジェクトに対してGDPRまたはCCPAリクエストで指定されたIDがTargetプロファイルストアに存在しない。<br>この結果は、Target でサポートされていない名前空間 ID タイプを送信しようとした場合も返されます（サポートされている ID については、上記を参照してください）。 |
| エラー | エラーメッセージ（詳細はエラーのタイプによって異なります） | 要求されたデータサブジェクトのプロファイルの取得または削除中にエラーが発生しました。<br>アクセス要請のために Azure にアップロード中にエラーが発生しました。 |

### Target は、アクセスの要請に対して GDPR API にどのような応答を送信しますか？{#section_D96D8FBEAF9C4BDAA638215FAFE00763}

Responses to access data requests contain a summary of the [!DNL Target] profile for the visitor in question. Note that this return is sent to the [!DNL Experience Cloud] GDPR API, which in turn sends Data Controllers a response.

A sample [!DNL Target] access API response could look like this:

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
| jobId | Indicates the GDPR or CCPA job ID from the Central GDPR API. |
| imsOrgID | お客様の会社の一意識別子を提供します。 |
| namespace | データソースとも呼ばれます。See "What IDs are supported to help customers complete a GDPR or CCPA access and deletion request for Target?" を参照してください。 |
| type | The type of ID for which you requested the GDPR or CCPA data access. Target はいくつかの ID タイプを受け付けます。一部は標準的なものですが、その他は Target に特化したものです。「GDPRまたはCCPAのアクセスおよびTargetの削除リクエストを完了する際に役立つIDは何ですか。」を参照してください。 を参照してください。 |
| value | 名前空間／データソースの ID。「GDPRまたはCCPAのアクセスおよびTargetの削除リクエストを完了する際に役立つIDは何ですか。」を参照してください。 （許容値について） |
| 統合コード | Integration code は、データソースの分かりやすい名前で、データソース ID を使用するより簡単にデータソースの追跡をおこなうことができます。 |

プロファイルを識別するために複数の値が提示される場合、有効な識別子それぞれに 1 つのプロファイルのファイルがあるということです。The profile file(s) are sent to the central GDPR Azure Blob through the GDPR Central API, in the format of [!DNL Target] Profile JSON response.

A sample [!DNL Target] Profile JSON could look like the following example:

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
| Sample_Parameter | Many pieces of information in the [!DNL Target] profile are uploaded or directly provided by the Data Controller. In this example, a parameter was uploaded into the [!DNL Target] profile using the Profile Update API. 詳しくは、Targetにデータを取 [得する方法を参照してください](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md)。 |
| user.ReturnTimeOfDay | この標準的なフィールドには、ユーザーの最後の再訪問の日時が含まれています。 |
| firstSessionStart | この標準的なフィールドには、ユーザーの初めてのセッションが開始された日時が含まれています。 |
| user.sessionCountScript | Many pieces of information in the [!DNL Target] profile are uploaded or directly provided by the Data Controller. この例では、プロファイルスクリプトが、この訪問者がデータ管理者のサイトで作ったセッション数を増分しています。詳しくは、[プロファイルスクリプト属性](/help/c-target/c-visitor-profile/profile-parameters.md)を参照してください。 |

>[!NOTE]
>
>This is a shortened version of a [!DNL Target] profile JSON for the purpose of illustration. Many of the fields of the [!DNL Target] profile are not standard. 何が返ってくるかは、その特定の訪問者のプロファイルに含まれる情報に左右されます。

### Target は IP の不明化に対応していますか？ {#section_428907B0CD9842D9B245B38C66A53C6A}

[!DNL Target] は、GDPRまたはCCPAの導入戦略の一部としてIPの不明化を使用する場合に、IPの不明化をサポートします。 For more information, see [Privacy](../../../c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0).
