---
keywords: ブラウザーオプション;タイプ;ブラウザータイプ;ブラウザー言語;言語;バージョン;ブラウザーバージョン
description: でオーディエンスを作成する方法を説明します。 [!DNL Adobe Target] を使用して、ページの訪問時に特定のブラウザーまたは特定のブラウザーオプションを使用しているユーザーをターゲットに設定することができます。
title: ブラウザータイプに基づいて訪問者をターゲットに設定することはできますか？
feature: Audiences
exl-id: 8420bbe3-b58a-4ddb-89bb-0265dab6b5fc
source-git-commit: c79b1d40e0bf0495dc3f3d5accd196f14d18b934
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 53%

---

# ブラウザー

ページの訪問時に特定のブラウザーまたは特定のブラウザーオプションを使用しているユーザーをターゲットに設定することができます。

次のブラウザーをターゲットに設定できます。

* Chrome
* Firefox
* Safari
* Internet Explorer
* Microsoft Edge
* Opera
* iPad
* iPhone

>[!IMPORTANT]
>
>2024 年 4 月 30 日以降、iPadとiPhoneは、使用可能な [!UICONTROL ブラウザー] タイプのドロップダウンリスト（オーディエンスのカテゴリを作成する場合） 回避策の設定については、 [ブラウザーオーディエンス属性からのiPadおよびiPhoneの廃止（2024 年 4 月 31 日）](#deprecation) 下

ブラウザーをターゲットにするには、2 つの方法があります。

* **事前設計されたオーディエンス：**&#x200B;特定のブラウザーを使用してサイトに訪問している訪問者のみをターゲットにしたい場合、事前設計されたオーディエンスを使用します。例えば、Chrome の拡張機能を提供している場合、Chrome ユーザーのみをターゲットにします。

   1. アクティビティを設定する際に、ドロップダウンリストからブラウザーを選択します。

      このオプションは、特定のブラウザーを使用する訪問者のみをアクティビティのターゲットにします。

      ![Chrome ユーザーのターゲット設定](/help/main/c-target/c-audiences/c-target-rules/assets/target-chrome.png)

* **カスタマイズされたブラウザーオーディエンスルール：** カスタマイズされたオーディエンスを使用すると、複数のブラウザーをターゲットにしたり、特定のブラウザー、ブラウザーのバージョンまたはブラウザーの言語に対するルールや除外を設定したりできます。 この機能は、ブラウザー属性に基づいてアクティビティをターゲット設定する際に、大幅な柔軟性を提供します。

   1. Adobe Analytics の [!DNL Target] インタフェース、クリック **[!UICONTROL オーディエンス]** > **[!UICONTROL オーディエンスを作成]**.
   1. オーディエンスに名前を付け、オプションで説明を追加します。
   1. ドラッグ&amp;ドロップ **[!UICONTROL ブラウザー]** を Audience Builder に貼り付けます。

      ![ルール/ブラウザー](assets/target_browser.png)

   1. 「**[!UICONTROL 選択]**」をクリックして、次のいずれかのオプションを選択します。

      * **タイプ：**&#x200B;特定のブラウザーをターゲットにするか除外します。[タイプ](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_6ADC758F23F145B3A310151546D83D56)を参照してください。
      * **言語：** 特定の言語を使用するように設定されているブラウザーをターゲットにするか除外します。 [言語](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_7520D1AA464A45A6843EABE2D2B431A1)を参照してください。
      * **バージョン：**&#x200B;特定のブラウザーのバージョンをターゲットにするか除外します。[バージョン](/help/main/c-target/c-audiences/c-target-rules/browser.md#section_37CC8CE45DA04E8682AE6388321BA6EF)を参照してください。

   1. （オプション）オーディエンス用の追加のルールを設定します。
   1. 「**[!UICONTROL Done]**」をクリックします。

  次の例は、バージョン 91 または 92 のMicrosoft Edge ユーザーを含むオーディエンスを示しています。

  ![Target Edge 91 または 92](assets/target_edge.png)

## ブラウザーオプション {#concept_221D8EEF53CC45AEACEB17CF336A3658}

ブラウザーのタイプ、言語またはバージョンに基づいてアクティビティ参加者をターゲット化または除外します。

### タイプ {#section_6ADC758F23F145B3A310151546D83D56}

特定のブラウザーをターゲットにするか除外します。

「**[!UICONTROL タイプ]**」を選択して、「次の値と等しい」または「次の値と等しくない」を選択します。

* 次の値と等しい：選択したブラウザーをターゲットにします。
* 次の値と等しくない：選択したブラウザーを除外します。

1 つ以上のブラウザーを選択します。複数のオプションは、OR を使用して接続できます。

### 言語 {#section_7520D1AA464A45A6843EABE2D2B431A1}

特定の言語を使用するように設定されているブラウザーをターゲットにするか除外します。

例えば、オファーが英語でのみ利用できる場合、英語に設定されたブラウザーをターゲットにすることがあります。または、ページで全角文字が無効な場合、東アジア言語に設定されたブラウザーを除外することがあります。

言語が場所よりも重要な場合、ブラウザーの言語を含めるまたは除外することで、地域に基づくターゲティングよりも正確に訪問者をターゲティングできます。例えば、英語で記載された記事を提供している場合、英語を話す国をターゲットにするか、英語に設定されたブラウザーをターゲットにすることができます。ブラウザーをターゲットにすることで、英語が第一言語でない国にいる英語話者に対して記事を提供できます。

「**[!UICONTROL 言語]**」を選択して、「次の値と等しい」または「次の値と等しくない」を選択します。

* 次の値と等しい：選択したブラウザーの言語をターゲットにします。
* 次の値と等しくない：選択したブラウザーの言語を除外します。

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

例えば、ページが Internet Explorer バージョン 11 以前で適切に表示されない場合、これらのバージョンを除外するオーディエンスを作成できます。この場合、ブラウザータイプが Internet Explorer に等しいというルールを設定し、バージョンが 11 以下であるという 2 番目のルールを追加します。

「**[!UICONTROL バージョン]**」を選択して、演算子を選択します。

* 次と等しい
* 次と等しくない
* 次より大きい
* 次よりも大きいか等しい
* 次より小さい
* 次よりも小さいか等しい

バージョン番号を入力します。 テキストフィールドにはメジャーバージョンのみ入力できます。指定したバージョンには、そのリリースの任意のマイナーバージョンが含まれます。例えば、バージョン 10 を指定した場合、バージョン 10.1 の訪問者も含まれます。

複数のオプションは、OR を使用して接続できます。

## トレーニングビデオ：オーディエンスの作成 ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)

## ブラウザーオーディエンス属性からの iPad と iPhone の非推奨（廃止予定）（2024年4月30日（PT）） {#deprecation}

[!DNL Adobe Target] 以下が可能です。 [複数のカテゴリ属性のいずれかに対するターゲット](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)（ページの訪問時に特定のブラウザーまたはブラウザーオプションを使用しているユーザーを含む）

2024 年 4 月 30 日以降、iPadとiPhoneは、使用可能な [!UICONTROL ブラウザー] タイプのドロップダウンリスト（オーディエンスのカテゴリを作成する場合）

[!UICONTROL ブラウザー]属性を使用して iPad または iPhone をターゲットに設定するオーディエンスがある場合、これらのオーディエンスが引き続き期待どおりに機能するように、2024年4月30日（PT）までにこれらの設定を変更する必要があります。

### を使用して作成されたオーディエンス [!DNL Target] UI

今後は、次の設定を使用できます。

* **ブラウザーの一致の場合[!DNL Apple]**: [!UICONTROL モバイル] > [!UICONTROL デバイスのベンダー] [!UICONTROL 一致する] [!DNL Apple]

  ![Apple](/help/main/r-release-notes/assets/apple.png)

* **ブラウザー一致タブレットの場合**: [!UICONTROL モバイル] > [!UICONTROL タブレット] > [!UICONTROL true]

  ![モバイルはタブレットです](/help/main/r-release-notes/assets/is-tablet.png)

* **ブラウザがiPadに一致する場合**: [!UICONTROL モバイル] > [!UICONTROL デバイスのマーケティング名] [!UICONTROL 一致する] [!DNL iPad] を含む And コンテナ [!UICONTROL モバイル] > [!UICONTROL タブレット] 次に該当 [!DNL true]

  ![iPad](/help/main/r-release-notes/assets/ipad.png)

* **ブラウザがiPhoneに一致する場合**: [!UICONTROL モバイル] > [!UICONTROL デバイスのマーケティング名] [!UICONTROL 一致する] [!DNL iPhone] を含む And コンテナ [!UICONTROL モバイル] > [!UICONTROL 携帯電話] 次に該当 [!DNL true]

  ![iPhone](/help/main/r-release-notes/assets/iphone.png)

条件が無効な場合など、他にも多くの設定が使用可能です。 否定条件の例を次に示します。

* **ブラウザーがiPhoneと一致しません**: [!UICONTROL モバイル] > [!UICONTROL デバイスのベンダー] [!UICONTROL 一致しない] [!UICONTROL Apple] OR コンテナが [!UICONTROL モバイル] > [!UICONTROL 携帯電話] 次に該当 [!UICONTROL false]

  ![携帯電話ではありません](/help/main/r-release-notes/assets/mobile-phone-false.png)

* **ブラウザーがiPadと一致しません**: [!UICONTROL モバイル] > [!UICONTROL デバイスのベンダー] [!UICONTROL 一致しない] [!UICONTROL Apple] OR コンテナが [!UICONTROL モバイル] > [!UICONTROL タブレット] 次に該当 [!UICONTROL false].

  ![タブレットではありません](/help/main/r-release-notes/assets/tablet-false.png)

### プロファイルスクリプトを使用して作成されたオーディエンス

次を使用する場合、 `user.browserType` JavaScript セグメントでの使用については、 [プロファイルと変数の用語集](/help/main/c-target/c-visitor-profile/variables-profiles-parameters-methods.md)に変更を加える場合は、次の変更を行う必要があります。

>[!NOTE]
>
>次のプロファイルは、2024 年 1 月 24 日現在、今後数日以内にリリースされる予定です。 The [最新のリリースノート](/help/main/r-release-notes/release-notes.md) これらのプロファイルが使用可能になると、が更新されます。

これらのプロファイルでは、次の変更が可能です。
>>
* `profile.mobile.isTablet`
>>
* `profile.mobile.isMobilePhone`

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