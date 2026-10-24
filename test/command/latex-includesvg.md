`\includesvg` adds `.svg` to a file name without an extension, like
the svg package; a bare `\textwidth` is a width of 100%.

```
% pandoc -f latex -t native
\includesvg[width=0.5\textwidth]{figs/diagram} \includesvg{figs/photo.png}
\includegraphics[width=\textwidth]{figs/plot.png}
^D
[ Para
    [ Image
        ( "" , [] , [ ( "width" , "50%" ) ] )
        [ Str "image" ]
        ( "figs/diagram.svg" , "" )
    , Space
    , Image
        ( "" , [] , [] ) [ Str "image" ] ( "figs/photo.png" , "" )
    , SoftBreak
    , Image
        ( "" , [] , [ ( "width" , "100%" ) ] )
        [ Str "image" ]
        ( "figs/plot.png" , "" )
    ]
]
```
