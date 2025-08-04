# 07: Tables

This guide explains how to create tables using the `tabular` environment and how to wrap them in the `table` environment to add captions and labels.

---

## The `tabular` Environment

The `tabular` environment is the core tool for creating the grid and content of a table.

- `\begin{tabular}{cols}`: Creates a table. The `{cols}` argument defines the column layout.

  |     `cols`      | Description                                                                                                                                 |
  | :-------------: | ------------------------------------------------------------------------------------------------------------------------------------------- |
  |       `l`       | A left-aligned column.                                                                                                                      |
  |       `c`       | A center-aligned column.                                                                                                                    |
  |       `r`       | A right-aligned column.                                                                                                                     |
  |   `p{width}`    | A paragraph column of a fixed width. Text will auto-wrap. See [04_lengths_and_dimensions.md](04_lengths_and_dimensions.md) for valid units. |
  | `@{expression}` | Replaces inter-column space with `expression` (e.g. `@{ -- }`). Use `@{}` to remove the space.                                              |
  |      `\|`       | Adds a vertical line between columns.                                                                                                       |

- Columns (`&`): Separates content into the next column.

- Rows (`\\`): Ends the current row.

- Horizontal Lines (`\hline`): Adds a horizontal line across the table.

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

## Spanning Columns and Rows

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

Here is the same table with a partial horizontal line:
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

- `\label{marker}`: Assigns a unique `marker` to the table, which you can reference elsewhere.

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
    \label{tab:shopping_list}
\end{table}

Some more text following the table.

\end{document}
```
