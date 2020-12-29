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
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4417315"
---
# <a name="troubleshoot-analytic-reports"></a><span data-ttu-id="056db-103">Solucionar problemas de relatórios analíticos</span><span class="sxs-lookup"><span data-stu-id="056db-103">Troubleshoot analytic reports</span></span>

<span data-ttu-id="056db-104">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="056db-104">**Issue**</span></span>

<span data-ttu-id="056db-105">As alterações de dados de um cliente não aparecem nas guias **Análise** de alguns espaços de trabalho do cliente.</span><span class="sxs-lookup"><span data-stu-id="056db-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="056db-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="056db-106">**Cause**</span></span>

<span data-ttu-id="056db-107">Por padrão, os relatórios do Microsoft Power BI são atualizados a cada quatro horas, de acordo com o plano de trabalho em lotes da implantação de medição.</span><span class="sxs-lookup"><span data-stu-id="056db-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="056db-108">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="056db-108">**Resolution**</span></span>

<span data-ttu-id="056db-109">Esse problema deve ser apenas de hora.</span><span class="sxs-lookup"><span data-stu-id="056db-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="056db-110">Siga essas etapas para iniciar o trabalho em lotes para atualizar os espaços de trabalho de análise.</span><span class="sxs-lookup"><span data-stu-id="056db-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="056db-111">Abra a página **Trabalho em lotes** em **Administração do sistema \> Links \> Trabalho em lotes \> Trabalho em lotes**.</span><span class="sxs-lookup"><span data-stu-id="056db-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="056db-112">Alternativamente, use Pesquisa e insira **Trabalho em lotes**.</span><span class="sxs-lookup"><span data-stu-id="056db-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="056db-113">Localize o trabalho **Implantar medição** na lista.</span><span class="sxs-lookup"><span data-stu-id="056db-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="056db-114">Selecione **Editar** na parte superior da página, e defina a data de início/hora programada para um valor que atualizará a análise para mais perto do tempo atual.</span><span class="sxs-lookup"><span data-stu-id="056db-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Trabalhos em lotes](media/batch-jobs.png)
