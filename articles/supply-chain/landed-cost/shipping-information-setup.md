---
title: Configuração de informações de remessa
description: Este tópico descreve como configurar informações de remessa para o módulo Custo de entrega.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 5093e42b0b5247c24c271ad50c80889516586d58
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020878"
---
# <a name="shipping-information-setup"></a><span data-ttu-id="37014-103">Configuração de informações de remessa</span><span class="sxs-lookup"><span data-stu-id="37014-103">Shipping information setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="37014-104">Este tópico descreve como configurar informações de remessa para o módulo **Custo de entrega**.</span><span class="sxs-lookup"><span data-stu-id="37014-104">This topic describes how to set up shipping information for the **Landed cost** module.</span></span>

## <a name="description-of-goods"></a><a name="description-of-goods"></a><span data-ttu-id="37014-105">Descrição das mercadorias</span><span class="sxs-lookup"><span data-stu-id="37014-105">Description of goods</span></span>

<span data-ttu-id="37014-106">As descrições de mercadorias ajudam a identificar uma viagem, um contêiner de remessa ou um fólio de mercadorias e as mercadorias contidas nele.</span><span class="sxs-lookup"><span data-stu-id="37014-106">Descriptions of goods help identify a voyage, shipping container, or folio of goods, and the goods in it.</span></span> <span data-ttu-id="37014-107">É possível selecionar uma descrição de mercadorias no cabeçalho do contêiner de remessa ou no cabeçalho do fólio.</span><span class="sxs-lookup"><span data-stu-id="37014-107">You can select a description of goods on the shipping container header or the folio header.</span></span>

<span data-ttu-id="37014-108">Para trabalhar com descrições de mercadorias, vá para **Custo de entrega \> Configuração de informações de remessa \> Descrição de mercadorias**.</span><span class="sxs-lookup"><span data-stu-id="37014-108">To work with descriptions of goods, go to **Landed cost \> Shipping information setup \> Description of goods**.</span></span> <span data-ttu-id="37014-109">Lá, você pode exibir, abrir, criar e excluir registros de descrições de mercadorias.</span><span class="sxs-lookup"><span data-stu-id="37014-109">There, you can view, open, create, and delete records for descriptions of goods.</span></span> <span data-ttu-id="37014-110">A tabela a seguir descreve os campos disponíveis para cada registro.</span><span class="sxs-lookup"><span data-stu-id="37014-110">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="37014-111">Campo</span><span class="sxs-lookup"><span data-stu-id="37014-111">Field</span></span> | <span data-ttu-id="37014-112">descrição</span><span class="sxs-lookup"><span data-stu-id="37014-112">Description</span></span> |
|---|---|
| <span data-ttu-id="37014-113">Descrição das mercadorias</span><span class="sxs-lookup"><span data-stu-id="37014-113">Description of goods</span></span> | <span data-ttu-id="37014-114">Insira um nome/número de identificação exclusivo para o tipo de mercadorias que usará esta descrição.</span><span class="sxs-lookup"><span data-stu-id="37014-114">Enter a unique identification name/number for the type of goods that will use this description.</span></span> |
| <span data-ttu-id="37014-115">descrição</span><span class="sxs-lookup"><span data-stu-id="37014-115">Description</span></span> | <span data-ttu-id="37014-116">Insira uma descrição do tipo de mercadorias nesta categoria.</span><span class="sxs-lookup"><span data-stu-id="37014-116">Enter a description of the type of goods in this category.</span></span> |

## <a name="vessels"></a><a name="vessels"></a><span data-ttu-id="37014-117">Embarcações</span><span class="sxs-lookup"><span data-stu-id="37014-117">Vessels</span></span>

<span data-ttu-id="37014-118">Uma embarcação é o nome exclusivo de um navio ou embarcação que uma agência ou empresa de transporte usa.</span><span class="sxs-lookup"><span data-stu-id="37014-118">A vessel is the unique name of a ship or vessel that a shipping company or agency uses.</span></span> <span data-ttu-id="37014-119">Ao criar uma viagem, você sempre deve selecionar ou inserir uma embarcação para ela.</span><span class="sxs-lookup"><span data-stu-id="37014-119">When you create a voyage, you must always either select or enter a vessel for it.</span></span> <span data-ttu-id="37014-120">Se você costuma usar as mesmas embarcações, é possível agilizar e facilitar a criação de uma nova viagem criando um registro de embarcação para cada uma delas, permitindo, assim, que os usuários selecionem a embarcação em uma lista em vez de inserir o nome ou o número manualmente a cada vez.</span><span class="sxs-lookup"><span data-stu-id="37014-120">If you often use the same vessels, then you can make it faster and easier to create a new voyage by creating a vessel record for each of them, thereby allowing users to select the vessel from a list rather then enter the name or number manually each time.</span></span>

<span data-ttu-id="37014-121">Para trabalhar com embarcações, vá para **Custo de entrega \> Configuração de informações de remessa \> Embarcações**.</span><span class="sxs-lookup"><span data-stu-id="37014-121">To work with vessels, go to **Landed cost \> Shipping information setup \> Vessels**.</span></span> <span data-ttu-id="37014-122">Lá, você pode exibir, abrir, criar e excluir registros de embarcações.</span><span class="sxs-lookup"><span data-stu-id="37014-122">There, you can view, open, create, and delete records for vessels.</span></span> <span data-ttu-id="37014-123">A tabela a seguir descreve os campos disponíveis para cada registro.</span><span class="sxs-lookup"><span data-stu-id="37014-123">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="37014-124">Campo</span><span class="sxs-lookup"><span data-stu-id="37014-124">Field</span></span> | <span data-ttu-id="37014-125">descrição</span><span class="sxs-lookup"><span data-stu-id="37014-125">Description</span></span> |
|---|---|
| <span data-ttu-id="37014-126">Embarcação</span><span class="sxs-lookup"><span data-stu-id="37014-126">Vessel</span></span> | <span data-ttu-id="37014-127">Insira um nome/número de identificação exclusivo para o navio que será usado para transportar mercadorias em uma viagem.</span><span class="sxs-lookup"><span data-stu-id="37014-127">Enter a unique identification name/number for the ship that will be used to transport goods on a voyage.</span></span> |
| <span data-ttu-id="37014-128">descrição</span><span class="sxs-lookup"><span data-stu-id="37014-128">Description</span></span> | <span data-ttu-id="37014-129">Insira uma descrição da embarcação.</span><span class="sxs-lookup"><span data-stu-id="37014-129">Enter a description of the vessel.</span></span> <span data-ttu-id="37014-130">Normalmente, essa descrição identifica o nome do navio e a empresa/agente de transporte.</span><span class="sxs-lookup"><span data-stu-id="37014-130">Typically, this description identifies the name of the ship and the shipping company/agent.</span></span> |
| <span data-ttu-id="37014-131">Modo de entrega</span><span class="sxs-lookup"><span data-stu-id="37014-131">Mode of delivery</span></span> | <span data-ttu-id="37014-132">Selecione o modo de entrega usado pela embarcação (como _Aéreo_, _Marítimo_ ou _Ferroviário_).</span><span class="sxs-lookup"><span data-stu-id="37014-132">Select the mode of delivery that the vessel uses (such as _Air_, _Ocean_, or _Train_).</span></span> |

## <a name="exporters"></a><span data-ttu-id="37014-133">Exportadores</span><span class="sxs-lookup"><span data-stu-id="37014-133">Exporters</span></span>

<span data-ttu-id="37014-134">Cada registro de exportador identifica um fornecedor ou exportador que pode ser definido como o fornecedor de uma viagem.</span><span class="sxs-lookup"><span data-stu-id="37014-134">Each exporter record identifies a vendor or exporter that can be defined as the vendor for a voyage.</span></span> <span data-ttu-id="37014-135">O exportador pode ser associado a uma viagem e usado para relatórios.</span><span class="sxs-lookup"><span data-stu-id="37014-135">The exporter can be associated with a voyage and used for reporting.</span></span>

<span data-ttu-id="37014-136">Para trabalhar com exportadores, vá para **Custo de entrega \> Configuração de informações de remessa \> Exportadores**.</span><span class="sxs-lookup"><span data-stu-id="37014-136">To work with exporters, go to **Landed cost \> Shipping information setup \> Exporters**.</span></span> <span data-ttu-id="37014-137">Lá, você pode exibir, abrir, criar e excluir registros de exportadores.</span><span class="sxs-lookup"><span data-stu-id="37014-137">There, you can view, open, create, and delete records for exporters.</span></span> <span data-ttu-id="37014-138">A tabela a seguir descreve os campos disponíveis para cada registro.</span><span class="sxs-lookup"><span data-stu-id="37014-138">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="37014-139">Campo</span><span class="sxs-lookup"><span data-stu-id="37014-139">Field</span></span> | <span data-ttu-id="37014-140">descrição</span><span class="sxs-lookup"><span data-stu-id="37014-140">Description</span></span> |
|---|---|
| <span data-ttu-id="37014-141">Exportador</span><span class="sxs-lookup"><span data-stu-id="37014-141">Exporter</span></span> | <span data-ttu-id="37014-142">Insira um nome/número de identificação exclusivo para o exportador de mercadorias transportadas em uma viagem.</span><span class="sxs-lookup"><span data-stu-id="37014-142">Enter a unique identification name/number for the exporter of goods that are transported on a voyage.</span></span> |
| <span data-ttu-id="37014-143">descrição</span><span class="sxs-lookup"><span data-stu-id="37014-143">Description</span></span> | <span data-ttu-id="37014-144">Insira uma descrição do exportador.</span><span class="sxs-lookup"><span data-stu-id="37014-144">Enter a description of the exporter.</span></span> <span data-ttu-id="37014-145">Normalmente, essa descrição identifica o nome completo da empresa/agente de transporte.</span><span class="sxs-lookup"><span data-stu-id="37014-145">Typically, this description identifies the full name of the shipping company/agent.</span></span> |

## <a name="commodity-codes"></a><span data-ttu-id="37014-146">Códigos de mercadoria</span><span class="sxs-lookup"><span data-stu-id="37014-146">Commodity codes</span></span>

<span data-ttu-id="37014-147">Você usa códigos de mercadoria para ajudar na identificação alfandegária e no cálculo de taxas de imposto para mercadorias em uma viagem.</span><span class="sxs-lookup"><span data-stu-id="37014-147">You use commodity codes to help with customs identification and the calculation of duty rates for goods on a voyage.</span></span> <span data-ttu-id="37014-148">Você pode selecionar códigos de mercadoria na página **Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="37014-148">You can select commodity codes on the **Released products** page.</span></span>

<span data-ttu-id="37014-149">Para trabalhar com códigos de mercadoria, vá para **Custo de entrega \> Configuração de informações de remessa \> Códigos de mercadoria**.</span><span class="sxs-lookup"><span data-stu-id="37014-149">To work with commodity codes, go to **Landed cost \> Shipping information setup \> Commodity codes**.</span></span> <span data-ttu-id="37014-150">Lá, você pode exibir, abrir, criar e excluir registros de códigos de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="37014-150">There, you can view, open, create, and delete records for commodity codes.</span></span> <span data-ttu-id="37014-151">A tabela a seguir descreve os campos disponíveis para cada registro.</span><span class="sxs-lookup"><span data-stu-id="37014-151">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="37014-152">Campo</span><span class="sxs-lookup"><span data-stu-id="37014-152">Field</span></span> | <span data-ttu-id="37014-153">descrição</span><span class="sxs-lookup"><span data-stu-id="37014-153">Description</span></span> |
|---|---|
| <span data-ttu-id="37014-154">Código da mercadoria</span><span class="sxs-lookup"><span data-stu-id="37014-154">Commodity code</span></span> | <span data-ttu-id="37014-155">Insira um código exclusivo para este tipo de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="37014-155">Enter a unique code for this type of commodity.</span></span> |
| <span data-ttu-id="37014-156">descrição</span><span class="sxs-lookup"><span data-stu-id="37014-156">Description</span></span> | <span data-ttu-id="37014-157">Insira uma descrição do tipo de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="37014-157">Enter a description of the commodity type.</span></span> |

## <a name="customs-description"></a><span data-ttu-id="37014-158">Descrição alfandegária</span><span class="sxs-lookup"><span data-stu-id="37014-158">Customs description</span></span>

<span data-ttu-id="37014-159">As descrições alfandegárias ajudam a identificar mercadorias para fins alfandegários.</span><span class="sxs-lookup"><span data-stu-id="37014-159">Customs descriptions help identify goods for customs purposes.</span></span> <span data-ttu-id="37014-160">Você pode selecionar uma descrição alfandegária na página **Produtos liberados** ou nas linhas da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="37014-160">You can select a customs description on the **Released products** page or on purchase order lines.</span></span>

<span data-ttu-id="37014-161">Para trabalhar com descrições alfandegárias, vá para **Custo de entrega \> Configuração de informações de remessa \> Descrição alfandegária**.</span><span class="sxs-lookup"><span data-stu-id="37014-161">To work with customs descriptions, go to **Landed cost \> Shipping information setup \> Customs description**.</span></span> <span data-ttu-id="37014-162">Lá, você pode exibir, abrir, criar e excluir registros de descrições alfandegárias.</span><span class="sxs-lookup"><span data-stu-id="37014-162">There, you can view, open, create, and delete records for custom descriptions.</span></span> <span data-ttu-id="37014-163">A tabela a seguir descreve os campos disponíveis para cada registro.</span><span class="sxs-lookup"><span data-stu-id="37014-163">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="37014-164">Campo</span><span class="sxs-lookup"><span data-stu-id="37014-164">Field</span></span> | <span data-ttu-id="37014-165">descrição</span><span class="sxs-lookup"><span data-stu-id="37014-165">Description</span></span> |
|---|---|
| <span data-ttu-id="37014-166">Descrição alfandegária</span><span class="sxs-lookup"><span data-stu-id="37014-166">Customs description</span></span> | <span data-ttu-id="37014-167">Insira um código exclusivo para este tipo de classificação alfandegária.</span><span class="sxs-lookup"><span data-stu-id="37014-167">Enter a unique code for this type of customs classification.</span></span> <span data-ttu-id="37014-168">Geralmente, esse código será a descrição oficial fornecida por uma autoridade alfandegária para a descrição e o valor qualitativo das mercadorias.</span><span class="sxs-lookup"><span data-stu-id="37014-168">Often, this code will be the official description that is provided by a customs authority for the description and qualitative value of the goods.</span></span> |
| <span data-ttu-id="37014-169">descrição</span><span class="sxs-lookup"><span data-stu-id="37014-169">Description</span></span> | <span data-ttu-id="37014-170">Insira uma descrição da classificação alfandegária.</span><span class="sxs-lookup"><span data-stu-id="37014-170">Enter a description of the customs classification.</span></span> |
