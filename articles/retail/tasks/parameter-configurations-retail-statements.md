--- 
title: " Configurações de parâmetro para obter demonstrativos de varejo"
description: "Este procedimento demonstra configurações dos parâmetros de varejo que afetam como as instruções de varejo foram criadas e lançadas."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 731a3ec06efa103ba663df83240c77dfe78bb7cd
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="parameter-configurations-for-retail-statements"></a><span data-ttu-id="7cd19-103"> Configurações de parâmetro para obter demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="7cd19-103">Parameter configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="7cd19-104">Este procedimento demonstra configurações dos parâmetros de varejo que afetam como as instruções de varejo foram criadas e lançadas.</span><span class="sxs-lookup"><span data-stu-id="7cd19-104">This procedure demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="7cd19-105">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="7cd19-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="7cd19-106">Vá para Varejo e comércio > Configuração da sede > Parâmetros > Parâmetros de varejo.</span><span class="sxs-lookup"><span data-stu-id="7cd19-106">Go to Retail and commerce > Headquarters setup  > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="7cd19-107">Clique na guia Lançamento.</span><span class="sxs-lookup"><span data-stu-id="7cd19-107">Click the Posting tab.</span></span>
    * <span data-ttu-id="7cd19-108">Selecione “Sim” se quiser lançar especificamente os valores de desconto periódico.</span><span class="sxs-lookup"><span data-stu-id="7cd19-108">Select "Yes" if you want to post the periodic discount amounts specifically.</span></span>  
    * <span data-ttu-id="7cd19-109">Selecione "Padrão" para usar contas padrão, ou selecione “Periódico”, se você quiser definir qual conta usar para cada desconto periódico.</span><span class="sxs-lookup"><span data-stu-id="7cd19-109">Select "Standard" to use default accounts, or select "Periodic" if you want to define which account to use for each periodic discount.</span></span>  
    * <span data-ttu-id="7cd19-110">Selecione "Resumo" se as linhas de estoque tiverem que ser agregadas, sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="7cd19-110">Select "Summary" if inventory lines should get aggregated whenever possible.</span></span>  
    * <span data-ttu-id="7cd19-111">Selecione “Sim” se as notas fiscais e pagamentos retornarem liquidado automaticamente, como parte do processo de lançamento do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="7cd19-111">Select "Yes" if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
    * <span data-ttu-id="7cd19-112">Selecione “Sim” se as transações do cofre de segurança forem agregadas.</span><span class="sxs-lookup"><span data-stu-id="7cd19-112">Select "Yes" if Safe drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="7cd19-113">Selecione “Sim” se as transações de depósito bancário forem agregadas.</span><span class="sxs-lookup"><span data-stu-id="7cd19-113">Select "Yes" if Bank drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="7cd19-114">Selecione "Sim" para ativar a agregação para o lançamento do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="7cd19-114">Select "Yes" to turn aggregation on for Statement posting.</span></span>  
    * <span data-ttu-id="7cd19-115">Selecione “Sim” para criar e processar ordens em paralelo quando as instruções forem lançadas.</span><span class="sxs-lookup"><span data-stu-id="7cd19-115">Select "Yes" to create and process orders in parallel when statements are posted.</span></span>  
    * <span data-ttu-id="7cd19-116">Insira as ordens máximas a serem processadas em cada tarefa do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="7cd19-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="7cd19-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7cd19-117">Click Save.</span></span>


