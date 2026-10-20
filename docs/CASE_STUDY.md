# Why I built Scope Pulse

[Deutsch](CASE_STUDY.de.md) · [Project](../README.md)

After working on publishing automation and short-video editing, I wanted a project that addressed the next question: what can I learn from the posts that have already gone out?

The difficulty is less about drawing a chart than about deciding what belongs in it. Two exports can contain cumulative numbers for the same post. An empty cell can mean “not available.” A newer post has had less time to collect interactions. Pulse keeps these distinctions visible.

## The choices behind the workflow

An import starts with a preview. The user can map unfamiliar headers, inspect the rows and see the issues before saving anything. Identical observations are skipped. Conflicting observations block the complete import, including when the database changes between preview and confirmation. Original CSV bytes remain private and unchanged.

Post identity, measurements and campaign assignment are kept separate. That makes it possible to correct an assignment without rewriting the imported file or losing earlier measurements. The selected cutoff determines which measurement belongs in an analysis.

The weighted interaction rate uses the same eligible posts in its numerator and denominator. For Instagram, the application counts likes, comments, shares and saves. For LinkedIn and X, it counts likes, comments and shares. These are the application's import rules, not a claim that every platform calculates its own rate this way.

The previous period has the same number of publication days. Measurement age and missing values remain visible because equal calendar periods do not make two groups of posts equivalent. Format medians are descriptive, and small groups are identified.

![Import blocked by a negative metric and an impossible capture date](../assets/pulse-import.jpg)

## Where the local model helps

The application supplies computed findings, supporting post references and allowed follow-up categories. Qwen chooses findings and drafts short next steps. The interface displays the original computed sentence alongside each editable suggestion.

During development, several model responses failed validation: repeated references, too many selections or incomplete output. Those responses did not become accepted briefs. I tightened the output structure and kept rejected attempts private for inspection. The final Instagram and LinkedIn runs produced accepted drafts.

Acceptance here means that the structure, references and checked numeric tokens passed validation. It does not certify the interpretation. I rewrote the sample's suggestions to avoid overstating causes and to propose more useful comparisons. The report records the reviewed text.

![Reviewed draft beside the report controls](../assets/pulse-brief.jpg)

## The design

I wanted posts to stay recognizable while switching metrics, so the main view uses large cards and a separate detail panel. The inspector keeps the calculation close to the content. Petrol and coral carry through to the comparison and import screens; the PDF uses a pale background suited to reading and printing.

![A page from the generated PDF report](../assets/pulse-report-page.jpg)

The narrow layout brings the detail panel below the cards. The demo label remains visible at small widths. A light view is also available.

<details>
<summary>See the light view and mobile layout</summary>

![Light view](../assets/pulse-light.jpg)

<img src="../assets/pulse-mobile.jpg" alt="Scope Pulse on a narrow screen" width="300">

</details>

## My role and the scope

I shaped the product direction, the visual style and the review workflow, then developed and iterated on the implementation with Codex. AI assistance was used for coding, tests, browser checks and documentation. The local Qwen model is a feature of the application; it did not calculate the reported metrics.

The result is a local portfolio application, verified with synthetic data. It is not a deployed analytics service or a study of real campaign performance. Multiuser access, native platform connectors and broader model evaluation would require additional work.

[Verification record](VERIFICATION.md) · [Sample report](../assets/sample-report.pdf)
