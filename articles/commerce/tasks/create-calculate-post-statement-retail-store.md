---
title: Criar, calcular e lançar demonstrativos para uma loja de varejo
description: Este tópico descreve as etapas manuais para criar, calcular e lançar um demonstrativo para uma loja.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ef31bc02fe1761a587ff6bcbecf4a0f34daea9b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964861"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="9ba30-103">Criar, calcular e lançar demonstrativos para uma loja de varejo</span><span class="sxs-lookup"><span data-stu-id="9ba30-103">Create, calculate, and post statements for a retail store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ba30-104">Este tópico descreve as etapas manuais para criar, calcular e lançar um demonstrativo para uma loja.</span><span class="sxs-lookup"><span data-stu-id="9ba30-104">This topic describes the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="9ba30-105">Há também os trabalhos em lotes que podem ser configurados para as mesmas tarefas.</span><span class="sxs-lookup"><span data-stu-id="9ba30-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="9ba30-106">As etapas para configurar e executar os trabalhos em lote podem ser encontradas em outros tópicos.</span><span class="sxs-lookup"><span data-stu-id="9ba30-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="9ba30-107">Para realizar este procedimento, você deve ter transações que foram executadas no PDV e inseridas no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9ba30-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics 365 Commerce.</span></span> <span data-ttu-id="9ba30-108">Esta gravação usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="9ba30-108">This recording uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="9ba30-109">Selecione **Finanças da loja** na home page.</span><span class="sxs-lookup"><span data-stu-id="9ba30-109">Select **Store financials** from the home page.</span></span>
2. <span data-ttu-id="9ba30-110">Selecione **Novo demonstrativo**.</span><span class="sxs-lookup"><span data-stu-id="9ba30-110">Select **New statement**.</span></span>
3. <span data-ttu-id="9ba30-111">No campo **Número da loja**, selecione uma opção no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="9ba30-111">In the **Store number** field, select a option from the drop-down.</span></span>
4. <span data-ttu-id="9ba30-112">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ba30-112">Select **OK**.</span></span>
5. <span data-ttu-id="9ba30-113">O grupo **Configuração** tem as configurações que controlam que transações são incluídas no demonstrativo e como são agrupadas nas linhas do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="9ba30-113">The **Setup** group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="9ba30-114">Você pode abrir o grupo **Configuração** e alterar essas configurações ou pode usar os padrões.</span><span class="sxs-lookup"><span data-stu-id="9ba30-114">You can open the **Setup** group and change these settings, or you can use the defaults.</span></span>  
    - <span data-ttu-id="9ba30-115">O campo **Método do demonstrativo** define como as linhas do demonstrativo serão agrupadas.</span><span class="sxs-lookup"><span data-stu-id="9ba30-115">The **Statement method** field defines how the statement lines will be grouped.</span></span>  
    - <span data-ttu-id="9ba30-116">Selecione um membro da equipe ou um registro no campo **equipe/registro** se desejar calcular um demonstrativo somente para o membro da equipe ou registro específico.</span><span class="sxs-lookup"><span data-stu-id="9ba30-116">Select a staff member or a register in the **staff/register** field if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="9ba30-117">No campo **Método de fechamento**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="9ba30-117">In the **Closing method** field, select an option.</span></span>
7. <span data-ttu-id="9ba30-118">Selecione **Calcular demonstrativo** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="9ba30-118">Select **Calculate statement** from the Action Pane.</span></span>
8. <span data-ttu-id="9ba30-119">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9ba30-119">Select **Yes**.</span></span>
    - <span data-ttu-id="9ba30-120">Depois de calcular o demonstrativo, deve haver linhas criadas com os valores totais para cada método de pagamento e o método do demonstrativo que foi usado.</span><span class="sxs-lookup"><span data-stu-id="9ba30-120">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    - <span data-ttu-id="9ba30-121">Insira um valor contado em cada linha caso seja necessário ser inserido ou atualizado.</span><span class="sxs-lookup"><span data-stu-id="9ba30-121">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="9ba30-122">O campo Contado será preenchido com valores das declarações de meios de pagamento feitas no PDV.</span><span class="sxs-lookup"><span data-stu-id="9ba30-122">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="9ba30-123">Selecione **Lançar demonstrativo** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="9ba30-123">Select **Post statement** from the Action Pane.</span></span>
10. <span data-ttu-id="9ba30-124">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="9ba30-124">Select **Close**.</span></span>
11. <span data-ttu-id="9ba30-125">Feche o painel.</span><span class="sxs-lookup"><span data-stu-id="9ba30-125">Close the pane.</span></span>
12. <span data-ttu-id="9ba30-126">Na home page, selecione **Finanças da loja**.</span><span class="sxs-lookup"><span data-stu-id="9ba30-126">At the home page, select **Store financials**.</span></span>
13. <span data-ttu-id="9ba30-127">Selecione a guia **Demonstrativos lançados**.</span><span class="sxs-lookup"><span data-stu-id="9ba30-127">Select the **Posted statements** tab.</span></span>

