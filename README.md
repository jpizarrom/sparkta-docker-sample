# README #

This README would normally document whatever steps are necessary to get your application up and running.

### What is this repository for? ###

* Quick summary
* Version
* [Learn Markdown](https://bitbucket.org/tutorials/markdowndemo)

### How do I get set up? ###
```
docker-compose -f sparta-compose-standalone.yml scale zookeeper=1 waitzk=1
docker-compose -f sparta-compose-standalone.yml scale namenode=1
docker-compose -f sparta-compose-standalone.yml scale datanode=1
docker-compose -f sparta-compose-standalone.yml scale spark-master=1
docker-compose -f sparta-compose-standalone.yml scale spark-slave=1
docker-compose -f sparta-compose-standalone.yml scale sparta=1
docker-compose -f sparta-compose-standalone.yml scale mongo=1
```

### samples ###

#### web socket input ####
```
ws://stream.meetup.com/2/rsvps
curl -H "Content-Type: application/json" --data @basic-ws.json http://localhost:9090/policyContext
```

#### socket input ####
```
nc -lk 9999
curl -H "Content-Type: application/json" --data @basic-socket.json http://localhost:9090/policyContext
```

#### kinesis input ####
replace aws credentials in basic-kinesis.json
```
curl -H "Content-Type: application/json" --data @basic-kinesis.json http://localhost:9090/policyContext
aws kinesis put-record --stream-name mystream --partition-key mystream --data '{"group":{"group_country":"es"},"mtime":1469654722000,"guests":2}'
```

#### download ####
```
wget http://apache.rediris.es/spark/spark-1.6.2/spark-1.6.2-bin-hadoop2.6.tgz
wget http://www.eu.apache.org/dist/hadoop/common/hadoop-2.7.1/hadoop-2.7.1.tar.gz
```
