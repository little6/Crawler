技术选择;
	httpclient 模拟http请求
	Jsoup进行解析html
	MySQL存入数据库,采用Mybatis

2016-8-3
	httpcore   是一套http协议实现包.实现了一系列的底层传输的功能,这些底层功能，可以用来去建立自己的client和server
	httpclient 是基于httpcore的一套客户端,httpclient是在httpcore上进行开发的,于是先看httpcore。 

2016-8-5
	为了方便排错，把已爬取的uri和图片uri保存在本地

2016-8-6
	之前经常在下载图片的接口里面跑出异常，说连接超时，后来把下载图片的缓冲区由1*1024*1024改成10*1024就好了，
	可能是每次从流中取出数据太大，时间不够.


一些思考：
	考虑怎么解析ajax请求中的链接
	<a/>标签的 href可以是相对路径，最好指定baseUri
	<img/>标签的 src一般是全路径
	图片爬尤果网  ugirl.com

	单线程爬
	多线程爬
	集群爬

	存储：将网页直接存入数据库，然后爬的时候就用jsoup做解析，将解析后的有用数据存储在数据库

	网址去重：目前只用Set集合来处理uri去重