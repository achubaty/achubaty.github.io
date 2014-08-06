---
layout: post
status: publish
published: true
title: ! "Essential software for biology grad students: Part III Writing
  Tools"
author: Alex Chubaty
date: 2013-07-15
---

Whenever I used to sit down in front of the computer to write anything other than an email, I would immediately open Microsoft Word and start clacking away on the keyboard. When I switched operating systems (away from Windows) I began using Open Office Writer and even now I still use Libre Office Writer for some of my writing needs. Each of these word processors offer similar sets of tools and can effectively be used for a wide range of writing tasks, from letters to essays, yet I feel most people use Word not because it's always the best tool for the job, but because it's ubiquitous and familiar.

There are plenty of limitations to using Word (and Writer), especially when it comes to 1) complex formatting (especially working with equations), 2) sharing documents and collaborating with others, 3) version control, and 4) converting to different file types.

To overcome these limitations and to make writing easier, I want to share my favourite writing tools -- <a href="http://daringfireball.net/projects/markdown/">Markdown</a> and <a href="http://www.latex-project.org/">LaTeX</a>, which use plain-text file formats and can be easily converted to any other file type with <a href="http://johnmacfarlane.net/pandoc/">Pandoc</a>.

The use of plain text format is important. <a href="http://alexchubaty.com/index.php/2013/07/essential-software-for-biology-grad-students-part-ii-backups-and-sync/">Version control software</a> like <a href="https://github.com/">Git</a> works perfectly with plain-text files, showing you which lines have changed between versions. However, this version differencing isn't possible using *binary* file formats like those used by Word (.doc and .docx). Additionally, you can open plain-text files on any computer without any special (proprietary!) software, so 10 years from now when you want to revisit an old document, you can do so without having to ensure you keep an old computer with old software around.

### You shouldn't have to worry about formatting

Markdown and LaTeX files are markup languages, which means that the text in a document is annotated in a way that indicates the structure and formatting of the text, using tags. For example, bolded text in <acronym title="HyperText Markup Language">HTML</acronym> (used for webpages) would be written like this: `<b>bold text here</b>`. Markdown makes this even simpler, so you spend less time formatting your document while writing, which means you can focus on actually writing rather than formatting.

It's fantastically easy to learn the markdown syntax and create documents with markdown:

```
# Simple Headings

## And Subheadings

Here's some paragraph text with some words *emphasized* with italics.

Others are **bolded** for emphasis.

### Don't Forget Subsubheadings

You can keep adding headings and subheadings by using more hashes!

# What about lists?

- lists are easy to make
- just use 4 spaces for sub-points
- numbered lists are also supported

# Markdown is great for embedding code too

You just put your code `inside the backticks` or use blocks of code.

# Blockquotes are just as easy
> Look at me go!

Check out [Markdown basics](http://daringfireball.net/projects/markdown/basics) to learn more.
```

The markdown text above produces this:

<a href="/uploads/2013/07/markdown.png"><img class="size-medium wp-image-229 aligncenter" alt="markdown" src="/uploads/2013/07/markdown-201x300.png" width="201" height="300" /></a>

And it doesn't stop there. Markdown also supports citations and references with bibtex, which means that you can easily write up that thesis chapter or manuscript, not worrying about the final format until you're ready to convert your markdown file to whatever file format you require.

### Equations and more!

Markdown is incredibly easy to learn, and will cover most of your writing needs, but if you are (or will be) making heavy use of code, equations, and statistics, then you need to be using LaTeX. The syntax is more complex than Markdown, but it hands-down beats MS Word for formatting, equation typesetting, and portability between computers. I've done all my thesis stuff, including manuscripts, in LaTeX and output as PDF or converted to .doc format when needed.

<a href="/uploads/2013/07/mpb-game-dpe.png"><img class="aligncenter  wp-image-232" title="a LaTeX equation" alt="a LaTeX equation" src="/uploads/2013/07/mpb-game-dpe-1024x231.png" width="625" height="140" /></a>

To make your introduction to LaTeX easier, I recommend starting out using an editor like <a href="http://www.xm1math.net/texmaker/">Texmaker</a>, which is cross platform and come with a GUI to assist with inserting various document elements. If you will be using equations, you'll want to make sure you use the `amsmath` package. There are a lot of other great packages for latex which will help with everything from document formatting and layout, to citation formatting with bibtex, as well as <a href="http://texblog.org/2012/06/21/classic-coffee-stains-with-latex/">adding coffee stains to your pdf documents</a>. I also recommend checking out the <a href="http://tex.stackexchange.com/">TeX Stack Exchange</a> site to get Q&amp;A help with everything (La)TeX.

Going further and using R+LaTeX+Sweave and you've got yourself a full-on powerhouse of reproducible, portable document publishing. Also remember, .tex files are simply a type of text file, so they work with version control software like Git.

### File conversion with Pandoc

Lastly, I'll quickly mention that the best way to take your Markdown and LaTeX documents and convert them to almost any type of document file including (e.g., .tex, .html, .pdf, .doc, .odt) is using Pandoc. It's a simple command-line tool, and <a href="http://johnmacfarlane.net/pandoc/README.html">using it is incredibly straightforward</a>.

### Use them everyday

Like any new software, there is a bit of a learning curve, so the best way to get used to it is simply to use it. Using markdown for everyday notetaking or creating and maintaining your cv with markdown/LaTeX are great ways to gain familiarity with these tools. Start using them today. Start using them with your collaborators. You (and they) won't be disappointed.
