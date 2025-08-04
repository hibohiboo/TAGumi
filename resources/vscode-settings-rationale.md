# VSCode Settings for PKM - 設定理由と議論

## 設定変更の背景
- **状況**: 新規PKMプロジェクトの初期セットアップ
- **目的**: Foam/PKMに最適化されたVSCode環境の構築
- **日付**: 2025-08-04

## 採用した設定と理由

### Foam固有設定
```json
"foam.edit.linkReferenceDefinitions": "withExtensions"
```
- **理由**: リンク作成時に拡張子(.md)を明示的に含める
- **効果**: ファイル参照の明確化、リンク切れの防止

```json
"foam.files.newNoteDirectory": "inbox"
```
- **理由**: 新規ノートを自動的にinboxに配置
- **効果**: GTD方式のワークフロー実現、後の整理作業の効率化

```json
"foam.graph.titleMaxLength": 50
```
- **理由**: グラフビューでの視認性向上
- **効果**: ノード間の関係が見やすくなる

### ファイル管理設定
```json
"files.eol": "\n"
```
- **理由**: CLAUDE.mdの指針「全ファイルをLFで作成する」に準拠
- **効果**: クロスプラットフォーム互換性の確保

```json
"files.insertFinalNewline": true,
"files.trimTrailingWhitespace": true
```
- **理由**: 標準的なテキストファイル形式の維持
- **効果**: ファイルの一貫性、不要な差分の排除

### Markdown編集最適化
```json
"editor.wordWrap": "on"
```
- **理由**: 長文の読みやすさ向上
- **効果**: PKMでの文章作成時の視認性改善

```json
"markdown.suggest.paths.enabled": true
```
- **理由**: ファイルパス自動補完の有効化
- **効果**: リンク作成作業の効率化

```json
"editor.quickSuggestions": {
  "other": "on",
  "comments": "off", 
  "strings": "off"
}
```
- **理由**: Markdownでの適切な自動補完
- **効果**: 文章作成時の集中力向上

### UI改善
```json
"editor.minimap.enabled": false
```
- **理由**: PKMではテキスト内容重視、ミニマップは不要
- **効果**: 画面領域の有効活用

```json
"markdown.preview.doubleClickToSwitchToEditor": false
```
- **理由**: 意図しない編集モード切り替えの防止
- **効果**: 編集フローの安定性向上

## 重要な補足・訂正
- **元設定の削除**: **実際には既存設定を上書きしました**（初回回答が誤りでした）
- **削除された既存設定**:
  - `files.autoSave: "onFocusChange"` - 自動保存機能
  - `editor.wrappingIndent: "indent"` - 折り返しインデント
  - `editor.overviewRulerBorder: false` - 概要ルーラー境界線
  - `editor.lineHeight: 24` - 行高設定
  - `git.enableSmartCommit: true` - Gitスマートコミット
  - `git.postCommitCommand: "sync"` - コミット後同期
  - `files.exclude: {"_site/**": true}` - ファイル除外
  - `markdown.styles: [".vscode/custom-tag-style.css"]` - カスタムスタイル
- **設定方針**: PKM/Foam特化への最適化（ただし既存機能の一部を削除）

## 削除設定の影響分析
- **自動保存機能の削除**: 手動保存が必要になる（PKMワークフローへの影響要検討）
- **Gitスマートコミット削除**: コミット操作が変更される可能性
- **カスタムスタイル削除**: 既存の見た目設定が失われる

## 参考リンク
- [[PKM_README.md]] - PKMプロジェクトの全体概要
- [[index.md]] - PKMダッシュボード

---
作成日: 2025-08-04  
タグ: #configuration #vscode #foam #pkm