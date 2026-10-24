# Figure with one image, caption and label

```
% pandoc -f latex -t native
\begin{document}
  \begin{figure}
    \includegraphics{../../media/rId25.jpg}
    \caption{CAP}
    \label{LAB}
  \end{figure}
\end{document}
^D
[ Figure
    ( "LAB" , [] , [] )
    (Caption Nothing [ Plain [ Str "CAP" ] ])
    [ Plain
        [ Image ( "" , [] , [] ) [] ( "../../media/rId25.jpg" , "" )
        ]
    ]
]
```

# Nested figures

```
% pandoc -f latex -t native
\begin{figure}
  \begin{subfigure}[b]{0.5\textwidth}
    \begin{subfigure}[b]{0.5\textwidth}
      \centering
      \includegraphics{test/media/rId25.jpg}
      \caption{CAP1.1}
    \end{subfigure}
    \begin{subfigure}[b]{0.5\textwidth}
      \centering
      \includegraphics{test/media/rId25.jpg}
      \caption{CAP1.2}
    \end{subfigure}
    \caption{CAP1}
    \label{fig:inner1}
  \end{subfigure}
  \begin{subfigure}[b]{0.5\textwidth}
    \includegraphics{test/media/rId25.jpg}
    \caption{CAP2}
    \label{fig:inner2}
  \end{subfigure}
  \caption{CAP}
  \label{fig:outer}
\end{figure}
^D
[ Figure
    ( "fig:outer" , [] , [] )
    (Caption Nothing [ Plain [ Str "CAP" ] ])
    [ Figure
        ( "fig:inner1" , [] , [ ( "width" , "50%" ) ] )
        (Caption Nothing [ Plain [ Str "CAP1" ] ])
        [ Figure
            ( "" , [] , [ ( "width" , "50%" ) ] )
            (Caption Nothing [ Plain [ Str "CAP1.1" ] ])
            [ Plain
                [ Image
                    ( "" , [] , [] ) [] ( "test/media/rId25.jpg" , "" )
                ]
            ]
        , Figure
            ( "" , [] , [ ( "width" , "50%" ) ] )
            (Caption Nothing [ Plain [ Str "CAP1.2" ] ])
            [ Plain
                [ Image
                    ( "" , [] , [] ) [] ( "test/media/rId25.jpg" , "" )
                ]
            ]
        ]
    , Figure
        ( "fig:inner2" , [] , [ ( "width" , "50%" ) ] )
        (Caption Nothing [ Plain [ Str "CAP2" ] ])
        [ Plain
            [ Image ( "" , [] , [] ) [] ( "test/media/rId25.jpg" , "" )
            ]
        ]
    ]
]
```

# Subfigures are lettered within their figure

```
% pandoc -f latex -t markdown
\begin{figure}
  \begin{subfigure}{0.5\textwidth}
    \includegraphics{a.png}
    \caption{Left}
    \label{fig:left}
  \end{subfigure}
  \begin{subfigure}{0.5\textwidth}
    \includegraphics{b.png}
    \caption{Right}
    \label{fig:right}
  \end{subfigure}
  \caption{Both}
  \label{fig:both}
\end{figure}
\begin{figure}
  \includegraphics{c.png}
  \caption{Next}
  \label{fig:next}
\end{figure}
See \ref{fig:both}, \ref{fig:right} and \ref{fig:next}.
^D
<figure id="fig:both">
<figure id="fig:left" style="width:50%;">
<img src="a.png" />
<figcaption>Left</figcaption>
</figure>
<figure id="fig:right" style="width:50%;">
<img src="b.png" />
<figcaption>Right</figcaption>
</figure>
<figcaption>Both</figcaption>
</figure>

![Next](c.png){#fig:next}

See [1](#fig:both){reference-type="ref" reference="fig:both"},
[1b](#fig:right){reference-type="ref" reference="fig:right"} and
[2](#fig:next){reference-type="ref" reference="fig:next"}.
```

# A subfigure's caption and label stay with the subfigure

```
% pandoc -f latex -t native
\begin{figure}
  \caption{Top}
  \begin{subfigure}{\textwidth}
    \includegraphics{d.png}
    \caption{Only}
    \label{fig:only}
  \end{subfigure}
\end{figure}
^D
[ Figure
    ( "" , [] , [] )
    (Caption Nothing [ Plain [ Str "Top" ] ])
    [ Figure
        ( "fig:only" , [] , [ ( "width" , "100%" ) ] )
        (Caption Nothing [ Plain [ Str "Only" ] ])
        [ Plain [ Image ( "" , [] , [] ) [] ( "d.png" , "" ) ] ]
    ]
]
```