---
title: Eliminar uma estimativa de projeto
description: Este tópico fornece informações sobre como eliminar uma estimativa de projeto após sua conclusão.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
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
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410190"
---
# <a name="eliminate-a-project-estimate"></a><span data-ttu-id="59412-103">Eliminar uma estimativa de projeto</span><span class="sxs-lookup"><span data-stu-id="59412-103">Eliminate a project estimate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59412-104">As estimativas de projeto fornecem a exibição financeira do trabalho que é previsto e programado para um projeto.</span><span class="sxs-lookup"><span data-stu-id="59412-104">Project estimates provide the financial view for work that is estimated and scheduled for a project.</span></span> <span data-ttu-id="59412-105">Para trabalhar com estimativas de um projeto, você deve anexar o projeto a um projeto previsto.</span><span class="sxs-lookup"><span data-stu-id="59412-105">To work with estimates for a project, you must attach the project to an estimate project.</span></span> <span data-ttu-id="59412-106">Um projeto previsto sempre se baseia em um projeto existente, mas vários projetos podem referenciar um único projeto previsto.</span><span class="sxs-lookup"><span data-stu-id="59412-106">An estimate project is always based on an existing project, however multiple projects can refer to a single estimate project.</span></span> <span data-ttu-id="59412-107">Somente os projetos de preço fixo e de investimento podem ser anexados a projetos previstos; esses projetos devem pertencer ao mesmo grupo de projetos que o projeto previsto.</span><span class="sxs-lookup"><span data-stu-id="59412-107">Only fixed-price and investment projects can be attached to estimate projects, and those projects must belong to the same project group as the estimate project.</span></span>

<span data-ttu-id="59412-108">Para eliminar um projeto previsto, ele precisa estar concluído.</span><span class="sxs-lookup"><span data-stu-id="59412-108">To eliminate an estimate project, it must be complete.</span></span> <span data-ttu-id="59412-109">As etapas a seguir explicam como eliminar uma previsão.</span><span class="sxs-lookup"><span data-stu-id="59412-109">The following steps explain how to eliminate an estimate.</span></span>

1. <span data-ttu-id="59412-110">Vá para **Gerenciamento e contabilidade de projeto** > **Todos os projetos** e abra o projeto.</span><span class="sxs-lookup"><span data-stu-id="59412-110">Go to **Project management and accounting** > **All Projects** and open the project.</span></span> 
2. <span data-ttu-id="59412-111">Na guia **Gerenciar**, selecione **Previsões**. Na página **Previsão** selecione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="59412-111">On the **Manage** tab, select **Estimates**, and on the **Estimate** page select **Eliminate**.</span></span>
3. <span data-ttu-id="59412-112">Na página **Eliminar estimativa** na guia **Geral**, defina as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="59412-112">On the **Eliminate estimate** page on the **General** tab, set the following options:</span></span>

   - <span data-ttu-id="59412-113">**Código de período**: selecione o código de período para escolher os projetos de previsão adequados.</span><span class="sxs-lookup"><span data-stu-id="59412-113">**Period code**: Select the period code to choose the appropriate estimate projects.</span></span> 
   - <span data-ttu-id="59412-114">**Data prevista**: selecione a data prevista adequada para eliminação.</span><span class="sxs-lookup"><span data-stu-id="59412-114">**Estimate date**: Select the appropriate estimate date for elimination.</span></span>
   - <span data-ttu-id="59412-115">**Eliminar com avisos WIP**: habilite esta opção para fornecer notificação quando uma previsão associada a um trabalho em andamento (WIP) for eliminada.</span><span class="sxs-lookup"><span data-stu-id="59412-115">**Eliminate with WIP warnings**: Enable this option to provide notification when an estimate that is associated with a work in progress (WIP) will be eliminated.</span></span> <span data-ttu-id="59412-116">Quando esta opção estiver desabilitada, a eliminação não poderá continuar se existir uma transação não prevista.</span><span class="sxs-lookup"><span data-stu-id="59412-116">When this option is not enabled, elimination can’t continue if any non-estimated transactions exist.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="59412-117">Esse opção só ficará disponível quando a eliminação for aplicada a um projeto previsto.</span><span class="sxs-lookup"><span data-stu-id="59412-117">This option is available only when elimination is applied to an estimate project.</span></span> <span data-ttu-id="59412-118">Ela não estará disponível se você estiver usando lançamentos periódicos.</span><span class="sxs-lookup"><span data-stu-id="59412-118">It is not available if you are using periodic postings.</span></span> <span data-ttu-id="59412-119">Esta configuração funciona com as configurações na guia **Previsão** na página **Parâmetros do projeto**, no grupo de campos **Permitir eliminação quando houver transações não previstas**.</span><span class="sxs-lookup"><span data-stu-id="59412-119">This setting works with the settings on the **Estimate** tab on the **Project parameters** page, in the **Allow elimination when non-estimated transactions exist** field group.</span></span>
   - <span data-ttu-id="59412-120">**Definir estágio como Concluído**: habilite esta opção para definir a fase do projeto previsto como **Concluída** após executar a eliminação.</span><span class="sxs-lookup"><span data-stu-id="59412-120">**Set stage to Finished**: Enable this option to set the estimate project’s stage to **Finished** after you run the elimination.</span></span>
   - <span data-ttu-id="59412-121">**Imprimir lista prevista**: selecione as informações a serem incluídas quando a lista prevista for impressa.</span><span class="sxs-lookup"><span data-stu-id="59412-121">**Print estimate list**: Select the information to be included when the estimate list is printed.</span></span>
   - <span data-ttu-id="59412-122">**Mostrar log de informações**: habilite esta opção para exibir o log de informações.</span><span class="sxs-lookup"><span data-stu-id="59412-122">**Show Infolog**: Enable this option to display the Infolog.</span></span>
   - <span data-ttu-id="59412-123">**Data de lançamento**: escolha a data de lançamento do razão da previsão.</span><span class="sxs-lookup"><span data-stu-id="59412-123">**Posting date**: Choose the ledger posting date of the estimate.</span></span>

4.  <span data-ttu-id="59412-124">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="59412-124">Select **OK**.</span></span>
5. <span data-ttu-id="59412-125">Depois que o processo de eliminação for concluído, o projeto previsto eliminado será exibido com um valor negativo.</span><span class="sxs-lookup"><span data-stu-id="59412-125">After the elimination process is complete, the eliminated estimate project is displayed with a negative value.</span></span> 

<span data-ttu-id="59412-126">Se você não pretende eliminar uma previsão, poderá selecionar a previsão eliminada e selecionar **Reverter eliminação**.</span><span class="sxs-lookup"><span data-stu-id="59412-126">If you did not intend to eliminate an estimate, you can select the eliminated estimate and select **Reverse elimination**.</span></span>   
