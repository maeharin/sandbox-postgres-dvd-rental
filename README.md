http://www.postgresqltutorial.com/postgresql-sample-database/ のサンプルデータベースをdockerコンテナで起動する

## how to use

イメージ作成

```
$ docker build -t postgres-dvd-rental .
```

コンテナ起動

```
$ docker run --rm --name postgres-dvd-rental-container -v ${PWD}/dumpfile/:/tmp/dumpfile/ postgres-dvd-rental
```

データをrestore

```
$ docker exec postgres-dvd-rental-container pg_restore -U postgres -d dvdrental /tmp/dumpfile/dvdrental.tar
```

psqlでデータ確認

```
$ docker exec -it postgres-dvd-rental-container psql -U postgres dvdrental
```

コンテナ停止

```
$ docker stop postgres-dvd-rental-container
```
