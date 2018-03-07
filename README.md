# MultipleProcess

本工程为[《Android多进程使用场景》](http://blog.spinytech.com/2016/11/17/android_multiple_process_usage_scenario/)的源码工程。

- 测试【打开状态】、【按了Home键被切换状态】、【按了Back键被退出状态】的adj
- A. 在Activity中直接播放音乐。
    - p1:adj->0->7->9
- B. 启动后台Service，播放音乐。
    - p1:adj->0->7->9
- C. 启动前台Service，播放音乐。
    - p1:adj->0->2->2
- D. 在新的进程中，启动后台Service，播放音乐。
    - p1:adj->0->7->9
    - p2:adj->5->5->5
- E. 在新的进程中，启动前台Service，播放音乐。
    - p1:adj->0->7->9
    - p2:adj->2->2->2
    - 像C方案，非常小，非常稳定，而且，我们还可以在系统进入后台后，手动杀掉主进程，使整个应用的内存消耗降到最低，内存低，优先级又高，E获得了今天的最稳定的方案奖。

