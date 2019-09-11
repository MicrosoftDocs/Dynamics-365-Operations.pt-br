---
title: Lançar em diário entradas de diário
description: Este procedimento aborda como lançar em diário entradas de diário postadas.
author: aprilolson
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e20229ca910aa0d7d820434c22edf5a27030bba5
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916244"
---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="033c0-103">Lançar em diário entradas de diário</span><span class="sxs-lookup"><span data-stu-id="033c0-103">Journalize posted journal entries</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="033c0-104">Este procedimento aborda como lançar em diário entradas de diário postadas.</span><span class="sxs-lookup"><span data-stu-id="033c0-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="033c0-105">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="033c0-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="033c0-106">No **painel de Navegação**, vá para **Módulos > Contabilidade > Configuração do razão > parâmetros de Contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="033c0-106">In the **Navigation pane**, go to **Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="033c0-107">O campo **Diário-razão estendido** pode ser definido como Sim ou Não.</span><span class="sxs-lookup"><span data-stu-id="033c0-107">The **Extended ledger journal** field can be set to Yes or No.</span></span> <span data-ttu-id="033c0-108">Se Sim, as versões de relatório serão diferentes.</span><span class="sxs-lookup"><span data-stu-id="033c0-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="033c0-109">Selecione se o período pode ser inserido se o processo se lançando em diário não foi executado.</span><span class="sxs-lookup"><span data-stu-id="033c0-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span> <span data-ttu-id="033c0-110">Se esta opção é definida em Sim, o período não poderá ser fechado até o processo se lançando em diário foi preenchido para o período.</span><span class="sxs-lookup"><span data-stu-id="033c0-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="033c0-111">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="033c0-111">Close the page.</span></span>
5. <span data-ttu-id="033c0-112">No **painel de Navegação**, vá para **Módulos > Contabilidade > Tarefas periódicas > Lançamento em diário**.</span><span class="sxs-lookup"><span data-stu-id="033c0-112">In the **Navigation pane**, go to **Modules > General ledger > Periodic tasks > Journalizing**.</span></span>
6. <span data-ttu-id="033c0-113">Clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="033c0-113">Click **Filter**.</span></span>
7. <span data-ttu-id="033c0-114">Realce a linha com os critérios do filtro que você deseja definir.</span><span class="sxs-lookup"><span data-stu-id="033c0-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="033c0-115">No campo **Critérios**, informe ou selecione os critérios do filtro.</span><span class="sxs-lookup"><span data-stu-id="033c0-115">In the **Criteria** field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="033c0-116">Clique em **OK** para fechar a página de filtro.</span><span class="sxs-lookup"><span data-stu-id="033c0-116">Click **OK** to close the filter page.</span></span>
10. <span data-ttu-id="033c0-117">Clique em **OK** para iniciar o processo de lançamento em diário.</span><span class="sxs-lookup"><span data-stu-id="033c0-117">Click **OK** to start the journalizing process.</span></span> <span data-ttu-id="033c0-118">Um relatório será gerado depois que o processo foi concluído.</span><span class="sxs-lookup"><span data-stu-id="033c0-118">A report will be generated after the process is complete.</span></span>  

