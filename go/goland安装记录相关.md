# 适用于ubuntu下安装JetBrain系列全家桶
***
+ [下载](https://www.jetbrains.com/zh-cn/go/download/other.html)
```shell
# install 
tar -zxvf xxx.version.tar.gz -C /usr/local/software/  #你自己定义的位置
# 创建图标文件
cd /usr/share/applications/

# gedit || vim 

#file content
[Desktop Entry]
Name=GoLand
Exec=sh /usr/local/software/GoLand-2021.1.3/bin/goland.sh
Terminal=false
Type=Application
Icon=/usr/local/software/GoLand-2021.1.3/bin/goland.png
Comment=GoLand
Categories=Application;
#save
# install finish
```

+ 清除使用记录
```shell
~/.config/JetBrains/<product><version>
~/.cache/JetBrains/<product><version>
~/.local/share/JetBrains/<product><version>
```

+ 重置脚本
```shell
# reset.sh

#!/bin/sh
# reset jetbrains ide evals

OS_NAME=$(uname -s)
JB_PRODUCTS="IntelliJIdea CLion PhpStorm GoLand PyCharm WebStorm Rider DataGrip RubyMine AppCode"
        echo 'Linux:'

        for PRD in $JB_PRODUCTS; do
        rm -rf ~/.${PRD}*/config/eval
        rm -rf ~/.config/${PRD}*/eval
        done

echo 'done.'



```

<https://3.jetbra.in/>

 