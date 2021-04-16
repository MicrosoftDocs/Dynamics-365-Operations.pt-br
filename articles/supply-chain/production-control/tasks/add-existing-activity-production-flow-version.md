---
title: Adicionar uma atividade existente a uma versão de fluxo de produção
description: Ao criar novas versões de fluxos de produção, você pode escolher adicionar atividades criadas para as versões anteriores à nova versão.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2fd6fe4ad25bde26a4212e236c9298a7ab832b66
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825101"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a><span data-ttu-id="12c07-103">Adicionar uma atividade existente a uma versão de fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="12c07-103">Add an existing activity to a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="12c07-104">Ao criar novas versões de fluxos de produção, você pode escolher adicionar atividades criadas para as versões anteriores à nova versão.</span><span class="sxs-lookup"><span data-stu-id="12c07-104">When creating new versions of production flows, you can choose to add activities created for the older versions, to the new version.</span></span> <span data-ttu-id="12c07-105">Este procedimento mostra como uma nova versão é criada para um fluxo de produção existente, sem copiar as atividades.</span><span class="sxs-lookup"><span data-stu-id="12c07-105">This procedure shows how a new version is created for an existing production flow, without copying the activities.</span></span> <span data-ttu-id="12c07-106">Na próxima etapa, uma atividade existente será adicionada à nova versão.</span><span class="sxs-lookup"><span data-stu-id="12c07-106">In the next step, an existing activity is added to the new version.</span></span> 

<span data-ttu-id="12c07-107">Esta tarefa requer o fluxo de produção com a versão e as atividades já criadas.</span><span class="sxs-lookup"><span data-stu-id="12c07-107">This task requires production flow with version and activities already created.</span></span>


## <a name="create-a-new-production-flow-version"></a><span data-ttu-id="12c07-108">Criar uma nova versão de fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="12c07-108">Create a new production flow version</span></span>
1. <span data-ttu-id="12c07-109">Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="12c07-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="12c07-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="12c07-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="12c07-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="12c07-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="12c07-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="12c07-112">Click Edit.</span></span>
5. <span data-ttu-id="12c07-113">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="12c07-113">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="12c07-114">No campo Data de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="12c07-114">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="12c07-115">Observe que antes de você criar uma nova versão do fluxo de produção, certifique-se de verificar a data e hora de vencimento da versão ativa.</span><span class="sxs-lookup"><span data-stu-id="12c07-115">Note that before you create a new production flow version, make sure to check the expiration date and time of the active version.</span></span> <span data-ttu-id="12c07-116">A nova versão será criada com uma data de início efetiva, conectada à data de vencimento da versão selecionada.</span><span class="sxs-lookup"><span data-stu-id="12c07-116">The new version will be created with an effective start date, which connects to the expiry date of the selected version.</span></span>  
7. <span data-ttu-id="12c07-117">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="12c07-117">Click Add.</span></span>
8. <span data-ttu-id="12c07-118">Selecione Não no campo Copiar da versão.</span><span class="sxs-lookup"><span data-stu-id="12c07-118">Select No in the Copy from version field.</span></span>
    * <span data-ttu-id="12c07-119">Selecione Não para iniciar com uma versão vazia se a maioria das atividades da versão copiada for substituída por novas atividades.</span><span class="sxs-lookup"><span data-stu-id="12c07-119">Select No to start with an empty version if most of the activities of the copied version will be replaced by new activities.</span></span> <span data-ttu-id="12c07-120">Adicione manualmente as atividades inalteradas à função Adicionar existente no formulário da atividade.</span><span class="sxs-lookup"><span data-stu-id="12c07-120">Add the unchanged activities to the Add existing function in the activity form manually.</span></span>  
9. <span data-ttu-id="12c07-121">Selecione Não no campo Duplicar regras kanban.</span><span class="sxs-lookup"><span data-stu-id="12c07-121">Select No in the Duplicate kanban rules field.</span></span>
    * <span data-ttu-id="12c07-122">Quando as atividades não são copiadas na nova versão, não é possível copiar as regras kanban no momento da criação da nova versão.</span><span class="sxs-lookup"><span data-stu-id="12c07-122">When the activities are not copied to the new version, it is not possible to copy the kanban rules at the time of creation of the new version.</span></span>   <span data-ttu-id="12c07-123">Em vez disso, você usará a função Criar kanban de substituição posteriormente no formulário da regra kanban para substituir as regras kanban da versão antiga do fluxo de produção com regras kanban usando as atividades da nova versão.</span><span class="sxs-lookup"><span data-stu-id="12c07-123">Instead you will use the create replacement kanban function later in the kanban rule form, to replace kanban rules of the old production flow version with kanban rules using the activities of the new version.</span></span>  
10. <span data-ttu-id="12c07-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="12c07-124">Click OK.</span></span>
11. <span data-ttu-id="12c07-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="12c07-125">In the list, find and select the desired record.</span></span>

## <a name="add-an-existing-activity"></a><span data-ttu-id="12c07-126">Adicionar uma atividade existente</span><span class="sxs-lookup"><span data-stu-id="12c07-126">Add an existing activity</span></span>
1. <span data-ttu-id="12c07-127">Clique em Atividades.</span><span class="sxs-lookup"><span data-stu-id="12c07-127">Click Activities.</span></span>
2. <span data-ttu-id="12c07-128">Clique em Adicionar existente para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="12c07-128">Click Add existing to open the drop dialog.</span></span>
    * <span data-ttu-id="12c07-129">Localizar e selecionar uma atividade existente que será adicionada à nova versão do fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="12c07-129">Find and select an existing activity to be added to the new production flow version.</span></span>  <span data-ttu-id="12c07-130">Observe que a lista mostra todas as atividades criadas para este fluxo de produção para todas as versões anteriores do fluxo.</span><span class="sxs-lookup"><span data-stu-id="12c07-130">Note that the list shows all activities that have been created for this production flow for all previous versions of the flow.</span></span>  
3. <span data-ttu-id="12c07-131">No campo Atividade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="12c07-131">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="12c07-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="12c07-132">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]