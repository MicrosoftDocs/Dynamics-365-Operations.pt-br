--- 
title: "Lançar em diário entradas de diário"
description: "Este procedimento aborda como lançar em diário entradas de diário postadas."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 490e9a4beda43f6e32b87792b11153c3e8e322d6
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="a33f0-103">Lançar em diário entradas de diário</span><span class="sxs-lookup"><span data-stu-id="a33f0-103">Journalize posted journal entries</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a33f0-104">Este procedimento aborda como lançar em diário entradas de diário postadas.</span><span class="sxs-lookup"><span data-stu-id="a33f0-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="a33f0-105">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="a33f0-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="a33f0-106">Valide as configurações para o lançamento em diário em Contabilidade > Configuração do razão > Parâmetros da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="a33f0-106">Validate the settings for journalizing under General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="a33f0-107">O campo de diários estendidos de motivo pode ser definido como Sim ou Não.</span><span class="sxs-lookup"><span data-stu-id="a33f0-107">The Extended ledger journal field can be set to Yes or No.</span></span> <span data-ttu-id="a33f0-108">Se Sim, as versões de relatório serão diferentes.</span><span class="sxs-lookup"><span data-stu-id="a33f0-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="a33f0-109">Selecione se o período pode ser inserido se o processo se lançando em diário não foi executado.</span><span class="sxs-lookup"><span data-stu-id="a33f0-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span>
    * <span data-ttu-id="a33f0-110">Se esta opção é definida em Sim, o período não poderá ser fechado até o processo se lançando em diário foi preenchido para o período.</span><span class="sxs-lookup"><span data-stu-id="a33f0-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="a33f0-111">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a33f0-111">Close the page.</span></span>
5. <span data-ttu-id="a33f0-112">Vá para Contabilidade > Tarefas periódicas > Lançamento em diário.</span><span class="sxs-lookup"><span data-stu-id="a33f0-112">Go to General ledger > Periodic tasks > Journalizing.</span></span>
6. <span data-ttu-id="a33f0-113">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="a33f0-113">Click Filter.</span></span>
7. <span data-ttu-id="a33f0-114">Realce a linha com os critérios do filtro que você deseja definir.</span><span class="sxs-lookup"><span data-stu-id="a33f0-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="a33f0-115">No campo Critérios, insira ou selecione o critério de filtro.</span><span class="sxs-lookup"><span data-stu-id="a33f0-115">In the Criteria field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="a33f0-116">Clique em OK para fechar a página de filtro.</span><span class="sxs-lookup"><span data-stu-id="a33f0-116">Click OK to close the filter page.</span></span>
10. <span data-ttu-id="a33f0-117">Clique em OK para iniciar o processo de colocar em diário.</span><span class="sxs-lookup"><span data-stu-id="a33f0-117">Click OK to start the journalizing process.</span></span>
    * <span data-ttu-id="a33f0-118">Um relatório será gerado depois que o processo foi concluído.</span><span class="sxs-lookup"><span data-stu-id="a33f0-118">A report will be generated after the process is complete.</span></span>  


