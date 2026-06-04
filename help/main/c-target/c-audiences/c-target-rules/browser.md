---
keywords: ブラウザーオプション;タイプ;ブラウザータイプ;ブラウザー言語;言語;バージョン;ブラウザーバージョン
description: 特定のブラウザーまたは特定のブラウザーオプションを使用するユーザーがページにアクセスしたときにターゲットにするオーディエンスを [!DNL Adobe Target] で作成する方法について説明します。
title: ブラウザーの種類に基づいて訪問者をターゲティングできますか？
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
TQID: https://experienceleague.adobe.com/D7cLw1OVT61u8SgkjpzEvWylcX1uz14Ia4rf8jAJyXs
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1116
ht-degree: 35%

---

# [!UICONTROL ブラウザー]

ページの訪問時に特定のブラウザーまたは特定のブラウザーオプションを使用しているユーザーをターゲットに設定することができます。

次のブラウザーをターゲットに設定できます。

* [!UICONTROL Chrome]
* [!UICONTROL Firefox]
* [!UICONTROL Safari]
* [!UICONTROL Internet Explorer]
* [!UICONTROL Microsoft Edge]
* [!UICONTROL  オペラ ]
* [!DNL iPad]
* [!DNL iPhone]

>[!IMPORTANT]
>
>[!DNL Target] Standard/Premium 24.3.1 （2024年3月4～6日）以降、`Browser:iPad`や`Browser:iPhone`など、Target UIを使用して作成された組み込みオーディエンスが更新され、`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone`、および`profile.mobile.isTablet`を使用して[!DNL iPad]および[!DNL iPhone]に対して適切なターゲティングが実行されるようになりました。
>
>このアップデートでは、お客様側でのアクションは必要ありません。 [!DNL Target] UIのラベルは今後変更され、これらの変更が行われた際に[[!DNL Target]  リリースノート（最新） ](/help/main/r-release-notes/release-notes.md)に発表されます。
>
>回避策の設定については、以下の[!UICONTROL  ブラウザー]のオーディエンス属性の [!DNL iPad] および [!DNL iPhone] の[更新（2024年4月30日） ](#updates)を参照してください。

ブラウザーをターゲットにするには、2 つの方法があります。

* **事前設計されたオーディエンス：**&#x200B;特定のブラウザーを使用してサイトに訪問している訪問者のみをターゲットにしたい場合、事前設計されたオーディエンスを使用します。 例えば、[!DNL Chrome]拡張機能を提供している場合、[!DNL Chrome]人のユーザーのみをターゲットにします。

   1. アクティビティを設定する際に、ドロップダウンリストからブラウザーを選択します。

      このオプションは、特定のブラウザーを使用する訪問者のみをアクティビティのターゲットにします。

      ![Chrome ユーザーのターゲティング ](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **カスタマイズされたブラウザーのオーディエンス ルール：** カスタマイズされたオーディエンスを使用すると、複数のブラウザーをターゲットにしたり、特定のブラウザー、ブラウザーのバージョン、ブラウザーの言語に対するルールや除外を設定したりできます。 この機能は、ブラウザーの属性に基づいてアクティビティをターゲティングする際に大きな柔軟性を提供します。

   1. [!DNL Target] インターフェイスで、「**[!UICONTROL オーディエンス]**」 > 「**[!UICONTROL オーディエンスを作成]**」をクリックします。
   1. オーディエンスに名前を付け、オプションの説明を追加します。
   1. **[!UICONTROL ブラウザー]**&#x200B;をオーディエンスビルダーにドラッグ&amp;ドロップします。

      ![ ルール > ブラウザー](assets/target_browser.png)

   1. 「**[!UICONTROL 選択]**」をクリックして、次のいずれかのオプションを選択します。

      * **タイプ：**&#x200B;特定のブラウザーをターゲットにするか除外します。 [タイプ](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56)を参照してください。
      * **言語：**&#x200B;特定の言語を使用するように設定されている特定のブラウザーをターゲットまたは除外します。 [言語](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1)を参照してください。
      * **バージョン：**&#x200B;特定のブラウザーのバージョンをターゲットにするか除外します。 [バージョン](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF)を参照してください。

   1. （オプション）オーディエンスの追加ルールを設定します。
   1. 「**[!UICONTROL Done]**」をクリックします。

  次の例は、バージョン 91または92の[!DNL Microsoft Edge] ユーザーを含むオーディエンスを示しています。

  ![Target Edge 91または92](assets/target_edge.png)

## ブラウザーオプション {#concept_221D8EEF53CC45AEACEB17CF336A3658}

ブラウザーのタイプ、言語またはバージョンに基づいてアクティビティ参加者をターゲット化または除外します。

### タイプ {#section_6ADC758F23F145B3A310151546D83D56}

特定のブラウザーをターゲットにするか除外します。

「**[!UICONTROL タイプ]**」を選択して、「次の値と等しい」または「次の値と等しくない」を選択します。

* [!UICONTROL 次と等しい]：選択したブラウザーをターゲットにします。
* [!UICONTROL 次と等しくない]：選択したブラウザーを除外します。

1 つ以上のブラウザーを選択します。 複数のオプションは、OR を使用して接続できます。

### 言語 {#section_7520D1AA464A45A6843EABE2D2B431A1}

特定の言語を使用するように設定されているブラウザーをターゲットにするか除外します。

例えば、オファーが英語でのみ利用できる場合、英語に設定されたブラウザーをターゲットにすることがあります。 または、ページで全角文字が無効な場合、東アジア言語に設定されたブラウザーを除外することがあります。

言語が場所よりも重要な場合、ブラウザーの言語を含めるまたは除外することで、地域に基づくターゲティングよりも正確に訪問者をターゲティングできます。 例えば、英語で記載された記事を提供している場合、英語を話す国をターゲットにするか、英語に設定されたブラウザーをターゲットにすることができます。 ブラウザーをターゲットにすることで、英語が第一言語でない国にいる英語話者に対して記事を提供できます。

「**[!UICONTROL 言語]**」を選択して、「次の値と等しい」または「次の値と等しくない」を選択します。

* [!UICONTROL 次と等しい]：選択したブラウザー言語をターゲットにします。
* [!UICONTROL 次と等しくない]：選択したブラウザー言語を除外します。

1 つ以上の言語を選択します。 複数のオプションは、OR を使用して接続できます。

次のブラウザー言語をターゲットにするか、または除外することができます。

* 英語
* フランス語
* ドイツ語
* 日本語
* 韓国語
* ポルトガル語
* ロシア語
* スペイン語
* 繁体字中国語

### バージョン {#section_37CC8CE45DA04E8682AE6388321BA6EF}

特定のブラウザーのバージョンをターゲットにするか除外します。

例えば、ページが[!DNL Internet Explorer] バージョン 11以前で正しく表示されない場合は、これらのバージョンを除外するオーディエンスを作成できます。 その場合、ブラウザーの種類が[!DNL Internet Explorer]に等しいルールを設定し、バージョンが11以下の2つ目のルールを追加します。

「**[!UICONTROL バージョン]**」を選択して、演算子を選択します。

* [!UICONTROL 次に等しい]
* [!UICONTROL 次と等しくない]
* [!UICONTROL が]より大きい
* 次よりも大きいか等しい
* [!UICONTROL が]より小さい
* [!UICONTROL が]以下

バージョン番号を入力します。 テキストフィールドにはメジャーバージョンのみ入力できます。 指定したバージョンには、そのリリースの任意のマイナーバージョンが含まれます。 例えば、バージョン 10を指定した場合、バージョン 10.1の訪問者も含まれます。

複数のオプションは、OR を使用して接続できます。

## トレーニングビデオ：オーディエンスの作成![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## [!UICONTROL  ブラウザー]のオーディエンス属性の[!DNL iPad]と[!DNL iPhone]の更新（2024年4月30日） {#updates}

[!DNL Adobe Target]を使用すると、特定のブラウザーまたはブラウザーのオプションを使用してページにアクセスしたユーザーを含む、複数のカテゴリ属性](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)のいずれかを[ ターゲットにできます。

[!DNL Target] Standard/Premium 24.3.1 （2024年3月4～6日）以降、`Browser:iPad`や`Browser:iPhone`など、Target UIを使用して作成された組み込みオーディエンスが更新され、`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone`および`profile.mobile.isTablet`を使用して[!DNL iPad]および[!DNL iPhone]に適切なターゲティングが実行されるようになりました。

[!DNL Target] UIを使用して作成された組み込みオーディエンス（`Browser:iPad`や`Browser:iPhone`など）は、新しいオーディエンス定義に自動的に移動され、顧客側での操作は必要ありません。 ただし、今後は、以下の設定[を使用する必要があります](#ui)。

任意のプロファイルスクリプトで`user.browserType`を使用して[!DNL iPhone]または[!DNL iPad] （例：`user.browserType == 'iphone'`または`user.browserType != 'ipad'`）であるかどうかを確認する場合、これらのオーディエンスが期待どおりに機能し続けるように、2024年4月30日までに、これらのプロファイルスクリプトを[以下の指示](#profile-scripts)に変更する必要があります。

JavaScript オーディエンスは、[!DNL Target Classic] UIで非推奨となった[!DNL Target]式を使用するレガシーオーディエンスです。 これらのオーディエンスは、API経由でのみ変更できます。 顧客は、アクティビティで従来のオーディエンスを引き続き使用する場合にのみ、これらのオーディエンスを更新する必要があります。

### [!DNL Target] UIを使用して作成されたオーディエンス {#ui}

今後は次の設定を使用できます。

* **ブラウザーが[!DNL Apple]**&#x200B;に一致：[!UICONTROL  モバイル ] > [!UICONTROL  デバイスベンダー] [!UICONTROL 一致] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **ブラウザーがタブレット**&#x200B;と一致する場合：[!UICONTROL  モバイル ] > [!UICONTROL はタブレット ] > [!UICONTROL true]です

  ![モバイルはタブレットです](/help/main/r-release-notes/assets/is-tablet.png)

* **For browser matches iPad**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPad] with an And container with [!UICONTROL Mobile] > [!UICONTROL Is Tablet] is [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **For browser matches iPhone**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPhone] with an And container with [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] is [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

条件が無効になっている場合など、他にも使用できる設定が多数あります。 否定された条件の例は次のようになります。

* **For browser does not match iPhone**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL が] [!UICONTROL Apple]と[!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone]のOr コンテナが[!UICONTROL false]に一致しません

  ![携帯電話ではありません](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **For browser does not match iPad**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL が] [!UICONTROL Apple]と[!UICONTROL Mobile] > [!UICONTROL Is Tablet]のOr コンテナが[!UICONTROL false]に一致しません。

  ![ タブレットではありません](/help/main/r-release-notes/assets/tablet-false.png)

### プロファイルスクリプトを使用して作成されたオーディエンス {#profile-scripts}

レガシー[!DNL Target Classic] オーディエンスまたはプロファイルスクリプトで`user.browserType`を使用する場合、変更には次のものが含まれる必要があります。

* **BrowserTypeはiPhone**&#x200B;です：

  置き換え：

  `user.browserType=="iphone"`

  次の使用条件：

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isMobilePhone`

* **BrowserTypeはiPhoneではありません**:

  置き換え：

  `user.browserType!="iphone"`

  次の使用条件：

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isMobilePhone`

* **BrowserTypeはiPad**&#x200B;です：

  置き換え：

  `user.browserType=="ipad"`

  次の使用条件：

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isTablet`

* **BrowserTypeはiPadではありません**:

  置き換え：

  `user.browserType!="ipad"`

  次の使用条件：

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isTablet`