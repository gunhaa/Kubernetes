FROM node:latest

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

# 해당 볼륨은 익명 볼륨이다
# 익명 볼륨은 컨테이너가 종료되면 사라진다
# VOLUME ["/app/feedback"]
# Named Volume은 컨테이너가 종료되도 
# 영구적이거나 편집, 직접 볼 필요가 없는 데이터
# 호스트 머신 폴더에서 접근 할 필요가 없을 때
# 생성할때 named 볼륨을 넣어야한다
# docker build -t feedback-node:volumes .
# docker run -d -p 3000:80 --rm --name feedback-app -v feedback:/app/feedback feedback-node:volumes
# 해당 명령은 호스트 머신 어딘가에 컨테이너의 /app/feedback의 세부사항을 저장한다. feedback: 을 붙여야 도커가 이해할 수 있는 구문이 된다
# 컨테이너가 삭제되어도 삭제되지 않는다. 컨테이너가 생성될때마다 익명 볼륨이 생성되기 때문에 익명 볼륨일 경우 종료될때 삭제된다.
# volume을 동일한 옵션을 사용하면, 이전의 설정을 불러올 수 있다
# docker volume prune 으로 익명 볼륨을 제거 할 수 있다
# WSL2에서 해당 방법으로 마운트 시킬 수 있다

# window wsl2 환경에서는 반드시 다음에서 지시하는 것을 해야 해당 방식으로 마운트 시킬 수 있다
# https://nickjanetakis.com/blog/setting-up-docker-for-windows-and-wsl-to-work-flawlessly#ensure-volume-mounts-work
# docker run -d -p 3000:80 --name feedback-app -v "feedback:/app/feedback" -v "/app/node_modules" -v "/c/workspace/git/Kubernetes/data-volumes-01-starting-setup:/app" feedback-node:volumes
# docker container에 넣을 때 원래 폴더의 node_modules를 유지시키는 방법은 -v 익명 볼륨 이용하는 것이다
# -v 볼륨 사용은, 있는 폴더를 사용해서 매핑시킨다는 뜻으로 생각하면 될 것 같다
# CMD ["node", "server.js"]

# nodemon 사용
# 윈도우에서 WSL2를 사용하는 경우, 리눅스 파일시스템에 파일이 따로 저장되는 것이기 때문에 nodemon을 사용할 수 없다.
# 아래 링크를 통해 설정을 추가로 해줘야 사용할 수 있다.
CMD ["npm", "start"]

