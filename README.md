# 跨域分析

### 产生跨域的原因
```
1. 浏览器限制
2. 不同协议域名端口
3. 请求类型是XHR（XMLHttpRequest）
```

### 解决跨域的几种方式
1. 通过命令关闭浏览器限制
2. 前端通过动态创建 \<script\> 标签来做请求,也就是jsonp的方式。需要后台配合约定callback参数通过返回一段js函数，函数名就是callback对应的值（如：src="xxx?callback=fun1"）
3. 后台解决（通过增加响应头"Access-Control-Allow-Origin", "http://localhost:8080"
"Access-Control-Allow-Methods", "GET"）
- 服务器端反向代理实现
- nginx配置
- apache配置
- nodejs

### jsonp的弊端
```
1. 服务器端需要改变代码
2. 只支持get请求
3. 发送的不是XHR请求
```

### 简单请求和非简单请求
#### 常见的简单请求:
- 方法为：
1. GET
2. HEAD
3. POST
- 请求header里面
1. 无自定义头信息
2. Content-Type为以下几种：  
text/plain  
multipart/form-data  
application/x-www-form-urlencoded
#### 常见的非简单请求:
1. put
2. delete
3. 发送json格式的ajax请求
4. 带自定义头的ajax请求
