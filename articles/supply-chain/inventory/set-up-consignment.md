---
title: Configurando consignação
description: Este tópico explica como configurar operações de estoque de entrada de consignação.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 51f7d6b0402ebbed417554978fc8d927f6b9c606
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422456"
---
# <a name="set-up-consignment"></a><span data-ttu-id="17754-103">Configurando consignação</span><span class="sxs-lookup"><span data-stu-id="17754-103">Set up consignment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="17754-104">Este tópico explica como configurar operações de estoque de entrada de consignação.</span><span class="sxs-lookup"><span data-stu-id="17754-104">This topic explains how to configure inbound consignment inventory operations.</span></span>

<span data-ttu-id="17754-105">Estoque em consignação é o estoque a que pertence a um fornecedor, mas está armazenado em seu site.</span><span class="sxs-lookup"><span data-stu-id="17754-105">Consignment inventory is inventory that’s owned by a vendor, but stored at your site.</span></span> <span data-ttu-id="17754-106">Quando estiver pronto para consumir ou usar o estoque, você obterá sobre a propriedade de estoque.</span><span class="sxs-lookup"><span data-stu-id="17754-106">When you’re ready to consume or use the inventory, you take over the ownership of the inventory.</span></span> <span data-ttu-id="17754-107">Este tópico descreve a configuração necessária habilitar processos de consignação.</span><span class="sxs-lookup"><span data-stu-id="17754-107">This topic describes the setup needed to enable consignment processes.</span></span> <span data-ttu-id="17754-108">Para obter mais informações sobre processos de consignação, consulte [Configurar a consignação](consignment.md).</span><span class="sxs-lookup"><span data-stu-id="17754-108">For more information about consignment processes, see [Set up consignment](consignment.md).</span></span>

## <a name="inventory-owners"></a><span data-ttu-id="17754-109">Proprietários de estoque</span><span class="sxs-lookup"><span data-stu-id="17754-109">Inventory owners</span></span>
<span data-ttu-id="17754-110">Para registrar o estoque físico de entrada em consignação, você precisa definir o proprietário do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="17754-110">In order to record physical inbound consignment inventory, you need to define a vendor owner.</span></span> <span data-ttu-id="17754-111">Isso é feito na página **Proprietário de estoque**.</span><span class="sxs-lookup"><span data-stu-id="17754-111">This is done on the **Inventory owner** page.</span></span> <span data-ttu-id="17754-112">Quando você seleciona uma **Conta de fornecedor** isso gera valores padrão para os campos **Nome** e **Proprietário**.</span><span class="sxs-lookup"><span data-stu-id="17754-112">When you select a **Vendor account** this generates default values for the **Name** and **Owner** fields.</span></span> <span data-ttu-id="17754-113">O valor no campo **Proprietário** ficará visível ao fornecedor, para que você possa alterá-lo se os nomes de contas do fornecedor não forem fáceis para os contatos externos reconhecerem.</span><span class="sxs-lookup"><span data-stu-id="17754-113">The value in the **Owner** field will be visible to the vendor, so you might want to change it if your vendor account names aren’t easy for external people to recognize.</span></span> <span data-ttu-id="17754-114">É possível editar o campo **Proprietário**, mas somente até o ponto em que você salvar o registro **Proprietário de estoque**.</span><span class="sxs-lookup"><span data-stu-id="17754-114">It’s possible to edit the **Owner** field, but only up to the point when you save the **Inventory owner** record.</span></span> <span data-ttu-id="17754-115">O campo **Nome** é preenchido com o nome do participante da conta do fornecedor está associada, e este não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="17754-115">The **Name** field is populated with the name of the party that the vendor account is associated with, and this cannot be changed.</span></span>

<span data-ttu-id="17754-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span><span class="sxs-lookup"><span data-stu-id="17754-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span></span>

## <a name="tracking-dimension-group"></a><span data-ttu-id="17754-117">Grupo de dimensões de rastreamento</span><span class="sxs-lookup"><span data-stu-id="17754-117">Tracking dimension group</span></span>
<span data-ttu-id="17754-118">Itens que estejam prestes a ser usado nos processos de consignação devem ser associados com **Grupo de dimensão de rastreamento** a qual **Proprietário** a dimensão é definida como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="17754-118">Items that are going to be used in consignment processes must be associated with a **Tracking dimension group** where the **Owner** dimension is set to **Active**.</span></span> <span data-ttu-id="17754-119">A dimensão do proprietário deve sempre **Estoque físico** e **Estoque financeiro** as opções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="17754-119">The Owner dimension always has the **Physical inventory** and **Financial inventory** options selected.</span></span> <span data-ttu-id="17754-120">**Plano de cobertura por dimensão** nunca é selecionado.</span><span class="sxs-lookup"><span data-stu-id="17754-120">The **Coverage plan by dimension** is never selected.</span></span>

<span data-ttu-id="17754-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span><span class="sxs-lookup"><span data-stu-id="17754-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span></span>

## <a name="inventory-ownership-change-journal"></a><span data-ttu-id="17754-122">Diário de alteração de propriedade de estoque</span><span class="sxs-lookup"><span data-stu-id="17754-122">Inventory ownership change journal</span></span>
<span data-ttu-id="17754-123">O diário **Alteração de propriedade de estoque** é usado para registrar a transferência de posse de estoque consignado do fornecedor para a entidade legal que o está consumindo.</span><span class="sxs-lookup"><span data-stu-id="17754-123">The **Inventory ownership change** journal is used to record the transfer of ownership of consignment inventory from the vendor to the legal entity that’s consuming it.</span></span> <span data-ttu-id="17754-124">Como qualquer diário de estoque, deve ser identificado com um nome de diário de estoque.</span><span class="sxs-lookup"><span data-stu-id="17754-124">Like any inventory journal, it must be identified with an Inventory journal name.</span></span> <span data-ttu-id="17754-125">Esses nomes são criados na página **Nomes de diário de estoque**, e o **Tipo de diário** deve ser definido como **Alteração de propriedade**.</span><span class="sxs-lookup"><span data-stu-id="17754-125">These names are created on the **Inventory journal names** page, and the **Journal type** must be set to **Ownership change**.</span></span>

<span data-ttu-id="17754-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span><span class="sxs-lookup"><span data-stu-id="17754-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span></span>

## <a name="vendor-collaboration-in-consignment-processes"></a><span data-ttu-id="17754-127">Colaboração de fornecedor em processos de consignação</span><span class="sxs-lookup"><span data-stu-id="17754-127">Vendor collaboration in consignment processes</span></span>
<span data-ttu-id="17754-128">Se os fornecedores serão usando a interface de colaboração de fornecedor, pode usar isso para monitorar o consumo de estoque no site.</span><span class="sxs-lookup"><span data-stu-id="17754-128">If your vendors are using the vendor collaboration interface, they can use this to monitor the consumption of inventory at your site.</span></span> <span data-ttu-id="17754-129">Para obter mais informações sobre como configurar fornecedores para usar a colaboração do fornecedor, consulte [Segurança do usuário no portal de fornecedor](../procurement/configure-security-vendor-portal-users.md).</span><span class="sxs-lookup"><span data-stu-id="17754-129">For more information about setting up vendors to use vendor collaboration, see [Vendor portal user security](../procurement/configure-security-vendor-portal-users.md).</span></span>
