# DokodemoGPT02

This software allows you to call OpenAI's LLM from within any application.  
(c) 2025 Satoshi Endo  
https://x.com/hortense667
https://ascii.jp/serialarticles/1225476/

## 動かすための準備

1. DokodemoGPT02.zipを適切なフォルダに解凍してください（フォルダ構成のまま）。
DokodemoGPT02.zipは、リポジトリのTag（https://github.com/hortense667/DokodemoGPT02/tags）にあります（現在 v2025-06-17）。
DokodemoGpt02ahk.exe
DokodemoGpt02.py
dist（DokodemoGpt02.pyをpyinstallerでexe化した実行形式が入っているフォルダ）ができます。

3. **環境変数の設定**  
- **OpenAIのAPIキー**  
  OpenAIのAPIキーを取得し、以下の環境変数を`setx`でセットしてください。  
  `OPENAI_API_KEY`

3. **自動実行のための登録**  
WindowsのスタートアップメニューにDokodemoGpt02ahk.exeのショートカットを登録します。

## 使い方の手順

1. **DokodemoGpt02ahk.exeの実行**  
実行するとトレイにAutoHotKeyの「H」アイコンが現れます。

2. **LLMの召喚の仕方**  
2-1. アプリで範囲選択  
エディタやGmail、Wordなどほとんどのアプリの編集画面で利用可能です。  
LLMで処理したいテキストを範囲選択してください。

2-2. プロンプトの入力  
`Win-Ctrl-o`を押すとプロンプト入力ウィンドウが現れるので、プロンプトを入力します。  
例：「読みやすく」「要約して」「英訳して」「誤字・脱字をチェック」など  
※長いプロンプトを与える場合は姉妹ソフトDokodemoPromptがあります。

3. **内容確認**  
「これでよいですか？」というウィンドウが表示されます。  
- 「はい」：結果に置き換えられる  
- 「いいえ」：変更なし  
- 「キャンセル」：元の文に続いて結果を入力

## エンジンやパラメーターの変更

1. **Pythonの環境を用意**
OpenAI、Pyperclip、pyinstall を必要に応じてpip installしてください。

2. **コードの書き換え**  
DokodemoGPT02.pyの適切な箇所を書き換え
- モデル（例: `model="gpt-4o-mini"`）
- 温度（例: `temperature=0.7`）
- 最大トークン（例: `max_tokens=4076`）

3. **exe化**
pyinstallを使用してexe形式を作ってください。
distフォルダにexeが作られます。

