# QW.Paginator
* 基于Jquery(>=1.7)的分页显示组件
* [戴子意 DZY](http://www.daiziyi.com/)
* Note:参考了网上的分页组件但不记得原作者，在此表示感谢，下次找到再加上对方的版权说明
* 感谢我的妻子前前，还有调皮的儿子琮琮和璋璋

# Usage
* **writing**
```javascript
$("选择器").QWPaginator({参数});
```
* **examples**
```javascript
$("#box").QWPaginator({
        totalCounts: 500,
        pageSize: 10,
        currentPage: 1,
        prev: '',
        next: '',
        page: '<li><a href="javascript:;">{{page}}</a></li>',
		pageinfo:'<span class="qw-pageinfo">第{{page}}/{{totalPages}}页 共{{totalCounts}}记录</span>',
        disableClass: 'disabled',
        activeClass: 'active',
        onPageChange: function (pageindex, type) {

        }
    });
```
	
# Property
| 名称 | 说明  | 提示 |
| ------------ | ------------ | ------------ |
| container| 容器 |  |
| options| 参数 | 见下表 |

# Parameter
| 名称 | 说明  | 默认值  | 示例  | 提示 |
| ------------ | ------------ | ------------ | ------------ | ------------ |
| first| 第一页 |  | - | 不使用请用空字符  {{page}}对应页码|
| prev| 上一页 |  | - | 不使用请用空字符  {{page}}对应页码|
| next| 下一页 |  | - | 不使用请用空字符  {{page}}对应页码|
| last| 末页 |  | - | 不使用请用空字符  {{page}}对应页码|
| page| 每页模板 |  | - | 不使用请用空字符 {{page}}对应页码|
| pageSize| 每页条数 | 10 | - | - |
| totalPages| 总页数 | 1 | - | - |
| totalCounts| 总条数 | 0 | - | - |
| currentPage| 当前页 | 1 | - | - |
| visiblePages| 可见页数量 | 7 | - | - |
| disableClass| 禁用样式 | disabled | - | - |
| activeClass| 活动样式 | page-cur | - | - |
| pageinfo| 页信息 |  | - | 模板字符说明： {{page}}当前页码 {{totalPages}}总页数 {{totalCounts}} 总计录数| 
| showInputPage| 是否显示页跳转 | true | - | 为false适用于下拉加载 |
| url| url地址 | null | - | 返回值为json |
| urlParameter| url参数 | null | - | - |
| urlMethod| 请求方式 | "get" | - | - |
| urlDataType| 获取数据方式 | "json" | - | - |
| urlPageName| 页参数名称 | "page" | - | - |
| urlPageSizeName| 页记录数参数名称 | "pagesize" | - | - |
| external| 外部参数 |  | - | 组件本身不使用此参数 |
| getDataLength| 获取数据长度 | function (d) {return d.length;} | - | 回调参数为静态数据data |
| onBeforeLoadData| 数据加载前 | null | function (o) {} | 回调参数为实例的options |
| onLoadDataed| 数据加载后 | null | function (o) {} | 回调参数为实例的options |
| onBeforeDraw| 界面绘制前事件 | null | function (t) {} | 回调参数为实例容器 |
| onDrawed| 界面绘制后事件 | null | function (t) {}  | 回调参数为实例容器 |
| onPageChange| 页跳转回调 |  | function (p, t) {} | 回调参数中t值init表示初始,change表示变换 |

# Method
* **option**
设置获取选项
```javascript
var opts=databox.QWPaginator("option", { });
```
* **redraw**
重绘分页
```javascript
databox.QWPaginator("redraw", { });
```
* **loading**
显示加载提示
```javascript
databox.QWPaginator("loading");
```
* **loaded**
隐藏加载提示
```javascript
databox.QWPaginator("loaded");
```
* **destroy**
释放实例
```javascript
databox.QWPaginator("destroy");
```
* **external**
设置获取外部参数
```javascript
var exdata=databox.QWPaginator("external");
```
