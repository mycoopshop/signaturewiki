Cross-Platform Component Object Model (XPCOM), a cross-platform component model from Mozilla, is similar to CORBA and Microsoft® COM. It has multiple language bindings and IDL descriptions, so the XPCOM components can be used and implemented in JavaScript, the Java™ language, Python, and C++. You can plug your custom functions into the framework and connect them with other components.

XPCOM supports the Windows® and Linux® platforms. In this article, all the instructions, environment variables, and command line will be in a Linux operating system.

In this article, learn how to:

    Define the XPCOM interface and write in the definition file.
    Implement on demand behavior for XPCOM components.
    Integrate and test XPCOM components with Firefox. 

Prerequisites

To follow along, you will need to:

    Download the Gecko SDK package. The Gecko SDK, also called XULRunner SDK, is a set of XPIDL files with headers and utilities to develop XPCOM components that can then be accessed from XUL using JavaScript. 

    Make sure the Firefox browser is installed on your Linux system. You will integrate and test the sample XPCOM in the Firefox browser.

Define XPCOM interfaces

XPCOM provides browser application interfaces you can use to access low-level operations, such as system hardware diagnostics, massive file operations, and system health real-time monitoring. Generally, XPCOM functions are written in C/C++, interfaces are linked as a dynamic library, and the connection between the JavaScript and C++ layer is XPConnect. Figure 1 shows a typical interaction between the browser and XPCOM.
Figure 1. Interaction between browser and XPCOM
Graphic depiction of interaction between browser and XPCOM

In Figure 1, sample.js contains JavaScript to call XPCOM interfaces. The code implements a call to the XPCOM interface with sufficient parameters and gets results from it when XPCOM finishes the task.

First, you have to define the interfaces you want to expose to the browser or the abilities you want to provide to the Web application. Interfaces are written in an .idl file. Listing 1 shows a sample interface definition file.
Listing 1. Sample IDL contents
1
2
3
4
5
6
7
8
9
	
#include "nsISupports.idl"
//658abc9e-29cc-43e9-8a97-9d3c0b67ae8b
[scriptable, uuid(658ABC9E-29CC-43E9-8A97-9D3C0B67AE8B)]
interface sample : nsISupports
{
  long    sample_numeric(in long a, in long b);
  string  sample_string();
  void    sample_nonreturn();
};

Each XPCOM component will have an interface name. In Listing 1, the name is sample, and three common function prototypes are shown. 658abc9e-29cc-43e9-8a97-9d3c0b67ae8b is an UUID; each XPCOM component has this unique ID. On a Linux system, you can easily get this ID by using the genuuid command in the shell: linux-d8xr:#: genuuid.

To translate the interface definition file to the C++ source file, you need the utilities in the gecko-sdk package (see Prerequisites). You can install gecko-sdk with the default option. Typically, it will store contents in /opt/gecko-sdk. The directory structure should look very similar to Listing 2.
Listing 2. Gecko-sdk installed contents
1
2
3
4
	
drwxrwxrwx 2 500 501   144 Jun  9  2006 bin
drwxrwxrwx 2 500 501  7984 Jun  9  2006 idl
drwxrwxrwx 5 500 501 10312 Jun  9  2006 include
drwxrwxrwx 2 500 501   368 Jun  9  2006 lib

To translate the interfaces defined in .idl, you need xpidl in the bin folder. The example uses it twice to generate an .xpt file and an .h file. The .xpt is a binary form of IDL, and the .h is a header file containing a base-class definition of your XPCOM interfaces. Typically, you wouldn't modify anything in this header file. However, to extend and inherit from the base class, you can add more private methods and variables for extension. Listing 3 shows an example of generating the command on Linux.
Listing 3. Generate .xpt and header file
1
2
3
4
	
XPID_BIN=the path to geck-sdk/bin/xpidl
GECK_SDK_PATH=the path to geok-sdk
     $(XPID_BIN) -m header -I $(GECKO_SDK_PATH)/idl -o sample sample.idl
     $(XPID_BIN) -m typelib -I $(GECKO_SDK_PATH)/idl -o sample sample.idl

If you define the interface in the sample.idl file, you will get sample.idl and sample.h after the commands are executed accurately.
Extend, customize, and implement XPCOM methods

In this section, you start the real XPCOM function development. As mentioned, you don't modify the two generated files: You inherit the interface from them. Sometimes, you might not complete all the interface at the beginning of the development phase. For example, sample.h needs to be regenerated and overwritten if you decide to modify, add, or delete interfaces of an XPCOM component. You'll want to keep the contents and structure of the base class as simple as possible. In the extend file, you can add more complicated methods and functions. Listing 4 shows an example of how to write your extend class.
Listing 4. Contents of extend class sample
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
	
#ifndef _SAMPLEEXTEND_H_
#define _SAMPLEEXTEND_H_
 
#include "sample.h"
 
#define SAMPLE_COMPONENT_CONTRACTID "@cn.ibm.com/XPCOM/sample;1"
#define SAMPLE_COMPONENT_CLASSNAME "Sample XPCOM Interface Layer"
#define SAMPLE_COMPONENT_CID  { 0x658abc9e, 0x29cc, 0x43e9, 
{ 0x8a, 0x97, 0x9d, 0x3c, 0x0b, 0x67, 0xae, 0x8b } }
 
//658abc9e-29cc-43e9-8a97-9d3c0b67ae8b
class sampleextend : public sample
{
 public:
  NS_DECL_ISUPPORTS
  NS_DECL_SAMPLE
 
  sampleextend();
  virtual ~sampleextend();
  //additional member functions
  int sampleextend_add();
};
#endif

Three required macros are shown above in bold.

SAMPLE_COMPONENT_CONTACTID
    In JavaScript, when custom code invokes anXPCOM method Firefox will look into the components registered to it and find the one matching the ID, then pass the parameters from JavaScript to the method entry. 
SAMPLE_CONTACT_CLASSNAME
    The name of your own XPCOM component.
SAMPLE_COMPONENT_CID
    The UUID that was generated. 

For the browser to benefit from the functions provide by an XPCOM component, the component must first be registered to the browser. There is a form you must prepare for your component. The three macros described above must be put in the form. The browser will be aware of your components upon start-up, and register them in the component list. Listing 5 shows a registration form for the sample.idl.
Listing 5. Sample component registration form
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
	
#include "nsIGenericFactory.h"
#include "sample.h"
#include "sampleextend.h"
 
NS_GENERIC_FACTORY_CONSTRUCTOR(sampleextend)
 
static nsModuleComponentInfo components[] =
{
  {
    SAMPLE_COMPONENT_CLASSNAME,
    SAMPLE_COMPONENT_CID,
    SAMPLE_COMPONENT_CONTRACTID,
    sampleextendConstructor,
  }
};
 
NS_IMPL_NSGETMODULE("sampleModule", components)

At this point, you have:

    sample.h, which contains the interface base class
    sampleextend.h, which contains extract private methods and functions definitions
    sampleComponent.cpp, which is a component registration form for the browser

It is highly recommended that you put the implementation of functions and service for your XPCOM in an individual project file. You don't need to modify these three files unless there's a need to modify the interfaces of your component. Listing 6 shows a sample.
Listing 6. XPCOM service implementation sample
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
80
81
82
83
84
85
86
87
88
89
90
91
92
93
94
95
96
97
98
99
100
101
102
103
104
	
#include "sample.h"
#include "sampleextend.h"
 
#include "nsMemory.h"
#include "plstr.h"
#include "stdio.h"
 
#include <iostream>
#include <iomanip>
#include <string>
#include <sstream>
#include <dlfcn.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <unistd.h>
#include <dirent.h>
#include <fcntl.h>
 
 
 
using namespace std;
 
NS_IMPL_ISUPPORTS1(sampleextend, sample)
 
sampleextend::sampleextend()
{}
 
sampleextend::~sampleextend()
{}
 
/* long sample_numeric (in long a, in long b); */
NS_IMETHODIMP sampleextend::Samplenumeric(PRInt32 a, PRInt32 b, PRInt32 *_retval)
{
  *_retval = a+b;
  return NS_OK;
}
 
/* string sample_string (); */
NS_IMETHODIMP sampleextend::Samplestring(char **_retval)
{
  *_retval = (char*) nsMemory::Alloc(20);
  PL_strcpy(*_retval,"hello from xpcom");
  return NS_OK;
}
 
/* void sample_nonreturn (); */
NS_IMETHODIMP sampleextend::Samplenonreturn(void)
{
  return NS_OK;
}
 
/* additional functions */
int sampleextend::sampleextend_add()
{
  return 1;
}
 
 
Here is an integrated makefile for generating headers and 
compiling sources for the sample component:
 
GECKO_SDK_PATH = $(PWD)/gecko-sdk/gecko-sdk
XPID_BIN = $(GECKO_SDK_PATH)/bin/xpidl
XPID_TARGET = sample.h sample.xpt
 
GECKO_CONFIG_INCLUDE = -include mozilla-config.h
GECKO_DEFINES  = -DXPCOM_GLUE -DMOZILLA_STRICT_API
GECKO_LDFLAGS =  -L $(GECKO_SDK_PATH)/lib -lxpcomglue -lxpcomglue_s
 
CXX=g++
INCLUDE = -I $(GECKO_SDK_PATH)/include
 
DEBUG=y
ifeq ($(DEBUG), y)
FLAGS = -g -Wall
else
FLAGS = -O2
endif
 
TMP_OBJECTS = $(foreach i,$(SOURCES),$i)
CPP_OBJECTS = $(TMP_OBJECTS:.cpp=$(OBJ))
OBJECTS = sampleModule.o  sampleextend.o
 
%.o:%.cpp
        $(CXX) -c -o $@ $(FLAGS) $(INCLUDE) $*.cpp
 
LIB_SUFFIX=.so
LIBRARY=sampleglue
LIB_FULL=lib$(LIBRARY)$(LIB_SUFFIX)
 
all: xpcomheader $(OBJECTS) $(LIB_FULL)
 
xpcomheader:
        $(XPID_BIN) -m header -I $(GECKO_SDK_PATH)/idl -o sample sample.idl
        $(XPID_BIN) -m typelib -I $(GECKO_SDK_PATH)/idl -o sample sample.idl
$(LIB_FULL):
        $(CXX) -shared -o $(LIB_FULL) $(OBJECTS)
.PHONY : clean
 
clean:xpcomclean
xpcomclean:
        -rm -rf $(XPID_TARGET)
        -rm -rf *.o
        -rm -rf *.so

The sample above simply returns "hello world" to the browser application. You can add more realistic logic or functions to support the application you want to develop. The sample makefile is a typical reference to use when building an XPCOM component. If you follow the steps described above, and use make to build the sample with makefile, you will have a sample.xpt and libsampleglue.so file. The next section explores a method to test these binaries.
Integrate and test XPCOM component

A browser like Firefox is able to use functions and services provided by XPCOM. Typically written in JavaScript, the mainframe of Web pages, you can simply implement using HTML or XML. The example uses XUL. If you try HTML, you can make various improvements. In most cases, JavaScript functions are included as a library and are keep in an individual .js file. Listing 7 shows an XUL sample.
Listing 7. Test page contents written in XUL and sample.js
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
	
============== sample.xul ============== 
<?xml version="1.0"?>
<?xml-stylesheet href="chrome://global/skin/" type="text/css"?>
 
<!DOCTYPE window>
<window id="sample" xmlns:html="http://www.w3.org/1999/xhtml"
        xmlns="http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul"
        width  = "1024"
        height = "768"
>
 
<script src="sample.js"/>
 
<hbox width="40"  height="45" style="background-color: blue;">
<button id="sample" label="press me" height="45" 
width="12" oncommand="sample_change();"/>
<description id="sample-glue">
  xpcom-sample
</description>
</hbox>
</window>
 
============== sample.js ==============
var samplegluexpcominterface=null;
 
function sample_change()
{
var res;
try
{
if(samplegluexpcominterface==null)
{
    netscape.security.PrivilegeManager.enablePrivilege("UniversalXPConnect");
    samplegluexpcominterface= Components.classes["@cn.ibm.com/XPCOM/sample;1"].
        createInstance(Components.interfaces.sample);
}
}
catch(err)
{
    alert(err);
}
  document.getElementById("sample-glue").value = samplegluexpcominterface.samplestring();
}

The sample does not do any actual work; it just calls to the XPCOM interface and returns a dummy "hello from xpcom." Note that the function is driven by an event when you press a button. Before you open the page in Firefox, be sure to follow the steps below to set up and register your XPCOM component to the browser:

    Copy sample.xpt to /usr/lib/firefox/components if your Firefox is installed in the default directory.
    Copy libsampleglue.so to /usr/lib/firefox/components.
    Make a directory called gui in /usr/lib/firefox/chrome, and copy sample.xul and sample.js to this new directory.
    Create a .manifest file and input your contents as follows: content sample gui. Copy this manifest to /usr/lib/firefox/chrome.

Now you can open an x-terminal in GUI mode and enter a command like the one shown below:
1
	
linux-d8rx#: firefox –chrome chrome://sample/gui/sample.xul

The result from the sample is shown in Figure 2.
Figure 2. Sample output in Firefox
Screen shot showing resulting sample output

You would do this mainly because the JavaScript and UI are on a single thread, so when one is busy, the other is blocked, especially when you load the XPCOM component and invoke a method exposed by it. If the duration of this method is long, the UI might appear hung with no response to the user.

Though Firefox might have a configuration setting allowing a script to run for a long time, letting the user configure the browser before executing your application is not an adequate solution. To avoid this problem, you can keep your XPCOM component fast and return to the UI. Or try to put the C++ functions into another thread. JavaScript also can provide a callback result function when invoked by the interface. See Related topics for more about this topic. 