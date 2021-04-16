---
title: Alterar convenções de depreciação para ativos fixos múltiplos
description: Esta tarefa atualiza a convenção de depreciação de um grupo de ativo fixo específico.
author: saraschi2
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysQueryForm, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a71b24b0c2ea072aeff8c994cfdac10bc57b64c6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823971"
---
# <a name="change-depreciation-conventions-for-multiple-fixed-assets"></a><span data-ttu-id="e1796-103">Alterar convenções de depreciação para ativos fixos múltiplos</span><span class="sxs-lookup"><span data-stu-id="e1796-103">Change depreciation conventions for multiple fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e1796-104">Esta tarefa atualiza a convenção de depreciação de um grupo de ativo fixo específico.</span><span class="sxs-lookup"><span data-stu-id="e1796-104">This task updates the depreciation convention for a specified fixed asset group.</span></span> <span data-ttu-id="e1796-105">Este guia de tarefa usa a empresa demo USMF.</span><span class="sxs-lookup"><span data-stu-id="e1796-105">This task guide uses the USMF demo company.</span></span>

1. <span data-ttu-id="e1796-106">Vá para Ativos fixos > Tarefas periódicas > Atualização em massa</span><span class="sxs-lookup"><span data-stu-id="e1796-106">Go to Fixed assets > Periodic tasks > Mass update</span></span>
2. <span data-ttu-id="e1796-107">No campo Livro de depreciação, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e1796-107">In the Depreciation book field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="e1796-108">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e1796-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e1796-109">No campo Posicionado no início do serviço, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="e1796-109">In the Placed in service start field, enter a date.</span></span>
5. <span data-ttu-id="e1796-110">No campo Posicionado no fim do serviço, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="e1796-110">In the Placed in service end field, enter a date.</span></span>
    * <span data-ttu-id="e1796-111">Serão atualizados apenas os ativos do registro de depreciações selecionado que tiverem sido disponibilizados entre essas datas.</span><span class="sxs-lookup"><span data-stu-id="e1796-111">Only assets that are a part of the select depreciation book and that have been placed in service between these dates will be updated.</span></span>  
6. <span data-ttu-id="e1796-112">No campo Convenção de depreciação atual, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="e1796-112">In the Current depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="e1796-113">Apenas os ativos com a convenção de depreciação atual serão atualizados.</span><span class="sxs-lookup"><span data-stu-id="e1796-113">Only assets that have the current depreciation convention will be updated.</span></span>  
7. <span data-ttu-id="e1796-114">No campo Convenção de nova depreciação, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="e1796-114">In the New depreciation convention field, select an option.</span></span>
    * <span data-ttu-id="e1796-115">Verifique o relatório que imprimirá o destino desejado.</span><span class="sxs-lookup"><span data-stu-id="e1796-115">Verify the report will print to the desired destination.</span></span>  
8. <span data-ttu-id="e1796-116">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="e1796-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="e1796-117">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="e1796-117">Click Filter.</span></span>
10. <span data-ttu-id="e1796-118">Na lista, selecione o grupo de Ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="e1796-118">In the list, select the Fixed asset group.</span></span>
11. <span data-ttu-id="e1796-119">No campo Critérios, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e1796-119">In the Criteria field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="e1796-120">Selecione o grupo de ativos fixos desejado.</span><span class="sxs-lookup"><span data-stu-id="e1796-120">Select the desired Fixed asset group.</span></span>
13. <span data-ttu-id="e1796-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e1796-121">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="e1796-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e1796-122">Click OK.</span></span>
15. <span data-ttu-id="e1796-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e1796-123">Click OK.</span></span>
    *  <span data-ttu-id="e1796-124">Os resultados do processo são mostrados no relatório de atualização em massa.</span><span class="sxs-lookup"><span data-stu-id="e1796-124">Results of the process are shown on the Mass update report.</span></span>     



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]