# Tivan - the collector of events

![](docs/tivan.jpg)

## Overview

This collector meant to be a highly available RESTful web service that receives events from client devices and secures them agnostic of cloud targets.

The collector is implemented in Go, runs on Ubuntu and OSX.

Events are sent in [Protobuf](https://github.com/sub-ninja/tivan/blob/master/payload/payload.proto) messages.

Currently supported cloud targets are (tested throughput two years old Macbook in parentheses):

* Amazon Web Services Simple Notification Service (AWS SNS - ?),
* Microsoft Azure Blob Store (MS ABS - 2 million per second),
* Microsoft Azure Queue Storage (MS AQS - 12 per second).

6Wunderkinder used a similar node.js based service that secured messages in AWS SNS. Based on experiences we've rewritten the app in Go that can handle 60x more requests on equal hardware resources.

Inspired by UNIX philosophy (do one thing and do it well) and [Marcio Castilho's approach](http://marcio.io/2015/07/handling-1-million-requests-per-minute-with-golang/).

## Clients

No official client is available at the moment. If you want to write your own please check out our [pseudo client specification](docs/pseudo-client.md).

## License

Copyright © 2016, Bence Faludi.

Distributed under the MIT License.