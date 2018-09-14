--- 
title: Transferir um ativo fixo
description: "Este guia da tarefa transfere as informações financeiras para um registro de ativo fixo de um conjunto de dimensões financeiras para um novo conjunto de dimensões financeiras."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, AssetTransfer, DimensionLookup, AssetTransferConfirmation
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: bb8a5b94d9a0bb510daa2a698524e0c380597991
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="transfer-a-fixed-asset"></a><span data-ttu-id="a9ed5-103">Transferir um ativo fixo</span><span class="sxs-lookup"><span data-stu-id="a9ed5-103">Transfer a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a9ed5-104">Este guia da tarefa transfere as informações financeiras para um registro de ativo fixo de um conjunto de dimensões financeiras para um novo conjunto de dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-104">This task guide will transfer the financial information for a fixed asset book from one financial dimension set to a new financial dimension set.</span></span>  <span data-ttu-id="a9ed5-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="a9ed5-106">Vá para Ativos fixos > Ativos fixos > Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-106">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="a9ed5-107">Na lista, localize e selecione o ativo fixo que você deseja transferir.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-107">In the list, find and select the fixed asset to transfer.</span></span>
3. <span data-ttu-id="a9ed5-108">No Painel de Ação, clique em Ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-108">On the Action Pane, click Fixed asset.</span></span>
4. <span data-ttu-id="a9ed5-109">Clique em Transferir ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-109">Click Transfer fixed assets.</span></span>
5. <span data-ttu-id="a9ed5-110">No campo Transferir, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-110">In the Transfer date field, enter a date.</span></span>
6. <span data-ttu-id="a9ed5-111">Inserir comentários para descrever a transferência.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-111">Enter comments to describe the transfer.</span></span>
    * <span data-ttu-id="a9ed5-112">A lista mostra todos os registros do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-112">This list shows all books for the fixed asset.</span></span>  
7. <span data-ttu-id="a9ed5-113">Marque os registros que você deseja transferir para um novo conjunto de dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-113">Mark the books you want to transfer to a new financial dimension set.</span></span>
    * <span data-ttu-id="a9ed5-114">A lista mostra os valores de dimensão financeira existentes para o registro selecionado.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-114">This list shows the existing financial dimension values for the selected book.</span></span>  
    * <span data-ttu-id="a9ed5-115">Selecione a dimensão financeira que você deseja atualizar para o registro de ativo fixo selecionado.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-115">Select the financial dimension you want to update for the selected fixed asset book.</span></span>  
8. <span data-ttu-id="a9ed5-116">No campo Dimensão financeira, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-116">In the Financial dimension field, click the drop down button to open the lookup.</span></span>
    * <span data-ttu-id="a9ed5-117">Definir outros valores de dimensão financeira conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-117">Set other financial dimension values as appropriate.</span></span>  
    * <span data-ttu-id="a9ed5-118">Todos os valores de dimensão financeira são alterados quando uma transferência ocorre, seja se um valor for inserido ou estiver em branco.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-118">All financial dimension values change when a transfer occurs, whether a value has been entered or left blank.</span></span> <span data-ttu-id="a9ed5-119">Por exemplo, se você inserir um valor para o campo BusinessUnit e deixar as dimensões financeiras de CostCenter e de Departamento em branco.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-119">For example, if you entered a value for the BusinessUnit and left the CostCenter and Department financial dimensions blank.</span></span> <span data-ttu-id="a9ed5-120">Se a estrutura de sua conta permitir valores em branco para CostCenter e Departamento, a transferência resultaria em cada modelo de valor tendo o novo valor para BusinessUnit e um valor em branco para CostCenter e Departamento.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-120">If your account structure allows blank values for CostCenter and Department, the transfer would result in each value model having the new value for BusinessUnit and a blank value for CostCenter and Department.</span></span>  
9. <span data-ttu-id="a9ed5-121">Clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-121">Click Update.</span></span>
    * <span data-ttu-id="a9ed5-122">Você tem a oportunidade de visualizar as alterações antes de finalizar a transferência.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-122">You have the opportunity to preview the changes before finalizing the transfer.</span></span>  
    * <span data-ttu-id="a9ed5-123">Revise os resultados antes de transferir os registros de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-123">Review results before transferring the fixed asset books.</span></span>  
10. <span data-ttu-id="a9ed5-124">Clique em Transferir.</span><span class="sxs-lookup"><span data-stu-id="a9ed5-124">Click Transfer.</span></span>


