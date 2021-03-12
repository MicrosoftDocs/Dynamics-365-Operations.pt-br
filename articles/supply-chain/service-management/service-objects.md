---
title: Visão geral de objetos de serviço
description: Objetos de serviço são os ativos e os produtos de um cliente para o qual você pode executar um serviço.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1e0a40d351150ce432164438cd9680cf80792e1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974301"
---
# <a name="service-objects-overview"></a>Visão geral de objetos de serviço

[!include [banner](../includes/banner.md)]

Objetos de serviço são os ativos e os produtos de um cliente para o qual você pode executar um serviço. Dependendo do tipo de serviço fornecido, os objetos podem ser tangíveis ou intangíveis:

-  Exemplos de objetos tangíveis são uma máquina ou um edifício, nos quais é possível executar uma tarefa de serviço física.

    Um objeto de serviço concreto também pode ser um item de estoque que você cria no formulário Detalhes do produto liberado. Dependendo do grupo de dimensões de estoque associado ao item, é possível criar um objeto de serviço com detalhes que incluem o número de série do item. Isso é útil quando você deve acompanhar o item exato representado pelo objeto de serviço.

    Um objeto de serviço concreto também pode ser um item que não esteja diretamente relacionado à produção direta ou à cadeia de fornecedores de uma empresa. Por exemplo, um kit de ferramentas que é usado para reparos em uma ordem de serviço pode ser um objeto de serviço que ainda não foi incluído no estoque. Nesse caso, você não o registra como um item de estoque.

-  Objetos intangíveis são itens abstratos, como um conjunto de contas ou um documento legal, nos quais você pode executar uma tarefa de serviço.

## <a name="example-of-an-intangible-service-object"></a>Exemplo de um objeto de serviço intangível

A empresa A mantém os registros financeiros de várias pequenas empresas. Um dos clientes da Empresa A é a equipe de futebol local, para a qual a Empresa A faz a escrituração contábil semanal e a auditoria anual das contas do clube. Essas contas são configuradas no formulário Objetos de serviço e são especificadas como objeto no contrato de serviço. Há duas linhas de contrato de serviço para o objeto. A linha 1 é a escrituração contábil semanal com um intervalo semanal atribuído à linha, e a linha 2 é a auditoria anual com um intervalo anual atribuído a ela.

## <a name="related-topics"></a>Tópicos relacionados

[Criar objetos de serviço](create-service-objects.md)

