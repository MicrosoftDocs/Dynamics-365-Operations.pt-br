---
title: Configurar parâmetros que afetam demonstrativos de varejo
description: Este tópico demonstra configurações dos parâmetros de comércio que afetam como as instruções são criadas e lançadas.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8cae6d2fa7c469f50fa92141a6cb5a0af1df4b0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021597"
---
# <a name="configure-parameters-that-affect-retail-statements"></a><span data-ttu-id="b91f3-103">Configurar parâmetros que afetam demonstrativos de varejo</span><span class="sxs-lookup"><span data-stu-id="b91f3-103">Configure parameters that affect retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="b91f3-104">Este tópico demonstra configurações dos parâmetros de comércio que afetam como as instruções são criadas e lançadas.</span><span class="sxs-lookup"><span data-stu-id="b91f3-104">This topic demonstrates configurations for Commerce parameters that affect how statements get created and posted.</span></span> <span data-ttu-id="b91f3-105">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="b91f3-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="b91f3-106">No painel de navegação, vá para **Módulos > Retail e Commerce > Configuração da sede > Parâmetros > Parâmetros de comércio**.</span><span class="sxs-lookup"><span data-stu-id="b91f3-106">In the navigation pane, go to **Modules > Retail and Commerce > Headquarters setup  > Parameters > Commerce parameters**.</span></span>
2. <span data-ttu-id="b91f3-107">Selecione a guia **Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="b91f3-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="b91f3-108">Selecione **Sim** se quiser lançar especificamente os valores de desconto periódico.</span><span class="sxs-lookup"><span data-stu-id="b91f3-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="b91f3-109">Selecione **Padrão** para usar as contas padrão, ou selecione **Periódico** se quiser definir qual conta usar para cada desconto periódico.</span><span class="sxs-lookup"><span data-stu-id="b91f3-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="b91f3-110">Selecione **Resumo** se as linhas de estoque tiverem que ser agregadas, sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="b91f3-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="b91f3-111">Selecione **Sim** se as notas fiscais e pagamentos retornarem liquidado automaticamente, como parte do processo de lançamento do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="b91f3-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="b91f3-112">Selecione **Sim** se as transações do cofre de segurança forem agregadas.</span><span class="sxs-lookup"><span data-stu-id="b91f3-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="b91f3-113">Selecione **Sim** se as transações de depósito bancário forem agregadas.</span><span class="sxs-lookup"><span data-stu-id="b91f3-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="b91f3-114">Selecione **Sim** para ativar a agregação para o lançamento do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="b91f3-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="b91f3-115">Selecione **Sim** para criar e processar ordens em paralelo quando as instruções forem lançadas.</span><span class="sxs-lookup"><span data-stu-id="b91f3-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="b91f3-116">Insira as ordens máximas a serem processadas em cada tarefa do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="b91f3-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="b91f3-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b91f3-117">Select **Save**.</span></span>

