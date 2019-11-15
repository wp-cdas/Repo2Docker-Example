# Repo2Docker Example Repository

Please check here [https://repo2docker.readthedocs.io/en/latest/](https://repo2docker.readthedocs.io/en/latest/) for the documentation of Repo2Docker.

This repository is a template for you to use when spawning your custom container on the DSP.  Always reference
the documentation for Repo2Docker as the primary source for using this tool but, by looking through the 
configuration files found here, you can get an idea of what is possible in your container.

The general idea of Repo2Docker on the DSP is that you can build the environment you want before logging in to work on the DSP.  Through the use of various files in the repository you can include other files,  install dependencies, other packages, and even clone external repositories.  When you log
on to the DSP you merely provide the GitHub URL and the DSP will do the rest and launch you into your custom container.  You can even make changes to the files in your container and push them back to the original GitHub repository.

Here are the uses of the configuration files most commonly used (in rough order of build priority):

- **environment.yml** - Using Conda to install a python environment and dependencies **Highly recommended to use this for python package install (even for pip installs)**.
- **requirements.txt** - Using PIP (python's built-in package manager) to install dependencies
- **apt.txt** - Installing Ubuntu packages
- **postBuild** - Operations you need to run after your container has been built
- **start** - Operations you need to run upon startup of a container. **Note**: DO NOT include a **start** file if spawning on the DSP.  This is only for unattended computations on future assets.
