---
keywords: automated personalization;ap
description: '[!UICONTROL Visual Experience Composer] を使用して、で [!UICONTROL Automated Personalization] （AP）アクティビティを作成する方法  [!DNL Adobe Target]  説明します。'
title: '[!UICONTROL Automated Personalization] アクティビティの作成方法'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '1743'
ht-degree: 29%

---

# [!UICONTROL Automated Personalization] アクティビティの作成

[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Adobe Target] に [!UICONTROL Automated Personalization] （AP）アクティビティを作成します。

[!DNL Target] の [!UICONTROL Automated Personalization] （AP）アクティビティワークフローは、他のアクティビティタイプのワークフローとは異なります。

1. [!DNL Target] [!UICONTROL Activities] リストで、**[!UICONTROL Create Activity]**/**[!UICONTROL Automated Personalization]** をクリックします。

   ![アクティビティを作成：Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. [!UICONTROL Visual Experience Composer] （VEC）を使用するには、「**[!UICONTROL Visual]**」をクリックします。

   [!UICONTROL Form-Based Experience Composer] を使用するには、「[!UICONTROL Form]」を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC と [!UICONTROL Form-Based Experience Composer] に加えて、[!DNL Target] は [!UICONTROL Single Page Application VEC] を提供します。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md) を参照してください。

1. （条件付き） [ ワークスペースを選択 ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) します。

1. アクティビティ URL を確認または入力し、「**[!UICONTROL Create]**」をクリックします。

   >[!NOTE]
   >
   >[!DNL Target] は URL プロトコル（[!DNL https] と [!DNL http]）を区別しません。 その結果、[!DNL `http://www.adobe.com`] と [!DNL `https://wwww.adobe.com`] の両方が一致します。

   指定された URL のページが VEC で開きます。

1. 「**[!UICONTROL Name]**」フィールドをクリックし、アクティビティ名を入力します。

   ![「名前」フィールド](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

   アクティビティ名は、次の文字で始めることはできません：

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名には、次の文字シーケンスを含めることはできません：

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、次と等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン マイナス |
   | ;@ | セミコロン、アットサイン |
   | ,= | コンマ、次と等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ，マイナス |
   | ,@ | コンマ、アットサイン |
   | `[`&quot; | 左角括弧、二重引用符 |
   | &quot;`]` | 二重引用符、閉じ角括弧 |

1. 「[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)」で説明しているとおりにページ要素を変更します。

   アセットマネージャーから一度に複数の画像を選択できます。これにより、アクティビティ用に設定された各画像を含むページをすばやく表示できます。 また、オファー内のテキスト要素を容易に編集することもできます。要素を編集すると、その要素が変更されたことを示すバーが要素上に表示されます。

1. 「**[!UICONTROL Manage Content]**」をクリックして、使用可能な組み合わせを設定します。

   ![「コンテンツを管理」オプション](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   画面上部に、[!UICONTROL Experiences]、[!UICONTROL Offers]、[!UICONTROL Exclusion Groups] の 3 つのオプションがダイアログボックスに表示されます。

   ![コンテンツを管理ダイアログボックス](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >1 つの AP アクティビティで作成できるエクスペリエンスは最大 30,000 個ですが、このアクティビティのパフォーマンスが最も高いのは、使用されるエクスペリエンスが 5,000 件未満の場合です。 アクティビティで「[!UICONTROL Disalow Duplicates]」オプションが有効になっていても、この同じ制限が適用されます。

   [!UICONTROL Experiences] のリストには、アクティビティ用に選択された各コンテンツと、そのコンテンツが割り当てられている場所が表示されます。

   目的のエクスペリエンスにカーソルを合わせて「[!UICONTROL Exclude]」アイコンをクリックすると、特定のエクスペリエンスを除外できます。

   ![除外アイコンにマウスポインターを置く](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   エクスペリエンスをバッチで除外または含めるには、関連するエクスペリエンスのチェックボックスをオンにし、ダイアログボックスの右上隅にある「[!UICONTROL Exclude]」アイコンをクリックします。

   ![一括除外オプション](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   [!UICONTROL Status] のドロップダウンリストをクリックすると、このリスト表示をフィルタリングして、除外されたアクティビティのみを表示したり、含まれたアクティビティのみを表示したりできます。

1. （条件付き） **[!UICONTROL Offers]** をクリックしてコンテンツを選択し、レポートグループに割り当てるか、特定の訪問者にのみターゲティング付きの特定のオファーを表示させます。

   レポートグループについて詳しくは、「[Automated Personalizationのオファーレポートグループ ](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)」を参照してください。

1. （条件付き）「**[!UICONTROL Exclusion Groups]**」をクリックして、アクティビティから除外する要素の組み合わせを選択します。

   ![コンテンツを管理ダイアログボックスの「除外グループ」タブ](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   AP テストでは最大 30,000 個のエクスペリエンスを作成できますが、アルゴリズムが最高のパフォーマンスを発揮するのは、使用される個別のエクスペリエンスが 10,000 個未満の場合です。 アクティビティで「[!UICONTROL Disalow Duplicates]」オプションが有効になっていても、この同じ制限が適用されます。

   アクティビティでまだ除外グループを使用していない場合は、「**除外グループを作成**」をクリックします。リストにフィルターを適用し、除外する組み合わせのみを表示できます。除外グループに名前を付け、「**保存**」をクリックします。

   既存の除外グループを編集するには、編集するグループにマウスポインターを置いてから鉛筆アイコンをクリックします。

1. アクティビティのコンテンツの設定が完了したら、「**[!UICONTROL Done]**」をクリックします。

1. **ターゲティング** ステップは、他の [!DNL Target] アクティビティタイプを使用したことがある場合によく見られます。 ここでは、オーディエンスを選択し、**[!UICONTROL Custom Allocation]** ドロップダウンリストをクリックしてコントロールエクスペリエンスを表示する訪問者の割合を指定してから、「**次へ** をクリックできます。

   「[!UICONTROL Custom Allocation]」ドロップダウンリストを使用すると、次のオプションから選択できます。

   ![トラフィック配分目標ドロップダウンリスト](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL Evaluate Personalization Algorithm (50/50)]:** アルゴリズムをテストすることが目標の場合は、コントロールとターゲットアルゴリズムの間で訪問者を 50/50% 分割して使用します。 この配分により、上昇率を最も正確に推定できます。「ランダムエクスペリエンス」をコントロールとして使用する場合にお勧めします。
   * **[!UICONTROL Maximizing Personalization Traffic (90/10)]:** 「常時稼動」アクティビティを作成することを目標としている場合は、訪問者の 10% をコントロールに配置します。 このオプションにより、アルゴリズムが時間の経過と共に学習を継続するのに十分なデータが得られます。 ここでのトレードオフは、トラフィックの大部分をパーソナライズする代わりに、正確な上昇率が何であるかについての精度が低くなることです。 特定のエクスペリエンスをコントロールとして使用する場合、目標に関係なく、このオプションは推奨されるトラフィック分割です。
   * **[!UICONTROL Custom Allocation]:** 必要に応じて割合を手動で分割します。

1. （条件付き） [!UICONTROL Control] ドロップダウンリストから、[ コントロールとして使用する特定のエクスペリエンスを選択 ](/help/main/c-activities/t-automated-personalization/experience-as-control.md) または [!UICONTROL Random Experience.] を選択します

   コントロールエクスペリエンスは、自動テストによってどれだけの上昇率を実現するかを判断するための比較となります。

   [!UICONTROL Automated Personalization] は、常にコントロール母集団に対するパフォーマンスを測定します。 少なくとも訪問者の 10％はコントロールグループに配分することをお勧めします。与えられたデータに対するパーソナライゼーションアルゴリズムが、パーソナライゼーションをおこなわない場合（ランダムに提供されたコントロールなど）よりも高いパフォーマンスを発揮するかどうかをテストすることが目標の場合、コントロールとパーソナライゼーションアルゴリズムの間で 50/50% のトラフィックを分割するのが、この目標を達成するための最速かつ最も正確な方法です。 パーソナライズされるトラフィックの量を最大化し、アクティビティで発生する正確な上昇率についてそれほど関心がない場合は、コントロールとパーソナライゼーションアルゴリズムの間で 10/90% のトラフィック配分を行うことが、この目標を達成するための最も速く最も正確な方法です。

   >[!NOTE]
   >
   >[!UICONTROL Automated Personalization] のアクティビティでは、エントリ条件（URL ターゲティング、テンプレートルール、オーディエンスターゲット）がリクエストごとに評価されます。 以前のバージョンでは、エントリ条件はセッションごとに 1 度評価されていました。

1. 「**[!UICONTROL Next]**」をクリックすると、**[!UICONTROL Goals & Settings]** のページが表示されます。
1. 次の設定でアクティビティを設定し、「**[!UICONTROL Save & Close]**」をクリックします。

   | 設定 | 説明 |
   |--- |--- |
   | [!UICONTROL Name] | アクティビティの名前を設定します。アクティビティに、チームメンバーが [!UICONTROL Activities] ータリストでアクティビティを認識できるような、わかりやすい名前を付けます。 上記の表を参照して、アクティビティ名で許可されていない文字を確認してください。 |
   | [!UICONTROL Objective] | （オプション）テストの目的を入力します。目的を設定しておくと、アクティビティの用途を覚えやすくなります。 |
   | [!UICONTROL Priority] | の [!DNL Target] UI とオプションは、設定によっ [!UICONTROL Priority] 異なります。 従来の設定である [!UICONTROL Low]、[!UICONTROL Medium]、[!UICONTROL High] を使用するか、0～999 の細かい優先度を有効にすることができます。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>[!UICONTROL Administration] > [!UICONTROL Reporting] （デフォルト）でこのオプションが有効になっていない場合は、優先度を [!UICONTROL Low]、[!UICONTROL Medium]、[!UICONTROL High] のいずれかに指定します。<P>詳細な優先度を有効にするには、[!UICONTROL Administration]/[!UICONTROL Reporting] をクリックし、「[!UICONTROL Enable Fine-Grained Priorities]」オプションを「オン」の位置に切り替えます。<P>このオプションが有効な場合は、0～999 の値を指定します。<ul><li>0 = 低</li><li>999 = 高</li></ul>以前のバージョンの [!DNL Target Standard/Premium] で作成されたアクティビティの場合、[!UICONTROL Low] の優先度は 0 に変換され、[!UICONTROL Medium] の優先度は 5 に変換され、[!UICONTROL High] の優先度は 10 に変換されます。 これらの値は必要に応じて調整できます。<P>**注意**：詳細設定プライオリを使用した後でこのオプションを無効にするには、すべての優先度を 0、5、10 に戻す必要があります。 |
   | [!UICONTROL Duration] | アクティビティの開始日と終了日を設定します。 [!UICONTROL When Activated] を選択するか、特定の日時を指定できます。 |
   | [!UICONTROL Optimization Goal] | 以下の 2 つのパラメーターを使用して最適化目標を指定します。<ul><li>このアクティビティで測定するもの</li><li>その目標が達成されたことを示すアクティビティ参加者によって取られるアクション。</li></ul>[!UICONTROL My Primary Goal] の右側の 3 つのドットを選択して、最適化目標に名前を付けることができます。 アクティビティ [!UICONTROL Automated Personalization]、[!UICONTROL Conversion] または [!UICONTROL Revenue] を測定できます。 コンバージョンを実行するには、ページを表示するか、mbox を表示します。 クリックを追跡することもできます。<P>主な目標は、エクスペリエンスの成功を計算するためにモデリングシステムで使用されるモデリング指標にもなります。<P>モデリングの目標に達した後も、訪問者をアクティビティ内にとどめて、追跡の対象とすることができます。例えば、多くの場合、クリック率の向上を目的に、モデリング目標として [!UICONTROL Automated Personalization] アクティビティを設定します。 しかし、クリック率の向上が最終的にどのようにコンバージョンにつながっているかを確認することが重要なので、最終的なコンバージョンまで追跡することが欠かせません。<P>複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。<P>成功指標の依存関係を設定する前に、両方（または複数）の成功指標を定義する必要があります。<P>[!UICONTROL Add Dependency] オプションを使用すると、別の成功指標に到達した場合または到達していない場合に、成功指標を増分できます。<P>依存関係を追加する手順は次のとおりです。<ol><li>指標を追加したら、[!UICONTROL Additional Goal] の右側にある「。..」メニューの下の「**[!UICONTROL Advanced Settings]**」をクリックします。</li><li>[!UICONTROL Reporting Settings] セクションの下部にある「**[!UICONTROL Add Dependency]**」オプションをクリックします。</li><li>目的の指標を左側のペインから右側のペインにドラッグ&amp;ドロップし、「[!UICONTROL Reached]」をクリックして [!UICONTROL Reached] と [!UICONTROL Not Reached] の設定を切り替えます。</li></ol>追加した依存関係は後で編集または削除できます。 |
   | [!UICONTROL Conversion Metric] | デフォルトでは、コンバージョン指標は最適化目標指標と同じです。 ただし、「コンバージョン」オプションのチェックを外すことで、別のコンバージョン指標を定義 [!UICONTROL Same as Optimization Goal] きます。 |
   | [!UICONTROL Additional Metrics] | 使用するレポート指標を追加します。 コンバージョンまたは売上高指標を追加できます。<P>**メモ**:[!UICONTROL Engagement] の指標は、追加の指標としてはサポートされていません。 [!DNL Target] UI では [!UICONTROL Engagement] 指標を選択できる場合がありますが、レポートにデータが正確に表示されません。 |
   | [!UICONTROL Audiences for Reporting] | オーディエンスを追加して、レポートでオーディエンスによるフィルタリングを可能にします。デフォルトでは、レポートにすべての認定訪問者の結果が表示されます。オーディエンスを追加して結果をフィルタリングすると、訪問者をさらに絞り込むことができます。<P>**注意**：他のアクティビティタイプと異なり、[!UICONTROL Automated Personalization] は [!UICONTROL Adobe Analytics] をレポートソースとして使用できません（A4T）。 |
   | [!UICONTROL Notes] | 自分または他のチーム メンバーに役立つ、アクティビティに関する情報を入力します。 [!UICONTROL Notes] ペインはサイズ変更可能です。 |

   指標に名前を付けたり、指標の名前を変更したりする場合、次の文字は使用できません。

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

「**[!UICONTROL Save & Close]**」をクリックすると、アクティビティの [!UICONTROL Overview] ページが表示されます。 **エクスペリエンスをプレビュー** をクリックして、配信時のエクスペリエンスの外観をプレビューします。 サイト上の AP エクスペリエンスへのリンクを表示および共有して、[!UICONTROL Target] [!UICONTROL Visual Experience Composer] （VEC）外のエクスペリエンスの「真のプレビュー」を取得するために使用できるポップアップが表示されます。 プレビューを共有するには、メッセージに表示されたリンクを共有する必要があります。リンクをクリックしてブラウザーから直接 URL をコピーすると、機能しません。 リンクをコピーすると、URL には、メッセージ内のリンクからページにアクセスした場合にのみページを正しく表示するパラメーターが含まれます。

詳しくは、「[Automated Personalizationレポート](/help/main/c-reports/personalization-reports/reports-ap.md)」を参照してください。
