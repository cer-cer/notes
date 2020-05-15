### Pod 命令在project 中的使用

#### Pod 的例子

``` git
platform :ios, '9.0'
inhibit_all_warnings!

target 'MyApp' do
  pod 'ObjectiveSugar', '~> 0.5'

  target 'MyAppTests' do
    inherit! :search_paths
    pod 'OCMock', '~> 2.0.1'
  end
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    puts "#{target.name}"
  end
end
workspace 'workspaceName.workspace'
```

#### 常用命令介绍

1. 定义依赖库 spec 所在的仓库 。

   source 命令可以全局指定依赖库的仓库地址，也可以分别指定依赖库的仓库地址。

   - 全局

   ```
    source 'https://github.com/CocoaPods/Specs.git'
   ```

   - 分别指定

   ```git
   pod 'PonyDebugger', :source => 'https://github.com/CocoaPods/Specs.git'
   ```

2. 定义 workspace

   ``` git
   workspace 'MyWorkspace'
   ```

   如果没有指定同时只有一个项目，则和项目同名。

3. 指定target

   target是pod中的重要单元；对应于project中的target。如果pod项目只有一个project，则默认为该项目添加project。如果有多个，需要用project指令指定要加的项目。target 可以嵌套。

   ```
   target 'name' do
   end
   ```

   1. platform 指定target 依赖的平台

   ``` 
   platform :ios, '4.0'
   ```

   2. project 指定 target 存在的项目

   ```
   project 'projectName'
   ```

   3. user_framework! 指定依赖库形式（动态，静态)

   ```
   use_frameworks! :linkage => :dynamic
   ```

   4. pod 依赖

   依赖是pod的库的核心功能。它有负责的参数配置

   - 依赖库名称, 且可选指定版本号。

   ``` 
   pod 'Objection', '0.9'
   ```

   - 依赖本地库

   ``` 
   pod 'AFNetworking', :path => '~/Documents/AFNetworking'
   ```

   - 依赖远程库，指定其git仓库。可选参数分支、tag、commit

   ``` 
   pod 'AFNetworking', :git => 'https://github.com/gowalla/AFNetworking.git'
   pod 'AFNetworking', :git => 'https://github.com/gowalla/AFNetworking.git', :branch => 'dev'
   pod 'AFNetworking', :git => 'https://github.com/gowalla/AFNetworking.git', :tag => '0.7.0'
   pod 'AFNetworking', :git => 'https://github.com/gowalla/AFNetworking.git', :commit => '082f8319af'
   ```

   - 其他依赖参数，参见 [^ 1]



参考文档

 [^ 1 ] [pod 语法](https://guides.cocoapods.org/syntax/podfile.html#podfile)