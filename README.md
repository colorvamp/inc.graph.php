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
