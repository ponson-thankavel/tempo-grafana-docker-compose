1. First start up the stack.

```console
docker-compose up -d
```

At this point, the following containers should be spun up -

```console
docker-compose ps
```
```
                  Name                                Command               State                         Ports
-------------------------------------------------------------------------------------------------------------------------------------
tempo-grafana-docker-compose_grafana_1   /run.sh                          Up      0.0.0.0:3000->3000/tcp
tempo-grafana-docker-compose_tempo_1     /tempo -config.file=/etc/t ...   Up      0.0.0.0:3200->3200/tcp, 0.0.0.0:4317->4317/tcp
```

2. If you're interested you can see the wal/blocks as they are being created.

```console
ls tempo-data/
```

3. Navigate to [Grafana](http://localhost:3000/explore) and paste the trace id to request it from Tempo.

5. To stop the setup use -

```console
docker-compose down -v
```
