# TongueDiagnosis

## 														中医智能舌诊——舌诊宝



### 一、项目概述

​	项目的主要功能是利用深度学习算法对用户上传的舌象图片进行分析，对舌象的舌色、舌苔色、薄厚、腻否进行四维分类。项目采用多模型拼接进行各类任务的专项训练。这种方法使得不同的舌象处理任务在不同的模型进行处理，然后将它们拼接起来形成完整的舌象分析链条。该多模型采用了yolov5目标检测模型、Segment Anything模型进行舌象的分割对用户上传的舌象图片进行预处理，使用ResNet50残差神经网络对剩余的完整舌象进行分类任务。

​	项目的多模型部署于Web应用的后端，用户可以便捷的使用浏览器在各类系统上进行舌象的上传以及获得舌象分析的结果。应用操作简单，使用便捷。

#### 二、应用功能：

	舌象上传与诊断：舌象诊断功能属于平台的核心业务，实现了舌象的上传、诊断并且生成健康报告和建议。在舌象上传环节，用户可以通过自己的设备进行舌象的上传，平台将会对用户上传的舌象进行诊断并生成属于用户的健康报告。生成的健康报告会及时显示给用户，同时平台将会储存用户的健康报告，供用户以后进行查看。
	
 	诊断记录查看：诊断记录查看为用户提供了健康报告的查询服务，包括健康报告记录列表显示，以及对应记录查询。用户还可以通过日期等进行过去健康报告的查询，同时，健康报告将按照时间进行降序排序，方便用户查询到自己最近的健康诊断报告。

#### 三、源码文件架构：

```
TongueDiagnosis{
	application (后端) {
		config (后端配置)
		core (核心算法)
		models (数据库模型)
		net (神经网络模型)
		orm (数据库映射模型)
		routes (路由)
		init.py (后端初始化)
	}
	frontend (前端) {
		cypress (调试文件)
		public (静态文件)
		src (源代码) {
			assets (资产)
			components (组件)
			router (路由)
			views (视图)
			App.vue (Vue应用根组件)
			main.js (Vue应用入口)
		}
		index.html (网站入口)
		package.json (所有包管理配置)
		vite.config.js (脚手架配置，打包代理跨域配置)
	}
	.gitignore (git忽略)
	run.py (整体应用入口)
}
```

   

​	
