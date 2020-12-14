---
date: "2017-07-05T11:06:12-03:00"
title: "Tipos de arquivos no Linux"
tags: ["Linux"]
author: "Danilo Arantes"
---

No linux, um arquivo pode se subdividir em um dos seguinte stipos:

 - Arquivos Comuns
 - Diretórios
 - Links
 - Device Files
 - Sockets
 - Pipes

Ok, mas o que é cada um desses tipos? Abaixo segue uma breve explicação sobre eles:
<!--more-->

**Arquivos Comuns:** Este tipo de arquivos inclui arquivos de texto ASCII e não ASCII, arquivos de texto de comando também conhecidos como shell scripts e arquivos binários executáveis.

**Diretórios:** São arquivos que contém os nomes de arquivos que estão armazenados ou organizados como um grupo. O agrupamento é arbitrário; você pode escolher a combinação desejada. Também pode alterar o agrupamento a qualquer momento.

**Links:** É um arquivo que faz referência a outro arquivo ou diretório dentro do sistema dearquivos. Isso permite a um arquivo ou diretório estar em dois ou mais lugares ao mesmo tempo, na sua localização original e no lugar referenciado pelo arquivo de link.

Os arquivos de link podem ser de dois tipos: Diretos (Hard Links) ou Simbólicos (Soft Links). Os links diretos criam novos nomes para um arquivo, associando dois ou mais nomes de arquivo a um mesmo inode, e não podem ser visualizados. Os links simbólicos são arquivos que fazem referência ao arquivo original, contendo o caminho completo da arvore de diretórios até este e podem ser visualizados com o comando _ls -F_ ou _ls -l_. Ambos os tipos de links são criados pelo comando _ln_.

**Device Files (arquivos de dispositivos):** São arquivos utilizados para representar dispositivos de hardware do computador. No UNIX e também no Linux tudo é um arquivo, seja um conjunto de dados, seja um arquivo de dispositivo representando um periférico do computador ( como um HD, um CD, drive, impressora, etc) ou o kernel do sistema operacional em si. Por exemplo: _/dev/hda, /dev/hdc, /dev/fd0._. Os arquivos de dispositivo podem ser de dois tipos: de caractere ou bloco. Os dispositivos de caractere são acessados sequencialmente, um byte por vez; uma porta paralela ou serial é um dispositivo de caractere. Os dispositivos de bloco são acessados em bloco de bytes (1024 bytes por acesso); um disco rígido é um dispositivo de bloco.

**Sockets:** São arquivos utilizados para comunicação entre processos, até mesmo para processos rodando em diferentes máquinas conectadas a uma rede de computadores.

**Pipes:** São arquivos também utilizados para intercomunicação entre processos e residem também sob o diretório _/dev._

**Referência:**
Linux -  Guia do Administrador do Sistema do autor Rubem E. Ferreira (2ªEdição)
