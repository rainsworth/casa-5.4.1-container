# casa-5.4.1-container

This repo contains the recipe for a [Singularity](https://www.sylabs.io/) container for [CASA](https://casa.nrao.edu/) version 5.4.1 for reducing radio data. Instructions for installing Singularity can be found [here](https://www.sylabs.io/guides/3.0/user-guide/installation.html#installation).

## Installation

Simply download the image from [Singularity Hub](https://www.singularity-hub.org/) by executing:

```
$ singularity pull --name casa-5.4.1.simg shub://rainsworth/casa-5.4.1-container
```


## Usage

You can interact with this image in several ways:

#### Shell

Use the [shell](https://www.sylabs.io/guides/3.0/user-guide/quick_start.html#shell) command to spawn a new shell within the container and interact with it as though it were a small virtual machine by executing

```
$ singularity shell casa-5.4.1.simg 
```

#### Run

Use the [run](https://www.sylabs.io/guides/3.0/user-guide/quick_start.html#running-a-container) command to trigger the [runscript](https://www.sylabs.io/guides/3.0/user-guide/definition_files.html#runscript), which has been setup to execute a CASA script provided as an argument with the following synopsis: ```singularity run [CONTAINER] [SCRIPT] [ARGS] ``` where the [ARGS] are any arguments to pass to the script. For example, execute:

```
$ singularity run casa-5.4.1.simg script.py
```

#### Exec

The [exec](https://www.sylabs.io/guides/3.0/user-guide/quick_start.html#executing-commands) command allows you to execute a custom command within a container by specifying the image file. For example, to execute a CASA script:

```
$ singularity exec casa-5.4.1.simg casa -c script.py 
```
