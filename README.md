# SwiftFramework


## 这个工程主要是教怎么在swift的工程中使用objective-c或者c语言的framework

Swift项目中引用Objective-C的framework：

1. 项目中加入该framework；

2. 在framework所在目录下，建立module.modulemap文件，其内容是：


<pre><code> 
module ObjcFramework {

    header "ObjcFramework.framework/Headers/XXX.h"
    
    export *
    
}
</pre></code>

ObjcFramework: objective-c framework的名字


3. 工程中加入xcconfig文件，其内容是：

<pre><code>
SWIFT_INCLUDE_PATHS = $(SRCROOT)/Framework
MODULEMAP_PRIVATE_FILE = $(SRCROOT)/Framework/module.modulemap
</pre></code>
