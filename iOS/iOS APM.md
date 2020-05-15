### Performace Monitor

- fps监控

  ```swift
  CADisplayLink
  Add Obersver to monitor the screen refresh.
  ```

  

- 网络监控（流量，http/https调用应答时长和包大小）

  - 网络接口失败监控

- 线程耗时(main thread)

```
 Add Runloop Observer to monitor the before source and after wake task.
```

- 内存

- CPU

  ```text
  内存和CPU只能获取当前app的占有数量
  ```

  

- 启动时长(静态监控)

  通过设置xcode启动项参数，让xcode打印app启动的市场。

  - DYLD_PRINT_STATISTICS_DETAILS

  - DYLD_PRINT_STATISTICS

- viewcontroller 显示时长

   statics the time between viewWillApear and viewDidApear

- I/O 文件读写监控

---

### 用户行为分析

- app 保活时长
- page 保活时长
- 页面/事件埋点



参考文档

- https://svitla.com/blog/mobile-application-performance-monitoring-tools-for-ios

- https://programmer.group/how-to-accurately-measure-ios-app-startup-time.html

- https://medium.com/@michael.eisel/measuring-your-ios-apps-pre-main-time-in-the-wild-98197f3d95b4