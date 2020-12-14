---
title: "Criando Arquivamentos com CPIO"
date: "2017-06-15T17:41:57-03:00"
draft: false
author: "Danilo Arantes"
tags: ["Linux"]
---

O comando CPIO utiliza uma lista de arquivos da saída padrão para criar um arquivamento, enviando estes para a saída padrão.

Vale lembrar que o CPIO apenas criar arquivamentos e não os compacta.

Com este comando, várias atividades são facilitadas, como por exemplo:

 - Copiar arquivos para um arquivamento;
 - Extrair arquivos de um arquivamento;
 - Copiar arquivos para outra estrutura de diretórios.

Alguns parâmetros utilizados com o CPIO:

 - **-i** - Extrair backup
 - **-o** - Cria backup
 - **-t** - Mostra o conteúdo do backup
 - **-F** - Especifica o arquivo de Backup
 - **-d** - Cria diretórios se necessário
 - **-v** - Modo Verboso – Mostra na tela as ações
 - **-p** - Ativa o modo de cópia

## **Criando cenário para teste:**
Execute os comandos abaixo para criar o cenário que será utilizado para teste:

```bash
mkdir Exemplo
cd Exemplo/
touch arquivo1 arquivo2 arquivo3
```

## **Criando Arquivamentos**

Para criar um arquivamento com o CPIO, utilize os parâmetros **-ov** :

```bash
cpio -ov > ../arquivo.cpio
```

Se você estiver fora do diretório Exemplo, faça o seguinte:

```bash
find Exemplo/ -name 'arq*' | cpio -ov > arquivo2.cpio
```

No exemplo acima estamos criando o arquivo.cpio e arquivo2.cpio contendo arquivo1 arquivo2 arquivo3.

## **Extraindo Arquivamentos**

Para extrair o conteúdo de um arquivamento, utilize os parâmetros **-idv** :

```bash
mkdir Exemplo2
cd Exemplo2
cpio -idv < ../arquivo.cpio
```

No exemplo acima, extraímos o conteúdo de arquivo.cpio dentro do diretório Exemplo2.

**OBS: O CPIO só extrairá os arquivos caso os arquivos de destino sejam mais velhos dos que estão no arquivamento.**

## **Visualizando o conteúdo de um arquivamentos**

É possível exibir na tela o conteúdo de um arquivamento sem extrair qualquer arquivo, como mostra o exemplo abaixo:

```bash
cpio -t < arquivo.cpio
```

## **Extraindo um arquivo específico de um arquivamentos**

Caso haja a necessidade de extrair um arquivo específico de um arquivamento, utilize o parâmetro -iF :

```bash
cpio -iF arquivo.cpio arquivo1
```

## **Criando arquivos .tar com CPIO**

Com o CPIO também é possível criar arquivos com a extensão .tar:

```bash
cd Exemplo/
ls | cpio -ov -H tar -F ../arquivo3.tar
```

## **Extraindo arquivos .tar com CPIO**

Para extrair um arquivamento .tar, faça como o exemplo abaixo:

```bash
cpio -idv -F arquivo3.tar
```

## **Visualizando o conteúdo de arquivos .tar com CPIO**

Também é possível apenas exibir na tela o conteúdo de um arquivo .tar:

```bash
cpio -it -F arquivo3.tar
```

## **Fazendo cópias de diretórios e subdiretórios com CPIO**

Uma das possibilidades do CPIO é a cópia de estruturas de diretórios para outra localidade:

```bash
find . -depth | cpio -pmdv /root/arquivos
```

### **Referência:**
[The Geek Stuff](http://www.thegeekstuff.com/2010/08/cpio-utility/) (acessado em 17/11/2015 às 20:00)
