---
description: Target の新たな SDK ライブラリを利用すると、デベロッパーが Android のモバイルアプリケーションのセットアップを一度おこなえば、マーケティング担当者がモバイル Visual Experience Composer（VEC）の機能を使用できるようになります。
keywords: mobile vec;mobile visual experience composer;mobile experience composerオプション;設定;android
seo-description: Adobe Targetの新しいSDKライブラリを使用すると、開発者はAndroidモバイルアプリで1回限りのセットアップを行うことができ、マーケティング担当者はMobile Visual Experience Composer（VEC）の機能を使用できます。
seo-title: Android- Adobe Target用のモバイルアプリの設定
solution: 'Target '
title: Android - モバイルアプリケーションのセットアップ
topic: Standard
uuid: 39938ec2-b12e-44cf-9218-69195fba0ff7
translation-type: tm+mt
source-git-commit: b2504613c0b86a83ae68c01ae6fe5f5d780d9193

---


# Android - モバイルアプリケーションのセットアップ{#android-set-up-the-mobile-app}

Adobe Target Mobile App Visual Experience Composer（VEC）を使用すると、開発者は Android モバイルアプリで 1 回限りの設定を行い、マーケティング担当者がモバイルアプリ VEC の機能を使用できるようになります。

Adobe Target VEC 拡張機能の有効化について詳しくは、[Adobe Experience Platform Mobile SDK](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) の *Adobe Target - Visual Experience Composer* を参照してください。

## Mobile SDK と Target のライブラリを追加する {#sdk-library}

1. SDK V5 の初期化について詳しくは、[SDK の初期化とトラッキングのセットアップ](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk)を参照してください。
1. 次の行を dependencies セクションに追加します。

   ```
   implementation 'com.adobe.marketing.mobile:target:1.+'
   implementation 'com.adobe.marketing.mobile:target-vec:1.+'
   ```

1. モバイルアプリ VEC では、次のアーティファクトを依存関係として `build.gradle` に含める必要があります。

   ```
    implementation 'android.arch.lifecycle:extensions:1.1.1'
    implementation 'io.github.sac:SocketclusterClientJava:1.7.5'
    implementation 'com.android.support:support-compat:28.0.0'
    implementation 'com.android.support:support-fragment:28.0.0'
   ```

1. `AndroidManifest.XML` ファイルに intent-filter を追加します。その際、Mobile VEC オーサリング用に一意のディープリンクスキームを選択します（例えば `[sdkbetabus://com.adobe.sdkbetabus](sdkbetabus://com.adobe.sdkbetabus)`）。

   ```
   <activity 
       android:name=".listing.MoviesListingActivity" 
       android:launchMode="singleTask"> 
       <intent-filter> 
           <action android:name="android.intent.action.VIEW" /> 
   
           <category android:name="android.intent.category.DEFAULT" /> 
           <category android:name="android.intent.category.BROWSABLE" /> 
   
           <data 
               android:host="com.adobe.sdkbetabus" 
               android:scheme="sdkbetabus" /> 
       </intent-filter> 
   </activity>
   ```

1. モバイルプロジェクトに移動し、`Application::onCreate override` の最後に次の行を挿入します。

   ```
   public class SDKTest extends MultiDexApplication { 
   
       @Override 
       public void onCreate() { 
           /* Put Your App's implementation */ 
           MobileCore.setApplication(this); 
           MobileCore.setLogLevel(LoggingMode.DEBUG); 
           MobileCore.configureWithAppID("YOUR_ADOBE_LAUNCH_APP_ID"); 
   
           ... 
           try { 
               TargetVEC.registerExtension(); //Single line code to initialize TargetVEC
               Target.registerExtension();
               Identity.registerExtension();
               Lifecycle.registerExtension();
               Signal.registerExtension();
               MobileCore.start(null);
           } catch (InvalidInitException e) { 
             .. 
           }
       }
   
   /* Rest of Application test goes here ... */
   ```

1. ビルドが動作しない場合、既定でビルドされるはずの以下のプロジェクトの例を参照し、次の箇所の変更を確認してください。

   1. `Application::OnCreate override`
   1. `AndroidManifest.XML`
   1. Android アプリケーションの `build.gradle`

## モバイルアプリケーションで Target ビューをセットアップ {#views}

Adobe Mobile SDK は、新しいビューが表示された際にトリガーする新しいメソッドを開発者に公開します。開発者は、ビューの名前が一意であり、UI のメインスレッド上で `targetView` が呼び出されるようにしなければなりません。この節では、まず、2 つの異なるデモンストレーションアプリケーションでこれらの呼び出しを適切に挿入する方法を示し、あらゆる Android アプリケーションで Target ビュー API の呼び出しを適切に挿入する方法について全般的なガイドラインを説明します。

>[!NOTE]
>
>トリガーされない場合、`targetView function` VEC拡張機能は Android アクティビティからの表示を識別しようとします。動的ビューを持たないアプリケーションの場合、これはオプションの手順です。

Target ビューは、関数の呼び出しでトリガーできます。任意のターゲティングパラメーターは、オプションでビューに提供できます。

```
public class TargetVEC { 
   
   /** 
    * Marks a view hierarchy for editing in Mobile App VEC.  Call must insert when the view hierarchy 
    * is memory and committed to being shown, but not yet shown on the screen. 
    * 
    * @param viewName the unique Target View Name 
    */ 
   public static void targetView(String viewName); 
  
  /** 
   * Trigger Target view 
   * Triggering a Target view may cause Target offers to be applied on the current container component. 
   * Note that Target offers are applied from local Target cache, so flicker should be negligible. 
   * 
   * @param viewName Mandatory Target View name, which must be unique at app level 
   * @param parameters Parameters to be included in the next Target call 
   */ 
  
    public static void targetView(String viewName, TargetParameters parameters); 
}
```

最初のプロジェクト例は、単純なバスのスケジュールアプリケーションのモックアップです。Mobile アプリケーション VEC でこのアプリケーションを利用するには以下の通り設定します。

1. Android Studio で、`build.gradle` パッケージサブディレクトリ内の `BusBooking` ファイルでプロジェクトを開きます。
1. `DemoApplication::OnCreate` このメソッドで、`TargetVEC.registerExtension()` Target VEC拡張機能を他の拡張機能と共に登録します。
1. アプリケーションをビルドして実行します。
1. Mobile アプリケーション VEC オーサリングモードに入るには、[!DNL sdkbetabus://com.adobe.sdkbetabus] を URL スキームとして使用し、デバイスで生成されたディープリンクを開きます（下記の説明を参照してください）。

このシンプルなバス予約アプリケーションから、アクティビティライフサイクルに関連して自動生成されたすべての Target ビューを利用します。さらに、隠れたボタンをクリックした際に動的に追加されるカスタムビュー要素の Target ビュー API を呼び出し、API の柔軟性を示します（画面上のオファー画像）。この新しい Target ビューは、コードの `OfferDetailsActivity.java:40` で API 呼び出しを挿入することで実装されています。隠れたボタンをクリックすると、「SURPRISE_VIEW」という新しい Target ビュー要素が呼び出され、マーケティング担当者がアプリケーションエクスペリエンス上の変更のターゲットをより正確に決められます。

ターゲット化した動的ビューの挿入：

```
package com.adobe.target.examples.bus; 
   
import android.app.DialogFragment; 
import android.os.Bundle; 
import android.os.Handler; 
import android.support.v7.app.AppCompatActivity; 
import android.support.v7.widget.Toolbar; 
import android.view.View; 
import android.view.ViewGroup; 
import android.widget.LinearLayout; 
import android.widget.Toast; 
   
import com.adobe.target.mobile.TargetVEC; 
   
/** 
 * This activity class is responsible to show offer details 
 */ 
public class OfferDetailsActivity extends AppCompatActivity { 
    @Override 
    protected void onCreate(Bundle savedInstanceState) { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_offer_details); 
        setUpToolBar(); 
        final Handler mainHandler = new Handler(getApplicationContext().getMainLooper()); 
   
        final View surpriseView = getLayoutInflater().inflate(R.layout.suprise_layout, 
                (ViewGroup) findViewById(android.R.id.content), false); 
   
        final View imagePresentView = this.findViewById(R.id.image_present); 
        final LinearLayout currentLayout = this.findViewById(R.id.offer_layout); 
   
        imagePresentView.setOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                Toast.makeText(getApplicationContext(),"Surprise!", Toast.LENGTH_SHORT).show(); 
                mainHandler.post(new Runnable() { 
                    @Override 
                    public void run() { 
                        currentLayout.addView(surpriseView); 
                        TargetVEC.targetView("SURPRISE_VIEW"); 
                        currentLayout.invalidate(); 
                    } 
                }); 
                // One-shot.  Remove clicker afterwards. 
                imagePresentView.setOnClickListener(null); 
            } 
        }); 
    } 
   
    private void setUpToolBar() { 
        Toolbar toolbar = findViewById(R.id.toolbar); 
        toolbar.setNavigationIcon(R.drawable.abc_ic_ab_back_material); 
        toolbar.setTitle("Buy 1 Get 1"); 
        toolbar.setNavigationOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                onBackPressed(); 
            } 
        }); 
    } 
   
    @Override 
    protected void onPause() { 
        super.onPause();
        MobileCore.lifecyclePause();
    } 
   
    @Override 
    protected void onResume() { 
        super.onResume();
        MobileCore.lifecycleStart(null);
    } 
}
```

## プロファイルパラメーターとその他のグローバルパラメーターの設定{#parameters}

この時点で、各 API 呼び出しで渡されるグローバルパラメーターを設定する操作と、mbox／ビューパラメーターを対応するビューに渡す操作がサポートされるようになりました。

パラメーターには次のものがあります。

* mbox／ビューパラメーター
* プロファイルパラメーター
* 製品パラメーター
* 注文パラメーター

**グローバルパラメーターのサポート：**

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("mboxparam1", "mboxvalue1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekey1", "profilevalue1"); 
  
TargetVEC.setGlobalRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**次のビュートリガーのパラメーターを渡す場合：**

アプリケーションに存在する各アクティビティとフラグメントに対してデフォルトで作成される自動ビュー（「`AUTO_<activity|fragment name>`」など）がいくつか用意されました。これらのパラメーターを渡すには、次の API を呼び出します。

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("viewKey1", "viewparam1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekeyforview1", "profilevalueforview1"); 
  
TargetVEC.setRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**特定のビューにパラメーターを渡す操作：**

`TargetVEC.targetView("view_name")` 経由でビューをトリガーする API については既に紹介しました。次のように、特定のビューに固有のパラメーターを渡すこともできます。

```
Map<String, String> profileParams = new HashMap<>(); 
profileParams.put("surprisekey1", "surprisevalue1");  //ProfileParams 
TargetVEC.targetView("SURPRISE_VIEW", 
        new TargetParameters.Builder() 
                .profileParameters(profileParams) 
                .product(new TargetProduct("3354", "kitchen")) 
                .build());
```

## プリフェッチ API の明示的な呼び出し {#section_2D02B74558474D3BA9F25E4D25E7C7E3}

ときには、プリフェッチ API を再度呼び出してキャッシュに保存されているオファーを更新しなければならないことがあります。公開されている API とその説明を以下に示します。

* **prefetchOffers**

   ```
   /** 
    * Prefetch Target offers. 
    * Note that calling this will pre-hide the current layout, until Target offers are prefetched 
    * and applied to currently visible Target views, possibly causing flicker, thus it's recommended 
    * to call this method inside the containing component's onCreate() lifecycle method 
    */ 
   public static void prefetchOffers();
   ```

* **prefetchOffersBackground**

   ```
   /** 
    * Prefetch Target offers in the background. 
    * Note, that in contrast to prefetchOffers(), calling this method will NOT pre-hide 
    * the current layout, instead prefetched Target offers will be only be cached and will subsequently 
    * be applied as Target Views are being triggered. 
    */ 
   public static void prefetchOffersBackground();
   ```

## チュートリアル:Mobile AndroidアプリケーションへのExperience Cloudの実装 {#tutorial}

* [Mobile AndroidアプリケーションへのExperience Cloudの実装](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-android-apps-with-launch/index.html)

このチュートリアルを完了すると、次のことが可能になります。

* モバイル開始プロパティの作成
* Androidアプリへの起動プロパティのインストール
* 以下のAdobe Experience Cloudソリューションを実装します。
   * Experience Cloud ID サービス
   * Adobe Target
   * Adobe Analytics
   * Adobe Audience Manager

* 開発環境、ステージング環境および実稼動環境での変更の発行
