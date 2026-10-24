A `table` float without a tabular, here an image of a table, keeps
its caption and label: its contents go in a one-cell table.

```
% pandoc -f latex -t native
\begin{table}
  \centering
  \includegraphics[width=\textwidth]{protocol.png}
  \caption{Coating protocol.}
  \label{tab:protocol}
\end{table}
See Table \ref{tab:protocol}.
^D
[ Table
    ( "tab:protocol" , [] , [] )
    (Caption
       Nothing
       [ Plain [ Str "Coating" , Space , Str "protocol." ] ])
    [ ( AlignDefault , ColWidthDefault ) ]
    (TableHead ( "" , [] , [] ) [])
    [ TableBody
        ( "" , [] , [] )
        (RowHeadColumns 0)
        []
        [ Row
            ( "" , [] , [] )
            [ Cell
                ( "" , [] , [] )
                AlignDefault
                (RowSpan 1)
                (ColSpan 1)
                [ Para
                    [ Image
                        ( "" , [] , [ ( "width" , "100%" ) ] )
                        [ Str "image" ]
                        ( "protocol.png" , "" )
                    ]
                ]
            ]
        ]
    ]
    (TableFoot ( "" , [] , [] ) [])
, Para
    [ Str "See"
    , Space
    , Str "Table"
    , Space
    , Link
        ( ""
        , []
        , [ ( "reference-type" , "ref" )
          , ( "reference" , "tab:protocol" )
          ]
        )
        [ Str "1" ]
        ( "#tab:protocol" , "" )
    , Str "."
    ]
]
```
