# node_test
aws ecr get-login-password --region ap-northeast-1 | docker login --username AWS --password-stdin 117232438179.dkr.ecr.ap-northeast-1.amazonaws.com
docker build -t app_runner/node-app .
docker tag app_runner/node-app:latest 117232438179.dkr.ecr.ap-northeast-1.amazonaws.com/app_runner:node
docker push 117232438179.dkr.ecr.ap-northeast-1.amazonaws.com/app_runner:node

docker run -p 4916:8000 -d app_runner/node-app
