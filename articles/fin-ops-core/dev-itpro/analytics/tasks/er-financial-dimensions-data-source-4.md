---
title: 'ER Usar dimensões financeiras como uma fonte de dados (Parte 4: Executar o relatório)'
description: As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 27498fb8290fa18abd64d7f306e9c0bf4713a72f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550125"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a><span data-ttu-id="ca58c-103">ER Usar dimensões financeiras como uma fonte de dados (Parte 4: Executar o relatório)</span><span class="sxs-lookup"><span data-stu-id="ca58c-103">ER Use financial dimensions as a data source (Part 4 - Run the report)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ca58c-104">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="ca58c-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="ca58c-105">Essas etapas podem ser executadas na empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="ca58c-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="ca58c-106">Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento “ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório).</span><span class="sxs-lookup"><span data-stu-id="ca58c-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 3: Design the report)” procedure.</span></span> <span data-ttu-id="ca58c-107">Você também deve configurar os tipos de documento padrão na página Parâmetros de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ca58c-107">You must also configure default document types on the Electronic reporting parameters page.</span></span> <span data-ttu-id="ca58c-108">Os tipos de documento padrão também são definidos quando você baixa e importa qualquer configuração ER.</span><span class="sxs-lookup"><span data-stu-id="ca58c-108">Default document types are also set when you download and import any ER configuration.</span></span> 


## <a name="run-report"></a><span data-ttu-id="ca58c-109">Executar relatório</span><span class="sxs-lookup"><span data-stu-id="ca58c-109">Run report</span></span>
1. <span data-ttu-id="ca58c-110">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="ca58c-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="ca58c-111">Na árvore, expanda "Modelo de exemplo de dimensões financeiras".</span><span class="sxs-lookup"><span data-stu-id="ca58c-111">In the tree, expand 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="ca58c-112">Na árvore, selecione "Modelo de exemplo de dimensões financeiras\Relatório de diário-razão".</span><span class="sxs-lookup"><span data-stu-id="ca58c-112">In the tree, select 'Financial dimensions sample model\Ledger journal report'.</span></span>
4. <span data-ttu-id="ca58c-113">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="ca58c-113">Click Run.</span></span>
5. <span data-ttu-id="ca58c-114">No campo Nome de dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ca58c-114">In the Dimension name field, In the Dimension name field, enter or select a value..</span></span>
    * <span data-ttu-id="ca58c-115">Para selecionar todas as dimensões na empresa atual, insira o seguinte:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span><span class="sxs-lookup"><span data-stu-id="ca58c-115">To select all dimensions in the current company, enter the following:  BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project</span></span>  
6. <span data-ttu-id="ca58c-116">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="ca58c-116">Expand the Records to include section.</span></span>
7. <span data-ttu-id="ca58c-117">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="ca58c-117">Click Filter.</span></span>
8. <span data-ttu-id="ca58c-118">Selecione a linha para a tabela Diário-razão e o campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="ca58c-118">Select the row for the Ledger journal table and the Journal batch number field.</span></span>
9. <span data-ttu-id="ca58c-119">No campo Critérios, digite "00057".</span><span class="sxs-lookup"><span data-stu-id="ca58c-119">In the Criteria field, type '00057'.</span></span>
10. <span data-ttu-id="ca58c-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ca58c-120">Click OK.</span></span>
11. <span data-ttu-id="ca58c-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ca58c-121">Click OK.</span></span>
    * <span data-ttu-id="ca58c-122">Revise a saída gerada.</span><span class="sxs-lookup"><span data-stu-id="ca58c-122">Review the generated output.</span></span> <span data-ttu-id="ca58c-123">Observe que, para cada transação do lote selecionado, as dimensões financeiras do conjunto de dimensões correspondentes são apresentadas.</span><span class="sxs-lookup"><span data-stu-id="ca58c-123">Note that for each transaction of the selected batch, the financial dimensions from the corresponding dimensions set are presented.</span></span> <span data-ttu-id="ca58c-124">Execute esse relatório e selecione dimensões diferentes para verificar se o relatório não é dependente do número de dimensões selecionadas ou do número de dimensões configuradas para essa instância.</span><span class="sxs-lookup"><span data-stu-id="ca58c-124">Run this report and select different dimensions to see that the report is not dependent on the number of selected dimensions or the number of dimensions configured for this instance.</span></span>  

