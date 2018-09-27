Selenium Webdriver for Mac with Python
======
This tutorial will help you set up Selenium with Webdriver on your Mac for use with Python. [Selenium](https://www.seleniumhq.org/ 'Selenium') is a package that helps programmers automate browser tasks, primarily for testing purposes. It can also be used with with other languages and operating systems.

Please share, reuse, and modify this tutorial, but please do credit the creator following  [CC-BY-2.0](https://creativecommons.org/licenses/by/2.0/ 'Creative Commons Attribution 2.0 Generic').

Installing Selenium for Python
------
There are two main steps needed for making Selenium Webdriver available for use with Python:
1. Install the Selenium Python library.
2. Install a [webdriver](https://www.seleniumhq.org/download/ 'webdriver') compatible with Selenium. This webdriver acts as a proxy--basically, it facilitates a link between your scripts and a web browser so that your script can control the browser's function.

Here's how to install Selenium on a Mac:

*Note that the following does require that you have administrator privileges on your computer.*

1. Open your Terminal application.
2. Use the following code to install Selenium:

`pip install selenium`

*Pip is a Python package manager. If you are working with Python 2.7.9 or 3.4 or greater, this should already be installed. If it's not, take a look at [these instructions](https://www.makeuseof.com/tag/install-pip-for-python/ 'How to Install PIP for Python on Windows, Mac, and Linux').*

3. If you are asked to authenticate, type in your Mac user password, and press enter.

4. The installation will run. Wait for it to finish and for a message indicating successful installation to appear.

Next, install a webdriver:

This tutorial will demo installing [GeckoDriver](https://www.softwaretestinghelp.com/geckodriver-selenium-tutorial/ 'GeckoDriver Selenium Tutorial') for Firefox. Every browser uses a different driver and may have slightly different set up instructions. Check this [list](https://www.seleniumhq.org/download/ 'webdriver') and consider which browser you really need to work in. Best practice would be to set up multiple drivers for browser compatibility testing.

3. Navigate to the GeckoDriver Github repo: https://github.com/mozilla/geckodriver/releases.

4. Download the latest version for Mac, e.g. geckodriver-v0.22.0-macos.tar.gz.

5. Locate the download on your hard drive and unzip it by double clicking on it. This will add a geckodriver.exe file to your harddrive.

6. This file needs to be added to the correct path on your computer so that Firefox can access it.

7. In the Finder menu, navigate to Go > Go to Folder...

8. In the pop up text box, enter the path `/usr/local/bin`, and press Go.

9. Drag geckodriver.exe into this this folder.


Testing Selenium in Python
------
Now that you have Selenium and GeckoDriver installed, let's test it out with Python.

1. If you already have Firefox open, you may need to restart it so that it recognizes the addition of GeckoDriver.

2. Open your favorite IDE. (I currently use the free version of [PyCharm](https://www.jetbrains.com/pycharm/ 'Pycharm')).

3. Create a new program and add in the following code:

```
from selenium import webdriver

# Open the file in a browser.
driver = webdriver.Firefox()
driver.get('http://www.wikipedia.org')
```

4. Run the program. If the program executes properly, a new Firefox window will open and will automatically load the URL indicated in `.get()`.

To Load a Local HTML File in Firefox
------

Use the following **absolute path** instead of a public URL: `file:///Users/.../myfile.html`.

Your program should look something like this:

```
from selenium import webdriver

# Open the file in a browser.
driver = webdriver.Firefox()
driver.get('file:///Users/.../myfile.html')
```

*The absolute path is required for opening local files with Selenium.*

To learn more about working with Selenium's Webdriver API in Python, check out [this section](https://selenium-python.readthedocs.io/api.html 'Webdriver API') of the Selenium documentation. Happy scripting!
