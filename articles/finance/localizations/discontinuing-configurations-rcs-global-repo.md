---
title: Descontinuar configurações no repositório Global do RCS
description: Este tópico descreve como descontinuar as configurações no repositório global RCS.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 25ad0744e7c3320505c13c465d440b6a364da47c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840283"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a><span data-ttu-id="5c804-103">Descontinuar configurações no repositório Global do RCS</span><span class="sxs-lookup"><span data-stu-id="5c804-103">Discontinue configurations in the RCS Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5c804-104">Este tópico descreve como descontinuar a configuração no repositório global RCS.</span><span class="sxs-lookup"><span data-stu-id="5c804-104">This topic describes how to discontinue configuration in the RCS Global repository.</span></span> <span data-ttu-id="5c804-105">Anteriormente, só foi possível excluir as configurações que não eram mais necessárias.</span><span class="sxs-lookup"><span data-stu-id="5c804-105">Previously, it was possible only to delete configurations that were no longer required.</span></span> <span data-ttu-id="5c804-106">No entanto, agora você pode marcar uma configuração liberada como **Descontinuada** no repositório Global do RCS.</span><span class="sxs-lookup"><span data-stu-id="5c804-106">However now you can mark a released configuration as **Discontinued** in the RCS Global repository.</span></span> <span data-ttu-id="5c804-107">Com essa funcionalidade, você também pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="5c804-107">With this functionality, you can also do the following:</span></span> 
 
 - <span data-ttu-id="5c804-108">Fornecer notificações antecipadas quando uma configuração for planejada para ser descontinuada.</span><span class="sxs-lookup"><span data-stu-id="5c804-108">Provide up front notifications when a configuration is planned to be discontinued.</span></span>
 - <span data-ttu-id="5c804-109">Inclua detalhes aplicáveis sobre a configuração de substituição.</span><span class="sxs-lookup"><span data-stu-id="5c804-109">Include applicable details about the replacement configuration.</span></span>
 - <span data-ttu-id="5c804-110">Defina uma data **Com suporte até** para a configuração específica para informar ao usuário quando ele será descontinuado.</span><span class="sxs-lookup"><span data-stu-id="5c804-110">Set a **Supported until** date for the specific configuration to inform the user when it will be discontinued.</span></span>

<span data-ttu-id="5c804-111">Ao interromper uma versão de configuração, você poderá especificar as seguintes informações opcionais:</span><span class="sxs-lookup"><span data-stu-id="5c804-111">When you discontinue a configuration version, you can specify the following optional information:</span></span>

  - <span data-ttu-id="5c804-112">**Configuração de substituição**</span><span class="sxs-lookup"><span data-stu-id="5c804-112">**Replacement configuration**</span></span>
  - <span data-ttu-id="5c804-113">**Versão de configuração de substituição**</span><span class="sxs-lookup"><span data-stu-id="5c804-113">**Replacement configuration version**</span></span>
  - <span data-ttu-id="5c804-114">**Nota de texto livre**: use esse campo para fornecer links ou referências de documentação</span><span class="sxs-lookup"><span data-stu-id="5c804-114">**Free text note**: Use this field to provide documentation links or references</span></span>
  - <span data-ttu-id="5c804-115">**Com suporte até**: esse campo fornece a data proposta até quando a configuração/versão atual terá suporte.</span><span class="sxs-lookup"><span data-stu-id="5c804-115">**Supported until**: This field provides the proposed date up to which the current configuration/version will be supported.</span></span> <span data-ttu-id="5c804-116">Essa data deve ser atualizada manualmente.</span><span class="sxs-lookup"><span data-stu-id="5c804-116">This date must be updated manually.</span></span>
  
<span data-ttu-id="5c804-117">Para descontinuar a configuração, conclua as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="5c804-117">To discontinue the configuration, complete the following steps.</span></span> 

1. <span data-ttu-id="5c804-118">Selecione se deseja descontinuar uma única versão ou todas as versões com as mesmas configurações em uma operação definindo **Todas as versões** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5c804-118">Select whether you want to discontinue a single version or all versions with the same settings in one operation by setting **All versions** to **Yes**.</span></span> 
2. <span data-ttu-id="5c804-119">Defina o parâmetro **Descontinuar** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5c804-119">Set the **Discontinue** parameter to **Yes**.</span></span>
3. <span data-ttu-id="5c804-120">Selecione **OK** para descontinuar as configurações.</span><span class="sxs-lookup"><span data-stu-id="5c804-120">Select **OK** to discontinue the configurations.</span></span> <span data-ttu-id="5c804-121">O campo **Data da descontinuação** será preenchido quando você salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="5c804-121">The **Discontinued date** field will be populated when you save the changes.</span></span>

![Descontinuar informações de configuração](media/Discontinue-details-2.png)
  
<span data-ttu-id="5c804-123">Você pode reverter a configuração para **Compartilhada** ou ajustar as informações de descontinuação a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="5c804-123">You can revert configuration back to **Shared** or adjust discontinuation information at any time.</span></span> <span data-ttu-id="5c804-124">Se você compartilhar uma configuração, especifique a data **Com suporte até** e todas as outras informações relacionadas à descontinuação para indicar seus planos para uma descontinuação futura.</span><span class="sxs-lookup"><span data-stu-id="5c804-124">If you share a configuration, specify the **Supported until** date and all other information related to the discontinuation to indicate your plans for future discontinuation.</span></span>

<span data-ttu-id="5c804-125">Se desejar compartilhar informações sobre uma descontinuação planejada, antes de realmente interromper a configuração, o usuário poderá preencher todos os campos relacionados à substituição, mas deixar o parâmetro **Descontinuar** definido como **Não**.</span><span class="sxs-lookup"><span data-stu-id="5c804-125">If you want to share information about a planned discontinuation, prior to actually discontinuing the configuration, user is able to prefill all fields related to replacement but leave the **Discontinue** parameter set to **No**.</span></span>

> [!NOTE]
> <span data-ttu-id="5c804-126">A descontinuação não limita as operações com configurações.</span><span class="sxs-lookup"><span data-stu-id="5c804-126">Discontinuation doesn't limit operations with configurations.</span></span> <span data-ttu-id="5c804-127">Você pode continuar a importar, executar ou derivar as configurações, esses campos são informativos.</span><span class="sxs-lookup"><span data-stu-id="5c804-127">You can continue to import, run, or derive the configurations, these fields are informational.</span></span>

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a><span data-ttu-id="5c804-128">O Finance dá suporte à exibição dessas informações desde a versão 10.0.14</span><span class="sxs-lookup"><span data-stu-id="5c804-128">Finance supports displaying this information starting in version 10.0.14</span></span>

<span data-ttu-id="5c804-129">A partir da versão 10.0.14, o Dynamics 365 Finance dá suporte à exibição de informações de descontinuação.</span><span class="sxs-lookup"><span data-stu-id="5c804-129">Starting in version 10.0.14, Dynamics 365 Finance supports displaying discontinuation information.</span></span> <span data-ttu-id="5c804-130">Na página **Repositório global**, você pode exibir informações atualizadas relacionadas à descontinuação.</span><span class="sxs-lookup"><span data-stu-id="5c804-130">On the **Global repository** page, you can view up to date information related to discontinuation.</span></span> <span data-ttu-id="5c804-131">Por padrão, as configurações descontinuadas são filtradas.</span><span class="sxs-lookup"><span data-stu-id="5c804-131">By default, configurations that are discontinued are filtered out.</span></span>
  
<span data-ttu-id="5c804-132">A página **Configurações importadas** (ERSolutionTable) mostra configurações que já foram descontinuadas quando foram importadas.</span><span class="sxs-lookup"><span data-stu-id="5c804-132">The **Imported configurations** (ERSolutionTable) page, shows configurations that were already discontinued when there were imported.</span></span> <span data-ttu-id="5c804-133">Para as configurações que foram interrompidas após a importação, as informações de descontinuação podem ser sincronizadas executando o trabalho **Importar atualizações de configurações**.</span><span class="sxs-lookup"><span data-stu-id="5c804-133">For those configurations that were discontinued after import, the discontinuation information can be synchronized by running the **Import configurations updates** job.</span></span>


