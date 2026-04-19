# PRML-Notes

基于 `ElegantBook 4.6` 的 PRML 课程笔记骨架，支持：

- 用 `main.tex` 一次性编译整本课程笔记
- 用每节课自己的 `lesson.tex` 单独编译单课 PDF
- 在 `config/` 中集中维护公共宏、盒子、定理环境、公式命令和代码样式

## 目录结构

```text
PRML-Notes/
├─ main.tex
├─ elegantbook.cls
├─ latexmkrc
├─ references.bib
├─ assets/branding/
├─ config/
└─ contents/week01/lessonXX-.../
   ├─ lesson.tex
   └─ figures/
```

## 编译命令

整本：

```powershell
latexmk -xelatex -outdir=build/book main.tex
```

单课：

```powershell
latexmk -xelatex -outdir=build/lesson01 contents/week01/lesson01-ml-intro/lesson.tex
```

## 命名约定

- 课程目录使用 ASCII slug，避免中文路径在 TeX 工具链中带来额外问题
- 正文标题保持中文
- 推荐标签前缀：
  - `chap:w01l01-*`
  - `sec:w01l01-*`
  - `fig:w01l01-*`
  - `eq:w01l01-*`

## 后续整理建议

- 直接在对应 `lesson.tex` 中逐段迁移 Markdown 内容
- 每课的图片、截图、实验结果统一放入同目录下的 `figures/`
- 新增课程时继续沿用 `contents/weekXX/lessonYY-slug/lesson.tex` 结构
