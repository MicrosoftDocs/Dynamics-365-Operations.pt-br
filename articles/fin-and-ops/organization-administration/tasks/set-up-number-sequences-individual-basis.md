--- 
title: "Configurar sequências numéricas em uma base individual"
description: "Sequências numéricas são usadas para gerar identificadores exclusivos e legíveis para registros de dados mestres e registros de transações que os exigirem."
author: sericks007
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4e2808e57dc8d137fac892d48e99d7687ff1bf81
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Configurar sequências numéricas em uma base individual

[!include[task guide banner](../../includes/task-guide-banner.md)]

Sequências numéricas são usadas para gerar identificadores exclusivos e legíveis para registros de dados mestres e registros de transações que os exigirem. Um registro de transação ou de dados mestres que exige um identificador é conhecido como referência. Antes de criar novos registros para referência, é necessário configurar uma sequência numérica e associá-la à referência. É possível configurar todas as sequências numéricas necessárias ao mesmo tempo, usando o assistente Configurar sequências de número, ou você pode criar ou modificar sequências de número individuais usando a página Sequências de números.

1. Vá para Administração da organização > Sequências numéricas > Sequências numéricas.
2. Clique em Sequência numérica.
3. No campo Número, selecione campo Código, digite um valor.
4. No campo Nome, digite um valor.
5. Expandir a seção Parâmetros de escopo.
    * Na Guia Rápida Parâmetros de escopo, selecione um escopo para a sequência numérica e selecione os valores do escopo.     O escopo define quais organizações usam a sequência numérica. Além de isso, as sequências numéricas que têm um escopo diferente de Compartilhado podem ter segmentos que correspondem ao escopo. Por exemplo, uma sequência numérica com um escopo Entidade legal pode conter um segmento da entidade legal. Para obter mais informações sobre os escopos, consulte o tópico da ajuda "Visão geral da sequência numérica".  
6. Expandir a seção Segmentos.
    * Na Guia Rápida Segmentos, defina o formato para a sequência numérica adicionando, removendo e reorganizando segmentos.  
    * As sequências numéricas de todos os escopos podem conter segmentos constantes e segmentos alfanuméricos. Os segmentos constantes contêm um conjunto de caracteres alfanuméricos que não são alterados. Use este tipo de segmento para adicionar um hífen ou separadores entre outros segmentos da sequência numérica. Os segmentos alfanuméricos contêm uma combinação de sinais de número (#) e de es-comerciais (&). Esses caracteres representam as letras e os números que aumentam sempre que um número de sequência é usado. Use um sinal numérico (#) para indicar o aumento de números e um e-comercial (&) para indicar o aumento de letras. Por exemplo, o formato #####_2014 cria a sequência 00001_2014, 00002_2014, e assim por diante.     Deve estar presente pelo menos um segmento alfanumérico. Os segmentos de escopo, como empresa ou entidade legal, não são necessários. No entanto, se você não incluir segmentos de escopo no formato, os números da referência selecionada serão geradas pelo escopo.  
7. Expandir a seção Referências.
    * Na Guia Rápida Referências, selecione o tipo de documento ou o registro para atribuir a esta sequência numérica.     Esta etapa é opcional para as sequências numéricas definidas pelos padrões especiais de uso do aplicativo. Nessas situações, um novo número é gerado usando o valor de um código de sequência numérica ou um ID, sem usar uma referência. Um exemplo de padrão especial de uso do aplicativo é uma série de comprovante usada para nomes de diários específicos. Entretanto, não recomendamos que você use esses padrões.  
8. Expanda a seção Geral.
    * Na Guia Rápida Geral, especifique se a sequência numérica é manual e se é contínua ou não contínua. Além disso, insira os números mais baixos e mais altos que podem ser usados na sequência numérica.     Não recomendamos alterar uma sequência numérica não contínua a uma sequência numérica contínua. A sequência numérica não será verdadeiramente contínua. Essa alteração também pode causar violações de chave duplicada no banco de dados. Além disso, as sequências numéricas contínuas têm um efeito maior no desempenho.   
9. Clique em Salvar.


