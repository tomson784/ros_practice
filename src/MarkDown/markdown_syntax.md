# Markdown記法のコードまとめ

- [見出し](#見出し)
- [箇条書きリスト](#箇条書きリスト)
- [番号付きリスト](#番号付きリスト)
- [折り畳み](#折り畳み)
- [空行・改行](#空行・改行)
- [スペース](#スペース)
- [コードの挿入](#コードの挿入)
    - [ブロック](#ブロック)
    - [インライン](#インライン)
- [リンクの挿入](#リンクの挿入)
- [画像の挿入](#画像の挿入)
- [テーブルの挿入](#テーブルの挿入)
- [文字装飾](#文字装飾)
- [水平線](#水平線)
- [エスケープ](#エスケープ)(Markdownの無効化)
- [引用](#引用)
- [コメントアウト](#コメントアウト)

<!--- 新しくコードを加える際のテンプレ

## コードの内容
説明  
<br>

**<u>コード</u>**
```
コード
```
<br>

**<u>表示結果</u>**  

<br>

--->
<br>

## 見出し
シャープを文字の先頭に記述する。`#` が増えるごとに文字のサイズが小さくなる。  
`#` が3つ目以降は下線が付かない。  
シャープと見出し文字の間には半角スペースを1つ入れること。  
<br>

**<u>コード</u>**
```
# 見出し h1
見出し h1
===
## 見出し h2
見出し h2
---
### 見出し h3
#### 見出し h4
##### 見出し h5
###### 見出し h6
```
<br>

**<u>表示結果</u>**

# 見出し h1
見出し h1
===
## 見出し h2
見出し h2
---
### 見出し h3
#### 見出し h4
##### 見出し h5
###### 見出し h6
<br>

## 箇条書きリスト
ハイフン、プラス、アスタリスクのいずれかで箇条書きリストを記述可能。
ハイフン、プラス、アスタリスクと箇条書きの項目の間には半角スペースを1つ入れること。  
<br>

**<u>コード</u>**
```
- リスト1
* リスト2
    + リスト2.1
        - リスト2.1.1
            * リスト2.1.1.1
    - リスト2.2
+ リスト3
```
<br>

**<u>表示結果</u>**

- リスト1
* リスト2
    + リスト2.1
        - リスト2.1.1
            * リスト2.1.1.1
    - リスト2.2
+ リスト3

<br>

## 番号付きリスト
**<u>コード</u>**

```
1. テキスト1
2. テキスト2
4. テキスト3
    1. テキスト3.1
    2. テキスト3.2
2. テキスト4
```
<br>

**<u>表示結果</u>**  

1. テキスト1
2. テキスト2
4. テキスト3
    1. テキスト3.1
    2. テキスト3.2
2. テキスト4

<br>

## 折り畳み
**<u>コード</u>**
```
<details><summary> 折りたたみ </summary>
本文

- 箇条書き
</details>
```
<br>

**<u>表示結果</u>**  
<details><summary> 折りたたみ </summary>
本文

- 箇条書き
</details>

<br>

## 空行・改行
**<u>コード</u>**
```
1行目  (半角スペース2つ)
2行目  (Enter×2)

3行目<br>
4行目
<br>
<br>
5行目
```
**<u>表示結果</u>**   

1行目  
2行目

3行目<br>
4行目
<br>
<br>
5行目

<br>

## スペース
MarkDownでは4種類の空白がある。  
<br>

**<u>コード</u>**
```
空白なし
スペースキーによる空白␣半角␣␣全角
&thinsp;&nbspより狭い空白
&nbsp;半角スペースと同じサイズの空白
&ensp;半角スペースより少し広めの空白
&emsp;半角スペースよりさらに広めの空白　全角スペースとほぼ同じ幅
```
<br>

**<u>表示結果</u>**  

空白なし  
スペースキーによる空白 半角　全角  
&thinsp;&nbspより狭い空白  
&nbsp;半角スペースと同じサイズの空白  
&ensp;半角スペースより少し広めの空白  
&emsp;半角スペースよりさらに広めの空白　全角スペースとほぼ同じ幅  

<br>

## コードの挿入
ブロックはまとめて、インラインは文章中にコードを挿入する場合など。  
コード表示内ではMarkdownは効かず、空白やタブなどもそのまま表示される。
<br>

### ブロック
**<u>コード</u>**

\```  
 コード内容  
 \### 見出し  
\```
<br>

**<u>表示結果</u>**  
```
コード内容
### 見出し 
```
<br>

### インライン
**<u>コード</u>**
```
`コード<br> ###見出し`
```
<br>

**<u>表示結果</u>**  
`コード<br> ###見出し`

<br>

## リンクの挿入
クリックしたらそのページに飛ぶやつ。  
内部リンクは見出し名に `#` を1つだけつける。  
<br>

**<u>コード</u>**  
1. 外部リンク(URL) 2. 外部リンク(パス) 3. 内部リンク 4. 画像付きリンク

```
[Google](http://google.com/)                   
[README](./README.md)
[画像の挿入](#画像の挿入)                       
[![image.jpg](./image.jpg)](#画像の挿入)        
```
<br>

**<u>表示結果</u>**  
[Google](http://google.com/)  
[README](./README.md)  
[画像の挿入](#画像の挿入)  
[![image.jpg](./image.jpg)](#画像の挿入)

<br>

## 画像の挿入
MarkDown記法では画像のサイズや位置を変えられないのでHTMLタグで指定する方法がある。  
ただし、つかえない場合もあるので注意。
<br>

**<u>コード</u>**  
文法：`![代替テキスト](画像のURL "画像タイトル")`  
2,3行目はHTMLタグ
```
![image.jpg](./image.jpg)
<img src="./image.jpg" width="100px"/>
<img src="./image.jpg" style="opacity:0.3;"/>
```
<br>

**<u>表示結果</u>**  

![image.jpg](./image.jpg)
<img src="./image.jpg" width="50px"/>
<img src="./image.jpg" style="opacity:0.3;"/>

<br>

## テーブルの挿入
入力補完がある？
見出し行（1行目）と最初のレコード行（3行目）の間に、  
`|:--|--:|:--:|`
のような行が入るが、実際には表示されない。  
表内で表示される文字の位置に関係している。  
`-`の数は1つでいい。 
表内で一部装飾文字系は利用できる。

**<u>コード</u>**
```
| header     | ヘッダー     |見出し        |
|:-----------|------------:|:------------:|
|左寄せ      | 右寄せ      | 中央寄せ      |
| column     | column      | column       |
| *column*   | _column_    | **column**   |
| __column__ | `column`    | column       |
```
<br>

**<u>表示結果</u>**

| header     | ヘッダー     |見出し        |
|:-----------|------------:|:------------:|
|左寄せ      | 右寄せ      | 中央寄せ      |
| column     | column      | column       |
| *column*   | _column_    | **column**   |
| __column__ | `column`    | column       |
<br>

## 文字装飾
多いのでテーブルで表す。
最後のカスタムについてはHTMLのタグ。中央寄せなどもできる。
<br>

| 装飾内容 | コード | 表示結果 |
|:--:|:-:|:-:|
| 太字 | \*\*太字**<br> \_\_太字__ | **太字** |
| 斜体 | \*斜体* <br> \_斜体_| *斜体* |
| 太字+斜体 | \*\*\*太字+斜体***<br> or<br> \_\_\_太字+斜体___| ***太字+斜体*** |
| 打ち消し | \~~打ち消し~~<br> \<s>打ち消し\</s> | ~~打ち消し~~ |
| 下線 | \<u>下線\</u> | <u>下線</u> |
| 下付き | 下付き\<sub>2\</sub> | 下付き<sub>2</sub> |
| 上付き | 上付き\<sup>2\</sup> | 上付き<sup>2</sup> |
| カスタム | \<span style="color:green; font-size:10pt; border: 1px red solid; padding: 2px;">text\</span> | <span style="color:green; font-size:10pt; border: 1px red solid; padding: 2px;">text</span> |
<br>

## 水平線
3つ以上の-,*,_を入力する。
間に半角スペースがあってもよい。
<br>

**<u>コード</u>**
```
---
***
___
* * * *
```
<br>

**<u>表示結果</u>**  

---
***
___
* * * *

<br>

## エスケープ
マークダウン記号の前に `\` をつける

<br>

**<u>コード</u>**
```
\`インライン表示されなくなる`
***太字+斜体***
\***斜体のみ無効***
\*\**太字のみ無効***
\*\*\*太字+斜体***
```
<br>

**<u>表示結果</u>**  
\`インライン表示されなくなる`  
***太字+斜体***  
\***斜体のみ無効***   
\*\**太字のみ無効***   
\*\*\*太字+斜体無効***

<br>

## 引用

<br>

**<u>コード</u>**
```
> 引用文１
> 
> 引用文２
```
<br>

**<u>表示結果</u>**  
> 引用文１
> 
> 引用文２

<br>
<!---->

## コメントアウト  
表示はされないが残しておきたいときに。HTML表記が一番楽。
<br>

**<u>コード</u>**
```
<!-- コメントアウトしたい内容 複数行も可 -->

[](
単行コメントアウト
)

[](
複数行のときは\
改行直前に\
バックスラッシュ\
)
```
<br>

**<u>表示結果</u>**   
表示されない。Visual Code上ではHTML表記で書いた場合は緑文字になる。

<!-- コメントアウトしたい内容 複数行も可 -->

[](
単行コメントアウト
)

[](
複数行のときは\
改行直前に\
バックスラッシュ\
)

<br>

## 参考
[Markdown記法 サンプル集](https://qiita.com/tbpgr/items/989c6badefff69377da7) <br>
[Qiita マークダウン記法 一覧表・チートシート](https://qiita.com/kamorits/items/6f342da395ad57468ae3)  
[Markdownチートシート](https://atmarksharp.v01.jp/posts/markdown-cheat-sheet.html)  
[Markdown 記法 サンプル 一覧](https://qiita.com/Nukioman/items/01cd7ff819bc2e69b652#-%E3%82%A8%E3%82%B9%E3%82%B1%E3%83%BC%E3%83%97)  
[Markdown記法でコメントアウトする](https://qiita.com/yu0819ki/items/e1e1d20cedc68706ba23)