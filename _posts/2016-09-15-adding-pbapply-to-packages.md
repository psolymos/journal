---
title: "Adding pbapply to R packages"
layout: blog
category: poster
tags: [Scribus, layout]
comments: false
published: true
---

There are two ways of adding the pbapply package to another package.

## 1. Suggests: pbapply

Add pbapply to the Suggests field in the `DESCRIPTION`.

Use a conditional statement in your code to fall back on a base function in case of pbapply not installed:

```
out <- if (requireNamespace("pbapply")) {
   pbapply::pblapply(X, FUN, ...)
} else {
   lapply(X, FUN, ...)
}
```

See a small example package [here](https://github.com/psolymos/pbapplySuggests).

## 2. Depends/Imports: pbapply

Add pbapply to the Depends or Imports field in the `DESCRIPTION`.

Use a the pbapply functions either as `pbapply::pblapply()` or specify them in the `NAMESPACE` (`importFrom(pbapply, pblapply)`) and
use it as `pblapply()` (without the `::`).

## Customizing the progress bar

Specify the progress bar options in the `zzz.R` file of the package:

```
.onAttach <- function(libname, pkgname){
    options("pboptions" = list(
        type = if (interactive()) "timer" else "none",
        char = "-",
        txt.width = 50,
        gui.width = 300,
        style = 3,
        initial = 0,
        title = "R progress bar",
        label = "",
        nout = 100L))
    invisible(NULL)
}
```

This will set the options and pbapply will not override when loaded.

See a small example package [here](https://github.com/psolymos/pbapplyDepends).

## Suppressing the progress bar

Suppressing the progress bar is sometimes handy. By default, progress bar is suppressed when `!interactive()`.
In other instances, put this inside a function:

```
pbo <- pboptions(type = "none")
on.exit(pboptions(pbo), add = TRUE)
```
