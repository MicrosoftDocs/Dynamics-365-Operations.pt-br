---
title: "Relatórios analíticos não são atualizados"
description: "Este tópico explica o que fazer se as alterações de dados de um cliente não aparecerem em alguns espaços de trabalho do cliente."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 46f426a4b0012e87b4d9d21032870ac7fc33c4ae
ms.contentlocale: pt-br
ms.lasthandoff: 12/04/2018

---

# <a name="analytic-reports-are-not-updated"></a>Relatórios analíticos não são atualizados

[!include [banner](includes/banner.md)]

**Saída**

As alterações de dados de um cliente não aparecem nas guias **Análise** de alguns espaços de trabalho do cliente.

**Causa**

Por padrão, os relatórios do Microsoft Power BI são atualizados a cada quatro horas, de acordo com o plano de trabalho em lote da implantação de medição.

**Resolução**

Esse problema deve ser apenas de hora. Siga essas etapas para iniciar o trabalho em lotes para atualizar os espaços de trabalho de análise.

1. Abra a página **Trabalho em lotes** em **Administração do sistema \> Links \> Trabalho em lotes \> Trabalho em lotes**. Alternativamente, use Pesquisa e insira **Trabalho em lotes**.
1. Localize o trabalho **Implantar medição** na lista.
1. Selecione **Editar** na parte superior da página, e defina a data de início/hora programada para um valor que atualizará a análise para mais perto do tempo atual.

![Trabalhos em lotes](media/batch-jobs.png)

