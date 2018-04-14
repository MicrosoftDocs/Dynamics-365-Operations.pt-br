--- 
title: "Criar, calcular e lançar uma declaração para uma loja de varejo"
description: "Este procedimento orienta nas etapas manuais para criar, calcular e lançar um demonstrativo para uma loja."
author: jashanno
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d9f9888d04f4e2419de9d4a6857a81ae40f6f21a
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a><span data-ttu-id="00494-103">Criar, calcular e lançar uma declaração para uma loja de varejo</span><span class="sxs-lookup"><span data-stu-id="00494-103">Create, calculate, and post a statement for a retail store</span></span>

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="00494-104">Este procedimento orienta nas etapas manuais para criar, calcular e lançar um demonstrativo para uma loja.</span><span class="sxs-lookup"><span data-stu-id="00494-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="00494-105">Há também os trabalhos em lotes que podem ser configurados para as mesmas tarefas.</span><span class="sxs-lookup"><span data-stu-id="00494-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="00494-106">As etapas para configurar e executar os trabalhos em lote podem ser encontradas em outros tópicos.</span><span class="sxs-lookup"><span data-stu-id="00494-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="00494-107">Para concluir este procedimento, você deve ter transações que foram concluídas no PDV e recebidas pelo Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="00494-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="00494-108">Esta gravação usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="00494-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="00494-109">Este procedimento pode fazer referência ao Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="00494-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="00494-110">Observe que o Dynamics AX agora se chama Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="00494-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="00494-111">Vá para Todos os espaços de trabalho > ..</span><span class="sxs-lookup"><span data-stu-id="00494-111">Go to All workspaces > ..</span></span> <span data-ttu-id="00494-112">> Finanças da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="00494-112">> Retail store financials.</span></span>
2. <span data-ttu-id="00494-113">Clique em Novo demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="00494-113">Click New statement.</span></span>
3. <span data-ttu-id="00494-114">No campo Número da loja, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="00494-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="00494-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="00494-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="00494-116">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="00494-116">Click OK.</span></span>
    * <span data-ttu-id="00494-117">O Grupo de configuração tem as configurações que controlam que transações são incluídas no demonstrativo e como são agrupadas nas linhas do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="00494-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="00494-118">Você pode abrir o grupo de configuração e alterar as configurações ou pode usar os padrões.</span><span class="sxs-lookup"><span data-stu-id="00494-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="00494-119">O campo Método do demonstrativo define como as linhas do demonstrativo serão agrupadas.</span><span class="sxs-lookup"><span data-stu-id="00494-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="00494-120">Selecione um membro da equipe ou um registro se você deseja calcular um demonstrativo somente para o membro da equipe ou registro específico.</span><span class="sxs-lookup"><span data-stu-id="00494-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="00494-121">No campo Método de fechamento, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="00494-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="00494-122">Clique em Calcular demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="00494-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="00494-123">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="00494-123">Click Yes.</span></span>
    * <span data-ttu-id="00494-124">Depois de calcular o demonstrativo, deve haver linhas criadas com os valores totais para cada método de pagamento e o método do demonstrativo que foi usado.</span><span class="sxs-lookup"><span data-stu-id="00494-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="00494-125">Insira um valor contado em cada linha caso seja necessário ser inserido ou atualizado.</span><span class="sxs-lookup"><span data-stu-id="00494-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="00494-126">O campo Contado será preenchido com valores das declarações de meios de pagamento feitas no PDV.</span><span class="sxs-lookup"><span data-stu-id="00494-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="00494-127">Clique em Lançar demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="00494-127">Click Post statement.</span></span>
10. <span data-ttu-id="00494-128">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="00494-128">Click Close.</span></span>
11. <span data-ttu-id="00494-129">Vá para Varejo e comércio > Canais > Finanças da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="00494-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="00494-130">Clique na guia Demonstrativos lançados.</span><span class="sxs-lookup"><span data-stu-id="00494-130">Click the Posted statements tab.</span></span>


