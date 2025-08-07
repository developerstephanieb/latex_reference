# 07: Tables

This guide explains how to create tables using the `tabular` environment and how to wrap them in the `table` environment to add captions and labels.

---

## Creating Tables

The `tabular` environment is the tool for creating the grid and content of a table.

- `\begin{tabular}{cols}`: Creates a table. The `cols` argument defines the column layout.

  |     `cols`      | Description                                                                                    |
  | :-------------: | ---------------------------------------------------------------------------------------------- |
  |       `l`       | A left-aligned column.                                                                         |
  |       `c`       | A center-aligned column.                                                                       |
  |       `r`       | A right-aligned column.                                                                        |
  |   `p{width}`    | A paragraph column of a fixed [`width`](04_lengths_and_dimensions.md). Text will auto-wrap.    |
  | `@{expression}` | Replaces inter-column space with `expression` (e.g. `@{ -- }`). Use `@{}` to remove the space. |
  |      `\|`       | Adds a vertical line between columns.                                                          |

- `&`: Separates content into the next column.

- `\\`: Ends the current row.

- `\hline`: Adds a horizontal line across rows.

```latex
\documentclass{article}

\begin{document}

Here is a simple table:
\begin{tabular}{lcr} % 3 columns: left, center, right
    Name   & Score & Grade  \\
    Alice  & 85    & B      \\
    Jordan & 92    & A      \\
\end{tabular}

Here is a table with lines:
\begin{tabular}{|l|c|r|} % Vertical lines between all columns
    \hline
    \textbf{Item} & \textbf{Quantity} & \textbf{Price} \\
    \hline
    Bread         & 1                 & \$3.50         \\
    Milk          & 2                 & \$2.99         \\
    \hline
\end{tabular}

Here is a table using @{} and p{}:
\begin{tabular}{l@{ -- }p{4cm}}
    Label & Description                                \\
    Name  & A string identifying the person or object. \\
    Age   & The number of full years since birth.      \\
\end{tabular}

\end{document}
```

---

## Spanning Columns

For more complex tables, a cell may need to span multiple columns.

- `\multicolumn{num}{cols}{text}`: Creates a single cell that spans `num` columns.
  
  | Argument | Description                                     |
  | -------- | ----------------------------------------------- |
  | `num`    | The number of columns to span.                  |
  | `cols`   | The column specifier for this new, merged cell. |
  | `text`   | The content of the cell.                        |

- `\cline{i-j}`: Draws a horizontal line spanning columns `i` through `j`. Useful when a full `\hline` is not needed.

```latex
\documentclass{article}

\begin{document}

Here is a table with merged header columns and a partial horizontal line:
\begin{tabular}{|l|c|c|}
    \hline
    \textbf{Item} & \multicolumn{2}{c|}{\textbf{Details}}          \\
    \cline{2-3}
                  & Quantity                              & Price  \\
    \hline
    Bread         & 1                                     & \$3.50 \\
    Milk          & 2                                     & \$2.99 \\
    \hline
\end{tabular}

\end{document}
```

---

## Spanning Rows

To create cells that spans multiple rows, load the `multirow` package in the preamble.

- `\usepackage{multirow}`: Loads the `multirow` package, enabling the `\multirow` command.

- `\multirow{num}{width}{text}`: Creates a cell that spans `num` rows.
  
  | Argument | Description                                                                                          |
  | -------- | ---------------------------------------------------------------------------------------------------- |
  | `num`    | The number of columns to span.                                                                       |
  | `width`  | The [width](04_lengths_and_dimensions.md) of the content. Use `*` for the natural width of the text. |
  | `text`   | The content of the cell.                                                                             |

```latex
\documentclass{article}
\usepackage{multirow} % Load the 'multirow' package in the preamble

\begin{document}

\begin{tabular}{|l|c|c|}
    \hline
    \textbf{Category}      & \textbf{Item} & \textbf{Price} \\
    \hline
    \multirow{2}{*}{Dairy} & Milk          & \$2.99         \\ % Spans 2 rows
                           & Cheese        & \$4.50         \\
    \hline
    Bakery                 & Bread         & \$3.50         \\
    \hline
\end{tabular}

\end{document}
```

---

## The `table` Environment: The Float

To add a caption, create a label for referencing, and control placement, wrap the `tabular` environment inside a `table` environment. This turns the table into a "floating" object.

- `\begin{table}[placement]`: Begins the table float. The optional `[placement]` specifier suggests where LaTeX should place the table. Multiple specifiers can be combined (e.g., `[htbp]`), to give LaTeX options.
  
  | `placement` | Description                                            |
  | :---------: | ------------------------------------------------------ |
  |     `h`     | **h**ere: At the exact point in the code.              |
  |     `t`     | **t**op: At the top of the current or next page.       |
  |     `b`     | **b**ottom: At the bottom of the current or next page. |
  |     `p`     | **p**age: On a special page of floats.                 |
  |     `!`     | Overrides LaTeX's internal placement rules.            |

- `\caption{text}`: Adds a numbered caption to the table.

- `\label{marker}`: Assigns a unique `marker` to the table, which can be referenced elsewhere.

- `\ref{marker}`: Prints the number of the table associated with `marker`.

- `\centering`: Often used inside the `table` environment to center the `tabular` block.

```latex
\documentclass{article}

\begin{document}

As shown in Table~\ref{tab:shopping_list}, the total cost is important.

\begin{table}[h!] % Place it HERE if possible, overriding rules
    \centering
    \begin{tabular}{|l|c|r|}
        \hline
        \textbf{Item} & \textbf{Quantity} & \textbf{Price} \\
        \hline
        Bread         & 1                 & \$3.50         \\
        Milk          & 2                 & \$2.99         \\
        \hline
    \end{tabular}
    \caption{A Sample Shopping List}
    \label{tab:shopping_list} % Place label after caption
\end{table}

\end{document}
```

---

## Side-by-Side Tables

To place tables next to each other, use the `minipage` environment. Each `tabular` environment is wrapped in its own `minipage`, and the `\hfill` command is used to push them apart. This entire construction can be placed inside a single `table` environment to create a unified, captioned table.

```latex
\documentclass{article}

\begin{document}

\begin{table}[h!]
    \begin{minipage}[b]{0.48\textwidth}
        \centering
        \begin{tabular}{|c|c|} \hline A & B \\ \hline 1 & 2 \\ \hline \end{tabular}
        \caption{First Floating Table}
        \label{tab:float1}
    \end{minipage}
    \hfill % Fills the space between the images
    \begin{minipage}[b]{0.48\textwidth}
        \centering
        \begin{tabular}{|c|c|} \hline C & D \\ \hline 3 & 4 \\ \hline \end{tabular}
        \caption{Second Floating Table}
        \label{tab:float2}
    \end{minipage}
\end{table}

Table~\ref{tab:float1} and Table~\ref{tab:float2} are placed side-by-side.

\end{document}
```

---

## The `booktabs` Package

To create professional, publication-quality tables with better spacing and visual appeal, load the `booktabs` package in the preamble. The package discourages the use of vertical lines.

- `\usepackage{booktabs}`: Loads the `booktabs` package, enabling its specialized rule commands.

- `\toprule`: A thicker rule for the top of the table, placed above the header row.

- `\midrule`: A standard-thickness rule used to separate the header from the table body.

- `\bottomrule`: A thicker rule for the bottom of the table, placed after the last row of data.

- `\cmidrule(trim){i-j}`: Draws a partial rule spanning from column `i` to column `j`.

  | `trim` | Description                                      |
  | ------ | ------------------------------------------------ |
  | `l`    | Trims the line on the left side.                 |
  | `r`    | Trims the line on the right side.                |
  | `lr`   | Trims the line on both the left and right sides. |

```latex
\documentclass{article}
\usepackage{booktabs} % Load the 'booktabs' package in the preamble

\begin{document}

\begin{table}[h!]
    \centering
    \caption{Quarterly Sales Data}
    \begin{tabular}{lrrr}
        \toprule
        \textbf{Region} & \multicolumn{3}{c}{\textbf{Quarter}}                       \\
        \cmidrule(lr){2-4} % A trimmed rule under columns 2 through 4
                        & Q1                                   & Q2       & Q3       \\
        \midrule
        North           & \$10,000                             & \$12,000 & \$15,000 \\
        South           & \$8,000                              & \$9,000  & \$11,000 \\
        East            & \$11,000                             & \$13,000 & \$14,000 \\
        \bottomrule
    \end{tabular}
\end{table}

\end{document}
```
