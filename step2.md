# SQS

## 생성

## send message

```bash
aws sqs send-message --queue-url "<queue url>" --message-body "<message>"  --region "<region>"
```

## receive message

```bash
aws sqs receive-message --queue-url "<queue url>" --region "<region>"
```

## delete message

```bash
aws sqs delete-message --queue-url "<queue url>" --receipt-handle "<receipt handle>" --region "<region>"
```

# docker

- [docker 설명](./etc/docker.md)

# ECS

## 배포 이미지 ECR에 배포

```bash
# 1. Docker 클라이언트에서 레지스트리에 인증하는 데 사용할 로그인 명령을 검색후 docker login
$(aws ecr get-login --no-include-email --region ap-northeast-2)

# 2.  Docker 이미지를 빌드합니다.
docker build -t <ECR repository 이름> .

# 3. 빌드 완료 후, 현재 리포지토리에 이미지를 푸시할 수 있도록 해당 이미지에 태그를 지정합니다.
docker tag <ECR repository 이름>:<TAG> <ECR repository URI>:<TAG>

# 4. 다음 명령을 실행하여 이 이미지를 새로 생성한 AWS 리포지토리로 푸시합니다.
docker push <ECR repository URI>:<TAG>
```
