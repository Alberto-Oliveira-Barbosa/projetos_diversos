# Cluster local com Docker Swarm e Vagrant

- Cria 1 Node Manager para gerenciar os demais Workers (Master)
- Cria 3 Nodes Workers (Node01,Node02, Node03)

## Descrição dos arquivos 

- `Vagrantfile` --> Arquivo que contém todas as configurações necessárias para instanciar as máquinas virtuais.
- `docker.sh` --> Arquivo que instala o docker na máquina virtual que está sendo criada 
- `master.sh` --> Arquivo que cria no node manager e após isso gera um novo arquivo *worker.sh* com o token usado para instanciar o node worker
- `worker.sh` --> Arquivo de exemplo de como é gerado pelo script *master.sh* 


## Modo de uso 

Com todos os aquivos e estando na pasta rodar o comando para instanciar as máquinas:

```shell
vagrant up
```

Apos isso, ativar o nó master com o comando:

```shell
vagrant ssh master
```

se tudo ocorrer bem, dentro do node master podemos alterar para o usuário root e listar os contêineres do node:

```shell
sudo su

docker node ls
```