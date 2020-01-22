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
ms.openlocfilehash: fc2e6259a8f9d17dc0f7652f207acfa53da76a8d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898564"
---
# <a name="analytic-reports-are-not-updated"></a><span data-ttu-id="a2d22-103">Relatórios analíticos não são atualizados</span><span class="sxs-lookup"><span data-stu-id="a2d22-103">Analytic reports are not updated</span></span>

<span data-ttu-id="a2d22-104">**Saída**</span><span class="sxs-lookup"><span data-stu-id="a2d22-104">**Issue**</span></span>

<span data-ttu-id="a2d22-105">As alterações de dados de um cliente não aparecem nas guias **Análise** de alguns espaços de trabalho do cliente.</span><span class="sxs-lookup"><span data-stu-id="a2d22-105">A customer's data changes don't appear on the **Analytics** tabs of any of the customer's workspaces.</span></span>

<span data-ttu-id="a2d22-106">**Causa**</span><span class="sxs-lookup"><span data-stu-id="a2d22-106">**Cause**</span></span>

<span data-ttu-id="a2d22-107">Por padrão, os relatórios do Microsoft Power BI são atualizados a cada quatro horas, de acordo com o plano de trabalho em lotes da implantação de medição.</span><span class="sxs-lookup"><span data-stu-id="a2d22-107">By default, Microsoft Power BI reports are refreshed every four hours, according to the schedule of the Deploy measurement batch job.</span></span>

<span data-ttu-id="a2d22-108">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="a2d22-108">**Resolution**</span></span>

<span data-ttu-id="a2d22-109">Esse problema deve ser apenas de hora.</span><span class="sxs-lookup"><span data-stu-id="a2d22-109">This issue might just be a matter of timing.</span></span> <span data-ttu-id="a2d22-110">Siga essas etapas para iniciar o trabalho em lotes para atualizar os espaços de trabalho de análise.</span><span class="sxs-lookup"><span data-stu-id="a2d22-110">Follow these steps to start the batch job and update the analytics workspaces.</span></span>

1. <span data-ttu-id="a2d22-111">Abra a página **Trabalho em lotes** em **Administração do sistema \> Links \> Trabalho em lotes \> Trabalho em lotes**.</span><span class="sxs-lookup"><span data-stu-id="a2d22-111">Open the **Batch jobs** page at **System administration \> Links \> Batch jobs \> Batch jobs**.</span></span> <span data-ttu-id="a2d22-112">Alternativamente, use Pesquisa e insira **Trabalho em lotes**.</span><span class="sxs-lookup"><span data-stu-id="a2d22-112">Alternatively, use Search, and enter **Batch Jobs**.</span></span>
1. <span data-ttu-id="a2d22-113">Localize o trabalho **Implantar medição** na lista.</span><span class="sxs-lookup"><span data-stu-id="a2d22-113">Find the **Deploy measurement** job in the list.</span></span>
1. <span data-ttu-id="a2d22-114">Selecione **Editar** na parte superior da página, e defina a data de início/hora programada para um valor que atualizará a análise para mais perto do tempo atual.</span><span class="sxs-lookup"><span data-stu-id="a2d22-114">Select **Edit** at the top of the page, and set the scheduled start date/time to a value that will refresh the analytics closer to the current time.</span></span>

![Trabalhos em lotes](media/batch-jobs.png)
