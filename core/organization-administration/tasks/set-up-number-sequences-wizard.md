--- 
title: "Configurar sequências numéricas usando um assistente"
description: "Sequências numéricas são usadas para gerar identificadores exclusivos e legíveis para registros de dados mestres e registros de transações que os exigirem."
author: sericks007
manager: AnnBe
ms.date: 11/10/2016
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
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5fe6e54b4ebcf6cd611af54e7066a3e39d0e677d
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a>Configurar sequências numéricas usando um assistente

[!include[task guide banner](../../includes/task-guide-banner.md)]

Sequências numéricas são usadas para gerar identificadores exclusivos e legíveis para registros de dados mestres e registros de transações que os exigirem. Um registro de transação ou de dados mestres que exige um identificador é conhecido como referência. Antes de criar novos registros para referência, é necessário configurar uma sequência numérica e associá-la à referência. Este processo explica como configurar todas as sequências numéricas necessárias ao mesmo tempo usando um assistente. A empresa de dados demo usada para criar este procedimento é USMF.

1. Vá para Administração da organização > Sequências numéricas > Sequências numéricas.
2. Clique em Gerar.
3. Clique em Avançar.
    * Nessa página, é possível alterar o código de identificação, o valor mais baixo e o valor mais alto. Além disso, é possível indicar se a sequência numérica deverá ser contínua.   
    * Não selecione a opção Contínuo se for necessário alocar antecipadamente os números para a sequência numérica.     Para adicionar um segmento de escopo ao formato de uma sequência numérica, selecione o formato na lista, e então clique em Incluir escopo ao formato.     Para remover um segmento de escopo do formato de uma sequência numérica, selecione o formato na lista, e então clique em Remover escopo do formato.     Para excluir uma sequência numérica da geração automática, selecione a sequência numérica na lista, e então clique em Excluir.  
4. Clique em Avançar.
5. Clique em Finish (Concluir).


