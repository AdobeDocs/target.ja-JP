---
keywords: ウェルカムキット;Target ウェルカムキット;概要;概要;はじめに
description: Adobe  [!DNL Target]  で初めてのアクティビティに着手して、投資の ROI を獲得しましょう。
title: Target で初めてアクティビティを作成する必要があります。何から始めればよいでしょうか。
feature: Overview
exl-id: 4d07b088-a577-4c82-b35f-18d0be8428d8
source-git-commit: 4564e0b95bbd19f20c75e5e83d452d12a5403083
workflow-type: tm+mt
source-wordcount: '1724'
ht-degree: 76%

---

# 第 7 章：初めての [!DNL Target] アクティビティの作成と実行

[!DNL Target] の最初のアクティビティを使い始める準備はよろしいですか？ 良。複雑すぎず、迅速に ROI を獲得できるので、[!DNL Target] を使用したテストやパーソナライズの可能性に期待できる、Web サイトやモバイルサイト、またはモバイルアプリのアクティビティを探してみましょう。 組織とその組織が何に重点を置いているかに応じて、最初のアクティビティで 3 つのルートのうち 1 つの使用を検討しているとします。

ただし、最初のアクティビティで重要なのは、改善しようとするビジネス指標のベースライン（売上高、クリックスルー数、フォーム送信、完了した登録など）を確立することです。 A/B テストでは、現在のエクスペリエンスやオファーを「コントロール」として使用し、そのエクスペリエンスやオファーのバリアントの影響を測定できます。 ただし、ほとんどのパーソナライゼーションアクティビティでは、パーソナライズされたバージョンを起動する前に、現在のエクスペリエンスのパフォーマンスを判断するのが理想的です。 これにより、パーソナライゼーションの影響を測定できます。

## ルート 1：すべての訪問者トラフィックに対する A/B テスト

基本的な [A/B テストアクティビティ](/help/main/c-activities/t-test-ab/test-ab.md)を設定し、オファーやエクスペリエンスの 1 つのバリエーションを、他の 1 つ以上のバリエーションと比較してテストし、訪問者の好みを確認できます。勝者のバリアントのみを探している場合は、A/B テストのセットアップワークフローの 2 番目の手順で [ 自動配分 ](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) を選択し、AI を活用して迅速に結果を得ることを選択できます。

例：あるメディア会社は、Web またはモバイルサイトのホームページ上でのギフト購読オファーに対して現在のコピーをテストし、どのバリエーションでより多くの訪問者がギフト購読を購入するかを調べます。自動配分を選択した場合、アクティビティは、テストの実行時に、より多くのトラフィックを勝者のバリエーションにシフトします。そうでない場合は、テストが終了した後に、ユーザーが手動で勝者エクスペリエンスをライブにプッシュするまで待機します。

## ルート 2：特定のオーディエンスに対するパーソナライズ

貴重なことがわかっている特定のオーディエンスにターゲットを設定し、それらのオーディエンスから共感を得られることがわかっているオファーやエクスペリエンスを提供する[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md)（XT）アクティビティを設定できます。

例：航空会社は、プラチナレベルメンバーをターゲットに設定し、次回航空便チケットを購入した際に倍のポイントを付与する特別なオファーを提供し、顧客の忠誠度をさらに高められるようにします。

## ルート 3：個別の訪問者に合わせて AI と自動化を適用

A/B テストのセットアップワークフローの 2 番目の手順で「[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)」を選択するだけで、複数のエクスペリエンスの中から各訪問者に最高のエクスペリエンスを提供する AI 駆動アクティビティを設定できます。最初のアクティビティで自動ターゲットを使用すると、どのエクスペリエンスが様々な訪問者の共感を得られるかわからない場合に非常に役立ちます。 自動ターゲットを使用すると、機械学習によってリアルタイムに予測属性を評価し、スコアを算出できます。また、提供するエクスペリエンスを決定する際に、訪問者の属性のうち何が最も重要かを特定できます。

例：複数の電話のブランドやモデルを販売する電話会社は、自動ターゲットをオンにして自動処理と機械学習を利用し、ホームページやモバイルアプリで開いている画面の 4 種類のエクスペリエンスやオファーのうち、幅広い訪問者から最も共感を得られるものを特定します。

## アクティビティのアイデアの生成

ボタンの色やコピーの変更テストは基本的に実行できますが、[!DNL Target] が重要なビジネス指標をどのくらい進められるかを示すことができるテストやパーソナライズはどうでしょうか。経営幹部レベルのエグゼクティブや事業部門のリーダーを驚かせること。

容易に実装でき、ビジネスに大きな影響を与える可能性のあるアクティビティのアイデアを思いつくには、次のような方法があります。

* **自分の知識を活用します。**&#x200B;貴社はおそらく、顧客を熟知しており、何が彼らの共感を得られるかをご存知でしょう。これを使用して、パーソナライズされたエクスペリエンスを開発します。
* **分析ソリューションを使用する。**&#x200B;顧客が購入フローから外れたり、ページから離脱する場所を、サイトから探します。ページのレビューを実施し、望ましいアクションを起こす前に顧客が退出してしまう可能性について、仮設を立てます。
* **自身の観察力を活用する。** Web サイトの主要ページをいくつか見て、改善が必要なものを直感的に特定します。製品の詳細ページが混みすぎていたり、文字が多すぎる場合は、シンプルにします。 購入ボタンが見つかりにくい場合は、より目立つ場所に移動させます。
* **競合他社を観察する。** 競合他社の Web サイトを確認することで、ビジネスの成果を促す効果が高いと思われるデザイン、オファー、コピー、その他の要素が明らかになる場合があります。 これらのアプローチを自社のサイトで試す方法を検討します。
* **顧客のフィードバックを利用する。**&#x200B;顧客は既に、オンライン調査やカスタマーサービスへの連絡を通じて、顧客体験を改善するためのアイデアを提供している可能性があります。複数の人が言及した問題箇所を特定し、それを排除できる可能性のあるエクスペリエンスを考え出します。

テストのアイデアを考え出す際には、提案したテストのアイデアが、ビジネスにとって重要な顧客体験と指標を改善できると考える理由を、データを使用して説明できると理想的です。

## アクティビティプランナーを使用してアクティビティを計画する

[Adobe Target アクティビティプランナー ](/help/main/assets/activity-planner.pdf) は、保存して何度も繰り返し使用できるスタンドアロンPDFとして含まれています。 PDF ファイルへのリンクをクリックして表示します。右クリックして PDF ファイルをダウンロードします。

有効なアクティビティを実行するには、プランナーの各領域に入力する必要があります。このツールは、テストとパーソナライゼーションのアクティビティに関するアイデアのブレインストーミングの際に使用します。

![Adobe Target アクティビティプランナー](/help/main/c-intro/assets/activity-planner.png)

プランナーの各領域には、次のような種類の考えを入力します。

### 改善可能な点は何か？

改善したいチャネルまたはタッチポイントを選択します。項目の URL を追加するか、説明します。この場合、テストバリエーションまたはパーソナライズされたエクスペリエンスの作成に使用する Web ページの URL を追加します。

### 仮説はどのようなものか？

現在の Web ページのエクスペリエンスに関する問題を、問題の特定に使用したデータやソースも含め、明確に説明します。変更を計画している内容と、それが顧客体験を向上させると考える理由を説明します。最後に、期待される結果を説明し、この新しいエクスペリエンスがもたらすと想定されるビジネス成功指標のビジネス価値を説明します。

### どのような種類のアクティビティが必要か？

実行するアクティビティの種類のボックスを選択します。[Target のアクティビティタイプ](/help/main/c-activities/target-activities-guide.md)のトピックや [Adobe Targetの製品概要](/help/main/c-intro/target-welcome-kit-2.md)の章を確認し、利用できる様々なタイプのアクティビティを理解します。

### ターゲットオーディエンスは誰か？

例えば、コントロールのエクスペリエンスとバリアントを含む A/B テストでは、訪問者の母集団全体を含めることができます。デフォルトでは、[!DNL Target] は 50％をコントロールに、50％をバリアントに配信します。しかし、パーソナライズをおこなう場合は、パーソナライズする 1 人または複数のオーディエンスを記述できます。AI を使用する際には、個人に合わせてパーソナライズするために AI を使用していることに注意してください。アクティビティに特定のオーディエンスを選択する場合は、その理由を仮説で述べておく必要があります。

### アクティビティの影響を測定するための主要指標は何か？

アクティビティの成功のインジケーターとして使用するビジネス指標について説明します。例えば、訪問者あたりの売上高（RPV）、コンバージョン率、平均注文額（AOV）の増加などです。影響をビジネスの収益に結び付けるほど、影響と売上高を結び付けることができるので理想的です。

### アクティビティの影響を測定するためのサブ指標は何か？

これは主要指標と同じです。アクティビティがビジネスに与える影響を測定するのに役立つ指標を選択します。

### 関与する必要のあるリソース／チームは？

アクティビティにデザイナー、web 開発者またはデータアナリストのサポートが必要な場合はそれらをここに記載し、アクティビティの一部として彼らが行う必要のあることを説明します。

### テストを実行する場合、有意性を達成するためには、このテストはどれくらいの期間実行する必要があるか？

テストから統計的に有意な結論を導くには、テスト母集団に特定の数の訪問者を含む必要があります。テストの参加者が 2 人だけであった場合、テスト結果を信頼できるでしょうか。

[!DNL Target] は、統計的な原則に基づいて、テストの結果が統計的に有効であることを判断します。[!DNL Adobe Target][ サンプルサイズ計算ツール ](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) を使用すると、結果に必要な信頼性に基づき、テストの実行期間を決定できます。 このボックスの「[!UICONTROL Learn More]」リンクをクリックして、計算ツールを開いて使用します。

### このアクティビティはどのくらい重要か。

組織には、必要なすべてのテストとパーソナライゼーションのアクティビティを実行するためのリソースが無限にあるわけではありません。この領域を使用して、数値（例 1 ～ 5）や、低、中、高のラベルを割り当て、ビジネスに対するこのアクティビティの相対的な重要度を反映させます。多くの場合、アクティビティの優先順位付けは、アクティビティの設定にかかる労力、時間、コストのレベルと、提供される可能性がある見返りのレベルを考慮しておこなわれます。

### どのような結果が得られるか？

アクティビティが完了したら、結果を文書化し、その結果を元の仮説や、アクティビティで使用した重要なオーディエンス、アクティビティの結果を評価しようとしていた前述の主要成功指標およびサブ成功指標に結び付けます。次章では、そのアクティビティ結果について説明します。

### アクティビティで絞り込む必要のあるもの／次のステップは何か？

アクティビティの結果により、次に取るべき行動に対するインサイトが得られることがよくあります。エクスペリエンスのバリエーションが大幅に成功した場合は、それを Web サイトにハードコーディングする必要があります。その成功を類似した他のページに適用する機会がわかる場合があります。結果により、このページの顧客体験を改善するために必要な多くの作業がわかることがあります。この領域を使用して、アクティビティから主な学習事項を文書化し、それらの学習事項に基づいてするべき対応を文書化します。

## [!DNL Target] の起動とアクティビティの作成および開始

アクティビティプランナーに入力しました。 次に、ソリューションを検討し、アクティビティを構築します。 [!DNL Target] を使用すると、[!UICONTROL Visual Experience Composer] で web ページを簡単に変更できます。
