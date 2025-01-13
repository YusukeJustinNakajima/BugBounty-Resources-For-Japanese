## BugBounty-Resources-For-Japanese
バグバウンティに関する有益な記事やサイトをまとめたリポジトリ。各記事に簡単な紹介文を付与。

## Disclaimer
- あくまで、筆者の所感で有益と感じた記事をリスト化しているので、本当に有益かどうかは各個人によります。
- 私の趣味嗜好で読んだ記事（脆弱性）に偏りがあります。したがって、網羅性については考慮しておりません。
- 記事ごとのコメントに誤りがある可能性があります。気づかれた場合には、遠慮なくご指摘ください。

## Timeline
- 2025/01/13 初版公開

## Table of Contents
- [General](#general)
- [XSS(Cross Site Scripting)](#xsscross-site-scripting)
- [CSS Injection](#css-injection)
- [CSRF(Cross-site request forgery)](#csrfcross-site-request-forgery)
- [CORS(Cross-origin resource sharing) Bypass](#corscross-origin-resource-sharing-bypass)
- [IDOR](#idor)
- [SSRF(Server-side request forgery)](#ssrfserver-side-request-forgery)
- [XXE(XML external entity)](#xxexml-external-entity)
- [SSTI(Server Side Template Injection)](#sstiserver-side-template-injection)
- [Web Cache Poisoning](#web-cache-poisoning)
- [Web Cache Deception](#web-cache-deception)
- [HTTP Request Smuggling](#http-request-smuggling)
- [Race Condition](#race-condition)
- [Prototype Pollution](#prototype-pollution)
- [GraphQL Attack](#graphql-attack)
- [LLM Attack](#llm-attack)
- [OAuth Bypass](#oauth-bypass)
- [Timing Attack](#timing-attack)
- [Email Vulnerability](#email-vulnerability)
- [Password Reset](#password-reset)
- [Rate Limit Bypass](#rate-limit-bypass)
- [File Upload Vulnerability](#file-upload-vulnerability)
- [Amazon AWS](#amazon-aws)
- [Mobile Hacking](#mobile-hacking)
- [Others](#others)

## Material List
### General 
#### [バグバウンティ入門(始め方) - blog of morioka12](https://scgajge12.hatenablog.com/entry/bugbounty_beginner#%E3%83%90%E3%82%B0%E3%83%90%E3%82%A6%E3%83%B3%E3%83%86%E3%82%A3%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0)
- morioka12さんのバグバウンティの始め方に関する記事
- 非常にわかりやすく、かつ、網羅的にバグバウンティについて知ることができる
#### [体系的に学ぶ 安全なWebアプリケーションの作り方 第2版](https://www.amazon.co.jp/%E4%BD%93%E7%B3%BB%E7%9A%84%E3%81%AB%E5%AD%A6%E3%81%B6-%E5%AE%89%E5%85%A8%E3%81%AAWeb%E3%82%A2%E3%83%97%E3%83%AA%E3%82%B1%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E4%BD%9C%E3%82%8A%E6%96%B9-%E7%AC%AC2%E7%89%88-%E8%84%86%E5%BC%B1%E6%80%A7%E3%81%8C%E7%94%9F%E3%81%BE%E3%82%8C%E3%82%8B%E5%8E%9F%E7%90%86%E3%81%A8%E5%AF%BE%E7%AD%96%E3%81%AE%E5%AE%9F%E8%B7%B5-%E5%BE%B3%E4%B8%B8/dp/4797393165)
- この界隈で非常に有名な書籍。サンプルが用意されているので、自分で手を動かしながら、代表的な脆弱性について理解を深めることがができる
#### [リアルワールドバグハンティング ―ハッキング事例から学ぶウェブの脆弱性](https://www.amazon.co.jp/%E3%83%AA%E3%82%A2%E3%83%AB%E3%83%AF%E3%83%BC%E3%83%AB%E3%83%89%E3%83%90%E3%82%B0%E3%83%8F%E3%83%B3%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0-%E2%80%95%E3%83%8F%E3%83%83%E3%82%AD%E3%83%B3%E3%82%B0%E4%BA%8B%E4%BE%8B%E3%81%8B%E3%82%89%E5%AD%A6%E3%81%B6%E3%82%A6%E3%82%A7%E3%83%96%E3%81%AE%E8%84%86%E5%BC%B1%E6%80%A7-Peter-Yaworski/dp/4873119219/)
- 様々な脆弱性の概要と実際の攻撃事例がまとまった書籍。辞書的に使うとよい。
#### [HackTricks | HackTricks](https://book.hacktricks.xyz/)
- バグバウンティに限らず、オフェンシブなセキュリティについて網羅的に記載されているサイト
#### [ハッキングAPI](https://www.oreilly.co.jp/books/9784814400249/)
- APIハッキングに関して、多くのラボを交えながら、実践的な知識を身に着けることができる
#### [Resources-for-Beginner-Bug-Bounty-Hunters](https://github.com/nahamsec/Resources-for-Beginner-Bug-Bounty-Hunters)
- バグバウンティに関する多数のツールやリソースがまとまったリポジトリ

### XSS(Cross Site Scripting)
#### [What is cross-site scripting (XSS) and how to prevent it?](https://portswigger.net/web-security/cross-site-scripting)
- XSS (Cross Site Scripting)とは何か、多くの実践的なラボを交えながら詳細に解説している記事
#### [What is cross-site scripting (XSS)? | Tutorial & examples](https://learn.snyk.io/lesson/xss/)
- Synk社によるXSSの解説記事。図が多く使われており、視覚的にもXSSを理解しやすい
#### [All about File upload XSS. Different ways to triggered XSS though](https://infosecwriteups.com/all-about-file-upload-xss-c72c797aaba3)
- ファイルアップロード経由での様々なXSSの事例を紹介
#### [バグバウンティにおける XSS の具体的な脅威の事例まとめ](https://scgajge12.hatenablog.com/entry/bugbounty_xss_escalation)
- morioka12さんによるXSSの事例紹介
- 単なるポップアップだけではなく、XSSをアカウント乗取りなどにエスカレーションさせる様々な事例について紹介
#### [S3経由でXSS!?不可思議なContent-Typeの値を利用する攻撃手法の新観点 - Flatt Security Blog](https://blog.flatt.tech/entry/content_type)
- Flatt Security社によるContent-Typeを利用する新たなXSSの提案
- Content-Typeに関するRFCと[WHATWG](https://whatwg.org/)の挙動の差異により、image/pngをtext/htmlなどに解釈させることが可能となる
#### [Hunting for blind XSS vulnerabilities: A complete guide](https://www.intigriti.com/researchers/blog/hacking-tools/hunting-for-blind-cross-site-scripting-xss-vulnerabilities-a-complete-guide)
- バグバウンティプログラムIntigritiによるblind XSSを見つけるための解説記事。
#### [ISO-2022-JPによるXSSの話 - 葉っぱ日記](https://hasegawa.hatenablog.com/entry/2025/01/02/203722)
- HTTPレスポンスヘッダーやHTML metaタグでの文字エンコーディング名の指定がない場合、ISO-2022-JP特有のバイト列を埋め込むことで、コンテンツをISO-2022-JPと誤認させることが可能
- これを悪用すると、バックスラッシュが円記号と解釈されることによりエスケープ処理を回避でき、XSSが成功する
#### [Exploiting XSS in hidden inputs and meta tags | PortSwigger Research](https://portswigger.net/research/exploiting-xss-in-hidden-inputs-and-meta-tags)
- inputタグにおいて、hidden属性が指定されている場合、XSSを成功させる条件は非常に厳しく、現実的な脅威にならない
- hidden属性が指定されている場合において、より現実的な方法で、XSSペイロードを実行する方法を発見した
#### [Cross-site scripting (XSS) cheat sheet](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)
- XSSに関するペイロードのチートシート
#### [DeepSeek AI: From Prompt Injection To Account Takeover](https://embracethered.com/blog/posts/2024/deepseek-ai-prompt-injection-to-xss-and-account-takeover/)
- LLMにXSSペイロードを作成させることで、そのウェブ画面上でXSSペイロードを発火させるという事例。
- Self-XSSではなく有効なXSSとするには、ソーシャルエンジニアリングによってファイルを読み込ませるなどの工夫が必要。

### CSS Injection
#### [CSSインジェクション | 技術者ブログ | 三井物産セキュアディレクション株式会社](https://www.mbsd.jp/research/20230403/css-injection/)
- CSS Injectionと呼ばれる本来のHTMLコンテンツ中には存在しないCSSを攻撃者が注入できる脆弱性について紹介
#### [Blind CSS Exfiltration: exfiltrate unknown web pages](https://portswigger.net/research/blind-css-exfiltration)
- CSPなどによってXSS攻撃ができない状況において、HTMLの属性値を抽出する攻撃方法を詳細に解説

### CSRF(Cross-site request forgery)
#### [What is CSRF (Cross-site request forgery)? Tutorial & Examples | Web Security Academy](https://portswigger.net/web-security/csrf)
- CSRF (Cross-site request forgery)とは何か、多くの実践的なラボを交えながら詳細に解説している記事
#### [CSRF(Cross-Site Request Forgery)攻撃について](https://zenn.dev/yktakaha4/articles/study_csrf_attack)
- CSRFに関する日本語での詳細な解説記事。実際に被害事例を交えながら、わかりやすくCSRFを解説している。
#### [Bypassing CSRF token validation | Web Security Academy](https://portswigger.net/web-security/csrf/bypassing-token-validation)
- 最も代表的なCSRF対策として、攻撃者に予測不可能なトークンを用意し、それがリクエストに含まれていない場合、リクエストを拒否するというものがある
- この対策のバイパス手法を、多くの実践的なラボを交えながら詳細に解説している記事
#### [Cookie Crumbles: Breaking and Fixing Web Session Integrity | USENIX](https://www.usenix.org/conference/usenixsecurity23/presentation/squarcina)
- SameSite CookieによるCSRF対策をバイパスする攻撃手法（CSRF token fixationなど）を提案し、多くのモダンなウェブフレームワークにおいてCSRF攻撃が成功することを示した
- CSRF攻撃だけではなく、CSRF攻撃の脅威を低減するためのCookieの仕組みについて詳細に解説しており、非常に有益な論文となっている
#### [Cross-Site POST Requests Without a Content-Type Header / nastystereo.com](https://nastystereo.com/security/cross-site-post-without-content-type.html)
- CSRF対策の一つとして、Content-Typeがapplication/jsonではない場合、リクエストを拒否するというものがある。
- これは、Content-Typeがapplication/jsonの場合は、fetch APIなどを使う必要があり、この場合には同一オリジンポリシーによって制限されるため、CORSバイパスが必要となるためである
- ウェブアプリケーションが、Content-Typeがapplication/jsonでないリクエストを拒否するだけのCSRF対策をしている場合、Blobオブジェクトによるペイロード送信によって、対策をバイパスできる

### CORS(Cross-origin resource sharing) Bypass
#### [What is CORS (cross-origin resource sharing)? Tutorial & Examples | Web Security Academy](https://portswigger.net/web-security/cors)
- CORS (cross-origin resource sharing)の設定ミスによる脆弱性について、多くの実践的なラボを交えながら詳細に解説している記事
#### [CORS Misconfiguration, could lead to disclosure of sensitive information](https://hackerone.com/reports/426165)
- HackerOneに報告されたCORSの設定ミスによる機微情報漏洩の事例

### IDOR
#### [Access control vulnerabilities and privilege escalation | Web Security Academy](https://portswigger.net/web-security/access-control)
- アクセス制御の不備による脆弱性とは何か、多くの実践的なラボを交えながら詳細に解説している記事
#### [Top 25 IDOR Bug Bounty Reports. In this article, we will discuss IDOR… | by Cristian Cornea | Medium](https://corneacristian.medium.com/top-25-idor-bug-bounty-reports-ba8cd59ad331)
- バグバウンティプログラムHackerOneに報告されたIDORのレポートにおいて、有益な25のレポートをまとめた記事
#### [Using E-Notation to bypass Access Control restrictions to access arbitrary user PII-discussions | by Keizo | Apr, 2024 | Medium](https://medium.com/@keizobugbounty/using-e-notation-to-bypass-access-control-restrictions-to-access-arbitrary-user-pii-discussions-1fa014b544d4)
- IDORに用いる数値表現をE-Notation（例えば、1230 = 123e1）で表現すると、IDOR対策をバイパスできた事例

### SSRF(Server-side request forgery)
#### [What is SSRF (Server-side request forgery)? Tutorial & Examples | Web Security Academy](https://portswigger.net/web-security/ssrf)
- SSRF (Server-side request forgery)とは何か、多くの実践的なラボを交えながら詳細に解説している記事
#### [Blind SSRF vulnerabilities | Web Security Academy](https://portswigger.net/web-security/ssrf/blind)
- Blind SSRFを見つけるための方法論について、実践的なラボを交えながら解説している記事
#### [Cracking the lens: targeting HTTP's hidden attack-surface | PortSwigger Research](https://portswigger.net/research/cracking-the-lens-targeting-https-hidden-attack-surface)
- Refererやホストヘッダーなど、様々なHTTPヘッダーに対してSSRFのペイロードを埋め込むことで、多くのBlind SSRF脆弱性を発見した事例
- Blind SSRFを見つけるための有益なBurp Suiteの拡張機能（Collaborator Everywhere）も併せて紹介
#### [Digging for SSRF in NextJS apps](https://www.assetnote.io/resources/research/digging-for-ssrf-in-nextjs-apps)
- CVE-2024-34351（NextJSのSSRF）の解説記事

### XXE(XML external entity)
#### [What is XXE (XML external entity) injection? Tutorial & Examples | Web Security Academy](https://portswigger.net/web-security/xxe)
- XXE (XML external entity)とは何か、多くの実践的なラボを交えながら詳細に解説している記事

### SSTI(Server Side Template Injection)
#### [Server-side template injection | Web Security Academy](https://portswigger.net/web-security/server-side-template-injection#identify)
- SSTI(Server Side Template Injection)とは何か、多くの実践的なラボを交えながら詳細に解説している記事

### Web Cache Poisoning
#### [Web cache poisoning | Web Security Academy](https://portswigger.net/web-security/web-cache-poisoning)
- Web cache poisoningとは何か、多くの実践的なラボを交えながら詳細に解説している記事
#### [Web Cache Entanglement: Novel Pathways to Poisoning](https://portswigger.net/research/web-cache-entanglement)
- ホストヘッダーとURLクエリに焦点を当てて、Web Cache Poisoningの様々な攻撃ベクターを紹介している記事
#### [DOS via cache poisoning. Today I’m going to talk about cache… | by Rachid.A | InfoSec Write-ups](https://infosecwriteups.com/dos-via-cache-poisoning-38f3a87f997c)
- "X-Timer"ヘッダーを悪用したWeb Cache PoisoningによるDoSの事例
#### [Cross-Site Scripting via Web Cache Poisoning and WAF bypass | by Lyubomir Tsirkov | Jun, 2024 | Medium](https://ltsirkov.medium.com/cross-site-scripting-via-web-cache-poisoning-and-waf-bypass-6cb3412d9e11)
- XSS対策をWeb Cache Poisoningによってバイパスした事例
- ブラウザで特殊文字がエンコードされた後に、CDNにキャッシュしても攻撃が成立しない。そこで、Burp Suiteなどのツール経由でエンコード前の値をCDNにキャッシュさせることで、有効な攻撃が可能になった

### Web Cache Deception
#### [Web cache deception | Web Security Academy](https://portswigger.net/web-security/web-cache-deception)
- Web Cache Deceptionとは何か、多くの実践的なラボを交えながら詳細に解説している記事
#### [Gotta cache 'em all: bending the rules of web cache exploitation | PortSwigger Research](https://portswigger.net/research/gotta-cache-em-all)
- PortSwiggerのMartin DoyhenardさんによるBlack Hat USA 2024の発表
- Web Cache Deceptionの原理から、パス正規化や静的パスの悪用など様々な攻撃ベクターを紹介
#### [How I Test For Web Cache Vulnerabilities + Tips And Tricks | by bombon | Medium](https://bxmbn.medium.com/how-i-test-for-web-cache-vulnerabilities-tips-and-tricks-9b138da08ff9)
- Web Cache Vulnerabilitiesに関する様々な事例を紹介
#### [A web cache deception chained to a CSRF, the recipe | by Rachid.A | InfoSec Write-ups](https://infosecwriteups.com/a-web-cache-deception-chained-to-a-csrf-the-recipe-9e9a5b5f53aa)
- Web Cache DeceptionによるCSRFトークンの窃取およびそのトークンの利用によるCSRF攻撃の事例
#### [ChatGPT Account Takeover - Wildcard Web Cache Deception | Harel Security Research](https://nokline.github.io/bugbounty/2024/02/04/ChatGPT-ATO.html)
- ChatGPTのshare機能のキャッシュ設定ミスによるアカウント乗取りの事例。CloudflareのCDNとウェブサーバーのURL正規化の差異を悪用したもの。

### HTTP Request Smuggling
#### [What is HTTP request smuggling? Tutorial & Examples | Web Security Academy](https://portswigger.net/web-security/request-smuggling)
- HTTP request smugglingとは何か、多くの実践的なラボを交えながら詳細に解説している記事
#### [HTTP リクエストスマグリング入門から最新研究まで - FFRIエンジニアブログ](https://engineers.ffri.jp/entry/2022/12/07/121640#HTTP-%E3%83%AA%E3%82%AF%E3%82%A8%E3%82%B9%E3%83%88%E3%82%B9%E3%83%9E%E3%82%B0%E3%83%AA%E3%83%B3%E3%82%B0)
- FFRI社によるHTTP Request Smugglingの入門から最新手法までの紹介記事
#### [HTTP Desync Attacks: Request Smuggling Reborn | PortSwigger Research](https://portswigger.net/research/http-desync-attacks-request-smuggling-reborn)
- HTTP Request SmugglingはRFCの修正によって、攻撃が難しくなっていき、もはや過去の攻撃と思われていた
- Transfer-Encodingに不正な値をインジェクトするなどの工夫によって、多くのアプリケーションにてHTTP Request Smugglingが成立することを示した
#### [Browser-powered request smuggling | Web Security Academy](https://portswigger.net/web-security/request-smuggling/browser)
- HTTP Request Smugglingはリクエスト長に関するヘッダー（Content-Length/Transfer-Encoding）のフロントサイド（プロキシやロードバランサなど）とサーバーサイド間の解釈不一致によって発生する脆弱性
- したがって、フロント - サーバーというシステム構成以外では成立しない攻撃であった
- ブラウザを用いることで、サーバー単体で動いているシステムにおいても、HTTP Request Smugglingを適用できることを示した
#### [Unveiling TE.0 HTTP Request Smuggling: Discovering a Critical Vulnerability in Thousands of Google Cloud Websites | @Bugcrowd](https://www.bugcrowd.com/blog/unveiling-te-0-http-request-smuggling-discovering-a-critical-vulnerability-in-thousands-of-google-cloud-websites/)
- TE.0と呼ばれる新たなHTTP Request Smugglingに関する攻撃ベクターを紹介。これは、バックエンドがTransfer-Encodingヘッダーを無視することにより発生。
- Google Cloudでホストされている数千のウェブサイトに影響を与えることを示した

### Race Condition
#### [Race conditions | Web Security Academy](https://portswigger.net/web-security/race-conditions)
- Race Conditionとは何か、多くの実践的なラボを交えながら詳細に解説している記事
#### [Smashing the state machine: the true potential of web race conditions](https://portswigger.net/research/smashing-the-state-machine)
- PortSwiggerのJames KettleさんによるBlack Hat USA 2023の発表
- これまでは、ネットワークの揺らぎなどによって、ウェブアプリケーションの多くではレースコンディション脆弱性を悪用するのは、非常に難しかった
- 本研究では、single-packet attackと呼ばれる攻撃によって、非常に短い時間幅において20-30のHTTPリクエストを送信することに成功させ、レースコンディション脆弱性を現実的な脅威にエスカレーションさせた
#### [Common Security Issues in Financially Oriented Web Applications](https://soroush.me/downloadable/common-security-issues-in-financially-orientated-web-applications.pdf)
- レースコンディションによって、TOCTOU（Time-of-check to time-of-use）がどのように発生しうるのか、金融系システムの具体的な処理を例に解説している記事
#### [10,000リクエストを166msで送信する、Race Conditionの新手法のリサーチについて](https://blog.flatt.tech/entry/expanding_single_packet_attack)
- Flatt Security社による"Smashing the state machine: the true potential of web race conditions"で提唱されたsingle-packet attackを拡張させた研究
- Single-packet attackでは、同時に送信できるパケット数は20-30に制限されていたが、この研究では、166msの間に約10,000リクエストを安定的に送信することに成功し、レースコンディションによるOTPバイパスをより現実的なものにしている

### Prototype Pollution
#### [What is prototype pollution? | Web Security Academy](https://portswigger.net/web-security/prototype-pollution)
- Prototype Pollutionとは何か、多くの実践的なラボを交えながら詳細に解説している記事
#### [Prototype pollution - and bypassing client-side HTML sanitizers - research.securitum.com](https://research.securitum.com/prototype-pollution-and-bypassing-client-side-html-sanitizers/)
- Prototype Pollutionによるクライアントサイドのサニタイザーのバイパス。DOMPurifyのバイパスにより、XSS攻撃を実行できた
#### [Exploiting prototype pollution - RCE in Kibana (CVE-2019-7609) - research.securitum.com](https://research.securitum.com/prototype-pollution-rce-kibana-cve-2019-7609/)
- KibanaにおけるPrototype Pollution経由でのRCE脆弱性（CVE-2019-7609）の解説記事

### GraphQL Attack
#### [GraphQL API vulnerabilities | Web Security Academy](https://portswigger.net/web-security/graphql)
- GraphQL Attackとは何か、多くの実践的なラボを交えながら詳細に解説している記事
#### [Learn with our GraphQL Tutorials, Examples, and Training - GraphQL Tutorials](https://www.apollographql.com/tutorials/#certifications)
- 代表的なGraphQLエンジンのAppploを使ったGraphQLのチュートリアル。GraphQLの文法や仕組みを理解するのに有益な記事。
#### [Black Hat GraphQL](https://nostarch.com/black-hat-graphql)
- GraphQLに対する攻撃の第一人者による書籍。
- GraphQLへの攻撃ベクターを網羅しており、かつ、それらを代表的なツールを用いながらハンズオンで学べる非常に有益な書籍。
#### [Authorization bypass due to cache misconfiguration | by Rikesh Baniya | Aug, 2024 | Medium](https://rikeshbaniya.medium.com/authorization-bypass-due-to-cache-misconfiguration-fde8b2332d2d)
- GraphQLのキャッシュ設定ミスによる認可バイパスの事例

### LLM Attack
#### [Web LLM attacks | Web Security Academy](https://portswigger.net/web-security/llm-attacks)
- LLMアプリケーションへの攻撃について、多くの実践的なラボを交えながら詳細に解説している記事
#### [OWASP Top 10 for Large Language Model Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- OWASPによるLLMアプリケーションに対する脅威とその対策の紹介
#### [LLM01: Invisible Prompt Injection](https://hackerone.com/reports/2372363)
- HackerOneの提供しているAIアシスタント[Hai](https://www.hackerone.com/hai-your-hackerone-ai-copilot)へのプロンプトインジェクションの事例
- ペイロードをUnicode形式でインジェクションすることによって、Haiにレポート内容を不当に高く評価させることに成功
#### [security flow in ChatGPT](https://salt.security/blog/security-flaws-within-chatgpt-extensions-allowed-access-to-accounts-on-third-party-websites-and-sensitive-data)
- Salt Security社によるChatGPTのエコシステム（現在のGPTs）のハッキング事例
- 認可制御の不備などにより、多くのプラグインにて機微情報の漏洩やアカウント乗取りが可能であったことの紹介
#### [Hacking Google Bard - From Prompt Injection to Data Exfiltration](https://embracethered.com/blog/posts/2023/google-bard-data-exfiltration/)
- GoogleのLLM(旧Bard, 現Gemini)に対するプロンプトインジェクションおよび情報抽出の事例
- マークダウン形式をHTMLにレンダリングする際に、攻撃者のサーバーに情報を送ることができた
- Google Docにプロンプトインジェクションと情報抽出するためのペイロードを仕込み、そのドキュメントを参照するように指示。その指示によって、HTMLへのレンダリングされ、情報漏洩が発生
#### [We Hacked Google A.I. for $50,000 - Lupin & Holmes](https://www.landh.tech/blog/20240304-google-hack-50000/)
- GoogleのLLM(旧Bard, 現Gemini)に対する攻撃事例の紹介
- Google Workspaceによって、GmailやGoogle Map等とLLMが連携できるようになったことを利用し、ユーザーのGmailコンテンツを攻撃者のサーバーに送信

### OAuth Bypass
#### [OAuth 2.0 authentication vulnerabilities | Web Security Academy](https://portswigger.net/web-security/oauth#how-does-oauth-2-0-work)
- OAuth 2.0の設定ミスによる脆弱性について、多くの実践的なラボを交えながら詳細に解説している記事
#### [OAuth Account Takeover - Account Takeover on Booking.com](https://salt.security/blog/traveling-with-oauth-account-takeover-on-booking-com)
- Salt Security社によるBooking.comのOAuthの設定ミスによるアカウント乗取りの脆弱性の解説記事
- OAuthの仕組みが多くの図で解説されており、OAuthの仕組みから、その設定ミスがどのように悪用されうるのか一連の流れを知ることができる

### Timing Attack
#### [Listen to the whispers: web timing attacks that actually work](https://portswigger.net/research/listen-to-the-whispers-web-timing-attacks-that-actually-work)
- PortSwiggerのJames KettleさんによるBlack Hat USA 2024の発表
- Burp Suiteの拡張機能Param Minerを用いることで、ペイロードの差異によって発生する非常に短い時間差を検出することに成功。
- この時間差を検出することで、多くのウェブサイトにて、Blind SQLiやリバースプロキシ発見などの多くの攻撃が可能であることを示した
#### [Welcome to this time-based CTF.](https://www.listentothewhispers.net/)
- "Listen to the whispers: web timing attacks that actually work"において提唱されたScored SSRF攻撃の知識を深めるためのCTF
#### [plORMbing your Prisma ORM with Time-based Attacks](https://www.elttam.com/blog/plorming-your-primsa-orm/)
- Prisma ORM(Object Relational Mapping)に対するタイミング攻撃の事例
- ORやNOTなどのオペレータを組み合わせることで、データベースから情報を抽出(ORM Leak)することに成功。併せて、それらのペイロードを用いて情報を抽出するツール"plORMber"を公開。

### Email Vulnerability
#### [Splitting the email atom: exploiting parsers to bypass access controls | PortSwigger Research](https://portswigger.net/research/splitting-the-email-atom)
- PortSwiggerのGareth HeyesさんによるBlack Hat USA 2024の発表
- 電子メールの複雑な仕様（Encorded-wordなど）を悪用することで、ウェブアプリケーションのパーサーとメールパーサーの解釈不一致を引き起こすことに成功。
- これによって、GithubやZendeskにおけるドメインバイパスに成功。ドメインバイパスは、特定のドメインに特権を与えている場合に特に有効。
#### [Old new email attacks - Slonser Notes](https://blog.slonser.info/posts/email-attacks/)
- 多くのメールパーサーを調査し、その多くがRFCに準拠していないことを示した。
- それによって、Outlookにメールを送る際に、任意のドメインに成りすませることを示した（CVE-2024-49040）
#### [Exploiting email address parsing with AWS SES - Nathan Davison](https://nathandavison.com/blog/exploiting-email-address-parsing-with-aws-ses)
- ウェブアプリケーションとAWS SES（電子メールプラットフォーム）間のアドレスの解釈不一致によるメール検証バイパスの事例
#### [How to Report DMARC Vulnerabilities Efficiently To Earn Bounties Easily | by Prajit Sindhkar | Techiepedia | Medium](https://medium.com/techiepedia/how-to-report-dmarc-vulnerabilities-efficiently-to-earn-bounties-easily-f7a65ecdd20b)
- DMARKとは何か、その設定不備がどのような影響を与えるか解説した記事
- バグバウンティにおいて、その設定不備をどのようにレポートすれば有効なレポートとなるのか紹介
#### [h@cktivitycon 2020: You've got pwned: exploiting e-mail systems - YouTube](https://www.youtube.com/watch?v=Bpnc1-g3fMk&t=150s)
- 電子メールにおける様々な攻撃ベクターを紹介
#### [A New Attack Surface on MS Exchange Part 1 - ProxyLogon!](https://blog.orange.tw/posts/2021-08-proxylogon-a-new-attack-surface-on-ms-exchange-part-1/)
- MS Exchangeにおける最も深刻な脆弱性の一つ"ProxyLogon"の解説記事
- ExchangeサーバーにおけるClient Access services（CAS）モジュールの不備によって、認証なしRCEを実現
#### [SMTP Smuggling - Spoofing E-Mails Worldwide](https://sec-consult.com/blog/detail/smtp-smuggling-spoofing-e-mails-worldwide/)
- 新たな攻撃ベクターである"SMTP Smuggling"を提唱した記事。メッセージ部分の終端記号の解釈が異なることを悪用する脆弱性。
- この脆弱性によって、任意のドメインから任意のメッセージを送ることが可能であり、非常に多くのメールクライアントに影響を及ぼすことを示した

### Password Reset
#### [All about Password Reset vulnerabilities | by Xcheater | InfoSec Write-ups](https://infosecwriteups.com/all-about-password-reset-vulnerabilities-3bba86ffedc7)
- パスワードリセット機能に関する脆弱性について、数多くの攻撃ベクターを紹介している記事
#### [Password reset poisoning | Web Security Academy](https://portswigger.net/web-security/host-header/exploiting/password-reset-poisoning)
- パスワードリセット機能がどのように動作するのか、そしてそれらをどのように攻撃するか、複数の実践的なラボを交えて解説している記事

### Rate Limit Bypass
#### [Methods to Bypass Rate Limit - Huzaifa Tahir - Medium](https://huzaifa-tahir.medium.com/methods-to-bypass-rate-limit-5185e6c67ecd)
- レート制限バイパスに関する様々な攻撃ベクターを紹介
#### [Bypassing Rate Limit Protection](https://github.com/tuhin1729/Bug-Bounty-Methodology/blob/main/RateLimit.md)
- レート制限バイパスに関する様々な攻撃ベクターを紹介
#### [Bypassing rate limits via race conditions](https://portswigger.net/web-security/race-conditions/lab-race-conditions-bypassing-rate-limits)
- レースコンディションによるレート制限バイパス

### File Upload Vulnerability
#### [Insecure file uploads: A complete guide to finding advanced file upload vulnerabilities](https://www.intigriti.com/researchers/blog/hacking-tools/insecure-file-uploads-a-complete-guide-to-finding-advanced-file-upload-vulnerabilities)
- バグバウンティプログラムIntigritiによるファイルアップロード機能に対する様々な攻撃ベクターの紹介

### Amazon AWS
#### [Amazon S3の脆弱な利用によるセキュリティリスクと対策 - Flatt Security Blog](https://blog.flatt.tech/entry/s3_security)
- Flatt Security社によるS3における脆弱性の事例紹介
- S3における脆弱性の詳細な解説だけではなく、その対策も提示しており、非常に有益な資料
#### [Amazon EC2 におけるセキュリティ(脆弱性)事例 - blog of morioka12](https://scgajge12.hatenablog.com/entry/ec2_security_ssrf)
- morioka12さんによるAmazon EC2 における脆弱性の事例紹介

### Mobile Hacking
#### [Android Pentesting 101: A Novice’s Handbook to Getting Started | by Saumya Kasthuri | Medium](https://medium.com/@srkasthuri/android-pentesting-101-a-novices-handbook-to-getting-started-8f56f877f418)
- Androidに対するハッキングのイントロダクション記事
#### [Android Emulator Setup for PenTest Using Android Studio | by Rafel | MII Cyber Security Consulting Services | Medium](https://medium.com/mii-cybersec/android-emulator-setup-for-pentest-using-android-studio-4191ad8a0684)
- Androidへのハッキングに必要なエミュレーターのセットアップ方法の紹介

### Others
#### [Confusion Attacks: Exploiting Hidden Semantic Ambiguity in Apache HTTP Server! | Orange Tsai](https://blog.orange.tw/posts/2024-08-confusion-attacks-en/)
- Orange TsaiさんによるBlack Hat USA 2024の発表
- Apache HTTP Serverの各モジュール間がそれぞれの仕様を理解していないこと（整合性が取れていないこと）による脆弱性を数多く報告している
- 複数のモジュール間の整合性の不一致からスタートし、（制約はあるものの）複数の脆弱性を組み合わせて認証なしRCEを実現した
#### [WorstFit: Unveiling Hidden Transformers in Windows ANSI!](https://blog.orange.tw/posts/2025-01-worstfit-unveiling-hidden-transformers-in-windows-ansi/)
- Orange TsaiさんによるBlack Hat Europe 2024の発表
- マルチバイトで表される文字列をシングルバイトの文字列に変換する際には、ベストフィット機能と呼ばれる機能が用いられる。
- 例えば、PHP-CGIの日本語と中国語環境においては、ソフトハイフン（0xAD）をハイフン（0x2D）に変換する。これにより、CVE-2012-1823の修正内容がバイパスされた。
- Windowsにおけるベストフィット機能の悪用という新たな攻撃ベクターを発見し、それがWindows標準実行ファイルや多数のライブラリに影響を及ぼすことを示した
#### [(Research) Exploiting HTTP Parsers Inconsistencies](https://rafa.hashnode.dev/exploiting-http-parsers-inconsistencies)
- ウェブフレームワークはHTTPリクエストをパースする際に、特定の文字やパスを無視することがある
- この挙動を悪用することで、ACLバイパスやWAFバイパス、SSRFにつながることを示した
#### [An Exploration & Remediation of JSON Interoperability… | Bishop Fox](https://bishopfox.com/blog/json-interoperability-vulnerabilities)
- JSONの処理方法（例えば、重複キーの処理やコメントの処理など）は、プログラミング言語やそのパーサーで異なることがある
- ユーザー入力のJSONを二つ以上の異なるパーサーが処理する場合に、さまざまな潜在的なセキュリティリスクにつながることを示した
#### [Till REcollapse Fuzzing the web for mysterious bugs](https://0xacb.com/2022/11/21/recollapse/)
- 多くの開発者は作成した正規表現を十分にテストすることなく、アプリケーションをデプロイしてしまっている
- これによって、意図しない文字を追加することで、メールアドレスの検証バイパスやリダイレクトによるアカウント乗取りが可能であることを示した
- ペイロード作成ツール[REcollapse](https://github.com/0xacb/recollapse)を公開
#### [Concealing payloads in URL credentials | PortSwigger Research](https://portswigger.net/research/concealing-payloads-in-url-credentials)
- URLは様々な形式で指定することができ、クレデンシャル入力部分（@より前の部分）にXSSなどのペイロードを仕込むことが可能
