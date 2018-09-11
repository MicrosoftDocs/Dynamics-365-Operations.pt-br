--- 
title: Descartar um ativo fixo usando uma fatura de texto livre
description: "Este procedimento mostra como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos."
author: saraschi2
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: bf449be5f9b79c1e6bf7d9a5dd6d7cdede20eea9
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="dispose-of-a-fixed-asset-using-a-free-text-invoice"></a><span data-ttu-id="e412d-103">Descartar um ativo fixo usando uma fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="e412d-103">Dispose of a fixed asset using a free text invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e412d-104">Este procedimento mostra como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="e412d-104">This procedure shows how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="e412d-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="e412d-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="e412d-106">Ir para Ativos fixos > Entradas de diário > Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="e412d-106">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="e412d-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="e412d-107">Click New.</span></span>
3. <span data-ttu-id="e412d-108">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="e412d-108">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="e412d-109">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="e412d-109">Click Lines.</span></span>
5. <span data-ttu-id="e412d-110">Clique em Propostas.</span><span class="sxs-lookup"><span data-stu-id="e412d-110">Click Proposals.</span></span>
6. <span data-ttu-id="e412d-111">Clique em Proposta de aquisição.</span><span class="sxs-lookup"><span data-stu-id="e412d-111">Click Acquisition proposal.</span></span>
7. <span data-ttu-id="e412d-112">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="e412d-112">Click Filter.</span></span>
8. <span data-ttu-id="e412d-113">Clique em Redefinir para limpar a saída de valores anteriores.</span><span class="sxs-lookup"><span data-stu-id="e412d-113">Click Reset to clear out previous values.</span></span>
9. <span data-ttu-id="e412d-114">Selecione a linha de Número de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="e412d-114">Select the Fixed asset number row.</span></span>
10. <span data-ttu-id="e412d-115">No campo Critérios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="e412d-115">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="e412d-116">Defina os critérios restantes para os ativos fixos que você deseja adquirir com esta proposta.</span><span class="sxs-lookup"><span data-stu-id="e412d-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
11. <span data-ttu-id="e412d-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e412d-117">Click OK.</span></span>
12. <span data-ttu-id="e412d-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e412d-118">Click OK.</span></span>
    * <span data-ttu-id="e412d-119">Verifique as linhas de transação criadas.</span><span class="sxs-lookup"><span data-stu-id="e412d-119">Verify the transaction lines created.</span></span>  
    * <span data-ttu-id="e412d-120">Somente os ativos fixos com a data de aquisição e o preço de aquisição definidos no registro serão incluídos na proposta de aquisição.</span><span class="sxs-lookup"><span data-stu-id="e412d-120">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
13. <span data-ttu-id="e412d-121">Clique na guia Registros.</span><span class="sxs-lookup"><span data-stu-id="e412d-121">Click the Books tab.</span></span>
14. <span data-ttu-id="e412d-122">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="e412d-122">Click Post.</span></span>


