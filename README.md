Redirect Within An HTML Body
============================

For some reason or another, I have to do an automagic
redirect from within an html body. Typically, this is not
something you'd like to do.

You better do redirects within the html header
and you don't need javascript for this.

How To Do It
------------

Basically, I'm using this proposal from StackOverflow: [HTML redirect within body tags?](https://stackoverflow.com/a/7320206):

```html
<html>
<body>

<h1>Source</h1>

<p>This is the source document. Hopefully there will be an automagic redirect.</p>

<script type="text/javascript">
    window.location = "destination.html";
</script>

</body>
</html>
```

Idea: When you open the document within the browser, the javascript within the
body get's executed and the browser gets redirected to "destination.html".
Hopefully, a relative destination works within subfolders, too!

How To Test It
--------------

- Change your working directory to the one containing this README.md: `cd ~/git-projects/redirect-html-body`
- Start a python http server: `python -m http.server 8888`
- Open this URL within a browser: [http://localhost:8888](http://localhost:8888)
- Top level test
  - Click on "source.html"
  - Expect "destination.html" to be shown
- Subfolder test
  - Click on "subfolder"
  - Click on "source-subfolder.html"
  - Expect "destination-subfolder.html" to be shown

Files
-----

- ./README.md
- ./source.html
- ./destination.html
- ./subfolder/source-subdir.html
- ./subfolder/destination-subdir.html

Links
-----

- [HTML redirect within body tags?](https://stackoverflow.com/questions/7320145/html-redirect-within-body-tags)
- [Basic HTML Document](https://www.w3schools.com/html/tryit.asp?filename=tryhtml_basic_document)
