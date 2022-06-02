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
	- **Windows**: TODO => instructions, test on my loaner
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
	```

5. Test that your notebook installation is working. We will be using notebooks for interactive analysis. Enter the command below and it should launch jupyter notebook book in a web browser.

	```
	jupyter lab
	```

6. Test your napari installation. Open a new terminal window (the one above is still running your notebook). Activate the python environment again (see 3 above). Enter the command below and an empty napari viewer should open. Please note that it takes a bit of extra time to launch napari the first time.

	```
	napari
	```
