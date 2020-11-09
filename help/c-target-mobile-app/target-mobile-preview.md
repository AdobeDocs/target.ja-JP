---
keywords: qa;preview;preview link;mobile;mobile preview
description: モバイルのプレビューリンクを使用して、モバイルアプリケーションアクティビティの簡易的なエンドツーエンドの QA を実行できます。特別なテスト用のデバイスがなくても、ご利用のデバイス上で様々なエクスペリエンスを確認できます。
title: Adobe Target モバイルでのモバイルプレビューリンクの使用
feature: mobile implementation
topic: Advanced,Standard,Classic
uuid: 313150fa-a7ec-46fe-9166-742a5c246a72
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 94%

---


# Target モバイルのプレビュー{#target-mobile-preview}

モバイルのプレビューリンクを使用して、モバイルアプリケーションアクティビティの簡易的なエンドツーエンドの QA を実行できます。特別なテスト用のデバイスがなくても、ご利用のデバイス上で様々なエクスペリエンスを確認できます。

>[!NOTE]
>
>モバイルプレビュー機能を使用するには、4.14 以降の適切なバージョンの Adobe Mobile SDK をダウンロードしてインストールする必要があります。

## 概要 {#section_981D6FA4AEE64098809EA606E89E4A5E}

モバイルプレビュー機能を使用して、モバイルアプリアクティビティを実稼動環境に投入する前に完全にテストすることができます。

## 前提条件 {#section_A763C564C9E84B0EB448237B5B1E4068}

1. **サポートされているバージョンの SDK を使用する：**&#x200B;モバイルプレビュー機能を使用するには、4.14 以降の適切なバージョンの Adobe Mobile SDK をダウンロードして対応するアプリにインストールする必要があります。

   適切な SDK をダウンロードする手順については、以下を参照してください。

   * **iOS:**[事前開始](https://experienceleague.adobe.com/docs/mobile-services/ios/getting-started-ios/requirements.html) ( *Mobile Services iOSヘルプ*)
   * **Android:**[開始の準備](https://experienceleague.adobe.com/docs/mobile-services/android/getting-started-android/requirements.html) ( *Mobile Services Androidヘルプ*)

1. **URL スキームを設定する：**&#x200B;プレビューリンクでは、URL スキームを使用してアプリを開きます。プレビュー用に一意の URL スキームを指定する必要があります。

   iOS の例を次の図に示します。

   ![](assets/mobile-preview-url-scheme-ios.png)

   Android の例を次の図に示します。

   ![](assets/Android_Deeplink.png)

1. **アドビの DeepLink を追跡する**

   **iOS：**&#x200B;アプリケーションデリゲートで、 デリゲートが前の手順で指定した URL スキームでリソースを開くように要求されたときに `[ADBMobile trackAdobeDeepLink:url` を呼び出します。

   コードスニペットの例を次に示します。

   ```
   - (BOOL) application:(UIApplication *)app openURL:(NSURL *)url 
                options:(NSDictionary<NSString *,id> *)options { 
   
       if ([[url scheme] isEqualToString:@"com.adobe.targetmobile"]) { 
           [ADBMobile trackAdobeDeepLink:url]; 
           return YES; 
       } 
       return NO; 
   } 
   ```

   **Android：**&#x200B;アプリケーションで、 呼び出し元が前の手順で指定した URL スキームでリソースを開くように要求されたときに `Config.trackAdobeDeepLink(URL);` を呼び出します。

   ```
    private Boolean shouldOpenDeeplinkUrl() { 
        Intent appLinkIntent = getIntent(); 
        String appLinkAction = appLinkIntent.getAction(); 
        Uri appLinkData = appLinkIntent.getData; 
        if (appLinkData.toString().startsWith("com.adobe.targetmobile")) { 
            Config.trackAdobeDeepLink(appLinkData); 
            return true; 
        } 
        return false; 
     }
   ```

   Android でモバイルプレビューが動作するように設定するには、さらに次のコードスニペットを [!DNL AndroidManifest.xml] に追加する必要があります。

   ```
   <activity android:name="com.adobe.marketing.mobile.FullscreenMessageActivity" />
   ```

## プレビューリンクの生成 {#section_D9D58173FFF34E9BB75EBF357273F128}

1. Target UI で、「**[!UICONTROL その他のオプション]**」アイコン（縦並びの省略記号）をクリックし、「**[!UICONTROL モバイルプレビューを作成]**」を選択します。

   ![](assets/mobile-preview-create.png)

1. プレビューするアクティビティを選択し、「**[!UICONTROL モバイルプレビューの作成リンク]**」をクリックします。

   >[!NOTE]
   >
   >フォームベースの AB および XT アクティビティのみを選択できます。

   ![](assets/mobile-preview-select-activities.png)

1. アプリの URL スキームを指定します。

   これは、iOS または Android アプリに存在する URL スキームと同じである必要があります。必要に応じて、iOS と Android でこのプロセスを別々に繰り返します。

   ![](assets/mobile-preview-enter-url-scheme.png)

1. 「**[!UICONTROL モバイルプレビューリンクを生成」をクリック]** して、リンクをコピーします。

   ![](assets/mobile-preview-generate-and-copy.png)

## デバイスでのプレビュー {#section_521F0D46F3DE4A2A98283A1B73FF69F6}

アプリをインストールしたデバイス上のモバイルブラウザーでリンクを開きます。Apple App Store または Google Play ストアからダウンロードした製品アプリを使用できます。特殊なビルドである必要はありません。アクティブなプレビューリンクがある場合は、デバイス上でエクスペリエンスを表示できます。

1. モバイルブラウザーでリンクを開きます。

   前の手順で Target UI からモバイルデバイスにコピーしたリンクを、任意の方法（テキスト、電子メール、Slack など）で共有します。

   |![ディープリンクのプレビュー1](/help/c-target-mobile-app/assets/mobile-preview-open-deeplink.png)|![ディープリンクのプレビュー2](/help/c-target-mobile-app/assets/mobile-preview-open-app.png)|

   アプリが開き、Target のモバイルプレビューモードが開始されます。

1. 表示するエクスペリエンスの組み合わせを選択し、「エクスペリエンス **[!UICONTROL を開始」をクリック]** します。

   |![mobile preview1](/help/c-target-mobile-app/assets/mobile-preview-experience-selection-1.png)|![モバイルプレビュー2](/help/c-target-mobile-app/assets/mobile-preview-experience-result-1-france.png)|![モバイルプレビュー3](/help/c-target-mobile-app/assets/mobile-preview-experience-result-1-shipfree.png)|
|![モバイルプレビュー4](/help/c-target-mobile-app/assets/mobile-preview-experience-selection-2.png)|![モバイルプレビュー5](/help/c-target-mobile-app/assets/mobile-preview-experience-result-2-aus.png)|![モバイルプレビュー6](/help/c-target-mobile-app/assets/mobile-preview-experience-result-2-10off.png)|

## 制限事項 {#section_4E9BDED0F718485292527EFB508305BD}

* 「[!UICONTROL エクスペリエンスを開始]」ボタンをクリックした後で新しいコンテンツを表示するには、ビューをもう一度読み込む必要があります。最も簡単な方法は、一旦別の画面に切り替えた後、変更を適用する画面に戻ることです。
* モバイルプレビューは、API-19（KitKat）より前の Android バージョンではサポートされません。