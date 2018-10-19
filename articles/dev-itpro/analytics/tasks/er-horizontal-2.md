--- 
title: "ER Usar intervalos expansíveis horizontalmente para adicionar colunas dinamicamente em relatórios do Excel (Parte 2 - Executar formato)"
description: "As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico (ER) pode configurar um formato para gerar relatórios como arquivos OPENXML de planilhas de Excel em que as colunas exigidas possam ser criadas dinamicamente como intervalos expansíveis horizontalmente."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 33c1a3134659bb66a67166fec3d7f53af0aa4c6c
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2-run-format"></a><span data-ttu-id="d826f-103">O ER horizontalmente usar intervalos expansíveis dinamicamente para adicionar colunas em relatórios do Excel (Parte 2: executar formato)</span><span class="sxs-lookup"><span data-stu-id="d826f-103">ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 2: Run format)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d826f-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico (ER) pode configurar um formato para gerar relatórios como arquivos OPENXML de planilhas de Excel em que as colunas exigidas possam ser criadas dinamicamente como intervalos expansíveis horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="d826f-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to generate reports as OPENXML worksheets (Excel) files in which the required columns can be created dynamically as horizontally expandable ranges.</span></span> <span data-ttu-id="d826f-105">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="d826f-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="d826f-106">Para concluir essas etapas, primeiramente você deve concluir as etapas no procedimento "ER Usar intervalos expansíveis horizontalmente para adicionar colunas a relatórios Excel dinamicamente (Parte 1: criar formato)".</span><span class="sxs-lookup"><span data-stu-id="d826f-106">To complete these steps, you must first complete the steps in the “ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)” procedure.</span></span>

<span data-ttu-id="d826f-107">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="d826f-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="find-created-format"></a><span data-ttu-id="d826f-108">Localizar formato criado</span><span class="sxs-lookup"><span data-stu-id="d826f-108">Find created format</span></span>
1. <span data-ttu-id="d826f-109">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="d826f-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="d826f-110">Na árvore, expanda "Modelo de exemplo de dimensões financeiras".</span><span class="sxs-lookup"><span data-stu-id="d826f-110">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="d826f-111">Na árvore, selecione 'Modelo de exemplo de dimensão financeira\Relatório de exemplo com intervalos expansíveis horizontalmente'.</span><span class="sxs-lookup"><span data-stu-id="d826f-111">In the tree, select 'Financial dimensions sample model\Sample report with horizontally expandable ranges'.</span></span>

## <a name="execute-format-to-create-excel-output"></a><span data-ttu-id="d826f-112">Executar o formato para criar saída do Excel</span><span class="sxs-lookup"><span data-stu-id="d826f-112">Execute format to create Excel output</span></span>
1. <span data-ttu-id="d826f-113">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="d826f-113">Click Run.</span></span>
2. <span data-ttu-id="d826f-114">No campo Nome da dimensão, digite 'BusinessUnit;CostCenter;Department'.</span><span class="sxs-lookup"><span data-stu-id="d826f-114">In the Dimension name field, type 'BusinessUnit;CostCenter;Department'.</span></span>
    * <span data-ttu-id="d826f-115">No campo Nome da dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d826f-115">In the Dimension name field, enter or select a value.</span></span>  <span data-ttu-id="d826f-116">Para selecionar todas as dimensões da empresa atual, insira o seguinte: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="d826f-116">To select all dimensions for the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
3. <span data-ttu-id="d826f-117">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="d826f-117">Expand the Records to include section.</span></span>
4. <span data-ttu-id="d826f-118">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="d826f-118">Click Filter.</span></span>
5. <span data-ttu-id="d826f-119">Selecione a linha para a tabela Diário-razão e o campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="d826f-119">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
6. <span data-ttu-id="d826f-120">No campo Critérios, digite '00057..00058'.</span><span class="sxs-lookup"><span data-stu-id="d826f-120">In the Criteria field, type '00057..00058'.</span></span>
    * <span data-ttu-id="d826f-121">00057..00058</span><span class="sxs-lookup"><span data-stu-id="d826f-121">00057..00058</span></span>  
7. <span data-ttu-id="d826f-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d826f-122">Click OK.</span></span>
8. <span data-ttu-id="d826f-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d826f-123">Click OK.</span></span>
    * <span data-ttu-id="d826f-124">Revise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="d826f-124">Review the generated output.</span></span> <span data-ttu-id="d826f-125">Observe que o arquivo Excel recém-criado contém o mesmo número de colunas que foram selecionadas para as dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="d826f-125">Note that the newly created Excel file contains the same number of columns that were selected for financial dimensions.</span></span> <span data-ttu-id="d826f-126">O cabeçalho do relatório nessas colunas representa os nomes das dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="d826f-126">The report header in those columns represents financial dimensions’ names.</span></span> <span data-ttu-id="d826f-127">As linhas das transações nessas colunas representam as dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="d826f-127">The transactions’ lines in those columns represent financial dimensions.</span></span> <span data-ttu-id="d826f-128">Execute esse relatório e selecione diferentes dimensões para verificar se o relatório não é dependente do número de dimensões selecionadas ou do número de dimensões configuradas para essa instância do Dynamics 365 for Finance and Operations, edição Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d826f-128">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations, Enterprise edition instance.</span></span>  


