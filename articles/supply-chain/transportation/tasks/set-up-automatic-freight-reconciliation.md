---
title: Configurar automatização de reconciliação de frete
description: Este procedimento mostra como definir dados para reconciliação automática de frete.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f11edc15821faad84485d5b81e4a9ded0b7e974
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421969"
---
# <a name="set-up-automatic-freight-reconciliation"></a><span data-ttu-id="da662-103">Configurar automatização de reconciliação de frete</span><span class="sxs-lookup"><span data-stu-id="da662-103">Set up automatic freight reconciliation</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="da662-104">Este procedimento mostra como definir dados para reconciliação automática de frete.</span><span class="sxs-lookup"><span data-stu-id="da662-104">This procedure shows how to set up data for automatic freight reconciliation.</span></span> <span data-ttu-id="da662-105">Isso normalmente é feito por um gerente de depósito.</span><span class="sxs-lookup"><span data-stu-id="da662-105">This is typically done by a warehouse manager.</span></span> <span data-ttu-id="da662-106">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="da662-106">You can use this procedure in demo data company USMF.</span></span>


## <a name="set-up-the-freight-bill-type"></a><span data-ttu-id="da662-107">Configurar o tipo de conta de frete</span><span class="sxs-lookup"><span data-stu-id="da662-107">Set up the freight bill type</span></span>
1. <span data-ttu-id="da662-108">Vá para Gerenciamento de transporte > Configuração > Reconciliação de frete > Tipo de nota de frete.</span><span class="sxs-lookup"><span data-stu-id="da662-108">Go to Transportation management > Setup > Freight reconciliation > Freight bill type.</span></span>
    * <span data-ttu-id="da662-109">O tipo de conta de fretes define como as contas de frete e faturas de transportadora devem ser correspondidas.</span><span class="sxs-lookup"><span data-stu-id="da662-109">The freight bill type defines how freight bills and carrier invoices  should be matched.</span></span>  
2. <span data-ttu-id="da662-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="da662-110">Click New.</span></span>
3. <span data-ttu-id="da662-111">No campo Tipo de nota de frete, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="da662-111">In the Freight bill type field, type a value.</span></span>
4. <span data-ttu-id="da662-112">No campo Assembly do mecanismo, digite 'Microsoft.Dynamics.Ax.Tms.dll'.</span><span class="sxs-lookup"><span data-stu-id="da662-112">In the Engine assembly field, type 'Microsoft.Dynamics.Ax.Tms.dll'.</span></span>
    * <span data-ttu-id="da662-113">Esta é a biblioteca de códigos do mecanismo de gerenciamento de transporte padrão.</span><span class="sxs-lookup"><span data-stu-id="da662-113">This is the standard Transportation management matching engine code library.</span></span>  
5. <span data-ttu-id="da662-114">No campo Classe do mecanismo, digite 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'.</span><span class="sxs-lookup"><span data-stu-id="da662-114">In the Engine class field, type 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'.</span></span>
    * <span data-ttu-id="da662-115">Esta é a classe do mecanismo de gerenciamento de transporte padrão.</span><span class="sxs-lookup"><span data-stu-id="da662-115">This is the standard Transportation management matching engine class.</span></span>  
6. <span data-ttu-id="da662-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="da662-116">Click New.</span></span>
7. <span data-ttu-id="da662-117">No campo Descrição, selecione o valor que deve coincidir na nota de frete e a fatura da transportadora.</span><span class="sxs-lookup"><span data-stu-id="da662-117">In the Description field, choose the value that should match on the freight bill and the carrier invoice.</span></span>  
8. <span data-ttu-id="da662-118">No campo Conciliação necessária, selecione "Sim".</span><span class="sxs-lookup"><span data-stu-id="da662-118">In the Match required field, select 'Yes'.</span></span>
    * <span data-ttu-id="da662-119">Se você definir este campo como Sim, significa que o valor selecionado no campo Descrição precisa combinar com a nota de frete e a fatura da transportadora.</span><span class="sxs-lookup"><span data-stu-id="da662-119">If you set this field to Yes this means that the value selected in the Description field needs to match on both the freight bill and the carrier invoice.</span></span> <span data-ttu-id="da662-120">Se for definido para Não, o campo pode estar em branco em um destes.</span><span class="sxs-lookup"><span data-stu-id="da662-120">If you set it to No, the field can be blank on one of these.</span></span>  
9. <span data-ttu-id="da662-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="da662-121">Click Save.</span></span>

## <a name="set-up-the-freight-bill-type-assignment"></a><span data-ttu-id="da662-122">Configurar a atribuição do tipo de conta de frete</span><span class="sxs-lookup"><span data-stu-id="da662-122">Set up the freight bill type assignment</span></span>
1. <span data-ttu-id="da662-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="da662-123">Close the page.</span></span>
2. <span data-ttu-id="da662-124">Vá para Gerenciamento de transporte > Configuração > Reconciliação de frete > Atribuições de tipo de nota de frete.</span><span class="sxs-lookup"><span data-stu-id="da662-124">Go to Transportation management > Setup > Freight reconciliation > Freight bill type assignments.</span></span>
    * <span data-ttu-id="da662-125">A atribuição do tipo de conta de frete é usada para especificar o tipo de conta de frete usado para uma transportadora específica.</span><span class="sxs-lookup"><span data-stu-id="da662-125">The freight bill type assignment is used to specify which freight bill type is used for a particular carrier.</span></span>   
3. <span data-ttu-id="da662-126">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="da662-126">Click New.</span></span>
4. <span data-ttu-id="da662-127">No campo Modo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="da662-127">In the Mode field, enter or select a value.</span></span>
5. <span data-ttu-id="da662-128">No campo Transportadora, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="da662-128">In the Shipping carrier field, enter or select a value.</span></span>
6. <span data-ttu-id="da662-129">No campo Tipo de nota de frete, selecione o tipo de nota de frete criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="da662-129">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
7. <span data-ttu-id="da662-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="da662-130">Close the page.</span></span>

## <a name="set-up-the-audit-master"></a><span data-ttu-id="da662-131">Configure o planejamento de auditoria</span><span class="sxs-lookup"><span data-stu-id="da662-131">Set up the audit master</span></span>
1. <span data-ttu-id="da662-132">Vá para Gerenciamento de transporte > Configuração > Reconciliação de frete > Auditoria mestre.</span><span class="sxs-lookup"><span data-stu-id="da662-132">Go to Transportation management > Setup > Freight reconciliation > Audit master.</span></span>
    * <span data-ttu-id="da662-133">O planejamento de auditoria define limites de tolerância para reconciliação automática de frete.</span><span class="sxs-lookup"><span data-stu-id="da662-133">The audit master defines the tolerance limits for automatic freight reconciliation.</span></span> <span data-ttu-id="da662-134">Especifique por quanto os valores monetários na conta de frete e na fatura de transportadora pode diferir e ainda conceder a reconciliação.</span><span class="sxs-lookup"><span data-stu-id="da662-134">It specifies by how much the monetary amounts on the freight bill and the carrier invoice can differ and still allow reconciliation to occur.</span></span> <span data-ttu-id="da662-135">Também define como cuidar de discrepâncias.</span><span class="sxs-lookup"><span data-stu-id="da662-135">It also defines how to handle discrepancies.</span></span>  
2. <span data-ttu-id="da662-136">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="da662-136">Click New.</span></span>
3. <span data-ttu-id="da662-137">No campo ID da auditoria mestre, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="da662-137">In the Audit master ID field, type a value.</span></span>
4. <span data-ttu-id="da662-138">No campo Transportadora, selecione a mesma transportadora utilizada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="da662-138">In the Shipping carrier  field, select the same shipping carrier as you did earlier.</span></span>
5. <span data-ttu-id="da662-139">No campo Tipo de nota de frete, selecione o tipo de nota de frete criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="da662-139">In the Freight bill type field, select the freight bill type that you created earlier.</span></span>
6. <span data-ttu-id="da662-140">Expandir a seção Tolerância.</span><span class="sxs-lookup"><span data-stu-id="da662-140">Expand the Tolerance section.</span></span>
7. <span data-ttu-id="da662-141">No campo Nível de tolerância mínimo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="da662-141">In the Minimum tolerance level field, enter a number.</span></span>
8. <span data-ttu-id="da662-142">No campo Nível de tolerância máximo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="da662-142">In the Maximum tolerance level field, enter a number.</span></span>
9. <span data-ttu-id="da662-143">Expandir a seção Resultado.</span><span class="sxs-lookup"><span data-stu-id="da662-143">Expand the Result section.</span></span>
10. <span data-ttu-id="da662-144">No campo Código de motivo de pagamento a maior, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="da662-144">In the Overpayment reason code field, enter or select a value.</span></span>
    * <span data-ttu-id="da662-145">Se os valores monetários são diferentes na conta de frete e na nota fiscal da transportadora, os códigos de motivo de pagamento maior/menor especifica as contas que a diferença deve ser registrada sobre, como a diferença está dentro dos níveis de tolerância.</span><span class="sxs-lookup"><span data-stu-id="da662-145">If the monetary amounts differ on the freight bill and the carrier invoice, the overpayment and underpayment reason codes specify the accounts that the difference should be registered on, as long as the difference is within the tolerance levels.</span></span>  
11. <span data-ttu-id="da662-146">No campo Código de motivo de pagamento a menor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="da662-146">In the Underpayment reason code field, enter or select a value.</span></span>
12. <span data-ttu-id="da662-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="da662-147">Close the page.</span></span>

