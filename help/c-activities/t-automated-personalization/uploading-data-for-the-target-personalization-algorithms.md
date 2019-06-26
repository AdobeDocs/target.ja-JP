---
description: CRM 情報や顧客のチャーン傾向スコアなどのオフラインデータは、パーソナライゼーションモデルを構築する際に非常に重要となることがあります。
seo-description: CRM 情報や顧客のチャーン傾向スコアなどのオフラインデータは、パーソナライゼーションモデルを構築する際に非常に重要となることがあります。
seo-title: Target のパーソナライゼーションアルゴリズムのデータのアップロード
solution: 'Target '
title: Target のパーソナライゼーションアルゴリズムのデータのアップロード
topic: Premium
uuid: eb0938b9-7f35-4bb5-ac4b-260b2144db5b
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Target のパーソナライゼーションアルゴリズムのデータのアップロード{#upload-data-for-target-s-personalization-algorithms} を参照してください。

CRM 情報や顧客のチャーン傾向スコアなどのオフラインデータは、パーソナライゼーションモデルを構築する際に非常に重要となることがあります。

Automated Personalization（AP）および 自動ターゲット のパーソナライゼーションアルゴリズムにデータを入力する方法はいくつかあります。[データを Target に送信する方法](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)で紹介している方法の他に、Experience Cloud 共有オーディエンス（Adobe Analytics、Audience Management）やアクティビティ内レポート用オーディエンスも使用されます。

自動的に収集され、Automated Personalization および自動ターゲットのパーソナライゼーションアルゴリズムで使用されるデータについて詳しくは、「[Automated Personalization のデータ収集](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)」を参照してください。

## ベストプラクティス {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

Target のパーソナライゼーションアルゴリズムのデータをアップロードするためのベストプラクティスを以下に示します。

* Target のパーソナライゼーションアルゴリズムで使用できる高品質データが増えれば増えるほど、AP および自動ターゲットアクティビティで結果として生成されるモデルの品質が向上します。
* 同じ目的を果たす複数のプロファイルスクリプトまたは属性の使用を制限します。
* セッション ID などの固有の ID は、必要ない限り渡しません。
* Target で自動的に収集されるデータ（[Target のパーソナライゼーションアルゴリズムのデータ収集](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)）を確認し、重複する情報を送信しないようにします。例えば、Target では IPアドレスを使用して訪問者の郵便番号を推定します。この情報を別個の変数として渡す必要はありません。
* 同じ属性／変数に複数の値を渡しません。複数の変数が連結されている場合、Target のパーソナライゼーションアルゴリズムでは各文字列を個別の値として扱い、パーソナライゼーションの情報の値を小さくします。
* 覚えやすく意味のある命名規則を使用して、[パーソナライゼーションインサイトレポート](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767)をわかりやすくします。

