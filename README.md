# AEM 6.4 Code Challenge

This project contains source generated from the AEM Maven Archetype (version 14) and is compatible with AEM 6.3 SP1+ and AEM 6.4. For the purposes of this code challenge we will be using AEM 6.4 GA.

## Task


Create an OSGi service to contact the attached API endpoint (unsecured - credentials aren't necessary) with query parameters passed.

Create a Path based Servlet(eg: /bin/radek) which would call the API through service and get the xml data. Parse the XML data returned in response and create nodes through API in any content path (ex: /content/radek/) from the xml response.

ex: Each xml data needs to be a node(can be named anything) and each data in xml can be added as property

Eg: <radek kod="AUD" mena="dolar" mnozstvi="1" kurz="16,471" zeme="Australie"/>  

If the servlet is hit the second time it would not override the nodes.



All of the required Maven dependencies have been added to the project already.

API URL: https://www.cnb.cz/cs/financni_trhy/devizovy_trh/kurzy_devizoveho_trhu/denni_kurz.xml
*Use DS Annotations

## Modules

The main parts of the project are:

* core: Java bundle containing all core functionality like OSGi services, listeners or schedulers, as well as component-related Java code such as servlets or request filters.
* ui.apps: contains the /apps (and /etc) parts of the project, ie JS&CSS clientlibs, components, templates, runmode specific configs as well as Hobbes-tests
* ui.content: contains sample content using the components from the ui.apps
* ui.tests: Java bundle containing JUnit tests that are executed server-side. This bundle is not to be deployed onto production.
* ui.launcher: contains glue code that deploys the ui.tests bundle (and dependent bundles) to the server and triggers the remote JUnit execution
