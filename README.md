# swarm

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

## Docker Stack

```bash
docker stack deploy --compose-file file.yml name
```

> [Documentation](https://docs.docker.com/engine/reference/commandline/stack/)