# 喫茶 三日月 — vintage-sundries/showa-retro Spec

**Status:** Approved
**Author:** torifo
**Created:** 2026-05-23
**Updated:** 2026-05-23

---

## 1. Overview

### Problem Statement
昭和レトロを愛好する30代男性は、戦後昭和を直接体験していない世代であり、「昭和の喫茶店」体験を、過剰なノスタルジー演出（古びた写真フィルター、英文の "RETRO" 表記）ではない形で味わいたいと考えている。日本人デザイナーが日本人ペルソナ向けに昭和を翻訳した Web の事例が少ない。

### Goal
神保町の純喫茶を改装した古道具部という設定で、昭和書体（Reggae One ・ Hina Mincho ・ DotGothic16 ・ Yuji Syuku）を組み合わせ、喫茶ブラウン×バタークリーム×レトロ赤の配色とレコード ・ ガラス ・ マッチ箱を主役にした架空店舗を実装する。

### Non-Goals
- 実在喫茶店メニューの再現
- カート ・ 決済機能
- 動画 ・ 効果音

### Background
- 喫茶 三日月（KISSA MIKAZUKI）は本デザイン研究のための架空店舗
- 同シリーズ4作の中で「明るくノスタルジック ・ 楽しい組版」が唯一のサイト

---

## 2. User Stories

| ID | Persona | Want to | So that |
|----|---------|---------|---------|
| US-01 | 純喫茶ノスタル系ライター（中村 涼太想定） | ページを開いた瞬間に「あの時代の喫茶店」が立ち上がる | 思い出と道具が結びつく |
| US-02 | 同上 | 古道具とレコードを一緒に見たい | 喫茶店総体としての雰囲気を味わいたい |
| US-03 | 同上 | 店主の手記を読みたい | なぜこの道具を扱うのかを納得して購入したい |
| US-04 | 同上 | 友人を連れて店に行ける情報が欲しい | デート ・ 出張ついでに立ち寄れる |

### Acceptance Criteria

**US-01:**
- WHEN ページが読み込まれた THEN レコード盤回転＋クリームソーダSVG＋大型レトロタイトルが現れる
- WHEN 表示後 THEN 喫茶ブラウン×バタークリームの「印刷ノスタルジー」感がある

**US-02:**
- WHEN ページをスクロールした THEN 商品メニュー → レコード棚 → マッチ箱の順で配置される
- WHEN レコード棚をホバーした THEN ジャケット裏からレコード盤が滑り出す

**US-03:**
- WHEN 店主の手記セクションに到達した THEN 店主の挨拶文が「お便り風」に表示される
- WHEN テキストを読んだ THEN 商品ではなく時代観が語られている

**US-04:**
- WHEN 店の案内に到達した THEN 住所 ・ 営業 ・ 道順 SVG マップが確認できる

---

## 3. Functional Requirements

| ID | Requirement | Priority | Notes |
|----|-------------|----------|-------|
| FR-01 | 看板ヘッダー（月マーク） | P0 | sticky、3D感のあるシャドウ |
| FR-02 | ヒーロー（レコード回転＋ソーダSVG） | P0 | レコードは spin animation |
| FR-03 | 商品メニュー（4品） | P0 | クリームソーダ ・ ナポリタン皿 ・ サイフォン ・ ホーロー看板 |
| FR-04 | レコード棚（6枚） | P0 | グラデジャケット、ホバーで盤が出る |
| FR-05 | マッチ箱コレクション（8個） | P1 | 8喫茶 ・ 8色 |
| FR-06 | 店主の手記 | P0 | 紙のレターパッド風 |
| FR-07 | 店の案内＋手書き地図 | P0 | SVG マップ含む |
| FR-08 | おしながき帯（CTA） | P1 | 食パン的縞模様 |
| FR-09 | ふわっとリビール | P1 | 1s pop |
| FR-10 | ナビゲーション（明朝 ・ レトロ風） | P0 | sticky |
| FR-11 | モバイル対応（375px） | P0 | レコードは縮小、看板は段落ち |

---

## 4. Architecture

```
showa-retro/index.html
├── <header>                       # 看板＋月マーク
├── <section class="hero">         # レコード＋ソーダ＋大型タイトル
├── <section id="menu">            # 商品メニュー 4品
├── <section class="osh-band">     # おしながき CTA
├── <section id="tana">            # レコード棚 6枚
├── <section class="matchcoll">    # マッチ箱 8個
├── <section id="shuki">           # 店主の手記
├── <section id="annai">           # 店の案内＋地図
└── <footer>                       # 4店舗ナビ
```

### Key Design Decisions

| Decision | Chosen | Rationale | Rejected |
|----------|--------|-----------|----------|
| テーマ | ライト（暖） | バタークリームの紙色 | ダーク |
| 主書体 | Reggae One+ Hina Mincho | 看板＋明朝のミックス | Hiragino のみ |
| 装飾 | リボン ・ マッチ箱 ・ レコード | 喫茶店の語彙 | テープ ・ スタンプ |
| アニメ | レコード回転＋ふわっと | 機械式ノスタル感 | 強いスライド |
| 補色 | レトロ赤＋ガラスエメラルド | 純喫茶インテリア | パステル |

---

## 5. Design System

### Color Palette
```css
--cha:#3a2418;       /* 深焙煎ブラウン */
--cha-koi:#221208;
--butter:#f4e4c1;    /* バタークリーム */
--butter-asa:#fbf3df;
--aka:#c93b3b;       /* レトロ赤 */
--aka-yami:#902525;
--midori:#3a8f7e;    /* クリームソーダ */
--orange:#e89234;    /* ランプ */
--shinchu:#b08940;   /* 真鍮 */
--kuro:#1a1212;
```

### Typography
```css
--font-kanban:'Reggae One','Hina Mincho',serif;
--font-hina:'Hina Mincho',serif;
--font-syuku:'Yuji Syuku','Hina Mincho',serif;
--font-tegaki:'Klee One','Hina Mincho',serif;
--font-dot:'DotGothic16',monospace;
```

### Motion
```css
@keyframes spin{ to{ transform: rotate(360deg) } }
.record{ animation: spin 12s linear infinite }

@keyframes pop{ from{ opacity:0; transform: translateY(20px) } to{ opacity:1; transform: none } }
```

---

## 9. Testing Strategy

| Layer | Scenarios |
|-------|-----------|
| Desktop (1280px) | レコード回転、ソーダSVG、看板タイトルのシャドウ重なり |
| Mobile (375px) | 看板ヘッダー段落ち、レコード棚 1〜2 カラム、地図 SVG 縮小 |
| アニメ | レコード 12s ループ、`prefers-reduced-motion` で停止 |
| ホバー | レコードジャケット → 盤が右に出てくる |
| フォント | Reggae One ・ Hina Mincho ・ DotGothic16 ・ Yuji Syuku 正常 |

---

## 10. Implementation Notes

- **レコード回転**: `animation: spin 12s linear infinite`、`prefers-reduced-motion` 時は停止
- **看板影**: `text-shadow: 3px 3px 0 var(--butter-asa), 6px 6px 0 var(--cha-koi)` で3D感を付与
- **マッチ箱**: 縦長 5:8 ratio、底に切手歯車風 `repeating-linear-gradient`
- **手書き地図**: SVG で道路 ・ 出口 ・ 店舗位置を作図、文字に DotGothic16 を Inline SVG で適用
- **おしながき帯**: 上下に `repeating-linear-gradient(45deg, ...)` で食パン縞を作成

---

## 11. Open Questions

| # | Question | Status |
|---|----------|--------|
| 1 | レコードジャケットを実写へ差し替えるか | Open |
| 2 | マッチ箱を別ページの詳細にリンクするか | Open |
| 3 | クリームソーダのSVGを夏限定で他に差し替えるか | Open |

---

## References

- [navigator README](../README.md)
- Font: [Reggae One](https://fonts.google.com/specimen/Reggae+One), [Hina Mincho](https://fonts.google.com/specimen/Hina+Mincho), [DotGothic16](https://fonts.google.com/specimen/DotGothic16)
- Inspiration: 純喫茶 ろまん／珈琲 美少年／喫茶 苦楽園、シティポップ レコードジャケット、昭和喫茶店のメニュー表
