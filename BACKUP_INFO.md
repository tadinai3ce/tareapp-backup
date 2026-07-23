# TareApp backup

- Generated: 2026-07-23T22:00:23Z
- Host: srv63255-225181.vps.etecsa.cu
- DB:   db.sql.gz (6.1M)
- Uploads: uploads.tar.gz (3.4M)

This repository holds the **latest** snapshot only. Each backup overwrites the
previous one via force-push. Restore with:

```
gunzip < db.sql.gz | docker exec -i tareapp-db-1 psql -U tareapp -d tareapp
docker run --rm -v tareapp_uploads:/data -v "$PWD:/in" alpine \
  sh -c 'cd /data && tar xzf /in/uploads.tar.gz'
```
