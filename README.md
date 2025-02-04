# ASA-Inactive-Devices-Notifications

This repo shows how inactive devices can be detected using Azure Stream Analytics.

## Test case

A Stream Analytics job handles messages from multiple devices via an Azure IoT Hub input.

If a device stops sending messages for more than five minutes, it is considered disconnected.

If it starts sending data later on, it is considered connected (again).

## Test data

The follow sample data is provided:

- device 1 offers data every 1 minute for 30 minutes (starting point 1 second after full minute)
- device 2 offers data every 1 minute for 30 minutes (starting point 1 second after full minute)
- device 3 offers data every 1 minute for 30 minutes with one gap of 4:59 minutes (starting point 1 second after full minute)
- device 4 offers data every 1 minute for 30 minutes with one gap of 5:01 minutes (starting point 1 second after full minute)
- device 5 offers data every 1 minute for 30 minutes with one gap of 10:01 minutes (starting point 1 second after full minute)
- device 6 offers data every 1 minute for 30 minutes with one gap of 5:01 minutes (starting exactly on full minute)

Only devices 4, 5, and 6 should generate disconnnect and connect events.

## Visual Studio Code extension

This Stream Analytics job project is developed and tested using the extension for [Visual Studio Code](https://learn.microsoft.com/en-us/azure/stream-analytics/quick-create-visual-studio-code).

## Credits

This solution is inspired on the approach suggeded by Florian Eiden in [this Stackoverflow question](https://stackoverflow.com/questions/67920749/how-to-detect-if-no-data-ingested-in-any-iothub-device-using-stream-analytics). 

