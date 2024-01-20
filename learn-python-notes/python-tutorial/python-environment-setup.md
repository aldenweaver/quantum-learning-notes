# Python Environment Setup [Notes]

## Python Packaging & Installation
+ [Python Packaging User Guide](https://packaging.python.org/en/latest/)
  - "Building your understanding of Python packaging is a journey. Patience and continuous improvement are key to success. The overview and flow sections provide a starting point for understanding the Python packaging ecosystem."
+ [Installing Python Packages](https://packaging.python.org/en/latest/tutorials/installing-packages/)

## Python Install on macOS
+ Open the Terminal app on a macOS
+ Use homebrew to install Python: `brew install python@3.9`
  + If needed, install homebrew package manager by running the following command in Terminal: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

## Python Setup via the Hitchhiker's Guide to Python
Use this guide to get set up:
+ [Hitchhiker's Guide to Python](https://docs.python-guide.org/starting/installation/#installation)
    - [x] [Installing Python 3 on Mac OS X](https://docs.python-guide.org/starting/install3/osx/#install3-osx)
    - [ ] [Pipenv & Virtual Environments](https://docs.python-guide.org/dev/virtualenvs/#virtualenvironments-ref)
      + [Python3 OSX Install Guide](https://docs.python-guide.org/starting/install3/osx/#install3-osx)
        + `Virtual Environments`: "keep the dependencies required by different projects in separate places, by creating virtual Python environments for them."
        + "It solves the “Project X depends on version 1.x but, Project Y needs 4.x” dilemma, and keeps your global site-packages directory clean and manageable."
      + "You have brains in your head & feet in your shoes, you can steer yourself in any direction you choose!" - Dr. Seuss
      + `pipenv`: dependency manager for Python projects
      + `pipenv` is similar to `npm` for Node.js or `bundler` for Ruby
  
### pipenv Error Troubleshooting
+ Fix `-bash: pipenv: command not found` error by installing pipenv globally
  + Using the `--global-option` requirement specifier doesn't work
  + Doesn't work: `♥ pip install --global-option pipenv`
    + Yields error: `ERROR: You must give at least one requirement to install (see "pip help install")`
  + Not smart: `sudo pip install pipenv`
    + Yields warnings: 
      + `WARNING: The directory '/Users/alden/Library/Caches/pip' or its parent directory is not owned or is not writable by the current user. The cache has been disabled. Check the permissions and owner of that directory. If executing pip with sudo, you should use sudo's -H flag.`
      + Multiple messages of type: `Requirement already satisfied [...]`
      + `WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv`
      + See: [pipenv-troubleshooting-terminal-snapshot-1](pipenv-troubleshooting-terminal-snapshot-1.png)
+ Troubleshooting Research:
  + [pipenv command not found](https://stackoverflow.com/questions/46391721/pipenv-command-not-found)
  + `pip3 install requests` in the project root folder worked (TODO: for now?)
    + TODO: not sure if proper fix
    + "add the user base’s binary directory to your PATH." - https://docs.python-guide.org/dev/virtualenvs/#virtualenvironments-ref
    + https://stackoverflow.com/questions/14637979/how-to-permanently-set-path-on-linux-unix/14638025#14638025
       
## Learning Notes
+ TODO: figure out balance between environment setup/troubleshooting & getting down to learning the language using less overhead such as JupyterLite online Jupyter Notebook