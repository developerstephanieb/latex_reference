# 06: Tables

This guide covers the tabular environment, the standard LaTeX tool for creating tables.

---

## The `tabular` Environment

The `tabular` environment is used to create tables.

- `\begin{tabular}{cols}`: Creates a table.

  | `cols` | Description              |
  | :----: | ------------------------ |
  |  `l`   | A left-aligned column.   |
  |  `c`   | A center-aligned column. |
  |  `r`   | A right-aligned column.  |

- Columns (`&`): Separates content into the next column.

- Rows (`\\`): Ends the current row.

- Vertical Lines (`|`): Adds a vertical line between columns.

- Horizontal Lines (`\hline`): Adds a horizontal line across the table.

```latex
\documentclass{article}

\begin{document}

Here is a simple table:
\begin{tabular}{lcr} % 3 columns: left, center, right
  Item & Quantity & Price \\ % Row 1
  Bread & 1 & \$3.50 \\ % Row 2
  Milk & 2 & \$2.99 \\ % Row 3
\end{tabular}

Here is a table with lines:
\begin{tabular}{|l|c|r|} % Vertical lines between all columns
  \hline
  \textbf{Item} & \textbf{Quantity} & \textbf{Price} \\
  \hline
  Bread & 1 & \$3.50 \\
  Milk & 2 & \$2.99 \\
  \hline
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

Here is a table that spans multiple columns:
\begin{tabular}{|l|c|c|}
  \hline
  \textbf{Item} & \multicolumn{2}{c|}{\textbf{Details}} \\ % Spans 2 columns
  \hline
   & \textbf{Quantity} & \textbf{Price} \\ % Note the empty first cell
  \hline
  Bread & 1 & \$3.50 \\
  Milk & 2 & \$2.99 \\
  \hline
\end{tabular}

Here is the same table with a partial horizontal line:
\begin{tabular}{|l|c|c|}
  \hline
  \textbf{Item} & \multicolumn{2}{c|}{\textbf{Details}} \\
  \cline{2-3}
               & Quantity & Price \\
  \hline
  Bread        & 1        & \$3.50 \\
  Milk         & 2        & \$2.99 \\
  \hline
\end{tabular}

\end{document}
```

---

## The `table` Environment

To add a caption, create a label for referencing, and control placement, wrap the `tabular` environment inside a `table` environment. This turns the table into a "floating" object.

- `\begin{table}[placement]`: Begins the table float. The optional `[placement]` specifier suggests where LaTeX should place the table. Multiple specifiers can be combined (e.g., [htbp]), to give LaTeX options.
  
  | `placement` | Description                                            |
  | :---------: | ------------------------------------------------------ |
  |     `h`     | **h**ere: At the exact point in the code.              |
  |     `t`     | **t**op: At the top of the current or next page.       |
  |     `b`     | **b**ottom: At the bottom of the current or next page. |
  |     `p`     | **p**age: On a special page of floats.                 |
  |     `!`     | Overrides LaTeX's internal placement rules.            |

- `\caption{text}`: Adds a numbered caption to the table.

- `\label{marker}`: Assigns a unique marker to the table, which you can reference elsewhere.

- `\ref{marker}`: Prints the number of the table associated with marker.

- `\centering`: Often used inside the table environment to center the tabular block.

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