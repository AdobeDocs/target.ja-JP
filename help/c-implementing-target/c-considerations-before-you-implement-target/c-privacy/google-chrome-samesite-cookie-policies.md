---
description: Google Chromeバージョン76以降で使用されるTargetおよびSameSite IETF標準に関する情報です。
keywords: google;samesite
seo-description: Google Chromeバージョン76で導入されたAdobe TargetおよびSameSite IETF標準に関する情報です。
seo-title: Adobe TargetおよびSAeSiteのcookieポリシー
solution: 'Target '
subtopic: 導入
title: Google Chromeサイトのcookieポリシー
topic: Standard
uuid: aaeda1e6-7b2c-4a00-b65d-bfc95ea796b5
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Google Chromeサイトのcookieポリシー

Googleは最近、Chrome76（2019年7月30日リリース用）で始まることを発表しました。開発者は、Webサイト間で動作できるcookieと、ユーザーを追跡できるcookieを明示的に指定する必要があります。

## SAMSSiteの概要

Google Chrome76（以降）で、cookieをサイト間で送信できるようにするときにセキュリティ保護を提供するために、GoogleはGoogle Chrome76（以降）で"sameSite"という名前のサポートを追加しています。SameSite requires web developers to manage cookies with the SameSite attribute component in the `Set-Cookie` header.

sameSite属性に渡すことができる値は3つあります。厳密、ラオスまたはなし。

| 値 | 説明 |
| --- | --- |
| 厳密な | この設定を持つcookieは、最初に設定されたドメインを訪問した場合にのみアクセスできます。つまり、厳密な場合、cookieはサイト全体で使用されないようにブロックされます。このオプションは、銀行など高セキュリティを必要とするアプリケーションに最適です。 |
| ラオス | Cookies with this setting are sent only on same-site requests or top-level navigation with non-idempotent HTTP requests, such as `HTTP GET`. Therefore, this option should be used if the cookie can be used by third-parties, but with an added security benefit that protects users from being victimized by [CSRF](https://en.wikipedia.org/wiki/Cross-site_request_forgery) (Cross-Site Request Forgery) attacks. |
| None | この設定を持つcookieは、cookieの動作と同じように機能します。 |

上記のことを念頭に置いて、Chrome76（以降）では次の2つの設定が導入されています。「デフォルトのcookieごとにSAMSSite"および"sameSiteを使用しないcookie"は保護されている必要があります。ユーザーは、設定のいずれかまたは両方を有効にすることができます。

| 設定 | 説明 |
| --- | --- |
| デフォルトのcookieでSAMSSiteを使用 | When set, all cookies that don't specify the SameSite attribute are automatically forced with `SameSite = Lax`. |
| sameSiteのないcookieは保護されている必要があります | When set, cookies without the SameSite attribute or with `SameSite = None`, must be Secure. このコンテキストで保護されている場合、すべてのブラウザーリクエストはHTTPSプロトコルに従う必要があります。この要件に準拠しないcookieは拒否されます。 |

![SAMSSite]設定ページ](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/samesite.png)

## Targetは、Googleのセキュリティのベストプラクティスに従います

Targetを使用すると、セキュリティの最新のベストプラクティスを常にサポートすることで、確実に成功を収めることができます。TargetがGoogle Chrome76で導入された新しいセキュリティ設定をサポートすることをお知らせします。

訪問者が「デフォルトのcookie"設定をオンにしている場合、"Targetは、影響を受けずに、ユーザーによる介入なしに、引き続きパーソナライゼーションを提供します。Target uses first-party cookies and will continue to function properly as the flag `SameSite = Lax` is applied by Google Chrome.

訪問者が"sameSiteを使用しないcookie"を有効にして、Targetのクロスドメイントラッキング機能のオプトインを有効にしていない場合、Targetのファーストパーティcookieは引き続き機能します。However, when you opt-in to using cross-domain tracking to leverage Target across multiple domains, Google Chrome 76 (and later) requires `SameSite = None` and `Secure` flags to be used for third-party cookies. つまり、サイトでHTTPSプロトコルを使用していることを確認する必要があります。Target's client-side libraries automatically use the HTTPS protocol and, in addition to that, attach the `SameSite = None` and `Secure` flags to Target’s third-party cookie to ensure all activities continue to deliver.

## 必要な操作

Google Chrome76以降のユーザー向けにTargetを引き続き動作させるには、次の表を参照してください。

テーブルには、次の列が含まれています。

* **Targetクライアント側ライブラリ**:mbox. js、at. js1を使用しているかどうか。*x*&#x200B;またはat. js2.*サイト上のx、* Google Chromeの設定による
* **デフォルトでcookieが有効になっているか= Enabled**:Chrome76以降で、訪問者に「デフォルトのcookieが有効になっています」というメッセージが表示されている場合、Targetにはどのように影響し、Targetを継続して動作させるために必要なものがありますか
* **sameSiteのないcookieは、secure= Enabledである**&#x200B;必要があります。訪問者がChrome76以降で「セキュリティで保護されている必要があります」を有効にしている場合、Targetにはどのような影響がありますか。これにより、Targetを継続して動作させるために必要なものがあります
* **Adobe Targetのクロスドメイントラッキング=有効**:訪問者が「デフォルトのサイトで同じサイト」を有効にしており、"sameSiteを使用しないcookieを有効にする必要があります」が有効になっており、クロスドメイン追跡にTargetを使用している場合、Targetをクロスドメイントラッキングに使用するにはどうしますか。Targetを引き続き機能させるには、次の手順に従います

| Targetのクライアント側ライブラリ | デフォルトではsameSiteが有効になっています=有効 | sameSiteのないcookieは保護=有効にする必要があります | Adobe Targetのクロスドメイントラッキング=有効 |
| --- | --- | --- | --- |
| mbox.js | mbox. jsがファーストパーティcookieを使用しているので、影響はありません | 顧客がクロスドメイントラッキングを使用していないので、影響はありません | お客様は、サイトのHTTPSプロトコルを有効にする必要があります。<br>Targetでは、サードパーティCookieを使用してユーザーを追跡し、 `SameSite = None` Googleにはサードパーティcookieが必要で、サイトにHTTPSプロトコルを使用する必要があります。 |
| at.js 1.*x* | at. js1では影響しません。*x* はファーストパーティcookieを使用する | 顧客がクロスドメイントラッキングを使用していないので、影響はありません | お客様は、サイトのHTTPSプロトコルを有効にする必要があります。<br>Targetでは、サードパーティCookieを使用してユーザーを追跡し、Googleはサードパーティcookieを必要とし、サイト `SameSite = None` にHTTPSプロトコルを使用する必要がある |
| at.js 2.*x* | at. js2では影響しません。*x* はファーストパーティcookieを使用する | 顧客がクロスドメイントラッキングを使用していないので、影響はありません | クロスドメイントラッキングはat. js2ではサポートされていません。*その* ため、お客様には影響はありません |

## アドビが必要とする作業

| Targetのクライアント側ライブラリ | デフォルトではsameSiteが有効になっています=有効 | sameSiteのないcookieは保護=有効にする必要があります | Adobe Targetのクロスドメイントラッキング=有効 |
| --- | --- | --- | --- |
| mbox.js | mbox. jsがファーストパーティcookieを使用しているので、影響はありません | 顧客がクロスドメイントラッキングを使用していないので、影響はありません | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 1.*x* | at. js1では影響しません。*x* はファーストパーティcookieを使用する | 顧客がクロスドメイントラッキングを使用していないので、影響はありません | Target adds `SameSite = None` and `Secure` flag to third-party cookie when the Target backend is called. |
| at.js 2.*x* | at. js2では影響しません。*x* はファーストパーティcookieを使用する | 顧客がクロスドメイントラッキングを使用していないので、影響はありません | クロスドメイントラッキングはat. js2ではサポートされていません。*x* |

## まとめ

業界では、消費者向けにより安全なWebを作成するために、Targetは、訪問者に対して、ミーティング中にパーソナライズされたエクスペリエンスを配信し、訪問者のプライバシー期待を超えていることに積極的にコミットされています。
