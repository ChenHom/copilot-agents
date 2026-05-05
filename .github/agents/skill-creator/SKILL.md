---
name: skill-creator
description: Use this skill when the user wants to create a new reusable skill, restructure an existing skill, or improve a skill's internal design. Especially use it when the task involves SKILL.md authoring, folder layout, references, scripts, eval skeletons, or defining skill boundaries. Do not use this skill for benchmark analysis, blind comparison workflows, or frontmatter trigger-only optimization.
---

# Skill Creator

## Purpose
建立新 skill，或把既有 skill 重構成更清楚、可維護、可驗證的結構。

## When to Use
- 使用者要建立新 skill
- 使用者要重寫或重構既有 `SKILL.md`
- 使用者要釐清 skill 邊界、資料夾結構、references / scripts / evals 骨架
- 使用者要把過胖的 skill 拆成較清楚的責任分工

## When NOT to Use
- 不要用來做 benchmark 比較或 blind comparison 主流程
- 不要用來只優化 frontmatter description 的觸發表現
- 不要用來做長迭代 regression 統計分析

## Inputs Expected
- 使用者需求或現有 skill 路徑
- 既有 `SKILL.md`、`scripts/`、`references/`、`evals/`
- 需要保留或拆分的責任邊界

## Output Requirements
- 產出清楚的 skill 邊界定義
- 產出或重構 `SKILL.md`
- 明確決定哪些內容放 `references/`、哪些放 `scripts/`
- 補出初始 `evals/` 骨架
- 說明重構 / 拆分結果與下一步

## Execution Steps
1. 先定義邊界：In scope / Out of scope / Should trigger / Should not trigger。
2. 先寫完成標準與可觀測訊號，再寫 `SKILL.md`。
3. 決定知識放哪裡：核心流程留在 `SKILL.md`，長篇細節移到 `references/`。
4. 判斷哪些檢查應腳本化，必要時補 `scripts/`。
5. 建立最小 `evals/` 骨架，但不要把 evaluator 的完整責任塞回這個 skill。
6. 若是拆分任務，先抽共享層，再把相鄰責任分流給其他 skill。

## Decision Rules
- 如果任務只是在比較 skill 表現或跑 benchmark，改用 `skill-evaluator`。
- 如果任務只是在改 frontmatter description 讓它更容易正確觸發，改用 `skill-description-optimizer`。
- 如果一個 skill 同時含有 authoring、benchmark、description optimization，優先提出拆分方案。
- 若使用者只想快速起草，不必強迫完整 benchmark；但仍要補最小結構與完成標準。

## Quality Bar
- 不要只寫原則，要寫成 agent 可執行的步驟。
- 不要把所有知識塞進 `SKILL.md`。
- 不要讓 description 模糊到容易誤觸發。
- 不要把 evaluator / description optimizer 的責任混回來。

## Definition of Done
- skill 邊界清楚
- `SKILL.md` 可直接使用
- `references/`、`scripts/`、`evals/` 骨架已就位
- 使用者看得懂這個 skill 負責什麼、不負責什麼

## References
- `../shared/templates/skill_requirement_card.md`
- `../shared/schemas/schemas.md`

## Scripts
- `python ../shared/scripts/quick_validate.py <skill_dir>`
- `python scripts/package_skill.py <skill_dir>`
