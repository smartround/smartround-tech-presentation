@snap[midpoint span-100]
### smartroundを支える技術
@snapend

---

### 初めに

* この資料は2020年10月時点の内容です
* まだサービス開発開始後2年未満で急成長中なので<br/>それを踏まえた上で現在とのDiffは脳内補完してください
* [Github管理しているので以前のものも見れます](https://github.com/smartround/smartround-tech-presentation)

---

### この資料で紹介すること

* 技術スタック
* smartroundのシステム特徴
* 技術選定の背景・理由
* その他smartroundの魅力について軽く触れる

---

### サービスについて

@snap[west span-50]
@img[](assets/img/startup-investor-advisor.png)
@snapend

@snap[east span-50]
* スタートアップ・投資家間の日本最大のデータプラットフォームとなることを目指しています
* スタートアップ向けには投資家の方とのやりとりや会社運営において必要な様々なサービスを提供
 * 株主総会・資本政策・経営管理・投資家とのマッチング
* 投資家向けには投資先管理のためのCRMを提供しています
 * スタートアップがデータ入力することで自動更新されるCRMというのが特徴です
* [サービスURLはこちら](https://jp.smartround.com)
@snapend

---

### 実績

* 業界のプレイヤーを巻き込みつつサービス展開しています
  * スタートアップ1200社登録
  * 投資家100社以上がパートナー企業に
* 著名エンジェル20名近くや海外投資家からも投資を受けています

---

### サービス使用技術

@snap[text-08]
* Frontend
  * 言語: TypeScript / SCSS
  * フレームワーク: Vue.js
* Backend
  * 言語: Kotlin(JVM)
  * フレームワーク: Ktor
* DB
  * RDB: PostgreSQL
  * KVS: Redis
* Infrastructure
  * AWS
  * 構成管理: Terraform / Serverless
@snapend
  
---

### 開発利用ツール

@snap[text-08]
* Communication
  * Slack / GitHub / ZenHub
* Design
  * Figma / Zeplin
* CI
  * CircleCI
* Monitoring
  * TrackJs
* Other
  * Docker
@snapend

---

### smartroundのシステム特徴

@snap[text-08]
* 1.UI/UXの追求
  先行サービスが日本では少ないため<br/>とにかくわかりやすいサービスにする必要がある
<br/>
* 2.セキュリティ
  （SaaSとしては珍しく）基本機能として<br/>他社データの閲覧ができるため情報漏洩が<br/>無いようにする必要がある
<br/>
* 3.メンテナンス性への配慮
  数値計算も多く、サービス規模が大きいため<br/>メンテナンス性を高く保つ必要がある
@snapend

---

@snap[midpoint span-100]
### フロントエンドについて
@snapend

---

### Vue.js採用背景

* スタートアップらしくリッチでイケてるUIに<br/>したい！✨
* 一方工数はそこまでかけられない…💰

<br/> 
⇒ 段階的に適用していくことができるVue.jsを採用

---


### Typescript採用背景

@snap[west span-50]
@img[](/assets/img/feature-capital-event-preview.png)
@snapend

@snap[east span-50]
* 数値計算等の処理もあるため、JSに型がつけられるTypescriptを採用
 * 例) 入力値から資本政策表を自動計算しリアルタイムプレビュー
@snapend

---

### その他特徴

@snap[west span-50]
@img[](/assets/img/feature-drag-and-drop.png)
@snapend

@snap[east span-50]
* UXを上げるためDrag and Drop APIなど積極的に利用
* 他にもWeb Pushやwebsocket等、UX向上のため様々チャレンジしています
@snapend

---

### コンポーネント設計

@snap[west span-50]
@img[](/assets/img/figma-symbols.png)
@snapend

@snap[east span-50]
* サービス規模が大きく長期的な目線で開発</br>していきたいためコンポーネント設計に</br>ついても意識しています
  * [StoryBookも公開しています](https://smartround.github.io/smartround-storybook/?path=/story/*)
  * Figmaでシンボル定義もしていっています 
@snapend

---

@snap[midpoint span-100]
### サーバサイドについて
@snapend

---

### 概要

* サーバサイドKotlin(JVM）で開発
  * 数値計算・権限制御等、堅牢性が重要だったため<br/>静的型付けでJVM資産が利用できるKotlinを採用

* フレームワークはKtor（Kotlinを作ったJetbrains社が開発しているフレームワーク）を採用
  * 特に権限制御処理等で色々なカスタマイズを<br/>行いたかったため薄いフレームワークが良かった
  * 採用時はバージョン1.0.0-betaだったので<br/>新規技術ならではの面白さにも期待して

---

### 特徴

* レイヤをきっちり分けている
 * 権限制御を多層的に漏れなく行えるようにするため
 * 3サービス同時展開で共通コードも多く<br/>メンテナンス性を確保するため

---

### サーバサイドアーキテクチャ

@img[](assets/img/serverside-architecute-graph.png)

---

@snap[midpoint span-100]
### インフラについて
@snapend

---

### インフラ

利用しているAWSサービスの一例です。

@snap[text-08]
* WebApp
  * ElasticBeanstalk / RDS / ElastiCache / S3
* Batch
  * Lambda
* WebsocketAPI
  * API Gateway / Lambda / DynamoDB 
* Build / Deploy
  * CodeBuild / CodePipeline
* Others
  * Route53 / CloudWatchLogs / QuickSight / CloudTrail / GuardDuty
@snapend

@snap[text-07]
※ 今後の拡張に備えなるべく一般的な構成にすることを意識してます
@snapend

---

### リリースサイクル

* 週1で定期リリースを行っています
  * リリースサイクルは短く保つことを意識しています

---

### 現在のチーム

* エンジニア3名、デザイナー1名という少数精鋭で進めています。
* やりたいことはたくさんあり、自身の力量が<br/>ダイレクトに反映されるやりがいのある仕事です💪
* コロナ禍によりオフィスを解約し社員全員フルリモート勤務になったため、勤務地は問いません！

---

### 制度的なサポート

* 開発マシンは自由に選べます
  * 例：MacbookProの最新機種にメモリ増設する人も
* カンファレンス参加費・技術書購入費へのサポートもあります
  * 例：KotlinConf2019への参加費全額出ました

---

### 他社との交流

* Kotlin, Ktorが技術的に新しいこともあり<br/>コミュニティとして交流が盛んです
  * 例：同じKtorを採用している近隣スタートアップと飲み会・勉強会を開催

---

### その他魅力1

* サービス開発スタート時から今に至るまでほぼ同じ<br/>エンジニア・デザイナーがフルコミット😎
  * 初期から一貫した思想でUI/UXやコードベースが<br/>作られてきました
  * スタートアップあるあるの立ち上げ期の謎の負債は<br/>極めて少ないです 

---

### その他魅力2

* ベンチャーファイナンスに詳しくなれます💰
  * 資金調達のメカニズムや株の仕組みについて詳しくなれます（[参考：弊社公開の資金調達マニュアル](https://www.smartround.com/public/articles) ）
  * 株主総会等、会社運営にも詳しくなれます（[参考：株主総会マニュアル](https://www.smartround.com/public/articles/shareholderMeeting) ）
* 社長が「自身で起業した会社をNTTドコモに売却した経験」「米国のVentureCapital勤務経験」等このドメインにとても詳しいので、様々学べます。

---

### 採用ページ

* 一緒にサービスを作っていきたい方お待ちしてます！
* 技術以外の面でも色々魅力がある会社なので詳細は[Wantedlyもご覧ください！](https://www.wantedly.com/companies/company_4346433/projects)

