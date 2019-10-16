@snap[midpoint span-100]
### smartroundを支える技術
@snapend

---

### 初めに

* この資料は2019年10月時点の内容です
* まだサービス開発開始後1年未満で急成長中なので<br/>それを踏まえた上で現在とのDiffは脳内補完してください

---

### この資料で紹介すること

* 技術スタック
* smartroundのシステム特徴
* 技術選定の背景・理由

---

### サービスについて

@snap[west span-50]
@img[](assets/img/startup.png)
@img[](assets/img/investor.png)
@img[](assets/img/advisor.jpg)
@snapend

@snap[east span-50]
* スタートアップが資金調達するプロセスを効率化するサービスです
* スタートアップ・投資家・アドバイザー（士業）向けの3サービスを提供しています
* [サービスURLはこちらです](https://jp.smartround.com)
@snapend

---

### サービス使用技術

@snap[text-08]
* Frontend
  * 言語: Typescript / SCSS
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
  * Slack / Github / Zenhub
* Design
  * Figma / Zeplin
* DevOps
  * CircleCI
* Monitoring
  * TrackJs
@snapend

---

### smartroundのシステム特徴

* 1.UX/UIの追求
  <br/>先行サービスが日本では少ないため<br/>とにかくわかりやすいサービスにする必要がある
<br/>
<br/>
* 2.セキュリティ
  <br/>特に他社のデータを閲覧できるという点は<br/>SaaSとしては珍しいサービス特性

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

### フロントエンドその他特徴

@snap[west span-50]
@img[](/assets/img/feature-drag-and-drop.png)
@snapend

@snap[east span-50]
* UXを上げるためDrag and Drop APIなど積極的に利用
* 他にもWeb Pushやwebsocket等、UX向上のため様々チャレンジしています
@snapend

---

### コンポーネント設計

* サービス規模が大きく長期的な目線で開発していけるようにしたいと考えているため、コンポーネント設計についても意識しています。
* [（社内向け資料ですが）StoryBookも公開しているのでご参考ください](https://github.com/smartround/smartround-storybook) 

---

@snap[midpoint span-100]
### サーバサイドについて
@snapend

---

### サーバサイド概要

レイヤをしっかり分けている
 * 権限制御を複数レイヤで行うため
 * 3サービス同時展開のためコードのメンテナンス性の確保する必要があるため

---

### サーバサイドアーキテクチャ


TODO: 簡単な図を書く

---

@snap[midpoint span-100]
### インフラについて
@snapend

---

### インフラ

利用しているAWSサービスの一例です。

@snap[text-08]
* WebApp
  * ElasticBeanstalk / RDS / Elasticache
* Batch
  * Lambda
* WebsocketAPI
  * API Gateway / Lambda / DynamoDB 
* Build / Deploy
  * CodeBuild / CodePipeline
* Others
  * Route53
@snapend

@snap[text-07]
※ 今後の拡張に備えなるべく一般的な構成にすることを意識してます
@snapend

---

### 現在のチーム

* エンジニア3名、デザイナー1名という少数精鋭で進めています。
* やりたいことはたくさんあり、自身の力量が<br/>ダイレクトに反映されるやりがいのある仕事です💪

---

### その他魅力1

サービス開発スタート時から今に至るまで<br/>同じエンジニア・デザイナーがフルコミット

* 初期から一貫した思想でUI/UXやコードベースが<br/>作られてきました
* スタートアップあるあるの立ち上げ期の謎の負債は<br/>極めて少ないです 

---

### その他魅力2

* ベンチャーファイナンスに詳しくなれます💰
* 社長が「自身で起業した会社をNTTドコモに売却した経験」「米国のVentureCapital勤務経験」等このドメインにとても詳しいので、様々学べます。

---

### 採用ページ

一緒にサービスを作っていきたい方お待ちしてます！
[Wantedlyページ](https://www.wantedly.com/companies/company_4346433/projects)
