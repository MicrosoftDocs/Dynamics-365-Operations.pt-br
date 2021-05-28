---
title: Tipos de problema para não conformidades
description: Este tópico descreve como criar e usar tipos de problema para não conformidades.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 742edec8570610efe41a2c627efd1df586e0733e
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022147"
---
# <a name="problem-types-for-nonconformances"></a><span data-ttu-id="b3fe7-103">Tipos de problema para não conformidades</span><span class="sxs-lookup"><span data-stu-id="b3fe7-103">Problem types for nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b3fe7-104">Este tópico descreve como criar e usar tipos de problema para não conformidades.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-104">This topic describes how to create and use problem types for nonconformances.</span></span>

<span data-ttu-id="b3fe7-105">Use a página **Tipos de problema** para definir uma classificação dos problemas de qualidade que podem ocorrer nos vários tipos de não conformidade.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-105">You use the **Problem types** page to define a classification of the quality problems that might occur for the various nonconformance types.</span></span> <span data-ttu-id="b3fe7-106">Para cada tipo de problema criado, você deve especificar os tipos de não conformidades com os quais o tipo de problema pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-106">For each problem type that you create, you must specify the types of nonconformances that the problem type can be used with.</span></span> <span data-ttu-id="b3fe7-107">Você pode configurar os tipos de não conformidade a seguir:</span><span class="sxs-lookup"><span data-stu-id="b3fe7-107">You can set up the following nonconformance types:</span></span>

- <span data-ttu-id="b3fe7-108">**Interno** – Não conformidades deste tipo estão relacionadas ao estoque disponível (por exemplo, ordens de qualidade ou ordens de quarentena).</span><span class="sxs-lookup"><span data-stu-id="b3fe7-108">**Internal** – Nonconformances of this type are related to on-hand inventory (for example, quality orders or quarantine orders).</span></span>
- <span data-ttu-id="b3fe7-109">**Cliente** – Não conformidades deste tipo estão relacionadas a ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-109">**Customer** – Nonconformances of this type are related to sales orders.</span></span>
- <span data-ttu-id="b3fe7-110">**Fornecedor** – Não conformidades deste tipo estão relacionadas a ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-110">**Vendor** – Nonconformances of this type are related to purchase orders.</span></span>
- <span data-ttu-id="b3fe7-111">**Solicitação de serviço** – Não conformidades deste tipo estão relacionadas a ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-111">**Service request** – Nonconformances of this type are related to service orders.</span></span>
- <span data-ttu-id="b3fe7-112">**Produção** – Não conformidades deste tipo estão relacionadas a ordens de lote ou ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-112">**Production** – Nonconformances of this type are related to batch orders or production orders.</span></span>
- <span data-ttu-id="b3fe7-113">**Produção de coprodutos** – Não conformidades deste tipo estão relacionadas a ordens de lote para coprodutos.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-113">**Co-product production** – Nonconformances of this type are related to batch orders for co-products.</span></span>

<span data-ttu-id="b3fe7-114">Ao criar um novo tipo de problema, selecione **Tipos de não conformidade** no Painel de Ações para criar uma lista de um ou mais tipos de não conformidade que estão autorizados para o tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-114">When you create a new problem type, select **Non conformance types** on the Action Pane to create a list of one or more nonconformance types that are authorized for the problem type.</span></span> <span data-ttu-id="b3fe7-115">Por exemplo, um tipo de problema relacionado a um código de defeito pode ser aplicado a todos os tipos de não conformidade.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-115">For example, a problem type that is related to a defect code might apply to all nonconformance types.</span></span> <span data-ttu-id="b3fe7-116">No entanto, um tipo de problema relacionado a reclamações de clientes pode ser aplicado somente aos tipos de não conformidade **Cliente** e **Solicitação de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-116">However, a problem type that is related to customer complaints might apply only to the **Customer** and **Service request** nonconformance types.</span></span>

## <a name="examples-of-problem-types"></a><span data-ttu-id="b3fe7-117">Exemplos de tipos de problema</span><span class="sxs-lookup"><span data-stu-id="b3fe7-117">Examples of problem types</span></span>

<span data-ttu-id="b3fe7-118">Veja alguns exemplos de cenários de tipos de problema que podem ser usados com os diferentes tipos de não conformidade:</span><span class="sxs-lookup"><span data-stu-id="b3fe7-118">Here are some examples of scenarios for problem types that can be used with the different nonconformance types:</span></span>

- <span data-ttu-id="b3fe7-119">**Cliente:** um cliente registrou uma reclamação, um cliente fez uma devolução ou as especificações de qualidade não foram atendidas.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-119">**Customer:** A customer filed a complaint, a customer made a return, or quality specifications weren't met.</span></span>
- <span data-ttu-id="b3fe7-120">**Fornecedor:** o produto foi danificado, as especificações de qualidade não foram atendidas ou o produto incorreto foi recebido.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-120">**Vendor:** The product was damaged, quality specifications weren't met, or the wrong product was received.</span></span>
- <span data-ttu-id="b3fe7-121">**Solicitação de serviço:** as especificações de qualidade não foram atendidas, um cliente registrou uma reclamação ou a manutenção da máquina é necessária.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-121">**Service request:** Quality specifications weren't met, a customer filed a complaint, or machine maintenance is required.</span></span>
- <span data-ttu-id="b3fe7-122">**Produção:** as especificações de qualidade não foram atendidas, a manutenção da máquina é necessária ou o produto foi danificado.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-122">**Production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>
- <span data-ttu-id="b3fe7-123">**Produção de coprodutos:** as especificações de qualidade não foram atendidas, a manutenção da máquina é necessária ou o produto foi danificado.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-123">**Co-product production:** Quality specifications weren't met, machine maintenance is required, or the product was damaged.</span></span>

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a><span data-ttu-id="b3fe7-124">Criar um tipo de problema e atribuí-lo a tipos de não conformidade</span><span class="sxs-lookup"><span data-stu-id="b3fe7-124">Create a problem type and assign it to nonconformance types</span></span>

1. <span data-ttu-id="b3fe7-125">Vá para **Gerenciamento de estoque \> Configuração \> Gerenciamento de qualidade \> Tipos de problema**.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-125">Go to **Inventory management \> Setup \> Quality management \> Problem types**.</span></span>
1. <span data-ttu-id="b3fe7-126">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-126">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b3fe7-127">Defina os seguintes campos para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="b3fe7-127">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="b3fe7-128">**Tipo de problema** – Insira um nome ou uma ID exclusiva para o tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-128">**Problem type** – Enter a unique ID or name for the problem type.</span></span>
    - <span data-ttu-id="b3fe7-129">**Descrição** – Insira uma descrição detalhada do tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-129">**Description** – Enter a detailed description of the problem type.</span></span>

1. <span data-ttu-id="b3fe7-130">Enquanto a nova linha ainda estiver selecionada, selecione **Tipos de não conformidade** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-130">While the new row is still selected, select **Non conformance types** on the Action Pane.</span></span>
1. <span data-ttu-id="b3fe7-131">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-131">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="b3fe7-132">Em seguida, para a nova linha, defina o campo **Tipo de não conformidade** como o tipo de não conformidade que você deseja permitir para o tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-132">Then, for the new row, set the **Non conformance type** field to the nonconformance type that you want to allow for the problem type.</span></span>
1. <span data-ttu-id="b3fe7-133">Repita a etapa anterior para cada tipo de não conformidade adicional que você deseja autorizar para o tipo de problema.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-133">Repeat the previous step for each additional nonconformance type that you want to authorize for the problem type.</span></span>
1. <span data-ttu-id="b3fe7-134">Feche as páginas.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-134">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b3fe7-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b3fe7-135">Additional resources</span></span>

- [<span data-ttu-id="b3fe7-136">Visão geral do gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="b3fe7-136">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="b3fe7-137">Habilitar gerenciamento de qualidade e não conformidade</span><span class="sxs-lookup"><span data-stu-id="b3fe7-137">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="b3fe7-138">Trabalhadores responsáveis por aprovar não conformidades</span><span class="sxs-lookup"><span data-stu-id="b3fe7-138">Workers responsible for approving nonconformances</span></span>](quality-responsible-workers.md)
- [<span data-ttu-id="b3fe7-139">Zonas de quarentena para não conformidades</span><span class="sxs-lookup"><span data-stu-id="b3fe7-139">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="b3fe7-140">Tipos de diagnóstico para não conformidades</span><span class="sxs-lookup"><span data-stu-id="b3fe7-140">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="b3fe7-141">Encargos de qualidade para não conformidades</span><span class="sxs-lookup"><span data-stu-id="b3fe7-141">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="b3fe7-142">Operações para não conformidades</span><span class="sxs-lookup"><span data-stu-id="b3fe7-142">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="b3fe7-143">Gerenciamento de qualidade para processos de depósito</span><span class="sxs-lookup"><span data-stu-id="b3fe7-143">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
