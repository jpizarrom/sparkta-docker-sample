# README #

This README would normally document whatever steps are necessary to get your application up and running.

### What is this repository for? ###

* Quick summary
* Version
* [Learn Markdown](https://bitbucket.org/tutorials/markdowndemo)

### How do I get set up? ###
```
docker-compose -f sparta-compose.yml scale zookeeper=1 waitzk=1
docker-compose -f sparta-compose.yml scale namenode=1
docker-compose -f sparta-compose.yml scale datanode=1
docker-compose -f sparta-compose.yml scale spark-master=1
docker-compose -f sparta-compose.yml scale spark-slave=1
docker-compose -f sparta-compose.yml scale sparta=1
docker-compose -f sparta-compose.yml scale mongo=1
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
aws kinesis put-record --stream-name mystream --partition-key mystream --data '{"group":{"group_country":"es"},"mtime":1469678639521,"guests":2}'
```