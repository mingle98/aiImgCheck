# 一、AI图片鉴黄检测合规
人工智能鉴黄是通过深度学习目标检测、图像分类、特征检索等技术对图像中的局部和全局信息进行分析，捕获不同类型的色情内容，此外系统还会通过OCR、标志识别、水印检测等技术手段协助判断隐藏在图像视频中的敏感内容，包括色情微信推广、色情APP、个人联系方式等。

# 二、使用步骤
## 1、接口

***重要提示:建议使用https协议,当https协议无法使用时再尝试使用http协议***

请求方式: POST

```
https://luckycola.com.cn/tools/checkImg
```
## 2、请求参数

**重要提醒**⚠️:该接口请求参数是**multipart/form-data**格式⚠️

| 序号 | 参数 | 是否必须|说明 |
|--|--|--|--|
| 1 |ColaKey  |是 | 唯一验证ColaKey, 可前往官网获取([http(s): //luckycola.com.cn](http://luckycola.com.cn))|
| 2 |file  |是 | 需要鉴别的图片资源(png、jpg、jpeg、png格式),注意:该接口请求参数是**multipart/form-data**格式|





**注意!!!: 如果您还没有ColaKey,请先请前往官网个人中心获取**
官网地址:[http(s): //luckycola.com.cn/](http://luckycola.com.cn/)


## 3、请求参数示例


**重要提醒**⚠️:该接口请求参数是**multipart/form-data**格式⚠️


![在这里插入图片描述](https://img-blog.csdnimg.cn/84000360bb0d444b82139777e53ef557.png#pic_center)

## 4、接口 返回示例
```json
{
	// 接口返回成功
	"code": 0,
	// 检测结果提示
	"msg": "图片合规",
	"data": {
		// 图片是否是合规的
		"isSafe": true,
		// 图片的类型特征
		"imgType": "中性的",
		// 图片的检测出的一些特征
		"predictions": [
			{
				// 图片的“中性“程度
				"className": "Neutral",
				"probability": 0.9218649864196777
			},
			{
				// 图片的“艺术性“程度
				"className": "Drawing",
				"probability": 0.02236325852572918
			},
			{
				// 图片的“性感“程度
				"className": "Sexy",
				"probability": 0.02040712907910347
			},
			{	
				// 图片的“变态“程度
				"className": "Hentai",
				"probability": 0.018754659220576286
			},
			{
				// 图片的“色情“程度
				"className": "Porn",
				"probability": 0.016609955579042435
			}
		]
	}
}
```

# 三、 报错说明
## 1、返回以下报错说明你没有正确传入检测是图片的参数(file参数),	且请求参数是**multipart/form-data**格式⚠️

![在这里插入图片描述](https://img-blog.csdnimg.cn/118fef49adc84560a9e76dec31e2380f.png#pic_center)



