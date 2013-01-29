Garmin Edge Agent
=================

A Mac OS X LaunchAgent to automatically upload activities from a Garmin Edge to Garmin Connect and/or Strava.

How to install
--------------

Clone this repository

Install dependencies using Composer (http://getcomposer.org/doc/00-intro.md#installation-nix)
    
    curl -s https://getcomposer.org/installer | php
    php composer.phar install

Create your config file
    
    cp config.json.default ~/.garmin-edge-agent/config.json

Fill in your username and password for Garmin Connect/Strava in the config, for example:

    {
        "garmin": {
            "username": "tom",
            "password": "qwerty"
        },
        "strava": {
            "email": "tom@test.com",
            "password": "qwerty"
        }
    }


Copy the agent file
    
    cp garmin-edge-agent.plist ~/Library/LaunchAgents/garmin-edge-agent.plist

Change the "ProgramArguments" in garmin-edge-agent.plist to point to the correct path

Load the agent
    
    launchctl load ~/Library/LaunchAgents/garmin-edge-agent.plist

Uninstalling
------------

Unload the agent

    launchctl unload ~/Library/LaunchAgents/garmin-edge-agent.plist

To-do
-----

* Easier installation/configuration
* Keep a backup of *.fit files locally
