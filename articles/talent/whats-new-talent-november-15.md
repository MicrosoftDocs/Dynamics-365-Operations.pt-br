---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (15 de novembro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
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
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b90d4230fe1e666aba4075670f6df206e8df7ce9
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "857301"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a><span data-ttu-id="73c57-103">Novidades ou alterações no Dynamics 365 for Talent Core HR (15 de novembro de 2018)</span><span class="sxs-lookup"><span data-stu-id="73c57-103">What's new or changed in Dynamics 365 for Talent Core HR (November 15, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="73c57-104">**Compilação 8.1.2045**</span><span class="sxs-lookup"><span data-stu-id="73c57-104">**Build 8.1.2045**</span></span>

<span data-ttu-id="73c57-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="73c57-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="other-changesfixes"></a><span data-ttu-id="73c57-106">Outras alterações/correções</span><span class="sxs-lookup"><span data-stu-id="73c57-106">Other changes/fixes</span></span>

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a><span data-ttu-id="73c57-107">Incapaz de alterar o cargo atual do funcionário para uma posição aberta futura</span><span class="sxs-lookup"><span data-stu-id="73c57-107">Unable to change employee´s current position to a future open position</span></span>

<span data-ttu-id="73c57-108">Uma alteração foi feita para permitir transferências de posição quando a posição só está disponível no futuro.</span><span class="sxs-lookup"><span data-stu-id="73c57-108">A change has been made to enable position transfers when the position is only available in the future.</span></span> 

### <a name="position-does-not-display-when-creating-a-new-employee"></a><span data-ttu-id="73c57-109">A posição não é exibida ao criar um novo funcionário</span><span class="sxs-lookup"><span data-stu-id="73c57-109">Position does not display when creating a new employee</span></span>

<span data-ttu-id="73c57-110">Uma alteração foi feita para exibir todas as posições abertas disponíveis para a atribuição ao contratar funcionários novos. em Talent.</span><span class="sxs-lookup"><span data-stu-id="73c57-110">A change has been made to display all open positions that are available for assignment when hiring new employees in Talent.</span></span> <span data-ttu-id="73c57-111">Isso inclui posições históricas ou se as posições foram datadas no futuro.</span><span class="sxs-lookup"><span data-stu-id="73c57-111">This includes historical positions or if the postitions have been future dated.</span></span> <span data-ttu-id="73c57-112">As posições agora aparecerão corretamente com base na data de início do emprego.</span><span class="sxs-lookup"><span data-stu-id="73c57-112">Positions will now appear correctly based on the employment start date.</span></span> 

### <a name="termination-date-is-displaying-based-on-user-settings"></a><span data-ttu-id="73c57-113">A data de demissão é exibida com base nas configurações do usuário</span><span class="sxs-lookup"><span data-stu-id="73c57-113">Termination date is displaying based on user settings</span></span>

<span data-ttu-id="73c57-114">Uma alteração foi feita à lista de funcionários passados para conta para quaisquer compensações de fuso horário para o fuso horário preferido ao exibir a data de demissão.</span><span class="sxs-lookup"><span data-stu-id="73c57-114">A change has been made to the past employees list to account for any time zone offsets for the employees preferred time zone when viewing the termination date.</span></span>

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a><span data-ttu-id="73c57-115">Itens de trabalho atribuídos a mim, links não exibidos com as informações corretas</span><span class="sxs-lookup"><span data-stu-id="73c57-115">Work items assigned to me links not displaying the correct information</span></span>

<span data-ttu-id="73c57-116">Com essa alteração, navegação aos detalhes dos itens de trabalho individual na lista exibirão as informações corretas para o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="73c57-116">With this change, navigation to the details of the individual work items in the list will display the correct information for the item selected.</span></span> <span data-ttu-id="73c57-117">O problema ocorreu apenas com opções avançadas de segurança.</span><span class="sxs-lookup"><span data-stu-id="73c57-117">This issue only occurred with advanced security options.</span></span>


## <a name="known-issue"></a><span data-ttu-id="73c57-118">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="73c57-118">Known issue</span></span>

- <span data-ttu-id="73c57-119">**Erro**: Ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos.</span><span class="sxs-lookup"><span data-stu-id="73c57-119">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="73c57-120">**Solução alternativa:** Antes de abrir a página do anexo, garante que os caixas de dados na página **Trabalhador** estejam fechadas.</span><span class="sxs-lookup"><span data-stu-id="73c57-120">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="73c57-121">Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões Anexos serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="73c57-121">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="73c57-122">(Esse problema será corrigido na próxima atualização de plataforma.)</span><span class="sxs-lookup"><span data-stu-id="73c57-122">(This issue will be fixed in the next platform update.)</span></span>
