# coredatabase.operationsStore

Storage of incoming operations. All plugins persist their operations in this central table. Alarmmonitor, UI and all other ALARMiator areas dealing with operations pull operation information out of this table. 

### id
Unique Identifier, Auto increment

### alarmdate
Date alarm / operation has been raised. This should report the alarmdate out of the source and not been set to the date the alarm has been recieved.

### alarmtime
Time the alarm / operation has been raised. This should report the alarmtime out of the source and not been set to the time the alarm has been recieved.

### alarmtimeCalc
Calculated timestamp of combination from alarmdate and alarmtime. Used for querying and sorting of operations.

### gear
List of gear requested in operation as it was reported from source.

### gearListCalc
JSON representation of `gear`. If `gear` lists more than one requested gear entry, this will be a JSON array.

### operationnumber
Operationnumer as reported by source of operation. This is ususally a unique identifier by ILS.

### location
Location of the operation

### message
Message with more details about the operation. This is usually a more detailed information of an ILS agent.

### community
community information for the operation

### rawdata
JSON representation of the whole operation as the source has sent it (before processing by the connector)

### object
Object as reported by the source

### district
District as reported by the source

### keywordId
ID or idenfifier part of the keyword

### keywordCategory
Category part of keyword

### keywordRaw
Keyword as RAW information

### keywordName
Name part of Keyword

### zveis
List of zveis as reported by source

### zveisListCalc
Calculated list of zveis from field `zveis` as JSON array

### subject
Subject as reported by source

### street
Street information for operation as reported by source

### gkx
X coordinate Gauss Krueger format

### gky
y coordinate Gauss Krueger format

### lat
Latitude information of operation

### lon
Longitude information of operation

### operationState
State of operation
* 0 New operation
* 1 Operation closed
* 2 Operation archived (not visisble anymore for plugins)

### operationSourceConnector
namespace of plugin the operation has been created from


