# DokodemoGPT02

This software allows you to call OpenAI's LLM from within any application.  
(c) 2025 Satoshi Endo  
https://x.com/hortense667
https://ascii.jp/serialarticles/1225476/

## 動かすための準備

1. **DokodemoGPT02.zip**  
DokodemoGPT02.zipを適切なフォルダに解凍してください（フォルダ構成のまま）。
DokodemoGPT02.zipは、リポジトリのReleasesにあります。
- DokodemoGpt02ahk.exe
- dit（DokodemoGpt02.pyをpyinstallerでexe化した実行形式が入っているフォルダ）
- source（AutoHotKeyとPythonのコードが入っているフォルダ）
  - DokodemoGpt02.py
  - DokodemoGpt02ahk.py
- Readme.md

2. **環境変数の設定**  
- **OpenAIのAPIキー**  
  OpenAIのAPIキーを取得し、以下の環境変数をセットしてください。  
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
※「どんな人？/w」などと最後に「/w」をつけるとWeb検索して最初の3つのサイトの冒頭1000文字を参考に答えます（テスト中）。
※「小説を書いて/1.3」などと最後に「/数字」をつけるとOpenAIのAPIのTempratureパラメータ（0～2）を与えられます。標準は0.7。大きい数字ほど創造性豊かになりますが2に近づくと日本語ですらなくなります。「/w/0」などの指定も可能（テスト中）。
※長いプロンプトを与える場合は姉妹ソフトDokodemoPromptがあります。

3. **内容確認**  
「これでよいですか？」というウィンドウが表示されます。  
- 「はい」：結果に置き換えられる  
- 「いいえ」：変更なし  
- 「キャンセル」：元の文に続いて結果を入力（したがって、文の続きや結論などを書かせるときに便利です）。

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

## Macでの使用
1. **AutoHotKey以外のスニペットツールを用意**
そのツールからDokodemoGPT02.pyを呼び出すように設定すればよい。
したがって、Pythonの動作環境が必要となります。
スニペットツールからはプロンプトがDokodemoGPT02.pyにクリップボードで渡され、DokodemoGPT02.pyからはやはりクリップボード経由で結果がスニペットツールに戻されるだけである。

