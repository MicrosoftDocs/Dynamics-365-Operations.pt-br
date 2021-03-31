---
title: Relatar uma ordem de produção como concluída
description: Este procedimento mostra como relatar uma ordem de produção como concluída.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f4848093bd4901d3aa801fc09d7ee3e79d65ebb0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204440"
---
# <a name="report-a-production-order-as-finished"></a><span data-ttu-id="2edf2-103">Relatar uma ordem de produção como concluída</span><span class="sxs-lookup"><span data-stu-id="2edf2-103">Report a production order as finished</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2edf2-104">Este procedimento mostra como relatar uma ordem de produção como concluída.</span><span class="sxs-lookup"><span data-stu-id="2edf2-104">This procedure shows how to report a production order as finished.</span></span> <span data-ttu-id="2edf2-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="2edf2-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="2edf2-106">Este é o sexto procedimento de sete que explica o ciclo de vida da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="2edf2-106">This is the sixth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="report-a-production-order-as-finished"></a><span data-ttu-id="2edf2-107">Relatar uma ordem de produção como concluída</span><span class="sxs-lookup"><span data-stu-id="2edf2-107">Report a production order as finished</span></span>
1. <span data-ttu-id="2edf2-108">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="2edf2-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="2edf2-109">Selecione uma ordem de produção com o status Iniciada.</span><span class="sxs-lookup"><span data-stu-id="2edf2-109">Select a production order that has the Started status.</span></span>  
2. <span data-ttu-id="2edf2-110">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="2edf2-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="2edf2-111">Clique em Relatar como concluído.</span><span class="sxs-lookup"><span data-stu-id="2edf2-111">Click Report as finished.</span></span>
    * <span data-ttu-id="2edf2-112">Nesta página, você pode confirmar a quantidade do produto finalizado a ser informada na conclusão.</span><span class="sxs-lookup"><span data-stu-id="2edf2-112">On this page, you can confirm the quantity of the finished product to be reported as finished.</span></span>  
4. <span data-ttu-id="2edf2-113">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="2edf2-113">Click the General tab.</span></span>
5. <span data-ttu-id="2edf2-114">Defina Quantidade de bens como '18'.</span><span class="sxs-lookup"><span data-stu-id="2edf2-114">Set Good quantity to '18'.</span></span>
6. <span data-ttu-id="2edf2-115">Defina Quantidade de erros como '2'.</span><span class="sxs-lookup"><span data-stu-id="2edf2-115">Set Error quantity to '2'.</span></span>
7. <span data-ttu-id="2edf2-116">No campo Causa do erro, selecione 'Material'.</span><span class="sxs-lookup"><span data-stu-id="2edf2-116">In the Error cause field, select 'Material'.</span></span>
8. <span data-ttu-id="2edf2-117">Marque ou desmarque a caixa de seleção Trabalho final.</span><span class="sxs-lookup"><span data-stu-id="2edf2-117">Select or clear the End job check box.</span></span>
9. <span data-ttu-id="2edf2-118">Marque ou desmarque a caixa de seleção Aceitar erro.</span><span class="sxs-lookup"><span data-stu-id="2edf2-118">Select or clear the Accept error check box.</span></span>
10. <span data-ttu-id="2edf2-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2edf2-119">Click OK.</span></span>

## <a name="verify-the-report-as-finished-journal"></a><span data-ttu-id="2edf2-120">Verificar o diário Relatório de conclusão</span><span class="sxs-lookup"><span data-stu-id="2edf2-120">Verify the Report as finished journal</span></span>
1. <span data-ttu-id="2edf2-121">No Painel de Ação, clique em Exibir.</span><span class="sxs-lookup"><span data-stu-id="2edf2-121">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="2edf2-122">Clique em Informado como concluído.</span><span class="sxs-lookup"><span data-stu-id="2edf2-122">Click Reported as finished.</span></span>
3. <span data-ttu-id="2edf2-123">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2edf2-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="2edf2-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2edf2-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2edf2-125">O diário Relatório de conclusão é lançado.</span><span class="sxs-lookup"><span data-stu-id="2edf2-125">The Report as finished journal is posted.</span></span> <span data-ttu-id="2edf2-126">Se quiser fazer ajustes no diário, você pode criar manualmente um diário no qual é possível fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="2edf2-126">If you want to make adjustments to the journal, you can manually create  a new journal where you can make changes.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]