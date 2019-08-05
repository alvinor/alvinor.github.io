# 创建一个公共资源类


----
----

## STEP ONE

---

### 1  在 [huweigroup](https://git.qxeden.com/huweigroup) 建立一个仓库 `myproject`

### 2  clone 到本地 http://git.qxeden.com/huweigroup/myproject.git
    
```shell
$ git clone http://git.qxeden.com/huweigroup/myproject.git
```

### 3  分支管理

#### 进入到目录 

```shell
$ cd myproject
```
   
  ####  创建开发分支

```shell
$ git branch develop
```
   
  #### 创建个人分支
   
```shell
$ git branch feature/alvinor
```
   
  #### 提交`dev`到远程分支
   
```shell
$ git checkout develop 
$ git push origin develop
```
   
#### 提交` feature/alvinor` 到远程分支

```shell
$ git checkout feature/alvinor
$ git push origin feature/alvinor
```
   

### 4  创建 composer.json 文件

  #### 进入到分支 
   
```shell
$ git checkout feature/alvinor
```

   
  ####  composer init 交互式生成
   
  ####  composer init  快速生成
      
```shell
$ composer      init [--name NAME] [--description DESCRIPTION] [--author AUTHOR] [--type [TYPE]] [--homepage HOMEPAGE] [--require REQUIRE] [--require-dev REQUIRE-DEV] [-s|--stability STABILITY] [-l|--license LICENSE] [--repository REPOSITORY]
```
      
   ####  复制 composer
   
```javascript
{
"name": "huweigroup/myporject",
"description": "这个是测试描述",
"homepage": "https://git.qxeden.com/huweigroup/common/wikis/home",
"license": "proprietary",
"authors": [
	{
		"name": "杜鑫",
		"email": "alvinor@qxeden.com",
		"role": "mantainer"
	},
	{
		"name": "刘德华",
		"email": "刘德华@qxeden.com",
		"role": "owner",
	}
],
"support": {
	"email": "huweigroup@qxeden.com",
	"issues": "http://doc.qxeden.com/",
	"irc": "qq:546624681",
	"forum": "http://doc.qxeden.com/pages/viewpage.action?pageId=12854712",
	"wiki": "https://git.qxeden.com/huweigroup/common/wikis/home",
	"source": "https://git.qxeden.com/huweigroup/common"
},
"require": {
	"php": ">=7.1.3"
},
"require-dev": {
	"phpunit/phpunit": "^7.0"
},
"autoload": {
	"classmap": [
		"other/"
	],
	"files": [
		"src/helpers.php"
	],
	"psr-4": {
		"huweigroup\\myproject": "src"
	}
},
"autoload-dev": {
	"classmap": [
		"tests/"
	]
},
"keywords": [
	"测试",
	"test"
],
"scripts": {
	"post-root-package-install": "@php -r \"echo '发个http请求给服务器';\""
},
"config": {
	"preferred-install": "dist",
	"sort-pkgs": true,
	"optimize-autoloader": true,
	"secure-http": false
},
"repositories": {
	"packagist": {
		"type": "composer",
		"url": "http://pkgs.qxeden.com"
	}
},
"minimum-stability": "stable",
"prefer-stable": true
}

```
   
   > 参考[composer.schema](composer.schema.md) 修改指定参数
   
 ### 5 根据 autoload 创建相应目录
    
    本例如下
    
```shell
$ mkdir other;
$ mkdir test;
$ mkdir src;

```

### 6 在src 中 创建脚本 `Test.php`

    $ vim Test.php
```php
    <?php 
namespace Jrcomposer\Common;

class Test{
    public function dt(){
        return date("Y-m-d H:i:s");
    }
}
```

### 7  提交到远程仓库

```shell
$ git add  ./
$ git commit -m "initial myproject"
$ git push origin feature/alvinor

$ git checkout dev
$ git merge feature/alvinor
$ git push origin dev
```

----

-----

## STEP TOW

-----
   
## 在项目中进行测试

### 1 修改项目composer.json 添加type为vcs的镜像

示例：

```shell
 "config": {
                "preferred-install": "dist",
                "sort-pkgs": true,
                "optimize-autoloader": true,
                "secure-http": false
        },
        "repositories": [
                {
                        "type": "composer",
                        "url": "http://pkgs.qxeden.com"
                },
                {
                        "type": "vcs",
                        "url": "https://git.qxeden.com/huweigroup/myproject"
                }
        ],
```        

### 2 加载依赖包


```shell
$ composer require huweigroup/myproject  dev-develop
```
_`dev-develop`中`develop`为git仓库中的分支_

### 3 在代码中直接引用使用

```php
return (new Jrcomposer\Myproject\Test())->dt()
```
------

-----

## STEP 3

-----

## 正式发包

### 1 dev 分支打包

```shell
$ git checkout dev
$ git tag v0.0.1
$ git push -tag
```

### 2  提交master 合并申请

### 3 master审查合并

### 4 通知运维正式发包

   
   
     
