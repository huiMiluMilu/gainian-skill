---
name: jargon-explainer
description: This skill should be used when the user asks to explain a term, word, concept, or piece of jargon they find obscure, difficult, or unfamiliar. It produces a three-part explanation — a professional/academic definition, a plain-language version simple enough for a primary-school child, and a concrete real-world example or case — so the user gains both rigor and intuition.
agent_created: true
---

# Jargon Explainer

## Overview

Turn an obscure or unfamiliar term into something the user both understands deeply and can explain to anyone. For every requested term, deliver exactly three parts:

1. **专业解释** — accurate, domain-correct, uses proper terminology.
2. **通俗解释（小学生也能懂）** — zero jargon, everyday analogy, a child could follow.
3. **案例** — one concrete, real-world scenario that shows the term in action.

This skill applies to any domain: finance, tech, law, science, philosophy, daily-life words, idioms, buzzwords, etc.

## When to Use

- The user says "解释一下 X", "X 是什么意思", "什么是 X", "帮我讲讲 X", "X 太晦涩了" or similar.
- The user pastes a term, acronym, or phrase they don't understand.
- The user asks for both a rigorous and a layperson-friendly take on the same concept.

If the request is ambiguous in meaning, domain, or scope, see Handling Ambiguity below — do not silently guess wrong.

## Output Format

Always respond in the user's language (default: Chinese). Use this exact three-section structure for each term:

### 1. 专业解释
- Give a precise, technically correct definition.
- Name the domain (e.g., 金融 / 计算机 / 法律 / 生物学).
- Include etymology, key components, or how it differs from closely related concepts when that adds clarity.
- If the term has formal variants or standards (e.g., a financial accounting rule, an RFC, a legal statute), cite them briefly.

### 2. 通俗解释（小学生也能懂）
- Rewrite the idea with no jargon, no acronyms, no math symbols unless unavoidable.
- Lead with a relatable analogy from everyday life (food, toys, animals, school, weather, sports).
- Keep it to 2–4 short sentences. A 7–10 year old should be able to repeat it back.
- If an analogy necessarily simplifies away an important caveat, add one short "不过要记住" sentence — but keep it child-friendly.

### 3. 案例
- Provide one concrete scenario or mini-story (real or realistic), not a list.
- Show the term actually being used / happening, so the abstract becomes visible.
- 1–3 short paragraphs, or 3–5 bullet-step walkthrough. Prefer the user's likely domain when known.

## Workflow

1. Identify the exact term and the user's intended domain. If the user already specified a domain, honor it.
2. Verify the definition before writing. For technical, financial, legal, or scientific terms that you are not 100% certain about, confirm with a quick search rather than guessing. Accuracy is the point of the professional section.
3. Write the three sections in order. Keep each section self-contained — do not force the reader to cross-reference.
4. If multiple unrelated terms are requested at once, handle each with its own three-part block (use a separator between them).
5. End with a one-line offer: e.g. "需要我把这个讲得更深，或换个例子吗？"

## Handling Ambiguity

- A term with several meanings (e.g., "hedge" in finance vs. gardening): pick the most common or the one matching the user's context, state the assumption in one line, and optionally list the other meanings briefly.
- If the user's intent is genuinely unclear (no context at all and the word is highly polysemous), ask one short clarifying question before answering rather than guessing.
- Do not over-ask. When a reasonable default exists, state it and proceed.

## Quality Bar

- Professional section must be defensibly correct, not hand-wavy.
- Kid section must contain no unexplained jargon — if a technical word is unavoidable, immediately re-explain it in plain words.
- Case must be specific and tangible, not a restatement of the definition.

## Example

User: 解释一下"沉没成本"。

Response:

**专业解释**
沉没成本（Sunk Cost）是经济学与决策理论中的概念，指已经发生、且无论如何决策都无法收回的支出（时间、金钱、精力）。它属于"历史成本"，在理性决策中不应影响未来选择——因为过去的投入已不可逆，正确的做法是只看未来的收益与成本。

**通俗解释（小学生也能懂）**
就像你花钱买了一张电影票，进去看了十分钟发现电影很无聊。票钱已经花掉、退不回来了，这钱就是"沉没成本"。聪明的小朋友不会想"钱都花了忍着看完"，而是直接离开去看更好玩的事——因为继续坐着也不会把钱变回来。

**案例**
小明花 200 元报了吉他课，上了两节发现完全没兴趣，但还剩 8 节课。如果只因为"钱都交了"就硬着头皮上完，他会再浪费 8 周时间还不快乐——这 200 元已经沉没了。理性做法是承认损失、把剩下时间拿去做喜欢的事。公司也一样：一条已经投了 1 亿、但市场证明没前途的生产线，继续砸钱"回本"往往亏更多。
