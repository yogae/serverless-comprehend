# AWS service 설명

## 주요 용어 정리

* region
  * 각 리전은 개별 지리 영역입니다.
  * [region별 service](https://aws.amazon.com/ko/about-aws/global-infrastructure/regional-product-services/)

* availity zone
  * 각 가용 영역은 서로 격리되어 있지만, 한 리전 안의 가용 영역은 지연 시간이 짧은 링크를 통해 연결되어 있습니다.
  * [AWS 글로벌 인프라 맵](https://aws.amazon.com/ko/about-aws/global-infrastructure/)

* edge location
  * AWS에서 CloudFront의 cache 서버
  * [CloudFront](https://aws.amazon.com/ko/cloudfront/features/?nc=sn&loc=2)

## computing

### ec2

#### instance

* spot instance

    Amazon EC2 스팟 인스턴스를 사용하면 AWS 클라우드에서 미사용 EC2 용량을 활용할 수 있습니다. 스팟 인스턴스는 온디맨드 요금과 비교하여 최대 90% 할인된 금액으로 제공됩니다.

* reserved instance

    Amazon EC2 예약 인스턴스(RI)는 온디맨드 요금과 비교하여 상당한 할인 혜택(최대 75%)을 제공하며 특정 가용 영역에서 사용하는 경우에는 용량 예약을 제공합니다.

* on-demand instance

#### orchestration

* ECS
  * ec2
  * fargate
* EKS

## storage

* object storage(S3)
* file storage(EFS)
* volume storage(EBS)

## network

* VPC
  * Virtual Private Cloud(VPC)는 사용자의 AWS 계정 전용 가상 네트워크입니다.
* subnet
  * 서브넷은 VPC의 IP 주소 범위입니다. 지정된 서브넷으로 AWS 리소스를 시작할 수 있습니다.
  * 인터넷에 연결되어야 하는 리소스에는 퍼블릭 서브넷을 사용하고, 인터넷에 연결되지 않는 리소스에는 프라이빗 서브넷을 사용하십시오.

> * [internet gateway](./images/internet-gateway.png)
> * [security group](./images/security-diagram.png)
> * [public&private subnet](./images/nat-gateway-diagram.png)

## 사용할 aws service

* lambda
* ECS
* ECR
* VPC
* sqs
  * [동작 방식](./images/sqs.png)
  * [visibility](https://docs.aws.amazon.com/ko_kr/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-visibility-timeout.html)
  * dead queue
  * message 소비자 종류
    * ecs
      * polling 방식
    * lambda
      * 자동으로 message가 쌓이면 trigger되는 방식
      * polling 방식
* IAM
  * group
  * user
  * rule
  * policy
* S3

## Reference

* [storage 종류별 특징](https://www.redhat.com/ko/topics/data-storage/file-block-object-storage)
