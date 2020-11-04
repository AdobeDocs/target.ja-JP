---
keywords: Target Standard;faq;frequently asked questions;cheat sheet;cheatsheet
description: Adobe Target の機能の使用方法に関するよくある質問のリストです。補足情報や詳細情報のリンクも紹介します。
title: Target の最適化とパーソナライゼーションに関する FAQ
feature: intro
topic: Advanced
uuid: b6052939-6ed4-4c90-b118-77b6fe42b0af
translation-type: tm+mt
source-git-commit: 55ee85188ec80a4dcc7dbb39cd0ce24f829ea331
workflow-type: tm+mt
source-wordcount: '2903'
ht-degree: 98%

---


# Target の最適化とパーソナライゼーションに関する FAQ{#target-optimization-and-personalization-faq}

Adobe Target の機能の使用方法に関するよくある質問のリストです。補足情報や詳細情報のリンクも紹介します。

## 一般情報 {#section_CE5713B5AAC341C9A75586C107797FA3}

**他の利用者が Adobe Target をどのように有効活用しているのかを知ることはできますか？**

お客様の成功事例については、[こちら](https://www.adobe.com/in/marketing-cloud/target/resources.html#x)でいくつか紹介しています。他のお客様がどのように Target を利用して最適化やパーソナライゼーションを強化し、ビジネス目標を達成しているのかを確認できます。

これらの顧客事例の一部では、Adobe Target Premium の機能を使用しているのでご注意ください。

**Target の最新機能の詳細はどこで確認できますか？**

最新リリースの詳細については、「[リリースノート](../r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A)」を参照してください。「[過去のリリース](../r-release-notes/release-notes-for-previous-releases.md)」すべての情報もオンラインで確認できます。

**Target に関する疑問の答えや詳細を確認できるアドビのコミュニティやフォーラムはありますか？**

[ Target コミュニティフォーラム](../cmp-resources-and-contact-information.md#concept_9C203A8AED054DFFA9A504811DB6BA42)をご覧ください。このフォーラムでは、アドビによるサポートも受けられますが、Adobe Target をご利用しているお客様同士が助け合うよう奨励しています。コミュニティやフォーラムの成功は、メンバーが活発に参加するかどうかで決まります。コミュニティの一員になり、他の利用者の疑問に答えたり、ご自分の疑問の答えを探したりしてください。

**Target はどのブラウザーをサポートしていますか？**

詳細については、「[サポートされているブラウザー](../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)」のマトリックスを参照してください。Target Standard／Premium Experience Cloud インターフェイスのサポートと、エンドユーザーのデスクトップ／デバイスでのブラウザーサポートの 2 種類があるのでご注意ください。

## Target JavaScript ライブラリ（at.js および mbox.js） {#section_C2AC78DFDAD84981A8C84DF20893E340}

**実装用の JavaScript ファイルは、at.js と mbox.js のどちらを使用すればよいですか？**

at.js は最も機能性に優れた最新の JavaScript ライブラリです。mbox.js は旧バージョンです。[at.js のメリット](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits)を参照して、この 2 つのライブラリの違いを把握してください。新規のお客様は、at.js を使用してください。

at.js をご利用の既存のお客様も、at.js に移行する必要があります。移行に取りかかる前に、[mbox.js から at.js への移行](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)手順を参照してください。

## アクティビティ {#section_CB95B3BF9934445DB98E8A7E22FC2CF6}

**統計的有意性に優れた手法で、コントロールエクスペリエンスを使用しながら勝者と敗者のエクスペリエンスを見極めることはできますか？**

[A/B テスト](../c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)（手動ターゲット設定オプション）と[サンプルサイズ計算ツール](../c-activities/t-test-ab/sample-size-determination.md#section_286EB6E671184239BB1552F0387DAEB5)の使用が最適です。

**アクティビティはいつまで実行する必要がありますか？**

データが不十分な段階でアクティビティを停止してしまうと、間違った結論が導かれる恐れがあります。[よくあるミスと、それを回避する方法](../c-activities/t-test-ab/common-ab-testing-pitfalls.md#section_DF01A97275E44CA5859D825E0DE2F49F)を確認してください。また、「[A/B テストを実行すべき期間はどのくらいですか？](/help/c-activities/t-test-ab/sample-size-determination.md)」も参照してください。

**期間が短い場合は、アクティビティをどのように実行すればよいですか？**

**テストを実施して目標に合わせた最適化をおこなうことはできますか？**

[レポートを参照して勝者のエクスペリエンスを見極めてください。](../c-activities/automated-traffic-allocation/determine-winner.md#concept_5741A89ED7224E1285A3BC34B2CCD0F9)

**一定のレベルのパーソナライゼーションを中核に据えてアクティビティを実行することはできますか？**

「 [自動ターゲット](/help/c-activities/auto-target-to-optimize.md) 」オプションをチェックアウトします。

**ニーズに合ったアクティビティのタイプを見極めるには、どうすればよいですか？**

詳細については、「[Target アクティビティのタイプ](../c-activities/target-activities-guide.md#concept_D974B0918EB74B3B8CB07ACD32BF37A1)」を参照してください。Adobe Target の各オプションがどのようなシナリオに適しているのかについて解説しています。

また、[Recommendations アクティビティ](../c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)も検討してください。

**効果が高いページ要素の組み合わせを把握したり、各要素がどの程度の効果を発揮しているのかを確認したりするためには、どうすればよいですか？**

お客様のニーズに対応できる可能性があるため、[全因子多変量分析（MVT）アクティビティ](../c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)と要素の貢献度分析を確認してください。

ただし、MVT アクティビティではトラフィック要件は厳しくなります。

**構成が異なる複数のページにまたがるアクティビティを実行できますか？**

**複数の場所（チェックアウトプロセスの各ページなど）でオファーを適用できますか？**

エクスペリエンス内で複数ページを使用できる[複数ページアクティビティ機能](../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48)をお試しださい。

**目標（プライマリまたはセカンダリ）の達成後はユーザーに再度そのアクティビティを表示することはせず、別のアクティビティを表示するようにするには、どうすればよいですか？**

あらゆる目標で利用できる「[詳細設定](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_E2FE441AFB324E498793ABB025ED9974)」オプションを使用すれば、簡単に実現できます。各オプションを利用し、ユーザーが目標に達した後の処理方法や、カウントを増分する方法を指定できます。

このケースでは、「カウントを増分、ユーザーをリリース、再入場を許可しない」と「デフォルト / 他のアクティビティのコンテンツ」を選択することで対処できます。他のオプションもチェックしてみてください。

**アクティビティで複数の目標を作成しました。レポートや分析のために、ファネルとして一連の目標の流れを作成することはできますか？**

**例えば、特定のファネルの数値を追跡するために、ユーザーが目標 A を達成した後に目標 B を追跡したいと考えています。**

Target の指標依存関係の機能を利用すれば可能です。[他の成功指標の依存関係](../c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B)を追加するだけです。「到達」、「未到達」などのオプションを利用したり、様々な方法で指標を結合し、あらゆる組み合わせを作成したりできます。

**目標達成のためにアクティビティを適切に設定するには、どうすればよいですか？**

そのためにあるのが[目標](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)です。

まず、何を重視して最適化をおこなうかを把握します。売上高、コンバージョン、エンゲージメントなどが考えられます。これらの各オプションは目標のセクションで利用できます。それぞれのオプションで、目標達成の条件と見なすサイトでのユーザー行動を定義できます。

この設定は、プライマリ目標設定（3 ステップのガイドによるワークフローのステップ 3）で指定できます。他の目標を追加し、レポートのデータの質を高めることもできます。

**スケジュールを設定し、特定の日時にアクティビティを開始して終了させることはできますか？**

3 ステップのガイドによるワークフローの[目標と設定ステップのスケジュール設定機能](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC)で、開始日時と終了日時を指定できます。

忘れずにアクティビティを有効にしてください。指定したスケジュールが適用されるのは、ライブアクティビティのみです。終了日に達したら、そのアクティビティのステータスは終了になります。

**3 ステップのガイドによるワークフロー全体ではなく、ターゲット設定のステップのみに変更を加えることはできますか？**

[アクティビティの概要ページから直接対象の手順に移動し、](../c-activities/edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0)「保存して閉じる」オプションを使用してその手順を終了します。

**特定のステップに留まってアクティビティ（オファーのテキストやカスタムコードなど）を編集しながら、別のタブで QA を実行することはできますか？**

これも可能です。その際は、[「保存」オプションを使用することで、特定のステップに留まったまま段階的に変更を加えることができます](../c-activities/edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0)。

**作成したばかりのアクティビティのプレビューを確認し、QA を実行するにはどうすればよいですか？**

[強力な QA モード機能](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40)を利用して、QA を実行できます。QA チームでリンクを共有して、レポートを含めたエンドツーエンドのアクティビティ QA を実行することもできます。これにより、アクティビティをライブにした後、テストでの想定どおりに進めることができます。

**Target の判定機能を利用し、シングルページアプリケーション（SPA）またはサーバー側の統合で使用できるエクスペリエンスやオファーを受け取るには、どうすればよいですか？**

その場合は、[フォームベースのアクティビティ](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)と [JSON オファー](../c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D)を利用することで対処できます。

**2 つのアクティビティを設定しました。訪問者にどちらが表示されるのかを把握するには、どうすればよいですか？**

**アクティビティに優先順位を設定することはできますか？**

Target の 3 ステップのガイドによるワークフローのステップ 3 で、優先度設定を使用して[アクティビティの優先度を設定](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC)できます。

2 つのオプションがあります。

* デフォルトは 3 つのレベル（低／中／高）
* カスタムは 0 ～ 999 の範囲。カスタムの場合は、詳細な優先度機能を有効にします（管理/Visual Experience Composer）。

## オーディエンス{#section_FA6314777ABC46D8B198D6F388051460}

**特定のアクティビティ専用のオーディエンスセグメントを作成できますか？オーディエンスライブラリには再利用の要素がないので、そのようなオーディエンスは作成できないように見えます。**

特定のアクティビティ専用のオーディエンスを定義するには、[アクティビティのみのオーディエンス機能](../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)を利用してください。

**場所を基準にユーザーをターゲットに設定するには、どうすればよいですか？**

その場合、[地理オーディエンス](../c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670)を利用します。この機能の精度のレベルを確認してください。

**セッション内で、ページ上の属性を基準にユーザーをターゲットに設定することはできますか？**

mbox と[カスタムオーディエンス](../c-target/c-audiences/c-target-rules/custom-parameters.md#concept_C4C6E00D7C5A4BE9B72D471DB2E3027B)を併用して適切なエクスペリエンスを提供する方法が最適です。

**複数の訪問にまたがり、訪問者属性を基にしてエクスペリエンスを提供することはできますか？**

**2 つのグループにランダムでトラフィックを分割することはできますか？**

その場合、[プロファイルスクリプト機能](../c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)を利用してください。コードを記述する必要がありますが、効果的にエクスペリエンスをパーソナライズできます。

**訪問者数が比較的少ない場合でも、アクティビティを開始できますか？**

その場合は、[Target の 3 ステップのガイドによるワークフローのステップ 2（ターゲット設定ページ）](../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087)で、割合による配分調整を使用して、アクティビティの設定方法を指定できます。

**Adobe Analytics も利用しているのですが、Target と連携させて活用することはできますか？この 2 つを統合することで、主にどのような機能を利用できるようになりますか？**

以下の製品情報を参照してください。

* [Analytics for Target（A4T）](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)
* [顧客属性](../c-target/c-visitor-profile/working-with-customer-attributes.md#concept_16C5C434D32D4EB1AD44A71821F3DEE8)
* [オーディエンス](../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)

## エクスペリエンス {#section_5959536B8D6A4BEA8FAA1273338F3451}

**構成が共通する複数のページにまたがるアクティビティを実行できますか？**

その場合、[テンプレートルール](../c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781)を利用して、指定された単一の URL のエクスペリエンスを作成し続けながら、構成が共通する多数のページをアクティビティに追加します。

**Visual Experience Composer（VEC）でページを読み込もうとすると、「ブラウザーでスクリプトをロードできるようにします」というメッセージが表示されます。どうすればこの問題を解消できますか？**

これは、お客様のサイトに、HTTP と HTTPS リソースの両方を取得する混合コンテンツがあることが原因です。IT チームに、HTTPS への完全移行をおこなうよう要求してください。

移行が完了するまでは、「[ブラウザーでの混在するコンテンツの有効化](../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md#concept_46D022D50280468C9EF6D5DF6EFC911C)」の手順に従い、ブラウザーに混合するコンテンツの読み込みを許可してください。これは最新のブラウザーのセキュリティ機能です。

**Target at.js ライブラリが実装されていなくても、サイトで Visual Experience Composer（VEC）を使用できますか？**

[拡張 Experience Composer](../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) でページを読み込んでみてください。

**Visual Experience Composer（VEC）内でサイトが読み込まれないのはなぜですか？**

ヘルプページの「[トラブルシューティング情報](../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4)」を参照してください。記載されている方法で問題を解消できなかった場合、[アドビサポート](../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)までお問い合わせください。

また、「[フォームベースの手法](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)」でブロックを解除できます。

[拡張 Experience Composer](../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) が役に立つケースと、そのメリットも確認してください。IT 部門に連絡し、 [allowlist Adobe&#39;s proxy servers](../c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6) as well.

**レスポンシブサイトを運営しています。アクティビティの作成中に重要なデバイスでの表示を確認するには、どうすればよいですか？**

その場合、[モバイルビューポート](../c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5)機能を利用します。この機能は、拡張 Experience Composer が有効になっている場合のみ利用できます。

**複数のドメインがあります。拡張 Experience Composer を有効にする必要があるドメインと、無効にする必要があるドメインがあるのですが、これはどうすれば設定できますか？**

You can always use [Enhanced Experience Composer option at the activity level](../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) to override the default setting ( Administration > Visual Experience Composer).

**画像を入れ替えるオプションが表示されないのはなぜですか？**

アドビまでお問い合わせいただけば、[お客様のアカウントで Scene7 を有効にします](../administrating-target/scene7-settings.md#task_37AD0768EFBA4E588955FE3D5DD670A5)。プロビジョニングが終わったら、簡単に別の画像と入れ替えられるようになります。

**一律割引とパーセンテージ割引など、2 種類のエクスペリエンスをテストしたいのですが、エクスペリエンスのターゲットを適切に設定する必要があります（違う国のユーザーには違うロケールのテキストや通貨を表示するなど）。これはどうすれば設定できますか？**

その場合、[複数のエクスペリエンスバージョン機能](../c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md#task_0138112E283A4A5B9F8AB9AAF2FBC2FF)を使用すると簡単に設定できます。この種のテストでは、提供時の微妙な違いにご注意ください。

**Visual Experience Composer（VEC）での変更内容を確認するには、どうすればよいですか？**

変更内容は、「[コードエディター](../c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5)」に常に表示されます。「変更」タブには、オファーに適用した CSS セレクターまたは mbox が表示されます。

CSS セレクターは Sizzle セレクターです。このセクションで、手早く小さな変更を加えたり特定のオファーを削除したりできます。

**実験／アクティビティの一部として JavaScript を配信し、動的要素に即座に変更を加えたり、サードパーティソリューションに呼び出しを送信したりしたいと考えています。これはどうすれば設定できますか？**

それを行う方法の 1 つは、[カスタムコードエディター](../c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5)の利用です。該当の JavaScript をセクションに設置すると配信されます。必要に応じて、head 内や body 最上部で配信することもできます。

**Visual Experience Composer（VEC）内でログインページ以降に進めなかったり、特定の URL がない深部に埋め込まれたページに移動したりできないのはなぜですか？**

構成および参照の機能を使用すれば、目的のページに移動してエクスペリエンスを作成できます。

![](assets/vec2.png)

**Target の 3 ステップのガイドによるワークフローのステップ 2（ターゲット設定ページ）から、目的のエクスペリエンスに移動するにはどうすればよいですか？**

ステップ 2 でエクスペリエンス名の前にあるサムネールをクリックすれば、対象のエクスペリエンスに移動できます。

![](assets/thumbnail_experiences.png)

**以前まで Target Classic を利用していました。特定の用途で自分の mbox を利用することはできますか？**

「[フォームベースの手法](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)」でアクティビティを作成してください。

**ユーザーのあらゆるデバイス全体を対象に、一貫性のある同一のエクスペリエンスが提供されているかを確認することはできますか？**

[Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) では、Co-op の機能を利用し、確率論に基づいて確定的にユーザーの複数のデバイスをリンクさせることができます。

Co-op 対象地域のお客様であれば、目標と設定ページのシンプルなフラグでこの機能を有効にできます。レポートのデータも、訪問者ではなく人を基準とした形に変わります。この機能を利用できるのは一部の地域のみなので、詳しくはアドビの担当者までお問い合わせください。

**目的のオファーやエクスペリエンスが表示されず、別のアクティビティが表示されるのはなぜですか？**

[デバッガー](../c-activities/c-troubleshooting-activities/content-trouble.md#concept_D2548B486C984B1E97ED7A72075B8EEA)を利用し、[アクティビティの衝突](../c-experiences/c-visual-experience-composer/activity-collisions.md#concept_0BC6B929592744DFA7DA01FF4F91052E)を確認してください。

## オファー {#section_A547B1EAD0B34FD38D3B87AAF62E3963}

**小さな変更を加えるのではなく、まったく違う新しいページをテストしたいと考えています。**

**新発売などに合わせ、新しいランディングページにユーザーを誘導したいと考えています。**

**これはどうすれば設定できますか？**

[リダイレクト URL 機能](../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94)を使用すると、対象のページにユーザーを誘導できます（現在のクエリパラメーターの有無は問いません）。

**QA プロセスでコンテンツ配信がおこなわれないのはなぜですか？**

お客様のサイトの要素に動的 ID、重複する ID または動的クラスが含まれている可能性があります。アカウントレベル（問題の範囲が特定のドメインやページのみの場合はアクティビティレベル）でサイトの基本設定オプションをチェックすることをお勧めします。[CSS セクター](/help/administrating-target/visual-experience-composer-set-up.md#css)を参照してください。

**目的のオファーやエクスペリエンスが表示されず、別のアクティビティが表示されるのはなぜですか？**

[デバッガー](../c-activities/c-troubleshooting-activities/content-trouble.md#concept_D2548B486C984B1E97ED7A72075B8EEA)を利用し、[アクティビティの衝突](../c-experiences/c-visual-experience-composer/activity-collisions.md#concept_0BC6B929592744DFA7DA01FF4F91052E)を確認してください。

**Target の判定機能を利用し、シングルページアプリケーション（SPA）またはサーバー側の統合で使用できるエクスペリエンスやオファーを受け取ることはできますか？**

その場合は、[フォームベースのアクティビティ](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)と [JSON オファー](../c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D)を利用することで対処できます。

## レポート（Analytics for Target - A4T を含む）{#section_8AECC69BEEB7422E894E7EC44A50BA0A}

**Adobe Analytics も利用しているのですが、Target と連携させて活用することはできますか？この 2 つを統合することで、主にどのような機能を利用できるようになりますか？**

以下の製品情報を参照してください。

* [Analytics for Target（A4T）](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)

* [顧客属性](../c-target/c-visitor-profile/working-with-customer-attributes.md#concept_16C5C434D32D4EB1AD44A71821F3DEE8)

* [オーディエンス](../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)


**複数のユーザーセグメントを対象に、レポートのデータを多角的に分析することはできますか？**

その場合は、3 ステップのガイドによるアクティビティワークフローのステップ 3 の目標と設定ページで利用できる[レポート対象のオーディエンス機能](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_13119392051044FBA6387D9B3B1C43CF)が最適です。

対象のセグメントを 50 個追加したり、アプリケーションポイント（アクティビティのエントリまたは特定の指標）を追加したりして、データを多角的に分析できます。

この場合 Target では、対象のオーディエンスを追加した時点からデータを収集します。そのため、テストの実施前にセグメントを追加していなかった場合は、このような分析はおこなえません。

**アクティビティの実行前にオーディエンスを定義できません。Target アクティビティのレポート用オーディエンスは、この点が不便だと思います。**

**このプロセスを簡略化するには、どうすればよいですか？**

そのためにあるのが [Analytics for Target（A4T）](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)です。Adobe Analytics を利用している場合は、ソースとして Analytics を選択すればこの問題を解消できます。あらゆる時点、あらゆるオーディエンスを対象に分析を実行できるようになり、事前にレポート用オーディエンスを定義する必要もなくなります。

**オフラインでレポートの計算を実行することはできますか？**

[レポートを CSV にエクスポートするオプションと、注文の詳細を CSV にダウンロードするオプション](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75)を利用して、対象のレポートデータをダウンロードしてください。

**レポートを評価するためにコントロールエクスペリエンスを変更したり、カウント手法を訪問者から訪問に変更したりできますか？**

[ レポートページの設定歯車](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)を使用してこれらの変更をおこないます。これらの設定で、計算方法がどう変わるかについて確認してください。

**レポートのデータの見方を教えてください。**

レポートは、[信頼区間のバー、上昇率範囲、有意性／信頼度、複数の指標の選択、表、グラフ、実行期間の平均など](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA)の機能によって、できるだけ直感的に理解できる仕組みになっているので、効果的な分析を簡単におこなえます。また、[Analytics for Target（A4T）](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)アクティビティを使用している場合、Analytics を参照してさらに詳細な分析をオーディエンスに掛けられます。

## レスポンストークン {#section_C2A7118B4B62482A9D630C2212112A3D}

**Google Analytics や ClickTale などのサードパーティシステムとの統合をおこない、エンドユーザーに提供されたアクティビティの情報を渡して分析に生かすことはできますか？**

これに関しては、[レスポンストークン](../administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4)機能を使用してください。

## トラブルシューティング {#section_6B8B4DC62AE34066A8C55915E9EC6C19}

**Adobe Target の利用ステータスを把握するには、どうすればよいですか？**

[アドビシステムステータスページ](../r-release-notes/system-status-updates.md#concept_5CBDF506BEFA40E483CC7DE0DA915EAD)を使用して、アドビ製品および Target を含む Experience Cloud ソリューションのステータスを表示します。このページは、発生した問題がシステムの更新によるものか、または日常のメンテナンスによるものかを判断するのに役立ちます。

**トラブルシューティング用のガイドはありますか？**

ご迷惑をおかけして大変申し訳ありません。トラブルシューティングについては、トラブルシューティングに関する様々なトピックへのリンクについては、「[Target のトラブルシューティング](../r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839)」を参照してください。

## Target モバイルアプリ {#section_07BA89F2C38747158ECD5B153274AEAF}

**モバイル SKU を使用しています。モバイルアクティビティを作成できますか？**

モバイルによる最適化とパーソナライゼーションの場合、[フォームベースのアクティビティ](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)と [Adobe SDK](../c-target-mobile-app/mobile-enable-target-in-sdk.md#task_FCA99AD0785A44E995468776AE76FE91) を併用する必要があります。詳細については、「[モバイルアプリのための Target](../c-target-mobile-app/target-mobile-app.md#concept_80126FF457724DE788CE37264A047559)」を参照してください。

## Target API {#section_714E85EFF6E3400389EF2E40D538E1DA}

**Target API の詳細はどこで確認できますか？**

API に関する詳細なドキュメントを用意してあります。「[Delivery API、NodeJS SDK、および Recommendations API のドキュメント](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md)」を参照してください。