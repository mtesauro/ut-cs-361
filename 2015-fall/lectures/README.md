The lectures in this directory can be converted from Markdown to Reveal.js by using the following command:

```
$ pandoc -s --self-contained --mathjax -i -t revealjs lecture-template.md -o Lecture-template.html
```

**Note** The pandoc program is required and can be installed from your distro repo or from http://pandoc.org/

The command also assumes a working directory which has the following prep work already completed:

```
$ mkdir lectures
$ cd lectures
$ git clone https://github.com/hakimel/reveal.js.git
$ cp reveal.js/css/reveal.css reveal.js/css/reveal.min.css
$ cp reveal.js/js/reveal.js reveal.js/js/reveal.min.js
```

Note: The reveal.js directory in this repository has already been 'prepared'.
