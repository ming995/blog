# 页面性能优化以及代码质量提升手段
#性能优化

## 指标参数
PV(访问量)：页面的浏览量或者点击量，页面每次刷新就被计算一次。
UV(独立访客)：一般使用cookie标记，访问您网站的一台电脑客户端(比如一台电脑开多个浏览器访问则为多个UV)为一个访客，00:00-24:00内相同的客户端只会被计算一次。
SPM(超级位置模型)，阿里的spm由：
	* A点：站点/业务
	* B点：页面
	* C点：页面区块
	* D点：区块内点位

## 技术
* PWA
* Lighthouse
* SSR
* NSR：客户端提前请求数据组装HTML渲染方式
* Rehydration：复用服务端渲染生成的DOM结构以及数据，并执行事件绑定来启动页面的过程

## RAIL模型
* 100ms响应用户输入
* 每帧动画在16ms内完成
* 最大化空闲时间
* 3G等设备5s内可交互

## 用户指标
* FCP：首次内容绘制时间
* LCP：最大内容绘制时间
* FID：首次输入延迟
* TTI：页面可交互时间
* TBT：主线程累计阻塞时间
* CLS：累计布局偏移

## 如何做优化
### 目的
* 加载速度
* 响应能力
* 动画流畅度
* 能耗
* 内存占用
* ……
### 常用手段
* 缓存
* 预加载
* 渲染 
