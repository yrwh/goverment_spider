#  介绍

政策爬虫系统，每日定时（凌晨1点）抓取指定网站的政策内容。(注意这里默认抓取的是**昨天**的，今天的需要明天凌晨抓取)



# 目录结构

```csharp
├─codes
│  ├─xx.py					    # 国家、省、市、区的网站爬取代码，后续新增可按相同格式往后添加即可（不用重新启动定时任务）
├─files							# 存放每个网站爬取的内容
│  ├─xxxx年xx月
│  │  ├─国家级/省级/市级/南山区
├─logs/							# 爬取日志，定时任务pid
├─xls_files						# 将每天的所有爬取内容汇总到一张表
│  ├─xxxx年xx月	
├─key_words.txt					# 需要抓取的关键词文件
├─logger.py						# 日志代码
├─start_project.py				# 程序入口
├─start.sh						# 定时任务启动文件
├─stop.sh						# 定时任务关闭文件
└─utils.py						# utils文件
```



# 定时任务启动与结束

**启动：**

> sh start.sh

**停止**：

> sh stop.sh

**拉取excel文件地址**：

> ip:9091



# 其他运行方式

## 单独爬取某个政府网站

> python 101.国家工信部.py

## 运行从指定日期到昨天

> python start_project.py --start_date 2024-01-01

## 单独运行指定日期

> python start_project.py --start_date 2024-02-03 --only_start_date

