# `tar`归档命令

[//]: # (UTF-8)

[TOC]

## 1. 打包文件

|参数|功能|
|--|--|
|`-c, --create`|创建新归档文件（打包）|
|`-f, --file`|指定归档文件名（压缩包名称）|
|`-v, --verbose`|显示命令执行过程（一般用于解压）|

打包一个压缩文件:

```shell
tar -cf newTar.tar dir/
```

这将`dir`目录归档到`newTar.tar`文件中。

> 这里末尾也可添加多个目录或文件，会被一并打包
> **注意**：如果采用类似`./dir/`形式的话，那么`.`会在压缩文件中形成一个目录

## 2. 压缩文件

就是在打包的基础上增加压缩选项:

|参数|功能|
|--|--|
|`-z, --gzip, --gunzip, --ungzip`|使用`gzip`压缩（压缩文件后缀为`.tar.gz`或`.tgz`）|
|`-j, --bzip2`|使用`bzip2`压缩（压缩文件后缀为`.tar.bz2`或`.tbz2`）|

这里对文件进行压缩：

```shell
tar -czf newTar.tar.gz ./dir
```

## 3. 解包文件

需要解压选项：

|参数|功能|
|--|--|
|`-x, --extract, --get`|解压归档文件|
|`-v, --verbose`|显示详细输出|

例如这样解包：

```shell
tar -xvf document.tar
```

对于压缩文件需要加上对应的压缩参数，像是`.tar.gz`格式的压缩文件需要加上相应的`-z`参数。像是：

```shell
tar -xzvf document.tar.gz
```

## 4. 不解压的情况下查看压缩文件内容

使用列出文件选项

|参数|功能|
|--|--|
|`-t, --list`|列出压缩文件内容|

例如这样：

```shell
tar -tf document.tar
```
