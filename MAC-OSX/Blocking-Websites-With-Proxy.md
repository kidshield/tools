# Blocking Websites with Proxy

The reason for this is due to how difficult it to use MAC OSX built-in parental control tools.  It is hell. 

If you are technical this is a better approach (I believe) 

This is what I use

* [AnyProxy](http://anyproxy.io/en/#install)
* [Nodejs](https://nodejs.org/en/download/)

## Setup

Install [Nodejs](https://nodejs.org/en/download/)

### Install & Configure Anyproxy

    npm install -g anyproxy 

Create a rules file, more details on how to [here](http://anyproxy.io/en/#rule-samples) 

    vi ~/.rules.js


[http://anyproxy.io/en/#modify-the-request-target] is the rule I used as a sample and [this](https://gist.github.com/csanz/e7e203b6dd252d49c61da8e1f3bb0360) is the one I'm currently using and modifying. 

Then you start any proxy with the rules and turn on the Proxy on host mac. 

    anyproxy --rule ~/.rules.js


## More info on Networking

You simply just use the `networksetup` command. You can find the params you need to you this way

    networksetup -setwebproxy | grep "setproxy"

    networksetup -setwebproxy <networkservice> <domain> <port number> <authenticated> <username> <password>
    networksetup -setsecurewebproxy <networkservice> <domain> <port number> <authenticated> <username> <password>

Then look up your network services with `networksetup -listallnetworkservices`

Thank you update... 

    networksetup -setwebproxy Wi-Fi 127.0.0.1 8001
    networksetup -setsecurewebproxy Wi-Fi 127.0.0.1 8001

## Turn On/Off

To turn them off is also super simple

Format 

    networksetup -setwebproxystate <networkservice> <on off>
    networksetup -setsecurewebproxystate <networkservice> <on off>

Example Turn On

    networksetup -setwebproxystate Wi-Fi on
    networksetup -setsecurewebproxystate Wi-Fi on

Example Turn Off

    networksetup -setwebproxystate Wi-Fi off
    networksetup -setsecurewebproxystate Wi-Fi off

## Verify It is Set

Format

    networksetup -getwebproxy <networkservice>
    networksetup -getsecurewebproxy <networkservice>

Example

    networksetup -getwebproxy Wi-Fi
    networksetup -getsecurewebproxy Wi-Fi




You simply just use the `networksetup` command. You can find the params you need to you this way

    networksetup -setwebproxy | grep "setproxy"

    networksetup -setwebproxy <networkservice> <domain> <port number> <authenticated> <username> <password>
    networksetup -setsecurewebproxy <networkservice> <domain> <port number> <authenticated> <username> <password>

Then look up your network services with `networksetup -listallnetworkservices`

Thank you update... 

    networksetup -setwebproxy Wi-Fi 127.0.0.1 8001
    networksetup -setsecurewebproxy Wi-Fi 127.0.0.1 8001

## Turn On/Off

To turn them off is also super simple

Format 

    networksetup -setwebproxystate <networkservice> <on off>
    networksetup -setsecurewebproxystate <networkservice> <on off>

Example Turn On

    networksetup -setwebproxystate Wi-Fi on
    networksetup -setsecurewebproxystate Wi-Fi on

Example Turn Off

    networksetup -setwebproxystate Wi-Fi off
    networksetup -setsecurewebproxystate Wi-Fi off

## Verify It is Set

Format

    networksetup -getwebproxy <networkservice>
    networksetup -getsecurewebproxy <networkservice>

Example

    networksetup -getwebproxy Wi-Fi
    networksetup -getsecurewebproxy Wi-Fi


