---
title: Definir e manter canais de varejo
description: Este tópico apresenta uma visão geral do processo de configurar lojas físicas, também chamadas de lojas no Dynamics 365 Commerce. Inclui informações sobre as tarefas que devem ser realizadas antes e depois de você configurar uma loja.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 51524ad6918d962d70a8a700f135f96e236f7d34
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000866"
---
# <a name="define-and-maintain-retail-channels"></a><span data-ttu-id="d2501-104">Definir e manter canais de varejo</span><span class="sxs-lookup"><span data-stu-id="d2501-104">Define and maintain retail channels</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d2501-105">Este tópico apresenta uma visão geral do processo de configurar lojas físicas, também chamadas de lojas no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d2501-105">This topic provides an overview of the process for setting up brick-and-mortar stores, which are referred to as stores in Dynamics 365 Commerce.</span></span> <span data-ttu-id="d2501-106">Inclui informações sobre as tarefas que devem ser realizadas antes e depois de você configurar uma loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-106">It includes information about the tasks that you must complete both before and after you set up a store.</span></span>

<span data-ttu-id="d2501-107">O Commerce dá suporte para vários canais, como lojas online, call centers e lojas físicas.</span><span class="sxs-lookup"><span data-stu-id="d2501-107">Commerce supports multiple channels, such as online stores, call centers, and brick-and-mortar stores.</span></span> <span data-ttu-id="d2501-108">Uma loja física é chamada de loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-108">A brick-and-mortar store is called a store.</span></span> <span data-ttu-id="d2501-109">Cada loja pode ter seus próprios métodos de pagamento, grupos de preços, registradoras de ponto de venda (POS), contas de renda e de despesa, e equipe.</span><span class="sxs-lookup"><span data-stu-id="d2501-109">Each store can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="d2501-110">Você deve configurar todos esses elementos de uma loja antes de criá-la.</span><span class="sxs-lookup"><span data-stu-id="d2501-110">You must set up all these elements for a store before you create it.</span></span> <span data-ttu-id="d2501-111">Depois de criar a loja, você atribui os produtos que deseja que ela tenha.</span><span class="sxs-lookup"><span data-stu-id="d2501-111">After you create the store, you assign the products that you want it to carry.</span></span> <span data-ttu-id="d2501-112">Você também atribui funcionários, registradoras e clientes à loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-112">You also assign employees, registers, and customers to the store.</span></span> <span data-ttu-id="d2501-113">Por fim, você adiciona a nova loja a uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="d2501-113">Finally, you add the new store to an organization hierarchy.</span></span>

## <a name="setting-up-stores"></a><span data-ttu-id="d2501-114">Configurando armazenamentos</span><span class="sxs-lookup"><span data-stu-id="d2501-114">Setting up stores</span></span>

<span data-ttu-id="d2501-115">Para configurar uma loja no Commerce, você deve executar algumas tarefas necessárias.</span><span class="sxs-lookup"><span data-stu-id="d2501-115">Before you can set up a store in Commerce, you must complete some prerequisite tasks.</span></span> <span data-ttu-id="d2501-116">É possível criar a loja e adicionar detalhes.</span><span class="sxs-lookup"><span data-stu-id="d2501-116">You can then create the store and add details.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="d2501-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d2501-117">Prerequisites</span></span>

<span data-ttu-id="d2501-118">Você deve executar as seguintes tarefas antes de configurar uma loja:</span><span class="sxs-lookup"><span data-stu-id="d2501-118">You must complete the following tasks before you can set up a store:</span></span>

1. <span data-ttu-id="d2501-119">Configure a estrutura de sua organização e configure hierarquias da organização para classificações, reabastecimento e relatório de varejo.</span><span class="sxs-lookup"><span data-stu-id="d2501-119">Configure your organization structure, and set up organization hierarchies for retail assortments, replenishment, and reporting.</span></span>
2. <span data-ttu-id="d2501-120">Configure um depósito que represente a loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-120">Set up a warehouse that represents the store.</span></span>
3. <span data-ttu-id="d2501-121">Configure sequências numéricas para lojas, demonstrativos de loja e comprovantes de demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="d2501-121">Set up number sequences for stores, store statements, and statement vouchers.</span></span>
4. <span data-ttu-id="d2501-122">Configure parâmetros para o Commerce.</span><span class="sxs-lookup"><span data-stu-id="d2501-122">Configure parameters for Commerce.</span></span>
5. <span data-ttu-id="d2501-123">Configurar os métodos de pagamento que a loja aceita.</span><span class="sxs-lookup"><span data-stu-id="d2501-123">Set up the methods of payment that the store accepts.</span></span>
6. <span data-ttu-id="d2501-124">Para processar transações de cartão de crédito em terminais de PDV, você também pode configurar os serviços de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d2501-124">To process credit card transactions at POS registers, you can also set up payment services.</span></span>
7. <span data-ttu-id="d2501-125">Configurar grupos de impostos.</span><span class="sxs-lookup"><span data-stu-id="d2501-125">Set up sales tax groups.</span></span>
8. <span data-ttu-id="d2501-126">Configure produtos.</span><span class="sxs-lookup"><span data-stu-id="d2501-126">Set up products.</span></span> <span data-ttu-id="d2501-127">Como parte desta tarefa, você também pode configurar hierarquias, grades e classificações de produtos.</span><span class="sxs-lookup"><span data-stu-id="d2501-127">As part of this task, you also set up product hierarchies, product variants, and product assortments.</span></span>
9. <span data-ttu-id="d2501-128">Configurar grupos de preços de produtos.</span><span class="sxs-lookup"><span data-stu-id="d2501-128">Set up product price groups.</span></span>
10. <span data-ttu-id="d2501-129">Configure os preços dos produtos.</span><span class="sxs-lookup"><span data-stu-id="d2501-129">Set up product pricing.</span></span> <span data-ttu-id="d2501-130">Como parte desta tarefa, você também pode configurar ajustes de preço, descontos, e períodos de desconto.</span><span class="sxs-lookup"><span data-stu-id="d2501-130">As part of this task, you also set up price adjustments, discounts, and discount periods.</span></span>
11. <span data-ttu-id="d2501-131">Configurar membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="d2501-131">Set up staff members.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2501-132">Você também deve atribuir permissões apropriadas aos trabalhadores para que eles possam se conectar e executar tarefas usando o sistema POS.</span><span class="sxs-lookup"><span data-stu-id="d2501-132">You must also assign appropriate permissions to the workers, so that they can sign in and perform tasks by using the POS system.</span></span>

12. <span data-ttu-id="d2501-133">Configure os perfis de PDV a serem atribuídos à loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-133">Configure the POS profiles to assign to the store.</span></span> <span data-ttu-id="d2501-134">Essa tarefa inclui várias tarefas como configurar registros, perfis offline e formatos e perfis de recebimento.</span><span class="sxs-lookup"><span data-stu-id="d2501-134">This task includes many other tasks, such as setting up registers, setting up offline profiles, and setting up receipt formats and profiles.</span></span>

<span data-ttu-id="d2501-135">Examine todas as tarefas incluídas nos pré-requisitos e execute somente as que se aplicam a você.</span><span class="sxs-lookup"><span data-stu-id="d2501-135">Review all the tasks that are included in the prerequisites, and complete only the tasks that apply to you.</span></span>

### <a name="set-up-a-store"></a><span data-ttu-id="d2501-136">Configurar uma loja</span><span class="sxs-lookup"><span data-stu-id="d2501-136">Set up a store</span></span>

<span data-ttu-id="d2501-137">Depois de concluir as tarefas necessárias, execute estas tarefas para configurar os detalhes da loja:</span><span class="sxs-lookup"><span data-stu-id="d2501-137">After you complete the prerequisite tasks, complete these tasks to set up the details for the store:</span></span>

1. <span data-ttu-id="d2501-138">Crie uma loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-138">Create a store.</span></span>
2. <span data-ttu-id="d2501-139">Atribua um grupo de impostos à loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-139">Assign a sales tax group to the store.</span></span>
3. <span data-ttu-id="d2501-140">Atribuir os métodos de pagamento aceitos à loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-140">Assign the accepted payment methods to the store.</span></span>
4. <span data-ttu-id="d2501-141">Adicione detalhes às descrições dos produtos que você oferece em suas lojas.</span><span class="sxs-lookup"><span data-stu-id="d2501-141">Add details to the product descriptions for products that you offer in your stores.</span></span> <span data-ttu-id="d2501-142">Por exemplo, você pode adicionar rich text e imagens.</span><span class="sxs-lookup"><span data-stu-id="d2501-142">For example, you can add rich text and images.</span></span> <span data-ttu-id="d2501-143">Esses detalhes de produto aparecem em vários contextos, como na registradora de PDV ou rótulos impressos.</span><span class="sxs-lookup"><span data-stu-id="d2501-143">These product details appear in various contexts, such as on the POS register or on printed labels.</span></span>
5. <span data-ttu-id="d2501-144">Adicione a loja à hierarquia organizacional padrão que tem por finalidade **Sortimento de varejo**, **Reabastecimento de varejo** ou **Relatório de varejo**.</span><span class="sxs-lookup"><span data-stu-id="d2501-144">Add the store to the default organization hierarchy that is assigned to a purpose of **Retail assortment**, **Retail replenishment**, or **Retail reporting**.</span></span>

### <a name="after-you-set-up-a-store"></a><span data-ttu-id="d2501-145">Depois de configurar uma loja</span><span class="sxs-lookup"><span data-stu-id="d2501-145">After you set up a store</span></span>

<span data-ttu-id="d2501-146">Depois de inserir os detalhes da loja, execute estas tarefas para enviar os dados da nova loja ao PDV:</span><span class="sxs-lookup"><span data-stu-id="d2501-146">After you enter the details for the store, complete these tasks to send the new store data to POS:</span></span>

1. <span data-ttu-id="d2501-147">Configurar terminais de PDV para a loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-147">Configure the POS registers for the store.</span></span>
2. <span data-ttu-id="d2501-148">Atribuir classificações de produtos à loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-148">Assign product assortments to the store.</span></span>
3. <span data-ttu-id="d2501-149">Processe as classificações para gerar a lista de produtos incluídos na classificação e disponibilizar os produtos na loja.</span><span class="sxs-lookup"><span data-stu-id="d2501-149">Process assortments to generate the list of products that are included in the assortment and to make the products available in the store.</span></span>
4. <span data-ttu-id="d2501-150">Envie dados, como sequências numéricas, perfis de hardware, layouts de tela de PDV, para os terminais do PDV.</span><span class="sxs-lookup"><span data-stu-id="d2501-150">Send data such as number sequences, hardware profiles, and POS screen layouts to the POS registers.</span></span>
5. <span data-ttu-id="d2501-151">Publique a loja para enviar dados da loja ao PDV.</span><span class="sxs-lookup"><span data-stu-id="d2501-151">Publish the store to send store data to POS.</span></span>
6. <span data-ttu-id="d2501-152">Execute os trabalhos para enviar os dados da loja ao PDV.</span><span class="sxs-lookup"><span data-stu-id="d2501-152">Run the jobs to send the store data to POS.</span></span>

## <a name="organization-hierarchies"></a><span data-ttu-id="d2501-153">Hierarquias da organização</span><span class="sxs-lookup"><span data-stu-id="d2501-153">Organization hierarchies</span></span>

<span data-ttu-id="d2501-154">O Commerce usa hierarquias da organização para estruturar canais.</span><span class="sxs-lookup"><span data-stu-id="d2501-154">Commerce uses organization hierarchies to structure channels.</span></span> <span data-ttu-id="d2501-155">As hierarquias da organização representam os relacionamentos entre as organizações que compõem sua empresa.</span><span class="sxs-lookup"><span data-stu-id="d2501-155">Organization hierarchies represent the relationships between the organizations that make up your business.</span></span> <span data-ttu-id="d2501-156">Ao configurar lojas, você pode adicioná-las a uma hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="d2501-156">When you set up stores, you can add them to an organization hierarchy.</span></span> <span data-ttu-id="d2501-157">As lojas compartilham dados usados para classificações, reabastecimento e relatórios.</span><span class="sxs-lookup"><span data-stu-id="d2501-157">The stores then share data that is used for assortments, replenishment, and reporting.</span></span>

> [!NOTE]
> <span data-ttu-id="d2501-158">Para usar a funcionalidade de vendas do Commerce, a chave de configuração **Diversos endereços de remessa** deve estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="d2501-158">To use Commerce sales functionality, the configuration key for **Multiple ship-to** must be enabled.</span></span> <span data-ttu-id="d2501-159">Essa chave de configuração pode ser encontrada nas chaves **Configuração de troca** em **Administração do sistema**\> **Configuração** \> **Configurações do sistema**.</span><span class="sxs-lookup"><span data-stu-id="d2501-159">This configuration key can be found in the **Trade configuration** keys under **System Administration**\> **Setup** \> **License Configuration**.</span></span> <span data-ttu-id="d2501-160">Isso é necessário devido a várias validações com base no endereço de entrega configurado no nível da linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d2501-160">This is required due to various validations based on the delivery address configured at the sales order line level.</span></span>

