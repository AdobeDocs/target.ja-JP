---
keywords: Target Standard;FQA;よくある質問;参照シート;早わかりシート
description: ' [!DNL Target] の機能の使用方法に関するよくある質問のリストです。詳細情報の情報やリンクも紹介します。'
title: 最適化とパーソナライゼーションに関する質問の回答はどこで見つけることができますか？
feature: Overview
exl-id: 75e29d2a-78e7-40aa-b134-36a7cc8b3ed8
source-git-commit: 6304cafb00916491cbeab0299f527df56da30ee6
workflow-type: tm+mt
source-wordcount: '2693'
ht-degree: 72%

---

# Target の最適化とパーソナライゼーションに関する FAQ

[!DNL Adobe Target] 機能の使用に関するよくある質問への回答を示します。 より深いインサイトを得るための直接リンクを使用して、実験を最適化し、エクスペリエンスをパーソナライズし、役立つリソースにアクセスする方法について説明します。

## 一般情報 {#section_CE5713B5AAC341C9A75586C107797FA3}

**更新された [!DNL Target] UI と [!UICONTROL Visual Experience Composer] （VEC）に関する情報はどこで入手できますか？**

+++詳細を見る

ユーザーインターフェイスは、[!DNL Target] を最大限に活用できるよう、論理的かつユーザーにわかりやすい形式で配置されています。以下の概要は、[!DNL Target] と VEC に慣れるのに役立ち、より詳細な情報と手順を説明するリンクを提供します。

詳しくは、[ [!DNL Target] UI について ](/help/main/c-intro/understand-the-target-ui.md) を参照してください。

+++

**他の顧客が [!DNL Target] をどのように有効活用しているのかを知ることはできますか？**

+++詳細を表示
実際の [ カスタマーサクセスストーリー ](https://www.adobe.com/jp/marketing-cloud/target/resources.html#x) を調べ、組織が [!DNL Target] をどのように活用して最適化を高め、エクスペリエンスをパーソナライズし、測定可能なビジネス成果を達成しているかを確認します。

+++

**最新の [!DNL Target] 機能について知るには、どこを参照してください。**

+++詳細を表示
最新のリリース [!DNL Target] 常に更新します。

* **最新リリース**：新機能、機能強化、バグ修正について詳しくは、[[!DNL Target]  リリースノート（最新） ](/help/main/r-release-notes/release-notes.md) を参照してください。
* **今後のリリース**:[[!DNL Target]  リリースノート（プレリリース） ](/help/main/r-release-notes/target-release-notes.md) にアクセスすると、次のリリースをプレビューできます。
* **以前のバージョン**：履歴の更新と変更については、[ 以前のリリースのリリースノート ](/help/main/r-release-notes/release-notes-for-previous-releases.md) を参照してください。

+++

**[!DNL Adobe] に関 [!DNL Target] る回答や詳細情報を見つけられるコミュニティやフォーラムはありますか？**

+++詳細を表示
[!DNL Target]Target コミュニティフォーラム [ で ](https://experienceleaguecommunities.adobe.com/t5/adobe-target/ct-p/adobe-target-community?profile.language=ja){target=_blank} の実務担当者の仲間とつながります。 専門知識を共有し、質問し、[!DNL Target] を使用している他のユーザーと共同作業してパーソナライゼーションと実験を推進します。 繁栄する社会は積極的な参加にかかっています。 あなたの洞察と経験は、他の人が成功するのに役立ちます。 ジャンプして投稿し、必要な回答を見つけます。

+++

**どのブラウザーがサポートされて [!DNL Target] ますか？**

+++詳細を表示
詳しくは、[ サポートされているブラウザー ](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/supported-browsers.html?lang=ja){target=_blank} マトリックスを参照してください。 デスクトップ/デバイスでの [!DNL Target Standard/Premium] インターフェイスのサポートとエンドユーザーブラウザーのサポートの 2 つの側面があることに注意してください。

+++

## アクティビティ {#section_CB95B3BF9934445DB98E8A7E22FC2CF6}

**統計的有意性に優れた手法で、コントロールエクスペリエンスを使用しながら勝者と敗者のエクスペリエンスを見極めることはできますか？**

[A/B テスト](/help/main/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)（手動ターゲット設定オプション）と[サンプルサイズ計算ツール](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_286EB6E671184239BB1552F0387DAEB5)の使用が最適です。

**アクティビティを停止するタイミングはどのように判断すればよいですか？**

データが不十分な段階でアクティビティを停止してしまうと、間違った結論が導かれる恐れがあります。[よくあるミスと、それを回避する方法](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md#section_DF01A97275E44CA5859D825E0DE2F49F)を確認してください。また、「[A/B テストを実行すべき期間はどのくらいですか？](/help/main/c-activities/t-test-ab/sample-size-determination.md)」も参照してください。

**期間が短い場合は、アクティビティをどのように実行すればよいですか？**

**テストを実施して目標に合わせた最適化をおこなうことはできますか？**

[レポートを参照して勝者のエクスペリエンスを見極めてください。](/help/main/c-activities/automated-traffic-allocation/determine-winner.md#concept_5741A89ED7224E1285A3BC34B2CCD0F9)

**一定のレベルのパーソナライゼーションを中核に据えてアクティビティを実行することはできますか？**

[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)オプションをチェックします。

**ニーズに合ったアクティビティタイプを見極めるには、どうすればよいですか？**

詳細については、「[Target アクティビティタイプ](/help/main/c-activities/target-activities-guide.md#concept_D974B0918EB74B3B8CB07ACD32BF37A1)」を参照してください。Adobe Target の各オプションがどのようなシナリオに適しているのかについて解説しています。

また、[Recommendations アクティビティ](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)も検討してください。

**効果が高いページ要素の組み合わせを把握したり、各要素がどの程度の効果を発揮しているのかを確認したりするためには、どうすればよいですか？**

お客様のニーズに対応できる可能性があるため、[全因子多変量分析（MVT）アクティビティ](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)と要素の貢献度分析を確認してください。

ただし、MVT アクティビティではトラフィック要件は厳しくなります。

**構成が異なる複数のページにまたがるアクティビティを実行できますか？**

**複数の場所（チェックアウトプロセスの各ページなど）でオファーを適用できますか？**

エクスペリエンス内で複数ページを使用できる[複数ページアクティビティ機能](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48)をお試しださい。

**目標（プライマリまたはセカンダリ）の達成後はユーザーに再度そのアクティビティを表示することはせず、別のアクティビティを表示するようにするには、どうすればよいですか？**

あらゆる目標で利用できる「[詳細設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_E2FE441AFB324E498793ABB025ED9974)」オプションを使用すれば、簡単に実現できます。各オプションを利用し、ユーザーが目標に達した後の処理方法や、カウントを増分する方法を指定できます。

このケースでは、「カウントを増分、ユーザーをリリース、再入場を許可しない」と「デフォルト / 他のアクティビティのコンテンツ」を選択することで対処できます。他のオプションもチェックしてみてください。

**アクティビティで複数の目標を作成しました。レポートや分析のために、ファネルとして一連の目標の流れを作成することはできますか？**

**例えば、特定のファネルの数値を追跡するために、ユーザーが目標 A を達成した後に目標 B を追跡したいと考えています。**

Target の指標依存関係の機能を利用すれば可能です。[他の成功指標の依存関係](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B)を追加するだけです。「到達」、「未到達」などのオプションを利用したり、様々な方法で指標を結合し、あらゆる組み合わせを作成したりできます。

**目標達成のためにアクティビティを適切に設定するには、どうすればよいですか？**

そのためにあるのが[目標](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)です。

まず、何を重視して最適化をおこなうかを把握します。売上高、コンバージョン、エンゲージメントなどが考えられます。これらの各オプションは目標のセクションで利用できます。それぞれのオプションで、目標達成の条件と見なすサイトでのユーザー行動を定義できます。

この設定は、プライマリ目標設定（3 ステップのガイドによるワークフローのステップ 3）で指定できます。他の目標を追加し、レポートのデータの質を高めることもできます。

**スケジュールを設定し、特定の日時にアクティビティを開始して終了させることはできますか？**

3 ステップのガイドによるワークフローの[目標と設定ステップのスケジュール設定機能](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC)で、開始日時と終了日時を指定できます。

忘れずにアクティビティを有効にしてください。指定したスケジュールが適用されるのは、ライブアクティビティのみです。終了日に達したら、そのアクティビティのステータスは終了になります。

**編集用に 3 ステップのガイド付きワークフロー全体を実行するのではなく、[!UICONTROL Targeting] ステップのみを変更することはできますか？**

[アクティビティの概要ページから直接対象の手順に移動し、](/help/main/c-activities/edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0)「保存して閉じる」オプションを使用してその手順を終了します。

**特定のステップに留まってアクティビティ（オファーのテキストやカスタムコードなど）を編集しながら、別のタブで QA を実行することはできますか？**

これも可能です。単に [ 保存オプションを使用して、手順を離れることなく増分変更を行うことができます ](/help/main/c-activities/edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0)。

**作成したばかりのアクティビティのプレビューを確認し、QA を実行するにはどうすればよいですか？**

[強力な QA モード機能](/help/main/c-activities/c-activity-qa/activity-qa.md)を利用して、QA を実行できます。QA チームでリンクを共有して、レポートを含めたエンドツーエンドのアクティビティ QA を実行することもできます。これにより、アクティビティをライブにした後、テストでの想定どおりに進めることができます。

**[!DNL Target] の意思決定機能を使用して、単一ページアプリケーション（SPA）またはサーバーサイド統合で使用できるエクスペリエンス/オファーを受け取るにはどうすればよいですか？**

その場合は、[フォームベースのアクティビティ](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)と [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D)を利用することで対処できます。

**2 つのアクティビティを設定しました。訪問者にどちらが表示されるのかを把握するには、どうすればよいですか？**

**アクティビティに優先順位を設定することはできますか？**

Target の 3 ステップのガイドによるワークフローのステップ 3 で、優先度設定を使用して[アクティビティの優先度を設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC)できます。

2 つのオプションがあります。

* デフォルトは 3 つのレベル（低／中／高）
* カスタムは 0 ～ 999 の範囲。カスタムの場合は、詳細な優先度機能（管理／Visual Experience Composer）を有効にします。

## オーディエンス {#section_FA6314777ABC46D8B198D6F388051460}

**特定のアクティビティ専用のオーディエンスセグメントを作成できますか？再利用の要素がないため、[!UICONTROL Audience Library] ーム内にそのようなオーディエンスを作成する必要はないと感じています**。

特定のアクティビティ専用のオーディエンスを定義するには、[アクティビティのみのオーディエンス機能](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)を利用してください。

**場所を基準にユーザーをターゲットに設定するには、どうすればよいですか？**

その場合、[地理オーディエンス](/help/main/c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670)を利用します。この機能の精度のレベルを確認してください。

**セッション内で、ページ上の属性を基準にユーザーをターゲットに設定することはできますか？**

mbox と[カスタムオーディエンス](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md#concept_C4C6E00D7C5A4BE9B72D471DB2E3027B)を併用して適切なエクスペリエンスを提供する方法が最適です。

**複数の訪問にまたがり、訪問者属性を基にしてエクスペリエンスを提供することはできますか？**

**2 つのグループにランダムでトラフィックを分割することはできますか？**

その場合、[プロファイルスクリプト機能](/help/main/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)を利用してください。コードを記述する必要がありますが、効果的にエクスペリエンスをパーソナライズできます。

**訪問者数が比較的少ない場合でも、アクティビティを開始できますか？**

その場合は、[Target の 3 ステップのガイドによるワークフローのステップ 2（ターゲット設定ページ）](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087)で、割合による配分調整を使用して、アクティビティの設定方法を指定できます。

**また、[!DNL Adobe Analytics] もあり、[!DNL Target] で活用したいと思っています。 この 2 つを統合することで、主にどのような機能を利用できるようになりますか？**

以下の製品情報を参照してください。

* [Analytics for Target（A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)
* [顧客属性](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html?lang=ja)
* [オーディエンス](/help/main/c-integrating-target-with-mac/mmp.md)

## エクスペリエンス {#section_5959536B8D6A4BEA8FAA1273338F3451}

**構成が共通する複数のページにまたがるアクティビティを実行できますか？**

その場合、[テンプレートルール](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781)を利用して、指定された単一の URL のエクスペリエンスを作成し続けながら、構成が共通する多数のページをアクティビティに追加します。

**[!UICONTROL Visual Experience Composer] （VEC）にページを読み込もうとすると、「ブラウザーがスクリプトを読み込むことを許可」メッセージにうんざりします。 どうすればこの問題を解消できますか？**

これは、サイトに混在したコンテンツがあり、HTTP リソースと HTTPS リソースの両方を取得するサイトであるためです。 IT チームに、HTTPS への完全移行をおこなうよう要求してください。

移行が完了するまでは、「[ブラウザーで混在したコンテンツを有効化する](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md#concept_46D022D50280468C9EF6D5DF6EFC911C)」の手順に従い、ブラウザーに混合するコンテンツの読み込みを許可してください。これは最新のブラウザーのセキュリティ機能です。

**[!UICONTROL Visual Experience Composer] at.js ライブラリがまだデプロイされていない場合でも、サイトで [!DNL Target] （VEC）を試すことはできますか？**

[拡張 Experience Composer](/help/main/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) でページを読み込んでみてください。

**[!UICONTROL Visual Experience Composer] （VEC）内でサイトが読み込まれないのはなぜですか？**

ヘルプページの「[トラブルシューティング情報](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4)」を参照してください。記載されている方法で問題を解消できなかった場合、[アドビサポート](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)までお問い合わせください。

また、「[フォームベースの手法](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)」でブロックを解除できます。

[拡張 Experience Composer](/help/main/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) が役に立つケースと、そのメリットも確認してください。IT 部門に連絡して [Adobeのプロキシ サーバーを許可リストする必要がある場合 ](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6) あります。

**レスポンシブサイトを運営しています。アクティビティの作成中に重要なデバイスでの表示を確認するには、どうすればよいですか？**

その場合、[モバイルビューポート](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5)機能を利用します。この機能は、拡張 Experience Composer が有効になっている場合のみ利用できます。

**複数のドメインがあります。1 つのドメインで [!UICONTROL Enhanced Experience Composer] を有効にする必要があり、その他のドメインでは無効にする必要があります。 これはどうすれば設定できますか？**

いつでも、[アクティビティレベルで拡張 Experience Composer オプション](/help/main/c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D)を利用して、デフォルト設定を上書きできます（セットアップ／Visual Experience Composer）。

**画像を入れ替えるオプションが表示されないのはなぜですか？**

アドビまでお問い合わせいただけば、[お客様のアカウントで Scene7 を有効にします](/help/main/administrating-target/scene7-settings.md#task_37AD0768EFBA4E588955FE3D5DD670A5)。プロビジョニングが終わったら、簡単に別の画像と入れ替えられるようになります。

**一律割引とパーセンテージ割引など、2 種類のエクスペリエンスをテストしたいのですが、エクスペリエンスのターゲットを適切に設定する必要があります（違う国のユーザーには違うロケールのテキストや通貨を表示するなど）。これはどうすれば設定できますか？**

その場合、[複数のエクスペリエンスバージョン機能](/help/main/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md#task_0138112E283A4A5B9F8AB9AAF2FBC2FF)を使用すると簡単に設定できます。この種のテストでは、提供時の微妙な違いにご注意ください。

**[!UICONTROL Visual Experience Composer] （VEC）で行った変更を確認するにはどうすればよいですか？**

変更内容は、「[コードエディター](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5)」に常に表示されます。「変更」タブには、オファーに適用した CSS セレクターまたは mbox が表示されます。

CSS セレクターは Sizzle セレクターです。このセクションで、手早く小さな変更を加えたり特定のオファーを削除したりできます。

**実験／アクティビティの一部として JavaScript を配信し、動的要素に即座に変更を加えたり、サードパーティソリューションに呼び出しを送信したりしたいと考えています。これはどうすれば設定できますか？**

それを行う方法の 1 つは、[カスタムコードエディター](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5)の利用です。該当の JavaScript をセクションに設置すると配信されます。必要に応じて、head 内や body 最上部で配信することもできます。

**[!UICONTROL Visual Experience Composer] （VEC）内のログインページや、内部に深く埋め込まれたページに移動して、特定の URL を持たないのはなぜですか？**

[!UICONTROL Compose] 機能と [!UICONTROL Browse] 機能を使用して目的のページに移動し、エクスペリエンスの作成を開始します。

![ デザインと参照の切り替え ](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

**私は以前 [!DNL Target Classic] ユーザーでした。 特定の用途で自分の mbox を利用することはできますか？**

「[フォームベースの手法](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)」でアクティビティを作成してください。

**目的のオファーやエクスペリエンスが表示されず、別のアクティビティが表示されるのはなぜですか？**

[デバッガー](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md#concept_D2548B486C984B1E97ED7A72075B8EEA)を利用し、[アクティビティの衝突](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md#concept_0BC6B929592744DFA7DA01FF4F91052E)を確認してください。

## オファー {#section_A547B1EAD0B34FD38D3B87AAF62E3963}

**小さな変更を加えるのではなく、まったく違う新しいページをテストしたいと考えています。**

**新発売などに合わせ、新しいランディングページにユーザーを誘導したいと考えています。**

**これはどうすれば設定できますか？**

[リダイレクト URL 機能](/help/main/c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)を使用すると、対象のページにユーザーを誘導できます（現在のクエリパラメーターの有無は問いません）。

**QA プロセスでコンテンツ配信がおこなわれないのはなぜですか？**

お客様のサイトの要素に動的 ID、重複する ID または動的クラスが含まれている可能性があります。アカウントレベル（問題の範囲が特定のドメインやページのみの場合はアクティビティレベル）でサイトの基本設定オプションをチェックすることをお勧めします。[CSS セクター](/help/main/administrating-target/visual-experience-composer-set-up.md#css)を参照してください。

**目的のオファーやエクスペリエンスが表示されず、別のアクティビティが表示されるのはなぜですか？**

[デバッガー](/help/main/c-activities/c-troubleshooting-activities/content-trouble.md#concept_D2548B486C984B1E97ED7A72075B8EEA)を利用し、[アクティビティの衝突](/help/main/c-experiences/c-visual-experience-composer/activity-collisions.md#concept_0BC6B929592744DFA7DA01FF4F91052E)を確認してください。

**[!UICONTROL Target] の意思決定機能を使用して、単一ページアプリケーション（SPA）またはサーバーサイド統合で使用できるエクスペリエンス/オファーを受け取ることはできますか？**

その場合は、[フォームベースのアクティビティ](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)と [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D)を利用することで対処できます。

## レポート（Analytics for Target - A4T を含む） {#section_8AECC69BEEB7422E894E7EC44A50BA0A}

**また、[!DNL Adobe Analytics] もあり、[!DNL Target] で活用したいと思っています。 この 2 つを統合することで、主にどのような機能を利用できるようになりますか？**

以下の製品情報を参照してください。

* [Analytics for Target（A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)

* [顧客属性](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html?lang=ja)

* [オーディエンス](/help/main/c-integrating-target-with-mac/mmp.md)


**複数のユーザーセグメントを対象に、レポートのデータを多角的に分析することはできますか？**

その場合は、3 ステップのガイドによるアクティビティワークフローのステップ 3 の目標と設定ページで利用できる[レポート対象のオーディエンス機能](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_13119392051044FBA6387D9B3B1C43CF)が最適です。

このようなセグメントを 50 個追加するオプションと、アプリケーションポイント（[!UICONTROL Activity Entry] または特定の指標）を追加して、強力な方法で多角的に分析できます。

この場合 Target では、対象のオーディエンスを追加した時点からデータを収集します。そのため、テストの実施前にセグメントを追加していなかった場合は、このような分析はおこなえません。

**アクティビティの実行前にオーディエンスを定義できません。Target アクティビティのレポート用オーディエンスは、この点が不便だと思います。**

**このプロセスを簡略化するには、どうすればよいですか？**

そのためにあるのが [Analytics for Target（A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)です。[!DNL Adobe Analytics] がある場合は、ソースを [!DNL Analytics] として選択するだけで、この制限がなくなります。 あらゆる時点、あらゆるオーディエンスを対象に分析を実行できるようになり、事前にレポート用オーディエンスを定義する必要もなくなります。

**オフラインでレポートの計算を実行することはできますか？**

Rep[orts ページの ](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md)Export Reports to CSV および Download Order Details to CSV オプションを使用して、目的のレポートデータをダウンロードします。

**レポート評価のコントロールエクスペリエンスを変更したり、カウント方法を [!UICONTROL Visitors] から [!UICONTROL Visits] に変更したりできますか？**

[ レポートページの設定歯車](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)を使用してこれらの変更をおこないます。これらの設定で、計算方法がどう変わるかについて確認してください。

**レポートのデータの見方を教えてください。**

[ 信頼区間バー、上昇率範囲、有意性/信頼性および複数の指標の選択、テーブルおよびグラフ表示、実行中の平均など ](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) の機能を使用して、強力で簡単なレポート分析を可能にするために、レポートをできるだけ直感的にするように努めました。 また、[Analytics for Target（A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)アクティビティを使用している場合、Analytics を参照してさらに詳細な分析をオーディエンスに掛けられます。

## レスポンストークン {#section_C2A7118B4B62482A9D630C2212112A3D}

**[!DNL Google Analytics] や [!DNL ClickTal]e などのサードパーティシステムと統合して、エンドユーザーに配信したアクティビティ情報を分析に渡すことはできますか？**

これに関しては、[レスポンストークン](/help/main/administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4)機能を使用してください。

## トラブルシューティング {#section_6B8B4DC62AE34066A8C55915E9EC6C19}

**[!DNL Target] の可用性ステータスを知るにはどうすればよいですか？**

[Adobeのシステムステータス ページ ](/help/main/r-release-notes/system-status-updates.md#concept_5CBDF506BEFA40E483CC7DE0DA915EAD) を使用して、[!DNL Adobe] 製品のステータスと [!DNL Experience Cloud] を含む [!DNL Target] ソリューションのステータスを表示します。 このページは、発生した問題がシステムの更新によるものか、または日常のメンテナンスによるものかを判断するのに役立ちます。

**トラブルシューティング用のガイドはありますか？**

ご迷惑をおかけして大変申し訳ありません。多くのトラブルシューティングトピックへのリンクについては、[Troubleshooting Target](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) を参照してください。

## [!DNL Target] API {#section_714E85EFF6E3400389EF2E40D538E1DA}

**Target API の詳細はどこで確認できますか？**

API に関する詳細なドキュメントを用意してあります。「[Delivery API、NodeJS SDK、および Recommendations API のドキュメント](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html?lang=ja){target=_blank}」を参照してください。
