---
title: Configurar e executar trabalho para calcular declarações
description: Este procedimento orienta como configurar e executar trabalhos em lotes recorrentes para criar e calcular demonstrativos para uma loja ou grupo de lojas selecionado.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8366bfff16bac8ef8f7b15cb97417d474b52f59c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232752"
---
# <a name="configure-and-run-job-to-calculate-statements"></a><span data-ttu-id="c98b4-103">Configurar e executar trabalho para calcular declarações</span><span class="sxs-lookup"><span data-stu-id="c98b4-103">Configure and run job to calculate statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c98b4-104">Este procedimento orienta como configurar e executar trabalhos em lotes recorrentes para criar e calcular demonstrativos para uma loja ou grupo de lojas selecionado.</span><span class="sxs-lookup"><span data-stu-id="c98b4-104">This procedure walks through configuring and running recurrent batch jobs to create and calculate statements for a selected store or group of stores.</span></span> <span data-ttu-id="c98b4-105">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="c98b4-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="c98b4-106">Vá para Todos os espaços de trabalho > Finanças da loja.</span><span class="sxs-lookup"><span data-stu-id="c98b4-106">Go to All workspaces > Store financials.</span></span>
2. <span data-ttu-id="c98b4-107">Clique em Calcular demonstrativos.</span><span class="sxs-lookup"><span data-stu-id="c98b4-107">Click Calculate statements.</span></span>
    * <span data-ttu-id="c98b4-108">Selecione uma loja específica ou um nó se você deseja criar trabalho em lotes para um grupo de lojas.</span><span class="sxs-lookup"><span data-stu-id="c98b4-108">Select either a specific store, or a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="c98b4-109">Clique na seta para adicionar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="c98b4-109">Click the arrow to add your selection.</span></span>  
3. <span data-ttu-id="c98b4-110">Clique na guia Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c98b4-110">Click the Run in the background tab.</span></span>
4. <span data-ttu-id="c98b4-111">Em Processamento em lotes, selecione 'Sim'.</span><span class="sxs-lookup"><span data-stu-id="c98b4-111">Under Batch processing, select 'Yes'.</span></span>
5. <span data-ttu-id="c98b4-112">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="c98b4-112">Click Recurrence.</span></span>
6. <span data-ttu-id="c98b4-113">No campo Data de início, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="c98b4-113">In the Start date field, enter a date.</span></span>
7. <span data-ttu-id="c98b4-114">No campo Hora de início, insira um horário.</span><span class="sxs-lookup"><span data-stu-id="c98b4-114">In the Start time field, enter a time.</span></span>
8. <span data-ttu-id="c98b4-115">Selecione a opção Nenhuma data de término.</span><span class="sxs-lookup"><span data-stu-id="c98b4-115">Select the No end date option.</span></span>
9. <span data-ttu-id="c98b4-116">No campo Unidade padrão, insira 'Dias'.</span><span class="sxs-lookup"><span data-stu-id="c98b4-116">In the PatternUnit field, enter 'Days'.</span></span>
10. <span data-ttu-id="c98b4-117">No campo Por, insira um número.</span><span class="sxs-lookup"><span data-stu-id="c98b4-117">In the Per field, enter a number.</span></span>
11. <span data-ttu-id="c98b4-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c98b4-118">Click OK.</span></span>
12. <span data-ttu-id="c98b4-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c98b4-119">Click OK.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]