---
title: Liberar uma ordem de produção
description: Este procedimento mostra como liberar uma ordem de produção.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f5c5ca5ebf51d0722318c455e6ca59d3a893793
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831953"
---
# <a name="release-a-production-order"></a><span data-ttu-id="1ffdf-103">Liberar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="1ffdf-103">Release a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1ffdf-104">Este procedimento mostra como liberar uma ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-104">This procedure shows how to release a production order.</span></span> <span data-ttu-id="1ffdf-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="1ffdf-106">Este é o quarto procedimento de sete que explica o ciclo de vida da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-106">This is the fourth procedure out of seven which explains the production order lifecycle.</span></span>

1. <span data-ttu-id="1ffdf-107">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-107">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="1ffdf-108">Na grade, selecione uma ordem de produção que tem o status Agendado.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-108">In the grid, select a production order that has the Scheduled status.</span></span>  
2. <span data-ttu-id="1ffdf-109">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-109">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="1ffdf-110">Clique em Liberar.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-110">Click Release.</span></span>
    * <span data-ttu-id="1ffdf-111">Nesta página, você pode confirmar a versão do intervalo selecionado de ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-111">On this page, you can confirm the release of the selected range of production orders.</span></span> <span data-ttu-id="1ffdf-112">Clique em Selecionar se deseja adicionar ordens.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-112">Click Select if you want to add orders.</span></span>  
    * <span data-ttu-id="1ffdf-113">A etapa de liberação indica quando a ordem de produção é liberada para o chão de fábrica de produção de modo que os operadores de chão de fábrica possam informar o progresso no trabalho de produção.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-113">The Release step indicates when the production order is released to the production shop floor so that the shop floor operators can report progress on the production jobs.</span></span> <span data-ttu-id="1ffdf-114">Os documentos de produção que contêm informações relevantes sobre o processamento do trabalho podem ser emitidos.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-114">Production papers that contain relevant information about processing the jobs can be issued.</span></span> <span data-ttu-id="1ffdf-115">O trabalho de depósito para a separação de matéria-prima é gerado para os itens configurados para o processo de depósito.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-115">The warehouse work for raw material picking is generated for the items that are set up for the warehouse process.</span></span>  
4. <span data-ttu-id="1ffdf-116">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-116">Click the General tab.</span></span>
    * <span data-ttu-id="1ffdf-117">Selecione os relatórios de produção que devem ser impressos.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-117">Select which production reports should be printed.</span></span> <span data-ttu-id="1ffdf-118">O relatório de ficha de trabalho imprime uma página para cada trabalho programado e requer a ordem de produção a ser planejada no nível do profissional.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-118">The Job card report prints a page for each scheduled job and requires the production order to be scheduled at the job level.</span></span> <span data-ttu-id="1ffdf-119">O relatório contém informações sobre as horas inicial e final programadas, a quantidade a gerar e o recurso que processa os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-119">The report contains information about the scheduled start and end time, the quantity to produce, and which resource processes the job.</span></span> <span data-ttu-id="1ffdf-120">O relatório de roteiro de trabalho coleta as mesmas informações na mesma página, mas não imprime uma página para cada trabalho.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-120">The Route job report collects the same information on the same page, but does not print a page for each job.</span></span> <span data-ttu-id="1ffdf-121">O relatório de cartão de roteiro mostra apenas as operações, mas não os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-121">The Route card report only shows the operations but not the jobs.</span></span> <span data-ttu-id="1ffdf-122">Consequentemente, este relatório não requer o plano de trabalho, mas pode ser usado quando as ordens de produção são planejadas no nível da operação.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-122">Therefore, this report does not require job scheduling, but can be used when production orders are scheduled at the operation level.</span></span>  
5. <span data-ttu-id="1ffdf-123">Clique na caixa de seleção Imprimir cartão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-123">Click the Print route card checkbox.</span></span>
6. <span data-ttu-id="1ffdf-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-124">Click OK.</span></span>
7. <span data-ttu-id="1ffdf-125">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1ffdf-125">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]