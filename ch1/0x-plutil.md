# QGIS-Plutil

I tried to see if I could write a script independently of QGis, because I
can't follow instructions. But I couldn't find `qgis-plugin` in pip.

What I did find was [plutil][pypi], an MIT-licensed library by Nicu Tofan
to develop QGis plugins. It's also on [GitHub][ghub]. How will it go?

Right now, all I have is a virtual environment with 0.1.1 installed:

    python3.8 -m venv qgis      # your version may vary
    source qgis/bin/activate
    pip install qgis-plutil

But nothing in that library is immediately obviously usable:

    import qgis_plutil
    from qgis_plutil import constants
    from qgis_plutil import plugins

More exploration is needed.

[pypi]: https://pypi.org/project/qgis-plutil/
[ghub]: https://github.com/pyqgis/plutil/
