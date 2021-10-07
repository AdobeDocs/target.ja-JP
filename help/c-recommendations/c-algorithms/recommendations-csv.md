---
keywords: カスタム条件作成;アルゴリズム;条件;レコメンデーション条件;csv;ftp;csv のアップロード
description: CSV ファイルをアップロードして、Adobe [!DNL Target] Recommendationsでレコメンデーションをカスタマイズする方法を説明します。
title: Recommendationsでカスタム条件をアップロードする方法を教えてください。
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 7a52f7c046fb00672ef1b13704308be39f89c7ad
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 39%

---

# ![PREMIUM](/help/assets/premium.png) カスタム条件のアップロード

CSV ファイルをアップロードして [!DNL Adobe Target] のレコメンデーションをカスタマイズします。

[!UICONTROL 新しい条件を作成]画面を表示するには、複数の方法があります。一部の画面オプションは、画面の表示方法によって異なります。

* **[!UICONTROL Recommendations]** / **[!UICONTROL 条件]** ライブラリ画面で、**[!UICONTROL 条件を作成]** / **[!UICONTROL 条件を作成]** をクリックします。 ここで作成した条件は、自動的にすべての [!DNL Recommendations] アクティビティで利用できるようになります。
* [!UICONTROL Visual Experience Composer](VEC) を使用して [!DNL Recommendations] アクティビティを作成する場合、ページ上の要素を選択し、「[!UICONTROL  条件を選択 ]」画面が表示されます。次に、「[!UICONTROL Recommendations] と置換 [!UICONTROL  前に挿入 ]」をクリックします。または [!UICONTROL Recommendationsを ] の後に挿入します。 次に、使用可能な条件を選択するか、「**[!UICONTROL 条件を作成]**」をクリックします。 新しい条件を作成する場合は、他の [!DNL Recommendations] アクティビティで使用するために条件を保存できます。 詳しくは、「[Recommendationsアクティビティの作成 ](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md)」を参照してください。
* [!DNL Recommendations] アクティビティを編集している場合、ページの「 [!UICONTROL レコメンデーションの場所]」ボックスをクリックして、「**[!UICONTROL 条件を変更]**」を選択します。[!UICONTROL  条件を選択 ] 画面で、「**[!UICONTROL 条件を作成]**」をクリックします。 新しい条件を保存して、他の [!DNL Recommendations] アクティビティで使用できます。

次の手順では、最初の方法を使用して [!UICONTROL  新しい条件を作成 ] 画面にアクセスすることを想定しています。**[!UICONTROL Recommendations]** / **[!UICONTROL 条件]** ライブラリ画面

1. **[!UICONTROL Recommendations]** / **[!UICONTROL 条件]** をクリックします。

1. 「**[!UICONTROL 条件を作成]**」をクリックします。

1. 「[ 基本情報 ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info)」セクションに情報を入力します。

   1. **[!UICONTROL アルゴリズムの選択]** タイプドロップダウンリストで、「**[!UICONTROL カスタム条件]**」を選択します。

   1. 「**[!UICONTROL アルゴリズム]**」ドロップダウンリストから「**[!UICONTROL カスタムアルゴリズム]**」を選択します。

      >[!NOTE]
      >
      >上記の手順では、[!UICONTROL CSV のアップロード ] セクションが [!UICONTROL  新しい条件の作成 ] ダイアログボックスの下部に表示されます。

1. （条件付き）[ バックアップコンテンツ ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content) セクションの情報を入力します。

1. （条件付き） [ インクルージョンルール ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) セクションの情報を入力します。

1. 「**[!UICONTROL CSV をアップロード]**」セクションで、CSV ファイルの **[!UICONTROL 場所]** を選択します。

   ![「CSV のアップロード」セクション](assets/upload-csv.png)

   アップロードを成功させるには、CSV ファイルが正しくフォーマットされている必要があります。「**[!UICONTROL CSV テンプレートのダウンロード]**」をクリックして、正しくフォーマットされた CSV ファイルをダウンロードします。

   次の 2 つの場所のオプションがあります。

   * **FTP：** FTP サーバーから CSV ファイルをアップロードするには、「**[!UICONTROL FTP]**」を選択し、必要な情報を入力します。SSL を使用できます。この SSL は、FTPS プロトコルを使用して CSV ファイルを安全に転送します。
   * **URL:** URL から CSV ファイルをアップロードするには、「 **[!UICONTROL URL]**」を選択し、フィード URL を入力します。

1. 「**[!UICONTROL 保存]**」をクリックします。

## 注意点

* カスタム条件エンティティ（行）は、最大 1,000 のレコメンデーション品目（列）を含むことができます。

* カスタム条件の更新は、デフォルトでは「累積的」です。既存のキーと値のペアが、CSV アップロードファイルで指定した新しいキーと値のペアで上書きされます。CSV アップロードで指定されたキーを持たない既存のキーと値のペアは、引き続き配信に使用でき、CSV ファイルの一部として最後にアップロードされた時点から 31 日で期限が切れます。

   クライアントケアに連絡して、次回の CSV アップロードに含まれていない既存の結果を破棄できるようにします。この設定を有効にした場合、カスタム CSV フィードファイルに存在するキーのみを配信できます。 この設定は、すべてのカスタム条件に適用されます。

* カスタム条件フィードは 24 時間ごとに更新されます。

   カスタム条件のアップロードと同期のステータスは、[!UICONTROL Recommendations] / [!UICONTROL  条件 ] ページの各条件カードの下部に表示されます。 また、カスタム条件の編集時に [!UICONTROL  編集 ] ダイアログボックスでステータスを確認することもできます。

* エラーのないアップロードのフローは、[!UICONTROL  スケジュール ] > [!UICONTROL  フィードファイルのダウンロード ] > [!UICONTROL  読み込み ] > [!UICONTROL  成功 ] です。

* [!DNL Target] でアップロードに問題が発生した場合に発生する可能性のあるエラーメッセージは、次のとおりです。

   | エラーメッセージ | 詳細 |
   |--- |--- |
   | 不明なエラー | 技術的な内部エラーを示します。 |
   | 解析エラー | フィードファイルの形式に問題がある可能性があります。ファイル形式を修正し、アルゴリズムを保存し直すと、ファイルのダウンロードプロセスが再開します。 |
   | サーバーが見つかりません | インターネット上で認識可能な IP またはホスト名を指定します。 |
   | 資格情報エラー | サーバーでアクティブなアカウントの有効なユーザー名とパスワードを指定します。 |
   | ディレクトリが見つかりません | サーバーに存在するディレクトリを指定します。 |
   | ファイルが見つかりません | サーバー上の指定したディレクトリに存在するファイルの名前を指定します。 |

## トレーニングビデオ：Recommendations の条件の作成（12:33）![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオには、次の情報が含まれています（カスタム条件のアップロードに関する詳細は 11:43 から始まります）。

* 条件の作成
* 条件のシーケンスの作成
* カスタム条件のアップロード

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
