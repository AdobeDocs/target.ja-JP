---
keywords: target のトラブルシューティング;target トラブルシューティング;デフォルトコンテンツ;テストが実行されない;アクティビティが実行されない;ターゲティングが動作しない;以前のエクスペリエンスが表示される;アクティビティを作成できない;アクティビティを作成できない;アクティビティの作成;ページ構造の変更;ページ構造の修正;エラーメッセージ;プロファイルスクリプト削除エラー;ajax が動作しない
description: Adobe  [!DNL Target] アクティビティがサイトに表示されない場合は、トラブルシューティングの提案を調べます。
title: アクティビティのトラブルシューティング方法
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: f1cbc46323f71c2fa091cd2c9a3e49d34676e7a1
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 50%

---

# アクティビティのトラブルシューティング

サイトに [!DNL Adobe Target] アクティビティが表示されない場合は、ここに示すトラブルシューティングの提案が解決に役立ちます。

>[!NOTE]
>
>以下のトラブルシューティング情報に加えて、「[Target のトラブルシューティング](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839)」を参照して、その他のトラブルシューティングトピック、FAQ、アクティビティやその他の機能のトラブルシューティングに関するのリンクを参照してください[!DNL Adobe Target]。

以下の節では、推奨される解決策で発生する可能性のある問題について説明します。

## [!DNL Target] UI を使用してアクティビティを作成しましたが、API を使用して更新できません。

を使用して作成されたアクティビティ [!DNL Target] UI は、 [!DNL Target] UI API を使用して作成されたアクティビティは、API から更新する必要があります。もともと API を使用してアクティビティを作成したが、後で [!DNL Target] UI は、すべての変更が更新されるわけではありません。 すべての変更はバックエンドに保存され、別の API 呼び出しをおこなうことで更新できます。

ベストプラクティスとして、最初にアクティビティを作成した際と同じアクティビティ（UI またはAPI）を使用して、メソッドを更新してみてください。

## デフォルトコンテンツが表示される。

アクティビティが完了し、アクティブ化済みであることを確認します。

## アクティビティが実行されない。

**検証：** に移動します。 [!UICONTROL 概要] 」タブに移動して、テストが非アクティブまたはドラフトに設定されていないかどうかを確認します。

**オプション：**

* テストをアクティブ化します。
* 「リンクをプレビュー」を使用して、非アクティブなテストを表示します。

## オーディエンスのターゲット設定条件に該当しない。

**検証：**&#x200B;概要ページでターゲット設定条件を確認します。

**オプション：**

* ターゲット設定条件に適合したら、もう一度試みます。
* 「リンクをプレビュー」を使用して、ターゲット設定条件を省略します。

## ページがページターゲット条件の対象にならない。

**検証：** の [!UICONTROL 概要] ページで、ページがターゲット設定条件外にないかどうかを確認します。

**オプション：**

* 次に移動： [!UICONTROL Visual Experience Composer]」で、 URL /詳細/現在のページをクリックします。

## 新しいエクスペリエンスではなく、以前のエクスペリエンスが表示される。

**検証：**&#x200B;下のいずれかのオプションを試して、エクスペリエンスを再度表示してみます。

**オプション：**

* キャッシュと cookie をクリアして、もう一度試みます。
* 別のブラウザーを使用してみます。
* プライベート／匿名モードを使用します。

## [!DNL Target] に最近追加されましたが、アクティビティを作成できません。

**検証：**「[!UICONTROL アクティビティを作成]」をクリックします。オプションが有効でない場合、たいていは、アクティビティを作成するのに十分な権限がありません。

**オプション：**

ユーザーとして [!DNL Target]、 [!UICONTROL 承認者] ロールを使用してアクティビティを作成できます。

* アカウントの管理者に問い合わせて、承認者にしてもらいます。
* 管理者の場合は、 [!UICONTROL 承認者] の役割 **[!UICONTROL 管理]** > **[!UICONTROL ユーザー]** in [!DNL Target].

   「[承認者の役割の割り当て](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)」を参照してください。

## アクティビティの設定後、ページの構造が変更された。

**検証：**[!UICONTROL 既存のアクティビティについて Visual Experience Composer に移動します。]セレクター（または構造）が変更されたことを示す警告メッセージを探します。

**オプション：**

* アクティビティを再構築します。

ページの変更の影響の詳細 [!DNL Target]表示する機能： [ページ修正のシナリオ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## ページの読み込み中にページの構造が変更される。

**検証：**&#x200B;開発者に問い合わせてください。

**注意：** 次のために [!DNL Target] アクティビティの変更が適用される場所を認識するには、同じクラスを持つ要素を動的に挿入したり、兄弟のクラスを動的に変更したりしないでください。

**オプション：**

* ページコードを更新して、テスト対象の各要素を一意に識別します（ID を使用）。
* 前述のとおり、クラスや兄弟を動的に修正するのを止めます。

ページの変更の影響の詳細 [!DNL Target]表示する機能： [ページ修正のシナリオ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## 同じページ上で他のアクティビティが実行される。

**検証：** 以下を使用： [!UICONTROL 衝突] タブをクリックして、他のアクティビティが実行中かどうかを確認します。

**注意：**[!UICONTROL 「衝突」タブは、テンプレートテストモジュールでは機能しません。]

**オプション：**

* このアクティビティの優先度を高くします。
* 他のアクティビティの優先度を低くします。
* 他のアクティビティのアクティブ化を解除します。

## プロファイルスクリプトを削除する際にエラーメッセージが表示される。

**検証：**[!DNL Target] からプロファイルスクリプトを削除すると、「プロファイルスクリプトを削除できませんでした」というエラーメッセージが表示されるかどうかを確認します。

**オプション：**

次のいずれかを実行します。

* プロファイルスクリプトを再度削除します。 成功メッセージが表示されます。
* を 10 分ほど待つ [!DNL Target] 実行するインポーター。 インポーターがプロファイルスクリプトのリストを更新します。

## 一部の ajax [!DNL Target] 呼び出しが機能しない。

**注意：** 複数の ajax [!DNL Target] 同じ名前で異なるパラメーターを持つ呼び出しは、同じページでは機能しません。 最初の呼び出しのみがおこなわれます。

## [!DNL Target] API を使用してアクティビティをアクティブ化しましたが、アクティビティのステータスが [!DNL Target] UI に[!UICONTROL 非アクティブ]として表示されます。

UI 外でのアクティビティのアクティブ化など、特定のアクションを実行するときに、 [!DNL Target] API：更新が UI に反映されるまでに最大 10 分かかる場合があります。

## アクティビティコンバージョン後、その訪問者はどのエクスペリエンスにも含まれません。

まれに、エクスペリエンスの条件を満たすアクティビティのコンバージョン指標が、アクティビティの条件と同じリクエストで送信された場合、リクエストの送信後、訪問者がどのエクスペリエンスにも含まれないことがあります。 この状況では、訪問者は、トークン経由でキャプチャされたデフォルトコンテンツとエクスペリエンス ID が —1 となっています。 [!DNL Adobe] では、同じでアクティビティの選定とコンバージョンを送信することはお勧めしません [!DNL Target] リクエスト。

両方の指標を同じリクエストで送信する場合は、 [!UICONTROL 詳細設定] を使用して、コンバージョン後も訪問者が同じエクスペリエンスにとどまるように指定します。
