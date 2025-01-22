# ASA-Inactive-Devices-Notifications
This repo shows how inactive devices can be detected using Azure Stream Analytics. 

## Case
In the dummy dataset there are 2 devices, which send a message every hour between 01-01-2025 and 08-01-2025. Device001 is constantly running and device002 experiences downtime occassionally. 
The goal is to detect when a device has been offline for the past 24 hours, but it was working the 24 hours previous, then it sends a notification of "Signal disconnected". 
And it should detect when a device comes back online after being offline for 24 hours, by sending a notification of "Signal back online".

    ![draft_asa_job](https://github.com/user-attachments/assets/212f59fc-a63f-4f4f-a8a0-edc884e561d0)

## Credits
The code provided is inspired by the solution in https://stackoverflow.com/questions/67920749/how-to-detect-if-no-data-ingested-in-any-iothub-device-using-stream-analytics
