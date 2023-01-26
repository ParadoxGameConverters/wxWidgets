# wxWidgets, Version 3.1.5

Windows headers, libs and DLLs sourced from:
https://www.wxwidgets.org/downloads/

* You need to include wxwidgets.props as a new property sheet in VS (View->Other Windows->Property Manager)
* In C++ section, add additional include directory: $(ProjectDir)\wxWidgets\3.2.1\include\msvc
* In Linker general, add additional library directory: $(ProjectDir)\wxWidgets\3.2.1\lib\vc14x_x64_dll
* Add wxbase32ud_vc14x_x64.dll and wxmsw32ud_core_vc14x_x64.dll to the project and set the to "Copy file" into output directory.
* In .h files, usually you need:
```
#pragma once
#include <wx/wxprec.h>
#ifndef WX_PRECOMP
#include <wx/wx.h>
#endif
```

For linux headers and libraries, install them locally:
```
sudo apt-key adv --fetch-keys https://repos.codelite.org/CodeLite.asc
sudo apt-add-repository 'deb https://repos.codelite.org/wx3.2/ubuntu/ jammy universe'
sudo apt-get update
apt-get install libwxbase3.2-0-unofficial \
                libwxbase3.2unofficial-dev \
                libwxgtk3.2-0-unofficial \
                libwxgtk3.2unofficial-dev \
                wx3.2-headers \
                wx-common 
```
