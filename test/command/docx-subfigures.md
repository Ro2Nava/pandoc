Subfigures are not numbered as figures of their own, so the next
figure is Figure 2, and their captions have no `Figure N:` prefix.
In the figure's table an absolute image size is kept as given; an
image without a size fills its cell.

```
% pandoc -f native -t docx+native_numbering -o - | pandoc -f docx -t native
[ Figure ("fig:both",[],[]) (Caption Nothing [Plain [Str "Both."]])
  [ Figure ("fig:left",[],[]) (Caption Nothing [Plain [Str "Left."]])
      [Plain [Image ("",[],[("height","2cm")]) [] ("lalune.jpg","")]]
  , Figure ("fig:right",[],[]) (Caption Nothing [Plain [Str "Right."]])
      [Plain [Image ("",[],[]) [] ("lalune.jpg","")]]
  ]
, Figure ("fig:next",[],[]) (Caption Nothing [Plain [Str "Next."]])
  [Plain [Image ("",[],[]) [] ("lalune.jpg","")]]
]
^D
[ Table
    ( "" , [] , [] )
    (Caption Nothing [ Para [ Str ":" , Space , Str "Both." ] ])
    [ ( AlignCenter , ColWidth 0.44919786096256686 )
    , ( AlignCenter , ColWidth 0.44919786096256686 )
    ]
    (TableHead ( "" , [] , [] ) [])
    [ TableBody
        ( "" , [] , [] )
        (RowHeadColumns 0)
        []
        [ Row
            ( "" , [] , [] )
            [ Cell
                ( "" , [] , [] )
                AlignCenter
                (RowSpan 1)
                (ColSpan 1)
                [ Para
                    [ Image
                        ( ""
                        , []
                        , [ ( "width" , "0.7874004811898513in" )
                          , ( "height" , "0.7874004811898513in" )
                          ]
                        )
                        []
                        ( "media/rId9.jpg" , "" )
                    ]
                , Para [ Str "Left." ]
                ]
            , Cell
                ( "" , [] , [] )
                AlignCenter
                (RowSpan 1)
                (ColSpan 1)
                [ Para
                    [ Image
                        ( ""
                        , []
                        , [ ( "width" , "2.7666666666666666in" )
                          , ( "height" , "2.7666666666666666in" )
                          ]
                        )
                        []
                        ( "media/rId9.jpg" , "" )
                    ]
                , Para [ Str "Right." ]
                ]
            ]
        ]
    ]
    (TableFoot ( "" , [] , [] ) [])
, Figure
    ( "" , [] , [] )
    (Caption Nothing [ Para [ Str ":" , Space , Str "Next." ] ])
    [ Plain
        [ Image
            ( ""
            , []
            , [ ( "width" , "2.0833333333333335in" )
              , ( "height" , "2.0833333333333335in" )
              ]
            )
            []
            ( "media/rId9.jpg" , "" )
        ]
    ]
]
```

A subfigure's width sets the width of its column.

```
% pandoc -f native -t docx -o - | pandoc -f docx -t native
[ Figure ("",[],[]) (Caption Nothing [Plain [Str "Both."]])
  [ Figure ("",[],[("width","30%")]) (Caption Nothing [Plain [Str "Narrow."]])
      [Plain [Image ("",[],[]) [] ("lalune.jpg","")]]
  , Figure ("",[],[("width","60%")]) (Caption Nothing [Plain [Str "Wide."]])
      [Plain [Image ("",[],[]) [] ("lalune.jpg","")]]
  ]
]
^D
[ Table
    ( "" , [] , [] )
    (Caption Nothing [ Para [ Str "Both." ] ])
    [ ( AlignCenter , ColWidth 0.2695187165775401 )
    , ( AlignCenter , ColWidth 0.5389304812834225 )
    ]
    (TableHead ( "" , [] , [] ) [])
    [ TableBody
        ( "" , [] , [] )
        (RowHeadColumns 0)
        []
        [ Row
            ( "" , [] , [] )
            [ Cell
                ( "" , [] , [] )
                AlignCenter
                (RowSpan 1)
                (ColSpan 1)
                [ Para
                    [ Image
                        ( ""
                        , []
                        , [ ( "width" , "1.6in" )
                          , ( "height" , "1.6in" )
                          ]
                        )
                        []
                        ( "media/rId9.jpg" , "" )
                    ]
                , Para [ Str "Narrow." ]
                ]
            , Cell
                ( "" , [] , [] )
                AlignCenter
                (RowSpan 1)
                (ColSpan 1)
                [ Para
                    [ Image
                        ( ""
                        , []
                        , [ ( "width" , "3.3493055555555555in" )
                          , ( "height" , "3.3493055555555555in" )
                          ]
                        )
                        []
                        ( "media/rId9.jpg" , "" )
                    ]
                , Para [ Str "Wide." ]
                ]
            ]
        ]
    ]
    (TableFoot ( "" , [] , [] ) [])
]
```

A line break between subfigures (`\\` in LaTeX) starts a new row of
the figure table, so a 2 by 2 grid stays within the text width.

```
% pandoc -f native -t docx -o - | pandoc -f docx -t native
[ Figure ("",[],[]) (Caption Nothing [Plain [Str "Grid."]])
  [ Figure ("",[],[("width","49%")]) (Caption Nothing [Plain [Str "A."]])
      [Plain [Image ("",[],[]) [] ("lalune.jpg","")]]
  , Figure ("",[],[("width","49%")]) (Caption Nothing [Plain [Str "B."]])
      [Plain [Image ("",[],[]) [] ("lalune.jpg","")]]
  , Para [LineBreak]
  , Figure ("",[],[("width","49%")]) (Caption Nothing [Plain [Str "C."]])
      [Plain [Image ("",[],[]) [] ("lalune.jpg","")]]
  , Figure ("",[],[("width","49%")]) (Caption Nothing [Plain [Str "D."]])
      [Plain [Image ("",[],[]) [] ("lalune.jpg","")]]
  ]
]
^D
[ Table
    ( "" , [] , [] )
    (Caption Nothing [ Para [ Str "Grid." ] ])
    [ ( AlignCenter , ColWidth 0.4402139037433155 )
    , ( AlignCenter , ColWidth 0.4402139037433155 )
    ]
    (TableHead ( "" , [] , [] ) [])
    [ TableBody
        ( "" , [] , [] )
        (RowHeadColumns 0)
        []
        [ Row
            ( "" , [] , [] )
            [ Cell
                ( "" , [] , [] )
                AlignCenter
                (RowSpan 1)
                (ColSpan 1)
                [ Para
                    [ Image
                        ( ""
                        , []
                        , [ ( "width" , "2.7083333333333335in" )
                          , ( "height" , "2.7083333333333335in" )
                          ]
                        )
                        []
                        ( "media/rId9.jpg" , "" )
                    ]
                , Para [ Str "A." ]
                ]
            , Cell
                ( "" , [] , [] )
                AlignCenter
                (RowSpan 1)
                (ColSpan 1)
                [ Para
                    [ Image
                        ( ""
                        , []
                        , [ ( "width" , "2.7083333333333335in" )
                          , ( "height" , "2.7083333333333335in" )
                          ]
                        )
                        []
                        ( "media/rId9.jpg" , "" )
                    ]
                , Para [ Str "B." ]
                ]
            ]
        , Row
            ( "" , [] , [] )
            [ Cell
                ( "" , [] , [] )
                AlignCenter
                (RowSpan 1)
                (ColSpan 1)
                [ Para
                    [ Image
                        ( ""
                        , []
                        , [ ( "width" , "2.7083333333333335in" )
                          , ( "height" , "2.7083333333333335in" )
                          ]
                        )
                        []
                        ( "media/rId9.jpg" , "" )
                    ]
                , Para [ Str "C." ]
                ]
            , Cell
                ( "" , [] , [] )
                AlignCenter
                (RowSpan 1)
                (ColSpan 1)
                [ Para
                    [ Image
                        ( ""
                        , []
                        , [ ( "width" , "2.7083333333333335in" )
                          , ( "height" , "2.7083333333333335in" )
                          ]
                        )
                        []
                        ( "media/rId9.jpg" , "" )
                    ]
                , Para [ Str "D." ]
                ]
            ]
        ]
    ]
    (TableFoot ( "" , [] , [] ) [])
]
```
