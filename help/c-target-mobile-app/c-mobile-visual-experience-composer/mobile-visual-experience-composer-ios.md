---
description: Adobe Target Mobile Visual Experience Composer（VEC）を使用すると、開発者はiOSモバイルアプリで1回限りのセットアップを行い、マーケティング担当者がモバイルアプリVECの機能を使用できるようになります。
keywords: Mobile App VEC;mobile visual experience composer;mobile experience composerオプション;設定、ios;Apple
seo-description: Adobe Target Mobile Visual Experience Composer（VEC）を使用すると、開発者はiOSモバイルアプリで1回限りのセットアップを行い、マーケティング担当者がモバイルアプリVECの機能を使用できるようになります。
seo-title: iOS - モバイルアプリケーションのセットアップ
solution: 'Target '
title: iOS - モバイルアプリケーションのセットアップ
topic: Standard
uuid: 6db4f06a-d8f4-4192-af6f-917594e721e6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# iOS - モバイルアプリケーションのセットアップ{#ios-set-up-the-mobile-app}

Adobe Target Mobile App Visual Experience Composer（VEC）を使用すると、開発者はiOSモバイルアプリで1回限りの設定を行い、マーケティング担当者がモバイルアプリVECの機能を使用できるようになります。

Adobe Target VEC拡張機能の有効化について詳しくは、Adobe [Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) のAdobe Target- Visual Experience *Composerを参照*してください。

## Mobile SDKとTargetライブラリのインクルード {#sdk-library}

1. ポッドを追加して、自分のプロジェクト [!DNL Podfile] にライブラリを追加`ACPTargetVEC`します。
1. XCode で Objective-C アプリケーションプロジェクトを開きます。
1. プロジェクトビルド設定に移動し、設定済みの場合は「常にすぐに標準ライブラリを埋め込む」を「はい」に設定します。
1. プロジェクトのビルド設定で「その他のリンカーフラグ」を検索し、まだ存在しない場合は `$(inherited)` を追加します。
1. Objective-C 専用プロジェクトの場合は、swift ファイルを作成してブリッジヘッダーを作成します。これにより、Swift 用のアプリケーション環境を設定します。
1. ディープリンクハンドラーを追加します。

   1. アプリケーションのプロジェクト設定で、 「**[!UICONTROL 情報]**」をクリックします。
   1. **[!UICONTROL &quot;URLタイプ]**」で、三角形をクリックして開き、プラス記号をクリックして新しいフィールドを追加します。
   1. 次の情報を追加します。

      * 識別子: `com.adobe.sdktest`
      * URLスキーム: `vectester`
      * 役割：Editor
   1. アプリケーションプロジェクト設定／**[!UICONTROL 一般]**をクリックします。
   1. Objective-C アプリケーションプロジェクト設定／**[!UICONTROL Info]を再度クリックして、設定が保存されたことを確認します。**

      URL のタイプの例では、アプリケーションの URL スキームは次のようになります。

      ```
      vectester://com.adobe.sdktest
      ```


1. XCode で、[!DNL AppDelegate] ファイルを開きます。
1. ファイルの最上部に、インポートの最後に次の行を追加します。

   `#import "ACPTargetVEC.h"`

   Swiftを使用している場合は、次の行を追加します。

   `import ACPTargetVEC`

1. [!DNL AppDelegate] ファイル内で、次の行を追加 `AppDelegate::application:didFinishLaunchingWithOptions:` します。デリゲート関数が定義されていない場合は、デリゲート関数を作成し、次の行を Objective-C または Swift アプリケーションに追加します。

   ```
   // CONFIGURATION LINE FOR OBJECTIVE C ONLY (Skip any framework which is not applicable for you): 
   [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
   [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
   [ACPLifecycle registerExtension]; 
   [ACPIdentity registerExtension]; 
   [ACPUserProfile registerExtension]; 
   [ACPTarget registerExtension];
   
   [ACPTargetVEC registerExtension];
   [ACPCore start:^{
        [ACPCore lifecycleStart:nil];
   }];
   
   // CONFIGURATION LINE FOR SWIFT ONLY: 
   ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
   ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
   ACPLifecycle.registerExtension() 
   ACPIdentity.registerExtension() 
   ACPUserProfile.registerExtension() 
   ACPTarget.registerExtension() 
   
   ACPTargetVEC.registerExtension() 
   
   ACPCore.start {
     ACPCore.lifecycleStart(nil)
   }
   ```

   例えば、メソッドは次のサンプルのようになっている必要があります。

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY: 
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions { 
        // Override point for customization after application launch. 
       [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"]; 
       [ACPCore setLogLevel:ACPMobileLogLevelDebug]; 
       [ACPLifecycle registerExtension]; 
       [ACPIdentity registerExtension]; 
       [ACPUserProfile registerExtension]; 
       [ACPTarget registerExtension]; 
   
       [ACPTargetVEC registerExtension]; 
   
       [ACPCore start:nil]; 
       [ACPCore lifecycleStart:nil]; 
   
      return YES; 
   } 
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY: 
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey : Any]? = nil) 
   { 
       ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID") 
       ACPCore.setLogLevel(ACPMobileLogLevel.debug) 
       ACPLifecycle.registerExtension() 
       ACPIdentity.registerExtension() 
       ACPUserProfile.registerExtension() 
       ACPTarget.registerExtension() 
   
       ACPTargetVEC.registerExtension() 
   
       ACPCore.start(nil) 
       ACPCore.lifecycleStart(nil)
   
       return true 
   
   }
   ```

1. 先頭に次の行を追加 `AppDelegate:application:openURL` します。デリゲート関数が定義されていない場合は、デリゲート関数を作成し、次の行を追加します。

   ```
   // URL HANDLER LINE FOR OBJECTIVE C ONLY: 
   [ACPTargetVEC handleDeepLink:url];
   
   // URL HANDLER LINE FOR SWIFT ONLY: 
   ACPTargetVEC.handleDeepLink(url)
   ```

   例えば、メソッドは次のサンプルのようになっている必要があります。

   ```
   // EXAMPLE OVERRIDE METHOD FOR OBJECTIVE C ONLY:
   -  (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary<NSString *, id> *)options {
    [ACPTargetVEC handleDeepLink:url];
    return YES;
   }
   
   // EXAMPLE OVERRIDE METHOD FOR SWIFT ONLY:
   func application(_ app: UIApplication, open url: URL, options: [UIApplication.OpenURLOptionsKey : Any] = [:]) -> Bool {
      ACPTargetVEC.handleDeepLink(url)
      return true;
   }
   ```

1. アプリケーションをビルドして実行し、それを使用してMobile App VEC機能をテストします。

## モバイルアプリでのターゲットビューの設定 {#views}

Adobe Mobile SDK は、新しいビューが表示された際にトリガーする新しいメソッドを開発者に公開します。iOSアプリ用のTargetビューAPI呼び出しを適切に挿入する方法については、一般的なガイドラインをお読みください。iOS では、すべての Target ビューが、それらが表示される `UIViewController` に対して定義されます。したがって、Android とは異なり、`TargetViews` の挿入は次の呼び出しに制限されます。

Adobe Mobile App VEC Extensionは、サブクラス化のクラス名に基づいて、Mobile App VECフレームワーク内でやり取り `UIViewControllers` するための名前を自動生成 `UIViewController`します。これらの名前をオーバーライドする場合は、次のメソッドを呼び出すこと `viewWillAppear``ViewController`ができます。

```
// TARGET VIEW LINE FOR OBJECTIVE C ONLY 
[ACPTargetVEC setTargetView:@"exampleViewController"]; 
   
// TARGET VIEW LINE FOR SWIFT ONLY 
ACPTargetVEC.setTargetView("exampleViewController")
```

Adobe Mobile SDK は、実行時にカスタムビューをターゲットにする代替メソッドをデベロッパーに公開します。デベロッパーは、ビューの名前が一意であることを確認する必要があります。ビューを追加する前に、次のメソッドを呼び出し `superview`ます。

```
// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN OBJECTIVE C 
CustomPopupView *popupView = [[CustomPopupView alloc] initWithFrame:CGRectMake(0, 0, 300, 200)]; 
[ACPTargetVEC setTargetView:@"myCustomPopupView" forView:popupView];

// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN SWIFT 
let popupView = CustomPopupView.init(frame: CGRect(x: 0, y: 0, width: 300, height: 200)) 
ACPTargetVEC.setTargetView("myCustomPopupView", for: popupView)
```

## プロファイルパラメーターとその他のグローバルパラメーターの設定 {#parameters}

各API呼び出しで渡されるグローバルパラメーターの設定、および対応するビューにmbox/ビューパラメーターを渡すことができるようになりました。

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
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setGlobalRequest(targetParams)
```

**次のビュートリガーのパラメーターを渡す操作：**

アプリにある各ビューコントローラーの「」`AUTO_<viewControllerName>`など、デフォルトで作成された自動表示がいくつかあります。これらのパラメーターを渡すには、次の API を呼び出します。

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
var product : ACPTargetProduct = ACPTargetProduct.init(id: "1234", categoryId: "furniture") 
var order : ACPTargetOrder = ACPTargetOrder.init(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"]) 
var targetParams : ACPTargetParameters = ACPTargetParameters.init(parameters: mboxParams, profileParameters: profileParams, product: product, order: order) 
ACPTargetVEC.setRequest(targetParams)
```

**特定のビューにパラメーターを渡す操作：**

APIのトリガービューを確認 `TargetVEC.targetView("view_name")`しました。次のように、特定のビューに固有のパラメーターを渡すこともできます。

```
//For Objective-c 
[ACPTargetVEC setTargetView:@"VIEW_NAME" withParameters:TARGET_PARAMS];

//FOR SWIFT 
ACPTargetVEC.setTargetView("VIEW_NAME", with: TARGET_PARAMS)
```

## プリフェッチAPIの明示的な呼び出し {#section_373DB4527FC649C58FBA3DF0C18C9836}

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

