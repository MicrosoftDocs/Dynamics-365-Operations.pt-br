--- 
title: "Exibir histórico do fluxo de trabalho"
description: "Use estas etapas para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 212f9fe8bc7807b9209523564ead716959875241
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="view-workflow-history"></a><span data-ttu-id="3f21c-103">Exibir histórico do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="3f21c-103">View workflow history</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3f21c-104">Use estas etapas para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação.</span><span class="sxs-lookup"><span data-stu-id="3f21c-104">Use these steps to view the status of a document that was submitted to the workflow system for processing and approval.</span></span> <span data-ttu-id="3f21c-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="3f21c-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="3f21c-106">Vá para Comum > Consultas > Fluxo de Trabalho > Histórico do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3f21c-106">Go to Common > Inquiries > Workflow > Workflow history.</span></span>
    * <span data-ttu-id="3f21c-107">Use este formulário para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação.</span><span class="sxs-lookup"><span data-stu-id="3f21c-107">Use this form to view the status of a document that was submitted to the workflow system for processing and approval.</span></span>  
    * <span data-ttu-id="3f21c-108">A ID da instância é o código de identificação da instância do fluxo de trabalho que está processando ou que processou o documento.</span><span class="sxs-lookup"><span data-stu-id="3f21c-108">The Instance ID is      the identification code of the workflow instance that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="3f21c-109">O Status é o status do fluxo de trabalho do documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="3f21c-109">The Status is the workflow status of the document.</span></span>  
    * <span data-ttu-id="3f21c-110">O ID do Fluxo de trabalho é o código de identificação do fluxo de trabalho que está processando ou que processou o documento.</span><span class="sxs-lookup"><span data-stu-id="3f21c-110">The Workflow ID is the identification code of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="3f21c-111">O Documento é o código de identificação do documento.</span><span class="sxs-lookup"><span data-stu-id="3f21c-111">The Document is the identification code of the document.</span></span>  
    * <span data-ttu-id="3f21c-112">O tipo de Documento é o tipo de documento que foi enviado para processamento.</span><span class="sxs-lookup"><span data-stu-id="3f21c-112">The Document type is the type of document that was submitted for processing.</span></span>  
    * <span data-ttu-id="3f21c-113">O Fluxo de trabalho é o nome do fluxo de trabalho que está processando ou que processou o documento.</span><span class="sxs-lookup"><span data-stu-id="3f21c-113">The Workflow is the name of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="3f21c-114">A Versão é o número da versão do fluxo de trabalho que está processando ou que processou o documento.</span><span class="sxs-lookup"><span data-stu-id="3f21c-114">The Version is the version number of the workflow that is processing, or has processed the document.</span></span>  
    * <span data-ttu-id="3f21c-115">A Data e hora de criação é a data e a hora em que o documento foi enviado.</span><span class="sxs-lookup"><span data-stu-id="3f21c-115">The Created date and time is the date and time that the document was submitted.</span></span>  
    * <span data-ttu-id="3f21c-116">O Tempo decorrido é o tempo passado desde que o documento foi enviado.</span><span class="sxs-lookup"><span data-stu-id="3f21c-116">The Elapsed time is the time that has passed since the document was submitted.</span></span>  
    * <span data-ttu-id="3f21c-117">O botão Continuar permite que você continue o processo de fluxo de trabalho para o documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="3f21c-117">The Resume button allows you to resume the workflow process for the selected document.</span></span>  
    * <span data-ttu-id="3f21c-118">O botão Recuperar permite recuperar o documento selecionado de forma que não seja processado.</span><span class="sxs-lookup"><span data-stu-id="3f21c-118">The Recall button allows you to recall the selected document so that it is not processed.</span></span>   
2. <span data-ttu-id="3f21c-119">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3f21c-119">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="3f21c-120">Certifique-se de que a seção Itens de trabalho está expandida.</span><span class="sxs-lookup"><span data-stu-id="3f21c-120">Make sure the Work items section is expanded.</span></span>    <span data-ttu-id="3f21c-121">Nesta seção você pode exibir os itens de trabalho associados ao documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="3f21c-121">In this section you can view the work items that are associated with the selected document.</span></span> <span data-ttu-id="3f21c-122">Por exemplo, uma tarefa pode precisar ser concluída ou o documento pode precisar de aprovação.</span><span class="sxs-lookup"><span data-stu-id="3f21c-122">For example, a task may have to be completed, or the document may have to be approved.</span></span>  
    * <span data-ttu-id="3f21c-123">O botão Reatribuir abre uma caixa de diálogo na qual é possível reatribuir um item de trabalho a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="3f21c-123">The Reassign button will open a dialog box where you can reassign a work item to another user.</span></span>  
    * <span data-ttu-id="3f21c-124">Certifique-se de que a seção Detalhes do rastreamento está expandida.</span><span class="sxs-lookup"><span data-stu-id="3f21c-124">Make sure the Tracking details section is expanded.</span></span>    <span data-ttu-id="3f21c-125">Nesta seção você pode exibir o histórico de fluxo de trabalho do documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="3f21c-125">In this section you can view the workflow history of the selected document.</span></span>  


