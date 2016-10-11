# Phapp CLI tool

The Phapp CLI tool is

## Installation

Installation requires composer. As there are some dependency conflicts with the
latest drush release it is recommened to install the tool via consolidation/cgr.
To do so, just execute:

     composer global require consolidation/cgr
     export INSTALL_DIR=$HOME/.composer/global/drunomics/phapp-cli
     mkdir -p $INSTALL_DIR && echo "{}" > $INSTALL_DIR/composer.json
     composer --working-dir=$INSTALL_DIR config repositories.drunomics composer https://packages.drunomics.com
     composer --working-dir=$INSTALL_DIR config minimum-stability dev
     composer --working-dir=$INSTALL_DIR config prefer-stable true
     cgr drunomics/phapp-cli

## Usage

Run `phapp list` to show a list of support commands. A few important commands
are highlighted below:


### build

  - Build the project as configured in phapp.yml:
  
        phapp build
        
    If no build command configured, phapp will just run a composer install.

  - Build a certain branch and commit the build result in `build/{{ branch }}`:
  
        phapp build {{ branch }}