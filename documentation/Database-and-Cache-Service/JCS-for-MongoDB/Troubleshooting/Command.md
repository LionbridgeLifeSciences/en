# Which commands are limited by the MongoDB?

## Problem Description

Which commands are limited by the MongoDB?

## Problem Processing
To ensure that the MongoDB replica set is running properly, the MongoDB limits some commands, and the commands supported and limited are as follows:

|Command	|Support	|Not Support|
|---|---|---|
|Aggregates Commands|aggregate<br />distinct<br />count<br />group<br />mapReduce<br />| |
|Authentication|	logout<br />authenticate<br />getnonce<br />authSchemaUpgrade<br />copydbgetnonce<br /> | |
|Diagnostic Commands	| explain<br />listDatabases<br />dbHash<br />listCommands<br /availableQueryOptions<br />buildInfo<br />collStats<br />dbStats<br />cursorInfo<br />dataSize<br />ping<br />profile<br />top<br />whatsmyuri<br />serverStatus<br />features<br />isSelf<br />validate<br />| |
|Geospatial Commands	|geoNear<br />geoSearch<br />| |
|Instance Administration Commands	|renameCollection<br />dropDatabase<br />listCollections<br />drop<br />create<br />cloneCollection<br />cloneCollectionAsCapped<br />convertToCapped<br />filemd5<br />createIndexes<br />listIndexes<br />dropIndexes<br />fsync<br />connectionStatus<br />collMod<br />reIndex<br />touch<br />getParameter<br />compact<br />copydb<br />clone<br />clean<br />shutdown<br />logRotate<br />repairDatabase<br />repairCursor<br />setParameter<br />connPoolSync<br />setReadonly<br />cloneCollection<br />| |
|Query and Write Operation Commands	 |insert<br />update<br />delete<br />findAndModify<br />getLastError<br />getPrevError<br />resetError<br />parallelCollectionScan<br />eval<br />| |
| Query Plan Cache Commands	|planCacheListFilters<br />planCacheSetFilter<br />planCacheClearFilters<br />planCacheListQueryShapes<br />planCacheListPlans<br />planCacheClear<br />| |
|Replication Commands	| |replSetInitiate<br />replSetFreeze<br />replSetMaintenance<br />replSetGetConfig<br />replSetRequestVotes<br />replSetReconfig<br />replSetStepDown<br />replSetSyncFrom<br />replSetElect<br />replSetUpdatePosition<br />resync<br />appendOplogNote<br />|
|Replication Commands Diagnostic	|isMaster<br />applyOps<br />| |
|Role Management Commands	|createRole<br />updateRole<br />dropRole<br />dropAllRolesFromDatabase<br />grantPrivilegesToRole<br />revokePrivilegesFromRole<br />grantRolesToRole<br />revokeRolesFromRole<br />rolesInfo<br />invalidateUserCache<br />| |
|Sharding Commands	| | addShard<br />removeShard <br />getShardVersion<br />setShardVersion<br />unsetSharding<br />checkShardingIndex<br /> |
|User Management Commands	|createUser<br />updateUser<br />dropUser<br />dropAllUsersFromDatabase<br />grantRolesToUser<br />revokeRolesFromUser<br />usersInfo<br />|
