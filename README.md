Pharo command-line launcher
---------------------------

This is a simple command-line launcher for Pharo images. It allows you to
associate images and VMs with arbitrary names, in order to launch them easily.
It stores the configuration in a `.pharo` file in the user's home folder.

For instance, if you want to give a name to an image, you can type:

    $ pharo add image your-image-name /path/to/the/image

Same thing if you want to add a vm:

    $ pharo add vm your-vm-name /path/to/the/vm

Then you can evaluate:

    $ pharo launch your-vm-name your-image-name

You can also launch using image/vm paths direclty instead of names:

    $ pharo launch /path/to/vm image-name
    $ pharo launch vm-name /path/to/image

### Python 2/3 versions

Branch `python2` contains the Python 2.x version of the launcher. `master` contains the Python 3.x version.

### Install instructions

* Clone this repo and put the `pharo` file in some directory in your `PATH`.
* Type `pharo help` to see the list of all available commands.
* If you want completion for commands and vm/image names, you must add the
following line to the `.bashrc` file:

        complete -C <path_to_pharo_completion_file> -o default pharo

    where `<path_to_pharo_completion_file>` is the path to the `pharo_completion`
    file of this repository.
