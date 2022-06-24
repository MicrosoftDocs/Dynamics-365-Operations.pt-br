---
title: Solucionar problemas de relatórios analíticos
description: Este artigo explica como diagnosticar e solucionar problemas, se as alterações de dados de um cliente não aparecerem em alguns espaços de trabalho do cliente.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1e6ae8931679feb2103172eb1a21649734acd995
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902217"
---
# <a name="troubleshoot-analytic-reports"></a>Solucionar problemas de relatórios analíticos


[!INCLUDE [PEAP](../includes/peap-2.md)]

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

![Trabalhos em Lotes.](media/batch-jobs.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
