---
title: Gerar documentos com dados da solicitação de emprego
description: Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER Gerar documentos com atualização de dados de aplicativo (Parte 4 – Modificar formato)".
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d95feb3395c36f9cf8a23770dc3173377067d9b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184867"
---
# <a name="generate-documents-that-have-application-data"></a><span data-ttu-id="f64df-103">Gerar documentos com dados da solicitação de emprego</span><span class="sxs-lookup"><span data-stu-id="f64df-103">Generate documents that have application data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f64df-104">Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER Gerar documentos com atualização de dados de aplicativo (Parte 4: Modificar formato)".</span><span class="sxs-lookup"><span data-stu-id="f64df-104">To complete the steps in this procedure, you must first complete the procedure, “ER Generate documents with application data update (Part 4: Modify format)”.</span></span>



<span data-ttu-id="f64df-105">As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico e atualizar os dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f64df-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="f64df-106">Nesse procedimento, você executa a configuração de formato de ER para gerar dados de aplicativo de atualização e de relatório Intrastat para arquivar detalhes do processo de relatório.</span><span class="sxs-lookup"><span data-stu-id="f64df-106">In this procedure, you execute the ER format configuration to generate the Intrastat report and update application data for archiving details of the reporting process.</span></span>



<span data-ttu-id="f64df-107">Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="f64df-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="f64df-108">Estas etapas podem ser concluídas usando o conjunto de dados de DEMF.</span><span class="sxs-lookup"><span data-stu-id="f64df-108">These steps can be completed using the DEMF dataset.</span></span> <span data-ttu-id="f64df-109">Antes de começar, verifique se o contexto de país para a empresa de DEMF é BEL (Bélgica).</span><span class="sxs-lookup"><span data-stu-id="f64df-109">Before you begin, make sure that the country context for the DEMF company is BEL (Belgium).</span></span>


## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="f64df-110">Configurar parâmetros de comércio exterior</span><span class="sxs-lookup"><span data-stu-id="f64df-110">Set up foreign trade parameters</span></span>
1. <span data-ttu-id="f64df-111">Vá para Imposto > Configuração > Comércio exterior > Parâmetros de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="f64df-111">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="f64df-112">Clique na aba Sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="f64df-112">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="f64df-113">Arquivando detalhes de processo de relatório Intrastat, precisamos identificar registros de cada arquivo morto que criamos.</span><span class="sxs-lookup"><span data-stu-id="f64df-113">Archiving details of Intrastat reporting process, we need to identify records of each archive we created.</span></span> <span data-ttu-id="f64df-114">Uma sequência numérica especial deve ser configurada para isso.</span><span class="sxs-lookup"><span data-stu-id="f64df-114">A special number sequence must be configured for that.</span></span>  
3. <span data-ttu-id="f64df-115">Selecione a referência 'ID de arquivo morto Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="f64df-115">Select the ‘Intrastat archive ID’ reference.</span></span>
4. <span data-ttu-id="f64df-116">No campo Número, selecione campo Código, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f64df-116">In the Number sequence code field, type a value.</span></span>
    * <span data-ttu-id="f64df-117">No campo 'Código de sequência numérica', digite ou selecione o valor ‘Fore_2’.</span><span class="sxs-lookup"><span data-stu-id="f64df-117">In the ‘Number sequence code’ field, enter or select the value ‘Fore_2’.</span></span>  
5. <span data-ttu-id="f64df-118">Altera o código de sequência numérica</span><span class="sxs-lookup"><span data-stu-id="f64df-118">ResolveChanges the Number sequence code.</span></span>
6. <span data-ttu-id="f64df-119">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f64df-119">Click Save.</span></span>
7. <span data-ttu-id="f64df-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f64df-120">Close the page.</span></span>

## <a name="run-modified-er-format"></a><span data-ttu-id="f64df-121">Execute o formato de ER modificado</span><span class="sxs-lookup"><span data-stu-id="f64df-121">Run modified ER format</span></span>
1. <span data-ttu-id="f64df-122">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="f64df-122">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="f64df-123">Na árvore, expanda 'Intrastat (model)'.</span><span class="sxs-lookup"><span data-stu-id="f64df-123">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="f64df-124">Na árvore, selecione 'Intrastat (modelo)\Intrastat (formato)'.</span><span class="sxs-lookup"><span data-stu-id="f64df-124">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="f64df-125">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="f64df-125">Click Run.</span></span>
5. <span data-ttu-id="f64df-126">No campo Inserir nome do arquivo, digite 'intrastat2.xml'.</span><span class="sxs-lookup"><span data-stu-id="f64df-126">In the Enter file name field, type 'intrastat2.xml'.</span></span>
    * <span data-ttu-id="f64df-127">intrastat2.xml</span><span class="sxs-lookup"><span data-stu-id="f64df-127">intrastat2.xml</span></span>  
6. <span data-ttu-id="f64df-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f64df-128">Click OK.</span></span>

## <a name="review-er-format-executions-results"></a><span data-ttu-id="f64df-129">Revise os resultados de execução de formato do ER</span><span class="sxs-lookup"><span data-stu-id="f64df-129">Review ER format execution’s results</span></span>
    * <span data-ttu-id="f64df-130">Revise o arquivo XML gerado.</span><span class="sxs-lookup"><span data-stu-id="f64df-130">Review the generated XML file.</span></span>  
1. <span data-ttu-id="f64df-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f64df-131">Close the page.</span></span>
2. <span data-ttu-id="f64df-132">Vá para Imposto > Declarações > Comércio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="f64df-132">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="f64df-133">Abra este formulário que contém as transações Intrastat que foram incluídas no documento eletrônico gerado.</span><span class="sxs-lookup"><span data-stu-id="f64df-133">Open this form containing Intrastat transactions that have been included to the generated electronic document.</span></span>  
3. <span data-ttu-id="f64df-134">Clique em Arquivo morto Intrastat.</span><span class="sxs-lookup"><span data-stu-id="f64df-134">Click Intrastat archive.</span></span>
    * <span data-ttu-id="f64df-135">Como o formato de ER executado agora contém configurações para a atualização de dados do aplicativo, os detalhes de relatório Intrastat concluído não foram arquivados.</span><span class="sxs-lookup"><span data-stu-id="f64df-135">Since the executed ER format contains now settings for application data update, the details of the completed Intrastat reporting have been archived.</span></span> <span data-ttu-id="f64df-136">Neste formulário, você pode consultar o registro de cabeçalho do arquivo-morto criado.</span><span class="sxs-lookup"><span data-stu-id="f64df-136">In this form, you can see the header record of the created archive.</span></span>  
4. <span data-ttu-id="f64df-137">Clique em Detalhes.</span><span class="sxs-lookup"><span data-stu-id="f64df-137">Click Details.</span></span>
    * <span data-ttu-id="f64df-138">Neste formulário, você pode consultar os detalhes do arquivo-morto criado.</span><span class="sxs-lookup"><span data-stu-id="f64df-138">In this form, you can see the details for the created archive.</span></span>  
5. <span data-ttu-id="f64df-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f64df-139">Close the page.</span></span>
6. <span data-ttu-id="f64df-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f64df-140">Close the page.</span></span>
7. <span data-ttu-id="f64df-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f64df-141">Close the page.</span></span>

