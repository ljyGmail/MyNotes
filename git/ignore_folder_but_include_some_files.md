# 忽略某个文件夹，但排除其中的某些文件时需要注意的点

- 此处文件夹后面必须加\*，否则达不到预期效果

```bash
some_folder/*
!some_folder/abc
```
