---
title: Definir e manter canais de varejo
description: "Este tópico fornece uma visão geral do processo para a configuração de lojas físicas, que são referidas como lojas de varejo no Microsoft Dynamics 365 for Retail. Inclui informações sobre as tarefas que devem ser concluídas antes e depois de você configurar uma loja de varejo."
author: mugunthanm
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 055ff18b16fa2680c73564b7a7ef0c087c55e701
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="bc9e6-104">Definir e manter canais de varejo</span><span class="sxs-lookup"><span data-stu-id="bc9e6-104">Define and maintain retail channels</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="bc9e6-105">Este tópico fornece uma visão geral do processo para a configuração de lojas físicas, que são referidas como lojas de varejo no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as retail stores in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="bc9e6-106">Inclui informações sobre as tarefas que devem ser concluídas antes e depois de você configurar uma loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-106">It includes information about the tasks that you must complete both before and after you set up a retail store.</span></span>

<span data-ttu-id="bc9e6-107">O Dynamics 365 for Retail dá suporte a vários canais de varejo, como lojas online, call centers e lojas tradicionais.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-107">Dynamics 365 for Retail supports multiple retail channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="bc9e6-108">Uma loja física é chamada de loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-108">A brick-and-mortar store is called a retail store.</span></span> <span data-ttu-id="bc9e6-109">Cada loja de varejo pode ter seus próprios métodos de pagamento, grupos de preços, terminais de pontos de venda (PDV), contas de receita e despesa e equipe.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-109">Each retail store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="bc9e6-110">Você deve configurar todos esses elementos para uma loja de varejo antes de criá-la.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-110">You must set up all these elements for a retail store before you create it.</span></span> <span data-ttu-id="bc9e6-111">Depois de criar a loja de varejo, você atribui os produtos que deseja que a loja contenha.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-111">After you create the retail store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="bc9e6-112">Você também atribui funcionários, registradoras e clientes à loja.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="bc9e6-113">Por fim, você adiciona a nova loja a uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-retail-stores"></a><span data-ttu-id="bc9e6-114">Configurando lojas de varejo</span><span class="sxs-lookup"><span data-stu-id="bc9e6-114">Setting up retail stores</span></span>
<span data-ttu-id="bc9e6-115">Antes de configurar uma loja de varejo no Dynamics 365 for Retail, você deve concluir algumas tarefas necessárias.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-115">Before you can set up a retail store in Dynamics 365 for Retail, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="bc9e6-116">É possível criar a loja de varejo e adicionar detalhes.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-116">You can then create the retail store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="bc9e6-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bc9e6-117">Prerequisites</span></span>

<span data-ttu-id="bc9e6-118">Você deve concluir as seguintes tarefas antes de poder configurar uma loja de varejo:</span><span class="sxs-lookup"><span data-stu-id="bc9e6-118">You must complete the following tasks before you can set up a retail store:</span></span>

1.  <span data-ttu-id="bc9e6-119">Configure a estrutura de sua organização e configure hierarquias da organização para classificações, reabastecimento e relatório de varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2.  <span data-ttu-id="bc9e6-120">Configurar um depósito que representa a loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-120">Set up a warehouse that represents the retail store.</span></span>
3.  <span data-ttu-id="bc9e6-121">Configure sequências numéricas para lojas de varejo, as instruções de armazenamento e os comprovantes do demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-121">Set up number sequences for retail stores, store statements, and statement vouchers.</span></span>
4.  <span data-ttu-id="bc9e6-122">Configurar parâmetros para varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-122">Configure parameters for Retail.</span></span>
5.  <span data-ttu-id="bc9e6-123">Configurar os métodos de pagamento que a loja aceita.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-123">Set up the methods of payment that the store accepts.</span></span>
6.  <span data-ttu-id="bc9e6-124">Para processar transações de cartão de crédito em terminais de PDV, você também pode configurar os serviços de pagamento.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-124">To process credit card transactions at retail POS registers, you can also set up payment services.</span></span>
7.  <span data-ttu-id="bc9e6-125">Configurar grupos de impostos.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-125">Set up sales tax groups.</span></span>
8.  <span data-ttu-id="bc9e6-126">Configurar produtos de varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-126">Set up retail products.</span></span> <span data-ttu-id="bc9e6-127">Como parte desta tarefa, você também pode configurar hierarquias de produtos de varejo, variantes de produto, e classificações de produtos.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-127">As part of this task, you also set up retail product hierarchies, product variants, and product assortments.</span></span>
9.  <span data-ttu-id="bc9e6-128">Configurar grupos de preços de produtos.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-128">Set up product price groups.</span></span>
10. <span data-ttu-id="bc9e6-129">Configure preços de produtos de varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-129">Set up retail product pricing.</span></span> <span data-ttu-id="bc9e6-130">Como parte desta tarefa, você também pode configurar ajustes de preço, descontos, e períodos de desconto.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="bc9e6-131">Configurar membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-131">Set up staff members.</span></span> <span data-ttu-id="bc9e6-132">**Observação:** Você também deve atribuir permissões apropriadas para trabalhadores, de modo que eles possam se conectar e executar as tarefas usando o Microsoft Dynamics 365 for Retail para o sistema Retail POS.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-132">**Note:** You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the Dynamics 365 for Retail for Retail POS system.</span></span>
12. <span data-ttu-id="bc9e6-133">Configure os perfis do Retail POS a serem atribuídos à loja.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-133">Configure the Retail POS profiles to assign to the store.</span></span> <span data-ttu-id="bc9e6-134">Essa tarefa inclui várias tarefas como configurar registros, perfis offline e formatos e perfis de recebimento.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="bc9e6-135">Examine todas as tarefas incluídas no pré-requisito, e conclua apenas as tarefas que se aplicam a você.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-135">Review all the tasks that are included in the prerequisite, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-retail-store"></a><span data-ttu-id="bc9e6-136">Configurar uma loja de varejo</span><span class="sxs-lookup"><span data-stu-id="bc9e6-136">Set up a retail store</span></span>

<span data-ttu-id="bc9e6-137">Depois de concluir as tarefas necessárias, conclua estas tarefas para configurar os detalhes da loja de varejo:</span><span class="sxs-lookup"><span data-stu-id="bc9e6-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the retail store:</span></span>

1.  <span data-ttu-id="bc9e6-138">Crie uma loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-138">Create a retail store.</span></span>
2.  <span data-ttu-id="bc9e6-139">Atribua um grupo de impostos à loja.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-139">Assign a sales tax group to the store.</span></span>
3.  <span data-ttu-id="bc9e6-140">Atribuir os métodos de pagamento aceitos à loja.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-140">Assign the accepted payment methods to the store.</span></span>
4.  <span data-ttu-id="bc9e6-141">Adicione detalhes às descrições do produto para os produtos que você oferece em suas lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-141">Add details to the product descriptions for products that you offer in your retail stores.</span></span> <span data-ttu-id="bc9e6-142">Por exemplo, você pode adicionar rich text e imagens.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="bc9e6-143">Esses detalhes de produto aparecem em vários contextos, como na registradora de PDV ou rótulos impressos.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5.  <span data-ttu-id="bc9e6-144">Adicione a loja à hierarquia organizacional padrão que tem por finalidade **Sortimento de varejo**, **Reabastecimento de varejo** ou **Relatório de varejo**.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-retail-store"></a><span data-ttu-id="bc9e6-145">Após configurar uma loja de varejo</span><span class="sxs-lookup"><span data-stu-id="bc9e6-145">After you set up a retail store</span></span>

<span data-ttu-id="bc9e6-146">Depois de inserir os detalhes da loja de varejo, conclua estas tarefas para enviar os dados da nova loja de varejo para o Retail POS:</span><span class="sxs-lookup"><span data-stu-id="bc9e6-146">After you enter the details for the retail store, complete these tasks to send the new retail store data to Retail POS:</span></span>

1.  <span data-ttu-id="bc9e6-147">Configurar terminais de PDV para a loja.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-147">Configure the POS registers for the store.</span></span>
2.  <span data-ttu-id="bc9e6-148">Atribuir classificações de produtos à loja.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-148">Assign product assortments to the store.</span></span>
3.  <span data-ttu-id="bc9e6-149">Processe as classificações para gerar a lista de produtos que são incluídos na classificação e para disponibilizar os disponíveis na loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store.</span></span>
4.  <span data-ttu-id="bc9e6-150">Envie dados como sequências numéricas, perfis de hardware, layouts de tela de PDV para as registradoras do Retail POS.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.</span></span>
5.  <span data-ttu-id="bc9e6-151">Publique a loja de varejo para enviar dados da loja para o Retail POS..</span><span class="sxs-lookup"><span data-stu-id="bc9e6-151">Publish the retail store to send store data to Retail POS.</span></span>
6.  <span data-ttu-id="bc9e6-152">Execute os trabalhos para enviar os dados da loja para o Retail POS.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-152">Run the jobs to send the store data to Retail POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="bc9e6-153">Hierarquias da organização</span><span class="sxs-lookup"><span data-stu-id="bc9e6-153">Organization hierarchies</span></span>
<span data-ttu-id="bc9e6-154">O Retail usa hierarquias da organização para estruturar canais de varejo.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-154">Retail uses organization hierarchies to structure retail channels.</span></span> <span data-ttu-id="bc9e6-155">As hierarquias da organização representam os relacionamentos entre as organizações que compõem sua empresa.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="bc9e6-156">Ao configurar lojas, você pode adicioná-las a uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="bc9e6-157">As lojas compartilham dados usados para classificações, reabastecimento e relatórios.</span><span class="sxs-lookup"><span data-stu-id="bc9e6-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>




