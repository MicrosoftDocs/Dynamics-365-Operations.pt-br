---
title: Ordens de venda do projeto
description: Este tópico explica como criar ordens de venda baseadas em projeto para projetos por tempo e material.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: 1d54c98a08dc7cccb5cafbbe401d0ce25a276c25
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/12/2019
ms.locfileid: "976628"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a>Ordens de venda de projeto para projetos por tempo e material

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Este tópico descreve como criar uma ordem de venda para um projeto. As ordens de venda só podem ser criadas para projetos do tipo **tempo e material**.

Se um projeto por tempo e material tiver várias fontes de financiamento em seu contrato, você deverá habilitar o parâmetro **Permitir ordens de venda para projetos com várias fontes de financiamento** na página **Parâmetros de gerenciamento e contabilidade de projetos**. 

> [!NOTE]
> - O suporte para ordens de venda de projeto com várias fontes de financiamento está disponível a partir da versão 10.0.2 e posterior do aplicativo.
> - O parâmetro para habilitar o suporte para ordens de venda de projeto com várias fontes de financiamento será removido na onda de lançamentos de abril de 2020, após a qual essa funcionalidade será habilitada sempre.

Você pode criar ordens de venda baseadas em projeto de duas maneiras:

- Acesse o projeto. No Painel de Ação, selecione **Gerenciar > Tarefas do item > Ordem de venda**. As informações sobre o projeto terão como padrão a ordem de venda do projeto. Se o contrato de projeto tiver mais de uma fonte de financiamento, você precisará selecionar a fonte de financiamento para definir o cliente para a ordem de venda. Se o projeto tiver apenas uma fonte de financiamento, o cliente será definido de forma automática.
- Vá para a página de listagem **Todas as ordens de venda** e crie uma ordem de venda. Você precisará selecionar o projeto para a ordem de venda. Depois que o projeto for selecionado, o cliente será definido com base na fonte de financiamento ou você terá de selecionar a fonte de financiamento se o contrato do projeto tiver várias.

