---
title: Configurar sequências numéricas individualmente
description: Este tópico explica como configurar sequências numéricas individualmente.
author: sericks007
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83ebcf96aa6a5b5c757285be1c5602ac4e8f50fc
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890849"
---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Configurar sequências numéricas individualmente

[!include [banner](../../includes/banner.md)]

Este tópico explica como configurar sequências numéricas individualmente. Sequências numéricas são usadas para gerar identificadores exclusivos e legíveis para registros de dados mestres e registros de transações que os exigirem. Um registro de transação ou de dados mestres que exige um identificador é conhecido como referência. Antes de criar novos registros para referência, é necessário configurar uma sequência numérica e associá-la à referência. É possível configurar todas as sequências numéricas necessárias ao mesmo tempo, usando o assistente **Configurar sequências numéricas**, ou você pode criar ou modificar sequências de número individuais usando a página **Sequências numéricas**.

1. Vá para **Painel de navegação > Módulos > Administração da organização > Sequências numéricas > Sequências numéricas**.
2. Selecionar **Sequência numérica**.
3. No campo **Código de sequência numérica**, digite um valor.
4. No campo **Nome**, digite um valor.
5. Na Guia Rápida **Parâmetros de escopo**, selecione um escopo para a sequência numérica e selecione os valores da lista suspensa. O escopo define quais organizações usam a sequência numérica. Além de isso, as sequências numéricas com um escopo diferente de **Compartilhado** podem ter segmentos que correspondam ao escopo. Por exemplo, uma sequência numérica com um escopo **Entidade legal** pode conter um segmento da entidade legal. Para obter mais informações sobre os escopos, consulte [Visão geral da sequência numérica](../number-sequence-overview.md). 
6. Expanda a seção **Segmentos**.
    - Defina o formato para a sequência numérica adicionando, removendo e reorganizando segmentos.  
    - As sequências numéricas de todos os escopos podem conter *Segmentos constantes* e *Segmentos alfanuméricos*. Os segmentos constantes contêm um conjunto de caracteres alfanuméricos que não são alterados. Use este tipo de segmento para adicionar um hífen ou separadores entre outros segmentos da sequência numérica. Os segmentos alfanuméricos contêm uma combinação de sinais de número (#) e de es-comerciais (&). Esses caracteres representam as letras e os números que aumentam sempre que um número de sequência é usado. Use um sinal numérico (#) para indicar o aumento de números e um e-comercial (&) para indicar o aumento de letras. Por exemplo, o formato `#####_2014` cria a sequência `00001_2014`, `00002_2014` e assim em diante. Deve estar presente pelo menos um segmento alfanumérico. Os segmentos de escopo, como empresa ou entidade legal, não são necessários. No entanto, se você não incluir segmentos de escopo no formato, os números da referência selecionada serão geradas pelo escopo.  
7. Expanda a seção **Referências**. Selecione o tipo de documento ou o registro para atribuir a esta sequência numérica. Esta etapa é opcional para as sequências numéricas definidas pelos padrões especiais de uso do aplicativo. Nessas situações, um novo número é gerado usando o valor de um código de sequência numérica ou um ID, sem usar uma referência. Um exemplo de padrão especial de uso do aplicativo é uma série de comprovante usada para nomes de diários específicos. Entretanto, não recomendamos que você use esses padrões.  
8. Expanda a seção **Geral**. Na Guia Rápida Geral, especifique se a sequência numérica é manual e se é contínua ou não contínua. Além disso, insira os números mais baixos e mais altos que podem ser usados na sequência numérica. Não recomendamos alterar uma sequência numérica não contínua a uma sequência numérica contínua. A sequência numérica não será verdadeiramente contínua. Essa alteração também pode causar violações de chave duplicada no banco de dados. Além disso, as sequências numéricas contínuas têm um efeito maior no desempenho.   
9. Clique em **Salvar**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
