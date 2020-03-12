# Setting environment variables on Linux

The book recommends setting `$PYTHONPATH` to the QGIS directory.

    export PYTHONPATH=/usr/share/qgis/python

Also, it calls for the `LD_LIBRARY_PATH` to be set, and so I did
as suggested:

    export LD_LIBRARY_PATH=/usr/share/qgis/python

I went along with it since I normally don't use those variables,
but why we need to do that isn't clear at the moment. Let's see.

