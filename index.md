---
title       : Speed Comparison
subtitle    : Testing the speed of data.table
author      : Joe Heywood
job         : 
framework   : io2012       # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
ext_widgets : {rCharts: libraries/nvd3}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Speed Comparison

*   Purpose of this project is to compare speed
*   Uses the `microbenchmarking` package
*   The code could be changed to compare whatever you want
*   But I have done a simple comparion of `data.table` and a normal data frame

![Stropwatch text]("~/DataProducts/projectSlides/stopwatch.jpg")


--- .class #id 

## How it works

*   I generate N rows of random numbers and strings of three characters 
*   These are stored in two data frames. 
*   I then scramble the order of the data frames and merge them 
*   `microbenchmark` repeats this process thousands of times, and returns the
median value
*   Out of the box, this product gives you a quick comparison of the function
below:

```
    mergeFrame <- function(DF1, DF2){
        ind1 = sample(1:nrow(DF1))
        ind2 = sample(1:nrow(DF2))
        merge(DF1[ind1, ], DF2[ind2,], by = 'ID')
    }
```

---
### Results of Analysis


<div id = 'chart1' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart1()
    });
    function drawchart1(){  
      var opts = {
 "dom": "chart1",
"width":    800,
"height":    400,
"x": "rows",
"y": "value",
"group": "variable",
"type": "lineChart",
"id": "chart1" 
},
        data = [
 {
 "rows":            100,
"variable": "data.frame",
"value":        1283396 
},
{
 "rows":            200,
"variable": "data.frame",
"value":      1641529.5 
},
{
 "rows":            300,
"variable": "data.frame",
"value":      1993373.5 
},
{
 "rows":            400,
"variable": "data.frame",
"value":      2431534.5 
},
{
 "rows":            500,
"variable": "data.frame",
"value":        2788955 
},
{
 "rows":            600,
"variable": "data.frame",
"value":      3336852.5 
},
{
 "rows":            700,
"variable": "data.frame",
"value":      3725903.5 
},
{
 "rows":            800,
"variable": "data.frame",
"value":      4301888.5 
},
{
 "rows":            900,
"variable": "data.frame",
"value":        4511343 
},
{
 "rows":           1000,
"variable": "data.frame",
"value":        5083043 
},
{
 "rows":           1100,
"variable": "data.frame",
"value":      5263436.5 
},
{
 "rows":           1200,
"variable": "data.frame",
"value":      5994441.5 
},
{
 "rows":           1300,
"variable": "data.frame",
"value":        6040045 
},
{
 "rows":           1400,
"variable": "data.frame",
"value":      6526105.5 
},
{
 "rows":           1500,
"variable": "data.frame",
"value":        6954728 
},
{
 "rows":           1600,
"variable": "data.frame",
"value":      7537118.5 
},
{
 "rows":           1700,
"variable": "data.frame",
"value":      7944218.5 
},
{
 "rows":           1800,
"variable": "data.frame",
"value":        8348309 
},
{
 "rows":           1900,
"variable": "data.frame",
"value":      8612969.5 
},
{
 "rows":           2000,
"variable": "data.frame",
"value":        9309397 
},
{
 "rows":           2100,
"variable": "data.frame",
"value":     10023226.5 
},
{
 "rows":           2200,
"variable": "data.frame",
"value":     10652306.5 
},
{
 "rows":           2300,
"variable": "data.frame",
"value":     10636403.5 
},
{
 "rows":           2400,
"variable": "data.frame",
"value":       13211969 
},
{
 "rows":           2500,
"variable": "data.frame",
"value":     13964339.5 
},
{
 "rows":           2600,
"variable": "data.frame",
"value":     12273471.5 
},
{
 "rows":           2700,
"variable": "data.frame",
"value":       13017143 
},
{
 "rows":           2800,
"variable": "data.frame",
"value":       13584543 
},
{
 "rows":           2900,
"variable": "data.frame",
"value":       13859454 
},
{
 "rows":           3000,
"variable": "data.frame",
"value":     14637525.5 
},
{
 "rows":           3100,
"variable": "data.frame",
"value":     14699014.5 
},
{
 "rows":           3200,
"variable": "data.frame",
"value":     15435417.5 
},
{
 "rows":           3300,
"variable": "data.frame",
"value":     16220408.5 
},
{
 "rows":           3400,
"variable": "data.frame",
"value":     16366855.5 
},
{
 "rows":           3500,
"variable": "data.frame",
"value":     16992287.5 
},
{
 "rows":           3600,
"variable": "data.frame",
"value":     18724357.5 
},
{
 "rows":           3700,
"variable": "data.frame",
"value":     19514408.5 
},
{
 "rows":           3800,
"variable": "data.frame",
"value":       18905492 
},
{
 "rows":           3900,
"variable": "data.frame",
"value":       20530033 
},
{
 "rows":           4000,
"variable": "data.frame",
"value":     21214913.5 
},
{
 "rows":            100,
"variable": "data.table",
"value":      2559673.5 
},
{
 "rows":            200,
"variable": "data.table",
"value":        2654168 
},
{
 "rows":            300,
"variable": "data.table",
"value":      2712333.5 
},
{
 "rows":            400,
"variable": "data.table",
"value":        2776127 
},
{
 "rows":            500,
"variable": "data.table",
"value":        2942860 
},
{
 "rows":            600,
"variable": "data.table",
"value":      3040268.5 
},
{
 "rows":            700,
"variable": "data.table",
"value":      3127746.5 
},
{
 "rows":            800,
"variable": "data.table",
"value":        3230610 
},
{
 "rows":            900,
"variable": "data.table",
"value":        3006443 
},
{
 "rows":           1000,
"variable": "data.table",
"value":      3123205.5 
},
{
 "rows":           1100,
"variable": "data.table",
"value":        2935776 
},
{
 "rows":           1200,
"variable": "data.table",
"value":      3272572.5 
},
{
 "rows":           1300,
"variable": "data.table",
"value":      3004149.5 
},
{
 "rows":           1400,
"variable": "data.table",
"value":      3053892.5 
},
{
 "rows":           1500,
"variable": "data.table",
"value":        3045828 
},
{
 "rows":           1600,
"variable": "data.table",
"value":        3204832 
},
{
 "rows":           1700,
"variable": "data.table",
"value":      3283407.5 
},
{
 "rows":           1800,
"variable": "data.table",
"value":      3141996.5 
},
{
 "rows":           1900,
"variable": "data.table",
"value":        3098959 
},
{
 "rows":           2000,
"variable": "data.table",
"value":      3316480.5 
},
{
 "rows":           2100,
"variable": "data.table",
"value":        3370065 
},
{
 "rows":           2200,
"variable": "data.table",
"value":        3438578 
},
{
 "rows":           2300,
"variable": "data.table",
"value":        3305435 
},
{
 "rows":           2400,
"variable": "data.table",
"value":      4022489.5 
},
{
 "rows":           2500,
"variable": "data.table",
"value":        4020915 
},
{
 "rows":           2600,
"variable": "data.table",
"value":        3422769 
},
{
 "rows":           2700,
"variable": "data.table",
"value":        3528595 
},
{
 "rows":           2800,
"variable": "data.table",
"value":      3632091.5 
},
{
 "rows":           2900,
"variable": "data.table",
"value":      3537680.5 
},
{
 "rows":           3000,
"variable": "data.table",
"value":      3698786.5 
},
{
 "rows":           3100,
"variable": "data.table",
"value":      3620616.5 
},
{
 "rows":           3200,
"variable": "data.table",
"value":      3666609.5 
},
{
 "rows":           3300,
"variable": "data.table",
"value":        3767114 
},
{
 "rows":           3400,
"variable": "data.table",
"value":      3695069.5 
},
{
 "rows":           3500,
"variable": "data.table",
"value":        3920674 
},
{
 "rows":           3600,
"variable": "data.table",
"value":        3931532 
},
{
 "rows":           3700,
"variable": "data.table",
"value":        3797268 
},
{
 "rows":           3800,
"variable": "data.table",
"value":        3933024 
},
{
 "rows":           3900,
"variable": "data.table",
"value":        4173606 
},
{
 "rows":           4000,
"variable": "data.table",
"value":      3970043.5 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus" || opts.type==="bulletChart")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .width(opts.width)
          .height(opts.height)
          
        if (opts.type != "bulletChart"){
          chart
            .x(function(d) { return d[opts.x] })
            .y(function(d) { return d[opts.y] })
        }
          
         
        
          
        

        
        
        
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

---
## Potential for Development
*   The code can be edited to measure whichever functions you choose
*   At the moment, it is set up to measure the two generated data frames
*   But other packages that aim to improve performance can also be tested
---


