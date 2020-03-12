# Automatically starting the Python console

Instead of having to press `Ctrl-Alt-P` every session, why not script it 
so that the console starts automatically? Luckily, it's easy:

    from console import console
    console.console_show()

Those two lines in the `~/startup.py` file will do the job. Any error in 
the file will cause Python to be disabled for that session, be warned.
