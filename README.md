# 1. Markdown TOC & Chapter Number

Add commands for table of contents (TOC) and chapter numbering to markdown.

## 1.1. Features

- Add command to generate a table of contents (TOC)
- Add command to add chapter numbers
- Control each depth independently
- Insert anchor in TOC

## 1.2. Demo

![demo](images/insert.gif)

### 1.2.1. Configuration

| Configuration ID                  | Description                                                                                            | Type   | Default |
| --------------------------------- | ------------------------------------------------------------------------------------------------------ | ------ | ------- |
| markdown-toc-num.tocDepthFrom     | TOC depth control, from [1-6]                                                                          | number | 2       |
| markdown-toc-num.tocDepthTo       | TOC depth control, to [1-6]                                                                            | number | 3       |
| markdown-toc-num.chapterDepthFrom | Chapter numbering depth control, from [1-6]                                                            | number | 2       |
| markdown-toc-num.chapterDepthTo   | Chapter numbering depth control, to [1-6]                                                              | number | 6       |
| markdown-toc-num.anchorMode       | Anchor style [`vscode,gitlab`, `vscode`, `gitlab`, `github`, `azure`, `embed`, `none`] | string | vscode  |

You can override them inline.

```md
<!-- TOC tocDepth:2..3 chapterDepth:2..6 anchorMode:embed -->

<!-- TOC tocDepthFrom:2 tocDepthTo:3 chapterDepthFrom:1 chapterDepthTo:6 anchorMode:embed -->

<!-- TOC tocDepthFrom:1 tocDepthTo:6 anchorMode:github -->
```

## Supplementary functions

### 1.2.2. Omit chapter in TOC

In case you are seeing unexpected TOC recognition, you can add a <!-- omit in toc --> comment above the list.

```md
# title

<!-- TOC tocDepth:2..3 chapterDepth:2..6 anchorMode:github -->

- [1. AAA](#user-content-1-aaa)
    - [1.2. AAA-2](#user-content-12-aaa-2)

<!-- /TOC -->

## 1. AAA

### 1.1. AAA-1 <!-- omit in toc -->

### 1.2. AAA-2
```

## 1.3. Anchor Styles

### 1.3.1. VSCode & GitLab style

With this style, anchors are started with `#`

```md
# title

<!-- TOC tocDepth:2..3 chapterDepth:2..6 anchorMode:vscode,gitlab -->

- [1. AAA](#1-aaa)
    - [1.1. AAA-1](#11-aaa-1)
    - [1.2. AAA-2](#12-aaa-2)

<!-- /TOC -->

## 1. AAA

### 1.1. AAA-1

### 1.2. AAA-2
```

### 1.3.2. GitHub style

With this style, anchors are started with `#user-content-`.

- With this sytle, the anchor links in TOC do NOT work in VSCode markdown preview.

```md
# title

<!-- TOC tocDepth:2..3 chapterDepth:2..6 anchorMode:github -->

- [1. AAA](#user-content-1-aaa)
    - [1.1. AAA-1](#user-content-11-aaa-1)
    - [1.2. AAA-2](#user-content-12-aaa-2)

<!-- /TOC -->

## 1. AAA

### 1.1. AAA-1

### 1.2. AAA-2
```

### 1.3.2. Azure DevOps style

With this style, anchors are started with `#user-content-`.

- With this sytle, the anchor links in TOC do NOT work in VSCode markdown preview.

```md
# title

<!-- TOC tocDepth:2..3 chapterDepth:2..6 anchorMode:azure -->

- [1. AAA](#user-content-1.-aaa)
    - [1.1. AAA-1](#user-content-1.1.-aaa-1)
    - [1.2. AAA-2](#user-content-1.2.-aaa-2)

<!-- /TOC -->

## 1. AAA

### 1.1. AAA-1

### 1.2. AAA-2
```

### 1.3.3. Embed style

With this style, html div elements are inserted automatically.

```md
<div id="toc-title" />

# title

<!-- TOC tocDepth:2..3 chapterDepth:2..6 anchorMode:embed -->

- [1. AAA](#toc-1--aaa)
    - [1.1. AAA-1](#toc-1-1--aaa-1)
    - [1.2. AAA-2](#toc-1-2--aaa-2)

<!-- /TOC -->

<div id="toc-1--aaa" />

## 1.1. AAA

<div id="toc-1-1--aaa-1" />

### 1.1.1. AAA-1

<div id="toc-1-2--aaa-2" />

### 1.1.2. AAA-2
```

## 1.4. Release Notes

- See [changelog](CHANGELOG.md).

## 1.5. Links

- [Source Code](https://github.com/takumisoft68/vscode-markdown-toc-num)
- [Marketplace](https://marketplace.visualstudio.com/items?itemName=TakumiI.markdown-toc-num)

## 1.6. License

Apache 2.0, See [LICENSE](LICENSE) for more information.
