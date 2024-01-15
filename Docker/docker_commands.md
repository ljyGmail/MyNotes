# 도커에서 자주 쓰는 명령

## 도커 컨테이너, 이미지 정리
* 실행중인 컨테이너 중지
```docker
docker stop $(docker ps | awk 'NR>1 {print $1, $2}' | grep -v 'datasciencetoolbox/dsatcl2e' | awk '{print $1}')
```

* 모든 컨테이너 삭제
```docker
docker rm $(docker ps -a | awk 'NR>1 {print $1, $2}' | grep -v 'datasciencetoolbox/dsatcl2e' | awk '{print $1}')
```

* 모든 이미지 삭제
```docker
docker rmi -f $(docker images | awk 'NR>1 {print $1, $3}' | grep -v 'datasciencetoolbox/dsatcl2e' | awk '{print $2}')
```

## Learn Docker in a Month of Lunches
* clean up commands for containers and images
```docker
docker container -rm -f $(docker container ls -a | awk 'NR > 1 { print $1, $2 }' | grep -v 'datasciencetoolbox/dsatcl2e' | awk '{ print $1 }')
```

```docker
docker image rm -f $(docker image ls -f reference='diamol/*' -q)
```