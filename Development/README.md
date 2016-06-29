
![alt tag](http://www.agile-project-iot.eu/wp-content/uploads/2016/03/logo-png-transparent-02_small.png)

# AGILE Architecture: The Development View

This view of the AGILE architecture aims at describing how the software of AGILE is decomposed from a development perspective into software components that will be developed and/or integrated into the AGILE software solution.
The following picture offers a representation of main software components that will be delivered by AGILE project.


![alt tag](http://agile-iot.eu/wp-content/uploads/2016/06/AGILE_arch_DevView.jpg)


AGILE components will run partly in the cloud and partly on the IoT Gateway. 

## AGILE Gateway Components:

At the gateway level, we can distinguish, from a software components point of view, the following types of software bundles:
* Gateway OS: At the lower level, the operating system hosting the whole AGILE services and applications.  As already described, the AGILE OS will be based on linux distributions with reference target distributions being Ubuntu Core, Raspbian and distributions created with [Yocto].  In terms of microprocessor architectures, AGILE targets multiple architectures with specific focus on  ARM, x86/x86 64  architectures. 
* Containerization infrastructure: on top of the operating system a layer offering containerization functionalities allowing to encapsulate AGILE services and AGILE applications into isolated micro-services hosted the operating system (Ubuntu Snappy and Docker as potential containerization technologies to be adopted);
* AGILE Framework:  a set of components aggregating a set of “DevOps” services to be exposed to AGILE developers to support development of AGILE IoT applications and to manage AGILE infrastructure (gateway and related cloud services). In particular, development services are exposed to developers through the AGILE API and related development libraries (AGILE SDKs);
* AGILE Apps: the infrastructure and components used to host and manage IoT AGILE applications deployed and running into AGILE Gateway;
* Remote Gateway and Fleet management: components used to remotely manage Gateway resources (on the AGILE Framework side) and hosted IoT applications (on the AGILE app side).



Learn more @ http://agile-iot.eu/

Follow us on Twitter: [@agile_iot]

[@agile_iot]:<https://twitter.com/agile_iot>
[AGILE API]:<https://github.com/Agile-IoT/agile-api-spec>
[Yocto]:<https://www.yoctoproject.org/>