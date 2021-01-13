---
title: "Gerenciamento de RAID via software no Debian | Aula 03"
date: 2021-01-13T20:06:45-03:00
tags: []
draft: false
---

Na segunda etapa da instalação do nosso servidor Debian, realizamos a configuração dos discos como RAID 1.

Nesta aula vou demonstrar para vocês como realizar os testes de funcionamento do RAID via software, procedimentos necessários para gerenciar e manter este serviço funcionando.

## Comandos para gerenciamento do RAID via software

Mostrarei somente alguns comandos necessários para este estudo. Sugiro que façam a leitura do manual do comando mdadm (no terminal digite man mdadm) para ver todas as possibilidades.

**Verificar detalhes sobre um dispositivo RAID**

```bash
mdadm --detail /dev/md0
```

**Remover dispositivo**

```bash
mdadm --manage /dev/md0 --fail /dev/sda1
```

**Remover um disco do RAID**

```bash
mdadm --manage /dev/md0 --remove /dev/sda1
```

**Adicionar disco ao RAID**

```bash
mdadm --manage /dev/md0 --add /dev/sda1
```

Assista a aula abaixo e veja esses comandos em funcionamento.

Bons estudos!

{{< youtube id="dVa8_1j3D74" >}}
