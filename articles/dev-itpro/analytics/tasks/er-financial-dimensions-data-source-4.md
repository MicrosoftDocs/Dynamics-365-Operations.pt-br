--- 
title: "Executar um relatório que use dimensões financeiras como uma fonte de dados"
description: "As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 47ba48461a1c502a93df416d1acac1e85a841079
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="run-a-report-that-uses-financial-dimensions-as-a-data-source"></a><span data-ttu-id="8d691-103">Executar um relatório que use dimensões financeiras como uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="8d691-103">Run a report that uses financial dimensions as a data source</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8d691-104">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="8d691-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="8d691-105">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="8d691-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="8d691-106">Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento “ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório).</span><span class="sxs-lookup"><span data-stu-id="8d691-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 3: Design the report)” procedure.</span></span> <span data-ttu-id="8d691-107">Você também deve configurar os tipos de documento padrão na página Parâmetros de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8d691-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="8d691-108">Os tipos de documento padrão também são definidos quando você baixa e importa qualquer configuração ER.</span><span class="sxs-lookup"><span data-stu-id="8d691-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="8d691-109">Executar relatório</span><span class="sxs-lookup"><span data-stu-id="8d691-109">Run report</span></span>
1. <span data-ttu-id="8d691-110">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="8d691-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="8d691-111">Na árvore, expanda "Modelo de exemplo de dimensões financeiras".</span><span class="sxs-lookup"><span data-stu-id="8d691-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="8d691-112">Na árvore, selecione "Modelo de exemplo de dimensões financeiras\Relatório de diário-razão".</span><span class="sxs-lookup"><span data-stu-id="8d691-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="8d691-113">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="8d691-113">Click Run.</span></span>
5. <span data-ttu-id="8d691-114">No campo Nome de dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="8d691-114">In the Dimension name field, In the Dimension name field, enter or select a value.</span></span>
    * <span data-ttu-id="8d691-115">Para selecionar todas as dimensões na empresa atual, insira o seguinte:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="8d691-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="8d691-116">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="8d691-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="8d691-117">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="8d691-117">Click Filter.</span></span>
8. <span data-ttu-id="8d691-118">Selecione a linha para a tabela Diário-razão e o campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="8d691-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="8d691-119">No campo Critérios, digite "00057".</span><span class="sxs-lookup"><span data-stu-id="8d691-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="8d691-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8d691-120">Click OK.</span></span>
11. <span data-ttu-id="8d691-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8d691-121">Click OK.</span></span>
    * <span data-ttu-id="8d691-122">Revise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="8d691-122">Review the generated output.</span></span> <span data-ttu-id="8d691-123">Observe que, para cada transação do lote selecionado, as dimensões financeiras do conjunto de dimensões correspondentes são apresentadas.</span><span class="sxs-lookup"><span data-stu-id="8d691-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="8d691-124">Execute esse relatório e selecione diferentes dimensões para verificar se o relatório não é dependente do número de dimensões selecionadas ou do número de dimensões configuradas para essa instância do Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8d691-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this Dynamics 365 for Finance and Operations instance.</span></span>  


