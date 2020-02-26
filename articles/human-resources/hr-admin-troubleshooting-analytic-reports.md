---
title: Solucionar problemas de relatórios analíticos
description: Este artigo explica o que fazer se as alterações de dados de um cliente não aparecerem em alguns espaços de trabalho do cliente.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 99d9eb3a16e6470820a2eb0a19c1d50e89bd3d36
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008039"
---
# <a name="troubleshoot-analytic-reports"></a>Solucionar problemas de relatórios analíticos

**Emissão**

As alterações de dados de um cliente não aparecem nas guias **Análise** de alguns espaços de trabalho do cliente.

**Causa**

Por padrão, os relatórios do Microsoft Power BI são atualizados a cada quatro horas, de acordo com o plano de trabalho em lotes da implantação de medição.

**Resolução**

Esse problema deve ser apenas de hora. Siga essas etapas para iniciar o trabalho em lotes para atualizar os espaços de trabalho de análise.

1. Abra a página **Trabalho em lotes** em **Administração do sistema \> Links \> Trabalho em lotes \> Trabalho em lotes**. Alternativamente, use Pesquisa e insira **Trabalho em lotes**.
1. Localize o trabalho **Implantar medição** na lista.
1. Selecione **Editar** na parte superior da página, e defina a data de início/hora programada para um valor que atualizará a análise para mais perto do tempo atual.

![Trabalhos em lotes](media/batch-jobs.png)
