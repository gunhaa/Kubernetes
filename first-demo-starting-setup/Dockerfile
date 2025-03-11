# node:14 이미지에는 Node.js와 함께 npm이 기본적으로 설치되어 있다.
FROM node:14
# 컨테이너 파일 시스템에는 디렉토리가 있다
# 모든 컨테이너에는 자체 파일 시스템이 있다
# 컨테이너 내에서 작업 디렉토리 설정
WORKDIR /app

# package.json 현재 작업 디렉토리(/app)으로 복사
COPY package.json .

# package.json의 모든 종속성 설치
RUN npm install

# 현재 디렉토리의 모든 파일을 컨테이너 작업 디렉토리로 복사
COPY . .

# 컨테이너의 3000번 포트를 외부에 노출
EXPOSE 3000

# 컨테이너 실행 시 app.mjs 파일을 Node.js로 실행
CMD [ "node", "app.mjs" ]

# docker build .
# 이미지를 빌드한다
# docker run -p 3000:3000 이미지ID
# 이미지를 실행시킨다