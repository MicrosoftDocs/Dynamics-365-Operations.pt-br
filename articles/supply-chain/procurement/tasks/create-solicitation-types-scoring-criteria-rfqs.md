---
title: Criar tipos de solicitação e critérios de avaliação para RFQs
description: Este guia mostra como criar um tipo da solicitação e associar esse tipo com um método de avaliação.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40625152a579bb269411d026d77d449902c8d4bc
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016797"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a><span data-ttu-id="820b2-103">Criar tipos de solicitação e critérios de avaliação para RFQs</span><span class="sxs-lookup"><span data-stu-id="820b2-103">Create solicitation types and scoring criteria for RFQs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="820b2-104">Este guia mostra como criar um tipo da solicitação e associar esse tipo com um método de avaliação.</span><span class="sxs-lookup"><span data-stu-id="820b2-104">This guide shows you how to create a solicitation type and associate this with a scoring method.</span></span> <span data-ttu-id="820b2-105">Ele também mostra como usar o tipo de solicitação em uma solicitação de cotação (RFQ) que então define o padrão do método de avaliação.</span><span class="sxs-lookup"><span data-stu-id="820b2-105">It also shows how to use the solicitation type on a request for quotation (RFQ) which then sets the default scoring method.</span></span> <span data-ttu-id="820b2-106">Essas tarefas são normalmente realizadas por um Gerente de compras.</span><span class="sxs-lookup"><span data-stu-id="820b2-106">These tasks would typically be carried out by a purchasing manager.</span></span> <span data-ttu-id="820b2-107">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="820b2-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="820b2-108">Você precisa ter um método de marcação disponível antes de começar.</span><span class="sxs-lookup"><span data-stu-id="820b2-108">You need to have a scoring method available before you start.</span></span>


## <a name="create-a-solicitation-type"></a><span data-ttu-id="820b2-109">Criar um tipo de solicitação.</span><span class="sxs-lookup"><span data-stu-id="820b2-109">Create a solicitation type</span></span>
1. <span data-ttu-id="820b2-110">Vá para Compras > Configuração > Solicitação de cotação > Tipo de solicitação.</span><span class="sxs-lookup"><span data-stu-id="820b2-110">Go to Procurement and sourcing > Setup > Request for quotation > Solicitation type.</span></span>
2. <span data-ttu-id="820b2-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="820b2-111">Click New.</span></span>
3. <span data-ttu-id="820b2-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="820b2-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="820b2-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="820b2-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="820b2-114">No campo Método de avaliação, selecione o método de avaliação que você deseja usar para este tipo de solicitação.</span><span class="sxs-lookup"><span data-stu-id="820b2-114">In the Scoring method field, select the scoring method that you want to use for this solicitation type.</span></span>
6. <span data-ttu-id="820b2-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="820b2-115">Click Save.</span></span>
7. <span data-ttu-id="820b2-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="820b2-116">Close the page.</span></span>

## <a name="use-the-solicitation-type"></a><span data-ttu-id="820b2-117">Use o tipo de solicitação</span><span class="sxs-lookup"><span data-stu-id="820b2-117">Use the solicitation type</span></span>
1. <span data-ttu-id="820b2-118">Vá para Aquisição e fornecimento > Solicitações de cotações > Todas as solicitações de cotações.</span><span class="sxs-lookup"><span data-stu-id="820b2-118">Go to Procurement and sourcing > Requests for quotations > All requests for quotations.</span></span>
2. <span data-ttu-id="820b2-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="820b2-119">Click New.</span></span>
3. <span data-ttu-id="820b2-120">No campo Tipo de solicitação, selecione o tipo de solicitação que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="820b2-120">In the Solicitation type field, select the solicitation type that you have just created.</span></span> 
    *   
4. <span data-ttu-id="820b2-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="820b2-121">Click OK.</span></span>
5. <span data-ttu-id="820b2-122">Clique em Critérios de pontuação.</span><span class="sxs-lookup"><span data-stu-id="820b2-122">Click Scoring criteria.</span></span>
    * <span data-ttu-id="820b2-123">Os critérios de avaliação que são mostrados são esses do método de avaliação que você associou com o tipo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="820b2-123">The scoring criteria that are shown are the ones from the scoring method that you associated with the solicitation type.</span></span> <span data-ttu-id="820b2-124">Você pode escolher adicionar ou suprimir critérios nesta página.</span><span class="sxs-lookup"><span data-stu-id="820b2-124">You can choose to add or delete criteria on this page.</span></span> <span data-ttu-id="820b2-125">É igualmente possível adicionar critérios novos copiando os de outros métodos de avaliação.</span><span class="sxs-lookup"><span data-stu-id="820b2-125">It's also possible to add new criteria by copying them from other scoring methods.</span></span>  
6. <span data-ttu-id="820b2-126">Clique em Copiar critérios.</span><span class="sxs-lookup"><span data-stu-id="820b2-126">Click Copy criteria.</span></span>
7. <span data-ttu-id="820b2-127">No campo Método de avaliação, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="820b2-127">In the Scoring method field, enter or select a value.</span></span>
8. <span data-ttu-id="820b2-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="820b2-128">Click OK.</span></span>
9. <span data-ttu-id="820b2-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="820b2-129">Close the page.</span></span>

