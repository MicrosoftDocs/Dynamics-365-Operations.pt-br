---
title: Definir agendas de continuidade
description: Este tópico aborda a configuração de um programa de continuidade (também conhecido como pedidos recorrentes).
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 06fd1e23ad84fdc5e94e309717d5a96fbff45035
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140890"
---
# <a name="define-continuity-schedules"></a><span data-ttu-id="36076-103">Definir agendas de continuidade</span><span class="sxs-lookup"><span data-stu-id="36076-103">Define continuity schedules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="36076-104">Este tópico aborda a configuração de um programa de continuidade (também conhecido como pedidos recorrentes).</span><span class="sxs-lookup"><span data-stu-id="36076-104">This topic walks through setting up a continuity program (otherwise known as reoccurring orders).</span></span> <span data-ttu-id="36076-105">Este tópico usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="36076-105">This topic uses company USRT in the demo data.</span></span>


## <a name="create-continuity-program"></a><span data-ttu-id="36076-106">Criar programa de continuidade</span><span class="sxs-lookup"><span data-stu-id="36076-106">Create continuity program</span></span>
1. <span data-ttu-id="36076-107">Vá para Varejo e Comércio > Continuidade > Programas de continuidade.</span><span class="sxs-lookup"><span data-stu-id="36076-107">Go to Retail and Commerce > Continuity > Continuity programs.</span></span>
2. <span data-ttu-id="36076-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="36076-108">Click New.</span></span>
3. <span data-ttu-id="36076-109">No campo ID da Agenda, digite a ID da agenda de continuidade.</span><span class="sxs-lookup"><span data-stu-id="36076-109">In the Schedule ID field, type the continuity schedule ID.</span></span>
4. <span data-ttu-id="36076-110">No campo Início da ordem, selecione "Primeiro evento".</span><span class="sxs-lookup"><span data-stu-id="36076-110">In the Order start field, select 'First event'.</span></span>
    * <span data-ttu-id="36076-111">Se um cliente estabelecer uma nova ordem para o programa da continuidade, há duas opções para envio do produto: 1.</span><span class="sxs-lookup"><span data-stu-id="36076-111">If a customer places a new order for the continuity program, there are two options for which product will be shipped:  1.</span></span> <span data-ttu-id="36076-112">Primeiro evento: o primeiro produto no programa de continuidade será enviado.</span><span class="sxs-lookup"><span data-stu-id="36076-112">First event: the first product in the continuity program will be shipped.</span></span>  <span data-ttu-id="36076-113">2.</span><span class="sxs-lookup"><span data-stu-id="36076-113">2.</span></span> <span data-ttu-id="36076-114">Evento atual: o produto atual será enviado.</span><span class="sxs-lookup"><span data-stu-id="36076-114">Current event: the current product will be shipped.</span></span> <span data-ttu-id="36076-115">Por exemplo.</span><span class="sxs-lookup"><span data-stu-id="36076-115">For example.</span></span> <span data-ttu-id="36076-116">três meses no programa, o cliente receberá o terceiro no programa.</span><span class="sxs-lookup"><span data-stu-id="36076-116">three months into the program, the customer will receive the third in the program.</span></span>  
5. <span data-ttu-id="36076-117">Selecione "Sim" para solicitar a data inicial da ordem.</span><span class="sxs-lookup"><span data-stu-id="36076-117">Select 'Yes' to prompt for the order start date.</span></span>
6. <span data-ttu-id="36076-118">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="36076-118">Click Add line.</span></span>
7. <span data-ttu-id="36076-119">No campo Número do item, digite o número de item do primeiro produto ("0013").</span><span class="sxs-lookup"><span data-stu-id="36076-119">In the Item number field, type the item number for the first product ('0013').</span></span>
8. <span data-ttu-id="36076-120">Digite "CP".</span><span class="sxs-lookup"><span data-stu-id="36076-120">Type 'CP'.</span></span>
9. <span data-ttu-id="36076-121">Insira a dada em que o primeiro produto estará disponível para ordem.</span><span class="sxs-lookup"><span data-stu-id="36076-121">Enter the date when the first product will be available for order.</span></span>
10. <span data-ttu-id="36076-122">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="36076-122">Click Add line.</span></span>
11. <span data-ttu-id="36076-123">No campo do número de item, digite '0014'.</span><span class="sxs-lookup"><span data-stu-id="36076-123">In the Item number field, type '0014'.</span></span>
12. <span data-ttu-id="36076-124">No campo Código do intervalo de datas, apague o valor para que o campo fique vazio.</span><span class="sxs-lookup"><span data-stu-id="36076-124">In the Date interval code field, clear the value so the field is empty.</span></span>
    * <span data-ttu-id="36076-125">Nesse procedimento, desmarque o intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="36076-125">For this procedure, clear the date interval.</span></span> <span data-ttu-id="36076-126">Você verá a data como incremental a partir da data inicial do primeiro item.</span><span class="sxs-lookup"><span data-stu-id="36076-126">You'll set the date as incremental from the start date of the first item.</span></span>  
13. <span data-ttu-id="36076-127">Aqui você inserirá o intervalo no qual os produtos serão enviados.</span><span class="sxs-lookup"><span data-stu-id="36076-127">Here you'll enter the interval at which the products are shipped.</span></span> <span data-ttu-id="36076-128">Digite "30".</span><span class="sxs-lookup"><span data-stu-id="36076-128">Type '30'.</span></span>
    * <span data-ttu-id="36076-129">Para um programa mensal, você inserirá 30 dias para o intervalo.</span><span class="sxs-lookup"><span data-stu-id="36076-129">For a monthly program, you'll enter 30 days for the interval.</span></span>  
14. <span data-ttu-id="36076-130">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="36076-130">Click Add line.</span></span>
15. <span data-ttu-id="36076-131">No campo do número de item, digite '0015'.</span><span class="sxs-lookup"><span data-stu-id="36076-131">In the Item number field, type '0015'.</span></span>
16. <span data-ttu-id="36076-132">Digite "Fim".</span><span class="sxs-lookup"><span data-stu-id="36076-132">Type 'End'.</span></span>
17. <span data-ttu-id="36076-133">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="36076-133">Click Save.</span></span>

## <a name="assign-to-continuity-item"></a><span data-ttu-id="36076-134">Atribuir ao item de continuidade</span><span class="sxs-lookup"><span data-stu-id="36076-134">Assign to continuity item</span></span>
1. <span data-ttu-id="36076-135">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="36076-135">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="36076-136">Selecione o item "0016".</span><span class="sxs-lookup"><span data-stu-id="36076-136">Select item '0016'.</span></span>
    * <span data-ttu-id="36076-137">Nesse procedimento, você selecionará o item nº 0016.</span><span class="sxs-lookup"><span data-stu-id="36076-137">For this procedure, you'll select item number 0016.</span></span> <span data-ttu-id="36076-138">Geralmente, você terá criado um produto liberado com lógica comercial de continuidade adicional aplicada ao ser colocada em uma ordem de venda em call center.</span><span class="sxs-lookup"><span data-stu-id="36076-138">Normally, you'll have created a released product that has additional continuity business logic applied when it's placed on a sales order in call center.</span></span>  
3. <span data-ttu-id="36076-139">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="36076-139">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="36076-140">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="36076-140">Click Edit.</span></span>
5. <span data-ttu-id="36076-141">Expanda ou recolha a seção Venda.</span><span class="sxs-lookup"><span data-stu-id="36076-141">Expand or collapse the Sell section.</span></span>
6. <span data-ttu-id="36076-142">Aqui você inserirá o programa de continuidade que esse item representa.</span><span class="sxs-lookup"><span data-stu-id="36076-142">Here you'll enter the continuity program that this item represents.</span></span> <span data-ttu-id="36076-143">Digite a ID da agenda criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="36076-143">Type the Schedule ID you created earlier.</span></span>
    * <span data-ttu-id="36076-144">Quando esse item é vendido em um call center, a lógica comercial adicional é aplicada a partir do programa de continuidade selecionado.</span><span class="sxs-lookup"><span data-stu-id="36076-144">When this item is sold in a call center, additional business logic is applied from the selected continuity program.</span></span>  
7. <span data-ttu-id="36076-145">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="36076-145">Click Save.</span></span>
