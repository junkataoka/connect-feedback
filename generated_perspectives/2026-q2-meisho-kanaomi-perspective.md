# Perspective: Meisho Kanaomi

**Updated:** 2026-05-17  
**Target Quarter:** FY26 Q4

---

## Keep doing ... (mandatory)

**Here's something I think Meisho does really well and hope Meisho keeps doing:**

Meisho consistently showed up as both the technical architect and the operational backbone of the Money Forward hackathon, which is a rare combination. On the technical side, Meisho explicitly owned overall architecture plus the MCP implementation ("全体的な構成を作るところと、主にはmcpを作る"), walked the team through the LLM-based evaluation pipeline, MCP agent design and API integration, and the OpenTelemetry + MLflow observability stack on Day 2, and shipped the practical glue (e.g., `.env` configs for Azure AI Foundry). On the operational side, Meisho created and owned the GitHub repo with formal Direct Owner accountability, assigned cross-role owners across SWE, DS, and TPM, ran the customer-facing logistics end-to-end (run-of-show, dinner planning, customer alignment checks like "お客様も日程に関して認識あっていますでしょうか？"), and closed the engagement with an explicit invitation to keep collaborating. That blend of **One Microsoft** orchestration — bridging Product, AI, Sales, and the external customer — with deep hands-on engineering is exactly the senior IC profile that ISE customer engagements rely on, and it's what made the Money Forward delivery land cleanly.

**Here's a suggestion for how Meisho could leverage this strength further:**

The hackathon playbook Meisho effectively invented in real time — run-of-show, repo bootstrap with default owner roles, customer-alignment checkpoints, licensing/infra risk-surfacing pattern — would be enormously valuable to ISE Japan as more customer hackathons come through. The tech blog instinct ("ISEテックブログ書くために見たくて") is already pointing in this direction. Packaging this as a reusable playbook (or even a short ADR + template repo) would mean the next engagement starts from a known baseline instead of being rebuilt from scratch, and would extend Meisho's impact past this single customer.

---

## Re-think ... (optional)

**Here's something Meisho may want to re-think:**

Looking across the email view, Meisho's execution-level decisions are very visible — repo classification, permission lifecycle changes, owner assignments — but there are almost no written decision narratives where Meisho proposes a direction, drives consensus, or broadcasts a final call. That likely reflects that the real conversations happen in Teams and meetings, which is healthy, but on cross-org engagements like Money Forward (and the Toyota-adjacent threads Meisho is part of), stakeholders who weren't in the room have a hard time staying aligned without a written artifact. This is less about communication style and more about creating durable decision memory for engagements that span multiple teams and weeks.

**Here's an example to consider for doing it another way:**

When a meaningful technical or scope decision lands — like the differentiation-from-chatbot push Meisho drove in the pre-alignment Loop meeting, or the licensing workaround for M365 Copilot — consider following up in the relevant Teams channel with a short "here's what we decided, here's why, here's what changes" post (or a 5-bullet ADR in the repo). Three bullets is plenty. This **Courage** of writing things down explicitly tends to surface disagreements early, gives async stakeholders a clean entry point, and makes Meisho's judgment visible to people who weren't in the meeting.

---

## Additional thoughts

**The thing I most value about working with Meisho is:**

What I value most is Meisho's blend of **Awareness** and **Curiosity** in how Meisho engages with both the customer and the team. The **Awareness** shows up in small but consequential moments — noticingお願いします"). The **Curiosity** shows up as genuine clarifying qucestions in open chat ("Docker → local開発用でしょうか？", "resource group → お客様のsubscriptionでしょうか？") and as a learning loop that closes — pulling the latest branch specifically to write the ISE tech blog, and explicitly framing the hackathon as "Agentに関して勉強する良い機会でして、大満足でした." It's a low-ego, high-context operating mode that's genuinely easy and productive to collaborate with.

**Here are some other thoughts I have that Meisho may want to consider:**

As more customer hackathons and engagements come Meisho's way, it may be worth periodically checking whether the operational load (repo permission edits, logistics, ad-hoc coordination) can be delegated or templated. Meisho's highest leverage clearly sits in architecture and hands-on engineering, and protecting that headspace will compound over time.

---

## Japanese translation (mandatory)

# パースペクティブ: Meisho Kanaomi

**更新日:** 2026-05-17  
**対象クォーター:** FY26 Q4

---

## 続けてほしいこと (必須)

**Meishoが非常に優れていて、ぜひ続けてほしいと思うことは:**

Meishoは、Money Forwardハッカソンにおいて、技術アーキテクトと運用面のバックボーンの両方を同時に担うという、なかなか難しいポジションを安定してこなしてくれました。技術面では、「全体的な構成を作るところと、主にはmcpを作る」と明言してアーキテクチャ全体とMCP実装を引き受け、Day 2ではLLMベースの評価パイプライン、MCPエージェントの設計とAPI統合、OpenTelemetry + MLflowによる可観測性スタックをチームに丁寧に説明し、Azure AI Foundry向けの `.env` 設定など実装の細部までしっかり押さえてくれました。運用面では、Direct OwnerとしてGitHubリポジトリを立ち上げてフォーマルなオーナーシップを引き受け、SWE / DS / TPMという複数ロールにオーナーを割り当て、顧客向けの当日進行（「9:45 お客様お出迎え / 10:00 ハッカソン開始…」）、ディナーや予算（100 USD/人）の調整、そして「お客様も日程に関して認識あっていますでしょうか？」と顧客側の認識合わせまで含めて最後まで一人で回しきり、最後は「また機会がありましたら積極的に協業お願いいたします」と次に繋がる形でクローズしてくれました。Product、AI、営業、外部のお客様まで橋渡しする**One Microsoft**としてのオーケストレーションと、ハンズオンのエンジニアリングがここまで同居しているのは、ISEのお客様エンゲージメントが本当に頼りにしているシニアICそのもので、Money Forwardのデリバリーがきれいに着地したのはこの組み合わせがあったからだと思います。

**この強みをさらに活かすための提案は:**

Meishoが今回のハッカソンで実質的に即興で組み上げた段取り — 当日進行、デフォルトのオーナー役割を入れたリポジトリ初期化、顧客との認識合わせのチェックポイント、ライセンス／インフラのリスクを事前に上げるパターン — は、これからISE Japanで顧客ハッカソンが増えていく中で、組織として非常に価値のある資産になります。「ISEテックブログ書くために見たくて」という言葉にもその方向性が出ています。これを再利用可能なプレイブック（あるいは短いADR + テンプレートリポジトリ）としてパッケージ化すれば、次のエンゲージメントは毎回ゼロから組み直すのではなく既知のベースラインから始められますし、Meishoのインパクトは今回のお客様1社を大きく超えて広がっていくはずです。

---

## 再考してほしいこと (任意)

**Meishoが再考した方がいいかもしれないことは:**

メールのデータを横断的に見ると、Meishoの実行レベルの判断 — リポジトリ分類、権限ライフサイクル、オーナー割り当て — は非常に可視化されていますが、Meisho自身が方向性を提案したり、合意を主導したり、最終的な決定を周知したりする「書かれた判断ナラティブ」がほとんど見えません。実際の議論はTeamsや会議で行われていることの裏返しで、そこ自体は健全なのですが、Money Forward（そしてMeishoが入っているToyota周辺のスレッド）のようなクロスオーガニゼーションのエンゲージメントでは、その場にいなかったステークホルダーが書かれた成果物なしに歩調を合わせるのは難しくなります。これはコミュニケーションのスタイルというよりも、複数チーム・複数週にまたがるエンゲージメントに「持続する意思決定の記憶」を作るかどうかの問題です。

**別のやり方を検討する例として:**

意味のある技術判断やスコープの判断が決まったタイミング — 例えばMeishoが事前認識合わせのLoopミーティングで推し進めた「既存チャットボットからの差別化」の方向付けや、M365 Copilotのライセンス制約に対する代替案 — のあとに、関連するTeamsチャネルに「決まったこと／その理由／何が変わるか」を3行でいいので投稿する、あるいはリポジトリに5行のADRを残す、という運用を検討してみてください。明文化するという**Courage**は、認識のズレを早めに表面化させ、非同期のステークホルダーに綺麗な入り口を提供し、その場にいなかった人にもMeishoの判断が見えるようになります。

---

## その他の所感

**Meishoと働く中で一番価値を感じることは:**

私が一番価値を感じているのは、Meishoがお客様にもチームにも向き合うときの**Awareness**と**Curiosity**の組み合わせです。**Awareness**は、小さいけれど効いてくる瞬間によく出ています — コミットする前にM365 Copilotのライセンス制約に気づいて代替案を提示する、進める前に顧客側のスケジュール認識を再確認する、チームメンバーの負荷を見て依頼先を組み替える（「じゅんさん色々忙しいと聞いたので、fumiさんにお願いします」）。**Curiosity**は、オープンチャットでの素直な確認の問い（「Docker → local開発用でしょうか？」「resource group → お客様のsubscriptionでしょうか？」）と、ちゃんとクローズする学習ループ（ISEテックブログのために最新ブランチを取りに行く、ハッカソンを「Agentに関して勉強する良い機会でして、大満足でした」と明言する）の両方に出ています。ローエゴで高コンテキストな働き方で、一緒に仕事をしていて本当に進めやすく、生産的です。

**Meishoが検討するとよいかもしれない、その他の考えとして:**

これから顧客ハッカソンやエンゲージメントがさらに増えていく中で、運用負荷（リポジトリの権限編集、ロジ周り、その場限りの調整）をどこまで委任・テンプレ化できるか、たまに棚卸ししてみる価値があると思います。Meishoの最大のレバレッジは明らかにアーキテクチャとハンズオンのエンジニアリングにあるので、そのヘッドスペースを守ることが長期的に効いてくるはずです。
