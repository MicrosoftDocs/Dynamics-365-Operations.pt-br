--- 
title: "Configurações de parâmetro para obter demonstrativos de varejo"
description: "Este procedimento demonstra configurações dos parâmetros de varejo que afetam como as instruções de varejo foram criadas e lançadas."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 1322c5beaa2455c0a3f70bb5e28af55ac110eaf3
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="parameter-configurations-for-retail-statements"></a><span data-ttu-id="5019f-103">Configurações de parâmetro para obter demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="5019f-103">Parameter configurations for Retail statements</span></span>

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5019f-104">Este procedimento demonstra configurações dos parâmetros de varejo que afetam como as instruções de varejo foram criadas e lançadas.</span><span class="sxs-lookup"><span data-stu-id="5019f-104">This procedure demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="5019f-105">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="5019f-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="5019f-106">Vá para Varejo e comércio > Configuração da sede > Parâmetros > Parâmetros de varejo.</span><span class="sxs-lookup"><span data-stu-id="5019f-106">Go to Retail and commerce > Headquarters setup  > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="5019f-107">Clique na guia Lançamento.</span><span class="sxs-lookup"><span data-stu-id="5019f-107">Click the Posting tab.</span></span>
    * <span data-ttu-id="5019f-108">Selecione “Sim” se quiser lançar especificamente os valores de desconto periódico.</span><span class="sxs-lookup"><span data-stu-id="5019f-108">Select "Yes" if you want to post the periodic discount amounts specifically.</span></span>  
    * <span data-ttu-id="5019f-109">Selecione "Padrão" para usar contas padrão, ou selecione “Periódico”, se você quiser definir qual conta usar para cada desconto periódico.</span><span class="sxs-lookup"><span data-stu-id="5019f-109">Select "Standard" to use default accounts, or select "Periodic" if you want to define which account to use for each periodic discount.</span></span>  
    * <span data-ttu-id="5019f-110">Selecione "Resumo" se as linhas de estoque tiverem que ser agregadas, sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="5019f-110">Select "Summary" if inventory lines should get aggregated whenever possible.</span></span>  
    * <span data-ttu-id="5019f-111">Selecione “Sim” se as notas fiscais e pagamentos retornarem liquidado automaticamente, como parte do processo de lançamento do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="5019f-111">Select "Yes" if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
    * <span data-ttu-id="5019f-112">Selecione “Sim” se as transações do cofre de segurança forem agregadas.</span><span class="sxs-lookup"><span data-stu-id="5019f-112">Select "Yes" if Safe drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="5019f-113">Selecione “Sim” se as transações de depósito bancário forem agregadas.</span><span class="sxs-lookup"><span data-stu-id="5019f-113">Select "Yes" if Bank drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="5019f-114">Selecione "Sim" para ativar a agregação para o lançamento do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="5019f-114">Select "Yes" to turn aggregation on for Statement posting.</span></span>  
    * <span data-ttu-id="5019f-115">Selecione “Sim” para criar e processar ordens em paralelo quando as instruções forem lançadas.</span><span class="sxs-lookup"><span data-stu-id="5019f-115">Select "Yes" to create and process orders in parallel when statements are posted.</span></span>  
    * <span data-ttu-id="5019f-116">Insira as ordens máximas a serem processadas em cada tarefa do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="5019f-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="5019f-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5019f-117">Click Save.</span></span>


