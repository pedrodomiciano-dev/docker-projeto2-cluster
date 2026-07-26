# Docker Swarm Cluster com Vagrant

## 📖 Descrição

Este projeto demonstra a criação de um cluster Docker Swarm utilizando máquinas virtuais provisionadas automaticamente pelo Vagrant.

O ambiente é composto por um nó **Manager** e dois nós **Workers**, todos executando Ubuntu Server com Docker instalado automaticamente durante o provisionamento.

Este projeto foi desenvolvido como prática da formação **Docker Fundamentals** da DIO.

---

## 🛠 Tecnologias utilizadas

* Docker Engine
* Docker Swarm
* Vagrant
* VirtualBox
* Ubuntu Server 22.04

---

## 📂 Estrutura do projeto

```
.
├── Vagrantfile
├── docker.sh
├── mestre.sh
├── trabalhador.sh
└── .gitignore
```

---

## 🖥 Arquitetura

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

## 🚀 Como executar

Clone o repositório:

```bash
git clone https://github.com/pedrodomiciano-dev/docker-projeto2-cluster.git
```

Entre na pasta:

```bash
cd docker-projeto2-cluster
```

Inicie o ambiente:

```bash
vagrant up
```

Acesse o nó Manager:

```bash
vagrant ssh master
```

Verifique os nós do cluster:

```bash
docker node ls
```

Verifique os serviços:

```bash
docker service ls
```

---

## 📜 Scripts

### docker.sh

Responsável por instalar o Docker em todas as máquinas virtuais.

### mestre.sh

Inicializa o Docker Swarm e configura a máquina Master como Manager.

### trabalhador.sh

Adiciona automaticamente os nós Worker ao cluster utilizando o token gerado pelo Manager.

---

## 🎯 Objetivo

Demonstrar na prática:

* Provisionamento automatizado com Vagrant;
* Instalação automática do Docker;
* Criação de um cluster Docker Swarm;
* Comunicação entre Manager e Workers;
* Automação utilizando Shell Script.

---

## 📚 Aprendizados

Durante este projeto foram praticados conceitos como:

* Docker Swarm;
* Orquestração de containers;
* Provisionamento de máquinas virtuais;
* Shell Script;
* Redes privadas no Vagrant;
* Cluster Manager e Worker.

---

## 👨‍💻 Autor

Pedro Domiciano

GitHub: https://github.com/pedrodomiciano-dev
