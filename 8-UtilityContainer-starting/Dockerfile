# 경량 버전
FROM node:14-alpine

WORKDIR /app

# docker run  작성했던 설정들이 모두 들어가며, 끝에 엔트리 포인트가 들어간다
# CMD의 경우 작성했던 설정이 모두 날라가고, CMD값만 들어간다
ENTRYPOINT [ "npm" ]

# docker run -it -v /mnt/C/workspace/git/Kubernetes/8-UtilityContainer-starting/Dockerfile:/app mynpm init 로 실행가능
# docker run -it -v /mnt/C/workspace/git/Kubernetes/8-UtilityContainer-starting/Dockerfile:/app mynpm install express --save 로 응용가능