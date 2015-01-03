STM32F4DISCOVERY C PROJECT WORKSPACE VARIANT
===

This workspace variant treats underlying projects as a kind of attached modules. It is designed for learning purpose to minimize any filesystem operations for new projects creation. 

So to create a project you should do the following:
* create a project folder under src directory
* create a Makefile inside that folder
* create own project stm32f4xx_conf.h file and make necessary configurations there
* create & include your own or library sources within project's Makefile

Project Makefile
---

Project Makefile has to define next variables:
* SRC - this is the space separated list of your source files
* NAME - this is the name used for compiled binaries
* (optional) PROJECT_SYSTEM_STM32F4XX - if equals true, than the default system_stm32f4xx.c is not included, but project should provide it's own variant through the SRC variable

After these variables are defined Makefile.common should be included via ```include ../../Makefile.common```

The common makefile assumes that the arm gcc toolchain is installed and it's executables are in the system's PATH variable. The same as the st-link utility. Please refer for [this post](http://denyadzi.github.io/blog/2014/12/25/installing-neccessary-tools-for-stm32f4discovery/) for details.

stm32f4xx_conf.h file
---

This file provides a way to control the library usage and is needed within every project folder. Please refer to that file for more information

Writing code
---

Just include ```#include "stm32f4_discovery.h"``` in your source, configure project stm32f4xx_conf.h file and you're ready for discovery. Do not forget to include library source files you need in project Makefile.

Please refer to hello_world project for more details


Feel free to make any changes to this workspace corresponding your needs.
