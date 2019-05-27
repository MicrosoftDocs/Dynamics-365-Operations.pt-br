---
title: Configurar permissões para solicitar produtos em nome de qualquer outra pessoa
description: Este procedimento mostra como conceder a trabalhadores a permissão para preparar requisições da compra em nome de outros trabalhadores.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 35688d191cef06cc15251a6e10a2e8c9afb0e08b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571854"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a><span data-ttu-id="02071-103">Configurar permissões para solicitar produtos em nome de qualquer outra pessoa</span><span class="sxs-lookup"><span data-stu-id="02071-103">Set up permissions for ordering products on behalf of someone else</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="02071-104">Este procedimento mostra como conceder a trabalhadores a permissão para preparar requisições da compra em nome de outros trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="02071-104">This procedure shows how to grant workers permission to prepare purchase requisitions on behalf of other workers.</span></span> <span data-ttu-id="02071-105">Ou seja, um "preparador" de requisição de compra pode criar uma requisição para outro "solicitante".</span><span class="sxs-lookup"><span data-stu-id="02071-105">In other words, a purchase requisition “preparer” can create a requisition for another “requester.”</span></span> <span data-ttu-id="02071-106">O procedimento também mostra como conceder permissões a um trabalhador para pedir itens e serviços em diferentes entidades legais ou unidades operacionais.</span><span class="sxs-lookup"><span data-stu-id="02071-106">The procedure also shows how to grant a worker permission to order items and services in different legal entities or operating units.</span></span> <span data-ttu-id="02071-107">Geralmente, essas tarefas são realizadas por um gerente de compras.</span><span class="sxs-lookup"><span data-stu-id="02071-107">Typically, these tasks are performed by a purchasing manager.</span></span> <span data-ttu-id="02071-108">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="02071-108">You can use this procedure either on data for the USMF demo company or on your own data.</span></span>


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a><span data-ttu-id="02071-109">Conceda permissões para inserir requisições de compra em nome de outro trabalhador</span><span class="sxs-lookup"><span data-stu-id="02071-109">Grant permission to enter purchase requisitions on behalf of another worker</span></span>
1. <span data-ttu-id="02071-110">Vá para Compras > Configuração > Políticas > Permissões de requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="02071-110">Go to Procurement and sourcing > Setup > Policies > Purchase requisition permissions.</span></span>
    * <span data-ttu-id="02071-111">Certifique-se de que o campo da exibição atual está ajustado pelo preparador.</span><span class="sxs-lookup"><span data-stu-id="02071-111">Make sure that the Current view field is set to By preparer.</span></span>  <span data-ttu-id="02071-112">A lista no painel à esquerda mostra as pessoas que podem receber a permissão para preparar requisições em nome de outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="02071-112">The list in the left pane shows the people who can be granted permission to prepare requisitions on behalf of other people.</span></span>  
2. <span data-ttu-id="02071-113">Selecione a pessoa para conceder a permissão (o preparador).</span><span class="sxs-lookup"><span data-stu-id="02071-113">Select the person to grant permission to (the preparer).</span></span>
3. <span data-ttu-id="02071-114">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="02071-114">Click Add.</span></span>
4. <span data-ttu-id="02071-115">Encontre e selecione a pessoa para adicionar como um solicitador.</span><span class="sxs-lookup"><span data-stu-id="02071-115">Find and select the person to add as a requester.</span></span>
    * <span data-ttu-id="02071-116">O solicitante é a pessoa com a qual o preparador pode criar requisições em seu nome.</span><span class="sxs-lookup"><span data-stu-id="02071-116">The requester is the person that the preparer can create requisitions on behalf of.</span></span>  
    * <span data-ttu-id="02071-117">No campo Autorização, selecione Específico se o preparador puder criar requisições da compra em nome do trabalhador selecionado.</span><span class="sxs-lookup"><span data-stu-id="02071-117">In the Authorization field, select Specific if the preparer should be able to create purchase requisitions on behalf of the selected worker.</span></span> <span data-ttu-id="02071-118">Selecione Relatório se o preparador também puder criar requisições da compra em nome de todos os trabalhadores que reportam a esse trabalhador.</span><span class="sxs-lookup"><span data-stu-id="02071-118">Select Reporting if the preparer should also be able to create purchase requisitions on behalf of all workers who report to that worker.</span></span>  
5. <span data-ttu-id="02071-119">No campo Efetivo, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="02071-119">In the Effective field, enter a date.</span></span>
6. <span data-ttu-id="02071-120">No campo Vencimento, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="02071-120">In the Expiration field, enter a date.</span></span>

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a><span data-ttu-id="02071-121">Veja os preparadores que têm a permissão para criar requisições de compra para um trabalhador selecionado</span><span class="sxs-lookup"><span data-stu-id="02071-121">View preparers who have permission to create purchase requisitions for a selected worker</span></span>
1. <span data-ttu-id="02071-122">No campo Exibição atual, selecione “Pelo solicitador”.</span><span class="sxs-lookup"><span data-stu-id="02071-122">In the Current view field, select 'By requester'.</span></span>
    * <span data-ttu-id="02071-123">Esta exibição exibe uma lista de preparadores que receberam permissão para criar requisições de compra em node de um trabalhador selecionado.</span><span class="sxs-lookup"><span data-stu-id="02071-123">This view shows a list of preparers who have been granted permission to create purchase requisitions on behalf of a selected worker.</span></span>  
2. <span data-ttu-id="02071-124">Use o filtro rápido para encontrar o trabalhador que você apenas adicionou como o solicitador.</span><span class="sxs-lookup"><span data-stu-id="02071-124">Use the Quick Filter to find the worker that you just added as the requester.</span></span>
3. <span data-ttu-id="02071-125">Selecione o solicitante.</span><span class="sxs-lookup"><span data-stu-id="02071-125">Select the requester.</span></span>
    * <span data-ttu-id="02071-126">A lista do preparador mostra as pessoas que têm a permissão para pedir artigos em nome do solicitador que é selecionado no painel à esquerda.</span><span class="sxs-lookup"><span data-stu-id="02071-126">The Preparer list shows the people who have permission to order items on behalf of the requester who is selected in the left pane.</span></span>   <span data-ttu-id="02071-127">Você pode adicionar preparadores adicionais aqui.</span><span class="sxs-lookup"><span data-stu-id="02071-127">You can add additional preparers here.</span></span>   <span data-ttu-id="02071-128">Esta exibição também permite que a permissão do solicitante crie requisições em entidades legais e unidades operacionais que não são a pessoa da entidade legal primária ou unidade operacional.</span><span class="sxs-lookup"><span data-stu-id="02071-128">This view also lets you grant the requester permission to create requisitions in legal entities and operating units that aren't that person's primary legal entity or operating unit.</span></span>  

