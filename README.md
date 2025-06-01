# AI_learn_iOS
用AI学习iOS开发

## iOS Hybrid H5离线优化
网页加载过程
webview初始化 -> 打开url -> DNS解析 -> html加载 -> css/js加载 -> js加载数据 -> dom渲染
![Uploading image.png…]()

优化思路
1. 降低请求量：合并资源，减少 HTTP 请求数，minify / gzip 压缩，webP，lazyLoad。
2. 加快请求速度：预解析DNS，减少域名数，并行加载，CDN 分发。
3. 缓存：HTTP 协议缓存请求，离线缓存 manifest，离线数据缓存 localStorage。
4. 渲染：JS/CSS优化，加载顺序，服务端渲染模板直出。
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
2. 测试网页https://claude.ai/public/artifacts/ba221f61-308c-4352-9307-7c7537fb9bfe
   
