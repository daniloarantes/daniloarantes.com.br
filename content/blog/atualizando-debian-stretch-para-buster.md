---
description: Atualizando Debian Stretch para Buster
title: "Atualizando Debian Stretch para Buster"
date: "2017-10-23T17:00:00-03:00"
tags: ["Linux"]
section: post
draft: false
author: "Danilo Arantes"
---

Este final de semana fiz a atualização do Debian Stretch que estava rodando no meu notebook para a versão testing, Debian Buster.

Após realizar backup dos dados importantes, iniciei o processo de atualização que consiste em alterar os repositórios do sistema para a versão Buster.

Para isso, utilizei o comando **sed** para modificar a versão dos repositórios no arquivo **/etc/apt/sources.list** :

```bash
 sed -i 's/Stretch/Buster/g' /etc/apt/sources.list
```

**Atenção:** você pode ter algum repositório que necessite permanecer na versão Stretch. Se executou o comando acima, acesse o arquivo sources.list com o editor de textos e modifique o que for necessário.

O próximo passo é atualizar os repositórios:

```bash
 apt update
```

Será exibido que há atualizações para o sistema. Então, faça o upgrade com o comando:

```bash
 apt dist-upgrade
```

Após o upgrade, se não ocorreu nenhum erro, reinicie o sistema e está finalizado o processo e você já estará com a versão Testing (Buster).
