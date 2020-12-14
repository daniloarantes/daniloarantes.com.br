---
date: "2017-10-12T18:02:42-03:00"
title: "Correção de erro 'failed to register layer' no Docker"
tags: ["Docker", "Linux"]
author: "Danilo Arantes"
---

![Docker](../../imagens/docker.png)

O Docker é uma ferramenta incrível e não é a toa que está conquistando o mercado e crescendo rapidamente. Para mim ainda é uma novidade e sempre que posso estudo para aprender mais.

Em uma das aventuras, ao tentar fazer o **pull** de um container com Evernote, me deparei com a seguinte mensagem de erro:

>"failed to register layer: symlink..."

E eu não conseguia finalizar o processo de forma alguma.

Pesquisando no DuckDuckGo, encontrei uma solução simples que consiste apenas em reiniciar o Docker. Na minha máquina estou rodando Debian 9, então o comando foi o seguinte:

```
systemctl restart docker
```
Simples!
Foi só realizar novamente o pull que finalizou com sucesso e consegui executar o Evernote perfeitamente.
