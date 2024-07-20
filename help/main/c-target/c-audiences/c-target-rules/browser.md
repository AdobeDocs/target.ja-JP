---
keywords: ブラウザーオプション;タイプ;ブラウザータイプ;ブラウザー言語;言語;バージョン;ブラウザーバージョン
description: でオーディエンスを作成して、ページ  [!DNL Adobe Target]  訪問時に特定のブラウザーまたは特定のブラウザーオプションを使用するユーザーをターゲットにする方法を説明します。
title: ブラウザータイプに基づいて訪問者をターゲットに設定することはできますか？
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: 784f41a73941877135a5902f2331972ba9d0e880
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 34%

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
>[!DNL Target] Standard/Premium 24.3.1 （2024 年 3 月 4～6 日（PT））以降、`Browser:iPad` や `Browser:iPhone` など、Target UI を使用して作成された組み込みオーディエンスが更新され、`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone` および `profile.mobile.isTablet` を使用して [!DNL iPad] および [!DNL iPhone] の適切なターゲティングが実行されるようになりました。
>
>この更新は、顧客側でのアクションは必要ありません。 [!DNL Target] UI のラベルは今後変更される予定で、これらの変更が行われた [[!DNL Target]  リリースノート（最新） ](/help/main/r-release-notes/release-notes.md) でお知らせします。
>
>回避策の設定については、以下の [ オーディエンス属性の  [!DNL iPad]  および  [!DNL iPhone]  の更新（2024 年 4 月 30 日（PT）） ](#updates)[!UICONTROL Browser] 参照してください。

ブラウザーをターゲットにするには、2 つの方法があります。

* **事前設計されたオーディエンス：**&#x200B;特定のブラウザーを使用してサイトに訪問している訪問者のみをターゲットにしたい場合、事前設計されたオーディエンスを使用します。例えば、[!DNL Chrome] 拡張機能を提供している場合、ターゲットにするユーザーは [!DNL Chrome] 人のみです。

   1. アクティビティを設定する場合、ドロップダウンリストからブラウザーを選択します。

      このオプションは、特定のブラウザーを使用する訪問者のみをアクティビティのターゲットにします。

      ![Target Chrome ユーザー ](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **カスタマイズされたブラウザーオーディエンスルール：** カスタマイズされたオーディエンスを使用すると、複数のブラウザーをターゲットにしたり、特定のブラウザー、ブラウザーバージョンまたはブラウザー言語のルールや除外を設定したりできます。 この機能により、ブラウザー属性に基づいてアクティビティをターゲティングする際に、大きな柔軟性が得られます。

   1. [!DNL Target] インターフェイスで、**[!UICONTROL Audiences]**/**[!UICONTROL Create Audience]** をクリックします。
   1. オーディエンスに名前を付け、オプションで説明を追加します。
   1. オーディエンスビルダーにドラッグ&amp;ドロップ **[!UICONTROL Browser]** ます。

      ![ ルール/ブラウザー ](assets/target_browser.png)

   1. 「**[!UICONTROL Select]**」をクリックして、次のいずれかのオプションを選択します。

      * **タイプ：**&#x200B;特定のブラウザーをターゲットにするか除外します。[タイプ](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56)を参照してください。
      * **言語：** 特定の言語を使用するように設定されている特定のブラウザーをターゲットにするか除外します。 [言語](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1)を参照してください。
      * **バージョン：**&#x200B;特定のブラウザーのバージョンをターゲットにするか除外します。[バージョン](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF)を参照してください。

   1. （任意）オーディエンスの追加ルールを設定します。
   1. **[!UICONTROL Done]** をクリックします。

  次の例では、バージョン 91 または 92 の [!DNL Microsoft Edge] ユーザーを含むオーディエンスを示しています。

  ![Target Edge 91 または 92](assets/target_edge.png)

## ブラウザーオプション {#concept_221D8EEF53CC45AEACEB17CF336A3658}

ブラウザーのタイプ、言語またはバージョンに基づいてアクティビティ参加者をターゲット化または除外します。

### タイプ {#section_6ADC758F23F145B3A310151546D83D56}

特定のブラウザーをターゲットにするか除外します。

「**[!UICONTROL Type]**」を選択し、「次と等しい」または「次と等しくない」を選択します。

* [!UICONTROL Equals]：選択したブラウザーをターゲットにします。
* [!UICONTROL Does not equal]：選択したブラウザーを除外します。

1 つ以上のブラウザーを選択します。複数のオプションは、OR を使用して接続できます。

### 言語 {#section_7520D1AA464A45A6843EABE2D2B431A1}

特定の言語を使用するように設定されているブラウザーをターゲットにするか除外します。

例えば、オファーが英語でのみ利用できる場合、英語に設定されたブラウザーをターゲットにすることがあります。または、ページで全角文字が無効な場合、東アジア言語に設定されたブラウザーを除外することがあります。

言語が場所よりも重要な場合、ブラウザーの言語を含めるまたは除外することで、地域に基づくターゲティングよりも正確に訪問者をターゲティングできます。例えば、英語で記載された記事を提供している場合、英語を話す国をターゲットにするか、英語に設定されたブラウザーをターゲットにすることができます。ブラウザーをターゲットにすることで、英語が第一言語でない国にいる英語話者に対して記事を提供できます。

「**[!UICONTROL Language]**」を選択し、「次と等しい」または「次と等しくない」を選択します。

* [!UICONTROL Equals]：選択したブラウザーの言語をターゲットにします。
* [!UICONTROL Does not equal]：選択したブラウザー言語を除外します。

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

例えば、[!DNL Internet Explorer] バージョン 11 以前でページが正しく表示されない場合は、それらのバージョンを除外するオーディエンスを作成できます。 その場合、ブラウザーのタイプが [!DNL Internet Explorer] に等しいルールを設定し、バージョンが 11 以下の 2 つ目のルールを追加します。

「**[!UICONTROL Version]**」を選択してから、演算子を選択します。

* [!UICONTROL Equals]
* [!UICONTROL Does not equal]
* [!UICONTROL Is greater than]
* 次よりも大きいか等しい
* [!UICONTROL Is less than]
* [!UICONTROL Is less than or equal to]

バージョン番号を入力します。 テキストフィールドにはメジャーバージョンのみ入力できます。指定したバージョンには、そのリリースの任意のマイナーバージョンが含まれます。例えば、バージョン 10 を指定した場合、バージョン 10.1 の訪問者も含まれます。

複数のオプションは、OR を使用して接続できます。

## トレーニングビデオ：オーディエンスの作成 ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## [!UICONTROL Browser] オーディエンス属性の [!DNL iPad] と [!DNL iPhone] の更新（2024年4月30日（PT）） {#updates}

[!DNL Adobe Target] を使用すると、ページの訪問時に特定のブラウザーまたはブラウザーオプションを使用するユーザーなど ](/help/main/c-target/c-audiences/c-target-rules/target-rules.md) 複数のカテゴリ属性のいずれかをターゲットに [ することができます。

[!DNL Target] Standard/Premium 24.3.1 （2024 年 3 月 4～6 日（PT））以降、`Browser:iPad` や `Browser:iPhone` など、Target UI を使用して作成された組み込みオーディエンスが更新され、`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone` および `profile.mobile.isTablet` を使用して [!DNL iPad] および [!DNL iPhone] の適切なターゲティングが実行されるようになりました。

`Browser:iPad` や `Browser:iPhone` など、[!DNL Target] UI を使用して作成された組み込みオーディエンスは、新しいオーディエンス定義に自動的に移動されるので、顧客側でのアクションは必要ありません。 ただし、今後は [ 以下に説明する ](#ui) 設定を使用する必要があります。

プロファイルスクリプトで `user.browserType` を使用して、[!DNL iPhone] または [!DNL iPad] （例：`user.browserType == 'iphone'` または `user.browserType != 'ipad'`）かどうかを確認する場合は、これらのオーディエンスが引き続き期待どおりに機能するように、2024 年 4 月 30 日（PT）より前に、これらのプロファイルスクリプトを [ 以下の手順 ](#profile-scripts) で変更する必要があります。

JavaScript オーディエンスは、[!DNL Target Classic] UI で非推奨となった [!DNL Target] 式を使用した従来のオーディエンスです。 これらのオーディエンスは、API 経由でのみ変更できます。 これらのオーディエンスを更新する必要があるのは、アクティビティで従来のオーディエンスを引き続き使用する場合のみです。

### [!DNL Target] UI を使用して作成されたオーディエンス {#ui}

今後、次の設定を使用できます。

* **ブラウザー一致[!DNL Apple]** の場合：[!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL matches] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **ブラウザーがタブレットと一致する場合**:[!UICONTROL Mobile]/[!UICONTROL is Tablet]/[!UICONTROL true]

  ![モバイルはタブレットです](/help/main/r-release-notes/assets/is-tablet.png)

* **ブラウザーがiPadと一致する場合**:[!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPad] と And コンテナが [!UICONTROL Mobile] > [!UICONTROL Is Tablet] と一致する場合 [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **ブラウザーがiPhoneと一致する場合**:[!UICONTROL Mobile] > [!UICONTROL Device Marketing Name] [!UICONTROL matches] [!DNL iPhone] と And コンテナが [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] と一致する場合 [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

条件を否定する場合など、使用できる設定は他にも多数あります。 条件の否定の例を次に示します。

* **ブラウザーがiPhoneと一致しない場合**:[!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] が Or コンテナで [!UICONTROL Mobile] > [!UICONTROL Is Mobile Phone] が [!UICONTROL false] である場合

  ![ 携帯電話なし ](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **ブラウザーがiPadと一致しない場合**:[!UICONTROL Mobile] > [!UICONTROL Device Vendor] [!UICONTROL does not match] [!UICONTROL Apple] と Or コンテナが [!UICONTROL Mobile] > [!UICONTROL Is Tablet] で [!UICONTROL false]。

  ![ タブレットではない ](/help/main/r-release-notes/assets/tablet-false.png)

### プロファイルスクリプトを使用して作成されたオーディエンス {#profile-scripts}

従来の [!DNL Target Classic] オーディエンスまたはプロファイルスクリプトで `user.browserType` を使用する場合は、変更に次を含める必要があります。

* **BrowserType はiPhoneです**。

  置き換え：

  `user.browserType=="iphone"`

  を使用：

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isMobilePhone`

* **BrowserType はiPhoneではありません**:

  置き換え：

  `user.browserType!="iphone"`

  を使用：

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isMobilePhone`

* **BrowserType はiPadです**。

  置き換え：

  `user.browserType=="ipad"`

  を使用：

  `profile.mobile.deviceVendor == "Apple" && profile.mobile.isTablet`

* **BrowserType はiPadではありません**:

  置き換え：

  `user.browserType!="ipad"`

  を使用：

  `profile.mobile.deviceVendor != "Apple" || !profile.mobile.isTablet`