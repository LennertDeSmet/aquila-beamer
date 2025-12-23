# Aquila-beamer

Aquila-beamer is part of the Aquila family of modern LaTeX templates.
It aims to follow and capture the principles for science communication as laid out by [Jean-luc Doumont](https://www.principiae.be/).


## How to start using Aquila-beamer

The template is packaged as a standard beamer theme, consisting of a number of `.sty` files and a `macros.tex` file containing useful environments and commands.
These files are sufficient to start making your own presentations using Aquila-beamer. 
An Aquila-beamer presentation is initialised by a quick `\usetheme{aquila}` command.


## Making sure you are using Aquila

Your shiny new beamer document should always start by calling the Aquila theme and its macros. By default, the fontsize is set to 10pt and the aspect ratio of each slide is nice and modern 16:9.

```
\documentclass[10pt, aspectratio=169]{beamer}
\usetheme{aquila}

\input{macros}
```

## The title slide

Your title slide should only be automatically built using `\maketitle`, for example

```
\titlegraphic{
    \includegraphics[height=3em]{images/your_image}
}

\title{Insert your title}
\subtitle{Insert your optional subtitle}
\institute{Insert your optional institute}
\author{Insert your name here}

\maketitle
```


## A normal beamer frame

All your regular slides will use regular old beamer frames. A quick and easy slide can be made with the important `\goldencolumn` command.
This command models two side-by-side columns filled with the provided content through two arguments.
For example, the following yields a simple frame with a keyword in the left column and some supporting text in the right column.

```
\begin{frame}
\frametitle{This is a dummy title}

\goldencolumn{
    % Content of the left column
    \shift{\colouraccent{\accentcolour}{Keyword}
}{
    % Content of the right column
    \emph{This is an important keyword} \\
    because it highlights a key aspect of this slide
}
\end{frame}
```

*Note: to be aesthetically pleasing, the command `\goldencolumn` distributes your columns according to [the golden ratio](https://en.wikipedia.org/wiki/Golden_ratio).*

There are a number of useful environment defined in the `beamerthemeaquila.sty` file.
Please have a look at their definition and the example presentations to see how to best use them.
A more thorough example and documentation will be provided in the near future.
A couple of smaller examples are given in the [examples](examples) folder.

## The end page

Your end page is just another beamer frame, but it uses the `stopframe` environment to repeat the title graphics.
You can use this space to show QR codes and can keep it showing for a while after your presentation has ended, for example during Q&A.

```
\begin{stopframe}

\attentioncenter{
    Please ask all your questions now!
}

\end{stopframe}
```

## Feedback, thoughts and recommendations

This template is meant as a starting point for making clean presentations in LaTeX. If you don't like certain aspects, you can change things to your hearts' desire. I also always welcome feedback and recommendations. For example, for more useful environments or automations.

*If you encounter any weird behaviour or face random issues, please also let me know. LaTeX can act in mysterious ways sometimes.*