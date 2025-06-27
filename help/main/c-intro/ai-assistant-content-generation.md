---
keywords: ai アシスタント；人工知能アシスタント；コンテンツ生成；コンテンツアクセラレーター；コンテンツ生成；コンテンツの生成
description: ' [!DNL AI Assistant] を使用して魅力的なコンテンツを生成する方法を説明します。'
title: ' [!DNL AI Assistant] in [!DNL Target]  を使用して魅力的なコンテンツを生成する方法'
feature: Overview
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
exl-id: eb6f07d8-729e-4f94-ae7a-a054bf54b030
source-git-commit: f8e91caa133a1addc12ab1834d7e178df7e7a3ce
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 1%

---

# コンテンツ生成に [!DNL Adobe Target] の [!DNL AI Assistant] を使用

[!DNL AI Assistant] を使用して、エンゲージメントとコンバージョン [!DNL Adobe Target] 促進します。 ジェネレーティブ AI を活用して、オーディエンスの共感を呼び、アクティビティ コンテンツを強化する、パーソナライズされた効果的なテキストを作成します。

## 前提条件

1. [ の有効化  [!DNL Adobe Experience Platform] [!DNL AI Assistant] で前提条件のタスクを完了していることを確認し  [!DNL Adobe Target]](/help/main/c-intro/enabling-ai-assistant.md) ください。

   * 組織はまず法的条件に同意する必要があります。 詳しくは、Adobe アカウントチームにお問い合わせください。
   * 管理者から、[!DNL AI Assistant] にアクセスするための十分な権限を付与してもらう必要があります。

## テキストを生成

[!DNL AI Assistant] を使用して魅力的なテキストを生成するには：

1. [[!DNL Target] [!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) （VEC）内から、VEC UI の右側のパネルにある **[!UICONTROL Show Content Assistant]** ール ![ コンテンツアシスタントアイコンを表示 ](/help/main/assets/icons/MagicWand.svg)）アイコンをクリックします。

   ![Content Assistant アイコンを表示 ](/help/main/c-intro/assets/ai-assistant-conntet-generation-icon.png)

1. [!DNL AI Assistant] を使用して昇格させるテキスト要素をクリックします。

   例えば、ヒーローテキストを変更するには、「次の移行を計画」をクリックして、テキストオプションを表示します。

   ![ テキスト設定ペイン ](/help/main/c-intro/assets/ai-text-settings.png)

1. （任意） **フルスクリーンアイコン** （![ フルスクリーンアイコン ](/help/main/assets/icons/FullScreen.svg)）をクリックして展開 [!DNL AI Assistant] ます。

1. **[!UICONTROL Prompt]** ボックスに、生成するテキストを入力します。

   例えば、季節限定の夏休みのセールには、「夏物セールを宣伝する魅力的なヒーローテキストを書く」と入力します。

   シンプルなプロンプトを魅力的で長 [!DNL AI Assistant] 形式の広告コピーに変換して、エキサイティングな NYC アドベンチャーを実現する方法については、以下の [ バリエーションの例 ](#variations) を参照してください。

1. **[!UICONTROL Text Settings]** アイコンをクリックして、テキストのトーンとコミュニケーション戦略を指定します。

   * **コミュニケーション方法**：生成テキストに最適なコミュニケーションスタイルを選択します。

     オプションには、[!UICONTROL None]、[!UICONTROL Urgent]、[!UICONTROL FOMO] （欠落恐怖）、[!UICONTROL Social Proof]、[!UICONTROL Scarcity]、[!UICONTROL Incentive]、[!UICONTROL Exclusivity]、[!UICONTROL Gameification]、[!UICONTROL Informative] および [!UICONTROL Education & Insights] があります。

   * **言語**：テキストに必要な言語を選択します。

     [!DNL AI Assistant] は現在、英語でのみ利用できます。

   * **トーン**：テキストのトーンは、オーディエンスの共感を呼ぶはずです。 有益な情報を伝えたい、エキサイティングな内容を伝えたい、遊び心がある、説得力がある内容を伝えたいなど、目的に応じてメッセージを調整で [!DNL AI Assistant] ます。

     オプションには、[!UICONTROL None]、[!UICONTROL Professional]、[!UICONTROL Empathetic]、[!UICONTROL Humorous]、[!UICONTROL Exciting]、[!UICONTROL Inspirational]、[!UICONTROL Persuasive]、[!UICONTROL Friendly]、[!UICONTROL Formal]、[!UICONTROL Apologetic]、[!UICONTROL Assertive]、[!UICONTROL  Story Telling] および [!UICONTROL Conversational] があります。

1. スライダーを使用して、テキストの長さ（[!UICONTROL Shorter Text]～[!UICONTROL Larger Text]）を選択します。

1. （任意）「Brand Assets」をクリックして、生成中に追加のコンテンツコンテキスト用にブランドアセットをアップロードまたは切り替えます。

1. 「**[!UICONTROL Generate]**」をクリックして、テキストバリエーションのリストを作成します。

   ![AI アシスタントのテキストのバリエーション ](/help/main/c-intro/assets/ai-variations-text.png)

1. 「**[!UICONTROL Apply]**」をクリックして、目的のテキストバリエーションを選択します。

   「**[!UICONTROL Preview]**」をクリックして、様々なバリエーションを表示することもできます。 目的のバリエーションをクリックし、「**[!UICONTROL Select]**」をクリックします。

   ![ 生成テキストを使用した AI アシスタント ](/help/main/c-intro/assets/ai-text-done.png)

1. （条件付き） [!UICONTROL Undo] 動アイコン（取り消しアイコン ![）をクリックして ](/help/main/assets/icons/Undo.svg) 変更を元に戻します。

1. （任意） [!DNL AI Assistant] ーザーにフィードバックを提供します。

   * サムズアップアイコン（![ サムズアップ ](/help/main/assets/icons/ThumbUp.svg)）をクリックすると、バリエーションが気に入 [!DNL AI Assistant] ていることが表示されます。
   * サムズダウン （![ サムズダウンアイコン ](/help/main/assets/icons/ThumbDown.svg)）アイコンをクリックして、バリエーションが気に入らないことを [!DNL AI Assistant] に知らせます。
   * [!UICONTROL Report Results] （結果を報告アイコン ![ アイコンをクリック ](/help/main/assets/icons/Flag.svg) て、問題を [!DNL AI Assistant] に報告します。

## バリエーションの例 {#variations}

ヒーローテキストの変更は、ほんの始まりにすぎません。 [!DNL AI Assistant] in [!DNL Target] を使用すると、基本的な編集に限定されません。 エクスペリエンス全体でコンテンツを作成、調整、昇格させる権限が付与されます。 バリエーションのブレーンストーミング、メッセージの最適化、その場での新しいコピーの生成など、[!DNL AI Assistant] はジェネレーティブ AI の力を活用して、説得力のある、インパクトの高いコンテンツを数秒で作成できます。

次のプロンプトとバリエーションは、[!DNL AI Assistant] のパワーを示しています。

**[!UICONTROL Prompt]**：主要な目的地を訪問するためにニューヨークへ 3 日間の旅行のために魅力的な広告を書いてください。
**[!UICONTROL Text Settings]**: FOMO、英語、説得力、Medium length。
* **[!UICONTROL Variation 1]**: 3 日間の特別な旅行でニューヨークの魔法を発見しましょう！ タイムズスクエア、セントラルパーク、自由の女神などの象徴的な観光スポットに浸りましょう。 すでに眠らない街のスリルと美しさを体験した無数の人に参加しましょう。 忘れられない思い出をお見逃しなく。 今日のあなたの冒険を予約して、興奮の一部である！ スポット限定！
* **[!UICONTROL Variation 2]**: 3 日間の特別な休暇でニューヨークの魔法を発見しましょう！ タイムズスクエアやセントラルパークなどの象徴的なランドマークを訪れ、ワールドクラスの食事やエンターテイメントに浸りましょう。 この忘れられない冒険をお見逃しなく。 スペースは限られており、誰もが彼らの素晴らしい経験について誇りに思っています。 今すぐ予約して、世界中の旅行者を魅了する興奮の一部になってください。
* **[!UICONTROL Variation 3]**：象徴的なランドマークが待つニューヨークに 3 日間のスリリングな逃走に乗り出そう！ Times Square の電動式雰囲気を体験し、マンハッタンで美味しい料理を味わい、エンパイアステートビルから息を呑むような景色を眺めることができます。 今行動し、彼らの夢を生きて無数の冒険に参加しています。 眠らない街に、忘れられない思い出を作ってみませんか。 スポットは限定されています。 今日のあなたの冒険を予約！
* **[!UICONTROL Variation 4]**：今すぐ 3 日間のニューヨークでのアドベンチャーを予約して、これまでにない魔法の街を体験してください。 象徴的な観光スポットから隠された宝石まで、ビッグAppleの隅々にはエキサイティングな何かが存在します。 他の人がすでに楽しんでいる忘れられない瞬間をお見逃しなく。 話題の一部である。 今日のあなたの場所を確保し、一生の思い出を作成します。 急いで、スペースはすぐに充填されている！

## トレーニングビデオ

### AI アシスタントを使用したコンテンツ生成の作成

>[!VIDEO](https://video.tv.adobe.com/v/3434635/?learn=on">https://video.tv.adobe.com/v/3434635/?learn=on)
