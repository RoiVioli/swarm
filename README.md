# swarm

## Init Swarm

```bash
docker swarm init --advertise-addr <IP>
```

## Swarm join

```bash
docker swarm join --token <TOKEN> <IP>
```
## Swarm join manager

```bash
docker swarm join-token manager
```

## Créer un service

```bash
docker service create --name web-server --publish 80:80 <image> --replicas x
```

## Consulter les services

```bash
docker service ls || docker service ps web-server
```

## Mise à l'échelle d'un service

```bash
docker service scale web-server=x
```

## Mettre à jour un service

```bash
docker service update --image <image>
```

> [docker service update](https://docs.docker.com/reference/cli/docker/service/update/)

## Retirer un nœud du service

```bash
docker node update --availability drain <node>
```

Pour réactiver le nœud, exécutez la commande

```bash
docker node update --availability active <node>
```

## Supprimer un service

```bash
docker service rm web-server
```

## Supprimer un cluster

```bash
docker swarm leave --force
```

## Backup

```bash
tar -czvf /tmp/swarm-backup.tar.gz /var/lib/docker/swarm
curl --upload-file /tmp/swarm-backup.tar.gz https://transfer.sh/swarm-backup.tar.gz
```

```bash
curl -L <lien> --output swarm-backup.tar.gz
tar -xzvf swarm-backup.tar.gz -C /var/lib/docker/swarm/
docker swarm init --force-new-cluster --advertise-addr <ip>
```

## Docker Stack

```bash
docker stack deploy --compose-file file.yml name
```

> [Documentation](https://docs.docker.com/engine/reference/commandline/stack/)