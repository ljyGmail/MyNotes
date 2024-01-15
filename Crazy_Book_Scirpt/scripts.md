# 대량으로  이미지 파일명 바꾸기
챕터별로 이미지 스캔 후 폴더에 저장 후, 각 풀더에서 다음 명령을 실행하면, 자동으로 순번이 매긴 파일명이 됨: 

```bash
paste 
	<(ls) # 현재 폴더내 파일명
	<(seq -w 01 $(ls | wc -l) | sed -e "s@^@$(pwd | awk -F/ '{ print $NF }' | cut -d_ -f1)\_@" -e 's/$/.png/') # 전환될 파일명 생성
| sed 's/^/mv /' # mv명령 생성
| bash # mv명령 실행

```

* 주석 없는 버전:
```bash
paste <(ls) <(seq -w 01 $(ls | wc -l) | sed -e "s@^@$(pwd | awk -F/ '{ print $NF }' | cut -d_ -f1)\_@" -e 's/$/.jpg/') | sed 's/^/mv /' | bash
```

## 링크 생성 명령:
```bash
seq -w 01 32 | sed -e 's@^@<img src="ch05_oop_1/ch05_@' -e 's@$@.jpg">@'
```

```docker
docker run --name my-nginx -v C:/Users/liang/Desktop/Playground/crazy_java_6ed:/usr/share/nginx/html -d nginx
```