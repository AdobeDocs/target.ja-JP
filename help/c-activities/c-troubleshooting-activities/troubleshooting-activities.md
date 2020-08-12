---
keywords: troubleshoot target;troubleshooting target;default content;test not live;activity not live;targeting not working;previous experience displays;cannot create activities;can't create activities;create activities;page structure changed;page structure modified;error message;error delete profile script;ajax not working
description: サイトにアクティビティが表示されない場合は、ここに示すトラブルシューティングの提案が解決に役立ちます。
title: アクティビティのトラブルシューティング
feature: null
topic: Advanced,Standard,Classic
uuid: 5b22c369-0efc-48c0-a0dc-0179b18536fe
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 81%

---


# アクティビティのトラブルシューティング{#troubleshoot-activities}

サイトにアクティビティが表示されない場合は、ここに示すトラブルシューティングの提案が解決に役立ちます。

>[!NOTE]
>
>以下のトラブルシューティング情報に加えて、「[Target のトラブルシューティング](../../r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839)」を参照して、その他のトラブルシューティングトピック、FAQ、アクティビティやその他の機能のトラブルシューティングに関するのリンクを参照してください[!DNL Adobe Target]。

以下のセクションでは、発生する可能性のある問題が推奨ソリューションと共に説明します。

## ターゲットUIを使用してアクティビティを作成しましたが、APIを使用して更新できません。

ターゲットUIを使用して作成されたアクティビティは、ターゲットUIを使用して更新する必要があります。 APIを使用して作成されたアクティビティは、APIを使用して更新する必要があります。 例えば、最初にAPIを使用してアクティビティを作成した後、後でターゲットUIを使用してアクティビティを編集した場合、すべての変更が更新されるわけではありません。 すべての変更はバックエンドに保存され、別のAPI呼び出しを行うことで更新できます。

ベストプラクティスとして、最初にアクティビティを作成するのに使用したのと同じアクティビティ（UIまたはAPI）を使用して、メソッドを更新してみてください。

## デフォルトコンテンツが表示される。

アクティビティが完了し、アクティブ化済みであることを確認します。

## アクティビティが実行されない。

**検証：**「概要」タブに移動し、テストが非アクティブまたはドラフトに設定されていないかどうかを確認します。

**オプション：**

* テストをアクティブ化します。
* 「リンクをプレビュー」を使用して、非アクティブなテストを表示します。

## オーディエンスのターゲット設定条件に適合しない。

**検証：**&#x200B;概要ページでターゲット設定条件を確認します。

**オプション：**

* ターゲット設定条件に適合したら、もう一度試みます。
* 「リンクをプレビュー」を使用して、ターゲット設定条件を省略します。

## ページがページのターゲット設定条件に適合しない。

**検証：**&#x200B;概要ページで、ページがターゲット設定条件外にないかどうかを確認します。

**オプション：**

* Visual Experience Composer に移動し、「URL」／「詳細」／「現在のページ」の順にクリックします。

## 新しいエクスペリエンスではなく、以前のエクスペリエンスが表示される。

**検証：**&#x200B;下のいずれかのオプションを試して、エクスペリエンスを再度表示してみます。

**オプション：**

* キャッシュと cookie をクリアして、もう一度試みます。

* 別のブラウザーを使用してみます。
* プライベート／匿名モードを使用します。

## Target に最近追加されたユーザーがアクティビティを作成できない。

**検証：**「アクティビティを作成」をクリックします。オプションが有効でない場合、たいていは、アクティビティを作成するのに十分な権限がありません。

**オプション：**

Target でユーザーとして追加されたら、アクティビティを作成するために承認者の役割が必要です。

* 承認者にしてもらうよう、アカウントの管理者に依頼します。
* If you are the Admin, give yourself the Approver role from **[!UICONTROL Administration]** > **[!UICONTROL Users]** in Target.

   「[承認者の役割の割り当て](../../administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)」を参照してください。

## アクティビティの設定後、ページの構造が変更された。

**検証：**&#x200B;既存のアクティビティについて Visual Experience Composer に移動します。セレクター（または構造）が変更されたことを示す警告メッセージを探します。

**オプション：**

* アクティビティを再構築します。

ページ構造が Target の表示機能に与える影響について詳しくは、[ページ修正のシナリオ](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)を参照してください。

## ページの読み込み中にページの構造が変更される。

**検証：**&#x200B;開発者に問い合わせてください。

**注意：**&#x200B;アクティビティの変更を適用する必要がある場所を Target が認識できるように、同じクラスの要素を動的に挿入したり、兄弟のクラスを動的に修正したりするのを避けてください。

**オプション：**

* ページコードを更新して、テストする各要素を一意に識別します（id を使用）。
* 前述のとおり、クラスや兄弟を動的に修正するのを止めます。

ページ構造が Target の表示機能に与える影響について詳しくは、[ページ修正のシナリオ](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB)を参照してください。

## mbox.js が &lt;head> から後続のすべてのコードを &lt;body> に移動する。

**検証：**&#x200B;ソースを表示して、終了タグより前の位置で、mbox.js ファイルの後に宣言が行われているかどうかを確認します </body> 。

**オプション：**

* mbox.js を、ページの `<head>` セクション内の最後の要素として配置します。
* body 内の最上位レベル要素に一意の div id を使用します。

## 同じページ上で他のアクティビティが実行される。

**検証：**「衝突」タブを使用して、他のアクティビティが実行されているかどうかを確認します。

**注意：**「衝突」タブは、テンプレートテストモジュールでは機能しません。

**オプション：**

* このアクティビティの優先度を高くします。
* 他のアクティビティの優先度を低くします。
* 他のアクティビティのアクティブ化を解除します。

## プロファイルスクリプトを削除する際にエラーメッセージが表示される。

**検証：** Target Standard/Premium からプロファイルスクリプトを削除すると、「プロファイルスクリプトを削除できませんでした」というエラーメッセージが表示されるかどうかを確認します。

**オプション：**

次のいずれかを実行します。

* もう一度削除します。成功メッセージが表示されます。
* Target Standard/Premium インポーターが実行されるまで、約 10 分待ちます。インポーターがプロファイルスクリプトのリストを更新します。

## Some ajax [!DNL Target] calls are not working.

**注意：**[!DNL Target]同じ 名で異なるパラメーターを持つ複数の ajax 呼び出しは、同じページでは動作しません。最初の呼び出しのみ作成されます。

## You activated an activity using the Target API, but the activity shows a status of [!UICONTROL Inactive] in the Target UI.

Target API を使用した UI 外でのアクティビティのアクティブ化など、特定のアクションを実行する場合、更新が UI に反映されるまで最大 10 分かかることがあります。