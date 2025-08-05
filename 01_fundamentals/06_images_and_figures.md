# 06: Images and Figures

This guide explains how to include images using the `graphicx` package and how to wrap them in the `figure` environment to add captions and labels.

---

## The `graphicx` Package

To include images, load the `graphicx` package in the preamble.

- `\usepackage{graphicx}`: Loads the `graphicx` package, enabling image-related commands.

- `\includegraphics[options]{filename}`: Inserts the image specified by `filename`. Common file types include PNG, JPG, and PDF. Image files should be placed in the same directory as the `.tex` file or referenced with a relative path (e.g., `path/to/filename`).

  | `options`       | Description                                                                                                                 |
  | --------------- | --------------------------------------------------------------------------------------------------------------------------- |
  | `width=length`  | Resizes the image to a specific `width` (see [04_lengths_and_dimensions.md](04_lengths_and_dimensions.md) for valid units). |
  | `height=length` | Resizes the image to a specific `height`(see [04_lengths_and_dimensions.md](04_lengths_and_dimensions.md) for valid units). |
  | `scale=factor`  | Scales the image by a `factor` (e.g., `0.5` for 50% of original size).                                                      |
  | `angle=degrees` | Rotates the image counter-clockwise by a number of `degrees`.                                                               |

```latex
\documentclass{article}
\usepackage{graphicx} % Load the package in the preamble

\begin{document}

Here is some text, followed by an image scaled to 80\% of the text width.

\includegraphics[width=0.8\textwidth]{example-image-a} % 'example-image-a' is a placeholder

\end{document}
```

---

## The `figure` Environment: The Float

To add a caption, create a label for referencing, and control placement, wrap the `\includegraphics` command inside a `figure` environment. This turns the image into a "floating" object.

- `\begin{figure}[placement]`: Begins the figure float. The optional `[placement]` specifier suggests where LaTeX should place the figure. Multiple specifiers can be combined (e.g., `[htbp]`), to give LaTeX options.
  
  | `placement` | Description                                            |
  | :---------: | ------------------------------------------------------ |
  |     `h`     | **h**ere: At the exact point in the code.              |
  |     `t`     | **t**op: At the top of the current or next page.       |
  |     `b`     | **b**ottom: At the bottom of the current or next page. |
  |     `p`     | **p**age: On a special page of floats.                 |
  |     `!`     | Overrides LaTeX's internal placement rules.            |

- `\caption{text}`: Adds a numbered caption to the figure.

- `\label{marker}`: Assigns a unique `marker` to the figure, which can then be referenced elsewhere.

- `\ref{marker}`: Prints the number of the figure associated with `marker`.

- `\centering`: Often used inside the `figure` environment to center the float.

```latex
\documentclass{article}
\usepackage{graphicx}

\begin{document}

As you can see in Figure~\ref{fig:sample}, the image is centered and has a caption.

\begin{figure}[h!] % Place it HERE if possible, overriding rules
  \centering
  \includegraphics[width=0.5\textwidth]{example-image-b}
  \caption{This is a sample figure.}
  \label{fig:sample} % Place label after caption
\end{figure}

\end{document}
```

---

## Side-by-Side Figures

To place figures next to each other, use the `minipage` environment. Each `\includegraphics` command is wrapped in its own `minipage`, and the `\hfill` command is used to push them apart. This entire construction can be placed inside a single `figure` environment to create a unified, captioned figure.

```latex
\documentclass{article}
\usepackage{graphicx}

\begin{document}

\begin{figure}[h!]
  \begin{minipage}[b]{0.48\textwidth}
    \centering
    \includegraphics[width=\textwidth]{example-image-a}
    \caption{The first image.}
    \label{fig:image1}
  \end{minipage}
  \hfill % Fills the space between the images
  \begin{minipage}[b]{0.48\textwidth}
    \centering
    \includegraphics[width=\textwidth]{example-image-b}
    \caption{The second image.}
    \label{fig:image2}
  \end{minipage}
\end{figure}

Figure~\ref{fig:image1} and Figure~\ref{fig:image2} are placed side-by-side.

\end{document}
```
