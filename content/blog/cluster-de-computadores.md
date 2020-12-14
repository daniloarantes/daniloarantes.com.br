---
title:  "O que é um Cluster de Computadores?"
author:  "Danilo Arantes"
tags: ["Ciência da Computação"]
date:  "2017-06-19T21:26:58+00:00"
---

Este é o trecho de um artigo meu sobre Redundância e Replicação de dados utilizando MySQL e MySQL Cluster. O desenvolvimento do artigo foi baseado em um cluster responsável pelo gerenciamento do banco de dados - em outro post falarei mais sobre esse trabalho com exemplo e aplicação prática.

## **Cluster &#8211; Conceito**

Os clusters podem ser utilizados em diversas aplicações, como por exemplo, renderização de efeitos especiais, meteorologia, simulações, etc.

Cluster pode ser definido como um sistema onde dois ou mais computadores trabalham de maneira conjunta para realizar processamento pesado. As tarefas são divididas entre os computadores chamados de nós que processam as informações, trabalhando como um único computador.

## **Tipos de Cluster**

Diversos modelos de clusters podem ser utilizados hoje em dia, cada modelo para um tipo de aplicação específica.
Abaixo são apresentados alguns tipos de cluster com uma breve descrição:

### **Alta Disponibilidade (High Availability (HA))**

Utilizando redundância, clusters HA são construídos para prover alta disponibilidade.

Caso um nó desse cluster venha apresentar algum tipo de problema, as aplicações e serviços estarão disponíveis em outro nó.

### **Balanceamento de Carga (Load Balancing)**

Neste modelo, as requisições e o tráfego de informações são distribuídas entre os diversos nós que executam os mesmos programas. Todos os nós são responsáveis pelo controle de pedidos. Caso algum dos nós do sistema falhe, as requisições são redistribuídas entre os outros nós disponíveis.

Clusters de Balanceamento de Carga são geralmente utilizados em grandes servidores web. Há também a possibilidade de combinar as características do cluster de Alta Disponibilidade com o cluster de Balanceamento de Cargas . A união desses dois modelos garante um sistema com maior disponibilidade e maior estabilidade

### **Processamento Distribuído ou Processamento Paralelo**

Este modelo de cluster é muito utilizado para atividades que exijam muito processamento das informações.

Aumentando a disponibilidade e com maior performance no processamento das aplicações, neste modelo uma grande tarefa pode ser dividida em pequenas outras tarefas que são distribuídas entre os nós. Dessa forma, este modelo de cluster “simula” em partes um supercomputador.

---

Além desses exemplos citados acima, existem várias outras configurações que podem ser implementadas de acordo com as necessidades e os recursos de hardware disponíveis.

Até a próxima!
