---
keywords: ブラウザーオプション;タイプ;ブラウザータイプ;ブラウザー言語;言語;バージョン;ブラウザーバージョン
description: でオーディエンスを作成する方法を説明します。 [!DNL Adobe Target] を使用して、ページの訪問時に特定のブラウザーまたは特定のブラウザーオプションを使用しているユーザーをターゲットに設定することができます。
title: ブラウザータイプに基づいて訪問者をターゲットに設定することはできますか？
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 784f41a73941877135a5902f2331972ba9d0e880
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 33%

---

# [!UICONTROL Browser]

ページの訪問時に特定のブラウザーまたは特定のブラウザーオプションを使用しているユーザーをターゲットに設定することができます。

次のブラウザーをターゲットに設定できます。

* [!UICONTROL Chrome]
* [!UICONTROL Firefox]
* [!UICONTROL Safari]
* [!UICONTROL Internet Explorer]
* [!UICONTROL Microsoft Edge]
* [!UICONTROL Opera]
* [!DNL iPad]
* [!DNL iPhone]

>[!IMPORTANT]
>
>の使用を開始する [!DNL Target] Standard/Premium 24.3.1（2024 年 3 月 4～6 日）:Target UI を使用して作成された組み込みオーディエンス ( 例： `Browser:iPad` および `Browser:iPhone` 適切なターゲティングを行うように更新された [!DNL iPad] および [!DNL iPhone] using `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone`、および `profile.mobile.isTablet`.
>
>この更新では、お客様側での操作は必要ありません。 のラベル [!DNL Target] UI は今後変更され、 [[!DNL Target] リリースノート（現行）](/help/main/r-release-notes/release-notes.md) 変更を加えたとき。
>
>回避策の設定については、 [の更新 [!DNL iPad] および [!DNL iPhone] in [!UICONTROL Browser] オーディエンス属性（2024 年 4 月 31 日）](#updates) 下

ブラウザーをターゲットにするには、2 つの方法があります。

* **事前設計されたオーディエンス：**&#x200B;特定のブラウザーを使用してサイトに訪問している訪問者のみをターゲットにしたい場合、事前設計されたオーディエンスを使用します。例えば、 [!DNL Chrome] 拡張機能の場合は、ターゲットにするのはのみです。 [!DNL Chrome] ユーザー。

   1. アクティビティを設定する際に、ドロップダウンリストからブラウザーを選択します。

      このオプションは、特定のブラウザーを使用する訪問者のみをアクティビティのターゲットにします。

      ![Chrome ユーザーのターゲット設定](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **カスタマイズされたブラウザーオーディエンスルール：** カスタマイズされたオーディエンスを使用すると、複数のブラウザーをターゲットにしたり、特定のブラウザー、ブラウザーのバージョンまたはブラウザーの言語に対するルールや除外を設定したりできます。 この機能は、ブラウザー属性に基づいてアクティビティをターゲット設定する際に、大幅な柔軟性を提供します。

   1. Adobe Analytics の [!DNL Target] インタフェース、クリック **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
   1. オーディエンスに名前を付け、オプションで説明を追加します。
   1. ドラッグ&amp;ドロップ **[!UICONTROL Browser]** を Audience Builder に貼り付けます。

      ![ルール/ブラウザー](assets/target_browser.png)

   1. クリック **[!UICONTROL Select]**&#x200B;次のいずれかのオプションを選択します。

      * **タイプ：**&#x200B;特定のブラウザーをターゲットにするか除外します。[タイプ](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56)を参照してください。
      * **言語：** 特定の言語を使用するように設定されているブラウザーをターゲットにするか除外します。 [言語](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1)を参照してください。
      * **バージョン：**&#x200B;特定のブラウザーのバージョンをターゲットにするか除外します。[バージョン](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF)を参照してください。

   1. （オプション）オーディエンス用の追加のルールを設定します。
   1. **[!UICONTROL Done]** をクリックします。

  次の例は、 [!DNL Microsoft Edge] バージョン 91 または 92 のユーザー：

  ![Target Edge 91 または 92](assets/target_edge.png)

## ブラウザーオプション {#concept_221D8EEF53CC45AEACEB17CF336A3658}

ブラウザーのタイプ、言語またはバージョンに基づいてアクティビティ参加者をターゲット化または除外します。

### タイプ {#section_6ADC758F23F145B3A310151546D83D56}

特定のブラウザーをターゲットにするか除外します。

選択 **[!UICONTROL Type]**「等しい」または「等しくない」を選択します。

* [!UICONTROL Equals]：選択したブラウザーをターゲットにします。
* [!UICONTROL Does not equal]：選択したブラウザーを除外します。

1 つ以上のブラウザーを選択します。複数のオプションは、OR を使用して接続できます。

### 言語 {#section_7520D1AA464A45A6843EABE2D2B431A1}

特定の言語を使用するように設定されているブラウザーをターゲットにするか除外します。

例えば、オファーが英語でのみ利用できる場合、英語に設定されたブラウザーをターゲットにすることがあります。または、ページで全角文字が無効な場合、東アジア言語に設定されたブラウザーを除外することがあります。

言語が場所よりも重要な場合、ブラウザーの言語を含めるまたは除外することで、地域に基づくターゲティングよりも正確に訪問者をターゲティングできます。例えば、英語で記載された記事を提供している場合、英語を話す国をターゲットにするか、英語に設定されたブラウザーをターゲットにすることができます。ブラウザーをターゲットにすることで、英語が第一言語でない国にいる英語話者に対して記事を提供できます。

選択 **[!UICONTROL Language]**「等しい」または「等しくない」を選択します。

* [!UICONTROL Equals]：選択したブラウザーの言語をターゲットにします。
* [!UICONTROL Does not equal]：選択したブラウザーの言語を除外します。

1 つ以上の言語を選択します。複数のオプションは、OR を使用して接続できます。

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

例えば、ページが [!DNL Internet Explorer] バージョン 11 以前では、これらのバージョンを除外するオーディエンスを作成できます。 この場合、ブラウザーのタイプが [!DNL Internet Explorer] バージョンが 11 以下の 2 つ目のルールを追加します。

選択 **[!UICONTROL Version]**、「 」、「 」、「 」、「 」、「 」、「 」、「 」、「 」、「 」、「 」、「 」、「 」、「 」、「 」、「 」、「 」、「 」の演算子を選択します。

* [!UICONTROL Equals]
* [!UICONTROL Does not equal]
* [!UICONTROL Is greater than]
* 次よりも大きいか等しい
* [!UICONTROL Is less than]
* [!UICONTROL Is less than or equal to]

バージョン番号を入力します。 テキストフィールドにはメジャーバージョンのみ入力できます。指定したバージョンには、そのリリースの任意のマイナーバージョンが含まれます。例えば、バージョン 10 を指定した場合、バージョン 10.1 の訪問者も含まれます。

複数のオプションは、OR を使用して接続できます。

## トレーニングビデオ：オーディエンスの作成 ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## の更新 [!DNL iPad] および [!DNL iPhone] in [!UICONTROL Browser] オーディエンス属性（2024 年 4 月 31 日） {#updates}

[!DNL Adobe Target] 以下が可能です。 [複数のカテゴリ属性のいずれかに対するターゲット](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)（ページの訪問時に特定のブラウザーまたはブラウザーオプションを使用しているユーザーを含む）

の使用を開始する [!DNL Target] Standard/Premium 24.3.1（2024 年 3 月 4～6 日）:Target UI を使用して作成された組み込みオーディエンス ( 例： `Browser:iPad` および `Browser:iPhone` 適切なターゲティングを行うように更新された [!DNL iPad] および [!DNL iPhone] using `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` および `profile.mobile.isTablet`.

を使用して作成された組み込みオーディエンス [!DNL Target] UI（例： ） `Browser:iPad` および `Browser:iPhone`は、自動的に新しいオーディエンス定義に移動され、顧客側での操作は不要です。 ただし、今後は、次の設定を使用する必要があります。 [以下に説明します](#ui).

次を使用する場合、 `user.browserType` 任意のプロファイルスクリプトで、 [!DNL iPhone] または [!DNL iPad] ( 例： `user.browserType == 'iphone'` または `user.browserType != 'ipad'`) の場合、これらのプロファイルスクリプトは次のように変更する必要があります。 [次に示す](#profile-scripts) 2024 年 4 月 30 日より前に更新され、これらのオーディエンスが引き続き期待どおりに機能するようになります。

JavaScript オーディエンスは、 [!DNL Target] で廃止された式 [!DNL Target Classic] UI これらのオーディエンスは、API 経由でのみ変更できます。 アクティビティで従来のオーディエンスを引き続き使用する場合にのみ、これらのオーディエンスを更新する必要があります。

### を使用して作成されたオーディエンス [!DNL Target] UI {#ui}

今後は、次の設定を使用できます。

* **ブラウザーの一致の場合[!DNL Apple]**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL matches] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **ブラウザー一致タブレットの場合**: [!UICONTROL Mobile] > [!UICONTROL is Tablet] > [!UICONTROL true]

  ![モバイルはタブレットです](/help/main/r-release-notes/assets/is-tablet.png)

* **ブラウザがiPadに一致する場合**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPad] を含む And コンテナ [!UICONTROL Mobile] > [!UICONTROL Is Tablet] 次に該当 [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **ブラウザがiPhoneに一致する場合**: [!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPhone] を含む And コンテナ [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] 次に該当 [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

条件が無効な場合など、他にも多くの設定が使用可能です。 否定条件の例を次に示します。

* **ブラウザーがiPhoneと一致しません**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] OR コンテナが [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] 次に該当 [!UICONTROL false]

  ![携帯電話ではありません](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **ブラウザーがiPadと一致しません**: [!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] OR コンテナが [!UICONTROL Mobile] > [!UICONTROL Is Tablet] 次に該当 [!UICONTROL false].

  ![タブレットではありません](/help/main/r-release-notes/assets/tablet-false.png)

### プロファイルスクリプトを使用して作成されたオーディエンス {#profile-scripts}

次を使用する場合、 `user.browserType` 従来の [!DNL Target Classic] オーディエンスまたはプロファイルスクリプトでは、変更に次の内容を含める必要があります。

* **BrowserType はiPhone**:

  置換：

  `user.browserType=="iphone"`

  次を使用：

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isMobilePhone`

* **BrowserType がiPhoneではありません**:

  置換：

  `user.browserType!="iphone"`

  次を使用：

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isMobilePhone`

* **BrowserType はiPad**:

  置換：

  `user.browserType=="ipad"`

  次を使用：

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isTablet`

* **BrowserType がiPadではありません**:

  置換：

  `user.browserType!="ipad"`

  次を使用：

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isTablet`