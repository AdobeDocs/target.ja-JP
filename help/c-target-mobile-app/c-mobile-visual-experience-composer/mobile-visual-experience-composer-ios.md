---
description: Adobe Target のモバイル Visual Experience Composer（VEC）を利用すると、開発者が iOS モバイルアプリへのセットアップを一度おこなえば、マーケティング担当者がモバイルアプリ VEC の機能を使用できるようになります。
keywords: モバイルアプリ vec;モバイル visual experience composer;モバイル experience composer オプション;設定;ios;apple
seo-description: Adobe Target のモバイル Visual Experience Composer（VEC）を利用すると、開発者が iOS モバイルアプリへのセットアップを一度おこなえば、マーケティング担当者がモバイルアプリ VEC の機能を使用できるようになります。
seo-title: iOS - モバイルアプリケーションのセットアップ
solution: 'Target '
title: iOS - モバイルアプリケーションのセットアップ
topic: Standard
uuid: 6db4f06a-d8f4-4192-af6f-917594e721e6
translation-type: tm+mt
source-git-commit: 0447ec6a589534ec9ad2da8d809b66900e9b4617

---


# iOS - モバイルアプリケーションのセットアップ{#ios-set-up-the-mobile-app}

Adobe Target のモバイルアプリ Visual Experience Composer（VEC）を利用すると、開発者が iOS モバイルアプリへのセットアップを一度おこなえば、マーケティング担当者がモバイルアプリ VEC の機能を使用できるようになります。

Adobe Target VEC 拡張機能の有効化について詳しくは、[Adobe Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) の *Adobe Target - Visual Experience Composer* を参照してください。

## Mobile SDK と Target のライブラリを追加する {#sdk-library}

1. ポッド「`ACPTargetVEC`」を追加して、CocoaPods [!DNL Podfile] 経由でプロジェクトにライブラリを追加します。

1. XCode で Objective-C アプリケーションプロジェクトを開きます。

1. プロジェクトのビルド設定に移動し、「Swift 標準ライブラリを常に埋め込む」がまだ設定されていない場合は「はい」に設定します。

1. プロジェクトのビルド設定で「その他のリンカーフラグ」を検索し、まだ存在しない場合は `$(inherited)` を追加します。

1. Objective-C 専用プロジェクトの場合は、swift ファイルを作成してブリッジヘッダーを作成します。これにより、Swift 用のアプリケーション環境を設定します。

1. ディープリンクハンドラーを追加します。

   1. アプリケーションのプロジェクト設定で、「**[!UICONTROL 情報]**」をクリックします。
   1. 「**[!UICONTROL URL タイプ]**」の下の三角形をクリックして開き、プラス記号をクリックして新しいフィールドを追加します。
   1. 次の情報を追加します。

      * 識別子：`com.adobe.sdktest`
      * URL スキーム：`vectester`
      * 役割：Editor
   1. アプリケーションプロジェクト設定／**[!UICONTROL 一般]** をクリックします。
   1. Objective-C アプリケーションプロジェクト設定／**[!UICONTROL Info]** を再度クリックして、設定が保存されたことを確認します。

      URL のタイプの例では、アプリケーションの URL スキームは次のようになります。

      ```
      vectester://com.adobe.sdktest
      ```


1. XCode で、[!DNL AppDelegate] ファイルを開きます。

1. ファイルの最上部に、インポートの最後に次の行を追加します。

   `#import "ACPTargetVEC.h"`

   Swiftを使用している場合は、次の行を追加します。

   `import ACPTargetVEC`

1. [!DNL AppDelegate] ファイルの `AppDelegate::application:didFinishLaunchingWithOptions:` に次の行を追加します。デリゲート関数が定義されていない場合は、デリゲート関数を作成し、次の行を Objective-C または Swift アプリケーションに追加します。

   ```
   // CONFIGURATION LINE FOR OBJECTIVE C ONLY
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
     //Other Extensions that you need
     [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"];
     [ACPCore setLogLevel:ACPMobileLogLevelDebug];
     [ACPTarget registerExtension];
     [ACPTargetVEC registerExtension];
     [ACPCore start:^{
       [ACPCore lifecycleStart:nil];
     }];
     // Override point for customization after application launch.
     return YES;
   }
   
   // CONFIGURATION LINE FOR SWIFT ONLY: 
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
     //Other Extensions that you need
     ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID")
     ACPCore.setLogLevel(ACPMobileLogLevel.debug)
     ACPTarget.registerExtension()
     ACPTargetVEC.registerExtension()
     [ACPCore start:^{
       [ACPCore lifecycleStart:nil];
     }];
     return true
   }
   ```

1. `AppDelegate:application:openURL` の先頭に次の行を追加します。デリゲート関数が定義されていない場合は、デリゲート関数を作成し、次の行を追加します。

   ```
   // URL HANDLER LINE FOR OBJECTIVE C ONLY: 
   - (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary<NSString *, id> *)options {
     [ACPCore collectLaunchInfo:@ {@"adb_deeplink": url.absoluteString}];
     return YES;
   }
   
   // URL HANDLER LINE FOR SWIFT ONLY: 
   func application(_ app: UIApplication, open url: URL, options: [UIApplicationOpenURLOptionsKey : Any] = [:]) -> Bool {
     ACPCore.collectLaunchInfo(["adb_deeplink": url.absoluteString])
     return true
   }
   ```

   アプリケーションをビルドして実行し、それを使用してモバイルアプリ VEC の機能をテストします。


## モバイルアプリケーションで Target ビューをセットアップ {#views}

Adobe Mobile SDK は、新しいビューが表示された際にトリガーする新しいメソッドを開発者に公開します。iOS アプリに Target ビュー API 呼び出しを適切に挿入する方法については、全般的ガイドラインを参照してください。iOS では、すべての Target ビューが、それらが表示される `UIViewController` に対して定義されます。したがって、Android とは異なり、`TargetViews` の挿入は次の呼び出しに制限されます。

Adobe Mobile アプリ VEC 拡張機能は、`UIViewControllers` がモバイルアプリ VEC フレームワーク内でやり取りするための名前を、サブクラス化した `UIViewController` のクラス名に基づいて自動生成します。これらの名前を上書きする場合は、`ViewController` の `viewWillAppear` で次のメソッドを呼び出すことができます。

```
// TARGET VIEW LINE FOR OBJECTIVE C ONLY 
[ACPTargetVEC setTargetView:@"exampleViewController"]; 
   
// TARGET VIEW LINE FOR SWIFT ONLY 
ACPTargetVEC.setTargetView("exampleViewController")
```

Adobe Mobile SDK は、実行時にカスタムビューをターゲットにする代替メソッドをデベロッパーに公開します。デベロッパーは、ビューの名前が一意であることを確認する必要があります。`superview` にビューを追加する前に、次のメソッドを呼び出します。

```
// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN OBJECTIVE C 
CustomPopupView *popupView = [[CustomPopupView alloc] initWithFrame:CGRectMake(0, 0, 300, 200)]; 
[ACPTargetVEC setTargetView:@"myCustomPopupView" forView:popupView];

// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN SWIFT 
let popupView = CustomPopupView.init(frame: CGRect(x: 0, y: 0, width: 300, height: 200)) 
ACPTargetVEC.setTargetView("myCustomPopupView", for: popupView)
```

## プロファイルパラメーターとその他のグローバルパラメーターの設定 {#parameters}

各 API 呼び出しで渡すグローバルパラメーターを設定できるようになったほか、対応するビューに mbox／ビューパラメーターを渡すことができるようになりました。

パラメーターには次のものがあります。

* mbox／ビューパラメーター
* プロファイルパラメーター
* 製品パラメーター
* 注文パラメーター

**グローバルパラメーターのサポート：**

```
//For Objective-c 
NSDictionary *mboxParams = @{@"mboxparam1":@"mboxvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekey1":@"profilevalue1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters: mboxParams
                      profileParameters: profileParams
                      product: product
                      order: order];
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product = ACPTargetProduct(id: "1234", categoryId: "furniture")
var order = ACPTargetOrder(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"])
var targetParams = ACPTargetParameters(parameters: mboxParams, profileParameters: profileParams, product: product, order: order)
ACPTargetVEC.setGlobalRequest(targetParams)
```

**次のビュートリガーのパラメーターを渡す場合：**

アプリ内に存在するビューコントローラごとに、「`AUTO_<viewControllerName>`」など、デフォルトで作成される自動ビューをいくつか用意しました。これらのパラメーターを渡すには、次の API を呼び出します。

```
//For Objective-c 
NSDictionary *mboxParams = @{@"viewparam1":@"viewvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekeyforview1":@"profilevalueforview1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product = ACPTargetProduct(id: "1234", categoryId: "furniture")
var order = ACPTargetOrder(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"])
var targetParams = ACPTargetParameters(parameters: mboxParams, profileParameters: profileParams, product: product, order: order)
ACPTargetVEC.setRequest(targetParams)
```

**特定のビューにパラメーターを渡す場合：**

`TargetVEC.targetView("view_name")` 経由でビューをトリガーする API については既に紹介しました。次のように、特定のビューに固有のパラメーターを渡すこともできます。

```
//For Objective-c 
[ACPTargetVEC setTargetView:@"VIEW_NAME" withParameters:TARGET_PARAMS];

//FOR SWIFT 
ACPTargetVEC.setTargetView("VIEW_NAME", with: TARGET_PARAMS)
```

## プリフェッチ API の明示的な呼び出し {#section_373DB4527FC649C58FBA3DF0C18C9836}

ときには、プリフェッチ API を再度呼び出してキャッシュに保存されているオファーを更新しなければならないことがあります。公開されている API とその説明を以下に示します。

**オファーのプリフェッチ：**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the main thread blocking the UI. 
 */ 
+ (void) prefetchOffers;
```

**バックグラウンドでオファーをプリフェッチ：**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the background thread so doesn't block UI. 
 */ 
+ (void) prefetchOffersBackground;
```

## チュートリアル:Mobile iOS Objective- CおよびSwiftアプリケーションにExperience Cloudを実装する {#tutorial}

* [Mobile iOS Objective- CアプリケーションにExperience Cloudを実装する](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-ios-objective-c-apps-with-launch/index.html)
* [Mobile iOS SwiftアプリケーションへのExperience Cloudの実装](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-ios-swift-apps-with-launch/index.html)

これらのチュートリアルを完了すると、次のことが可能になります。

* モバイル開始プロパティの作成
* Objective- CまたはSwiftアプリケーションに起動プロパティをインストールする
* 以下のAdobe Experience Cloudソリューションを実装します。
   * Experience Cloud ID サービス
   * Adobe Target
   * Adobe Analytics
   * Adobe Audience Manager

* 開発環境、ステージング環境および実稼動環境での変更の発行