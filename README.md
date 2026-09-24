# README : everettfr-del.github.io

## What this repository is
This is a repository containing my personal site detailing my master's program work and some data analysis within blog posts. 

## What you'll need to build it
You'll require the following list of software to build this repository. Each will be listed along with instructions on how to install it. Most steps will require the use of your terminal - in Windows, open Command Prompt or PowerShell; on macOS, search for Terminal using Spotlight; on Linux, open your preferred terminal.

### R
Created with R 4.6.1.

If you do not have R installed, download and install R from CRAN:
[Download R for Windows from CRAN](https://cran.r-project.org/bin/windows/base)
[Download R for macOS from CRAN](https://cran.r-project.org/bin/macosx/)

For Linux, R can be installed using your Linux distribution's package manager. For example, on Ubuntu or Debian:
```bash
sudo apt update
sudo apt install r-base
```
Installation instructions for other Linux distributions are available from CRAN's R for Linux page.

The project uses renv to restore the required R package environment, so individual R packages do not need to be installed manually. You can verify your R installation from the terminal with:

```bash
R --version
```
### Quarto
Created with Quarto 1.10.18.

If you do not have Quarto installed, download and run the appropriate installer for your operating system from the official Quarto website:

[Install Quarto](https://quarto.org/docs/get-started)

You can verify the installation from the terminal with:
```bash
quarto --version
```
### uv
Created with uv 0.12.7.

If you do not have uv installed, it can be installed from PowerShell with the following for Windows:
```bash
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```
Or the following for Mac/Linux:
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```
After installation, restart your terminal if necessary and verify the installation with:
```bash
uv --version
```
### Git

Created with Git 2.55.0.windows.5.

If you do not have Git installed, download the Git for Windows installer from:

[Install Git for Windows](https://git-scm.com/install/windows)

On Mac, Git can be installed using Apple's Xcode Command Line Tools:
```bash
xcode-select --install
```

On Linux, Git can be installed using your distribution's package manager.
For Ubuntu or Debian:
```bash
sudo apt update
sudo apt install git
```

Verify the installation with:
```bash
git --version
```

### Python
Created with Python 3.14.7.

Python does not need to be installed separately before setting up this project. uv can download and manage the required Python version. After installing uv, Python 3.14.7 can be installed with:
```bash
uv python install 3.14.7
```
You can verify the installed version with:
```bash
uv run python --version
```
## How to build it
Firstly, you'll need to clone this repository to your local machine. Open up your terminal and navigate to the directory that you'd like the cloned repository to appear in - [see here for help on navigating using the command console.](https://datacarpentry.github.io/shell-economics/02-the-filesystem/index.html). Once in the desired directory, type the following into your terminal:
```bash
git clone https://github.com/everettfr-del/everettfr-del.github.io
```
Then, enter the cloned repository by typing:
```bash
cd everettfr-del.github.io/
```
From this point forward, the directory you are currently in will be referred to as the **root** directory. All terminal commands will be run from here unless specified otherwise.

Firstly, restore your Python environment and install the project's required python dependencies with:
```bash
uv sync
```
Similiarly, the R environment will need to be restored. Firstly, type
```bash
R
```
to enter an R console. Type:
```r
renv::restore()
```
If prompted, say yes. Follow with:
```r
q()
```
to exit the R environment. If prompted, don't save the workspace. Lastly, you'll need to type the following to render the site:
```bash
uv run quarto render
```
## Where the built site lands
The render will output to the 'docs' folder - you can navigate there with 
```bash
cd docs
```
The final render is called **index.html**. You can run it once in the docs directory by typing the following on Windows:
```bash
start index.html
```
Or the following on Mac:
```bash
open index.html
```
Or the following on Linux:
```bash
xdg-open index.html
```
which will open the render in whatever your device defaults to opening html files with.

## Data sources
The two data analysis blog posts utilize the [Gapminder](https://www.gapminder.org/data/) data set, compiled by the Gapminder Organization in Sweden to show real-world development trends over time and fight misconceptions about the state of the world through data. It contains information regarding life expectancy, population, and GDP per capita for 140+ nations around the world, assembled from a variety of sources such as the Institute for Health Metrics and Evaluation, the US Census Bureau’s International Database, the United Nations Statistics Division, and the World Bank.

An internet connection is required during initial environment setup to obtain Python and R dependencies as well as do any necessary software installation. Once those dependencies are installed, the site build itself does not require network access as the Gapminder dataset is already bundled within the packages.