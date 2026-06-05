# Perspective: Akira

**Updated:** 2026-05-17 **Target Quarter:** FY26 Q4

---

## Keep doing ... (mandatory)

**Here's something I think Akira does really well and hope Akira keeps doing:**

Akira owned hard, cross-layer technical work end-to-end this quarter in Panasonic VLA engagement — unifying the DevContainer and Azure ML environments behind a shared Dockerfile, standing up the AML training pipeline skeleton with MLflow, and diagnosing the ~58 GB model re-upload problem with a clean architectural fix (decoupling registration into a separate pipeline step).

What stood out to me wasn't just the delivery; it was his instinct woven through it — explicitly designing the shared environment "so DS and SE can both use it," coordinating Panasonic engineers as peers rather than recipients of instruction, and making sure work crossed team boundaries cleanly.

**Here's a suggestion for how Akira could leverage this strength further:**

Akira is already operating as a co-DS lead informally; the next leverage step is making that visible earlier. When evaluating options like Push vs. Poll vs. Event Grid, Akira's option-tradeoff write-ups are decision-ready — posting that same structure proactively at the start of a new workstream (rather than after debate begins) would let Akira shape direction for the whole MS × Panasonic team, not just resolve it.

---

## Re-think ... (optional)

**Here's something Akira may want to re-think:**

On a few ML deliverables this quarter, evaluation criteria (how we'd know the model was "good enough") surfaced mid-execution rather than upfront — I saw this in the Robotics Game Plan thread around the >90% target. To be clear, this is a hard problem: with physical-hardware success rates and cross-embodiment transfer, **practicing awareness** of how much was genuinely unknowable at kickoff matters here, and tight sprint timing pushed all of us toward "start building, refine later."

**Here's an example to consider for doing it another way:**

What if the first deliverable in any ML workstream was a one-pager that just names the evaluation question — what we'd measure, the validation pipeline, and an honest "we don't know yet" list — before any pipeline code lands? Akira already drafts uncertainty openly ("please change and find best practice"); making that **courageous** framing the _first_ artifact, not a mid-sprint correction, would lock in alignment when it's cheapest.

---

## Additional thoughts

**The thing I most value about working with Akira is:**

The combination of technical depth and the **courage** to question how we work. Raising that MS was still over-directing — and that Panasonic owners should be driving the tasks — wasn't a comfortable thing to say, and Akira timed it with real care for team morale ("propose in final retro… saying it now may reduce motivation"). That's organizational-design thinking, and it's the kind of input that has shifted how I think about scaling this engagement.

**Here are some other thoughts I have that Akira may want to consider:**

As the ramp into adjacent domains continues (Isaac Sim being the recent example), the team would benefit if Akira's learning notes became shared artifacts — even a rough "assumptions I'm making about Isaac Sim" doc would turn an individual ramp into team enablement, which is exactly the One Microsoft amplification I'd love to see more of.

---

## Japanese translation (mandatory)

# パースペクティブ: Akira

**更新日:** 2026-05-17 **対象四半期:** FY26 Q4

---

## 続けてほしいこと (必須)

**Akiraが本当に得意で、これからも続けてほしいと思うこと:**

今四半期、Akiraはレイヤーをまたぐ難しい技術課題をエンドツーエンドでオーナーシップを 持って進めてくれました。DevContainerとAzure MLの環境を共有Dockerfileで統一し、 MLflowを組み込んだAML training pipelineの骨格を立ち上げ、約58GBのモデル再アップロードに 起因するパイプライン障害を診断したうえで、モデル登録を独立した軽量ステップに分離する という綺麗なアーキテクチャ修正を提案してくれました。私が特に印象的だったのはデリバリ そのものではなく、**One Microsoft** の発想が一貫していたこと —「DSとSEの両方が 使えるように」と意識して共有環境を設計し、Panasonic側エンジニアを指示を受ける側では なくピアとして巻き込み、チーム境界を越えた仕事をきれいに繋げてくれました。

**Akiraがこの強みをさらに活かすための提案:**

Akiraは既に非公式にco-architectとして動いていますが、次のレバレッジは「それを早い段階で 可視化すること」だと思います。Push vs. Poll vs. Event Gridのトレードオフ整理のような 書き出しはそのまま意思決定に使える品質なので、議論が始まってから出すのではなく、新しい ワークストリームの立ち上げ時点で自発的に同じ構造を投稿すれば、議論を収束させるだけで なく、MS × Panasonicチーム全体の方向性そのものをAkiraが形作れるはずです。

---

## 再考してみてほしいこと (任意)

**Akiraが少し見直してみるとよいかもしれないこと:**

今四半期のいくつかのML成果物では、評価基準(モデルが「十分良い」と判断する基準)が キックオフ時点ではなく実行の途中で出てきていたように感じました — Robotics Game Planの

> 90%目標まわりのやり取りで特に顕著でした。前提として、これは本質的に難しい問題で、
> 実機の成功率やcross-embodiment transferのような領域では、開始時点でどこまでが本当に
> 未知だったのかを**Awareness(認識)**として受け止めることが大切ですし、タイトな
> スプリントの中では「まず作って後から精緻化する」方向に皆が引っ張られがちでした。

**別のやり方として参考になりそうな例:**

ML系ワークストリームの最初の成果物を、評価の問いだけを書いた1枚紙にしてみるのは どうでしょう — 何を測るか、検証パイプライン、そして正直な「まだわからないこと」リスト を、パイプラインのコードが入る前にまとめる。Akiraは元々「please change and find best practice」のように不確実性をオープンに出せる人なので、その**Courage(勇気)**ある姿勢を スプリント途中の軌道修正ではなく _最初の成果物_ にすることで、最も安価なタイミングで アラインメントを固められると思います。

---

## その他の考え

**Akiraと一緒に働くうえで私が最も価値を感じていること:**

技術的な深さと、「働き方そのものを問い直す勇気」の組み合わせです。MS側が依然として 過剰に指示を出しているのではないか、Panasonic側のオーナーが主導すべきではないか — これを言うのは決して心地よいことではなかったはずですが、チームのモチベーションへの 配慮までしたうえで(「最終retroで提案する方がよさそう、今出すとモチベーションを 削ぐ可能性がある」)切り出してくれました。これは組織設計レベルの思考であり、私自身が このエンゲージメントをどうスケールさせるかを考え直すきっかけになっています。

**Akiraに考えてみてほしい、その他のこと:**

隣接領域への立ち上げが続いていく中で(直近ではIsaac Simがその例ですが)、Akiraの ラーニングノートが共有資産になるとチーム全体の助けになります。「Isaac Simについて自分が 置いている前提」のラフなドキュメントでも十分で、個人のramp upをチームのenablementに 変えられます — これこそ、もっと見たいOne Microsoftの増幅の形です。
