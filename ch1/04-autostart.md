# Automatically starting the Python console

Instead of having to press `Ctrl-Alt-P` every session, why not script it 
so that the console starts automatically? Luckily, it's easy:

    from console import console
    console.console_show()

Those two lines in the `~/.qgis2/startup.py` file will do the job. Any
error in the file will cause Python to be disabled for that session of
QGis, and a warning dialogue box will pop up, so I was warned.

When I tried this, however, there was no error dialogue but no console
either. So...
