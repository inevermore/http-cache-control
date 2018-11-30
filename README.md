## HTTP cache control
### 强缓存和协商缓存
发起请求前，根据请求头的expires、cache-control判断如果命中强缓存不会发送请求，直接从缓存获取资源；

如果没有命中强缓存，会向服务端发起请求，根据etag、last-modified判断如果命中协商缓存，返回正文是空，从缓存中获取资源；

如果没有命中协商缓存，则从服务端获取资源。
#### 强缓存

* expires：http1.0,返回秒级的绝对时间，由于存在浏览器和服务端时间可能出现较大误差http1.1提出了cache-control

* cache-control：相对时间，http1.1
优先级： cache-control > expires
