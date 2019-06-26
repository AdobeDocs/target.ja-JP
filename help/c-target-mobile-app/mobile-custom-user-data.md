---
description: 場所やユーザーに関する追加情報を名前と値のペアとして Target に送信できます。
keywords: モバイルアプリ、モバイルアプリ送信データ、targetモバイルアプリ、モバイルカスタムユーザーデータ、モバイルアプリのカスタムデータ
seo-description: 場所やユーザーに関する追加情報を名前と値のペアとして Target に送信できます。
seo-title: iOS - カスタムユーザーデータの送信
title: iOS - カスタムユーザーデータの送信
topic: 'Target '
uuid: 00baa1e2-4d1c-4835-ac55-47c9ac8985ac
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# iOS - カスタムユーザーデータの送信{#ios-send-custom-user-data}

場所やユーザーに関する追加情報を名前と値のペアとして Target に送信できます。

この情報は、カスタムオーディエンス（例えば、25,000 マイルを超えたユーザー）の構築とレポートで使用できます。

Target の呼び出しで送信できるパラメーターには次の 2 種類があります。

* mbox パラメーター

   Mbox パラメーターは、セッションを超えて持続しません。
* プロファイルパラメーター

   プロファイルパラメーターは、訪問者のプロファイルストアに保存され、セッションを超えて持続します。Mbox パラメーターは永続的ではありません。一部のキーは予約されていますが、プロファイルと mbox の両方のパラメーターはカスタムのキーと値のペアとすることができます。

予約済みのキーがありますが、プロファイルと mbox の両方のパラメーターにはカスタムのキーと値のペアを含めることができます。

1. 辞書を作成します。

   まず、Target に渡すために送信する値で辞書を作成します。利便性のため、これを `welcomeMessageCampaign` メソッドの内部に追加すると、範囲について考慮する必要がなくなります。

   次にサンプルの辞書を示します。コピー `(void)welcomeMessageCampaign` することができます。`userLevel` や `userMiles` のようなキーの値は、この例ではハードコードされています。通常は、対応する変数を使用して渡します。

   ```
   NSDictionary *targetParams = [[NSDictionary alloc] initWithObjectsAndKeys: 
                                 @"platinum",@"userLevel", 
                                 @26500,@"userMiles", 
                                 @"1067007",@"entity.id", 
                                 @"dealsapp.qa", @"host", 
                                 @"fashion",@"entity.categoryId", 
                                 @"millenial", @"profile.persona", 
                                 @"cohort_5", @"profile.cohort", 
                                 nil];
   ```

   * プレフィックスプロファイルのあるキー（例えば、`profile.persona`）は、ユーザーのプロファイルに保存されます。

      これらのプロファイル属性は、様々なアクティビティおよびチャネルで使用できます。

   * プレフィックスのないキー（例えば、`userMiles`）は mbox パラメーターです。

      これらのパラメーターは、セッション中にのみ利用できます。

   * プレフィックスエンティティのあるキー（例えば、`entity.category.id`）は製品のレコメンデーションで使用されます。

1. データを検証します。
   1. アプリケーション `didFinishLaunchingWithOptions` で、コメントを解除または追加 `[ADBMobile setDebugLogging:YES];` します。

      これにより、詳細なデバッグログが出力されます。
   1. アプリを構築します。
   1. Target の呼び出しにパラメーターが渡されていることを確認します。

      デバッグコンソールで Target の場所の名前を検索します。先ほど渡したすべてのパラメーターとともに、`YOUR-CLIENT-CODE.tt.omtrdc.net` への呼び出しが表示されます。

      ![](assets/mobile-debug.png)
   Target Standard では、オーディエンスを構築して、これらのパラメーターを使用し、コンテンツの表示を制限またはターゲット設定することができます。
