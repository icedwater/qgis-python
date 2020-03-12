# Using the QGIS Python Console

This code was supplied on page 14 of my book:

    layer = QgsVectorLayer("Point?crs=epsg:4326", "MyPoint", "memory")
    pr = layer.dataProvider()
    pt = QgsFeature()
    point1 = QgsPoint(20, 20)
    pt.setGeometry(QgsGeometry.fromPoint(point1))
    pr.addFeatures([pt])
    layer.updateExtents()
    QgsMapLayerRegistry.instance().addMapLayers([layer])

Yay! The console returned a list:

    [<qgis._core.QgsVectorLayer object at 0xMEM>]

and a red dot appeared in the blankness above the console. What I think it 
just did is:

  1. Define a new layer called `MyPoint` which uses the `EPSG:4326` coordinate 
     reference system (CRS).
  2. Define a `dataProvider`, `pr`, for that layer with a single `QgsFeature`.
  3. Define `point1` at the coordinates (20, 20) and tell `pt` to use
     this point for its geometry.
  4. Add a list of `Features` (currently only `pt`) to `pr`.
  5. Draw the layer using the data in `pr`.
  6. On a new unnamed Map instance, add the layer we just defined.

## Adding one Point ...

So I went on to try adding:

    point2 = QgsPoint(30, 30)
    pt.setGeometry(QgsGeometry.fromPoint(point2))
    pr.addFeatures([pt])
    layer.updateExtents()
    QgsMapLayerRegistry.instance().addMapLayers([layer])

This time, the return was `[]` and there was no visible change. Whoops.
That probably had something to do with step 6: that the Map didn't have
a handle and so it was trying to add a layer to a new instance.

So I gave it a handle:

    testmap = QgsMapLayerRegistry.instance()
    testmap.addMapLayers([layer])

But again, the console returned an `[]`. Still I pushed on:

    layer2 = QgsVectorLayer("Point?crs=epsg:4326", "NextPoint", "memory")
    pr2 = layer2.dataProvider()
    pt2 = QgsFeature()
    point2 = QgsPoint(25, 30)
    pt2.setGeometry(QgsGeometry.fromPoint(point2))
    pr2.addFeatures([pt2])
    layer2.updateExtents()
    testmap.addMapLayers([layer2])

Finally, a new layer appeared, called "NextPoint", containing a green
dot this time, but also, a second red dot appeared on the MyPoint layer.
This suggests that the first `Point2` had been added to the first layer
with the `updateExtents()` call, I just hadn't seen it yet.

