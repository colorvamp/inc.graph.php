inc.graph.php
=============

Documentation
=============


```
include_once('inc.graph.php');
$svg = graph_bars(array(
	'cell.marginx'=>2,
	'bar.indicator'=>true,
	'graph'=>array(
		'prim'=>array(1,2,3,4,5)
	),
	'header'=>array(
		'enr','feb','mar','abr','may'
	)
));
echo $svg;
```

Result:

![Simple Bar Graph](http://i.imgur.com/uuhzjo9.png "Simple Bar Graph")


Using gradients
---------------

To work with a gradient, use the keys **graph.gradient.from** and **graph.gradient.to** with hex values.


```
include_once('inc.graph.php');
$svg = graph_bars(array(
	'cell.marginx'=>2,
	'bar.indicator'=>true,
	'graph.gradient.from'=>'8cc277',
	'graph.gradient.to'=>'6fa85b',
	'graph'=>array(
		'prim'=>array(1,2,3,4,5)
	),
	'header'=>array(
		'enr','feb','mar','abr','may'
	)
));
echo $svg;
```

Result:

![Gradient Bar Graph](http://i.imgur.com/oqPKWlW.png "Gradient Bar Graph")


Variable bar and column sizes
-----------------------------

The key **cell.width** controls the columns width while **cell.marginx** marks
the distance between the bar and the column limits.


```
include_once('inc.graph.php');
$svg = graph_bars(array(
	'cell.width'=>40,
	'cell.marginx'=>8,
	'bar.indicator'=>true,
	'graph.gradient.from'=>'8cc277',
	'graph.gradient.to'=>'6fa85b',
	'graph'=>array(
		'prim'=>array(1,2,3,4,5,6,7,8,9,10)
	),
	'header'=>array(
		'enr','feb','mar','abr','may','jun','jul','ago','sep','oct'
	)
));
echo $svg;
```

![Thin Bar Graph](http://i.imgur.com/q9bjGZ8.png "Thin Bar Graph")



No indicator and flat bars
--------------------------

If the key **bar.indicator** is not supplied the graph will not show any indicator.
The key **cell.marginy** controls the column top and bottom margins.

```
include_once('inc.graph.php');
$svg = graph_bars(array(
	'cell.width'=>40,
	'cell.marginx'=>8,
	'cell.marginy'=>14,
	'graph.gradient.from'=>'8cc277',
	'graph.gradient.to'=>'6fa85b',
	'graph'=>array(
		'prim'=>array(1,2,3,4,5,6,7,8,9,10)
	),
	'header'=>array(
		'enr','feb','mar','abr','may','jun','jul','ago','sep','oct'
	)
));
echo $svg;
```

![No indicator Bar Graph](http://i.imgur.com/GSKfqFg.png "No indicator Bar Graph")



Header and graph background
---------------------------

You can change the graph background through **graph.background**. The header background
will default to this value. Alternatively you can pass **header.even.background** and 
**header.odd.background** to create something like the following:


```
include_once('inc.graph.php');
$svg = graph_bars(array(
	'cell.width'=>40,
	'cell.marginx'=>8,
	'cell.marginy'=>12,
	'bar.indicator'=>true,
	'graph.background'=>'ccc',
	'graph.gradient.from'=>'8cc277',
	'graph.gradient.to'=>'6fa85b',
	'graph'=>array(
		'prim'=>array(1,2,3,4,5,6,7,8,9,10)
	),
	'header.even.background'=>'eee',
	'header.odd.background'=>'aaa',
	'header'=>array(
		'enr','feb','mar','abr','may','jun','jul','ago','sep','oct'
	)
));
echo $svg;
```

![Header and graph background Bar Graph](http://i.imgur.com/ldmgH4A.png "Header and graph background Bar Graph")


Legend line color, legend width and indicator count
---------------------------------------------------

Change the indicator cuts count setting the key **graph.legend.count**, in the next example 
you can see 4 cuts. The key **graph.legend.width** controls the legend width as noted in the
example. Finally, the color of the horizontal markers matching the rule is set by the **graph.legend.line.color** 
key.

```
include_once('inc.graph.php');
$svg = graph_bars(array(
	'graph.height'=>240,
	'cell.width'=>40,
	'cell.marginx'=>8,
	'cell.marginy'=>12,
	'bar.indicator'=>true,
	'graph.background'=>'ccc',
	'graph.gradient.from'=>'8cc277',
	'graph.gradient.to'=>'6fa85b',
	'graph'=>array(
		'prim'=>array(1,2,3,4,5,6,7,8,9,10)
	),
	'header.even.background'=>'eee',
	'header.odd.background'=>'aaa',
	'header'=>array(
		'enr','feb','mar','abr','may','jun','jul','ago','sep','oct'
	),
	'graph.legend.width'=>100,
	'graph.legend.count'=>4,
	'graph.legend.line.color'=>'aaa',
));
echo $svg;
```

![Legend line color, legend width and indicator count](http://i.imgur.com/Jz9mOFN.png "Legend line color, legend width and indicator count")


