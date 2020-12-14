---
date: "2017-06-27T15:13:00-03:00"
title: "Compiladores e Interpretadores"
author: "Danilo Arantes"
tags: ["Ciência da Computação"]
Description: "A maneira de se comunicar com um computador chama-se programa e a única linguagem que o computador entende chama-se linguagem de máquina. Portanto todos os programas que se comunicam com a máquina devem estar em linguagem de máquina."
---

A maneira de se comunicar com um computador chama-se programa e a única linguagem que o computador entende chama-se _linguagem de máquina_. Portanto todos os programas que se comunicam com a máquina devem estar em linguagem de máquina.

A forma como os programas são traduzidos para a linguagem de máquina classifica-os em duas categorias:

- Interpretados
- Compilados

Os programas que fazem estas traduções são chamados _interpretadores_ e _Compiladores_.

### **INTERPRETADORES**

Um interpretador lê a primeira instrução do programa, faz uma consistência de sua sintaxe e se não houver erro converte-a para linguagem de máquina para finalmente executá-la. Segue, então, para a próxima instrução, repetindo o processo até que a última instrução seja executada ou a consistência aponte algum erro.

O interpretador precisa estar presente todas as vezes que vamos executar o nosso programa e o trabalho de checagem da sintaxe e tradução deverá ser repetido. Se uma parte donorograma necessita ser executada muitas vezes, o processo é feito o mesmo número de vezes.

### **COMPILADORES**

Um interpretador lê a primeira instrução do programa, faz uma consistência de sua sintaxe e se não houver erro converte-a para linguagem de máquina e, em vez de executá-la, segue para a próxima instrução repetindo o processo até o processo até que a última instrução seja atingida ou a consistência aponte algum erro.

Se nao houver erros, o compilador gera um programa em disco com o sufixo **.obj** com as instruções já traduzidas. Este programa não pode ser executado até que sejam agregadas a ele rotinas em linguagem de máquina que lhe permitirão a sua execução Este trabalho é feito por um programa chamado _linkeditor_ que, além de juntar as rotinas necessárias ao programa **.obj**, cria um produto final em disco com o sufixo **.exe** que pode ser executado diretamente do sistema operacional.

Com isto a velocidade de execução do programa chega a ser 15 a 20 vezes mais rápida do que quando o programa é interpretado.

<br /><br />
**Referência:** Treinamento em Linguagem C: módulo 1 e 2 da autora Victorine Viviane Mizrahi.
