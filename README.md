# helm chart 관리 방법

## 폴더 구성 원칙
- /charts 폴더 밑에 helm chart 폴더(python-backend)를 생성한다.
- /charts/python-backend/ 폴더 밑으로 버전(1.0.0) 폴더를 생성한다.
- /charts/python-backend/1.0.0/ 폴더 밑으로 chart source 를 구성한다.
- chart version 은 Chart.yaml 파일에 명시되어 있다.

## chart 테스트
- chart source 테스트는 아래 명령어를 사용한다.
- temp.yaml 내용을 확인하면서 source 를 테스트 한다.
```
cd ./charts/python-backend/1.0.0
helm template python-backend . > temp.yaml
```

## chart package & dist
- chart source 를 package 해서 저장한다.
```
cd ./charts/python-backend/1.0.0
helm package . --destination ../../../charts
```

## chart index update
- helm chart index.yaml 파일을 업데이트 해준다.
```
helm repo index ../../../charts
```

.끝.