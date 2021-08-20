---
title: Configurar fluxos de trabalho de item de linha
description: Este tópico explica como configurar um elemento do fluxo de trabalho de item de linha.
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11a3ff7d8d952bf0599ad9a38f21ffbb9e9dafa651a1bb32830b8fafaf42ecaa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754945"
---
# <a name="configure-line-item-workflows"></a>Configurar fluxos de trabalho de item de linha

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar um elemento do fluxo de trabalho de item de linha.

Para configurar um elemento do fluxo de trabalho de item de linha, no editor de fluxo de trabalho, clique com o botão direito do mouse no elemento **Propriedades** e clique em **Propriedades** para abrir a página. Então use os procedimentos a seguir para configurar as propriedades de elemento do fluxo de trabalho de item de linha.

## <a name="name-the-line-item-workflow-element"></a>Forneça um nome ao elemento do fluxo de trabalho de item de linha.

Siga estas etapas para inserir um nome para o elemento do fluxo de trabalho de item de linha.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. No campo **Nome**, insira um nome exclusivo para o elemento do fluxo de trabalho de item de linha.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Especifique se o mesmo fluxo de trabalho será usado para processar todos os itens de linha.

Siga estas etapas para especificar se o mesmo fluxo de trabalho será usado para processar todos os itens de linha em um documento.

1. No painel esquerdo, clique em **Configurações Básicas**.
2. Se o mesmo fluxo de trabalho processar todas as linhas de item em um documento, clique em **Invocar um único fluxo de trabalho para todos os itens de linha**. Em seguida, selecione o fluxo de trabalho a ser usado para processar os itens de linha.
3. Se um fluxo de trabalho específico processar as linhas de item que atenderem um conjunto específico de condições, clique em **Invocar um fluxo de trabalho para cada item de linha**. Para definir o conjunto de condições, siga estas etapas:

    1. Clique em **Adicionar**.
    2. Selecione a condição na tabela.
    3. Na guia **Nome da condição**, insira um nome para o conjunto de condições que você está configurando.
    4. Clique em **Adicionar condição** para inserir uma condição.
    5. Insira quaisquer condições adicionais necessárias.
    6. Para verificar se o conjunto de condições que você inseriu está configurado corretamente, clique em **Teste**. Na página **Testar condição de fluxo de trabalho**, na área **Validar condição**, selecione um registro e clique em **Teste**. O sistema avaliará o registro para determinar se ele atende às condições definidas. Clique em **OK** ou **Cancelar** para retornar à página **Propriedades**.

    Na guia **Fluxo de trabalho**, selecione o fluxo de trabalho no fluxo de trabalho a ser usado para processar as linhas de item que atenderem o conjunto de condições definidas.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]