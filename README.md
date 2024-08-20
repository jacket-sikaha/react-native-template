# react-native 环境搭建踩坑注意点

1. rn 运行所需要的 Android studio，貌似只认安装时候的默认路径，不按默认路径的话 npx react-native doctor 执行后 AS 那行会爆红
2. AS 环境变量有三个缺一不可，sdk，emulator，platform-tools（adb）
3. 要用 yarn 下载的依赖来启动，pnpm 的启动项目时会有问题
4. 用到 react-native-screens，记得按照官方文档修改 MainActivity.kt，如果漏掉 import android.os.Bundle;项目启动会报错
