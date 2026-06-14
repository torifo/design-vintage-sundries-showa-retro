[English](#english) | [日本語](#japanese)

---

<a id="english"></a>

# KISSA MIKAZUKI — design-vintage-sundries-showa-retro

> **"Lighting Showa, one cup at a time."**

A design study exploring a fictional Showa-retro old-goods shop housed inside a Jimbocho jazz coffee shop — targeting **a 32-year-old nostalgia-oriented magazine writer** who never lived through the Showa era but built his identity around its city-pop, kissaten, and vinyl culture.

KISSA MIKAZUKI is a fictional shop created for this design study.

## Overview

| | |
|---|---|
| **Brand** | KISSA MIKAZUKI (喫茶 三日月) |
| **Persona** | showa-retro |
| **Live Site (planned)** | `design.vintage-sundries-showa-retro.riumu.net` |

## Design Concept

- **Color**: Roasted brown `#3a2418` × butter cream `#f4e4c1` × retro red `#c93b3b` × cream-soda green `#3a8f7e`
- **Typography**: Reggae One (display signage) × Hina Mincho (display alt) × Klee One (body) × DotGothic16 (mono) × Yuji Syuku (accents)
- **Aesthetic**: Showa-era jun-kissa (purist coffee shop) × city pop × LP record collection
- **UX**: Spinning record hero, matchbox collection, hand-drawn SVG map, store note as letter pad
- **Texture**: Print halftone, glass reflection, butter-cream paper stripes

## Tech Stack

- Pure HTML + CSS Custom Properties + Vanilla JS
- Google Fonts CDN
- No framework, no build step — GitHub Pages ready

## Spec

See [spec.md](./spec.md) for the full design specification.

## Install as a skill / スキルとして導入

This repo ships a cross-agent **`SKILL.md`** (open standard) usable by both Claude Code and Codex CLI as a design-reference skill. Link the repo into the agent's skills directory:

このリポジトリは Claude Code / Codex CLI 共通の **`SKILL.md`**（オープン標準）を同梱し、デザイン参照スキルとして使えます。

```bash
# Claude Code
ln -s "$(pwd)" ~/.claude/skills/design-vintage-sundries-showa-retro
# Codex CLI
ln -s "$(pwd)" ~/.codex/skills/design-vintage-sundries-showa-retro
```

Restart the agent; it is matched automatically by the skill's `description` (skill name: `design-vintage-sundries-showa-retro`). / エージェント再起動後、`description` に基づき自動マッチします。

## Part of

vintage-sundries persona series — 1 of 4. Navigator: [vintage-sundries](../README.md)

---

<a id="japanese"></a>

# 喫茶 三日月 — design-vintage-sundries-showa-retro（日本語）

> **「昭和の灯を、いまも一杯。」**

ヴィンテージ雑貨 ・ デザイン研究シリーズの昭和レトロペルソナ。**32歳・ノスタル系雑誌ライター**——昭和を直接体験せず、シティポップと純喫茶と中古LPを介して昭和を再構築した層——に特化した、神保町の純喫茶を改装した架空店舗です。

喫茶 三日月は本デザイン研究のために作成した架空店舗です。

## 概要

| | |
|---|---|
| **ブランド** | 喫茶 三日月（KISSA MIKAZUKI） |
| **ペルソナ** | showa-retro（昭和レトロ） |
| **公開URL（予定）** | `design.vintage-sundries-showa-retro.riumu.net` |

## デザインコンセプト

- **カラー**: 深焙煎ブラウン × バタークリーム × レトロ赤 × クリームソーダ
- **フォント**: Reggae One（看板）× Hina Mincho × Klee One（本文）× DotGothic16（モノ）× Yuji Syuku
- **世界観**: 昭和の純喫茶 × シティポップ × LPレコード
- **UX**: 回転レコードヒーロー、マッチ箱コレクション、手書きSVG地図、店主のレターパッド風手記
- **テクスチャ**: 印刷網点、ガラス反射、バタークリームのストライプ罫線

## 技術

- 純粋なHTML + CSS Custom Properties + Vanilla JS
- Google Fonts CDN、ビルド不要で GitHub Pages 対応

## 仕様書

詳細は [spec.md](./spec.md) を参照。デザイン判断の経緯は [DESIGN_LEARNINGS.md](./DESIGN_LEARNINGS.md) に。

## シリーズ

ヴィンテージ雑貨 ・ ペルソナシリーズ4作のうち1作。
ナビゲーターページ: [vintage-sundries](../README.md)
