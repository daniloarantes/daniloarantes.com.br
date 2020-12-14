---
description: ""
date: "2017-06-15T19:32:42-03:00"
title: "Configurando o Automount (Autofs)"
categories: []
tags: ["Linux"]
author: "Danilo Arantes"
---

A montagem automática é utilizada como um sistema de montagem sob demanda.

Imagine que toda vez que um usuário acessar um diretório específico, o compartilhamento remoto seja montado, disponibilizando acesso a um servidor de arquivos, por exemplo.

Inicialmente, instale o pacote autofs:

```bash
apt-get install autofs
```

Principal arquivo de configuração: **/etc/auto.master**

## **Configurando automount:**

Edite o arquivo /etc/auto.master

```bash
vim /etc/auto.master
```

Dentro desse arquivo, verifique se a linha +dir está descomentada. Caso essa linha não exista, retire o comentário da linha Include.

Essas linhas apontam para um diretório onde ficarão os arquivos de configuração (/etc/auto.master.d).

Crie o diretório _/etc/auto.master.d_

Dentro de _/etc/auto.master.d_ crie o arquivo _montagem.autofs_ e dentro desse arquivo coloque o seguinte conteúdo:

```bash
/Arquivos /etc/auto.montagem &#8211;timeout=10
```

Agora crie o arquivo _/etc/auto.montagem_ com o conteúdo abaixo:

```bash
montagem -fstype=xfs,rw :/dev/sdb1
```

**&#8220;montagem&#8221;** é o ponto de montagem para a partição **/dev/sdb1** que possui sistema de arquivos **XFS** e será permitido RW &#8211; Leitura e Escrita.

O diretório &#8220;montagem&#8221; será montado dentro do diretório &#8220;/Arquivos&#8221;, portanto, crie esse diretório:

```bash
mkdir /Arquivos
```

Reinicie o Autofs:

```bash
service autofs restart
```

# **Testando**

Execute o comando abaixo para verificar os pontos de montagem:

```bash
df -h
```

Acesse o diretório **/Arquivos/montagem**

```bash
cd /Arquivos/montagem
```

Ao executar o comando abaixo, deverá ser exibida a partição **/dev/sdb1** apontando para o diretório _montagem_.

```bash
df -h
```

### **Referência**
[Autofs - Basic Configuration](http://www.youtube.com/watch?v=sRqre0ekfMA)
