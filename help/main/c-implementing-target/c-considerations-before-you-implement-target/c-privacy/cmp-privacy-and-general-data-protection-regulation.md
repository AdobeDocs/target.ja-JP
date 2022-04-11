---
keywords: gdpr;eu;欧州連合;プライバシー;faq;よくある質問;カリフォルニア州消費者プライバシー法;ccpa;プライバシー;データ 保護;オプトアウト;政府;規制
description: 詳細 [!DNL Target] および欧州連合 (EU) 一般データ保護規則 (GDPR)、カリフォルニア州消費者プライバシー法 (CCPA) およびその他のプライバシー要件に関する情報をまとめています。
title: 方法 [!DNL Target] プライバシーとデータ保護規制の処理
feature: Privacy & Security
role: Developer
exl-id: 5013a9d2-a463-4787-90ee-3248d9cb02b2
source-git-commit: 2dad7d51935cd1550f60218e63277b84ce9088ac
workflow-type: tm+mt
source-wordcount: '2209'
ht-degree: 54%

---

# プライバシーとデータ保護規制

欧州連合 (EU) の一般データ保護規則 (GDPR)、カリフォルニア州消費者プライバシー法 (CCPA) およびその他の国際的なプライバシー要件に関する情報です。 これらの規制が組織に及ぼす影響と [!DNL Adobe Target].

## プライバシーと一般データ保護規則（GDPR）の概要 {#topic_DE567ECB6C944695AEE5073889F1AEA9}

2018 年 5 月 25 日に、欧州連合の GDPR が発効されました。この規則が何を意味するかについて詳しくは、 [GDPR とビジネス](https://business.adobe.com/privacy/general-data-protection-regulation.html).

[!DNL Adobe] が企業に対してソフトウェアやサービスを提供する場合、[!DNL Adobe] はサービス提供の一環として同社が処理または保管する個人データのデータ処理事業者に該当します。[!DNL Adobe] はデータ処理者として、お客様の許可と指示（お客様と [!DNL Adobe] との間で締結された契約の内容など）に従って個人データを処理します。

データ管理者であるお客様は、[!DNL Adobe] に処理および保管を委任する個人データを決めます。[!DNL Adobe Experience Cloud] ソリューションをご利用のお客様の場合は、お客様が使用しているソリューションと、お客様が [!DNL Adobe Experience Cloud] アカウントに送信するよう設定した情報に基づいて、[!DNL Adobe] は個人データをホストします。詳細な例については、[Adobe Experience Cloud のプライバシー](https://www.adobe.com/privacy/experience-cloud.html#collect)を参照してください。

[!DNL Adobe Experience Cloud] にはデータ管理者向けの GDPR に対応した API が用意されており、これらを使用して次のタスクを実行できます。

* [!DNL Target] に保存されているデータ主体情報へのアクセス
* [!DNL Target] に保存されているデータ主体情報の削除

詳しくは、次を参照してください。

* [AdobePrivacy Serviceの概要](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html){target=-blank}
* [Privacy ServiceAPI ガイド](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html){target=_blank}
* [Privacy ServiceUI の概要](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html){target=_blank}

## カリフォルニア州消費者プライバシー法（CCPA）の概要

カリフォルニア州消費者プライバシー法（CCPA）は、カリフォルニア州の消費者に個人情報に関する新しい権利を提供し、カリフォルニア州でビジネスをおこなう特定の事業者に対してデータ保護の責任を課します。CCPA は 2020 年 1 月 1 日に施行されました。

概要としては、この法律は、カリフォルニアの人々に次の権利を含む、いくつかの主要な権利を提供します。

* 要求情報（データアクセス）
* 個人情報の販売のオプトアウト（サードパーティとの情報の共有をオプトアウトするために広く定義された権利）
* 個人情報を削除させる
* 個人情報が公開または販売されたことを知る

昨年の欧州のプライバシー法 (GDPR) の準備に取り組んでいた場合、これらの権利の一部に精通している可能性があり、おこなった作業の多くは再利用できます。

>[!NOTE]
>
>CCPA に適用されるデータへのアクセスと削除は、GDPR の場合と同じ手順に従います。

## Adobe [!DNL Target] および [!DNL Adobe Experience Platform] オプトイン {#section_6F7B53F5E40C4425934627B653E831B0}

[!DNL Target] では、 [!DNL Adobe Experience Platform] 同意管理戦略を支援する。 オプトイン機能を使用すると、[!DNL Target] タグを実行する方法とタイミングを制御できます。また、[!DNL Adobe Experience Platform] を介して [!DNL Target] タグを事前に承認するオプションも提供されています。[!DNL Target] の at.js ライブラリでオプトインを使用する機能を有効にするには、`targetGlobalSettings` を使用し、`optinEnabled=true` 設定を追加する必要があります。In [!DNL Adobe ExperiencePlatform]、「有効にする」を [!UICONTROL GDPR Opt-In] 拡張機能のインストール表示のドロップダウンリスト。 詳しくは、 [実装方法 [!DNL Target] using [!DNL Adobe Experience Platform]](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) を参照してください。

次のコードスニペットに、`optinEnabled=true` 設定を有効にする方法を示します。

```
window.targetGlobalSettings = {
  optinEnabled: true
};
```

>[!NOTE]
>
>オプトイン機能は、at.js バージョン 1.7.0 および at.js 2.1.0 以降でサポートされます。オプトインは、at.js バージョン 2.0.0 および 2.0.1 ではサポートされていません。
>
>オプトインの管理には、[!DNL Adobe Experience Platform] を使用することをお勧めします。より詳細な制御は、 [!DNL Adobe Experience Platform] 選択した要素を前に非表示にするには [!DNL Target] の実行を使用することをお勧めします。

オプトインを使用する場合に検討すべきシナリオには、以下の 3 つがあります。

1. **[!DNL Target] タグが [!DNL Adobe Experience Platform] を介して事前に承認されている（またはデータ主体が [!DNL Target] を事前に承認している）：**&#x200B;同意を得られるまで [!DNL Target] タグが保留されることはなく、期待どおりに機能します。
1. **[!DNL Target] タグが事前に承認されていない状態で、`bodyHidingEnabled` が FALSE に設定されている：**[!DNL Target] タグは、お客様から同意が得られるまで実行されません。同意が得られるまでは、デフォルトコンテンツのみを使用できます。同意が得られると [!DNL Target] が呼び出されて、パーソナライズされたコンテンツがデータ主体（訪問者）に対して提供されるようになります。同意の前にはデフォルトコンテンツしか利用できないので、適切な方法（ページの一部をカバーするスプラッシュページや、パーソナライズする可能性のあるコンテンツなど）を使用することが重要です。 このプロセスにより、データ主体（訪問者）に対してエクスペリエンスの一貫性を維持できます。
1. **[!DNL Target] タグが事前に承認されていない状態で、`bodyHidingEnabled` が TRUE に設定されている：**[!DNL Target] タグは、お客様から同意が得られるまで実行されません。同意が得られるまでは、デフォルトコンテンツのみを使用できます。ただし、`bodyHidingEnabled` が true に設定されているので、[!DNL Target] タグが実行されるまで（またはデータ主体がオプトインを拒否するまで）ページ上で非表示になるコンテンツは `bodyHiddenStyle` によって決定されます。データ主体がオプトインを拒否した場合は、デフォルトコンテンツが表示されます。デフォルトでは、 `bodyHiddenStyle` が `body { opacity:0;}`を呼び出し、HTMLbody タグを非表示にします。 Adobeで推奨されるページ設定を次に示します。この場合、同意管理ダイアログ以外のページ本文全体を非表示にするには、ページの内容を 1 つのコンテナに、同意管理ダイアログを別のコンテナに配置します。 このように [!DNL Target] を設定すると、ページコンテンツのコンテナのみが非表示になります。詳しくは、 [Privacy Serviceの概要](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en).

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

## プライバシーとデータ保護規制 FAQ {#concept_41F88DE95D2943178BEC382736B5C038}

欧州連合 (EU) の一般データ保護規則 (GDPR)、カリフォルニア州消費者プライバシー法 (CCPA) および次に特有のその他の国際的なプライバシー要件に関するよくある質問 [!DNL Target].

### 概要 [!DNL Adobe] これらの規制に対する方針は？ {#section_A6849628D6524C80A6E16946DC5D25A9}

[!DNL Adobe] は、データ処理者としての義務を既に果たしているか、または履行中です。 Adobeは、2018 年 5 月の締め切りまでに、認定済みのセキュリティとプライバシー制御の強力な基盤を設計し、製品の機能強化をおこないました。 企業のお客様は、これらの機能強化を実装し、必要なポリシーや手順を更新する責任を負います。

### データ管理者である自社が、各自に GDPR または CCPA 要求を送信する必要がある [!DNL Adobe Experience Cloud] 使用するソリューションは？ {#section_1DCFA9387D0C4506B14DCE04C49AC22A}

いいえ、 [!DNL Adobe] は、データ管理者が GDPR および CCPA の要件を満たすのに役立つ一元化された方法を提供します。 データ管理者は、各ソリューションに直接アクセスする必要はありません。

をまたいだすべての GDPR および CCPA リクエスト [!DNL Experience Cloud] ソリューション： [!DNL Target]は、 [!DNL Adobe] API。現在、GDPR API と呼ばれています。 次に、API は、データ管理者の [!DNL Experience Cloud] ソリューションスイート。

### 情報の機能 [!DNL Adobe] データ主体/ユーザーの要求に応じて、顧客がを削除できるようにしますか？ {#section_4B51D00924EC4166B2442218B69214F0}

個々の訪問者に関する [!DNL Target] 内の情報は、[!DNL Target] 訪問者プロファイルに格納されています。[!DNL Target] を使用すると、顧客は訪問者プロファイルで ID に関連付けられているすべてのデータを削除できます。 プロファイルデータ [!DNL Target] ストアの例については、[訪問者プロファイル](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)を参照してください。

個人を特定しない集計されたデータや匿名化されたデータ（レポートデータなど）、または特定の個人に関連しないデータ（コンテンツデータなど）は、ユーザーからの削除要求の対象外です。

90 日間非アクティブであった [!DNL Target] の訪問者プロファイルは、特に作業をおこなわなくてもデフォルト設定で削除されます。

### [!DNL Target] で顧客が GDPR または CCPA のアクセスおよび削除要求をおこなうには、どのような ID を利用できますか？{#section_F7D0EE4E6A28490FB20056A0D26118BC}

顧客プロファイルを見つけるために [!DNL Target] がサポートするのは、次の ID タイプです。

| ユーザー ID | 名前空間 ID タイプ | 名前空間 ID | 定義 |
|--- |--- |--- |--- |
| Experience Cloud ID (ECID) | Standard | 4 | [!UICONTROL Adobe Experience Cloud ID]：旧称：訪問者 ID またはExperience CloudID。 JavaScript API を利用して ID を見つけることができます（詳細は下記を参照してください）。 |
| TnT ID／Cookie ID（TNTID） | 標準 | 9 | [!DNL Target]訪問者のブラウザーで cookie として設定される 識別子。JavaScript API を利用して ID を見つけることができます（詳細は下記を参照してください）。 |
| サードパーティ ID／CRM ID（THIRDPARTYID） | [!DNL Target]-特定の | 該当なし | 次を指定する場合： [!DNL Target] CRM や、顧客の一意の識別子情報を含む |

>[!NOTE]
>
>[!DNL Target] では、ファーストパーティとサードパーティのクロスドメイン Cookie が両方ともサポートされていますが、GDPR および CCPA を確実に順守するには、ファーストパーティの [!DNL Target] Cookie のみを使用することをお勧めします。

### [!DNL Target] はどのように同意の管理をおこないますか？ {#section_C86BF5EE4FAA47039659850E7594A6BA}

GDPR および CCPA では、いつ同意を得る必要があるかに関する変更はありませんが、同意の取得方法が変更されます。 各顧客の同意戦略は、データ収集と使用の方法とプライバシーポリシーに依存します。 [!DNL Target] では、GDPR および CCPA に対する同意の管理をサポートしておらず、またそれを実現すべきではありません。

[!DNL Adobe] では、現在、同意管理ソリューションは提供していませんが、市場では新たな要件のいくつかに対処するための様々なツールが開発されています。同意管理者を含む、プライバシーツール全般について詳しくは、 [2017 年プライバシーテクニカルベンダーレポート](https://iapp.org/media/pdf/resource_center/Tech-Vendor-Directory-1.4.1-electronic.pdf) の *国際プライバシープロフェッショナル協会 (IAAP)* web サイト。

[!DNL Target] は、 [!DNL Adobe Experience Platform] 同意管理戦略を支援する。 オプトイン機能を使用すると、[!DNL Target] タグを実行する方法とタイミングを制御できます。また、[!DNL Adobe Experience Platform] を介して [!DNL Target] タグを事前に承認するオプションも提供されています。オプトインの管理には、[!DNL Adobe Experience Platform] を使用することをお勧めします。より詳細な制御は、 [!DNL Adobe Experience Platform] ページの選択した要素を、ページの前に非表示にするには [!DNL Target] の実行を使用することをお勧めします。

GDPR、CCPA、 [!DNL Adobe Experience Platform]を参照してください。 [Adobeのプライバシーに関する JavaScript ライブラリと GDPR](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en). また、 *Adobe TargetとAdobe Experience Platformのオプトイン* 」の節を参照してください。

### `AdobePrivacy.js` は情報を GDPR API に送信しますか？ {#section_1EB8A2BAAD31474C97C1D455F41DA739}

[!DNL AdobePrivacy.js] は API に情報を&#x200B;*送信しません*。これは、お客様がおこなう必要があります。このライブラリは、特定の訪問者のブラウザーに保存されている ID のみを提供します。

### 機能 `removeIdentities` 削除しますか？ {#section_D3A1591EA1B84C499CE1563DEAF32448}

[!DNL `removeIdentities`] が削除するのは、ブラウザーからの識別子&#x200B;*のみ*&#x200B;で、[!DNL Adobe] ソリューションが実装したものかどうかによって決まります。

例えば、[!DNL Target] は ID を保存した Cookie を削除しますが、[!DNL Adobe Audience Manager]（AAM）はサードパーティ Cookie に保存された demdex ID は削除しません。

### に含める必要のある情報 [!DNL Target] GDPR または CCPA のリクエスト {#section_D29A4744AE6344E68AD7710B185FD6D0}

Central Privacy Service からの要件に加えて、[!DNL Target] の有効な GDPR または CCPA メッセージには次のものが含まれます。

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

### 期待できる応答のタイプ [!DNL Target] GDPR API を使用する {#section_F67263D2A72B4641A47CE36729CCAE8F}

| 要求のステータス | [!DNL Target] 応答メッセージ | シナリオ |
|--- |--- |--- |
| 処理中 | 処理中 | [!DNL Target] は GDPR または CCPA 要求を受信し、処理中です。 |
| 完了 | 該当なし - 会社のコンテキストは適用できません | GDPR または CCPA 要求の IMS ID は、 [!DNL Target] クライアント。<br>一部の会社には複数の IMS ID があります。 次の場合に IMS ID を送信します。 [!DNL Target] がプロビジョニングされている。 |
| 完了 | 該当なし - ユーザーのコンテキストがありません | GDPR または CCPA 要求で提供された、特定の訪問者またはデータ主体の ID は、 [!DNL Target] プロファイルストア。<br>この結果は、でサポートされていない名前空間 ID タイプを送信しようとした場合も返されます。 [!DNL Target] （サポートされる ID については、上記を参照）。 |
| エラー | エラーメッセージ（詳細はエラーのタイプによって異なります） | 要求されたデータ主体のプロファイルの取得または削除中にエラーが発生しました。<br>アクセス要求のために Azure にアップロード中にエラーが発生しました。 |

### 応答の内容 [!DNL Target] を GDPR API に送信してアクセス要求を受け取る場合 {#section_D96D8FBEAF9C4BDAA638215FAFE00763}

データアクセスの要求への応答には、該当する訪問者の [!DNL Target] プロファイルの概要が含まれます。この返信は [!DNL Experience Cloud] GDPR API は、データ管理者に応答を送信します。

[!DNL Target] のアクセス API 応答の例を次に示します。

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
| jobId | Central GDPR API からの GDPR または CCPA のジョブ ID を示します。 |
| imsOrgID | お客様の会社の一意識別子を提供します。 |
| namespace | データソースとも呼ばれます。詳しくは、「 [!DNL Target]?」 を参照してください。 |
| type | GDPR または CCPA データアクセスを要求した ID のタイプ。[!DNL Target] は複数の ID タイプを受け入れます。一部は標準で、一部はに固有です。 [!DNL Target]. 詳しくは、「 [!DNL Target]?」 を参照してください。 |
| value | 名前空間／データソースの ID。詳しくは、「 [!DNL Target]?」 を参照してください。 |
| 統合コード | Integration code は、データソースの分かりやすい名前で、データソース ID を使用するより簡単にデータソースの追跡をおこなうことができます。 |

プロファイルを識別するために複数の値が提示される場合、有効な識別子それぞれに 1 つのプロファイルのファイルがあるということです。1 つ以上のプロファイルファイルが、GDPR Central API を通じての形式で一元化された GDPR Azure Blob に送信されます。 [!DNL Target] プロファイル JSON 応答。

サンプルの [!DNL Target] プロファイル JSON は次の例のようになります。

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
| Sample_Parameter | [!DNL Target] プロファイル内の情報の多くが、データ管理者によってアップロードされるか、直接提供されます。この例では、プロファイル更新 API を利用して [!DNL Target] プロファイルにパラメーターがアップロードされました。詳しくは、[データを に送信する方法 [!DNL Target]](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md)を参照してください。 |
| user.ReturnTimeOfDay | この標準的なフィールドには、ユーザーの最後の再訪問の日時が含まれています。 |
| firstSessionStart | この標準的なフィールドには、ユーザーの初めてのセッションが開始された日時が含まれています。 |
| user.sessionCountScript | [!DNL Target] プロファイル内の情報の多くが、データ管理者によってアップロードされるか、直接提供されます。この例では、プロファイルスクリプトが、この訪問者がデータ管理者のサイトでおこなったセッション数を増分しています。詳しくは、[プロファイルスクリプト属性](/help/main/c-target/c-visitor-profile/profile-parameters.md)を参照してください。 |

>[!NOTE]
>
>このコードサンプルは、 [!DNL Target] profile JSON を参照してください。 [!DNL Target] プロファイルのフィールドの多くは、標準的なものではありません。何が返ってくるかは、その特定の訪問者のプロファイルに含まれる情報に左右されます。

### 実行 [!DNL Target] IP の不明化をサポートしますか？ {#section_428907B0CD9842D9B245B38C66A53C6A}

GDPR または CCPA 実装戦略の一部として使用するように選択した場合、[!DNL Target] は IP の不明化をサポートします。詳しくは、[プライバシー](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md#concept_639482A343DB4963A6144378E1D8D7F0)を参照してください。

### データがサードパーティに共有または販売されるのを防ぐために何らかの処理をおこなう必要がありますか？

[!DNL Target] 顧客が直接データを共有または販売することを許可しない [!DNL Target] サードパーティへのオプトアウトの場合は、 [!DNL Target].
