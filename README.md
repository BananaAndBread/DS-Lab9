### report

installation was done using helm:

$ helm install --name qweqweqwe stable/mongodb-replicaset

the chat was rocketchat:

$ helm install --name qwer -f rocket.yaml stable/rocketchat

`rocket.yaml`:
```yaml
externalMongodbUrl: mongodb://qweqweqwe-mongodb-replicaset-0.qweqweqwe-mongodb-replicaset,qweqweqwe-mongodb-replicaset-1.qweqweqwe-mongodb-replicaset,qweqweqwe-mongodb-replicaset-2.qweqweqwe-mongodb-replicaset/rocketchat?replicaSet=rs0
externalMongodbOplogUrl: mongodb://qweqweqwe-mongodb-replicaset-0.qweqweqwe-mongodb-replicaset,qweqweqwe-mongodb-replicaset-1.qweqweqwe-mongodb-replicaset,qweqweqwe-mongodb-replicaset-2.qweqweqwe-mongodb-replicaset/local?replicaSet=rs0

service.type: NodePort
mongo.enabled: false
```

`rs.status()`:
```json
{
        "set" : "rs0",
        "date" : ISODate("2019-11-01T17:43:54.249Z"),
        "myState" : 2,
        "term" : NumberLong(2),
        "syncingTo" : "qweqweqwe-mongodb-replicaset-0.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
        "syncSourceHost" : "qweqweqwe-mongodb-replicaset-0.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
        "syncSourceId" : 0,
        "heartbeatIntervalMillis" : NumberLong(2000),
        "optimes" : {
                "lastCommittedOpTime" : {
                        "ts" : Timestamp(1572630225, 1),
                        "t" : NumberLong(2)
                },
                "readConcernMajorityOpTime" : {
                        "ts" : Timestamp(1572630225, 1),
                        "t" : NumberLong(2)
                },
                "appliedOpTime" : {
                        "ts" : Timestamp(1572630225, 1),
                        "t" : NumberLong(2)
                },
                "durableOpTime" : {
                        "ts" : Timestamp(1572630225, 1),
                        "t" : NumberLong(2)
                }
        },
        "members" : [
                {
                        "_id" : 0,
                        "name" : "qweqweqwe-mongodb-replicaset-0.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "health" : 1,
                        "state" : 1,
                        "stateStr" : "PRIMARY",
                        "uptime" : 939,
                        "optime" : {
                                "ts" : Timestamp(1572630225, 1),
                                "t" : NumberLong(2)
                        },
                        "optimeDurable" : {
                                "ts" : Timestamp(1572630225, 1),
                                "t" : NumberLong(2)
                        },
                        "optimeDate" : ISODate("2019-11-01T17:43:45Z"),
                        "optimeDurableDate" : ISODate("2019-11-01T17:43:45Z"),
                        "lastHeartbeat" : ISODate("2019-11-01T17:43:54.122Z"),
                        "lastHeartbeatRecv" : ISODate("2019-11-01T17:43:54.122Z"),
                        "pingMs" : NumberLong(0),
                        "lastHeartbeatMessage" : "",
                        "syncingTo" : "",
                        "syncSourceHost" : "",
                        "syncSourceId" : -1,
                        "infoMessage" : "",
                        "electionTime" : Timestamp(1572629272, 1),
                        "electionDate" : ISODate("2019-11-01T17:27:52Z"),
                        "configVersion" : 3
                },
                {
                        "_id" : 1,
                        "name" : "qweqweqwe-mongodb-replicaset-1.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "health" : 1,
                        "state" : 2,
                        "stateStr" : "SECONDARY",
                        "uptime" : 941,
                        "optime" : {
                                "ts" : Timestamp(1572630225, 1),
                                "t" : NumberLong(2)
                        },
                        "optimeDate" : ISODate("2019-11-01T17:43:45Z"),
                        "syncingTo" : "qweqweqwe-mongodb-replicaset-0.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "syncSourceHost" : "qweqweqwe-mongodb-replicaset-0.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "syncSourceId" : 0,
                        "infoMessage" : "",
                        "configVersion" : 3,
                        "self" : true,
                        "lastHeartbeatMessage" : ""
                },
                {
                        "_id" : 2,
                        "name" : "qweqweqwe-mongodb-replicaset-2.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "health" : 1,
                        "state" : 2,
                        "stateStr" : "SECONDARY",
                        "uptime" : 914,
                        "optime" : {
                                "ts" : Timestamp(1572630225, 1),
                                "t" : NumberLong(2)
                        },
                        "optimeDurable" : {
                                "ts" : Timestamp(1572630225, 1),
                                "t" : NumberLong(2)
                        },
                        "optimeDate" : ISODate("2019-11-01T17:43:45Z"),
                        "optimeDurableDate" : ISODate("2019-11-01T17:43:45Z"),
                        "lastHeartbeat" : ISODate("2019-11-01T17:43:54.123Z"),
                        "lastHeartbeatRecv" : ISODate("2019-11-01T17:43:52.671Z"),
                        "pingMs" : NumberLong(0),
                        "lastHeartbeatMessage" : "",
                        "syncingTo" : "qweqweqwe-mongodb-replicaset-1.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "syncSourceHost" : "qweqweqwe-mongodb-replicaset-1.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "syncSourceId" : 1,
                        "infoMessage" : "",
                        "configVersion" : 3
                }
        ],
        "ok" : 1,
        "operationTime" : Timestamp(1572630225, 1),
        "$clusterTime" : {
                "clusterTime" : Timestamp(1572630225, 1),
                "signature" : {
                        "hash" : BinData(0,"AAAAAAAAAAAAAAAAAAAAAAAAAAA="),
                        "keyId" : NumberLong(0)
                }
        }
}
```

`rs.config()`:
```json
{
        "_id" : "rs0",
        "version" : 3,
        "protocolVersion" : NumberLong(1),
        "members" : [
                {
                        "_id" : 0,
                        "host" : "qweqweqwe-mongodb-replicaset-0.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "arbiterOnly" : false,
                        "buildIndexes" : true,
                        "hidden" : false,
                        "priority" : 1,
                        "tags" : {

                        },
                        "slaveDelay" : NumberLong(0),
                        "votes" : 1
                },
                {
                        "_id" : 1,
                        "host" : "qweqweqwe-mongodb-replicaset-1.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "arbiterOnly" : false,
                        "buildIndexes" : true,
                        "hidden" : false,
                        "priority" : 1,
                        "tags" : {

                        },
                        "slaveDelay" : NumberLong(0),
                        "votes" : 1
                },
                {
                        "_id" : 2,
                        "host" : "qweqweqwe-mongodb-replicaset-2.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "arbiterOnly" : false,
                        "buildIndexes" : true,
                        "hidden" : false,
                        "priority" : 1,
                        "tags" : {

                        },
                        "slaveDelay" : NumberLong(0),
                        "votes" : 1
                }
        ],
        "settings" : {
                "chainingAllowed" : true,
                "heartbeatIntervalMillis" : 2000,
                "heartbeatTimeoutSecs" : 10,
                "electionTimeoutMillis" : 10000,
                "catchUpTimeoutMillis" : -1,
                "catchUpTakeoverDelayMillis" : 30000,
                "getLastErrorModes" : {

                },
                "getLastErrorDefaults" : {
                        "w" : 1,
                        "wtimeout" : 0
                },
                "replicaSetId" : ObjectId("5dbc6b07dedb6432d7d6d791")
        }
}
```

### Screenshot of spam:

### Brutally murdering master

```
$ kubectl delete qweqweqwe-mongodb-replicaset-0
```

### Screenshot of spam again:


`rs.status()`:
```json
{
        "set" : "rs0",
        "date" : ISODate("2019-11-01T17:44:05.676Z"),
        "myState" : 2,
        "term" : NumberLong(2),
        "syncingTo" : "",
        "syncSourceHost" : "",
        "syncSourceId" : -1,
        "heartbeatIntervalMillis" : NumberLong(2000),
        "optimes" : {
                "lastCommittedOpTime" : {
                        "ts" : Timestamp(1572630240, 1),
                        "t" : NumberLong(2)
                },
                "readConcernMajorityOpTime" : {
                        "ts" : Timestamp(1572630240, 1),
                        "t" : NumberLong(2)
                },
                "appliedOpTime" : {
                        "ts" : Timestamp(1572630240, 1),
                        "t" : NumberLong(2)
                },
                "durableOpTime" : {
                        "ts" : Timestamp(1572630240, 1),
                        "t" : NumberLong(2)
                }
        },
        "members" : [
                {
                        "_id" : 0,
                        "name" : "qweqweqwe-mongodb-replicaset-0.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "health" : 0,
                        "state" : 8,
                        "stateStr" : "(not reachable/healthy)",
                        "uptime" : 0,
                        "optime" : {
                                "ts" : Timestamp(0, 0),
                                "t" : NumberLong(-1)
                        },
                        "optimeDurable" : {
                                "ts" : Timestamp(0, 0),
                                "t" : NumberLong(-1)
                        },
                        "optimeDate" : ISODate("1970-01-01T00:00:00Z"),
                        "optimeDurableDate" : ISODate("1970-01-01T00:00:00Z"),
                        "lastHeartbeat" : ISODate("2019-11-01T17:44:04.326Z"),
                        "lastHeartbeatRecv" : ISODate("2019-11-01T17:44:02.127Z"),
                        "pingMs" : NumberLong(0),
                        "lastHeartbeatMessage" : "Connection refused",
                        "syncingTo" : "",
                        "syncSourceHost" : "",
                        "syncSourceId" : -1,
                        "infoMessage" : "",
                        "configVersion" : -1
                },
                {
                        "_id" : 1,
                        "name" : "qweqweqwe-mongodb-replicaset-1.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "health" : 1,
                        "state" : 2,
                        "stateStr" : "SECONDARY",
                        "uptime" : 952,
                        "optime" : {
                                "ts" : Timestamp(1572630240, 1),
                                "t" : NumberLong(2)
                        },
                        "optimeDate" : ISODate("2019-11-01T17:44:00Z"),
                        "syncingTo" : "",
                        "syncSourceHost" : "",
                        "syncSourceId" : -1,
                        "infoMessage" : "could not find member to sync from",
                        "configVersion" : 3,
                        "self" : true,
                        "lastHeartbeatMessage" : ""
                },
                {
                        "_id" : 2,
                        "name" : "qweqweqwe-mongodb-replicaset-2.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "health" : 1,
                        "state" : 2,
                        "stateStr" : "SECONDARY",
                        "uptime" : 926,
                        "optime" : {
                                "ts" : Timestamp(1572630240, 1),
                                "t" : NumberLong(2)
                        },
                        "optimeDurable" : {
                                "ts" : Timestamp(1572630240, 1),
                                "t" : NumberLong(2)
                        },
                        "optimeDate" : ISODate("2019-11-01T17:44:00Z"),
                        "optimeDurableDate" : ISODate("2019-11-01T17:44:00Z"),
                        "lastHeartbeat" : ISODate("2019-11-01T17:44:05.324Z"),
                        "lastHeartbeatRecv" : ISODate("2019-11-01T17:44:05.578Z"),
                        "pingMs" : NumberLong(0),
                        "lastHeartbeatMessage" : "",
                        "syncingTo" : "qweqweqwe-mongodb-replicaset-1.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "syncSourceHost" : "qweqweqwe-mongodb-replicaset-1.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "syncSourceId" : 1,
                        "infoMessage" : "",
                        "configVersion" : 3
                }
        ],
        "ok" : 1,
        "operationTime" : Timestamp(1572630240, 1),
        "$clusterTime" : {
                "clusterTime" : Timestamp(1572630240, 1),
                "signature" : {
                        "hash" : BinData(0,"AAAAAAAAAAAAAAAAAAAAAAAAAAA="),
                        "keyId" : NumberLong(0)
                }
        }
}
```

`rs.config()`:

```json
{
        "_id" : "rs0",
        "version" : 3,
        "protocolVersion" : NumberLong(1),
        "members" : [
                {
                        "_id" : 0,
                        "host" : "qweqweqwe-mongodb-replicaset-0.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "arbiterOnly" : false,
                        "buildIndexes" : true,
                        "hidden" : false,
                        "priority" : 1,
                        "tags" : {

                        },
                        "slaveDelay" : NumberLong(0),
                        "votes" : 1
                },
                {
                        "_id" : 1,
                        "host" : "qweqweqwe-mongodb-replicaset-1.qweqweqwe-mongodb-replicaset.default.svc.cluster.local:27017",
                        "arbiterOnly" : false,
                        "buildIndexes" : true,
                        "hidden" : false,
                        "priority" : 1,
                        "tags" : {

                        },
                        "slaveDelay" : NumberLong(0),
                        "votes" : 1
                },
                {
                        "_id" : 2,
                        "host" : "qweqweqwe-mongodb-replicaset-2.qweqweqwe-mongodb-replicaset.default.svcr.local:27017",
                        "arbiterOnly" : false,
                        "buildIndexes" : true,
                        "hidden" : false,
                        "priority" : 1,
                        "tags" : {

                        },
                        "slaveDelay" : NumberLong(0),
                        "votes" : 1
                }
        ],
        "settings" : {
                "chainingAllowed" : true,
                "heartbeatIntervalMillis" : 2000,
                "heartbeatTimeoutSecs" : 10,
                "electionTimeoutMillis" : 10000,
                "catchUpTimeoutMillis" : -1,
                "catchUpTakeoverDelayMillis" : 30000,
                "getLastErrorModes" : {

                },
                "getLastErrorDefaults" : {
                        "w" : 1,
                        "wtimeout" : 0
                },
                "replicaSetId" : ObjectId("5dbc6b07dedb6432d7d6d791")
        }
}
```
