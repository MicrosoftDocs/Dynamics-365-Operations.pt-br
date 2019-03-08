---
title: Criar ordens de produção
description: Ao criar uma ordem de produção, você inicia uma solicitação para iniciar a fabricação de um item. A ordem de produção contém informações sobre o que será produzido, a quantidade a ser produzida e a data de conclusão planejada. Também contém informações sobre quais materiais consumir e qual processo seguir para produzir o item.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2957b387aac9e0218f88572fa605cde1a30c52e5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "324620"
---
# <a name="create-production-orders"></a><span data-ttu-id="c7645-105">Criar ordens de produção</span><span class="sxs-lookup"><span data-stu-id="c7645-105">Create production orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7645-106">Ao criar uma ordem de produção, você inicia uma solicitação para iniciar a fabricação de um item.</span><span class="sxs-lookup"><span data-stu-id="c7645-106">When a production order is created, a request is initiated to start producing an item.</span></span> <span data-ttu-id="c7645-107">A ordem de produção contém informações sobre o que será produzido, a quantidade a ser produzida e a data de conclusão planejada.</span><span class="sxs-lookup"><span data-stu-id="c7645-107">The production order contains information about what will be produced, the quantity to produce, and the planned finish date.</span></span> <span data-ttu-id="c7645-108">Também contém informações sobre quais materiais consumir e qual processo seguir para produzir o item.</span><span class="sxs-lookup"><span data-stu-id="c7645-108">It also contains information about which materials to consume and which process to follow to produce the item.</span></span>

<span data-ttu-id="c7645-109">Uma ordem de produção passa pelos estágios do ciclo de vida de produção.</span><span class="sxs-lookup"><span data-stu-id="c7645-109">A production order passes through stages of the production life cycle.</span></span> <span data-ttu-id="c7645-110">Quando uma ordem é criada, ela recebe o status **Criada**.</span><span class="sxs-lookup"><span data-stu-id="c7645-110">When an order is created, it is assigned the status **Created**.</span></span> <span data-ttu-id="c7645-111">Quando uma ordem é concluída, recebe o status **Encerrada**.</span><span class="sxs-lookup"><span data-stu-id="c7645-111">When an order is finished, it is assigned the status **Ended**.</span></span> <span data-ttu-id="c7645-112">Uma configuração de parâmetro em cada estágio permite que um usuário configure cada etapa.</span><span class="sxs-lookup"><span data-stu-id="c7645-112">A parameter setting in each stage allows a user to configure each step.</span></span> <span data-ttu-id="c7645-113">A configuração pode ser configurada para um único usuário ou para todos.</span><span class="sxs-lookup"><span data-stu-id="c7645-113">The setting can be set up for a single user or for all users.</span></span>

<span data-ttu-id="c7645-114">A lista de materiais de produção e o roteiro de produção são as principais entidades da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="c7645-114">The production bill of material and the production route are the main entities of the production order.</span></span> <span data-ttu-id="c7645-115">Elas são copiadas para a ordem de produção com base no item selecionado e na quantidade que será produzida.</span><span class="sxs-lookup"><span data-stu-id="c7645-115">They are copied to the production order based on the selected item and quantity that are going to be produced.</span></span> <span data-ttu-id="c7645-116">Antes que a ordem de produção seja iniciada, a lista de materiais e o roteiro de produção podem ser editados.</span><span class="sxs-lookup"><span data-stu-id="c7645-116">Before the production order is started, the production bill of material and route can be edited.</span></span>

<span data-ttu-id="c7645-117">Uma ordem de produção pode ser criada nestes cenários:</span><span class="sxs-lookup"><span data-stu-id="c7645-117">A production order can be created in the following scenarios:</span></span>

-   <span data-ttu-id="c7645-118">Criada pela execução do planejamento mestre com base na demanda de materiais.</span><span class="sxs-lookup"><span data-stu-id="c7645-118">Created by master planning execution based on material demand.</span></span>
-   <span data-ttu-id="c7645-119">Criada diretamente de uma linha da ordem de venda ou quando uma ordem de produção de nível superior é criada e prevista (fornecimento vinculado).</span><span class="sxs-lookup"><span data-stu-id="c7645-119">Created directly from a sales order line or when a higher-level production order is created and estimated (pegged supply).</span></span>
-   <span data-ttu-id="c7645-120">Criada manualmente.</span><span class="sxs-lookup"><span data-stu-id="c7645-120">Created manually.</span></span>




