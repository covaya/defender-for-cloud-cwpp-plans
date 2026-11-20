# Microsoft Defender for Cloud ― CWPP プランと保護対象の一覧

- 調査日: 2026-11-19
- 出典: Microsoft 公式の**原文（英語版）**のみ。Microsoft Learn の `en-us` と、Azure の価格ページの `en-us`
- 脚注 `(*n)` は文末の URL 一覧（すべて原文のページ）に対応する

## この文書の読み方

- **原文版（1-A）**: 脚注のページに書かれている英語の表現をそのまま写している。コピーして、脚注のページでページ内検索（Ctrl+F）すれば該当箇所に飛べる。
- **翻訳版（1-B）**: 原文版を日本語に訳したもの。行の並びと、セルの中の改行の順番は原文版と同じなので、上から何番目かで原文と突き合わせられる。
- **翻訳はこの文書のために付けた訳で、Microsoft の日本語版ページの表現ではない。** 日本語版ページはほとんどが機械翻訳で、プラン名の訳がページごとに違い、誤訳も 1 件あった（Amazon RDS の機密データ検出を「計画されています」と訳している）。そのため照合には使わない。
- 原文で検索して見つからないときは、語句の前半だけで検索する。ページ上ではリンクや改行で語句が区切られていることがある。
- **「提供状態（Azure）」の列は、「主な機能」の列と同じ順番で 1 行ずつ対応している。** 書き方は次の 4 通り。
  - `GA: 〇〇 (*n)`: 脚注のページが、その機能を GA（一般提供）と明記している。`〇〇` はそのページでの機能名（原文）で、検索に使える。概要ページとサポート表で機能名が違うことがあるため、こちらで対応づけている。
  - `プランは GA: 〇〇 (*n)`: プランとしては GA と明記されているが、機能ごとの提供状態は公式ページに書かれていない。「同上」は上の行と同じという意味。
  - `記載なし`: 読んだ公式ページに、その機能の提供状態が書かれていない。プレビューという意味ではない。
  - `―`: 機能ではない行（説明文や内訳）。
- 提供状態は Azure 上のもの。AWS / GCP での状態は 3 節を見る。

## 1-A. プラン・保護対象・主な機能（原文版）

| プラン | 保護対象 | 主な機能 | 提供状態（Azure） | 課金の数量単位 | 価格（Japan East・JPY） | 数量（入力用） |
|---|---|---|---|---|---|---|
| Defender for Servers Plan 1 (P1) (*2) | protects Windows and Linux machines in multicloud environments (*2) | Defender for Endpoint EDR<br>Attack surface reduction<br>Next-generation protection<br>Integrated alerts and incidents<br>Software inventory discovery<br>Regulatory compliance assessment<br>Vulnerability scanning (agent-based)<br>(*2) | GA: Microsoft Defender for Endpoint integration (*19)<br>記載なし<br>記載なし<br>記載なし<br>記載なし<br>GA: Compliance standards (*19)<br>GA: VM vulnerability scanning - Microsoft Defender for Endpoint sensor (*19) | /server/month (*1) | ¥776.214/server/month (*1) |  |
| Defender for Servers Plan 2 (P2) (*2) | protects Windows and Linux machines in multicloud environments (*2) | provides the same features as Plan 1 and other capabilities<br>Vulnerability scanning (agentless)<br>Malware scanning (agentless)<br>Machine secrets scanning (agentless)<br>File integrity monitoring<br>Just-in-time virtual machine access<br>Defender for DNS alerts<br>Threat detection (Azure network layer)<br>OS system updates<br>Defender for Vulnerability Management premium features<br>Network map<br>Free data ingestion (500 MB)<br>(*2) | ―<br>GA: Virtual Machines (VM) vulnerability scanning-agentless (*19)<br>GA: Agentless malware scanning (*19)<br>GA: Agentless secret scanning (*19)<br>GA: File integrity monitoring (*19)<br>GA: Just-in-time VM access (*19)<br>プランは GA: Defender for Domain Name System (DNS) (*4)<br>記載なし<br>GA: System updates and patches (*19)<br>記載なし<br>記載なし<br>― | /server/month (*1) | ¥2,310.159/server/month (*1) |  |
| Defender for Containers (*5) | Kubernetes clusters, nodes, workloads, registries, images (*5)<br>Azure Kubernetes Service (AKS), Amazon Elastic Kubernetes Service (EKS), and Google Kubernetes Engine (GKE) (*3)<br>Azure Container Registry (ACR), Amazon Elastic Container Registry (ECR), Google Artifact Registry (GAR), Google Container Registry (GCR), Docker Hub, and JFrog Artifactory (*3) | Security posture management<br>Vulnerability assessment<br>Run-time threat protection<br>Software supply chain protection<br>Deployment & monitoring<br>(*5) | GA: Agentless discovery for Kubernetes、Control plane hardening (*18)<br>GA: Container registry VA (*18)<br>GA: Workload detection (*18)。一部 Preview: Binary drift blocking (*3)、Response actions in XDR (*18)<br>GA: Gated deployment (*18)<br>記載なし | /vCore/month<br>per image digest<br>(*1) | ¥1,086.9294/vCore/month<br>¥45.887 per image digest<br>(*1) |  |
| Defender for Storage (*6) | Azure Blob Storage<br>Azure Files<br>Azure Data Lake Storage<br>(*6) | Activity monitoring<br>Sensitive data threat detection<br>Malware scanning<br>Event-driven response<br>(*6) | GA: Activity monitoring (security alerts) (*4)<br>GA: Sensitive data threat detection (Sensitive Data Discovery) (*4)<br>GA: Malware scanning (*4)<br>記載なし | per storage account/month<br>for every 1 million transactions that exceed the threshold<br>/GB of data scanned<br>(*1) | ¥1,548 per storage account/month<br>¥23.6080 for every 1 million transactions that exceed the threshold<br>¥23.735/GB of data scanned<br>(*1) |  |
| Defender for Azure SQL Databases (*8) | Azure SQL single databases and elastic pools<br>Azure SQL managed instances<br>Azure Synapse Analytics (formerly Azure SQL Data Warehouse) dedicated SQL pools<br>(*8) | Vulnerability assessment<br>Threat protection<br>Potential SQL injection attacks<br>Anomalous database access and query patterns<br>Suspicious database activity<br>(*8) | GA: Vulnerability assessment Express and Classic configurations (*4)<br>GA: Advanced threat protection (*4)<br>―<br>―<br>― | /Instance/month (*1) | ¥2,373.451/Instance/month (*1) |  |
| Defender for SQL Servers on Machines (*7) | SQL Server instances running on Azure VMs, AWS EC2 instances (via Arc), and GCP Compute Engine instances (via Arc) (*3)<br>SQL servers that run on virtual machines or physical servers (*7) | SQL threat detection and vulnerability assessment on multicloud machines (*3) | プランは GA: Defender for SQL servers on machines (*4) | /Instance/month<br>/Instance/vCore/month<br>(*1) | ¥2,373.451/Instance/month<br>¥1,732.619/Instance/vCore/month<br>(*1) |  |
| Defender for Open-Source Relational Databases (*9) | Azure Database for PostgreSQL<br>Azure Database for MySQL<br>Flexible Server: All pricing tiers<br>Amazon RDS<br>Aurora PostgreSQL<br>Aurora MySQL<br>MariaDB<br>(*9) | Anomalous database access and query patterns<br>Suspicious database activity<br>the plan also includes sensitive data discovery<br>(*9) | プランは GA: Defender for Open-Source Relational Databases (*4)<br>同上<br>AWS RDS で GA (*17)。サポート表では AWS は Preview (*3) | /Instance/month (*1) | ¥2,373.451/Instance/month<br>¥2,373.4564/Instance/month (Outside Azure)<br>(*1) |  |
| Defender for Azure Cosmos DB (*10) | Azure Cosmos DB for NoSQL (*10) | Potential SQL injection attacks<br>Anomalous database access patterns<br>Suspicious database activity<br>(*10) | プランは GA: Defender for Azure Cosmos DB (*4)。別の表にプレビューの注釈あり（6 節）<br>同上<br>同上 | per 100 RUs/month (*1) | ¥138.6095 per 100 RUs/month (*1) |  |
| Defender for App Service (*11) | identify attacks targeting applications running over App Service<br>An App Service plan on any App Service tier<br>(*11) | Pre-attack threats<br>Initial access threats<br>Execution threats<br>Dangling DNS detection<br>(*11) | プランは GA: Defender for App Service (*4)<br>同上<br>同上<br>同上 | /Instance/month (*1) | ¥2,310.159/Instance/month (*1) |  |
| Defender for Key Vault (*12) | advanced threat protection for Azure Key Vault (*12) | detects unusual and potentially harmful attempts to access or exploit Key Vault accounts (*12) | GA: Release state (*12) | /Vault/month (*1) | ¥39.28/Vault/month (*1) |  |
| Defender for Resource Manager (*13) | automatically monitors the resource management operations in your organization (*13) | Suspicious resource management operations<br>Use of exploitation toolkits<br>Lateral movement<br>(*13) | プランは GA: Defender for Resource Manager (*4)<br>同上<br>同上 | /Subscription/month (*1) | ¥797.01/Subscription/month (*1) |  |
| Defender for APIs (*15) | currently provides security for APIs published in Azure API Management (*15) | Inventory<br>Security findings<br>Security posture<br>API data classification<br>Threat detection<br>Defender CSPM integration<br>Azure API Management integration<br>SIEM integration<br>(*15) | プランは GA: Defender for APIs (*4)<br>同上<br>同上<br>同上<br>同上<br>同上<br>同上<br>同上 | per subscription/month up to 1 million API calls<br>per API call<br>(*1) | ¥31,649.17 per subscription/month up to 1 million API calls<br>¥0.03165 per API call<br>(*1) |  |
| Defender for AI Services (*16) | Azure OpenAI supported models<br>Azure AI Model Inference service supported models<br>currently supports text tokens only<br>(*16) | Activity monitoring (security alerts)<br>Prompt evidence (security alerts)<br>data leakage, data poisoning, jailbreak, credential theft<br>(*16) | GA: Activity monitoring (security alerts) (*16)<br>GA: Prompt evidence (security alerts) (*16)<br>― | /1K tokens/month (*1) | ¥0.1266/1K tokens/month (*1) |  |
| Defender for DNS (*14) | all Azure resources that use Azure DNS's Azure-provided name resolution capability (*14) | Data exfiltration<br>Malware<br>DNS attacks<br>Communication with domains used for malicious activities<br>(*14) | プランは GA: Defender for Domain Name System (DNS) (*4)。新規には選べない (*14)<br>同上<br>同上<br>同上 | ―（価格ページに行がない） | ― |  |

## 1-B. プラン・保護対象・主な機能（翻訳版）

行の並びとセル内の順番は 1-A と同じ。脚注も 1-A と同じ原文のページを指す。

| プラン | 保護対象 | 主な機能 | 提供状態（Azure） | 課金の数量単位 | 価格（Japan East・JPY） | 数量（入力用） |
|---|---|---|---|---|---|---|
| Defender for Servers プラン 1 (P1) (*2) | マルチクラウド環境の Windows と Linux のマシンを保護する (*2) | Defender for Endpoint の EDR<br>攻撃面の縮小<br>次世代の保護<br>アラートとインシデントの統合<br>ソフトウェア インベントリの検出<br>規制コンプライアンスの評価<br>脆弱性スキャン（エージェント ベース）<br>(*2) | GA: Microsoft Defender for Endpoint integration (*19)<br>記載なし<br>記載なし<br>記載なし<br>記載なし<br>GA: Compliance standards (*19)<br>GA: VM vulnerability scanning - Microsoft Defender for Endpoint sensor (*19) | サーバーの台数（月あたり）(*1) | ¥776.214（サーバー 1 台・月）(*1) |  |
| Defender for Servers プラン 2 (P2) (*2) | マルチクラウド環境の Windows と Linux のマシンを保護する (*2) | プラン 1 と同じ機能に加えて、ほかの機能も提供する<br>脆弱性スキャン（エージェントレス）<br>マルウェア スキャン（エージェントレス）<br>マシンのシークレット スキャン（エージェントレス）<br>ファイル整合性監視<br>Just-In-Time の仮想マシン アクセス<br>Defender for DNS のアラート<br>脅威検出（Azure ネットワーク層）<br>OS のシステム更新<br>Defender 脆弱性の管理のプレミアム機能<br>ネットワーク マップ<br>無料のデータ取り込み（500 MB）<br>(*2) | ―<br>GA: Virtual Machines (VM) vulnerability scanning-agentless (*19)<br>GA: Agentless malware scanning (*19)<br>GA: Agentless secret scanning (*19)<br>GA: File integrity monitoring (*19)<br>GA: Just-in-time VM access (*19)<br>プランは GA: Defender for Domain Name System (DNS) (*4)<br>記載なし<br>GA: System updates and patches (*19)<br>記載なし<br>記載なし<br>― | サーバーの台数（月あたり）(*1) | ¥2,310.159（サーバー 1 台・月）(*1) |  |
| Defender for Containers (*5) | Kubernetes のクラスター、ノード、ワークロード、レジストリ、イメージ (*5)<br>Azure Kubernetes Service (AKS)、Amazon Elastic Kubernetes Service (EKS)、Google Kubernetes Engine (GKE) (*3)<br>Azure Container Registry (ACR)、Amazon Elastic Container Registry (ECR)、Google Artifact Registry (GAR)、Google Container Registry (GCR)、Docker Hub、JFrog Artifactory (*3) | セキュリティ態勢の管理<br>脆弱性評価<br>実行時の脅威保護<br>ソフトウェア サプライ チェーンの保護<br>デプロイと監視<br>(*5) | GA: Agentless discovery for Kubernetes、Control plane hardening (*18)<br>GA: Container registry VA (*18)<br>GA: Workload detection (*18)。一部 Preview: Binary drift blocking (*3)、Response actions in XDR (*18)<br>GA: Gated deployment (*18)<br>記載なし | ワーカー ノードの vCore 数（月あたり）<br>無料枠を超えたスキャンは、イメージ ダイジェストの数<br>(*1) | ¥1,086.9294（vCore 1 つ・月）<br>¥45.887（イメージ ダイジェスト 1 つ）<br>(*1) |  |
| Defender for Storage (*6) | Azure Blob Storage<br>Azure Files<br>Azure Data Lake Storage<br>(*6) | アクティビティの監視<br>機密データの脅威検出<br>マルウェア スキャン<br>イベント駆動の対応<br>(*6) | GA: Activity monitoring (security alerts) (*4)<br>GA: Sensitive data threat detection (Sensitive Data Discovery) (*4)<br>GA: Malware scanning (*4)<br>記載なし | ストレージ アカウントの数（月あたり）<br>しきい値を超えたトランザクション 100 万件ごと<br>マルウェア スキャンは、スキャンしたデータの GB 数<br>(*1) | ¥1,548（ストレージ アカウント 1 つ・月）<br>¥23.6080（超過トランザクション 100 万件）<br>¥23.735（スキャンした 1 GB）<br>(*1) |  |
| Defender for Azure SQL Databases (*8) | Azure SQL の単一データベースとエラスティック プール<br>Azure SQL マネージド インスタンス<br>Azure Synapse Analytics（旧 Azure SQL Data Warehouse）の専用 SQL プール<br>(*8) | 脆弱性評価<br>脅威保護<br>SQL インジェクション攻撃の可能性<br>異常なデータベース アクセスとクエリのパターン<br>不審なデータベース アクティビティ<br>(*8) | GA: Vulnerability assessment Express and Classic configurations (*4)<br>GA: Advanced threat protection (*4)<br>―<br>―<br>― | インスタンスの数（月あたり）(*1) | ¥2,373.451（インスタンス 1 つ・月）(*1) |  |
| Defender for SQL Servers on Machines (*7) | Azure VM、AWS EC2 インスタンス（Arc 経由）、GCP Compute Engine インスタンス（Arc 経由）で動く SQL Server インスタンス (*3)<br>仮想マシンまたは物理サーバーで動く SQL サーバー (*7) | マルチクラウドのマシンでの SQL の脅威検出と脆弱性評価 (*3) | プランは GA: Defender for SQL servers on machines (*4) | Azure 内または Arc 対応: インスタンスの数（月あたり）<br>Azure 外で Arc 非対応: インスタンスの vCore 数（月あたり）<br>(*1) | ¥2,373.451（インスタンス 1 つ・月）<br>¥1,732.619（インスタンスの vCore 1 つ・月）<br>(*1) |  |
| Defender for Open-Source Relational Databases (*9) | Azure Database for PostgreSQL<br>Azure Database for MySQL<br>フレキシブル サーバー: すべての価格レベル<br>Amazon RDS<br>Aurora PostgreSQL<br>Aurora MySQL<br>MariaDB<br>(*9) | 異常なデータベース アクセスとクエリのパターン<br>不審なデータベース アクティビティ<br>プランには機密データの検出も含まれる（Amazon RDS の場合）<br>(*9) | プランは GA: Defender for Open-Source Relational Databases (*4)<br>同上<br>AWS RDS で GA (*17)。サポート表では AWS は Preview (*3) | インスタンスの数（月あたり）(*1) | ¥2,373.451（インスタンス 1 つ・月）<br>¥2,373.4564（Azure 外のインスタンス 1 つ・月）<br>(*1) |  |
| Defender for Azure Cosmos DB (*10) | Azure Cosmos DB for NoSQL (*10) | SQL インジェクション攻撃の可能性<br>異常なデータベース アクセスのパターン<br>不審なデータベース アクティビティ<br>(*10) | プランは GA: Defender for Azure Cosmos DB (*4)。別の表にプレビューの注釈あり（6 節）<br>同上<br>同上 | 100 RU ごと（月あたり）(*1) | ¥138.6095（100 RU・月）(*1) |  |
| Defender for App Service (*11) | App Service で動くアプリケーションを狙った攻撃を特定する<br>どのレベルの App Service プランでもよい<br>(*11) | 攻撃前の脅威<br>初期アクセスの脅威<br>実行の脅威<br>ダングリング DNS（宙に浮いた DNS エントリ）の検出<br>(*11) | プランは GA: Defender for App Service (*4)<br>同上<br>同上<br>同上 | インスタンスの数（月あたり）(*1) | ¥2,310.159（インスタンス 1 つ・月）(*1) |  |
| Defender for Key Vault (*12) | Azure Key Vault 向けの高度な脅威保護 (*12) | Key Vault アカウントへの、通常と異なる有害なおそれのあるアクセスや悪用の試みを検出する (*12) | GA: Release state (*12) | vault（キー コンテナー）の数（月あたり）(*1) | ¥39.28（vault 1 つ・月）(*1) |  |
| Defender for Resource Manager (*13) | 組織内のリソース管理操作を自動的に監視する (*13) | 不審なリソース管理操作<br>悪用ツールキットの使用<br>横方向の移動（ラテラル ムーブメント）<br>(*13) | プランは GA: Defender for Resource Manager (*4)<br>同上<br>同上 | サブスクリプションの数（月あたり）(*1) | ¥797.01（サブスクリプション 1 つ・月）(*1) |  |
| Defender for APIs (*15) | 現在は、Azure API Management で公開された API のセキュリティを提供する (*15) | インベントリ<br>セキュリティの検出結果<br>セキュリティ態勢<br>API データの分類<br>脅威検出<br>Defender CSPM との統合<br>Azure API Management との統合<br>SIEM との統合<br>(*15) | プランは GA: Defender for APIs (*4)<br>同上<br>同上<br>同上<br>同上<br>同上<br>同上<br>同上 | サブスクリプションごとの月額（Plan 1 は API 呼び出し 100 万回まで）<br>枠を超えた API 呼び出しの回数<br>(*1) | ¥31,649.17（Plan 1。サブスクリプション 1 つ・月、100 万回まで）<br>¥0.03165（Plan 1 の超過 1 回）<br>(*1) |  |
| Defender for AI Services (*16) | Azure OpenAI の対応モデル<br>Azure AI Model Inference サービスの対応モデル<br>現在はテキストのトークンだけに対応<br>(*16) | アクティビティの監視（セキュリティ アラート）<br>プロンプトの証拠（セキュリティ アラート）<br>データ漏えい、データ ポイズニング、ジェイルブレイク、資格情報の窃取<br>(*16) | GA: Activity monitoring (security alerts) (*16)<br>GA: Prompt evidence (security alerts) (*16)<br>― | 1,000 トークンごと（月あたり）(*1) | ¥0.1266（1,000 トークン・月）(*1) |  |
| Defender for DNS (*14) | Azure DNS の Azure 提供の名前解決機能を使うすべての Azure リソース (*14) | データの持ち出し<br>マルウェア<br>DNS 攻撃<br>悪意のある活動に使われるドメインとの通信<br>(*14) | プランは GA: Defender for Domain Name System (DNS) (*4)。新規には選べない (*14)<br>同上<br>同上<br>同上 | ―（価格ページに行がない） | ― |  |

## 2. 表の補足

| 内容（翻訳） | 原文（検索できる表現） | 脚注 |
|---|---|---|
| Defender for DNS は新規には選べず、新しいサブスクリプションでは Servers プラン 2 に含まれる | For new subscriptions, alerts about suspicious DNS activity are included as part of Defender for Servers Plan 2 (P2) | (*14) |
| SQL 系・オープンソース・Cosmos DB の 4 つは Defender for Databases を構成し、別々に価格が決まる | Each of these database protection plans is priced separately | (*7) |
| Cosmos DB で対象外の API | Azure Cosmos DB for Apache Cassandra<br>Azure Cosmos DB for MongoDB<br>Azure Cosmos DB for Table<br>Azure Cosmos DB for Apache Gremlin | (*10) |
| オープンソース データベースは Arc 対応マシンでは使えない | It isn't supported on Azure Arc-enabled machines | (*9) |
| マルウェア スキャンは設定で有効にする機能で、スキャンした GB あたりで課金される | Malware scanning is a configurable feature in the new Defender for Storage plan that is priced per GB scanned | (*6) |
| 機密データの脅威検出は追加料金なしで有効・無効を切り替えられる | You can enable or disable it at no additional cost | (*6) |
| AWS / GCP のマシンは Azure Arc での接続が必要 | AWS and GCP machines require | (*3) |
| Foundry の AI エージェントの脅威保護はプレビュー | Threat protection for AI agents (Preview) | (*17) |

## 3. クラウドごとの提供状況

出典は (*3) の表「Plan availability by cloud」。プラン名と値は原文のまま。値の意味は、GA が一般提供、Preview がプレビュー、Not supported が非対応。

| プラン | Azure | AWS | GCP |
|---|---|---|---|
| Defender for Servers (Plan 1 and Plan 2) | GA | GA | GA |
| Defender for Containers | GA | GA | GA |
| Defender for SQL Servers on Machines | GA | GA | GA |
| Defender for Open-Source Relational Databases | GA | Preview | Not supported |
| Defender for Azure SQL Databases | GA | Not supported | Not supported |
| Defender for Azure Cosmos DB | GA | Not supported | Not supported |
| Defender for Storage | GA | Not supported | Not supported |
| Defender for Key Vault | GA | Not supported | Not supported |
| Defender for Resource Manager | GA | Not supported | Not supported |
| Defender for DNS | GA | Not supported | Not supported |
| Defender for App Service | GA | Not supported | Not supported |
| Defender for APIs | GA | Not supported | Not supported |
| Defender for AI Services | GA | Not supported | Not supported |

## 4. 課金の数量単位と価格

課金額は「数量 × 単価」で決まる。この節は、プランごとに何を数えればよいかをまとめている。

- 出典は価格ページ (*1) の「Plan-Based Pricing」タブ。ページを開いた直後は「DWU Pricing」タブが表示されるので、切り替えてから検索する。
- 「原文」の列は、ブラウザーで開いた画面の文字をそのまま写している。
- **価格は Japan East（東日本）リージョンで固定している。** 2026-11-20 に、ページの Region を「Japan East」、表示を月額（Month）にして読み取った。通貨は USD と JPY（Japan – Yen）の 2 通りを載せている。
- Japan East の USD の価格は、ページを開いた直後の既定のリージョン（Central US）の価格と、全行で同じ値だった。
- JPY の価格は、ページの説明によると USD から為替レートで換算した見積もりで、レートは月ごとに変わる。契約によっても変わるので、見積もりの前にページで値を確かめる。
- この節に出てくる金額（4-2、4-4 を含む）は、すべて Japan East のもの。

### 4-1. 数量単位と価格

| プラン（原文の行名） | 数える数量（翻訳） | 原文（検索できる表現） | 価格（Japan East・USD） | 価格（Japan East・JPY） | 数量（入力用） |
|---|---|---|---|---|---|
| Microsoft Defender for Servers Plan 1 | サーバーの台数 | /server/month | $4.906/server/month | ¥776.214/server/month |  |
| Microsoft Defender for Servers Plan 2 | サーバーの台数 | /server/month | $14.60/server/month | ¥2,310.159/server/month |  |
| Microsoft Defender for Containers | Kubernetes のワーカー ノードの vCore 数 | /vCore/month | $6.8693/vCore/month | ¥1,086.9294/vCore/month |  |
| Microsoft Defender for SQL on Azure-connected databases と Microsoft Defender for SQL Servers on machines (in Azure, or Arc-enabled) | インスタンスの数 | /Instance/month | $15/Instance/month | ¥2,373.451/Instance/month |  |
| Microsoft Defender for SQL Servers on machines (outside Azure and not Arc-enabled) | インスタンスの vCore 数 | /Instance/vCore/month | $10.95/Instance/vCore/month | ¥1,732.619/Instance/vCore/month |  |
| Microsoft Defender for MySQL | インスタンスの数 | /Instance/month | $15/Instance/month | ¥2,373.451/Instance/month |  |
| Microsoft Defender for PostgreSQL | インスタンスの数 | /Instance/month | $15/Instance/month | ¥2,373.451/Instance/month |  |
| Microsoft Defender for Open-Source Relational Databases (Outside Azure) | インスタンスの数 | /Instance/month | $15.0001/Instance/month | ¥2,373.4564/Instance/month |  |
| Microsoft Defender for Azure Cosmos DB | RU（要求ユニット）を 100 単位で | per 100 RUs/month | $0.8760 per 100 RUs/month | ¥138.6095 per 100 RUs/month |  |
| Microsoft Defender for Storage | ストレージ アカウントの数 | per storage account/month | $10 per storage account/month | ¥1,548 per storage account/month |  |
| Malware Scanning (add-on to Defender for Storage) | スキャンしたデータの GB 数 | /GB of data scanned | $0.15/GB of data scanned | ¥23.735/GB of data scanned |  |
| Microsoft Defender for AI Services | トークン数を 1,000 単位で | /1K tokens/month | $0.0008/1K tokens/month | ¥0.1266/1K tokens/month |  |
| Microsoft Defender for APIs Plan 1 | サブスクリプションの数（API 呼び出し 100 万回まで） | per subscription/month up to 1 million API calls | $200.02 | ¥31,649.17 |  |
| Microsoft Defender for APIs Plan 2 | 同上（500 万回まで） | per subscription/month up to 5 million API calls | $700.00 | ¥110,760.53 |  |
| Microsoft Defender for APIs Plan 3 | 同上（5,000 万回まで） | per subscription/month up to 50 million API calls | $4,999.99 | ¥791,148.27 |  |
| Microsoft Defender for APIs Plan 4 | 同上（1 億回まで） | per subscription/month up to 100 million API calls | $6,999.97 | ¥1,107,605.27 |  |
| Microsoft Defender for APIs Plan 5 | 同上（10 億回まで） | per subscription/month up to 1 billion API calls | $50,000.04 | ¥7,911,505.76 |  |
| Microsoft Defender for App Service | インスタンスの数 | /Instance/month | $14.60/Instance/month | ¥2,310.159/Instance/month |  |
| Microsoft Defender for Key Vault | vault（キー コンテナー）の数 | /Vault/month | $0.25/Vault/month | ¥39.28/Vault/month |  |
| Microsoft Defender for Resource Manager | サブスクリプションの数 | /Subscription/month | $5.04/Subscription/month | ¥797.01/Subscription/month |  |
| Defender for DNS | 価格ページに行がない | ― | ― | ― |  |

### 4-2. 追加で数える数量（超過分・無料枠）

| プラン | 数える数量（翻訳） | 原文（検索できる表現） |
|---|---|---|
| Defender for Containers | 課金対象の vCore 1 つにつき、月 20 回の脆弱性評価が無料 | This price includes 20 free monthly vulnerability assessments |
| Defender for Containers | 無料枠を超えたスキャンは、イメージ ダイジェスト 1 つごとに $0.29（JPY 表示では ¥45.887） | Every subsequent scan will be charged at $0.29 per image digest |
| Defender for Storage | 月 7,300 万トランザクションを超えた分は、100 万件ごとに $0.1492（JPY 表示では ¥23.6080） | Storage accounts that exceed 73 million monthly transactions will be charged $0.1492 for every 1 million transactions |
| マルウェア スキャン | 最初の 30 日間も無料にならず、初日から課金 | will be charged from the first day |
| Defender for Azure Cosmos DB | サーバーレスのアカウントは、RU の合計に係数 0.00003125 を掛けて換算する | using a conversion factor of 0.00003125 |
| Defender for APIs | 枠を超えた API 呼び出し 1 回ごとに超過課金（Plan 1 は $0.0002。JPY 表示では Plan 1 から順に ¥0.03165、¥0.02216、¥0.01583、¥0.01108、¥0.00792） | Plan 1: $0.0002 per API call, Plan 2: $0.00014, Plan 3: $0.0001, Plan 4: $0.00007, Plan 5: $0.00005 per API call |
| Defender for AI Services | 試用は 30 日または 750 億トークンの早いほうまで | capped at 30 days or 75 billion tokens, whichever comes first |
| 全プラン共通 | 最初の 30 日間は無料 | free for the first 30 days |

### 4-3. 数え方の補足

| 内容（翻訳） | 原文（検索できる表現） | 脚注 |
|---|---|---|
| Servers はサーバーの稼働時間で数える（サーバー・時間あたりの課金） | billed per server-hour | (*17) |
| App Service は、すべての App Service プランのコンピュート インスタンスの合計で数える | total compute instances across all App Service plan tiers | (*11) |
| Storage は、保護するストレージ アカウントの数で決まる | based on the number of storage accounts you protect | (*6) |
| 価格の表示は時間単位と月単位を切り替えられる | Display pricing by: | (*1) |

### 4-4. 別の料金体系（DWU）

価格ページを開いた直後のタブ「DWU Pricing」には、プラン別とは別の単位が載っている。

| 内容（翻訳） | 原文（検索できる表現） | 表示されていた価格 |
|---|---|---|
| Defender Workload Unit（DWU）という共通の単位 | Defender Workload Unit | $5.00/month（JPY 表示では ¥791.12/month） |
| サーバー、データベース、コンテナー、ストレージ、CSPM、AI、API、App Service、Key Vault、Resource Manager のワークロードが対象 | Defender Workload Unit covers workloads in | ― |

各プランの数量が何 DWU に換算されるかは、価格ページには書かれておらず、確かめていない。

## 5. 最近の変更（プラン選びに関わるもの）

出典はすべてリリース ノート (*17)。原文の列はリリース ノートの見出し。

| 日付 | 内容（翻訳） | 原文（検索できる表現） |
|---|---|---|
| 2026-09-30 告知（2026-11-01 発効） | Servers の課金の変更。プラン 1 でクライアント端末が課金対象から外れ、プラン 1 / 2 とも課金対象のサーバーの数え方が細かくなる | Upcoming billing updates for Defender for Servers |
| 2026-07-05 | 廃止済みの 5 プランを API からも新規に有効化できなくした。既存の利用者はそのまま。終了日は未発表 | Plan enablement API now blocks onboarding to five deprecated Defender plans |
| 2026-06-01 | オープンソース データベースが AWS RDS で一般提供、課金開始 | General availability of Microsoft Defender for Open-Source Relational Databases on AWS RDS |
| 2026-07-01 | Containers の新機能が一般提供 | New container security capabilities are now generally available |
| 2026-02-02 | Foundry の AI エージェントの脅威保護がプレビュー | Threat protection for AI agents (Preview) |

廃止済みの 5 プランと移行先 (*17)。左 2 列が原文、右 2 列が翻訳。

| Deprecated plan | Migration path | 廃止済みのプラン（翻訳） | 移行先（翻訳） |
|---|---|---|---|
| Microsoft Defender for Azure Kubernetes Service | Defender for Containers | Azure Kubernetes Service 向けの Defender | Defender for Containers |
| Microsoft Defender for Azure Container Registry | Defender for Containers | Azure Container Registry 向けの Defender | Defender for Containers |
| Microsoft Defender for Key Vault | Fixed pricing model | Defender for Key Vault（旧料金体系） | 固定料金モデル |
| Microsoft Defender for DNS | Defender for Servers | Defender for DNS | Defender for Servers |
| Microsoft Defender for Azure Resource Manager | Fixed pricing model | Defender for Resource Manager（旧料金体系） | 固定料金モデル |

Key Vault と Resource Manager の「（旧料金体系）」は、移行先が固定料金モデルであることからの読み取りで、原文にこの語はない。

## 6. 公式ページ間の食い違い

1. **Open-Source Relational Databases の AWS 対応**: サポート表 (*3) は `Preview`。リリース ノート (*17) は 2026-06-01 に AWS RDS で GA としている。どちらが正しいかは確かめられていない。
2. **データベース系のプレビュー表記**: (*4) の表「Security benefits for Azure services」は、Azure Cosmos DB、Azure Database for MySQL、Azure Database for PostgreSQL に `These features are currently supported in preview` の注釈を付けている。同じページの「Cloud support」の表と (*3) は、どれも Azure で GA としている。

## 7. 今回確かめていないこと

- Japan East 以外のリージョン（Japan West など）の価格。載せた価格は Japan East だけ
- DWU の価格（$5.00/month）が Japan East の USD 表示でも同じかどうか。USD は既定のリージョンで、JPY は Japan East で読み取った
- DWU（Defender Workload Unit）への換算。各プランの数量が何 DWU になるか、プラン別の料金とどちらが適用されるか
- 「インスタンス」「サーバー」が具体的に何を 1 つと数えるかの定義（たとえば Azure SQL で論理サーバー単位かデータベース単位か）。価格ページには単位名しか書かれていない
- Defender for SQL Servers on Machines の専用の概要ページ（`defender-for-sql-servers-introduction`）。この行は (*3) と (*7) の記述だけで書いている
- 日本のリージョンでの提供状況
- 「提供状態」が「記載なし」「プランは GA」の機能の、機能ごとの提供状態。公式ページに機能単位の記載が見つからなかったもので、プレビューでないと確かめたわけではない
- アラート単位のプレビュー。アラートの一覧には、名前に (Preview) が付いた個別のアラートがある（AI Services で 2 件を確認）。ほかのプランのアラート一覧は調べていない
- 価格ページ以外のページをブラウザーで開いたときの見え方。語句は取得したページ本文から写しており、実際の画面で 1 つずつ検索して確かめたわけではない（価格ページだけは画面の文字を写している）

## 脚注（照合用 URL・すべて原文）

| 脚注 | ページ | ms.date | URL |
|---|---|---|---|
| (*1) | Pricing（価格ページ）。「Plan-Based Pricing」タブに切り替え、Region で「Japan East」を選んで見る | ― | https://azure.microsoft.com/en-us/pricing/details/defender-for-cloud/ |
| (*2) | Overview of Defender for Servers | 2026-11-13 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-servers-overview |
| (*3) | Multicloud support matrix | 2026-09-11 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/multicloud-support-matrix |
| (*4) | Interoperability with Azure services, Azure clouds, and client operating systems | 2026-07-01 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/support-matrix-defender-for-cloud |
| (*5) | Introduction to Microsoft Defender for Containers | 2026-08-10 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-containers-introduction |
| (*6) | What is Microsoft Defender for Storage | 2026-06-28 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-storage-introduction |
| (*7) | Protect your Databases with Defender for Databases | 2026-07-03 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/tutorial-enable-databases-plan |
| (*8) | Benefits and Features of Defender for Azure SQL Databases | 2025-05-13 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-sql-introduction |
| (*9) | Overview of Defender for Open-Source Relational Databases | 2026-08-10 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-databases-introduction |
| (*10) | Overview of Defender for Azure Cosmos DB | 2024-12-24 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/concept-defender-for-cosmos |
| (*11) | Microsoft Defender for App Service - Benefits and Features | 2026-05-14 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-app-service-introduction |
| (*12) | Microsoft Defender for Key Vault - the benefits and features | 2025-08-20 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-key-vault-introduction |
| (*13) | Microsoft Defender for Resource Manager - Benefits and Features | 2026-04-19 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-resource-manager-introduction |
| (*14) | Microsoft Defender for DNS - the benefits and features | 2025-08-20 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-dns-introduction |
| (*15) | Overview of the Microsoft Defender for APIs plan | 2025-07-14 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-apis-introduction |
| (*16) | AI threat protection in Microsoft Defender for Cloud | 2026-05-19 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/ai-threat-protection |
| (*17) | What's New in Defender for Cloud Features（リリース ノート） | 2026-11-05 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/release-notes |
| (*18) | Containers support matrix in Defender for Cloud（コンテナーのサポート表。Azure のタブを見る） | 2026-06-02 | https://learn.microsoft.com/en-us/azure/defender-for-cloud/support-matrix-defender-for-containers |
| (*19) | Support for the Defender for Servers plan（Servers のサポート表。「Azure cloud support」の表を見る） | ― | https://learn.microsoft.com/en-us/azure/defender-for-cloud/support-matrix-defender-for-servers |