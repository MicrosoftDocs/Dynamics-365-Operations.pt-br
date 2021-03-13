---
title: Criar um novo produto
description: Este tópico descreve como criar um novo produto compartilhado.
author: ShylaThompson
manager: tfehr
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d313d76d40476bec5c8bc9c8ea5fc93b217e7e87
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007557"
---
# <a name="create-a-new-product"></a><span data-ttu-id="6326b-103">Criar um novo produto</span><span class="sxs-lookup"><span data-stu-id="6326b-103">Create a new product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6326b-104">Este tópico descreve como criar um novo produto compartilhado.</span><span class="sxs-lookup"><span data-stu-id="6326b-104">This topic describes how to create a new shared product.</span></span> <span data-ttu-id="6326b-105">Geralmente é realizado por um designer do produto.</span><span class="sxs-lookup"><span data-stu-id="6326b-105">It is usually carried out by a product designer.</span></span> <span data-ttu-id="6326b-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="6326b-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-product"></a><span data-ttu-id="6326b-107">Criar um produto</span><span class="sxs-lookup"><span data-stu-id="6326b-107">Create a product</span></span>
1. <span data-ttu-id="6326b-108">No Painel de navegação, vá para **Módulos > Gerenciamento de informações sobre produtos > Produtos > Produtos**.</span><span class="sxs-lookup"><span data-stu-id="6326b-108">In the Navigation pane, go to **Modules > Product information management > Products > Products**.</span></span>
2. <span data-ttu-id="6326b-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="6326b-109">Select **New**.</span></span>
3. <span data-ttu-id="6326b-110">No campo **Número do produto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6326b-110">In the **Product number** field, type a value.</span></span> <span data-ttu-id="6326b-111">Se uma sequência numérica não foi configurada para o número do produto, deve ser inserida manualmente.</span><span class="sxs-lookup"><span data-stu-id="6326b-111">If a number sequence has not been set up for the product number, it must be entered manually.</span></span>  
4. <span data-ttu-id="6326b-112">No campo **Nome do produto**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6326b-112">In the **Product name** field, type a value.</span></span> <span data-ttu-id="6326b-113">O Nome do produto padrão ao nome de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6326b-113">The product name defaults to the search name.</span></span> <span data-ttu-id="6326b-114">Você pode mudar isso, se necessário.</span><span class="sxs-lookup"><span data-stu-id="6326b-114">You can change this if needed.</span></span>  
5. <span data-ttu-id="6326b-115">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="6326b-115">Select **OK**.</span></span>

## <a name="set-up-dimension-groups"></a><span data-ttu-id="6326b-116">Configurar grupos de dimensões</span><span class="sxs-lookup"><span data-stu-id="6326b-116">Set up dimension groups</span></span>
1. <span data-ttu-id="6326b-117">Selecione **Grupos de dimensões** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6326b-117">Select **Dimension groups** to open the drop dialog.</span></span>
2. <span data-ttu-id="6326b-118">No campo **Grupo de dimensões de armazenamento**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6326b-118">In the **Storage dimension group** field, enter or select a value.</span></span> <span data-ttu-id="6326b-119">O grupo de dimensões de armazenamento determina quais dimensões de estoque você deve inserir em cada transação para o produto e como são rastreados no estoque.</span><span class="sxs-lookup"><span data-stu-id="6326b-119">The storage dimension group determines which storage dimensions you must enter on each transaction for the product and how it will be tracked in inventory.</span></span>  
3. <span data-ttu-id="6326b-120">No campo **Grupo de dimensões de rastreamento**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6326b-120">In the **Tracking dimension group** field, enter or select a value.</span></span> <span data-ttu-id="6326b-121">O grupo de dimensões de rastreamento determina quais dimensões de rastreamento você deve inserir em cada transação para o produto e como são lidadas no estoque.</span><span class="sxs-lookup"><span data-stu-id="6326b-121">The tracking dimension group determines which tracking dimensions you must enter for each transaction for the product, and how it will be handled in inventory.</span></span>  
4. <span data-ttu-id="6326b-122">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="6326b-122">Select **OK**.</span></span>

