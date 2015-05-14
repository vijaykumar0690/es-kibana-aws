# docker-eck-aws

This Dockerfile can be used to build an EllasticSearch Cluster with Kibana, that can be used to run  in AWS, with auto discovery by passing the appropriate ENV variables

`AWS_ACCESS_KEY_ID`  ---> Your AWS Access key

`AWS_SECRET_KEY`     ---> Your AWS Secret Key

`ES_CLUSTER_NAME`    ---> ElasticSearch Cluster Name *Important No default cluster name set

`AWS_SECURITY_GROUP` ---> AWS Security Group Name

`AWS_REGION`         ---> AWS Region

Create a separate IAM user with EC2 read only access and use the access keys here.

  docker run -it -p 9200:9200 -p 9300:9300 -p 80:5601 \
    -e AWS_ACCESS_KEY_ID=XXXXXXXXXXXXXXXXXXXXXX \
    -e AWS_SECRET_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx \
    -e AWS_SECURITY_GROUP=default \
    -e AWS_REGION=us-east-1 \
    -e ES_CLUSTER_NAME=elasticsearch \
 shanmugakarna/es-kibana-aws
 
 Please provide fixed port mapping to 9200 and 9300 as it is required for auto-discovery to work.
