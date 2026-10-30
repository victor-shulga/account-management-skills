---
name: upsell-mapper
description: >
  Builds a client × services cross-sell map for a B2B service company: which active
  client uses which services, where the gaps are, and which gaps are realistic
  expansion opportunities — with a prioritized action list. Use when the user says:
  "карта апсейлів", "upsell map", "cross-sell map", "кому що допродати", "де ростити
  акаунти", "expansion opportunities", or pastes a client list + service list and asks
  where the growth is. NOT for account health scoring (use client-health-check) and
  NOT for new-business offers (use offer tools).
---

# Upsell Mapper

## What it produces

1. A **client × services matrix**: ✅ uses · ➕ realistic opportunity · — not a fit.
2. A **prioritized opportunity list**: top expansions with the reason, the entry move,
   and an owner.

## Process

1. Collect inputs (ask only for the missing ones):
   - List of active clients (name or anonymized label, industry, size, current monthly value).
   - List of services the company sells.
   - For each client: which services they buy today.
2. For every empty cell, decide: **➕ opportunity** or **— not a fit**. An opportunity
   needs a reason grounded in facts the user gave: adjacent work already happening,
   a pain mentioned on calls, a team they lack, a project phase coming up. No reason —
   no ➕. Do not invent demand.
3. Score each ➕ on two axes (1–3 each):
   - **Likelihood** — existing trust, budget owner already known, natural adjacency.
   - **Value** — potential monthly/project revenue relative to their current spend.
4. Output the matrix, then the opportunity list sorted by likelihood × value.
5. For the top 3–5 opportunities, write the **entry move** — not a pitch, a low-friction
   step: "on the next status call, ask how they currently handle X",
   "send the case study about Y after the QBR", "offer a 2-week paid pilot of Z".
6. Each opportunity gets an owner and a check-in date. Recommend refreshing the map
   quarterly and after every QBR.

## Rules

- Facts only: every ➕ carries its reason in the output. Cells without evidence stay empty.
- Current spend matters: a $2k/mo client with a $30k opportunity is a different play
  than a $30k/mo client with a $2k add-on — flag the asymmetry.
- The map is a working artifact: output it as a table the user can paste into Notion
  or the CRM, with a "status" column (idea → conversation started → proposal → won/lost).

## Terms and plain-language output

<!-- glossary:start terms=cross-sell-map,upsell-score,entry-move,qbr,paid-pilot,expand -->
Rules for every document a client or their team will read (review, roast, canvas, offer cards, instruction):

1. **Open with «Словник цього документа»**: only the terms that actually appear in it, at most 10, each as «термін: що це простими словами». Like the definitions section of a contract.
2. **No internal codes or letter scales in the text** (A/B/C, D L T E, BLEND numbers without words, Own/Shared/Generic, Z1.4, GATE 2.5, T1–T6). Write the meaning instead: «є цифра з клієнтом», not «A».
3. **Use the plain form from the table below.** English stays only for tool names and for copy that ships in English (promises, hooks, subject lines). If the document is in another language, translate the plain form, never the internal term.
4. **Do not score what cannot exist yet.** A block that depends on work not done (signal catalog, case studies, a previous step) gets «пропущено: спершу потрібно <що саме>», not a score.
5. **Every section of a review opens with one concrete action** («до наступного дзвінка: …»), then at most five lines of why. No paragraph that only restates the framework.


| Internal term (this skill) | Write for the reader | What it means |
|---|---|---|
| cross-sell map, client × services matrix | карта допродажів | таблиця клієнтів і послуг: що кожен купує, а що реально можна запропонувати |
| Likelihood × Value (1–3 each) | імовірність × цінність | дві оцінки від 1 до 3 для кожної можливості допродажу; добуток визначає порядок |
| entry move | перший легкий крок | невеликий крок замість продажу: питання на статус-зустрічі, кейс після квартальної зустрічі, короткий платний пілот |
| QBR | квартальна зустріч з клієнтом | раз на квартал разом з клієнтом підсумовуєте результати і плануєте наступні кроки. |
| entry (paid pilot) | платний пілот | невелика робота з фіксованим обсягом, ціною і строком, яка доводить результат до великого договору |
| expand, land-and-expand | допродаж після першої роботи | дорожчі сходинки не пропонуємо холодним людям, їх продаємо клієнту, який уже отримав результат на вхідному офері |
<!-- glossary:end -->
