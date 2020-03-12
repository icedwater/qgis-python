# Installing PyQGIS using the Debian package manager

The book calls for the package `qgis-plugin-grass` to be installed.

However, at the time of the work-through, that has been deprecated:

    sudo apt-get install qgis python-qgis qgis-provider-grass

The new package to use is `qgis-provider-grass`.
