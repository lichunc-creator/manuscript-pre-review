# manuscript-pre-review

投稿前自我審查與退修稿（R1/R2）檢核的 Claude Skill，適用於護理與健康科學稿件。

A Claude Skill for pre-submission self-review and revision (R1/R2) checking of nursing and health science manuscripts.

## 功能

- **初投稿模式**（預設）：通讀全文 → 查證文獻（PubMed，附 PMID/DOI）→ 七個審查面向 → 報告規範對照（STROBE、COREQ/SRQR、GRAMMS、CONSORT/TREND、PRISMA、TRIPOD+AI 等）→ 內部一致性檢查 → desk-reject 預篩 → 多角色審查。
- **退修模式**（輸入 `R1`、`R2`…）：把審查意見拆解成單一項目，逐條核對回覆信與修訂稿是否一致，判定為：完整回應、部分回應、未回應、合理反駁、反駁風險高、回覆與稿件不符；另外抓出修改帶來的新問題，並預測下一輪可能被追問的事。
- **目標期刊簡則**：開場先問目標期刊，上網查官方投稿簡則，整理成檢核清單，附來源網址。
- **條件模組**：依研究設計自動啟用相關檢查，例如權力關係、叢集資料、兒童或易受傷害族群、介入方案、量表、質性或混合方法、AI 工具研究、非人體研究、GenAI 使用揭露。
- **防錯**：每項指摘都附位置和原文短引；無法驗證的標為「無法驗證」；絕不捏造文獻。
- **輸出**：審查報告用英文，行動清單與意見對照表用中文。

## 安裝

- **Claude（claude.ai / desktop）**：下載 [`dist/manuscript-pre-review.skill`](dist/manuscript-pre-review.skill)，在技能設定中上傳。
- **Claude Code**：把 `SKILL.md` 放到 `~/.claude/skills/manuscript-pre-review/SKILL.md`。

## 使用範例

```
審查稿件，目標期刊 Nurse Education Today，Original research。（附上稿件）
```

```
R1，目標期刊 BMC Nursing。（附上審查意見、回覆信草稿、修訂稿）
```

```
R2，回覆信還沒寫，請幫我做回覆規劃。
```

## 設計依據

審查流程參考 King, G., & Worthington, S. (2026). *AI Article Reviews Dominate Human Peer Reviews at Their Best: Evidence and Policy Choices.* https://gking.harvard.edu/peerless/

本 skill 的指示依該研究的結構與原則重新撰寫，並未收錄原文 prompt。另外增加了期刊簡則查詢、報告規範、條件模組、防錯機制、停止規則與退修模式。

## 注意

AI 審查仍可能出錯：上述研究中，即使是最好的 AI 審查，也有 37.1% 至少含一處錯誤。請逐項核對報告中的指摘和文獻後再修改稿件。
