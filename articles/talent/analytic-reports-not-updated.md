---
title: Relatórios analíticos não são atualizados
description: Este tópico explica o que fazer se as alterações de dados de um cliente não aparecerem em alguns espaços de trabalho do cliente.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d6a6487b50908093f876237ffef840a3144b3fe6
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "857444"
---
# <a name="analytic-reports-are-not-updated"></a>Relatórios analíticos não são atualizados

[!include [banner](includes/banner.md)]

**Saída**

As alterações de dados de um cliente não aparecem nas guias **Análise** de alguns espaços de trabalho do cliente.

**Causa**

Por padrão, os relatórios do Microsoft Power BI são atualizados a cada quatro horas, de acordo com o plano de trabalho em lotes da implantação de medição.

**Resolução**

Esse problema deve ser apenas de hora. Siga essas etapas para iniciar o trabalho em lotes para atualizar os espaços de trabalho de análise.

1. Abra a página **Trabalho em lotes** em **Administração do sistema \> Links \> Trabalho em lotes \> Trabalho em lotes**. Alternativamente, use Pesquisa e insira **Trabalho em lotes**.
1. Localize o trabalho **Implantar medição** na lista.
1. Selecione **Editar** na parte superior da página, e defina a data de início/hora programada para um valor que atualizará a análise para mais perto do tempo atual.

![Trabalhos em lotes](media/batch-jobs.png)
