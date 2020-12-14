---
date: "2018-03-06T11:02:07-03:00"
title: "Desabilitando o Bluetooth na inicialização do Debian"
tags: ["Linux"]
author: "Danilo Arantes"
---

Geralmente os notebooks vem com bluetooth, que por um lado é bom mas por outro não. Manter o bluetooth ligado direto faz com que consuma muita bateria e não é isso o que queremos quando o assunto é notebook.

**Para sistemas com SYSTEMD**

Se o seu sistema estiver utilizando SYSTEMD, o procedimento pode ser facilmente realizado seguindo as etapas abaixo:

1º - Verificar o status do Bluetooth

```bash
systemctl status bluetooth
```
Serão retornadas mensagens sobre o status de funcionamento do serviço.

2º - Parar o serviço

```bash
systemctl stop bluetooth
```

3º - Desabilitar o serviço
```bash
systemctl disable bluetooth
```

Após esse procedimento o bluetooth estará desabilitado em seu sistema. Para habilitar novamente, substitua o **disable** do passo 3 para **enable** e substitua o **stop** so passo 2 para **start**.

**Para sistemas sem SYSTEMD, siga os passos abaixo:**

Uma maneira prática para desabilitar o bluetooth na inicialização do sistema é inserir uma simples linha no arquivo **/etc/rc.local.**


**Como fazer:**

1º - Instalar o pacote rfkill

```bash
apt-get install rfkill
```

2º - Inserir comando dentro do arquivo **/etc/rc.local**

Utilizando seu editor preferido, abra o arquivo:

```bash
vi /etc/rc.local
```

3º - Dentro do **rc.local **insira a linha abaixo:

```bash
rfkill block bluetooth
```

Salve e saia do arquivo.

Pronto! Agora basta reiniciar o computador e verificar se funcionou corretamente.


### **Referência**

[Blog Pseudomorph](http://pseudomorph.wordpress.com/2012/01/15/disabling-bluetooth-as-default-in-debian-based-distros/)
<br/>
<br/>
