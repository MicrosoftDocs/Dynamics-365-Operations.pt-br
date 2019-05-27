---
title: Lançamento de vendas e pagamentos online
description: Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13839bbe6ca03f3cfc7036fce87477bf7d5af2a7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550199"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="67f61-103">Lançamento de vendas e pagamentos online</span><span class="sxs-lookup"><span data-stu-id="67f61-103">Posting of online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="67f61-104">Este procedimento orienta como configurar e executar um trabalho em lotes periódico para criar ordens de venda e pagamentos para transações de lojas online.</span><span class="sxs-lookup"><span data-stu-id="67f61-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="67f61-105">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="67f61-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="67f61-106">Vá para Todos os espaços de trabalho > Finanças da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="67f61-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="67f61-107">Clique em Sincronizar ordens.</span><span class="sxs-lookup"><span data-stu-id="67f61-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="67f61-108">No campo Hierarquia da organização, selecione 'Lojas de varejo por região'.</span><span class="sxs-lookup"><span data-stu-id="67f61-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="67f61-109">Selecione uma loja online específica ou selecione um nó se você deseja criar o trabalho em lotes para um grupo de lojas.</span><span class="sxs-lookup"><span data-stu-id="67f61-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="67f61-110">Clique na seta para adicionar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="67f61-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="67f61-111">Clique na guia Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="67f61-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="67f61-112">Marque ou desmarque a caixa de seleção Processamento em lotes.</span><span class="sxs-lookup"><span data-stu-id="67f61-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="67f61-113">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="67f61-113">Click Recurrence.</span></span>
7. <span data-ttu-id="67f61-114">Selecione a opção Nenhuma data de término.</span><span class="sxs-lookup"><span data-stu-id="67f61-114">Select the No end date option.</span></span>
8. <span data-ttu-id="67f61-115">No campo Contagem, insira um número.</span><span class="sxs-lookup"><span data-stu-id="67f61-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="67f61-116">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="67f61-116">Click OK.</span></span>
10. <span data-ttu-id="67f61-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="67f61-117">Click OK.</span></span>

