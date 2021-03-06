---
platform: windows-10-iot-enterprise-ltsb
device: ark-1123c
language: csharp
---

Run a simple sample on ARK-1123C device running Windows 10 IoT Enterprise LTSB
===
---

# Table of Contents

-   [Introduction](#Introduction)
-   [Step 1: Prerequisites](#Step-1:-Prerequisites)
-   [Step 2: Prepare your Device](#Step-2:-PrepareDevice)
-   [Step 3: Build and Run the Sample](#Step-3:-Build)
-   [Next Steps](#NextSteps)

<a name="Introduction"></a>
# Introduction

**About this document**

This document provides step-by-step guidance on how to connect an ARK-1123C device running **Windows 10 IoT Enterprise LTSB** with Azure IoT SDK. This multi-step process includes:
-   Configuring Azure IoT Hub
-   Registering your IoT device
-   Build and deploy Azure IoT SDK on device

<a name="Step-1:-Prerequisites"></a>
# Step 1: Prerequisites

-    Computer with GitHub installed and access to the
    [azure-iot-sdk-csharp](https://github.com/Azure/azure-iot-sdk-csharp) GitHub
    private repository.
-   ARK-1123C.
-   Install any version of [Visual Studio 2015](https://www.visualstudio.com/downloads/download-visual-studio-vs.aspx).
-   Install [Microsoft Azure SDK](http://www.microsoft.com/download/details.aspx?id=48178).
-   [Setup your IoT hub][lnk-setup-iot-hub]
-   [Provision your device and get its credentials][lnk-manage-iot-hub]

<a name="Step-2:-PrepareDevice"></a>
# Step 2: Prepare your Device
##  Install Windows 10 IoT Enterprise LTSB on ARK-1123C
-   Create a bootable USB Drive. Please follow this guide on how to create a bootable drive (<https://www.microsoft.com/en-us/download/windows-usb-dvd-download-tool>).
-   Insert the bootable USB Drive from the previous step into your ARK-1123C. Turn on your ARK-1123Cdevice and press the **Delete** key.
-   Change the BIOS Boot option filter to **UEFI and Legacy**.
-   Change the **Boot Option Priorities** to boot from your USB Drive.
-   Save changes and restart your ARK-1123C. Follow on screen instructions to install Windows Operating System on your ARK-1123C.

<a name="Step-3:-Build"></a>
# Step 3: Build and Run the sample

-   Download the [Azure IoT SDK](https://github.com/Azure/azure-iot-sdk-csharp) and save them to your local repository.
-   Start a new instance of Visual Studio 2015.
-   Open the **iothub_csharp_client.sln** solution in the `csharp\device` folder in your local copy of the repository.
-   In Visual Studio, from Solution Explorer, navigate to the **samples** folder.
-   In the **DeviceClientAmqpSample** project, open the ***Program.cs*** file.
-   Locate the following code in the file:

        private const string DeviceConnectionString = "<replace>";
        
-   Replace `<replace>` with the connection string for your device.
-   In visual Studio, under Solution Explorer, right-click the **DeviceClientAmqpSample** project, click ***Debug &minus;&gt; Start new instance*** to build and run the sample. The console displays messages as the application sends device-to-cloud messages to IoT Hub.
-   See [Manage IoT Hub][lnk-manage-iot-hub] to learn how to observe the messages IoT Hub receives from the application and how to send cloud-to-device messages to the application.

<a name="NextSteps"></a>
# Next Steps

You have now learned how to run a sample application that collects sensor data and sends it to your IoT hub. To explore how to store, analyze and visualize the data from this application in Azure using a variety of different services, please click on the following lessons:

-   [Manage cloud device messaging with iothub-explorer]
-   [Save IoT Hub messages to Azure data storage]
-   [Use Power BI to visualize real-time sensor data from Azure IoT Hub]
-   [Use Azure Web Apps to visualize real-time sensor data from Azure IoT Hub]
-   [Weather forecast using the sensor data from your IoT hub in Azure Machine Learning]
-   [Remote monitoring and notifications with Logic Apps]   

[Manage cloud device messaging with iothub-explorer]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-explorer-cloud-device-messaging
[Save IoT Hub messages to Azure data storage]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-store-data-in-azure-table-storage
[Use Power BI to visualize real-time sensor data from Azure IoT Hub]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-live-data-visualization-in-power-bi
[Use Azure Web Apps to visualize real-time sensor data from Azure IoT Hub]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-live-data-visualization-in-web-apps
[Weather forecast using the sensor data from your IoT hub in Azure Machine Learning]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-weather-forecast-machine-learning
[Remote monitoring and notifications with Logic Apps]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-monitoring-notifications-with-azure-logic-apps
[lnk-setup-iot-hub]: ../setup_iothub.md
[lnk-manage-iot-hub]: ../manage_iot_hub.md
