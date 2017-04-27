---
title: Configurar um fluxo de trabalho de item de linha
description: "Este tópico explica como configurar um elemento do fluxo de trabalho de item de linha."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 6c2b2c863d0783bd436db57d9fd3c7c5aa8dba5c
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-line-item-workflow"></a>Configurar um fluxo de trabalho de item de linha

[!include[banner](../includes/banner.md)]


Este tópico explica como configurar um elemento do fluxo de trabalho de item de linha.

Para configurar um elemento do fluxo de trabalho de item de linha, no editor de fluxo de trabalho, clique com o botão direito do mouse no elemento **Propriedades** e clique em **Propriedades** para abrir a página. Então use os procedimentos a seguir para configurar as propriedades de elemento do fluxo de trabalho de item de linha.

## <a name="name-the-lineitem-workflow-element"></a>Forneça um nome ao elemento do fluxo de trabalho de item de linha.
Siga estas etapas para inserir um nome para o elemento do fluxo de trabalho de item de linha.

1.  No painel esquerdo, clique em **Configurações Básicas**.
2.  No campo **Nome**, insira um nome exclusivo para o elemento do fluxo de trabalho de item de linha.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Especifique se o mesmo fluxo de trabalho será usado para processar todos os itens de linha.
Siga estas etapas para especificar se o mesmo fluxo de trabalho será usado para processar todos os itens de linha em um documento.

1.  No painel esquerdo, clique em **Configurações Básicas**.
2.  Se o mesmo fluxo de trabalho processar todas as linhas de item em um documento, clique em **Invocar um único fluxo de trabalho para todos os itens de linha**. Em seguida, selecione o fluxo de trabalho a ser usado para processar os itens de linha.
3.  Se um fluxo de trabalho específico processar as linhas de item que atenderem um conjunto específico de condições, clique em **Invocar um fluxo de trabalho para cada item de linha**. Para definir o conjunto de condições, siga estas etapas:
    1.  Clique em **Adicionar**.
    2.  Selecione a condição na tabela.
    3.  Na guia **Nome da condição**, insira um nome para o conjunto de condições que você está configurando.
    4.  Clique em **Adicionar condição** para inserir uma condição.
    5.  Insira quaisquer condições adicionais necessárias.
    6.  Para verificar se o conjunto de condições que você inseriu está configurado corretamente, clique em **Teste**. Na página **Testar condição de fluxo de trabalho**, na área **Validar condição**, selecione um registro e clique em **Teste**. O sistema avaliará o registro para determinar se ele atende às condições definidas. Clique em **OK** ou **Cancelar** para retornar à página **Propriedades**.

    Na guia **Fluxo de trabalho**, selecione o fluxo de trabalho no fluxo de trabalho a ser usado para processar as linhas de item que atenderem o conjunto de condições definidas.





