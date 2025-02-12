# DT4H AI Dashboard front-end Demo

This repository contains the front-end of an [openVRE](https://github.com/inab/openVRE)-based analysis platform customized for DT4H. It corresponds to a PHP-based web application enabling a cloud-based analysis environment offering
- a user-friendly web-based interface that integrates a number of pluggable resources:
	- analysis tools or pipelines,
	- interfaces to external data repositories,
	- visualizaters
- an scalable backend for cloud computing compatible with OCCI middlewares like OpenNebula or OpenStack.

> **_NOTE:_**  Currently, the AI Dashboard is only for demonstration purposes.

## Related repositories
- Dashboard Demo full compute platform deployment: https://github.com/DataTools4Heart/AI-dashboard-platform-demo/
- Dashboard Runner for FEM tasks: https://gitlab.bsc.es/inb/dt4h/FEM-runner

### Requirements
- Web Server (*e.g.* Apache2)
- Mongo Client: mongodb-org-shell, mongodb-org-tools, php-mongo
- Oracle Grid Engine cluster queue client (formerly Sun Grin Engine): gridengine-client gridengine-common
- OpenID Connect/OAuth 2.0 client of an Identity Provider

### openVRE installation
This repository contains all the code to build a functional openVRE-based analysis platform, *prior* installation and configuration. The final product is an online application with the virtual research environment integrating for demonstration purposes:
- one analysis tool: tool-skeleton
- one visualizer: [NGL](https://nglviewer.org/) viewer)

See [the installation guide](./install/README.md) for more detailed instructions.

##### Dependencies
- PHP (>=7.3)
- Composer : https://getcomposer.org/doc/00-intro.md

### openVRE core

openVRE cores is a server-side web application mainly written in PHP modules, as well as some Java Script based libraries.  Following, a short description of the content of this repository. 

- composer.json: 3rd party software requirements
- [config](./config) : configuration files 
	- [settings](./config/globals.inc.php.sample) sample for the global application settings
	- [bootstrap](./config/bootstrap.php) bootstrap VRE application
- [install](./install) : installation instructions and data 
	- [install](./install/README.md) instructions
	- [database](./install/database) skeleton with structural collections
	- [data](./install/data) datasets and sample schemas
- [public](./public) : web application elements under the web server root directory
	- **web pages**
	- [home](./public/home) pages for 'Homepage' section
	- [workspace](./public/workspace) pages for 'User Workspace' section
	- [getdata](./public/getdata) pages for 'Get Data' section
	- [launch](./public/launch) pages for 'Run Tool / Visualizers' section
	- [help](./public/help) pages for 'Help' section
	- [helpdesk](./public/helpdesk) pages for 'Helpdesk' section
	- [admin](./public/admin) pages for 'Admin' section
	- [user](./public/user) pages for 'User Profile' section
	- [cookies](./public/cookies) notification
	- **libraries**
	- [applib](./public/applib) : pages' backend
	- [assets](./public/assets) : pages' client scripts
	- [phplib](./public/phplib) : VRE libraries and classes
	- [htmlib](./public/htmlib) : html templates
	- **content**
	- [tools](./public/tools) : web form, assets and summart page for integrated tools
	- [visualizers](./public/visualizers) : visualizers code
- [scripts](./scripts) : maintainance scripts
