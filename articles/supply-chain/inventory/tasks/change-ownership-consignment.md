---
title: "Alterar a propriedade de estoque de consignação com base na demanda de produção"
description: "Este procedimento mostra como alterar o proprietário de estoque de remessa do fornecedor à entidade legal quando há uma demanda para o estoque na produção."
author: perlynne
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: a665387244c571907afab24a54bc88580eca093e
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a><span data-ttu-id="64def-103">Alterar a propriedade de estoque de consignação com base na demanda de produção</span><span class="sxs-lookup"><span data-stu-id="64def-103">Change the ownership of consignment inventory based on production demand</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64def-104">Este procedimento mostra como alterar o proprietário de estoque de remessa do fornecedor à entidade legal quando há uma demanda para o estoque na produção.</span><span class="sxs-lookup"><span data-stu-id="64def-104">This procedure shows how to change the owner of consignment inventory from the vendor to your legal entity when there is demand for the inventory in production.</span></span> <span data-ttu-id="64def-105">Esta alteração de propriedade é feita criar e lançar um diário de alteração de propriedade do estoque.</span><span class="sxs-lookup"><span data-stu-id="64def-105">This change of ownership is done by creating and posting an inventory ownership change journal.</span></span> <span data-ttu-id="64def-106">As linhas de diário da alteração de propriedade podem ser criadas manualmente ou, como mostra do registro, com base em demanda existente de produção.</span><span class="sxs-lookup"><span data-stu-id="64def-106">The ownership change journal lines can be created manually or, as shown in this recording, based on existing production demand.</span></span> <span data-ttu-id="64def-107">Normalmente, um supervisor de fábrica executa esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="64def-107">Typically, a shop floor supervisor performs this task.</span></span> <span data-ttu-id="64def-108">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="64def-108">You can use this procedure in the USMF demo data company or on your own data.</span></span> <span data-ttu-id="64def-109">Se estiver usando seus próprios dados, verifique se você tem os seguintes pré-requisitos: um nome de diário de estoque que é configurado para a alteração de propriedade de estoque, itens disponíveis fisicamente de lucros registrados, e uma ou mais linhas de ordem de produção para material.</span><span class="sxs-lookup"><span data-stu-id="64def-109">If you're using your own data, make sure that you have the following prerequisites: an inventory journal name that has been set up for inventory ownership change, physically recorded vendor-owned on-hand items, and one or more production order lines for the material.</span></span> <span data-ttu-id="64def-110">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="64def-110">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>


## <a name="create-an-inventory-ownership-journal"></a><span data-ttu-id="64def-111">Criar um diário de propriedade de estoque</span><span class="sxs-lookup"><span data-stu-id="64def-111">Create an inventory ownership journal</span></span>
1. <span data-ttu-id="64def-112">Vá para Gerenciamento de estoque > Entradas de diário > Itens > Alteração de propriedade de estoque.</span><span class="sxs-lookup"><span data-stu-id="64def-112">Go to Inventory management > Journal entries > Items > Inventory ownership change.</span></span>
2. <span data-ttu-id="64def-113">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="64def-113">Click New.</span></span>
    * <span data-ttu-id="64def-114">O diário da alteração de propriedade de estoque é usado para alterar o proprietário de estoque de remessa do fornecedor à entidade legal atual.</span><span class="sxs-lookup"><span data-stu-id="64def-114">The inventory ownership change journal is used to change the owner of consignment inventory from the vendor to the current legal entity.</span></span> <span data-ttu-id="64def-115">Esta alteração de propriedade é feita liberando o estoque disponível que pertence o fornecedor e em seguida recebimento do estoque na entidade legal atual.</span><span class="sxs-lookup"><span data-stu-id="64def-115">This change of ownership is done by releasing the on-hand inventory that is owned by the vendor and then receiving that inventory in the current legal entity.</span></span>  
3. <span data-ttu-id="64def-116">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="64def-116">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="64def-117">Você só pode selecionar os nomes de diário de estoque com um tipo de diário de alteração de propriedade.</span><span class="sxs-lookup"><span data-stu-id="64def-117">You can select only inventory journal names that have a journal type of Ownership change.</span></span>  
4. <span data-ttu-id="64def-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="64def-118">Click OK.</span></span>
5. <span data-ttu-id="64def-119">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="64def-119">Click Functions.</span></span>
6. <span data-ttu-id="64def-120">Clique em Criar linhas de diário a partir de ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="64def-120">Click Create journal lines from production orders.</span></span>
    * <span data-ttu-id="64def-121">Você pode iniciar o processo a alteração de propriedade consultando todas as linhas de produção com a solicitação para o consumo de matéria-prima.</span><span class="sxs-lookup"><span data-stu-id="64def-121">You can start the change of ownership process by querying all the production lines that have demand for consumption of raw material.</span></span>  
7. <span data-ttu-id="64def-122">Os status de saída de estoque para incluir o campo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="64def-122">In the Inventory issue statuses to include field, select an option.</span></span>
    * <span data-ttu-id="64def-123">Esta opção permite filtrar por status de saída de transações de estoque.</span><span class="sxs-lookup"><span data-stu-id="64def-123">This option lets you filter by the issue status of the inventory transactions.</span></span> <span data-ttu-id="64def-124">Por exemplo, você pode criar linhas de diário do estoque com os status físicas separados e reservados.</span><span class="sxs-lookup"><span data-stu-id="64def-124">For example, you can create journal lines for inventory that has the Picked and Reserved physical statuses.</span></span>  
8. <span data-ttu-id="64def-125">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="64def-125">Expand the Records to include section.</span></span>
    * <span data-ttu-id="64def-126">Esta seção permite aplicar filtros adicionais.</span><span class="sxs-lookup"><span data-stu-id="64def-126">This section lets you apply additional filtering.</span></span> <span data-ttu-id="64def-127">Por exemplo, você pode selecionar uma data específica de matéria-prima.</span><span class="sxs-lookup"><span data-stu-id="64def-127">For example, you can select a specific raw material date.</span></span>  
9. <span data-ttu-id="64def-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="64def-128">Click OK.</span></span>

## <a name="post-the-inventory-ownership-change-journal"></a><span data-ttu-id="64def-129">Lançar o diário de alteração de propriedade de estoque</span><span class="sxs-lookup"><span data-stu-id="64def-129">Post the inventory ownership change journal</span></span>
1. <span data-ttu-id="64def-130">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="64def-130">Click Post.</span></span>
    * <span data-ttu-id="64def-131">Quando o diário for lançado, o estoque pertencido ao fornecedor é liberado usando uma referência "Alteração de posse".</span><span class="sxs-lookup"><span data-stu-id="64def-131">When the journal is posted, the vendor-owned inventory is released by using an "Ownership change" reference.</span></span> <span data-ttu-id="64def-132">O estoque é recebido em como disponíveis usando uma transação de estoque que é atualizada com um recebimento de produtos de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="64def-132">The inventory is then received as on-hand by using an inventory transaction that is updated with a purchase order product receipt.</span></span> <span data-ttu-id="64def-133">Observe que somente as transações relacionadas ao diário lançado serão criadas.</span><span class="sxs-lookup"><span data-stu-id="64def-133">Note that only transactions that are related to the posted journal are created.</span></span> <span data-ttu-id="64def-134">Nenhuma transação de estoque foi criada.</span><span class="sxs-lookup"><span data-stu-id="64def-134">No expected inventory transactions are created.</span></span>  
2. <span data-ttu-id="64def-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="64def-135">Click OK.</span></span>
3. <span data-ttu-id="64def-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="64def-136">Close the page.</span></span>

