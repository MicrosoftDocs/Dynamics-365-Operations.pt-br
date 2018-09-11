--- 
title: "Relatar uma ordem de produção como concluída"
description: "Este procedimento mostra como relatar uma ordem de produção como concluída."
author: johanhoffmann
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 3ad1027eccd543adf883890d343705b928daa405
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="report-a-production-order-as-finished"></a><span data-ttu-id="26dbf-103">Relatar uma ordem de produção como concluída</span><span class="sxs-lookup"><span data-stu-id="26dbf-103">Report a production order as finished</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="26dbf-104">Este procedimento mostra como relatar uma ordem de produção como concluída.</span><span class="sxs-lookup"><span data-stu-id="26dbf-104">This procedure shows how to report a production order as finished.</span></span> <span data-ttu-id="26dbf-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="26dbf-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="26dbf-106">Este é o sexto procedimento de sete que explica o ciclo de vida da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="26dbf-106">This is the sixth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="report-a-production-order-as-finished"></a><span data-ttu-id="26dbf-107">Relatar uma ordem de produção como concluída</span><span class="sxs-lookup"><span data-stu-id="26dbf-107">Report a production order as finished</span></span>
1. <span data-ttu-id="26dbf-108">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="26dbf-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="26dbf-109">Selecione uma ordem de produção com o status Iniciada.</span><span class="sxs-lookup"><span data-stu-id="26dbf-109">Select a production order that has the Started status.</span></span>  
2. <span data-ttu-id="26dbf-110">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="26dbf-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="26dbf-111">Clique em Relatar como concluído.</span><span class="sxs-lookup"><span data-stu-id="26dbf-111">Click Report as finished.</span></span>
    * <span data-ttu-id="26dbf-112">Nesta página, você pode confirmar a quantidade do produto finalizado a ser informada na conclusão.</span><span class="sxs-lookup"><span data-stu-id="26dbf-112">On this page, you can confirm the quantity of the finished product to be reported as finished.</span></span>  
4. <span data-ttu-id="26dbf-113">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="26dbf-113">Click the General tab.</span></span>
5. <span data-ttu-id="26dbf-114">Defina Quantidade de bens como '18'.</span><span class="sxs-lookup"><span data-stu-id="26dbf-114">Set Good quantity to '18'.</span></span>
6. <span data-ttu-id="26dbf-115">Defina Quantidade de erros como '2'.</span><span class="sxs-lookup"><span data-stu-id="26dbf-115">Set Error quantity to '2'.</span></span>
7. <span data-ttu-id="26dbf-116">No campo Causa do erro, selecione 'Material'.</span><span class="sxs-lookup"><span data-stu-id="26dbf-116">In the Error cause field, select 'Material'.</span></span>
8. <span data-ttu-id="26dbf-117">Marque ou desmarque a caixa de seleção Trabalho final.</span><span class="sxs-lookup"><span data-stu-id="26dbf-117">Select or clear the End job check box.</span></span>
9. <span data-ttu-id="26dbf-118">Marque ou desmarque a caixa de seleção Aceitar erro.</span><span class="sxs-lookup"><span data-stu-id="26dbf-118">Select or clear the Accept error check box.</span></span>
10. <span data-ttu-id="26dbf-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="26dbf-119">Click OK.</span></span>

## <a name="verify-the-report-as-finished-journal"></a><span data-ttu-id="26dbf-120">Verificar o diário Relatório de conclusão</span><span class="sxs-lookup"><span data-stu-id="26dbf-120">Verify the Report as finished journal</span></span>
1. <span data-ttu-id="26dbf-121">No Painel de Ação, clique em Exibir.</span><span class="sxs-lookup"><span data-stu-id="26dbf-121">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="26dbf-122">Clique em Informado como concluído.</span><span class="sxs-lookup"><span data-stu-id="26dbf-122">Click Reported as finished.</span></span>
3. <span data-ttu-id="26dbf-123">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="26dbf-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="26dbf-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="26dbf-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="26dbf-125">O diário Relatório de conclusão é lançado.</span><span class="sxs-lookup"><span data-stu-id="26dbf-125">The Report as finished journal is posted.</span></span> <span data-ttu-id="26dbf-126">Se quiser fazer ajustes no diário, você pode criar manualmente um diário no qual é possível fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="26dbf-126">If you want to make adjustments to the journal, you can manually create  a new journal where you can make changes.</span></span>  


