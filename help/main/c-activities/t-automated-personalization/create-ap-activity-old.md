---
keywords: 自動パーソナライゼーション；アプリ
description: '[!UICONTROL Visual Experience Composer]を使用して [!DNL Adobe Target] で[!UICONTROL Automated Personalization] （AP） アクティビティを作成する方法を説明します。'
title: '[!UICONTROL Automated Personalization] アクティビティを作成するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: c467f629596b37c334276d6f095f19b639a8518d
workflow-type: tm+mt
source-wordcount: '1765'
ht-degree: 31%

---

# [!UICONTROL Automated Personalization] アクティビティの作成

[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Adobe Target]で[!UICONTROL Automated Personalization] （AP） アクティビティを作成します。

[!DNL Target]の[!UICONTROL Automated Personalization] （AP） アクティビティワークフローは、他のアクティビティタイプのワークフローとは異なります。

1. [!DNL Target] [!UICONTROL Activities] リストから、**[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]**&#x200B;をクリックします。

   ![アクティビティを作成：Automated Personalization](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. [!UICONTROL Visual Experience Composer] （VEC）を使用するには、**[!UICONTROL Visual]**&#x200B;をクリックします。

   [!UICONTROL Form-Based Experience Composer]を使用するには、[!UICONTROL Form]を選択します。 詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VECと[!UICONTROL Form-Based Experience Composer]に加えて、[!DNL Target]は[!UICONTROL Single Page Application VEC]を提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VECに関するトラブルシューティング情報については、[Visual Experience Composerのトラブルシューティング ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き） [ ワークスペースを選択](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

1. アクティビティ URLを確認または入力し、**[!UICONTROL Create]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >[!DNL Target]は、URL プロトコル （[!DNL https]と[!DNL http]）を区別しません。 結果、[!DNL `http://www.adobe.com`]と[!DNL `https://wwww.adobe.com`]は両方とも一致します。

   指定されたURLを持つページがVECで開きます。

1. 「**[!UICONTROL Name]**」フィールドをクリックし、アクティビティ名を入力します。

   ![「名前」フィールド](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

   アクティビティ名の先頭に次の文字を使用することはできません：

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名に次の文字シーケンスを含めることはできません。

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、次に等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン、マイナス |
   | ;@ | セミコロン、記号 |
   | ,= | コンマ、次に等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ、マイナス |
   | ,@ | コンマ、記号 |
   | `[`&quot; | 角括弧を開く、二重引用符 |
   | &quot;`]` | 二重引用符、角括弧を閉じる |

1. 「[Visual Experience Composer のオプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)」で説明しているとおりにページ要素を変更します。

   アセットマネージャーから一度に複数の画像を選択できます。 これにより、アクティビティ用に設定された各画像を含むページをすばやく表示できます。 また、オファー内のテキスト要素を容易に編集することもできます。 要素を編集すると、その要素が変更されたことを示すバーが要素上に表示されます。

1. **[!UICONTROL Manage Content]**&#x200B;をクリックして、使用可能な組み合わせを設定します。

   ![「コンテンツを管理」オプション](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   ダイアログボックスが表示され、画面上部に[!UICONTROL Experiences]、[!UICONTROL Offers]、[!UICONTROL Exclusion Groups]の3つのオプションが表示されます。

   ![コンテンツを管理ダイアログボックス](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >AP アクティビティでは最大30,000個のエクスペリエンスを作成できますが、5,000個未満のエクスペリエンスを使用すると、このアクティビティのパフォーマンスは最も高くなります。 アクティビティで[!UICONTROL Disallow Duplicates] オプションが有効になっている場合でも、同じ制限が適用されます。

   [!UICONTROL Experiences] リストには、アクティビティ用に選択された各コンテンツと、そのアクティビティが割り当てられている場所が表示されます。

   目的のエクスペリエンスにカーソルを合わせて[!UICONTROL Exclude] アイコンをクリックすると、特定のエクスペリエンスを除外できます。

   ![除外アイコンにマウスポインターを置く](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   関連するエクスペリエンスのチェックボックスを選択し、ダイアログボックスの右上隅にある「[!UICONTROL Exclude]」アイコンをクリックすることで、エクスペリエンスを一括除外または含めることができます。

   ![一括除外オプション](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   このリストビューをフィルタリングして、[!UICONTROL Status] ドロップダウンリストをクリックすることで、除外されたアクティビティのみを表示したり、含まれたアクティビティのみを表示したりできます。

1. （条件付き） **[!UICONTROL Offers]**&#x200B;をクリックしてコンテンツを選択し、レポートグループに割り当てるか、特定の訪問者にターゲティング付きの特定のオファーのみを表示できるようにします。

   レポートグループについて詳しくは、[Automated Personalizationでのレポートグループの提供](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)を参照してください。

1. （条件付き） **[!UICONTROL Exclusion Groups]**&#x200B;をクリックして、アクティビティから除外する要素の組み合わせを選択します。

   ![コンテンツを管理ダイアログボックスの「除外グループ」タブ](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   AP テストでは 30,000 個までエクスペリエンスを作成できますが、アルゴリズムが最高のパフォーマンスを発揮するのはエクスペリエンスが 10,000 個未満の場合です。 アクティビティで[!UICONTROL Disallow Duplicates] オプションが有効になっている場合でも、同じ制限が適用されます。

   アクティビティでまだ除外グループを使用していない場合は、「**除外グループを作成**」をクリックします。 リストにフィルターを適用し、除外する組み合わせのみを表示できます。 除外グループに名前を付け、**保存**&#x200B;をクリックします。

   既存の除外グループを編集するには、編集するグループにマウスポインターを置いてから鉛筆アイコンをクリックします。

1. アクティビティのコンテンツの設定が完了したら、**[!UICONTROL Done]**&#x200B;をクリックします。

1. 他の[!DNL Target] アクティビティタイプを使用している場合、**ターゲティング**&#x200B;手順は見慣れています。 ここで、オーディエンスを選択し、**[!UICONTROL Custom Allocation]** ドロップダウンリストをクリックしてコントロールエクスペリエンスを表示する訪問者の割合を指定し、**次へ**&#x200B;をクリックします。

   [!UICONTROL Custom Allocation] ドロップダウンリストでは、次のオプションから選択できます。

   ![トラフィック配分目標ドロップダウンリスト](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL Evaluate Personalization Algorithm (50/50)]:**&#x200B;目標がアルゴリズムをテストする場合は、コントロールとターゲット アルゴリズムの間で訪問者を50/50%分割します。 この配分により、上昇率を最も正確に推定できます。 「ランダムエクスペリエンス」をコントロールとして使用する場合にお勧めします。
   * **[!UICONTROL Maximizing Personalization Traffic (90/10)]:**&#x200B;目標が「常時稼動」アクティビティを作成する場合は、訪問者の10%をコントロールに入れます。 このオプションにより、アルゴリズムが継続的に学習するのに十分なデータが確保されます。 ここでのトレードオフは、より多くのトラフィックをパーソナライズする見返りとして、正確な上昇率を把握する精度が低くなることです。 特定のエクスペリエンスをコントロールとして使用する場合、このオプションは目標に関係なく推奨されるトラフィック分割です。
   * **[!UICONTROL Custom Allocation]:**&#x200B;必要に応じて、手動で割合を分割します。

1. （条件付き） [!UICONTROL Control] ドロップダウンリストから、[ コントロールとして使用する特定のエクスペリエンスを選択](/help/main/c-activities/t-automated-personalization/experience-as-control.md)するか、[!UICONTROL Random Experience.]を選択します

   コントロールエクスペリエンスは、自動テストによってどれだけの上昇率を実現するかを判断するための比較となります。

   [!UICONTROL Automated Personalization]は、コントロール グループに対するパフォーマンスを常に測定します。 少なくとも訪問者の 10％はコントロールグループに配分することをお勧めします。 与えられたデータに対するパーソナライゼーションアルゴリズムが、パーソナライゼーションを行わない場合（ランダムに提供されたコントロールなど）よりも優れたパフォーマンスを発揮するかどうかをテストする場合、コントロールとパーソナライゼーションアルゴリズムの間のトラフィックを50/50%分割することが、この目標を達成するための最も迅速かつ正確な方法です。 パーソナライズされたトラフィックの量を最大化したい場合、アクティビティが生み出す正確な上昇率を把握することにあまり関心がない場合は、コントロールとパーソナライゼーションアルゴリズムの間でトラフィックを10/90%分割することが、この目標を達成するための最も迅速で最も正確な方法です。

   >[!NOTE]
   >
   >[!UICONTROL Automated Personalization]のアクティビティでは、エントリ条件（URL ターゲティング、テンプレートルール、オーディエンスターゲット）がリクエストごとに評価されます。 以前のバージョンでは、エントリ条件はセッションごとに 1 度評価されていました。

1. **[!UICONTROL Next]**&#x200B;をクリックして&#x200B;**[!UICONTROL Goals & Settings]** ページを表示します。
1. 次の設定でアクティビティを設定し、**[!UICONTROL Save & Close]**&#x200B;をクリックします。

   | 設定 | 説明 |
   |--- |--- |
   | [!UICONTROL Name] | アクティビティの名前を設定します。 チームメンバーが[!UICONTROL Activities] リストでアクティビティを認識できるほど、わかりやすい名前をアクティビティに付けます。 上記の表を参照して、アクティビティ名で許可されていない文字を確認してください。 |
   | [!UICONTROL Objective] | （オプション）テストの目的を入力します。 目的を設定しておくと、アクティビティの用途を覚えやすくなります。 |
   | [!UICONTROL Priority] | 設定に応じて、[!UICONTROL Priority]の[!DNL Target] UIとオプションは異なります。 [!UICONTROL Low]、[!UICONTROL Medium]または[!UICONTROL High]の従来の設定を使用するか、0 ～ 999の細かい優先度を有効にできます。<P>優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。 ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。<P>このオプションが[!UICONTROL Administration] > [!UICONTROL Reporting] （デフォルト）で有効になっていない場合は、優先度を[!UICONTROL Low]、[!UICONTROL Medium]、または[!UICONTROL High]に指定します。<P>きめ細かい優先度を有効にするには、[!UICONTROL Administration] > [!UICONTROL Reporting]をクリックし、[!UICONTROL Enable Fine-Grained Priorities] オプションを「オン」の位置に切り替えます。<P>このオプションが有効になっている場合は、0 ～ 999の値を指定します。<ul><li>0 = 低</li><li>999 = 高</li></ul>以前のバージョンの[!DNL Target Standard/Premium]で作成されたアクティビティの場合、[!UICONTROL Low]の優先度は0に変換され、[!UICONTROL Medium]の優先度は5に変換され、[!UICONTROL High]の優先度は10に変換されます。 これらの値は必要に応じて調整できます。<P>**注意**：きめ細かい優先順位を使用した後にこのオプションを無効にする前に、すべての優先順位を0、5、および10に戻す必要があります。 |
   | [!UICONTROL Duration] | アクティビティの開始日と終了日を設定します。 [!UICONTROL When Activated]を選択するか、特定の日時を指定できます。 |
   | [!UICONTROL Optimization Goal] | 以下の 2 つのパラメーターを使用して最適化目標を指定します。<ul><li>このアクティビティで測定するもの</li><li>その目標が達成されたことを示すアクティビティ参加者によって取られるアクション。</li></ul>[!UICONTROL My Primary Goal]の右側にある3つのドットを選択して、最適化の目標に名前を付けることができます。 [!UICONTROL Automated Personalization] アクティビティは、[!UICONTROL Conversion]または[!UICONTROL Revenue]を測定できます。 コンバージョンは、ページを表示するか、mboxを表示することで達成できます。 クリックを追跡することもできます。<P>また、主な目標は、モデリングシステムがエクスペリエンスの成功を計算するために使用するモデリング指標になります。<P>モデリングの目標に達した後も、訪問者をアクティビティ内にとどめて、追跡の対象とすることができます。 例えば、多くの場合、[!UICONTROL Automated Personalization] アクティビティはクリック率の向上に使用され、これがモデリング目標として設定されます。 しかし、クリック率の向上が最終的にどのようにコンバージョンにつながっているかを確認することが重要なので、最終的なコンバージョンまで追跡することが欠かせません。<P>複数の指標の依存関係を指定したり、指標に到達したらカウントを増分するか、指標に到達しなかったらカウントを増分するかを柔軟に選択したりできます。<P>成功指標の依存関係を設定する前に、両方（または複数）の成功指標を定義する必要があります。<P>[!UICONTROL Add Dependency] オプションを使用すると、別の成功指標に達した場合または達しなかった場合に、成功指標を増分できます。<P>依存関係を追加する手順は次のとおりです。<ol><li>追加の指標を追加したら、[!UICONTROL Additional Goal]の右側にある3点メニューの下の&#x200B;**[!UICONTROL Advanced Settings]**&#x200B;をクリックします。</li><li>「[!UICONTROL Reporting Settings]」セクションの下部にある「**[!UICONTROL Add Dependency]**」オプションをクリックします。</li><li>左側のペインから右側のペインに目的の指標をドラッグ&amp;ドロップし、[!UICONTROL Reached]をクリックして[!UICONTROL Reached]と[!UICONTROL Not Reached]の間で設定を切り替えます。</li></ol>追加した依存関係は後で編集または削除できます。 |
   | [!UICONTROL Conversion Metric] | デフォルトでは、コンバージョン指標は最適化目標指標と同じです。 ただし、[!UICONTROL Same as Optimization Goal] オプションのチェックを外すことで、別のコンバージョン指標を定義できます。 |
   | [!UICONTROL Additional Metrics] | 使用する追加のレポート指標を追加します。 コンバージョンまたは売上高指標を追加できます。<P>**注**: [!UICONTROL Engagement]指標は追加の指標としてサポートされていません。 [!DNL Target] UIで[!UICONTROL Engagement]指標を選択できる場合がありますが、データはレポートに正確に表示されません。 |
   | [!UICONTROL Audiences for Reporting] | オーディエンスを追加して、レポートでオーディエンスによるフィルタリングを可能にします。 デフォルトでは、レポートにすべての認定訪問者の結果が表示されます。 オーディエンスを追加して結果をフィルタリングすると、訪問者をさらに絞り込むことができます。<P>**注**：他のアクティビティ タイプとは異なり、[!UICONTROL Automated Personalization]は[!UICONTROL Adobe Analytics]をレポート ソース （A4T）として使用できません。 |
   | [!UICONTROL Notes] | 自身や他のチームメンバーにとって役立つアクティビティ情報を入力します。 [!UICONTROL Notes] ペインはサイズ変更可能です。 |

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

**[!UICONTROL Save & Close]**&#x200B;をクリックすると、アクティビティの[!UICONTROL Overview] ページが表示されます。 「**エクスペリエンスのプレビュー**」をクリックして、配信時にエクスペリエンスがどのように表示されるかをプレビューします。 [!UICONTROL Target] [!UICONTROL Visual Experience Composer] （VEC）以外のエクスペリエンスの「真のプレビュー」を取得するために、サイト上のAP エクスペリエンスへのリンクを表示および共有するために使用できるポップアップが表示されます。 プレビューを共有するには、メッセージに表示されたリンクを共有する必要があります。 リンクをクリックした後、ブラウザーから直接URLをコピーしても機能しません。 リンクをコピーすると、メッセージ内のリンクからページにアクセスする場合にのみ、ページを正しく表示するパラメーターがURLに含まれます。

詳しくは、「[Automated Personalizationレポート](/help/main/c-reports/personalization-reports/reports-ap.md)」を参照してください。
