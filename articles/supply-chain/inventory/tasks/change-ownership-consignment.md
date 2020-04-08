---
title: Alterar a propriedade de estoque de consignação com base na demanda de produção
description: Este procedimento mostra como alterar o proprietário de estoque de remessa do fornecedor à entidade legal quando há uma demanda para o estoque na produção.
author: perlynne
manager: AnnBe
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8200e0235fa78cbef4fdadd1d1c124446b89e72a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145862"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="608cb-103">Alterar a propriedade de estoque de consignação com base na demanda de produção</span><span class="sxs-lookup"><span data-stu-id="608cb-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="608cb-104">Este procedimento mostra como alterar o proprietário de estoque de remessa do fornecedor à entidade legal quando há uma demanda para o estoque na produção.</span><span class="sxs-lookup"><span data-stu-id="608cb-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="608cb-105">Esta alteração de propriedade é feita criar e lançar um diário de alteração de propriedade do estoque.</span><span class="sxs-lookup"><span data-stu-id="608cb-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="608cb-106">As linhas de diário da alteração de propriedade podem ser criadas manualmente ou, como mostra do registro, com base em demanda existente de produção.</span><span class="sxs-lookup"><span data-stu-id="608cb-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="608cb-107">Normalmente, um supervisor de fábrica executa esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="608cb-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="608cb-108">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="608cb-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="608cb-109">Se estiver usando seus próprios dados, verifique se você tem os seguintes pré-requisitos: um nome de diário de estoque que é configurado para a alteração de propriedade de estoque, itens disponíveis fisicamente de lucros registrados, e uma ou mais linhas de ordem de produção para material.</span><span class="sxs-lookup"><span data-stu-id="608cb-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="608cb-110">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="608cb-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

> [!NOTE]
> <span data-ttu-id="608cb-111">Além de os processos de consignação de saída não receberem suporte imediato, o processamento automático do diário de propriedade não é compatível.</span><span class="sxs-lookup"><span data-stu-id="608cb-111">Outbound consignment processes are not supported out-of-the-box and automatic ownership journal processing is not supported.</span></span>

## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="608cb-112">Criar um diário de propriedade de estoque</span><span class="sxs-lookup"><span data-stu-id="608cb-112">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="608cb-113">Vá para Gerenciamento de estoque > Entradas de diário > Itens > Alteração de propriedade de estoque.</span><span class="sxs-lookup"><span data-stu-id="608cb-113">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="608cb-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="608cb-114">Click New.</span></span>
    * <span data-ttu-id="608cb-115">O diário da alteração de propriedade de estoque é usado para alterar o proprietário de estoque de remessa do fornecedor à entidade legal atual.</span><span class="sxs-lookup"><span data-stu-id="608cb-115">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="608cb-116">Esta alteração de propriedade é feita liberando o estoque disponível que pertence o fornecedor e em seguida recebimento do estoque na entidade legal atual.</span><span class="sxs-lookup"><span data-stu-id="608cb-116">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="608cb-117">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="608cb-117">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="608cb-118">Você só pode selecionar os nomes de diário de estoque com um tipo de diário de alteração de propriedade.</span><span class="sxs-lookup"><span data-stu-id="608cb-118">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="608cb-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="608cb-119">Click OK.</span></span>
5. <span data-ttu-id="608cb-120">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="608cb-120">Click Functions.</span></span>
6. <span data-ttu-id="608cb-121">Clique em Criar linhas de diário a partir de ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="608cb-121">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="608cb-122">Você pode iniciar o processo a alteração de propriedade consultando todas as linhas de produção com a solicitação para o consumo de matéria-prima.</span><span class="sxs-lookup"><span data-stu-id="608cb-122">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="608cb-123">Os status de saída de estoque para incluir o campo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="608cb-123">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="608cb-124">Esta opção permite filtrar por status de saída de transações de estoque.</span><span class="sxs-lookup"><span data-stu-id="608cb-124">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="608cb-125">Por exemplo, você pode criar linhas de diário do estoque com os status físicas separados e reservados.</span><span class="sxs-lookup"><span data-stu-id="608cb-125">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="608cb-126">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="608cb-126">Expand the Records to include section.</span></span>
    * <span data-ttu-id="608cb-127">Esta seção permite aplicar filtros adicionais.</span><span class="sxs-lookup"><span data-stu-id="608cb-127">This section lets you apply additional filtering.</span></span> <span data-ttu-id="608cb-128">Por exemplo, você pode selecionar uma data específica de matéria-prima.</span><span class="sxs-lookup"><span data-stu-id="608cb-128">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="608cb-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="608cb-129">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="608cb-130">Lançar o diário de alteração de propriedade de estoque</span><span class="sxs-lookup"><span data-stu-id="608cb-130">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="608cb-131">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="608cb-131">Click Post.</span></span>
    * <span data-ttu-id="608cb-132">Quando o diário for lançado, o estoque pertencido ao fornecedor é liberado usando uma referência "Alteração de posse".</span><span class="sxs-lookup"><span data-stu-id="608cb-132">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="608cb-133">O estoque é recebido em como disponíveis usando uma transação de estoque que é atualizada com um recebimento de produtos de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="608cb-133">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="608cb-134">Observe que somente as transações relacionadas ao diário lançado serão criadas.</span><span class="sxs-lookup"><span data-stu-id="608cb-134">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="608cb-135">Nenhuma transação de estoque foi criada.</span><span class="sxs-lookup"><span data-stu-id="608cb-135">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="608cb-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="608cb-136">Click OK.</span></span>
3. <span data-ttu-id="608cb-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="608cb-137">Close the page.</span></span>

