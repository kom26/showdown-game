# CLAUDE.md

## プロジェクト概要

「SHOWDOWN」カードゲームのWebアプリ。単一HTMLファイル構成。

## ファイル構成

- `index.html` — 全コード（約5900行、CSS + JS 一体型）
- `ogp.png` — OGP画像

## index.html の構成

| 行範囲 | 内容 |
|--------|------|
| 1–28 | head, Firebase SDK読み込み |
| 29–665 | `<style>` CSS |
| 666–1323 | HTMLマークアップ |
| 1324– | `<script>` JavaScript |

## 技術スタック

- Vanilla JS（フレームワークなし）
- Firebase Realtime Database（オンラインモード）

## ゲームの主要機能

- **オフライン/オンラインモード** — `selectOfflineMode()` / `selectOnlineMode()`
- **部屋作成・参加** — `createRoom()` / `joinRoom()`
- **ゲーム進行** — `startGame()` → `showCardSelect()` → `confirmCard()` → `showRoundResults()`
- **さいころチャンス** — `startDiceRoll()` / `applyChanceResult()`
- **ガード機能** — `openGuardSelect()` / `selectGuardTarget()`
- **そーそーモード** — `toggleSosoMode()`
- **サク負けモード** — `toggleSakuMode()`

## 編集時の注意

- `index.html` は1ファイルにCSS・HTML・JSが全部入っている
- Firebase設定は `<script>` 内の `firebaseConfig` オブジェクト
- `grep -n "function xxx"` で関数の行番号を探すと効率的

## 行動ルール

### 出力スタイル
- 思考過程の独り言は出力しない。原因特定・修正方針は明確に伝える。

### 新機能実装フロー
1. **要件確認** — 不明点・詰め切れていない点を質問する
2. **実装計画** — 要件が固まったら計画を提示し、追加質問があれば確認
3. **実装許可** — 計画に問題なければ許可を取る
4. **段階的コーディング** — 1ステップずつ確実に実装
5. **バグ確認** — 実装後にバグがないか検証・修正
6. **デプロイ確認** — 問題なければデプロイの許可を取る

### コード編集時
- 括弧の追加・削除は必ず前後の数を確認してシンタックスエラーを防ぐ

### バグ発見時
- 本当にバグか再検証する
- バグと確認できたら以下を報告：
  - ゲームへの影響度
  - 発生条件
  - 修正難易度
