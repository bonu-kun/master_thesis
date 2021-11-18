# master_thesis

# 卒論・修論のテンプレート

林研の卒論・修論のテンプレートです．

### 使い方
基本的には，
```tex
% START: XXXX--------------------------------------

% END: XXXX----------------------------------------
```
で囲われた中を編集していきます．  

1. **追加で使用したいパッケージや設定を以下の場所に記述します．**
```tex
% START:ユーザ設定＆ユーザパッケージ読み込み---------

// ここに追加の設定やパッケージを書く

% END:ユーザ設定＆ユーザパッケージ読み込み-----------
```

2. **タイトルページを編集する**
```tex
% START: 論文の種類-------------------------------
%{\Huge 修士論文}
{\Huge 卒業論文}
% END: 論文の種類---------------------------------

% START: 日本語タイトル---------------------------
日本語タイトル
% END: 日本語タイトル-----------------------------

% START: 英語タイトル-----------------------------
English Title
% END: 英語タイトル-------------------------------

% START: 論文の種類-------------------------------
%所属 & 新潟大学自然科学研究科 電気情報工学専攻・林隆史研究室 \\
所属 & 新潟大学工学部情報工学科・林隆史研究室 \\
% END: 論文の種類---------------------------------

% START: 在籍番号---------------------------------
在籍番号 & X00Y000 \\
% END: 在籍番号-----------------------------------

% START: 論文著者---------------------------------
氏名 & XX XX \\
% START: 論文著者---------------------------------
```
3. **アブストラクトを以下の場所に記述する**
```tex
% START:アブストラクト-----------------------------
\section*{概要}
日本語のアブストラクト

\section*{Abstract}
English Abstract Here

% END:アブストラクト-------------------------------
```

4. **本編を以下の場所に記述する**
```tex
% START:本編--------------------------------------
\section{はじめに}
ここから本編

% END:本編----------------------------------------
```

5. **参考文献を以下の場所に記述する**  
必要に応じてbibtex用のコメントアウトを消す．
```tex
% START:参考文献----------------------------------
%% ベタ打ちの場合
\begin{thebibliography}{1}
\bibitem{key1}サイト名\\ \url{http://google.com} （yyyy年mm月dd日アクセス） % ウェブサイトの場合
\bibitem{key2}著者，書籍タイトル，出版                                      % 書籍，論文の場合
\end{thebibliography}


%% bibtexを使用する場合
%\bibliography{ref}         % .bibファイルから拡張子を外した名前 ex)ref.bib
%\bibliographystyle{junsrt} % 参考文献出力スタイル
%\nocite{*}                 % 参照していない項目も出力する
% END:参考文献------------------------------------
```

### コンパイル
```platex```コマンドでも良いが，pdf出力まで可能な以下のコマンドをおすすめする．
```sh
ptex2pdf -l template.tex
```

bibtexを使用する場合は以下のようにコンパイルする．
```sh
pbibtex template
ptex2pdf -l template.tex
ptex2pdf -l template.tex
```
