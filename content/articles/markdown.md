---
title: "Markdown 記法"
description: この記事では、Markdown を記入すると、どのように表示されるかについての一覧をまとめました。
emoji: ""
tags:
    - Markdown
    - 記事の確認
createdAt: 2021/4/18
updatedAt: 2021/4/18
---

## 見出し

``` markdown
# H1
## H2
### H3

```

# H1
## H2
### H3

## 強調、斜体、打消し線

```markdown
// 斜体
*This is test*
// 強調
**これはテストです。**
// 打消し線
~消されているかチェック~
```

*This is test*
**これはテストです。**
~消されているかチェック~
## リスト

入力方法

```markdown
- First List 
- Second List
    - sample 1
    - sample 2 
        - sample3
        - sample4
```
- First List 
- Second List
    - sample 1
    - sample 2 
        - sample3
        - sample4

## テーブル

``` markdown

| column１ | column２ | column3 |
|:-----------|------------:|:------------:|
|左端|右端|真ん中|
|へ寄る|へ寄る|に置かれる|
```
| column１ | column２ | column3 |
|:-----------|------------:|:------------:|
|左端|右端|真ん中|
|へ寄る|へ寄る|に置かれる|

## 分割線


```markdown
------
```

------

## 引用

```markdown 
> サンプル
>>入れ子でどんどん記入される
```
> サンプル
>>入れ子でどんどん記入される

## コードブロック

>基本的に、Markdownはファイル名やコードブロック内の特定の行のハイライトをサポートしていません。
>しかし、このモジュールは独自のカスタム構文でそれを可能にします。
> - 中括弧内のハイライトしたい行番号を書く
> - 角括弧内にファイル名を書く
>(Nuxt Content 公式ドキュメントより引用)

```markdown
    ```js{1,3-5}[server.js]
    const http = require('http')
    const bodyParser = require('body-parser')

    http.createServer((req, res) => {
    bodyParser.parse(req, (error, body) => {
    res.end(body)
    })
    }).listen(3000)
    ```
```

```js{1,3-5}[server.js]

const http = require('http')
const bodyParser = require('body-parser')

http.createServer((req, res) => {
bodyParser.parse(req, (error, body) => {
res.end(body)
})
}).listen(3000)

```

## 数式

```markdown
 y = \frac{1}{x+1}
```

$$
 y = \frac{1}{x+1}
$$

## 埋め込み

### Twitter
URL を埋め込むだけで表示されます！
```markdown 
https://twitter.com/31415O_Kyo/status/1264947520423129088
```
https://twitter.com/31415O_Kyo/status/1264947520423129088

### Youtube 

```markdown
<youtube-embed vid="JeyVU4nMWCg"></youtube-embed>
``` 
とすると、しっかりと埋め込むことができます。

<youtube-embed vid="JeyVU4nMWCg"></youtube-embed>

### 独自コンポーネント
この Nuxt Content では、`/content/global`に設定された `.vue` ファイルを読み込み、Nuxt Content 下で使用できる Vue コンポーネントを用意してくれます。

```markdown[sample.md]
```vue[/content/global/sample.vue]
<template>

</template>
<script>

</script> ```
```
