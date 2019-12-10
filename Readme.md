# okarabox

hinagata.texとSQM1TEAcom######.styは、量子力学演習Ⅰ期末レポート用のTeXテンプレです。
hinagata.texの名前は使用の際には変更して構いません。以下では該当ファイルをhinagata.texと呼んでいます。

内容物：
・hinagata.tex　---　メイン文書です。
・SQM1TEAcom######.sty　---　TeX Liveに含まれるPackageの読み込みの宣言、各種コマンドの定義と再定義を行っています。
・latexmkrc　---　自動コンパイル用ファイルです。詳細は下記にあります。

要求と諸注意：
・TeX Liveをダウンロードおよびインストールしてください。
・hinagata.texは、複数の解答texファイルを連結してコンパイルするためのファイルです。
・hinagata.texとSQM1TEAcom######.styは同じ場所に保存してください。（違う場所に保存した場合の動作は未確認です。）
・hinagata.texとSQM1TEA#_#.tex（解答ファイル）は同じ場所に保存してください。
  （違う場所に保存した場合の参照失敗を確認済みです。直せる方は直して構いません。）
・各SQM1TEA#_#.texは、以下のように記述してください：

\begin{subsection}{}
（解答を記述）
\end{subsection}
\setcounter{equation}{0}

　一行目の末尾{}を忘れるとErrorを吐きます。最後の行の命令がないと式番号が小問を超えて加算されます。
・小問解答記述中のenumerate環境に対応していません（subsectionのインデントが解除されてしまいます。）

latexmkrcについて：
hinagata.texのあるフォルダでコマンドプロンプトを起動し、以下のように命令してください。
ただし、hinagata.texの部分は自分で変更したファイル名に読み替えてください。

  latexmk hinagata.tex -pvc
  
これにより、コマンドプロンプトが常にhinagata.texの状態を監視し、変更があった場合に直ちにコンパイルが開始されます。

何か不具合などございましたら、GithubもしくはTwitterなどでご連絡ください。
