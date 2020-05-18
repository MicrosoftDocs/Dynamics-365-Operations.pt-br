---
title: Criar modelos de previsão para orçamentos de projeto
description: Este tópico descreve como criar um modelo de previsão para orçamentos restantes.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321770"
---
# <a name="create-forecast-models-for-project-budgets"></a><span data-ttu-id="2a668-103">Criar modelos de previsão para orçamentos de projeto</span><span class="sxs-lookup"><span data-stu-id="2a668-103">Create forecast models for project budgets</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a668-104">Este tópico descreve como criar um modelo de previsão para orçamentos restantes.</span><span class="sxs-lookup"><span data-stu-id="2a668-104">This topic describes how to create a forecast model for remaining budgets.</span></span> <span data-ttu-id="2a668-105">Um projeto que está sujeito ao controle de orçamento usa dois tipos de orçamentos: original e restante.</span><span class="sxs-lookup"><span data-stu-id="2a668-105">A project that is subject to budget control uses two types of budgets: original and remaining.</span></span> <span data-ttu-id="2a668-106">Ao criar um orçamento de projeto, você deve especificar os modelos de previsão de orçamento original e restante que foram criados na página **Modelos de previsão**.</span><span class="sxs-lookup"><span data-stu-id="2a668-106">When you create a project budget, you must specify the original and remaining budget forecast models that were created in the **Forecast models** page.</span></span> <span data-ttu-id="2a668-107">Os orçamentos de projeto baseados nos modelos especificados são criados quando você compromete o orçamento do projeto.</span><span class="sxs-lookup"><span data-stu-id="2a668-107">Project budgets based on the specified models are created when you commit the project budget.</span></span>

> [!NOTE]
> <span data-ttu-id="2a668-108">Um modelo de previsão usado para controle de orçamento não pode ter um submodelo ou ser usado como um submodelo.</span><span class="sxs-lookup"><span data-stu-id="2a668-108">A forecast model that is used for budget control can’t have a submodel or be used as a submodel.</span></span>

1. <span data-ttu-id="2a668-109">Selecione **Gerenciamento e contabilidade do projeto** > **Configuração** > **Previsões**  > **Modelos de previsão**.</span><span class="sxs-lookup"><span data-stu-id="2a668-109">Select **Project management and accounting** > **Setup** > **Forecasts**  > **Forecast models**.</span></span>
2. <span data-ttu-id="2a668-110">Selecione **Novo** para criar um novo modelo de previsão e insira um número de ID de modelo e um nome para o novo modelo.</span><span class="sxs-lookup"><span data-stu-id="2a668-110">Select **New** to create a new forecast model, and then enter a model ID number and name for the new model.</span></span> 
3. <span data-ttu-id="2a668-111">Defina a opção **Interrompido** como **Sim** para impedir qualquer alteração nas linhas de previsão para o modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="2a668-111">Set the **Stopped** option to **Yes** to prevent any changes to the forecast lines for the forecast model.</span></span> 
4. <span data-ttu-id="2a668-112">Se as linhas de previsão às quais o modelo está associado devem gerar previsões de fluxo de caixa na contabilidade, defina **Incluir em previsões de fluxo de pagamento à vista** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2a668-112">If the forecast lines that the model is associated with should generate cash flow forecasts in the general ledger, set **Include in Cash flow forecasts** to **Yes.**</span></span> 
5. <span data-ttu-id="2a668-113">Para usar a data do projeto como a data da nota fiscal, defina **Data da previsão da nota fiscal** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2a668-113">To use the project date as the invoice date, set **Forecast Invoice date** to **Yes**.</span></span> 
6. <span data-ttu-id="2a668-114">No campo **Tipo de orçamento**, selecione um dos seguintes tipos de modelo:</span><span class="sxs-lookup"><span data-stu-id="2a668-114">In the **Budget type** field, select one of the following model types:</span></span>

   - <span data-ttu-id="2a668-115">**Orçamento original**: use os valores do orçamento original que são comprometidos quando o orçamento inicial é criado e aprovado.</span><span class="sxs-lookup"><span data-stu-id="2a668-115">**Original budget**: Use the original budget amounts that are committed when the initial budget is created and approved.</span></span>
   - <span data-ttu-id="2a668-116">**Orçamento restante**: use os valores do orçamento restante durante a vida útil do projeto.</span><span class="sxs-lookup"><span data-stu-id="2a668-116">**Remaining budget**: Use the remaining budget amounts during the life of the project.</span></span> <span data-ttu-id="2a668-117">Os saldos neste modelo de previsão são reduzidos por transações reais e aumentados ou reduzidos por revisões de orçamento.</span><span class="sxs-lookup"><span data-stu-id="2a668-117">The balances in this forecast model are reduced by actual transactions and increased or decreased by budget revisions.</span></span>
   - <span data-ttu-id="2a668-118">**Postergação**: use os valores de orçamento mantido para uso futuro do projeto.</span><span class="sxs-lookup"><span data-stu-id="2a668-118">**Carry-forward**: Use the carry-forward budget amounts for the project.</span></span> <span data-ttu-id="2a668-119">Postergar é um processo opcional que pode ser executado para transferir valores de orçamento não utilizados de um ano fiscal para outro.</span><span class="sxs-lookup"><span data-stu-id="2a668-119">Carry-forward is an optional process that can be run to transfer unused budget amounts from one fiscal year to another.</span></span>

7. <span data-ttu-id="2a668-120">Defina as seguintes opções, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="2a668-120">Set the following options as required:</span></span>

   - <span data-ttu-id="2a668-121">Habilite **Data da previsão da nota fiscal** para usar a data do projeto como a data da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="2a668-121">Enable **Forecast invoice date** to use the project date as the invoice date.</span></span>
   - <span data-ttu-id="2a668-122">Habilite **Previsão com WIP** para previsão com base no trabalho em andamento (WIP) e selecione o tipo de WIP.</span><span class="sxs-lookup"><span data-stu-id="2a668-122">Enable **Forecast with WIP** to forecast based on work in progress (WIP), and then select the type of WIP.</span></span> 
   - <span data-ttu-id="2a668-123">Você pode manter o **Tipo de orçamento** padrão como **Nenhum** ou inserir um novo tipo.</span><span class="sxs-lookup"><span data-stu-id="2a668-123">You can keep the default **Budget type** as **None** or enter a new type.</span></span> <span data-ttu-id="2a668-124">O tipo de orçamento não pode ser alterado depois que um registro é alterado.</span><span class="sxs-lookup"><span data-stu-id="2a668-124">The budget type can't be changed after you change a record.</span></span>     
    > [!NOTE]
    > <span data-ttu-id="2a668-125">Se você alterar o tipo de orçamento padrão, todas as outras opções se tornarão indisponíveis para atualizações e não será possível reutilizar esse modelo de previsão.</span><span class="sxs-lookup"><span data-stu-id="2a668-125">If you change the default budget type, all other options will become unavailable for updates, and you can't reuse this forecast model.</span></span> 
   


 

