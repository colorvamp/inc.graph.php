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
	'graph.legend.line.color'=>'aaa'
));
echo $svg;
```

![Legend line color, legend width and indicator count Bar Graph](http://i.imgur.com/Jz9mOFN.png "Legend line color, legend width and indicator count Bar Graph")


Graph + table
-------------

If you want a table to follow graph, you only need to feed the key **table**

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
		'first'=>array(1,2,3,4,5,6,7,8,9,10)
	),
	'header.even.background'=>'eee',
	'header.odd.background'=>'aaa',
	'header'=>array(
		'enr','feb','mar','abr','may','jun','jul','ago','sep','oct'
	),
	'graph.legend.width'=>100,
	'graph.legend.count'=>4,
	'graph.legend.line.color'=>'aaa',
	'table'=>array(
		'first'=>array(1,2,3,4,5,6,7,8,9,10),
		'secnd'=>array(1,2,3,4,5,6,7,8,9,10),
		'third'=>array(1,2,3,4,5,6,7,8,9,10)
	),
));
echo $svg;
```

![Graph + table Bar Graph](http://i.imgur.com/1qkykJp.png "Graph + table Bar Graph")

**Update**

The table background now matchs **graph.background** if no **table.background** is set. Keys 
**table.even.background** and **table.odd.background** now already exists.

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
		'first'=>array(1,2,3,4,5,6,7,8,9,10)
	),
	'header.even.background'=>'eee',
	'header.odd.background'=>'aaa',
	'header'=>array(
		'enr','feb','mar','abr','may','jun','jul','ago','sep','oct'
	),
	'graph.legend.width'=>100,
	'graph.legend.count'=>4,
	'graph.legend.line.color'=>'aaa',
	'table'=>array(
		'first'=>array(1,2,3,4,5,6,7,8,9,10),
		'secnd'=>array(1,2,3,4,5,6,7,8,9,10),
		'third'=>array(1,2,3,4,5,6,7,8,9,10)
	),
	'table.even.background'=>'eee',
	'table.odd.background'=>'ccc'
));
echo $svg;
```

![Graph + table Update Bar Graph](http://i.imgur.com/SqD778E.png "Graph + table Update Bar Graph")



Line graph + table
------------------

In case you want to print a line graph, most of the keys un the past examples apply here. Now you need 
to pass via **graph** key more than 1 array of items in order to paint diferente lines. The **table** 
key just need to be set and will be feed with the same **graph** values. For the different colours of
the lines you need to fill **graph.colors**, one value per line with a fixed string meaning solid colour
or a pair of two being a gradient.


```
include_once('inc.graph.php');
$svg = graph_lines(array(
	'graph.height'=>240,
	'cell.width'=>40,
	'cell.marginx'=>8,
	'cell.marginy'=>12,
	'bar.indicator'=>true,
	'graph.background'=>'ccc',
	'graph'=>array(
		'first'=>array(1,2,3,4,5,6,7,8,9,10),
		'second'=>array(6,7,7,13,10,11,15,7,14,15),
		'third'=>array(21,22,22,28,25,26,30,22,29,30)
	),
	'graph.colors'=>array(
		array('8cc277','6fa85b'),
		'00f',
		array('2980b9','216896'),
	),
	'header.even.background'=>'eee',
	'header.odd.background'=>'aaa',
	'header'=>array(
		'enr','feb','mar','abr','may','jun','jul','ago','sep','oct'
	),
	'graph.legend.width'=>100,
	'graph.legend.count'=>4,
	'graph.legend.line.color'=>'aaa',
	'table'=>true,
	'table.even.background'=>'eee',
	'table.odd.background'=>'ccc'
));
echo $svg;
```

![Line graph + table Graph](http://i.imgur.com/1zmyu6M.png "Line graph + table Graph")

