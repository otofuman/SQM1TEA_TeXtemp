The Template for Submitting SQM1 Term-end Assignment with (La)TeX
==

**更新内容：(最終更新　2019/12/17)**
- 12/17　相対パス指定に対応
- 12/11　公開

## 使い方
hinagata.texの名前は使用の際には変更して構わない。以下では該当ファイルをhinagata.texと呼ぶ。
**内容物**
- [hinagata.tex](hinagata.tex)
- [SQM1TEAcom191208.sty](SQM1TEAcom191208.sty)　:　TeX Liveに含まれるPackageの読み込みの宣言、各種コマンドの定義と再定義。
- [latexmkrc](latexmkrc)　:　自動コンパイル用ファイル。詳細は下記。

**要求と諸注意**
- **TeX Live**をダウンロードおよびインストールしておくこと。
- hinagata.texは複数の解答texファイルを連結してコンパイルするためのファイル。
- hinagata.texとSQM1TEAcom191208.styは同じ場所に保存すること。（違う場所に保存した場合の動作は未確認。）
- hinagata.texのある場所にPr〇なるファイルを用意し、大問〇の(△)の解答ファイル〇_△.texをその中に格納すること。Pr〇の名称は適宜変えてよいが、hinagata.tex内の対応するパスも変更する。
- 各〇_△.texは、以下のように記述すること：

> \begin{subsection}{}

> （解答を記述）

> \end{subsection}

> \setcounter{equation}{0}

- **一行目の末尾{}を忘れるとErrorを吐く。最後の行の命令がないと式番号が小問を超えて加算される。**
- **小問解答記述中のenumerate環境に未対応。（subsectionのインデントが解除不具合あり。）**

**latexmkrcについて**
hinagata.texのあるフォルダでコマンドプロンプトを起動し、以下のように命令する。 ただし、hinagata.texの部分は自分で変更したファイル名に読み替える。

> latexmk hinagata.tex -pvc

これにより、コマンドプロンプトが常にhinagata.texの状態を監視し、変更があった場合に直ちにコンパイルが開始される。
