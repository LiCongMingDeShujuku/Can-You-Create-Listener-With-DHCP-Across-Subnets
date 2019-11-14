![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# 可以使用DHCP跨子网创建侦听器吗？
#### Can You Create Listener With DHCP Across Subnets？
**发布-日期: 2015年03月19日 (评论)P**

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
答案是不能。你将遇到此错误：
```
承载主副本和辅助副本的WSFC节点属于不同的子网。
可用性副本不支持跨多个子网的DHCP。
可以使用静态IP配置可用性组侦听器。
```

## English
The short answer is ‘No’. You will run into this error:

```The WSFC nodes that host the primary and secondary replicas belong to different subnets. 
DHCP across multiple subnets is not supported for availability replicas. 
Use the static IP option to configure the availability group listener.
```

---
## Logic
```SQL
use master;
set nocount on 

alter availability group [SQLAG1]
add
	listener 'sqlag1_listener' 
		(with dhcp on ('10.101.117.0', '255.255.255.0')， port=1433);
		
go
```

![#](images/Create-Listener-With-DHCP-Across-Subnets.png?raw=true "#")


[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

