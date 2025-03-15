FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

CMD ["node", "app.js"]

# 이미지 빌드
# docker build -t favorites-node .

# 이 컨테이너는 노드앱과 그에 속한 코드만을 포함한다
# MongoDB는 다른 컨테이너에 소속되어 있다

# 컨테이너 실행
# docker run --name favorites -d --rm -p 3000:3000 favorites-node
# 현재 mongodb가 없어 컨테이너 실행이 안된다

# 이미지 재 빌드, db부분 삭제 후 실행 가능

# docker run -d --name mongodb mongo로 mongodb 컨테이너 설치, 실행 가능

# docker container inspect mongodb 
# Network
# "Networks": {
#     "bridge": {
#         "IPAMConfig": null,
#         "Links": null,
#         "Aliases": null,
#         "MacAddress": "02:42:ac:11:00:02",
#         "DriverOpts": null,
#         "NetworkID": "c84c6b8e610ec069f74bba9ea1b3fb9a4df1259132379e9e0bd0f7fd58059770",
#         "EndpointID": "252328d304fd76ef2bdce29b71c77b9d5a176b174a49b6d8777d7b06856d9f1e",
#         "Gateway": "172.17.0.1",
#         "IPAddress": "172.17.0.2",
#         "IPPrefixLen": 16,
#         "IPv6Gateway": "",
#         "GlobalIPv6Address": "",
#         "GlobalIPv6PrefixLen": 0,
#         "DNSNames": null
#     }
# }
# IPAddress 를 통해 연결 가능하다.

# 해당 앱 /favorites를 통해 테스트 가능
# GET favorites 반환 POST favorites 생성
# {
#     "name" : "A new Hope",
#     "type" : "movie",
#     "url" : "http://swap.dev/api/files/1/"
# }
# post로 해당 body 보내면 favorites 내용 저장

# 네트워크 생성
# docker network create favorites-net

# docker run 에서 옵션으로 --network my_network 를 넣으면 네트워크에 참여할 수 있다.
# docker run -d --name mongodb --network favorites-net mongo
# mongo 의 경우 -p 옵션이 없는 것은 외부에서 접근할 필요가 없어서 그런 것이다
# docker run --name favorites --network favorites-net -d --rm -p 3000:3000 favorites-node