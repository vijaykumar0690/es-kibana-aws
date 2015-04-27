# docker-eck-aws

This Dockerfile can be used to build an EllasticSearch image with Kibana, that can be used to run  in AWS, with auto discovery by passing the appropriate ENV variables

Note: Data Source is CouchBase here

`AWS_ACCESS_KEY_ID`  ---> Your AWS Access key

`AWS_SECRET_KEY`     ---> Your AWS Secret Key

`ES_CLUSTER_NAME`    ---> ElasticSearch Cluster Name

`AWS_SECURITY_GROUP` ---> AWS Security Group Name

`AWS_REGION`         ---> AWS Region

`HOST_IP`            ---> Host Machine IP the Docker is running on

`
docker run -it -p 9200:9200 -p 9300:9300 -p 9091:9091 -p 80:5601 -e AWS_ACCESS_KEY_ID=XXXXXXXXXXXXXXXX -e AWS_SECRET_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx -e ES_CLUSTER_NAME=elasticsearch -e AWS_SECURITY_GROUP=default -e AWS_REGION=us-east-1 -e HOST_IP=$(hostname -i) shanmugakarna/eck:latest`
