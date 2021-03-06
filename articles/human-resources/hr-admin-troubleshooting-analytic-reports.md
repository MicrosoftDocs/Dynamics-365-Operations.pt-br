---
title: Solucionar problemas de relatórios analíticos
description: Este artigo explica o que fazer se as alterações de dados de um cliente não aparecerem em alguns espaços de trabalho do cliente.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8dab12213e9730e72aede70c5b5d1368ef77664e
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053530"
---
# <a name="troubleshoot-analytic-reports"></a>Solucionar problemas de relatórios analíticos

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]