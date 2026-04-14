---
keywords: ai アシスタント；ai アシスタント；コンテンツ生成；コンテンツアクセラレーター；コンテンツ生成；コンテンツ生成
description: ' [!DNL AI Assistant]で魅力的なコンテンツを生成する方法について説明します。'
title: ' [!DNL AI Assistant] in [!DNL Target] を使用して魅力的なコンテンツを生成するにはどうすればよいですか？'
feature: Overview
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
exl-id: eb6f07d8-729e-4f94-ae7a-a054bf54b030
source-git-commit: f6034e83564a9a386e21e4e57279c66cc3c94537
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 1%

---

# [!DNL AI Assistant]の[!DNL Adobe Target]をコンテンツ生成に使用

[!DNL Adobe Target]さんと[!DNL AI Assistant]のエンゲージメントとコンバージョンを促進します。 生成AIを活用して、オーディエンスの共感を呼び、アクティビティやコンテンツを向上させる、パーソナライズされたインパクトの大きいテキストを作成します。

## 前提条件

1. 前提条件となるタスクが[で完了したことを確認します。 [!DNL Adobe Experience Platform] [!DNL AI Assistant]を [!DNL Adobe Target]](/help/main/c-intro/enabling-ai-assistant.md)で有効にします。

   * 組織はまず法的条件に同意する必要があります。 詳しくは、Adobe アカウントチームにお問い合わせください。
   * 管理者は、[!DNL AI Assistant]にアクセスするための十分な権限を付与する必要があります。

## テキストを生成

[!DNL AI Assistant]を使用して魅力的なテキストを生成するには：

1. [[!DNL Target] [!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md) （VEC）内から、VEC UIの右側のパネルにある&#x200B;**[!UICONTROL Show Content Assistant]** （![&#x200B; コンテンツアシスタントアイコン &#x200B;](/help/main/assets/icons/MagicWand.svg)）アイコンをクリックします。

   ![&#x200B; コンテンツアシスタントアイコンを表示](/help/main/c-intro/assets/ai-assistant-conntet-generation-icon.png)

1. [!DNL AI Assistant]を使用して昇格するテキスト要素をクリックします。

   例えば、ヒーローテキストを変更するには、「次の休暇を計画」をクリックしてテキストオプションを表示します。

   ![&#x200B; テキスト設定ペイン &#x200B;](/help/main/c-intro/assets/ai-text-settings.png)

1. （オプション） **フルスクリーンアイコン** （![&#x200B; フルスクリーンアイコン &#x200B;](/help/main/assets/icons/FullScreen.svg)）をクリックして、[!DNL AI Assistant]を展開します。

1. **[!UICONTROL Prompt]** ボックスに、生成するテキストを記述します。

   たとえば、季節ごとのバケーションセールには、「期間限定の夏休みセールを広告する魅力的なヒーローテキストを書く」と入力するとします。

   以下の[&#x200B; バリエーションの例](#variations)を参照して、[!DNL AI Assistant]がシンプルなプロンプトをどのように魅力的で長い形式の広告コピーに変換し、エキサイティングなニューヨークの冒険を実現するかを確認してください。

1. **[!UICONTROL Text Settings]** アイコンをクリックして、テキストのトーンとコミュニケーション戦略を指定します。

   * **コミュニケーション戦略**：生成したテキストに最適なコミュニケーション スタイルを選択します。

     オプションには、[!UICONTROL None]、[!UICONTROL Urgent]、[!UICONTROL FOMO] （見落としを恐れる）、[!UICONTROL Social Proof]、[!UICONTROL Scarcity]、[!UICONTROL Incentive]、[!UICONTROL Exclusivity]、[!UICONTROL Gameification]、[!UICONTROL Informative]および[!UICONTROL Education & Insights]が含まれます。

   * **言語**: テキストに使用する言語を選択します。

     [!DNL AI Assistant]は現在英語でのみ利用できます。

   * **トーン**: テキストのトーンは、オーディエンスの心に響くものでなければなりません。 有益で、刺激的で、遊び心があり、説得力のあるメッセージを表示したい場合でも、[!DNL AI Assistant]はメッセージを適切に調整できます。

     オプションには、[!UICONTROL None]、[!UICONTROL Professional]、[!UICONTROL Empathetic]、[!UICONTROL Humorous]、[!UICONTROL Exciting]、[!UICONTROL Inspirational]、[!UICONTROL Persuasive]、[!UICONTROL Friendly]、[!UICONTROL Formal]、[!UICONTROL Apologetic]、[!UICONTROL Assertive]、[!UICONTROL &#x200B; Story Telling]および[!UICONTROL Conversational]が含まれます。

1. スライダーを使用して、テキストの長さを短くする長さを選択します。

1. （オプション） **[!UICONTROL Brand Assets]**&#x200B;をクリックして、生成中に追加のコンテンツコンテキスト用のブランドアセットをアップロードまたは切り替えます。

1. 「**[!UICONTROL Generate]**」をクリックして、テキストのバリエーションのリストを作成します。

   ![AI アシスタントのテキストのバリエーション &#x200B;](/help/main/c-intro/assets/ai-variations-text.png)

1. **[!UICONTROL Apply]**&#x200B;をクリックして、目的のテキストバリエーションを選択します。

   **[!UICONTROL Preview]**&#x200B;をクリックして、様々なバリエーションを表示することもできます。 目的のバリエーションをクリックし、**[!UICONTROL Select]**&#x200B;をクリックします。

   生成されたテキストを含む![AI アシスタント &#x200B;](/help/main/c-intro/assets/ai-text-done.png)

1. （条件付き）変更を元に戻すには、[!UICONTROL Undo] アイコン（![取り消しアイコン &#x200B;](/help/main/assets/icons/Undo.svg)）をクリックします。

1. （オプション） [!DNL AI Assistant]にフィードバックを提供します。

   * サムズアップアイコン（![&#x200B; サムズアップ &#x200B;](/help/main/assets/icons/ThumbUp.svg)）をクリックして、[!DNL AI Assistant]にバリエーションが気に入っていることを伝えます。
   * 下の親指（![下の親指アイコン &#x200B;](/help/main/assets/icons/ThumbDown.svg)）アイコンをクリックして、[!DNL AI Assistant]にバリエーションが気に入らないことを伝えます。
   * [!UICONTROL Report Results] （![結果を報告アイコン &#x200B;](/help/main/assets/icons/Flag.svg)）アイコンをクリックして、問題を[!DNL AI Assistant]に報告します。

## バリエーションの例 {#variations}

ヒーローテキストの変更は始まりに過ぎません。 [!DNL AI Assistant]の[!DNL Target]では、基本的な編集に限定されません。 エクスペリエンス全体をまたいで、コンテンツを制作、洗練、向上させる力を手に入れましょう。 バリエーションのブレインストーミングから、メッセージの最適化、新しいコピーの生成に至るまで、[!DNL AI Assistant]は生成AIのパワーを活用して、魅力的でインパクトの大きいコンテンツを数秒で作成することができます。

次のプロンプトとバリエーションは、[!DNL AI Assistant]の機能を示しています。

**[!UICONTROL Prompt]**: ニューヨークへの3日間の旅行の魅力的な広告を作成して、上位の目的地を訪問します。
**[!UICONTROL Text Settings]**: FOMO、英語、説得力、Mediumの長さ
* **[!UICONTROL Variation 1]**: 3日間の特別旅行で、ニューヨーク市の魅力を発見しましょう！ タイムズスクエア、セントラルパーク、自由の女神像などの象徴的な観光スポットに浸りましょう。 眠ることのない街のスリルと美しさを既に経験している数え切れないほどの他の人に参加してください。 忘れられない思い出をお見逃しなく。 今日は冒険を予約して、興奮の一部になってください！ 限定スポットあり！
* **[!UICONTROL Variation 2]**: 3日間の特別な休暇で、ニューヨーク市の魅力を発見しましょう！ タイムズスクエアやセントラルパークなどの象徴的なランドマークを訪れ、世界クラスの食事やエンターテイメントに没頭してください。 忘れられない冒険をお見逃しなく。 スペースは限られており、誰もが自分の素晴らしい体験を高く評価しています。 今すぐ予約して、世界中の旅行者を魅了する興奮の一部になってください！
* **[!UICONTROL Variation 3]**：象徴的なランドマークが待っているニューヨークへのスリリングな3日間のエスケープに乗り出しましょう！ タイムズスクエアの電気の雰囲気やマンハッタンの料理を堪能し、エンパイアステートビルからの息をのむような景色を堪能しましょう。 今すぐ行動し、夢を生きる無数の冒険家に参加してください。 決して眠らない街で忘れられない思い出を作り出すことを忘れないでください。 限定的な機能。 今すぐ冒険を予約しましょう！
* **[!UICONTROL Variation 4]**：今すぐ3日間のニューヨークの冒険を予約して、これまでにない街の魔法を体験しましょう！ 象徴的な観光スポットから隠れた宝石まで、ビッグAppleのあらゆるコーナーにはエキサイティングなものがあります。 他の人が既に楽しんでいる忘れられない瞬間を逃さないでください。 話題の一部になってください。 今日の場所を確保し、生涯続く思い出を作りましょう。 急いで、スペースは素早く埋まっています！

## トレーニングビデオ

### AI アシスタントを利用して、コンテンツを制作する

>[!VIDEO](https://video.tv.adobe.com/v/3434635/?learn=on">https://video.tv.adobe.com/v/3434635/?learn=on)
