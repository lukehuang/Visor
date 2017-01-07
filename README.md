![Python 3.4](https://img.shields.io/badge/python-3.4-green.svg)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)]()
[![in progress](https://img.shields.io/badge/in%20progress-3-orange.svg)](https://github.com/xuwenyihust/Visor/projects/1)
# Visor: Real-time Log Monitor - [READ the Docs](https://goo.gl/F0rADZ)

Web page: *https://xuwenyihust.github.io/Visor/*

A real-time log monitor that support different log patterns: Apache access logs and Apache error logs.

Monitor multiple log sources, done in realtime using Spark Streaming.

Has its own fake log generator to generate likely log files for analytics.

## Documentation
The Visor's documentation is hosted on GitBook at https://xuwenyihust.gitbooks.io/visor-real-time-log-monitor/content/. 

## Log Format
### Apache Log

**Access Log**
> 127.0.0.1 user-identifier frank [10/Oct/2000:13:55:36 -0700] "GET /apache_pb.gif HTTP/1.0" 200 2326

**Error Log**
> [Wed Oct 11 14:32:52 2000] [ERROR] [pid 35708:tid 4328636416] [client 127.0.0.1] client denied by server configuration: /export/home/live/ap/htdocs/test

**Fields**

|Access Log Fields|Error Log Fields|
|-----|-----|
|IP address of the client|Date and time|
|RFC 1413 identity of the client|Message level|
|UserID of the client|Process ID|
|The time that the request was received|Client Address|
|Request line from the client|Detailed error message|
|HTTP status code||
|Size of the object returned to the client||


## Configuration
### $PYTHONHOME
Add the root directory to `$PYTHONHOME`.

### Configuration Files
Use JSON for configuration files, stored at **$HOME/config**. Here are part of the configurations.
```json
{
    "heartbeat" : { 
        "interval": "3",
        "message": "HEARBEAT"
    },
    "warn": {
        "interval": {
            "min": 5,
            "max": 30
            },
        "message": [
            "Have no idea what the professor is talking about", 
            "My phone is out of battery", 
            "Forgot to bring my wallet with me", 
            "Do not play overwatch" 
        ]
    }
```
### Configure log contribution

## Usage

### Log Generation

**Apache Access Log**
```
python3.4 ../src/fake_log_gen/fake_log_gen.py fake_access_file.log access
```

**Apache Error Log**
```
python3.4 ../src/fake_log_gen/fake_log_gen.py fake_error_file.log error
```

### Machine Learning Model Training

### Log Analysis

## Example

## Requirements
* Python 3.4

## Resources
* [Apache Log Files](https://httpd.apache.org/docs/1.3/logs.html)

## License
See the LICENSE file for license rights and limitations (MIT).

