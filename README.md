# DokodemoGPT

This software allows you to call OpenAO LLM from within any application.  
(c) 2025 Satoshi Endo  
https://x.com/hortense667
https://ascii.jp/serialarticles/1225476/

2. **How to Call the OpenAI API**  
2-1. Select a range in the software's text input area  
Select the part you want to pass to the OpenAI API in the editing screen of most applications like editors, Gmail, Word, etc.

2-2. Input the prompt  
Press `Win-Ctrl-o` to bring up the prompt input window, where you can enter your prompt.  
Examples: "Rewrite for readability", "Summarize", "Translate to English", "Check for typos and omissions", etc.  
* Note: Adding "/w" at the end, like "What kind of person?/w", will perform a web search and respond based on the first 1000 characters of the top three sites.  
* Note: If you write "Readable/0.2", "0.2" will be given as the Temperature parameter to the OpenAI API.  
You can press the up and down arrow keys in the prompt input window to retrieve previously entered prompts. You can use them as they are or edit them. Clicking the "v" on the right side of the input field will display a list as well. Once you finalize your prompt, click "OK".

3. **Content Confirmation**  
After a few seconds to several dozen seconds, a window will appear asking, "Is this okay?"  
- "Yes": Replaces with the result  
- "No": No changes  
- "Cancel": The result will be input following the original text.

## Necessary Settings for Operation

1. **Setting Environment Variables**  
- **OpenAI API Key**  
  Obtain your OpenAI API key and set the following environment variable:  
  `OPENAI_API_KEY`

2. Unzip DokodemoGPT.zip  
Download dokodemogpt02.zip from the "Releases" section of the DokodemoGPT repository.  
Extract it to an appropriate folder.  
Running DokodemoGPT02ahk.exe in the extracted folder will allow you to use the OpenAI API anywhere at any time.  
Please place the dist folder and its contents directly in the folder where DokodemoGPT02ahk.exe is located.

3. **Register for Automatic Execution**  
Register a shortcut for DokodemoGpt02ahk.exe in the Windows startup menu.

## Shortcut Modification
1. Modify DokodemoGpt02ahk.ahk  
The line " ^#o:: " corresponds to the Ctrl-Win-o trigger.  
Rewrite this and compile it from AutoHotKey Dash to create a new DokodemoGpt02ahk.exe.  
AutoHotKey Dash can be used by installing AutoHotKey.

## Changing Engine and Parameters

1. **Prepare the Python Environment**  
Install necessary packages like OpenAI, Pyperclip, and pyinstall via pip as needed.

2. **Rewrite the Code**  
Modify the appropriate sections of DokodemoGPT02.py  
- Model (e.g., `model="gpt-4o-mini"`)  
- Temperature (e.g., `temperature=0.7`)  
- Max tokens (e.g., `max_tokens=4076`)

3. **Create .exe**  
Use pyinstall to create an executable file.  
An .exe will be created in the dist folder.

## Using on Mac
1. **Prepare a snippet tool other than AutoHotKey**  
Create a script that calls DokodemoGPT02.py from that tool.  
Therefore, a Python runtime environment is needed.  
The prompt will be passed to DokodemoGPT.py via the clipboard from the snippet tool, and the result will be returned to the snippet tool via the clipboard again. Please refer to the source code for more details.


## 概要
Windowsのほとんどのソフトウェアのテキストを入力するシーンでOpenAIのAPIを呼び出して結果を入力できるソフトウェアです。スニペットツールのAutoHotKeyとPythonを使って書かれています。どちらもexe化してあるので、APIキーなどの設定をすればすぐに使いはじめることができます。モデルは「model="gpt-4o-mini」が使用されます。

## 使い方の手順

1. **DokodemoGPT02ahk.exeの実行**  
実行するとトレイにAutoHotKeyの「H」アイコンが現れます。すでに実行中のときはそれを終了してから実行してください。

2. **OpenAI APIの呼び出し方**  
2-1. ソフトウェアのテキスト入力エリアで範囲選択  
エディタやGmail、Wordなどほとんどのアプリの編集画面でOpenAIのAPIに渡したい部分を範囲選択してください。

2-2. プロンプトの入力  
`Win-Ctrl-o`を押すとプロンプト入力ウィンドウが現れるので、プロンプトを入力します。  
例：「読みやすく書き換えて」「要約して」「英訳して」「誤字・脱字をチェック」など 。
※「どんな人？/w」などと最後に「/w」をつけるとWeb検索して最初の3つのサイトの冒頭1000文字を参考に答えます。
※「読みやすく/0.2」などとすると「0.2」をOpenAIのAPIにTemperatureとして与えます。
またプロンプト入力ウィンドウでカーソル上下キーを押すことで過去に入力したプロンプトが出てきます。そのまま使ってもよいし編集してもよいです。入力欄の右側の「v」をクリックすることで一覧も表示されます。
プロンプトが決まったら「OK」をクリックします。
なお、過去のプロンプトの履歴は最大100件までDokodemoGPT02ahk.exeを実行したフォルダ上に「prompt_history.txt」というファイルに作成されます。

3. **内容確認**  
数秒から数十秒が経過すると「これでよいですか？」というウィンドウが表示されます。  
- 「はい」：結果に置き換えられる  
- 「いいえ」：変更なし  
- 「キャンセル」：元の文に続いて結果が入力されます。

## 動作のために必要な設定

1. **環境変数の設定**  
- **OpenAIのAPIキー**  
  OpenAIのAPIキーを取得し、以下の環境変数をセットしてください。  
  `OPENAI_API_KEY`

2. DokodemoGPT.zipの解凍
DokodemoGPTのリポジトリの「リリース」からdokodemogpt02.zipをダウンロード。
適切なフォルダに展開してください。
解答したフォルダの中にあるDokodemoGPT02ahk.exeを実行するとどこでもOpenAIのAPIがいつでも使える状態となります。
解凍ファイルのdistとフォルダとその中身は、DokodemoGPT02ahk.exeのあるフォルダにそのまま置いてください。

3. **自動実行のための登録**  
WindowsのスタートアップメニューにDokodemoGpt02ahk.exeのショートカットを登録します。

## ショートカットの変更
1. DokodemoGpt02ahk.ahkの修正
「^#o::」は、Ctrl-Win-oでの起動です。
ここを書き換えて、AutoHotKey DashからコンバイルしてDokodemoGpt02ahk.exeを新しくしてください。
AutoHotKey Dashは、AutoHotKeyをインストールことで使えるようになります。

## エンジンやパラメーターの変更

1. **Pythonの環境を用意**
OpenAI、Pyperclip、pyinstall など必要に応じてpip installしてください。

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
そのツールからDokodemoGPT02.pyを呼び出すようにスクリプトを作ってください。
したがって、Pythonの動作環境が必要となります。
スニペットツールからはプロンプトがDokodemoGPT.pyにクリップボードで渡され、DokodemoGPT.pyからはやはりクリップボード経由で結果がスニペットツールに戻されます。詳しくはソースコードをご覧ください。

## Overview
This software allows you to call the OpenAI API and input the results in scenes where text is input into most Windows software. It is written using the snippet tool AutoHotKey and Python. Both are compiled into .exe files, so you can start using it immediately after setting the API key and other configurations. The model used is "model='gpt-4o-mini'".

## Usage Steps

1. **Run DokodemoGPT02ahk.exe**  
When executed, an AutoHotKey "H" icon will appear in the tray. If it is already running, please exit it before executing again.

