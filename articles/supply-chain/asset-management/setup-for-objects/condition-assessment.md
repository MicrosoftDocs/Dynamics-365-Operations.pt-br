---
title: Avaliação de condição
description: Este tópico explica como criar um modelo de avaliação de condição e um registro em um ativo no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5294325f67f0484b39194b5bd9784a2e612001a4
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783060"
---
# <a name="condition-assessment"></a><span data-ttu-id="5fbb6-103">Avaliação de condição</span><span class="sxs-lookup"><span data-stu-id="5fbb6-103">Condition assessment</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="5fbb6-104">Este tópico explica como criar um modelo de avaliação de condição e um registro em um ativo no Gerenciamento de Ativos.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-104">This topic explains how to create a condition assessment template and registration on an asset in Asset Management.</span></span> <span data-ttu-id="5fbb6-105">A avaliação da condição é executada em intervalos regulares e a finalidade principal é criar e manter dados de condição em ativos.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-105">Condition assessment is performed at regular intervals, and the primary objective is to create and maintain condition data on assets.</span></span> <span data-ttu-id="5fbb6-106">Sob uma perspectiva de manutenção preventiva, é importante monitorar informações como a condição atual e o tempo de vida útil restante.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-106">Seen from a preventive maintenance perspective, it is important to monitor key information such as current condition, and remaining life span.</span></span> <span data-ttu-id="5fbb6-107">Além disso, se você realizar a avaliação da condição em intervalos regulares, poderá monitorar e comparar condições nas máquinas da sua fábrica.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-107">Furthermore, if you carry out condition assessment at regular intervals, you will be able to monitor and compare conditions on the machinery in your factory.</span></span>

<span data-ttu-id="5fbb6-108">A avaliação da condição pode ser usada para medir e monitorar muitas condições no seu equipamento.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-108">Condition assessment can be used to measure and monitor many conditions on your equipment.</span></span> <span data-ttu-id="5fbb6-109">Exemplo: você pode medir vibrações em suas máquinas.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-109">Example: You could measure vibrations on your machinery.</span></span> <span data-ttu-id="5fbb6-110">Após registrar medidas de vibração em Gerenciamento de Ativos em vários tipos de equipamento, você poderá procurar a avaliação recém-registrada e exibir medidas de vibração.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-110">After you have registered vibration measurements in Asset Management on various types of equipment, you can search for the latest registered assessment and view vibration measurements.</span></span>

<span data-ttu-id="5fbb6-111">A avaliação da condição é criada em ativos.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-111">Condition assessment is created on assets.</span></span> <span data-ttu-id="5fbb6-112">Você configura um modelo de avaliação de condição em um tipo de ativo antes de executar o procedimento de avaliação de condição.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-112">You set up a condition assessment template on an asset type before you carry out the condition assessment procedure.</span></span> <span data-ttu-id="5fbb6-113">O motivo para usar modelos para a avaliação de condição é evitar a variação de dados de condição em ativos semelhantes.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-113">The reason for using templates for condition assessment is to avoid variation of condition data on similar assets.</span></span> <span data-ttu-id="5fbb6-114">A sequência para configurar e usar a avaliação da condição em Gerenciamento de Ativos é: primeiro, configure os métodos de avaliação de condições.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-114">The sequence for setting up and using condition assessment in Asset Management is: First you set up the required condition assessment templates.</span></span> <span data-ttu-id="5fbb6-115">Em seguida, você associa modelos com tipos de ativo no formulário **Tipos de ativo**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-115">Next, you associate templates with asset types in the **Asset types** form.</span></span> <span data-ttu-id="5fbb6-116">Finalmente, você pode criar registros de avaliação de condição em um ativo no formulário **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-116">Finally, you can create condition assessment registrations on an asset in the **Asset** form.</span></span>

## <a name="create-a-condition-assessment-template"></a><span data-ttu-id="5fbb6-117">Crie um modelo de avaliação de condição</span><span class="sxs-lookup"><span data-stu-id="5fbb6-117">Create a condition assessment template</span></span>

1. <span data-ttu-id="5fbb6-118">Selecione **Gerenciamento de ativos** > **Configuração** > **Tipos de ativo** > **Avaliação de condição**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-118">Select **Asset management** > **Setup** > **Asset types** > **Condition assessment**.</span></span>
2. <span data-ttu-id="5fbb6-119">Selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-119">Select **New** to create a new template.</span></span>
3. <span data-ttu-id="5fbb6-120">Insira uma ID para o modelo no campo **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-120">Insert and ID for the template in the **Template** field.</span></span>
4. <span data-ttu-id="5fbb6-121">Insira um nome para o modelo no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-121">Insert a name for the template in the **Name** field.</span></span>
5. <span data-ttu-id="5fbb6-122">Na Guia Rápida **Linhas de avaliação de condição**, adicione linhas necessárias para a avaliação da condição, incluindo a seleção do tipo de condição apropriado e da unidade de medida.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-122">On the **Condition assessment lines** FastFab, add the lines required for the condition assessment, including selection of the appropriate condition type and measurement unit.</span></span>
6. <span data-ttu-id="5fbb6-123">Na Guia Rápida **Tipos de ativo**, adicione os tipos de ativo que devem utilizar o modelo de avaliação de condição.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-123">On the **Asset types** FastTab, add the asset types that should use the condition assessment template.</span></span>
7. <span data-ttu-id="5fbb6-124">Nos campos **Linhas** e **Tipos de ativo** no grupo **Detalhes** na parte superior da tela, você verá o número de linhas de avaliação e tipos de ativo relacionados ao modelo de avaliação de condição selecionado.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-124">In the **Lines** and **Asset types** fields in the **Details** group at the top of the screen, you will see the number of assessment lines and asset types related to the selected condition assessment template.</span></span>


## <a name="create-condition-assessment-registration-on-an-asset"></a><span data-ttu-id="5fbb6-125">Crie o registro de avaliação de condição em um ativo</span><span class="sxs-lookup"><span data-stu-id="5fbb6-125">Create condition assessment registration on an asset</span></span>

1. <span data-ttu-id="5fbb6-126">Selecione **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os Ativos**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-126">Select **Asset management** > **Common** > **Assets** > **All Assets**.</span></span>
2. <span data-ttu-id="5fbb6-127">Na lista, selecione o ativo para o qual deseja criar um registro de avaliação de condição.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-127">In the list, select the asset for which you want to create a condition assessment registration.</span></span>
3. <span data-ttu-id="5fbb6-128">Na guia **Geral**, clique em **Avaliação de condição**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-128">On the **General** tab, click **Condition assessment**.</span></span>
4. <span data-ttu-id="5fbb6-129">Clique em **Novo** para criar um novo registro.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-129">Click **New** to make a new registration.</span></span>
5. <span data-ttu-id="5fbb6-130">Selecione a data para a avaliação de condição no campo **Data**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-130">Select the date for the condition assessment in the **Date** field.</span></span>
6. <span data-ttu-id="5fbb6-131">Selecione o nome do trabalhador que realizou o registro de avaliação no campo **Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-131">Select the name of the worker who carried out the assessment registration in the **Worker** field.</span></span>
7. <span data-ttu-id="5fbb6-132">No campo **Linhas**, você verá o número de linhas de avaliação definidas na avaliação de condição.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-132">In the **Lines** field, you see the number of assessment lines set up on the condition assessment.</span></span>
8. <span data-ttu-id="5fbb6-133">Selecione um modelo para a avaliação de condição no campo **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-133">Select a template for the condition assessment in the **Template** field.</span></span> <span data-ttu-id="5fbb6-134">O nome do modelo é inserido automaticamente no campo **Nome**; as linhas de registro relacionadas são inseridas na Guia Rápida **Linhas de avaliação de condição**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-134">The name of the template is automatically inserted in the **Name** field, and the related registration lines are inserted on the **Condition assessment lines** FastTab.</span></span>
9. <span data-ttu-id="5fbb6-135">Você pode inserir notas em relação à avaliação de condição selecionada na Guia Rápida **Notas**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-135">You can insert notes relating to the selected condition assessment on the **Notes** FastTab.</span></span>
10. <span data-ttu-id="5fbb6-136">Para cada linha de avaliação de condição, insira dados de medida no campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-136">For each condition assessment line, insert measurement data in the **Value** field.</span></span>
11. <span data-ttu-id="5fbb6-137">Você pode inserir um comentário sobre a linha de registro selecionada na Guia Rápida **Linhas de avaliação de condição** > campo **Comentários**.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-137">You can insert a comment relating to the selected registration line on the **Condition assessment lines** FastTab > **Comments** field.</span></span> <span data-ttu-id="5fbb6-138">Se você adicionar um comentário em uma linha, a caixa de seleção **Comentário** será marcada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-138">If you add a comment on a line, the **Comment** check box is automatically selected.</span></span>

<span data-ttu-id="5fbb6-139">Após fazer um registro de avaliação de condição em um ativo, você poderá imprimir um relatório de avaliação de condição.</span><span class="sxs-lookup"><span data-stu-id="5fbb6-139">After you have made a condition assessment registration on an asset, you can print a condition assessment report.</span></span>

>[!NOTE]
><span data-ttu-id="5fbb6-140">Você também pode registrar a avaliação de condição em uma ordem de serviço (botão**Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** > **Avaliação de condição**.)</span><span class="sxs-lookup"><span data-stu-id="5fbb6-140">You can also register condition assessment on a work order (**Asset management** > **Common** > **Work orders** > **All Work orders** > **Condition assessment** button.)</span></span>
