# AI_learn_iOS
用AI学习iOS开发

## iOS Hybrid H5离线优化
网页加载过程
webview初始化 -> 打开url -> DNS解析 -> html加载 -> css/js加载 -> js加载数据 -> dom渲染
1. webview的性能测试基于performance.timing的
```
                dnsLookup: timing.domainLookupEnd - timing.domainLookupStart,
                tcpConnect: timing.connectEnd - timing.connectStart,
                request: timing.responseStart - timing.requestStart,
                response: timing.responseEnd - timing.responseStart,
                domProcessing: timing.domComplete - timing.domLoading,
                domReady: timing.domContentLoadedEventEnd - navigationStart,
                loadComplete: timing.loadEventEnd - navigationStart,
                totalTime: timing.loadEventEnd - navigationStart
```
