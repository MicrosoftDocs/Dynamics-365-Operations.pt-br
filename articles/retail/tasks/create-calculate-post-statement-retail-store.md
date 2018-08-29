--- 
title: "Criar, calcular e lançar demonstrativos para uma loja de varejo"
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
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 1c31c849c4c72762f0fdeb3f1d256cd3529394b2
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="a4e76-103">Criar, calcular e lançar demonstrativos para uma loja de varejo</span><span class="sxs-lookup"><span data-stu-id="a4e76-103">Create, calculate, and post statements for a retail store</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="a4e76-104">Este procedimento orienta nas etapas manuais para criar, calcular e lançar um demonstrativo para uma loja.</span><span class="sxs-lookup"><span data-stu-id="a4e76-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="a4e76-105">Há também os trabalhos em lotes que podem ser configurados para as mesmas tarefas.</span><span class="sxs-lookup"><span data-stu-id="a4e76-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="a4e76-106">As etapas para configurar e executar os trabalhos em lote podem ser encontradas em outros tópicos.</span><span class="sxs-lookup"><span data-stu-id="a4e76-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="a4e76-107">Para concluir este procedimento, você deve ter transações que foram concluídas no PDV e recebidas pelo Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="a4e76-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="a4e76-108">Esta gravação usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="a4e76-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="a4e76-109">Este procedimento pode fazer referência ao Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="a4e76-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="a4e76-110">Observe que o Dynamics AX agora se chama Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="a4e76-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="a4e76-111">Vá para Todos os espaços de trabalho > ..</span><span class="sxs-lookup"><span data-stu-id="a4e76-111">Go to All workspaces > ..</span></span> <span data-ttu-id="a4e76-112">> Finanças da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="a4e76-112">> Retail store financials.</span></span>
2. <span data-ttu-id="a4e76-113">Clique em Novo demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="a4e76-113">Click New statement.</span></span>
3. <span data-ttu-id="a4e76-114">No campo Número da loja, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a4e76-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="a4e76-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="a4e76-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a4e76-116">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a4e76-116">Click OK.</span></span>
    * <span data-ttu-id="a4e76-117">O Grupo de configuração tem as configurações que controlam que transações são incluídas no demonstrativo e como são agrupadas nas linhas do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="a4e76-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="a4e76-118">Você pode abrir o grupo de configuração e alterar as configurações ou pode usar os padrões.</span><span class="sxs-lookup"><span data-stu-id="a4e76-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="a4e76-119">O campo Método do demonstrativo define como as linhas do demonstrativo serão agrupadas.</span><span class="sxs-lookup"><span data-stu-id="a4e76-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="a4e76-120">Selecione um membro da equipe ou um registro se você deseja calcular um demonstrativo somente para o membro da equipe ou registro específico.</span><span class="sxs-lookup"><span data-stu-id="a4e76-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="a4e76-121">No campo Método de fechamento, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="a4e76-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="a4e76-122">Clique em Calcular demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="a4e76-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="a4e76-123">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="a4e76-123">Click Yes.</span></span>
    * <span data-ttu-id="a4e76-124">Depois de calcular o demonstrativo, deve haver linhas criadas com os valores totais para cada método de pagamento e o método do demonstrativo que foi usado.</span><span class="sxs-lookup"><span data-stu-id="a4e76-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="a4e76-125">Insira um valor contado em cada linha caso seja necessário ser inserido ou atualizado.</span><span class="sxs-lookup"><span data-stu-id="a4e76-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="a4e76-126">O campo Contado será preenchido com valores das declarações de meios de pagamento feitas no PDV.</span><span class="sxs-lookup"><span data-stu-id="a4e76-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="a4e76-127">Clique em Lançar demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="a4e76-127">Click Post statement.</span></span>
10. <span data-ttu-id="a4e76-128">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="a4e76-128">Click Close.</span></span>
11. <span data-ttu-id="a4e76-129">Vá para Varejo e comércio > Canais > Finanças da loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="a4e76-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="a4e76-130">Clique na guia Demonstrativos lançados.</span><span class="sxs-lookup"><span data-stu-id="a4e76-130">Click the Posted statements tab.</span></span>


