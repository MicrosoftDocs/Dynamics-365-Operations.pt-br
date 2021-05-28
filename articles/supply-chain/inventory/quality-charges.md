---
title: Encargos para operações de não conformidade
description: Este tópico descreve como criar encargos de qualidade que possam ser usados com operações para uma não conformidade.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 382890232bff47a885840af1eb7e91d27bb46cae
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022291"
---
# <a name="charges-for-nonconformance-operations"></a><span data-ttu-id="f9a16-103">Encargos para operações de não conformidade</span><span class="sxs-lookup"><span data-stu-id="f9a16-103">Charges for nonconformance operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9a16-104">Este tópico descreve como criar encargos de qualidade que possam ser usados com operações para uma não conformidade.</span><span class="sxs-lookup"><span data-stu-id="f9a16-104">This topic describes how to create quality charges that can be used with operations for a nonconformance.</span></span>

<span data-ttu-id="f9a16-105">Use a página **Encargos de qualidade** para definir os tipos de encargos que podem ser adicionados a operações para uma não conformidade.</span><span class="sxs-lookup"><span data-stu-id="f9a16-105">You use the **Quality charges** page to define the types of charges that can be added to operations for a nonconformance.</span></span> <span data-ttu-id="f9a16-106">Os encargos permitem acompanhar detalhes sobre taxas ou encargos que você deve a um cliente por produtos que não estão em conformidade ou que um fornecedor deve a você por produtos que não estão em conformidade recebidos.</span><span class="sxs-lookup"><span data-stu-id="f9a16-106">Charges let you track details about fees or charges that you owe to a customer for nonconforming products, or that a vendor owes to you for nonconforming products that you received.</span></span> <span data-ttu-id="f9a16-107">Você também pode usar encargos para rastrear os custos necessários para que fornecedores ou serviços externos executem uma operação.</span><span class="sxs-lookup"><span data-stu-id="f9a16-107">You might also use charges to track costs that are required for external vendors or services to perform an operation.</span></span>

## <a name="examples-of-quality-charges"></a><span data-ttu-id="f9a16-108">Exemplos de encargos de qualidade</span><span class="sxs-lookup"><span data-stu-id="f9a16-108">Examples of quality charges</span></span>

<span data-ttu-id="f9a16-109">Você trabalha para uma empresa de fabricação.</span><span class="sxs-lookup"><span data-stu-id="f9a16-109">You work for a manufacturing company.</span></span> <span data-ttu-id="f9a16-110">Sua empresa tem contratos com vários fornecedores.</span><span class="sxs-lookup"><span data-stu-id="f9a16-110">Your company has contracts with several vendors.</span></span> <span data-ttu-id="f9a16-111">Esses contratos descrevem os padrões de remessa no prazo, danos e qualidade de produto para itens.</span><span class="sxs-lookup"><span data-stu-id="f9a16-111">Those contracts outline standards for on-time shipment, damages, and product quality for items.</span></span> <span data-ttu-id="f9a16-112">Da mesma forma, vários clientes têm contratos com a sua empresa sobre devoluções, danos e qualidade de produto.</span><span class="sxs-lookup"><span data-stu-id="f9a16-112">Likewise, several of your customers have agreements with your company about returns, damages, and product quality.</span></span>

<span data-ttu-id="f9a16-113">Uma estrutura de taxa é definida para cada circunstância e especificada no contrato.</span><span class="sxs-lookup"><span data-stu-id="f9a16-113">A fee structure is defined for each circumstance and specified in the contract.</span></span> <span data-ttu-id="f9a16-114">Você pode configurar os encargos de qualidade para destacar os vários tipos de encargos, como *Danos*, *Remessa atrasada* e *Qualidade*.</span><span class="sxs-lookup"><span data-stu-id="f9a16-114">You can configure quality charges to outline the various types of charges, such as *Damages*, *Late shipment*, and *Quality*.</span></span> <span data-ttu-id="f9a16-115">Em seguida, ao criar uma não conformidade, adicione uma ou mais operações.</span><span class="sxs-lookup"><span data-stu-id="f9a16-115">Then, when you create a nonconformance, you add one or more operations.</span></span> <span data-ttu-id="f9a16-116">Para cada operação, selecione **Encargos** para definir os detalhes sobre as taxas.</span><span class="sxs-lookup"><span data-stu-id="f9a16-116">For each operation, you select **Charges** to define the details about the fees.</span></span>

## <a name="create-a-quality-charge"></a><span data-ttu-id="f9a16-117">Criar um encargo de qualidade</span><span class="sxs-lookup"><span data-stu-id="f9a16-117">Create a quality charge</span></span>

1. <span data-ttu-id="f9a16-118">Vá para **Gerenciamento de estoque \> Configuração \> Gerenciamento de qualidade \> Encargos de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="f9a16-118">Go to **Inventory management \> Setup \> Quality management \> Quality charges**.</span></span>
1. <span data-ttu-id="f9a16-119">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="f9a16-119">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="f9a16-120">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="f9a16-120">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="f9a16-121">**Código de encargos** – Insira um nome ou uma ID exclusiva para o encargo de qualidade.</span><span class="sxs-lookup"><span data-stu-id="f9a16-121">**Charges code** – Enter a unique ID or name for the quality charge.</span></span>
    - <span data-ttu-id="f9a16-122">**Descrição** – Insira uma descrição detalhada do encargo de qualidade.</span><span class="sxs-lookup"><span data-stu-id="f9a16-122">**Description** – Enter a detailed description of the quality charge.</span></span>

1. <span data-ttu-id="f9a16-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f9a16-123">Close the page.</span></span>

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a><span data-ttu-id="f9a16-124">Adicionar um encargo de qualidade a uma operação para uma não conformidade</span><span class="sxs-lookup"><span data-stu-id="f9a16-124">Add a quality charge to an operation for a nonconformance</span></span>

<span data-ttu-id="f9a16-125">Para obter detalhes sobre como adicionar operações a uma não conformidade e aplicar encargos a elas, consulte [Operações para não conformidades](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="f9a16-125">For details about how to add operations to a nonconformance and apply charges to them, see [Operations for nonconformances](quality-operations.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f9a16-126">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f9a16-126">Additional resources</span></span>

- [<span data-ttu-id="f9a16-127">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="f9a16-127">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="f9a16-128">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="f9a16-128">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="f9a16-129">Trabalhadores responsáveis por aprovar não conformidades</span><span class="sxs-lookup"><span data-stu-id="f9a16-129">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="f9a16-130">Zonas de quarentena para não conformidades</span><span class="sxs-lookup"><span data-stu-id="f9a16-130">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="f9a16-131">Tipos de diagnóstico para não conformidades</span><span class="sxs-lookup"><span data-stu-id="f9a16-131">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="f9a16-132">Encargos de qualidade para não conformidades</span><span class="sxs-lookup"><span data-stu-id="f9a16-132">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="f9a16-133">Operações para não conformidades</span><span class="sxs-lookup"><span data-stu-id="f9a16-133">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="f9a16-134">Gerenciamento de qualidade para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="f9a16-134">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
