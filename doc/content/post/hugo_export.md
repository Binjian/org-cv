+++
title = "Markdown Hugo Exporter"
author = ["Óscar Nájera"]
draft = false
weight = 1005
+++

If your target is not a PDF file but a website, this exporter extends the
[ox-hugo](https://ox-hugo.scripter.co/) exporter backend. So be sure to install that too.

To export, there is nothing fancy to keep track of, but as an example I
exclude some tags during export.

```emacs-lisp
(let ((org-export-exclude-tags '("noexport" "latexonly")))
     (org-export-to-file 'hugocv "hugocv.md"))
```

You are responsible for styling your website. Use all the CSS magic you know.
Each entry is inside a `div` container and each element of the properties has
its own class.

Make sure that your hugo config has the markup parser attributes active

```yaml
markup:
  goldmark:
    parser:
      attribute:
        title: true
        block: true
```

<iframe src="/post/cv/" title="rendered CV"></iframe>
