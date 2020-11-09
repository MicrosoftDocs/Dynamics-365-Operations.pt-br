---
title: Atributos de lote
description: Este tópico fornece informações sobre atributos de lote. Os atributos de lote são características de matérias-primas e produtos acabados que compõem os lotes de estoque. O tópico também explica como atribuir atributos de lote e como você pode pesquisar neles ao reservar lotes.
author: ShylaThompson
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup, WHSBatchAttribReserve
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 370893e415a79091404f1c4eb0404ba8fd5b9ff2
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017514"
---
# <a name="batch-attributes"></a><span data-ttu-id="1be15-105">Atributos de lote</span><span class="sxs-lookup"><span data-stu-id="1be15-105">Batch attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1be15-106">Este tópico fornece informações sobre atributos de lote.</span><span class="sxs-lookup"><span data-stu-id="1be15-106">This topic provides information about batch attributes.</span></span> <span data-ttu-id="1be15-107">Os atributos de lote são características de matérias-primas e produtos acabados que compõem os lotes de estoque.</span><span class="sxs-lookup"><span data-stu-id="1be15-107">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="1be15-108">O tópico também explica como atribuir atributos de lote e como você pode pesquisar neles ao reservar lotes.</span><span class="sxs-lookup"><span data-stu-id="1be15-108">The topic also explains how to assign batch attributes, and how you can search on them when you reserve batches.</span></span>

<span data-ttu-id="1be15-109">Os atributos de lote são características de matérias-primas e produtos acabados que compõem os lotes de estoque.</span><span class="sxs-lookup"><span data-stu-id="1be15-109">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="1be15-110">Os atributos de lote podem variar, dependendo de fatores como as condições do ambiente, a qualidade de matérias-primas usadas para produzir o lote ou o resultado do produto acabado.</span><span class="sxs-lookup"><span data-stu-id="1be15-110">Batch attributes can vary, depending on factors such as environmental conditions, the quality of the raw materials that are used to produce the batch, or the outcome of the finished product.</span></span> <span data-ttu-id="1be15-111">O número e os tipos de atributos de lote que são usados podem variar muito de um setor para outro.</span><span class="sxs-lookup"><span data-stu-id="1be15-111">The number and types of batch attributes that are used can vary widely from one industry to another.</span></span> <span data-ttu-id="1be15-112">Veja a seguir dois exemplos que mostram como usar atributos de lote:</span><span class="sxs-lookup"><span data-stu-id="1be15-112">Here are two examples that show how to use batch attributes:</span></span>

-   <span data-ttu-id="1be15-113">Na indústria de queijo, o leite, que é uma das matérias-primas usadas para fabricar o queijo, pode ter atributos como gordura e porcentagem de peso.</span><span class="sxs-lookup"><span data-stu-id="1be15-113">In the cheese industry, milk, which is one of the raw materials that are used to produce the cheese, can have attributes such as fat content and percentage weight.</span></span> <span data-ttu-id="1be15-114">O queijo que é produzido do leite pode ter outros atributos, como o teor de umidade e idade.</span><span class="sxs-lookup"><span data-stu-id="1be15-114">The cheese that is produced from the milk can have other attributes, such as moisture and age.</span></span>
-   <span data-ttu-id="1be15-115">Na indústria siderúrgica, o ferro que é produzido pode ter atributos, como as porcentagens de teor de magnésio, prata e zinco.</span><span class="sxs-lookup"><span data-stu-id="1be15-115">In the steel industry, the iron that is produced might have attributes such as the percentages of magnesium content, silver content, and zinc content.</span></span>

<span data-ttu-id="1be15-116">Para gerenciar melhor o número e os tipos de atributos, você pode usar os grupos de atributos de lote.</span><span class="sxs-lookup"><span data-stu-id="1be15-116">To better manage the number and types of attributes, you can use batch attribute groups.</span></span> <span data-ttu-id="1be15-117">Dessa forma, você não precisará adicionar cada atributo individualmente.</span><span class="sxs-lookup"><span data-stu-id="1be15-117">In this way, you don't have to add each attribute individually.</span></span>

## <a name="assign-batch-attributes"></a><span data-ttu-id="1be15-118">Atribuir atributos de lote</span><span class="sxs-lookup"><span data-stu-id="1be15-118">Assign batch attributes</span></span>
<span data-ttu-id="1be15-119">Você pode atribuir atributos de lote a produtos individuais que são mantidos em lotes de estoque, ou você pode atribuí-los a produtos associados a clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="1be15-119">You can assign batch attributes to individual products that are held in inventory batches, or you can assign them to products that are associated with specific customers.</span></span> <span data-ttu-id="1be15-120">Antes de atribuir um atributo de lote no nível do cliente, primeiro você deverá atribuí-lo no nível do produto.</span><span class="sxs-lookup"><span data-stu-id="1be15-120">Before you can assign a batch attribute at the customer level, you must assign it at the product level.</span></span> <span data-ttu-id="1be15-121">O produto deve ter a dimensão de lote definida como **Ativa** no grupo de dimensão de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="1be15-121">The product must have the batch dimension set to **Active** in the tracking dimension group.</span></span> <span data-ttu-id="1be15-122">Para atribuir um atributo de lote a um produto individual, use a página específica do produto.</span><span class="sxs-lookup"><span data-stu-id="1be15-122">To assign a batch attribute to an individual product, use the product-specific page.</span></span> <span data-ttu-id="1be15-123">Se o atributo for específico de um produto para um cliente, use a página específica do cliente.</span><span class="sxs-lookup"><span data-stu-id="1be15-123">If the attribute is specific to a product for a customer, use the customer-specific page.</span></span> <span data-ttu-id="1be15-124">Quando você adiciona um atributo a um produto, você também define outros parâmetros.</span><span class="sxs-lookup"><span data-stu-id="1be15-124">When you add an attribute to a product, you also define other parameters.</span></span> <span data-ttu-id="1be15-125">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="1be15-125">Here are some examples:</span></span>

-   <span data-ttu-id="1be15-126">Os intervalos mínimo e máximo de um atributo do tipo **Inteiro** ou **Fração**.</span><span class="sxs-lookup"><span data-stu-id="1be15-126">The minimum and maximum ranges for an attribute of the **Integer** or **Fraction** type.</span></span>
-   <span data-ttu-id="1be15-127">As ações de tolerância para um atributo do tipo **Inteiro** ou **Fração**.</span><span class="sxs-lookup"><span data-stu-id="1be15-127">The tolerance actions for an attribute of the **Integer** or **Fraction** type.</span></span> <span data-ttu-id="1be15-128">Se o valor do atributo estiver fora do intervalo mínimo e máximo, a ação pode ser uma mensagem de aviso ou uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="1be15-128">If the value of the attribute falls outside the minimum and maximum range, the action can be either a warning message or an error message.</span></span>
-   <span data-ttu-id="1be15-129">O valor de meta do atributo.</span><span class="sxs-lookup"><span data-stu-id="1be15-129">The target value for the attribute.</span></span> <span data-ttu-id="1be15-130">Esse é o melhor valor do atributo, e se aplica a todos os tipos de atributo.</span><span class="sxs-lookup"><span data-stu-id="1be15-130">This value is the optimal value of the attribute, and it applies to all attribute types.</span></span>

<span data-ttu-id="1be15-131">Você pode acessar as páginas dos produtos selecionados na página de **Produtos liberados** no Gerenciamento de informações do produto.</span><span class="sxs-lookup"><span data-stu-id="1be15-131">You can access the pages for products that you select on the **Released products** page in Product information management.</span></span> <span data-ttu-id="1be15-132">Depois de atribuir atributos de lote a um produto, você poderá adicionar valores específicos aos atributos na página **Atributos de lotes de estoque**.</span><span class="sxs-lookup"><span data-stu-id="1be15-132">After you assign batch attributes to a product, you can add specific values to the attributes on the **Inventory batch attributes** page.</span></span>

## <a name="reserve-batches"></a><span data-ttu-id="1be15-133">Reservar lotes</span><span class="sxs-lookup"><span data-stu-id="1be15-133">Reserve batches</span></span>
<span data-ttu-id="1be15-134">Você pode pesquisar em atributos de lote ao processar as reservas de lote para uma ordem de venda a fim de atender ao pedido de um cliente, ou quando você escolhe e reserva lotes para uma ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="1be15-134">You can search on batch attributes when you do batch reservations for a sales order to fulfill a customer's order, or when you pick and reserve batches for a production order.</span></span> <span data-ttu-id="1be15-135">A pesquisa ajuda a localizar um lote de estoque que contém o produto que tem o atributo de lote que você deseja.</span><span class="sxs-lookup"><span data-stu-id="1be15-135">The search helps locate an inventory batch that contains the product that has the batch attribute that you want.</span></span> <span data-ttu-id="1be15-136">Depois de localizar o lote ou os lotes, será possível reservar o produto na linha de transação de estoque de origem.</span><span class="sxs-lookup"><span data-stu-id="1be15-136">After you locate the batch or batches, you can reserve the product to the originating inventory transaction line.</span></span>



