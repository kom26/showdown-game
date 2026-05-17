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
