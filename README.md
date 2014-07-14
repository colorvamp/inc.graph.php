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
