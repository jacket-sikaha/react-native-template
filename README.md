# react-native 环境搭建踩坑注意点

1. rn 运行所需要的 Android studio，貌似只认安装时候的`默认路径`，不按默认路径的话 npx react-native doctor 执行后 AS 那行会爆红
2. AS 环境变量有三个缺一不可，`sdk，emulator，platform-tools（adb）`
3. 要用 yarn 下载的依赖来启动，pnpm 的启动项目时会有问题
4. 魔法上网原因有：比较难下的包`gradle-x.x-all.zip`，`react-android-0.xx.x-debug.aar`,还有就是 maven 的相关依赖。提供一个骚办法就是：可以用某个镜像网站 url 替换 build.gradle 的`distributionUrl`，接着增加 maven 镜像源(参考下方)
5. 用到 `react-native-screens`，记得按照官方文档修改 `MainActivity.kt`，如果漏掉 `import android.os.Bundle;`项目启动会报错
6. `gradle 8.6` 版本貌似有问题一直报`Could not move temporary workspace`问题 ,更换一下版本即可。其他问题见[链接](https://blog.csdn.net/qq_44184452/article/details/139762839)

```gradle

 repositories {
       google()
         maven {
      url 'https://maven.aliyun.com/repository/public/'
    }
    maven {
      url 'https://maven.aliyun.com/repository/central'
    }
    mavenLocal()
    mavenCentral()

    }
```
