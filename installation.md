# python setup & napari installation

## Installing python via anaconda

In this tutorial, we will install python via miniconda. However, if you already have anaconda, miniconda, or miniforge installed, those will work as well and you can skip to the next section.

1. In your web browser, navigate to the [miniconda page](https://docs.conda.io/en/latest/miniconda.html).
2. Scroll down to the "Latest Miniconda Installer Links" section. Click the link to download the appropriate version for your operating system.
  - **Windows**: Most likely the Miniconda3 Windows 64-bit  
	- **Mac OS**: Choose between Apple M1 (new Macs with Apple Silicon) or MacOSX. Choose the pkg download for an easy installation procedure  
3. Once you have downloaded the miniconda installer, run it to install python and follow the installer instructions.

## Setting up your environment
1. Open your terminal.
	- **Windows**: Open Anaconda Prompt
	- **Mac OS**: Open Terminal (you can search for it in spotlight - cmd + space)
	- **Linux**: Open your terminal application

2. We use an environment to encapsulate the python tools used for this workshop. This ensures that the requirements for this workshop do not interfere with your other python projects. To create the environment (named `napari-tutorial`), enter the following command.

	```
	conda create -n napari-tutorial python=3.9
	```

3. Once the environment setup has finished, activate the environment. If you successfully activated the environment, you should now see `(napari-tutorial)` to the left of your command prompt.

	```
	conda activate napari-tutorial
	```

4. Install the dependencies with the commands below

	```
	pip install "napari[all]"
	pip install jupyterlab
	pip install imageio
	pip install imagecodecs
	pip install napari_animation
	```

5. Test that your notebook installation is working. We will be using notebooks for interactive analysis. Enter the command below and it should launch jupyter notebook book in a web browser.

	```
	jupyter lab
	```

6. Test your napari installation. Open a new terminal window (the one above is still running your notebook). Activate the python environment again (see 3 above). Enter the command below and an empty napari viewer should open. Please note that it takes a bit of extra time to launch napari the first time.

	```
	napari
	```


## Known issues & workarounds
1. Conda can't install dependencies because of proxy settings.
Check whether you have specified proxy variables. For windows, they are set [here](https://docs.oracle.com/en/database/oracle/machine-learning/oml4r/1.5.1/oread/creating-and-modifying-environment-variables-on-windows.html#GUID-DD6F9982-60D5-48F6-8270-A27EC53807D0) and deleting them solved the issues for some users. On Mac, they would be set in the .bashrc or .zshrc file in your home directory.

2. Can't install PyQt5 on M1 macs. `AttributeError: module 'sipbuild.api' has no attribute 'prepare_metadata_for_build_wheel'`
The problem: The current version of PyQt5 in pip does not support M1 macs. Install manually via conda before installing napari:
`conda install pyqt`

3. Installing `imagecodecs` fails on M1 Macs
Install manually using conda: `conda install imagecodecs`
