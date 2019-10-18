---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (16 de outubro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 13e89faa3f8470125010ccdb40a6f01c0a9c4fe7
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008768"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-october-19-2018"></a><span data-ttu-id="e6cf7-103">Novidades ou alterações no Dynamics 365 Talent: Core HR (19 de outubro de 2018)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-103">What's new or changed in Dynamics 365 Talent: Core HR (October 19, 2018)</span></span>

[!include[banner](includes/banner.md)]

<span data-ttu-id="e6cf7-104">**Compilação 8.1.1067**</span><span class="sxs-lookup"><span data-stu-id="e6cf7-104">**Build 8.1.1067**</span></span>

<span data-ttu-id="e6cf7-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-managers-to-update-time-off-requests"></a><span data-ttu-id="e6cf7-106">Permite que os gerentes atualizem tempo das solicitações</span><span class="sxs-lookup"><span data-stu-id="e6cf7-106">Allow managers to update time off requests</span></span>

<span data-ttu-id="e6cf7-107">As solicitações de licença dos funcionários precisam ser atualizadas após aprovação por meio do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-107">Employee time off requests may need to be updated after they are approved through the workflow.</span></span> <span data-ttu-id="e6cf7-108">Em muitos casos, o gerente faz essas atualizações em nome do funcionário.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-108">In many cases, the manager makes these updates on the employee’s behalf.</span></span> <span data-ttu-id="e6cf7-109">Este novo recurso fornece a capacidade dos gerentes atualizar o tempo ausente ou cancelar as solicitações de licença em nome de seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-109">This new feature provides the ability for managers to update time off or cancel time off requests on behalf of their employees.</span></span> <span data-ttu-id="e6cf7-110">Este recurso é controlado pelo parâmetro **Trabalho em nome** que pode ser definido na página **Parâmetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-110">This capability is controlled by the **Work on behalf** parameter that can be set on the **Human Resource Parameters** page.</span></span> 
 
## <a name="allow-hr-to-update-time-off-requests"></a><span data-ttu-id="e6cf7-111">Permite que o RH atualize as solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="e6cf7-111">Allow HR to update time off requests</span></span>

<span data-ttu-id="e6cf7-112">Semelhante ao recurso acima, as solicitações de licença do funcionário precisam ser atualizadas pelo RH após terem sido aprovadas anteriormente por meio do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-112">Similar to the feature above, employee time off requests may need to be updated by HR after they have been previously approved through the workflow.</span></span> <span data-ttu-id="e6cf7-113">Este recurso fornece a capacidade para usuários de RH de atualizar as solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-113">This feature provides the ability for HR users to update time off requests.</span></span> <span data-ttu-id="e6cf7-114">A funcionalidade está habilidade no fluxo de trabalho **Pessoas** e na página **Trabalhador**, usando uma nova opção chamada **Exibir tempo fora**.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-114">The capability is enabled in the **People** workspace and on the **Worker** page, using a new option called **View time off**.</span></span> <span data-ttu-id="e6cf7-115">Nessas páginas, os usuários do RH podem ver as solicitações e atualizar as transações de tempo de licença, semelhante a como os gerentes podem realizar essas ações.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-115">On those pages, HR users can view requests and update time off transactions, similar to how managers can perform these actions.</span></span>

<span data-ttu-id="e6cf7-116">A obrigação de segurança que controla acesso a essa funcionalidade é:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-116">The security duty that controls access to this functionality is:</span></span>
- <span data-ttu-id="e6cf7-117">Obrigação: Manter processos de licença e ausência específicos ao trabalhador.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-117">Duty: Maintain worker-specific leave and absence processes.</span></span>
- <span data-ttu-id="e6cf7-118">Privilégio: Manter solicitações de licença e ausência para todos os trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-118">Privilege: Maintain leave and absence requests for all workers.</span></span>

## <a name="other-changes"></a><span data-ttu-id="e6cf7-119">Outras alterações</span><span class="sxs-lookup"><span data-stu-id="e6cf7-119">Other changes</span></span>
<span data-ttu-id="e6cf7-120">As atualizações a seguir foram feitas nesta versão:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-120">The following updates have been made in this release:</span></span>
- <span data-ttu-id="e6cf7-121">Alterações a ações de contratação de trabalhador para que eles não fiquem mais "presos" no estado **Fluxo de trabalho completo**.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-121">Changes to worker hire actions so that they are no longer "stuck" in **Workflow complete** state.</span></span>
- <span data-ttu-id="e6cf7-122">O registro de emprego agora pode ser criado sem uma data de início do trabalho.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-122">Employment record can now be created without an employment start date.</span></span>
- <span data-ttu-id="e6cf7-123">Agora, a data de registro do Dynamics 365 Talent para um curso exibido no autoatendimento do funcionário aplica o deslocamento de fuso horário à data.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-123">The Dynamics 365 Talent registration date for a course shown in Employee self-service now applies the time zone offset to the date.</span></span>
- <span data-ttu-id="e6cf7-124">Os arquivos excel podem ser importados várias vezes sem quaisquer erros usando **Entidade do funcionário**.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-124">Excel files can be imported multiple times without any errors using **Employee Entity**.</span></span>

## <a name="known-issue"></a><span data-ttu-id="e6cf7-125">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="e6cf7-125">Known issue</span></span>

- <span data-ttu-id="e6cf7-126">**Erro**: Ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-126">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="e6cf7-127">**Solução alternativa:** Antes de abrir a página do anexo, garante que os caixas de dados na página **Trabalhador** estejam fechadas.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-127">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="e6cf7-128">Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões Anexos serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-128">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="e6cf7-129">(Esse problema será corrigido na próxima atualização de plataforma.)</span><span class="sxs-lookup"><span data-stu-id="e6cf7-129">(This issue will be fixed in the next platform update.)</span></span>
