Meta-analysis
-------------

    # Simple Meta-analysis
    library(rmeta)
    data("cochrane"); ?cochrane

    ## starting httpd help server ... done

    # FE model
    model_FE <- meta.MH(n.trt, n.ctrl, ev.trt, ev.ctrl, 
                        names = name, data = cochrane)
    summary(model_FE)

    ## Fixed effects ( Mantel-Haenszel ) meta-analysis
    ## Call: meta.MH(ntrt = n.trt, nctrl = n.ctrl, ptrt = ev.trt, pctrl = ev.ctrl, 
    ##     names = name, data = cochrane)
    ## ------------------------------------
    ##                OR (lower  95% upper)
    ## Auckland     0.58    0.38       0.89
    ## Block        0.16    0.02       1.45
    ## Doran        0.25    0.07       0.81
    ## Gamsu        0.70    0.34       1.45
    ## Morrison     0.35    0.09       1.41
    ## Papageorgiou 0.14    0.02       1.16
    ## Tauesch      1.02    0.37       2.77
    ## ------------------------------------
    ## Mantel-Haenszel OR =0.53 95% CI ( 0.39,0.73 )
    ## Test for heterogeneity: X^2( 6 ) = 6.9 ( p-value 0.3303 )

    plot(model_FE)

![](test_files/figure-markdown_strict/cars-1.png)

    # RE model
    model_RE <- meta.DSL(n.trt,n.ctrl,ev.trt,ev.ctrl, 
                         names=name,data=cochrane)
    summary(model_RE)

    ## Random effects ( DerSimonian-Laird ) meta-analysis
    ## Call: meta.DSL(ntrt = n.trt, nctrl = n.ctrl, ptrt = ev.trt, pctrl = ev.ctrl, 
    ##     names = name, data = cochrane)
    ## ------------------------------------
    ##                OR (lower  95% upper)
    ## Auckland     0.58    0.38       0.89
    ## Block        0.16    0.02       1.45
    ## Doran        0.25    0.07       0.81
    ## Gamsu        0.70    0.34       1.45
    ## Morrison     0.35    0.09       1.41
    ## Papageorgiou 0.14    0.02       1.16
    ## Tauesch      1.02    0.37       2.77
    ## ------------------------------------
    ## SummaryOR= 0.53  95% CI ( 0.37,0.78 )
    ## Test for heterogeneity: X^2( 6 ) = 6.86 ( p-value 0.334 )
    ## Estimated random effects variance: 0.03

    plot(model_RE)

![](test_files/figure-markdown_strict/cars-2.png)

Including Plots
---------------

You can also embed plots, for example:

![](test_files/figure-markdown_strict/pressure-1.png)

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
