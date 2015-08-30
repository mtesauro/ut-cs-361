The lectures in this directory can be converted from Markdown to Reveal.js by using the followig command:

```
$ pandoc -s --self-contained --mathjax -i -t revealjs template-deck.md -o template-deck.html
```

This assumes a working directory which has the following prep work already completed:

```
$ mkdir lectures
$ git clone https://github.com/hakimel/reveal.js.git
$ 
```

