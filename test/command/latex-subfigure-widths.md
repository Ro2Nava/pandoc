The widths of subfigures and minipages are kept as a "width"
attribute, which the LaTeX writer uses for the subfigures.

```
% pandoc -f latex -t native
\begin{figure}
  \begin{minipage}{0.2\textwidth}
    \includegraphics[height=2cm]{a.png}
  \end{minipage}
  \begin{subfigure}{0.6\textwidth}
    \includegraphics[width=\textwidth]{b.png}
    \caption{B}
  \end{subfigure}
  \caption{Both}
\end{figure}
^D
[ Figure
    ( "" , [] , [] )
    (Caption Nothing [ Plain [ Str "Both" ] ])
    [ Div
        ( "" , [ "minipage" ] , [ ( "width" , "20%" ) ] )
        [ Plain
            [ Image
                ( "" , [] , [ ( "height" , "2cm" ) ] )
                []
                ( "a.png" , "" )
            ]
        ]
    , Figure
        ( "" , [] , [ ( "width" , "60%" ) ] )
        (Caption Nothing [ Plain [ Str "B" ] ])
        [ Plain
            [ Image
                ( "" , [] , [ ( "width" , "100%" ) ] )
                []
                ( "b.png" , "" )
            ]
        ]
    ]
]
```

```
% pandoc -f latex -t latex
\begin{figure}
  \begin{minipage}{0.2\textwidth}
    \includegraphics[height=2cm]{a.png}
  \end{minipage}
  \begin{subfigure}{0.6\textwidth}
    \includegraphics[width=\textwidth]{b.png}
    \caption{B}
  \end{subfigure}
  \caption{Both}
\end{figure}
^D
\begin{figure}
\centering
\begin{minipage}[t]{0.2\linewidth}
\includegraphics[width=\linewidth,height=2cm,keepaspectratio]{a.png}
\end{minipage}
\hfill
\begin{subfigure}[t]{0.6\linewidth}
\centering
\includegraphics[width=1\linewidth,height=\textheight,keepaspectratio]{b.png}
\caption{B}
\end{subfigure}
\caption{Both}
\end{figure}
```
