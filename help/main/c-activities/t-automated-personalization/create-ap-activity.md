---
keywords: 自動パーソナライゼーション；ap
description: 以下を作成する方法を説明します。 [!UICONTROL Automated Personalization] (AP) でのアクティビティ [!DNL Adobe Target] の使用 [!UICONTROL Visual Experience Composer].
title: 作成方法 [!UICONTROL Automated Personalization] 活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '1884'
ht-degree: 43%

---

# [!UICONTROL Automated Personalization] アクティビティの作成

の作成 [!UICONTROL Automated Personalization] (AP) でのアクティビティ [!DNL Adobe Target] の使用 [!UICONTROL Visual Experience Composer] (VEC) を参照してください。

The [!UICONTROL Automated Personalization] (AP) でのアクティビティワークフロー [!DNL Target] は、他のアクティビティタイプのワークフローとは異なります。

1. 次から： [!DNL Target] [!UICONTROL アクティビティ] リスト、クリック **[!UICONTROL アクティビティを作成]** > **[!UICONTROL Automated Personalization]**.

   ![アクティビティを作成：Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. 次の手順で [!UICONTROL Visual Experience Composer] (VEC)、 **[!UICONTROL ビジュアル]**.

   次の手順で [!UICONTROL フォームベースの Experience Composer]を選択します。 [!UICONTROL フォーム]. 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC および [!UICONTROL フォームベースの Experience Composer], [!DNL Target] は、 [!UICONTROL シングルページアプリケーション VEC]. 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VEC のトラブルシューティングについて詳しくは、 [Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. （条件付き） [ワークスペースを選択](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. アクティビティ URL を確認または入力して、「 **[!UICONTROL 作成]**.

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] および [!DNL http]）を区別しません。その結果、[!DNL `http://www.adobe.com`] と [!DNL `https://wwww.adobe.com`] の両方が一致します。

   指定した URL のページが VEC で開きます。

1. 次をクリック： **[!UICONTROL 名前]** 「 」フィールドにアクティビティ名を入力します。

   ![「名前」フィールド](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

   アクティビティ名の先頭に次の文字を使用することはできません。

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名に次の文字シーケンスを含めることはできません。

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン、マイナス |
   | ;@ | セミコロン、アットマーク |
   | ,= | コンマ、等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ、マイナス |
   | ,@ | コンマ、アットマーク |
   | `[`&quot; | 開き角括弧、二重引用符 |
   | &quot;`]` | 二重引用符、閉じ角括弧 |

1. 「[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)」で説明しているとおりにページ要素を変更します。

   アセットマネージャーから一度に複数の画像を選択できます。これにより、各画像がアクティビティ用に設定されたページをすばやく表示できます。 また、オファー内のテキスト要素を容易に編集することもできます。要素を編集すると、その要素が変更されたことを示すバーが要素上に表示されます。

1. 「**[!UICONTROL コンテンツを管理]**」をクリックして、使用可能な組み合わせを設定します。

   ![「コンテンツを管理」オプション](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   画面上部に 3 つのオプションが表示されるダイアログボックスが表示されます。 [!UICONTROL エクスペリエンス], [!UICONTROL オファー]、および [!UICONTROL 除外グループ].

   ![コンテンツを管理ダイアログボックス](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >AP アクティビティではエクスペリエンスを 30,000 個まで作成できますが、エクスペリエンスが 5,000 個未満の場合にアクティビティは最高のパフォーマンスを発揮します。この制限は、アクティビティで [!UICONTROL 重複を許可しない] オプション。

   The [!UICONTROL エクスペリエンス] リストには、アクティビティ用に選択されたコンテンツの各部分と、それが割り当てられている場所が表示されます。

   特定のエクスペリエンスを除外するには、対象のエクスペリエンスにマウスポインターを置いてから [!UICONTROL 除外] アイコン。

   ![除外アイコンにマウスポインターを置く](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   複数のエクスペリエンスのチェックボックスをオンにしてから「 [!UICONTROL 除外] アイコンをクリックします。

   ![一括除外オプション](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   このリスト表示では、[!UICONTROL ステータス]ドロップダウンリストをクリックすることでフィルターを適用し、除外済みのアクティビティまたは追加済みのアクティビティのみを表示できます。

1. （条件付き）「**[!UICONTROL オファー]**」をクリックして、コンテンツを選択してレポートグループに割り当てたり、ターゲット設定によって特定のオファーの閲覧を特定の訪問者のみに許可したりします。

   レポートグループについて詳しくは、 [Automated Personalizationのオファーレポートグループ](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. （条件付き）クリック **[!UICONTROL 除外グループ]** ：アクティビティから除外する要素の組み合わせを選択します。

   ![コンテンツを管理ダイアログボックスの「除外グループ」タブ](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   AP テストでは 30,000 個までエクスペリエンスを作成できますが、アルゴリズムが最高のパフォーマンスを発揮するのはエクスペリエンスが 10,000 個未満の場合です。この制限は、アクティビティで [!UICONTROL 重複を許可しない] オプション。

   アクティビティでまだ除外グループを使用していない場合は、「**除外グループを作成**」をクリックします。リストにフィルターを適用し、除外する組み合わせのみを表示できます。除外グループに名前を付けて、「 **保存**.

   既存の除外グループを編集するには、編集するグループにマウスポインターを置いてから鉛筆アイコンをクリックします。

1. アクティビティのコンテンツの設定が終了したら、「**[!UICONTROL 完了]**」をクリックします。

1. The **ターゲット設定** 他の [!DNL Target] アクティビティのタイプ。 ここでは、オーディエンスを選択し、 **[!UICONTROL カスタム配分]** ドロップダウンリストから、 **次へ**.

   [!UICONTROL カスタム配分]ドロップダウンリストで、以下のオプションを選択できます。

   ![トラフィック配分目標ドロップダウンリスト](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL パーソナライゼーションアルゴリズムの評価(50/50)]:** 目標がアルゴリズムをテストする場合は、コントロールとターゲットアルゴリズムの間で訪問者の50/50%の分割を使用します。 この配分により、上昇率を最も正確に推定できます。「ランダムエクスペリエンス」をコントロールとして使用する場合にお勧めします。
   * **[!UICONTROL パーソナライゼーショントラフィックの最大化(90/10)]:** 「常時稼動」アクティビティを作成することを目標としている場合は、訪問者の 10%をコントロールに配置します。 このオプションを使用すると、時間の経過と共に学習を続行するのに十分なデータをアルゴリズムに保持できます。 ここでのトレードオフは、トラフィックの大部分をパーソナライズする代わりに、正確な上昇率の精度が低下するということです。 目標に関係なく、このオプションは、特定のエクスペリエンスをコントロールとして使用する場合の推奨トラフィック分割です。
   * **[!UICONTROL カスタム配分]:** 必要に応じて、割合を手動で分割します。

1. （条件付き）[!UICONTROL コントロール]ドロップダウンリストから、[コントロールとして使用する特定のエクスペリエンスを選択](/help/main/c-activities/t-automated-personalization/experience-as-control.md)するか、[!UICONTROL ランダムエクスペリエンス]を選択します。

   コントロールエクスペリエンスは、自動テストによってどれだけの上昇率を実現するかを判断するための比較となります。

   [!UICONTROL Automated Personalizationは、常にコントロールグループに基づいてパフォーマンスを測定します。]少なくとも訪問者の 10％はコントロールグループに配分することをお勧めします。目標が、提供されたデータに対するパーソナライゼーションアルゴリズムのパーソナライゼーション（ランダムに提供されるコントロールなど）が無い場合に50/50%のトラフィック分割でこの目標を達成できます。 パーソナライズされるトラフィックの量を最大化し、アクティビティが生成する正確な上昇率を把握することにあまり関心がない場合は、コントロールとパーソナライゼーションアルゴリズムの間で10/90%のトラフィック分割が、この目標を達成する最も迅速かつ正確な方法です。

   >[!NOTE]
   >
   >In [!UICONTROL Automated Personalization] アクティビティ、エントリ条件（URL ターゲット設定、テンプレートルール、オーディエンスターゲット）は、リクエストごとに評価されます。 以前のバージョンでは、エントリ条件はセッションごとに 1 度評価されていました。

1. 「**[!UICONTROL 次へ]**」をクリックして、**[!UICONTROL 目標と設定]**&#x200B;ページを表示します。
1. 次の設定を使用してアクティビティを構成し、「**[!UICONTROL 保存して閉じる]**」をクリックします。

   | 設定 | 説明 |
   |--- |--- |
   | [!UICONTROL 名前] | アクティビティの名前を設定します。チームメンバーが [!UICONTROL アクティビティ] リスト。 上記の表を参照して、アクティビティ名で許可されていない文字を確認してください。 |
   | [!UICONTROL 目的] | （オプション）テストの目的を入力します。目的を設定しておくと、アクティビティの用途を覚えやすくなります。 |
   | [!UICONTROL 優先度] | 設定に応じて、 [!DNL Target] の UI とオプション [!UICONTROL 優先度] 変化する。 従来の設定の [!UICONTROL 低], [!UICONTROL 中]または [!UICONTROL 高]または、0 ～ 999 の詳細な優先度を有効にすることもできます。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>このオプションが [!UICONTROL 管理] > [!UICONTROL レポート] （デフォルト）次の優先度を指定します。 [!UICONTROL 低], [!UICONTROL 中]または [!UICONTROL 高].<P>優先度の詳細設定を有効にするには、 [!UICONTROL 管理] > [!UICONTROL レポート]、次に [!UICONTROL 詳細な優先度の有効化] オプションを「オン」位置に設定します。<P>このオプションを有効にした場合は、0 ～ 999 の値を指定します。<ul><li>0 = 低</li><li>999 = 高</li></ul>以前のバージョンので作成されたアクティビティの場合 [!DNL Target Standard/Premium], [!UICONTROL 低] 優先度は 0 に変換され、 [!UICONTROL 中] 優先度は 5 に変換され、 [!UICONTROL 高] 優先度が 10 に変換されます。 これらの値は必要に応じて調整できます。<P>**注意**： 優先度の詳細設定を使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。 |
   | [!UICONTROL 期間] | アクティビティの開始日と終了日を設定します。次の項目を選択できます。 [!UICONTROL 有効化時] または、特定の日時を指定できます。 |
   | [!UICONTROL 最適化目標] | 以下の 2 つのパラメーターを使用して最適化目標を指定します。<ul><li>このアクティビティで測定するもの</li><li>その目標が達成されたことを示すアクティビティ参加者によって取られるアクション。</li></ul>右側の 3 つのドットを選択し、最適化目標に名前を付けることができます。 [!UICONTROL マイプライマリ目標]. [!UICONTROL Automated Personalization] アクティビティを測定可能 [!UICONTROL コンバージョン] または [!UICONTROL 売上高]. コンバージョンは、ページを表示するか、mbox を表示することで達成できます。 クリックを追跡することもできます。<P>また、主な目標は、モデリングシステムがエクスペリエンスの成功を計算するために使用するモデリング指標になります。<P>モデリングの目標に達した後も、訪問者をアクティビティ内にとどめて、追跡の対象とすることができます。例えば、多くの場合、 [!UICONTROL Automated Personalization] アクティビティを使用してクリック率を向上させます。これはモデリングの目標として設定されます。 しかし、クリック率の向上が最終的にどのようにコンバージョンにつながっているかを確認することが重要なので、最終的なコンバージョンまで追跡することが欠かせません。<P>複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。<P>成功指標の依存関係を設定する前に、両方（または複数）の成功指標を定義する必要があります。<P>「[!UICONTROL 依存関係を追加]」オプションを利用すると、ある成功指標に到達した場合、または到達しなかった場合に別の成功指標を増分するよう設定できます。<P>依存関係を追加する手順は次のとおりです。<ol><li>指標を追加したら、 **[!UICONTROL 詳細設定]** 右の三点メニューの下で [!UICONTROL 追加の目標].</li><li>「[!UICONTROL レポート設定]」セクションの下部にある「**[!UICONTROL 依存関係を追加]**」オプションをクリックします。</li><li>目的の指標を左側のパネルから右側のパネルにドラッグ＆ドロップしてから、「[!UICONTROL 到達]」をクリックし、「[!UICONTROL 到達]」と「[!UICONTROL 未到達]」を切り替えて設定します。 </li></ol>追加した依存関係は後で編集または削除できます。 |
   | [!UICONTROL コンバージョン指標] | デフォルトでは、コンバージョン指標は最適化目標指標と同じです。 ただし、「[!UICONTROL 最適化目標と同じ]」オプションをオフにすれば、個別のコンバージョン指標を定義できます。 |
   | [!UICONTROL 追加の指標] | 使用する他のレポート指標を追加します。 コンバージョンまたは売上高指標を追加できます。<P>**注意**: [!UICONTROL エンゲージメント] 指標は、追加の指標としてサポートされていません。 The [!DNL Target] UI で [!UICONTROL エンゲージメント] 指標を使用するが、レポートに正確にデータが表示されない。 |
   | [!UICONTROL レポート対象のオーディエンス] | オーディエンスを追加して、レポートでオーディエンスによるフィルタリングを可能にします。デフォルトでは、レポートにすべての認定訪問者の結果が表示されます。オーディエンスを追加して結果をフィルタリングすると、訪問者をさらに絞り込むことができます。<P>**注意**：他のアクティビティタイプとは異なり、 [!UICONTROL Automated Personalization] 使用できません [!UICONTROL Adobe Analytics] を作成します (A4T)。 |
   | [!UICONTROL メモ] | 自分や他のチームメンバーに役立つ、アクティビティに関する情報を入力します。 The [!UICONTROL メモ] ウィンドウはサイズ変更可能です。 |

   指標に名前を付けたり、名前を変更したりする場合、次の文字は使用できません。

   | 文字 | 説明 |
   |--- |--- |
   | / | フォワードスラッシュ |
   | ? | 疑問符 |
   | # | 番号記号 |
   | : | コロン |
   | = | イコール |
   | + | プラス |
   | - | マイナス |
   | @ | アットマーク |

次をクリックした後： **[!UICONTROL 保存して閉じる]**、アクティビティの [!UICONTROL 概要] ページが表示されます。 クリック **エクスペリエンスをプレビュー** を使用して、エクスペリエンスが提供されたときの外観をプレビューできます。 ポップアップが表示されます。このポップアップを使用して、サイト上の AP エクスペリエンスへのリンクを表示および共有して、 [!UICONTROL Target] [!UICONTROL Visual Experience Composer] (VEC) を参照してください。 プレビューを共有するには、メッセージに表示されたリンクを共有する必要があります。リンクをクリックしてブラウザーから直接 URL をコピーしても、機能しません。 リンクをコピーすると、URL には、メッセージ内のリンクからページにアクセスした場合にのみページを正しく表示するパラメーターが含まれます。

詳しくは、「[Automated Personalizationレポート](/help/main/c-reports/personalization-reports/reports-ap.md)」を参照してください。
