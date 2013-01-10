Garmin Edge Agent
=================

A Mac OS X LaunchAgent to automatically update activities from a Garmin Edge to Garmin Connect

How to install
--------------

Clone this repository

Install dependencies using Composer (http://getcomposer.org/doc/00-intro.md#installation-nix)
    
    curl -s https://getcomposer.org/installer | php
    php composer.phar install

Create your config file
    
    cp config.json.default config.json

Fill in your username and password for Garmin Connect in the config, for example:

    {"username": "tom", "password": "qwerty"}

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
* Automatically upload to Strava

FAQ
---

Why PHP?
~~~~~~~~
Why not?

When will it support Windows?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
When someone kindly sends me a pull request.
