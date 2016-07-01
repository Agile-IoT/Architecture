
![alt tag](http://www.agile-project-iot.eu/wp-content/uploads/2016/03/logo-png-transparent-02_small.png)

# AGILE Architecture: The Logical View

The following picture gives a representation of functional components of AGILE Software Architecture.

![alt tag](https://camo.githubusercontent.com/0e9d051567a2c0a683241bcf3338e1f28191168e/687474703a2f2f6167696c652d696f742e65752f77702d636f6e74656e742f75706c6f6164732f323031362f30362f4147494c455f6c6f676963616c5f6172636869746563747572652e706e67)

AGILE Software stack is divided into two main bundles:

-> The full software stack that will run on the AGILE Gateway, i.e. on edge devices that will interface IoT Devices and that will host local IoT applications on the gateway itself;

-> The set of components that will run into the cloud offering capabilities for communicating and managing AGILE Gateways from remote and offering  integrations with external cloud services for data management.
Focusing on the AGILE Gateway, we can identify different logical layers composing the full software stack of AGILE:
* At the lower level, the operating system running on the gateway itself. The reference OS for AGILE is a Debian–based linux for embedded devices. Reference distributions for AGILE development are: Ubuntu Core, Raspbian and distributions created with [Yocto].  In terms of microprocessor architectures, AGILE targets multiple architectures with specific focus on  ARM, x86/x86 64  architectures. 
* Remote Gateway and Fleet Management System: this layer deals with all the capabilities needed to allow a remote access to the gateway for management and for managing a fleet of remote gateways in an efficient and simple way. 
* Device Discovery, Communication and Data Storage: this layer is composed by three main components:
    * IoT Device & Hw module Discovery: module for device and HW module discovery (could be also separate components): Responsible for detecting the wireless modules (LoRA, ZigBee, BLE, etc.) user plugs on the gateway and enabling the proper drivers. Scans the network (WiFi, Ehernet, wireless) for connected IoT devices using appropriate standards (KNX, uPNP, Zwave, Thread, etc.) or family of standards (AllJoyn, oneM2M, etc.). Should be a microservice exposing functionality over an API to other components. 
    * IoT Device Communication: A micro-service responsible for implementing the communication with connected IoT Devices. Once a device is detected, it exposes the features of the device and allows data polling or sending actuations to the device by supporting a number of various IoT device protocols (KNX, Zwave, ZigBee, Thread, etc.). It should provide an API for other components to use this service. In addition, it will feature an easy way of integrating future protocols.
    * Data Storage: a local NoSQL database for managing IoT device data. Should be lightweight and expose an API (used as micro-service) at the same time for data management. 
* Gateway and Device Management layer: this layer is composed by components dedicated to the management of the gateway itself and to all managed connected devices:
    * Gateway Management UI: The UI for managing the Gateway as a device: see resource status, perform reboots, updates of OS and various components, control also the I/O of the board, manage devices directly connected to the gateway;
    * Device Management UI: User Interface for managing the IoT devices connected (wirelessly or wired) to the gateway. Should use the device discovery and communication modules to list automatically found devices and provide real-time data readings or actuations.
    * Application-level Support Services this layer is composed by services needed to support the creation and deployment of applications running on the AGILE Gateway. It is composed by the following three main components:
    * IoT Data management Interface: Interface for managing IoT data from connected devices. Managing refers to retrieval from the local storage, realtime view, data visualization, etc. The component will have a graphical UI and potentially an API/SDK to provide services (e.g., visualization of data queries) to other components (e.g. the App Developer UI.
    * IoT App Developers UI: The visual interface (Node-RED like) for creating application logic and running it on the gateway. It will be web-based UI, which would use the recommender for proposing nodes (functional modules) and workflow examples based on the configuration (hw) of the gateway. The collaboration tool shall enable the easy share of data or workflow editing between users. It should also support popular IoT protocols like MQTT, WebSockets, CoAP, etc.
    * IoT Apps: this component is in charge of supporting the execution of IoT applications using services offered by various components via AGILE APIs, offering services to install, upgrade and uninstall applications inside AGILE Gateway. IoT Apps will be bundled as “bundles” and can be mapped onto “Ubuntu Snaps” or “docker containers”.
    
* Additional AGILE Gateway services:
    * IoT App Recommendation: this is a component at the service of IoT developers and AGILE end users, offering recommendations based on AGILE Gateway configuration, that will suggest type of devices that can be integrated in the current gateway configuration, recommendations on which network modules to be used based on gateway usage scenarios, and what IoT applications available in the AGILE repository can be installed and supported by current gateway configuration.
    * AGILE APIs: AGILE capabilities and services are offered to developers through a set of predefined APIs. Two different logical types of APIs can be identified in AGILE and exactly:
    * AGILE integration APIs: these APIs are intended to allow AGILE developers to extend and integrate additional services and capabilities into the AGILE Gateway (e.g. support for a new IoT protocol implementation);
    * AGILE APIs for IoT Apps Development: these APIs will be used by third party developers in order to develop IoT Apps using AGILE Gateway services that will be delivered and axecuted on the AGILE Gateway itself. These APIs are practically a subset of APIs described above. 


Focusing on the AGILE Cloud side, we can identify different services that complement and complete capabilities offered by AGILE at the gateway level:
Data Cloud services:

* AGILE Data Cloud Integration: AGILE will offer components to support connectors (libraries and APIs support) allowing AGILE users to extend the capabilities of the gateway by managing data and deploying apps in existing public and private cloud infrastructures;
* Remote Gw Management: backend services and user interfaces used to remotely manage the/a fleet of Gateways. These services are the cloud-counterpart and integrate with Gateway Management features available on each AGILE Gateway;   
* IoT Apps Repository:  the cloud repository where AGILE IoT apps will be described stored;
o	IoT Apps Recommender: cloud services to perform recommendations to end users about available IoT Apps in the repository.




Learn more @ http://agile-iot.eu/

Follow us on Twitter: [@agile_iot]

[@agile_iot]:<https://twitter.com/agile_iot>
[AGILE API]:<https://github.com/Agile-IoT/agile-api-spec>
[Yocto]:<https://www.yoctoproject.org/>