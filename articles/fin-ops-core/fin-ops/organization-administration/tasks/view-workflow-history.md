---
title: Exibir histórico do fluxo de trabalho
description: Este tópico descreve as etapas para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação.
author: jasongre
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd5b8d9f3fd2edab50b52a8345f254ebc6b31d0a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140389"
---
# <a name="view-workflow-history"></a><span data-ttu-id="d7424-103">Exibir histórico do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d7424-103">View workflow history</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d7424-104">Este tópico descreve as etapas para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação.</span><span class="sxs-lookup"><span data-stu-id="d7424-104">This topic describes the steps to view the status of a document that was submitted to the workflow system for processing and approval.</span></span> <span data-ttu-id="d7424-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="d7424-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="d7424-106">Vá para **Painel de navegação > Módulos > Comum > Consultas > Fluxo de trabalho > Histórico de fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="d7424-106">Go to **Navigation pane > Modules > Common > Inquiries > Workflow > Workflow history**.</span></span>
    - <span data-ttu-id="d7424-107">Use este formulário para exibir o status de um documento que foi enviado ao sistema de fluxo de trabalho para processamento e aprovação.</span><span class="sxs-lookup"><span data-stu-id="d7424-107">Use this form to view the status of a document that was submitted to the workflow system for processing and approval.</span></span>  
    - <span data-ttu-id="d7424-108">A **ID da instância** é o código de identificação da instância do fluxo de trabalho que está processando ou que processou o documento.</span><span class="sxs-lookup"><span data-stu-id="d7424-108">The **Instance ID** is the identification code of the workflow instance that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="d7424-109">O **Status** é o status do fluxo de trabalho do documento.</span><span class="sxs-lookup"><span data-stu-id="d7424-109">The **Status** is the workflow status of the document.</span></span>  
    - <span data-ttu-id="d7424-110">A **ID do fluxo de trabalho** é o código de identificação do fluxo de trabalho que está processando ou que processou o documento.</span><span class="sxs-lookup"><span data-stu-id="d7424-110">The **Workflow ID** is the identification code of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="d7424-111">O **Documento** é o código de identificação do documento.</span><span class="sxs-lookup"><span data-stu-id="d7424-111">The **Document** is the identification code of the document.</span></span>  
    - <span data-ttu-id="d7424-112">O **Tipo de documento** é o tipo de documento que foi enviado para processamento.</span><span class="sxs-lookup"><span data-stu-id="d7424-112">The **Document type** is the type of document that was submitted for processing.</span></span>  
    - <span data-ttu-id="d7424-113">O **Fluxo de trabalho** é o nome do fluxo de trabalho que está processando ou que processou o documento.</span><span class="sxs-lookup"><span data-stu-id="d7424-113">The **Workflow** is the name of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="d7424-114">A **Versão** é o número da versão do fluxo de trabalho que está processando ou que processou o documento.</span><span class="sxs-lookup"><span data-stu-id="d7424-114">The **Version** is the version number of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="d7424-115">A **Data e hora de criação** é a data e a hora em que o documento foi enviado.</span><span class="sxs-lookup"><span data-stu-id="d7424-115">The **Created date and time** is the date and time that the document was submitted.</span></span>  
    - <span data-ttu-id="d7424-116">O **Tempo decorrido** é o tempo passado desde que o documento foi enviado.</span><span class="sxs-lookup"><span data-stu-id="d7424-116">The **Elapsed time** is the time that has passed since the document was submitted.</span></span>  
    - <span data-ttu-id="d7424-117">O botão **Continuar** permite que você continue o processo de fluxo de trabalho para o documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="d7424-117">The **Resume** button allows you to resume the workflow process for the selected document.</span></span>  
    - <span data-ttu-id="d7424-118">O botão **Recuperar** permite recuperar o documento selecionado de forma que não seja processado.</span><span class="sxs-lookup"><span data-stu-id="d7424-118">The **Recall** button allows you to recall the selected document so that it is not processed.</span></span>   
2. <span data-ttu-id="d7424-119">Na lista, selecione o link na linha desejada.</span><span class="sxs-lookup"><span data-stu-id="d7424-119">In the list, select the link in the desired row.</span></span>
    - <span data-ttu-id="d7424-120">Certifique-se de que a seção **Itens de trabalho** está expandida.</span><span class="sxs-lookup"><span data-stu-id="d7424-120">Make sure the **Work items** section is expanded.</span></span> <span data-ttu-id="d7424-121">Nesta seção você pode exibir os itens de trabalho associados ao documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="d7424-121">In this section you can view the work items that are associated with the selected document.</span></span> <span data-ttu-id="d7424-122">Por exemplo, uma tarefa pode precisar ser concluída ou o documento pode precisar de aprovação.</span><span class="sxs-lookup"><span data-stu-id="d7424-122">For example, a task may have to be completed, or the document may have to be approved.</span></span>  
    - <span data-ttu-id="d7424-123">O botão **Reatribuir** abre uma caixa de diálogo na qual é possível reatribuir um item de trabalho a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="d7424-123">The **Reassign** button will open a dialog box where you can reassign a work item to another user.</span></span>  
    - <span data-ttu-id="d7424-124">Certifique-se de que a seção **Detalhes do rastreamento** está expandida.</span><span class="sxs-lookup"><span data-stu-id="d7424-124">Make sure the **Tracking details** section is expanded.</span></span> <span data-ttu-id="d7424-125">Nesta seção você pode exibir o histórico de fluxo de trabalho do documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="d7424-125">In this section you can view the workflow history of the selected document.</span></span>  

