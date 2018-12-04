---
title: Tornar o delimitador do plano de contas exclusivo
description: "No Dynamics 365 for Finance and Operations, você não pode ter o mesmo delimitador para o plano de contas e para os valores de dimensão. Você deve alterar os valores do delimitador após a atualização."
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e197a1b44e038a97b8bf6db692dcc2eef2bc5f7b
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---

# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Tornar o delimitador do plano de contas exclusivo

[!include [banner](../includes/banner.md)]

No Microsoft Dynamics AX 2012, é possível usar o mesmo delimitador para o plano de contas e para os valores de dimensão. No Dynamics 365 for Finance and Operations, você não pode ter o mesmo delimitador para o plano de contas e para os valores de dimensão. Se houver um delimitador duplicado, você poderá alterá-lo após a atualização. 

Este recurso não está disponível no:
- Dynamics 365 for Finance and Operations, versão 8.0
- Dynamics 365 for Finance and Operations, versão 7.1, KB 4094701 – não é possível inserir as dimensões financeiras quando os valores de dimensões contiverem o delimitador de plano de contas
- Dynamics 365 for Finance and Operations, versão 7.2, KB 4094701 – não é possível optar por subprojeto como a dimensão quando o formato do subprojeto contiver o delimitador de dimensão

## <a name="update-delimiter"></a>Atualizar delimitador
Se houver um conflito com o Plano de contas, o delimitador do Plano de contas e o formato da ID de projeto/subprojeto poderá ser alterado. Nenhum outro delimitador de dimensão pode ser alterado. 
- Você poderá alterar o delimitador do plano de contas depois que atualizar o Finance and Operations em **Parâmetros de contabilidade** > **Plano de contas e dimensões** > **Alterar delimitador**. 
- Se o único conflito for com o formato da ID do projeto/subprojeto, você poderá alterar esse valor em **Parâmetros de gerenciamento e contabilidade de projetos** > **Geral** > **Modificar o formato do subprojeto**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Como determinar se o ambiente requer delimitadores atualizados 
Se os delimitadores em seu ambiente atualizado estiverem em conflito, é possível que haja instabilidade ao inserir valores em um controle de entrada segmentada ou em um controle entrada de dimensão. Isso significa que você sempre precisará usar pesquisas ou um menu suspenso ao inserir combinações de conta e dimensão.

