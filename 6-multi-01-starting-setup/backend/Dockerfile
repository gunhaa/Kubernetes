FROM node:latest

WORKDIR /app

COPY package.json /app

RUN npm install

COPY . .

EXPOSE 80

# 동적으로 db 연결 설정 입력
# =를 통해 기본 값 넣기
ENV MONGODB_USERNAME=gunha 
ENV MONGODB_PASSWORD=secret

# CMD ["node" , "app.js"]

# nodemon 사용시 package.json에 의존성을 추가후 CMD를 바꾼다
CMD ["npm", "start"]

# mongodb 올리기
# docker run --name mongodb -d --rm -p 27017:27017 mongo

# 사용하지 않는 모든 이미지 제거
# docker image prune -a

# 백엔드 이미지 빌드
# docker build -t goals-node .

# 컨테이너 실행
# 프론트와 통신을위해 public 옵션으로 포트를 열어야 한다
# docker run --name goals-backend -d --rm -p 80:80 goals-node