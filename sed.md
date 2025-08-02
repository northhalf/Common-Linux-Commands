# `sed`流式编辑和转化文本

[//]: # (UTF-8)

语法：

```shell
sed [-V] [--version] [--help] [-n] [--quiet] [--silent]
    [-l N] [--line-length=N] [-u] [--unbuffered]
    [-E] [-r] [--regexp-extended]
    [-e script] [--expression=script]
    [-f script-file] [--file=script-file]
    [script-if-no-other-script]
    [file...]
```

## 1. 命令选项

| 选项                                            | 作用                                |
|-----------------------------------------------|-----------------------------------|
| `-n`, `--quiet`, `--silent`                   | 不再自动打印匹配行                         |
| `-e` script, `--expression=`<u>script</u>     | 添加脚本给 sed                         |
| `-f` script-file, `--file=`<u>script-file</u> | 添加脚本文件的内容给 sed 执行                 |
| `-l` N, `--line-length=`<u>N</u>              | 指定每行最大长度(超过N个字符的行会自动换行)           |
| `-E`, `-r`, `--regexp-extended`               | 使用正则表达式扩展模式                       |
| `-s`, `--separate`                            | 将文件视为单独的文件，而不合并为一个输入流(行数每个文件单独计数) |
| `-u`, `--unbuffered`                          | 每行立即输出，而不是输出到缓冲区中                 |

## 2. 作用于单行

| 命令              | 作用                                       |
|-----------------|------------------------------------------|
| `i` <u>text</u> | 在匹配到的行的行之前插入文本，并且会自动插入换行符(看起来就像是之前插入了一行) |
| `a` <u>text</u> | 在匹配到的行的行之后插入文本，并且会自动插入换行符(看起来就像是之后插入了一行) |

## 3. 作用于多行

| 命令                     | 作用                       |
|------------------------|--------------------------|
| `c` <u>text</u>        | 用指定文本替换匹配到的行，自动添加换行符     |
| `p`                    | 打印模式空间内容，可以与 `-n` 选项一起使用 |
| `s/regexp/replacement` | 用replacement替换匹配内容       |
