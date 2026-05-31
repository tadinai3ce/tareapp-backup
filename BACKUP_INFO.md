# TareApp backup

- Generated: 2026-05-31T06:00:04Z
- Host: tests
- DB:   db.sql.gz (44K)
- Uploads: uploads.tar.gz (844K)

This repository holds the **latest** snapshot only. Each backup overwrites the
previous one via force-push. Restore with:

```
gunzip < db.sql.gz | docker exec -i tareapp-db-1 psql -U tareapp -d tareapp
docker run --rm -v tareapp_uploads:/data -v "$PWD:/in" alpine \
  sh -c 'cd /data && tar xzf /in/uploads.tar.gz'
```
