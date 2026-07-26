# Docker Swarm Cluster com Vagrant (Desafio da DIO)

## Descrição

Este projeto demonstra a criação de um cluster Docker Swarm utilizando máquinas virtuais com Vagrant.

O ambiente é composto por um nó **Master** e dois nós **Workers**, executandos no Ubuntu Server com Docker instalado automaticamente durante o provisionamento.

Este projeto foi desenvolvido como prática da formação **Docker Fundamentals** da DIO.

---

## Tecnologias 

* Docker Engine
* Docker Swarm
* Vagrant
* VirtualBox
* Ubuntu Server

---

## Estrutura do projeto

```
.
├── Vagrantfile
├── docker.sh
├── mestre.sh
├── trabalhador.sh
└── .gitignore
```

---

## Arquitetura (para melhor visualização)

```
                +-----------------------+
                |        Master         |
                |    10.10.10.100       |
                |   Docker Manager      |
                +-----------+-----------+
                            |
              -----------------------------
              |                           |
      +---------------+           +---------------+
      |    Node001    |           |    Node002    |
      | 10.10.10.101  |           | 10.10.10.102  |
      | Docker Worker |           | Docker Worker |
      +---------------+           +---------------+
```

---

## Como executar

1- Clone o repositório:

```bash
git clone https://github.com/pedrodomiciano-dev/docker-projeto2-cluster.git
```

2- Entre na pasta:

```bash
cd docker-projeto2-cluster
```

3- Inicie o ambiente:

```bash
vagrant up
```

4- Acesse o nó Manager:

```bash
vagrant ssh master
```

5- Verifique os nós do cluster:

```bash
docker node ls
```

6- Verifique os serviços:

```bash
docker service ls
```

---

## Scripts e suas funçoes:

### docker.sh

Instala o Docker em todas as máquinas virtuais.

### master.sh

Inicializa o Docker Swarm e configura a máquina Master como Manager.

### worker.sh

Adiciona automaticamente os nós Worker ao cluster utilizando o token gerado pelo Manager.

---


