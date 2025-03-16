# node에 의존한다
FROM node

# 다른 컨테이너이기에 backend와 충돌하지 않는다
WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm" , "start"]

# build
# docker build -t goals-react .  

# run
# docker run --rm --name goals-frontend -p 3000:3000 -it goals-react
# -it가 없으면 자동 종료된다, -d면 자동 종료되는 메커니즘이 react에 있다