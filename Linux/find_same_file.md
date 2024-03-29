# 寻找相同文件的相关命令

* 寻找内容相同的文件
```bash
find . -type f -iname "*python*.pdf" -print0 | xargs -0 md5 -r | awk '{ print substr($0, 1, 32) "@@@" substr($0, 34)}' | awk -F"@@@" '{ counts[$1]+=1; names[$1]=$2 " ##### " names[$1]} END { for(key in counts) { print counts[key] " " key ": " names[key]} }' | grep -v '1 ' | sort -nr
```

* 下面的命令问题在于执行ls -lh时文件的顺序会发生变化
```bash
find . -type f -iname "*python*.pdf" -print0 | xargs -0 ls -lh | awk '{ print $5 }'
```

* 使用这种方式才可以不影响find命令结果的顺序
```bash
find . -type f -iname "*python*.pdf" -print | sed -e 's/^/ls -lh "/'  -e 's/$/"/' | bash 
```

* checksum 文件名 文件大小
```bash
paste <(find . -type f -iname "*python*.pdf" -print0 | xargs -0 md5 -r) <(find . -type f -iname "*python*.pdf" -print | sed -e 's/^/ls -lh "/'  -e 's/$/"/' | bash | awk '{ print $5 }')
```