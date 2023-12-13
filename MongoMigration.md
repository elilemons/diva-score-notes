# Mongo Migration

Run these commands in the shell, not mongoshell
```sh
mongodump --uri="DBCONNECTIONSTRING" \
  --collection="COLLECTIONNAME" \
  --forceTableScan -v --gzip --out ./dump
```

**I did have to move the .gz files out of the folder this created for the restore to work**

```sh
mongorestore --uri="PRODCONNECTIONSTRING" \
  --drop --noIndexRestore --gzip -v ./dump
```


Used this [guide](https://www.loginradius.com/blog/engineering/live-data-migration-mongodb/)