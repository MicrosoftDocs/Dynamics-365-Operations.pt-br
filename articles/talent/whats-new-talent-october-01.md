---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (1 de outubro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 97820cd25ece48dc0b8045d9ba509d0971ca5aad
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "303237"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-1-2018"></a><span data-ttu-id="5699d-103">Novidades ou alterações no Dynamics 365 for Talent Core HR (1 de outubro de 2018)</span><span class="sxs-lookup"><span data-stu-id="5699d-103">What's new or changed in Dynamics 365 for Talent Core HR (October 1, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5699d-104">**Compilação 8.1.1035.0**</span><span class="sxs-lookup"><span data-stu-id="5699d-104">**Build 8.1.1035.0**</span></span>

<span data-ttu-id="5699d-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="5699d-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="turn-off-electronic-payment-validation"></a><span data-ttu-id="5699d-106">Desativar validação de pagamentos eletrônicos</span><span class="sxs-lookup"><span data-stu-id="5699d-106">Turn off electronic payment validation</span></span>

<span data-ttu-id="5699d-107">A validação das informações de pagamentos eletrônicos ocorre se você configurar os pagamentos para depósito direto no espaço de trabalho **Autoatendimento para funcionários** (ESS) ou diretamente no formulário do funcionário.</span><span class="sxs-lookup"><span data-stu-id="5699d-107">Electronic payment information validation occurs if you set up disbursements for direct deposit either through **Employee self-service** workspace (ESS) or directly on the employee form.</span></span> <span data-ttu-id="5699d-108">Essa opção oferece a flexibilidade para remover essa validação se você não requer as verificações de validação para valores e valores restantes.</span><span class="sxs-lookup"><span data-stu-id="5699d-108">This option gives you the flexibility to remove that validation if you do not require the validation checks for amounts and remainder values.</span></span> <span data-ttu-id="5699d-109">Esse recurso é útil se você está se integrando a um sistema de folha de pagamento externo que tem com requisitos diferentes.</span><span class="sxs-lookup"><span data-stu-id="5699d-109">This feature is helpful if you're integrating with an external payroll system that has different requirements.</span></span>

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a><span data-ttu-id="5699d-110">Autoatendimento para gerentes – Adicionar metas para membros de equipe no bloco Metas de desempenho da equipe</span><span class="sxs-lookup"><span data-stu-id="5699d-110">Manager self-service - Add goals for team members through the Team performance goals tile</span></span>

<span data-ttu-id="5699d-111">Antes desta versão, os gerentes podiam adicionar metas aos funcionários individualmente por meio das metas de desempenho associadas a cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="5699d-111">Prior to this release, managers can add goals to their employees individually through the performance goals associated to each employee.</span></span> <span data-ttu-id="5699d-112">Com essa atualização, os gerentes podem acessar o bloco **Metas de desempenho da equipe** e criar novas metas marcando alguns de seus relatórios diretos.</span><span class="sxs-lookup"><span data-stu-id="5699d-112">With this update, managers can access the **Team performance goals** tile and create new goals by selecting any of their direct reports.</span></span>

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a><span data-ttu-id="5699d-113">Autoatendimento para gerentes – Adicionar avaliações para membros de equipe no bloco Avaliações de desempenho da equipe</span><span class="sxs-lookup"><span data-stu-id="5699d-113">Manager self-service - Add reviews for team members through the Team performance reviews tile</span></span>

<span data-ttu-id="5699d-114">Antes desta versão, os gerentes podiam adicionar avaliações aos funcionários individualmente com as avaliações associadas a cada funcionário.</span><span class="sxs-lookup"><span data-stu-id="5699d-114">Prior to this release, managers can add reviews to their employees individually through the reviews associated to each employee.</span></span> <span data-ttu-id="5699d-115">Com essa atualização, os gerentes podem acessar o bloco **Avaliações de desempenho da equipe** e criar novas avaliações marcando alguns de seus relatórios diretos.</span><span class="sxs-lookup"><span data-stu-id="5699d-115">With this update, managers can access the **Team performance reviews** tile and create new reviews by selecting any of their direct reports.</span></span>

## <a name="configure-proration-options-by-leave-plan"></a><span data-ttu-id="5699d-116">Configurar opções de rateio por plano de licença</span><span class="sxs-lookup"><span data-stu-id="5699d-116">Configure proration options by leave plan</span></span>

<span data-ttu-id="5699d-117">As organizações concedem folgas de maneira diferente com base em quando os funcionários entraram e saíram da empresa.</span><span class="sxs-lookup"><span data-stu-id="5699d-117">Organizations award time off differently based on when employees join and leave the company.</span></span> <span data-ttu-id="5699d-118">Para algumas organizações, os funcionários são recebem a alocação total na sua data de início, enquanto outros fazem rateio da concessão.</span><span class="sxs-lookup"><span data-stu-id="5699d-118">For some organizations, employees are awarded their full allocation on their start date while others prorate the award.</span></span> <span data-ttu-id="5699d-119">São oferecidas novas opções nesta versão para escolher como fazer o rateio de concessões e competências para pessoas que estão entrando ou saindo de uma organização.</span><span class="sxs-lookup"><span data-stu-id="5699d-119">New options are provided in this release to choose how to prorate the awards and accruals for joiners and leavers in an organization.</span></span> <span data-ttu-id="5699d-120">As opções incluem: rateado, competência total e nenhuma competência.</span><span class="sxs-lookup"><span data-stu-id="5699d-120">Options include: Prorated, Full accrual, and No accrual.</span></span>

## <a name="other-changes"></a><span data-ttu-id="5699d-121">Outras alterações</span><span class="sxs-lookup"><span data-stu-id="5699d-121">Other changes</span></span>

-   <span data-ttu-id="5699d-122">Entidade de funcionário atualizada – O título **Pessoal** agora pode ser atualizado usando o suplemento/gerenciamento de dados do Excel.</span><span class="sxs-lookup"><span data-stu-id="5699d-122">Employee entity updated - The **Personal** title can now be updated using the Excel add-in/data management.</span></span>

-   <span data-ttu-id="5699d-123">Alteração de segurança para permitir a remoção dos botões **Excluir** e **Desativar** no autoatendimento para funcionários de informações de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5699d-123">Security change to allow removal of the **Delete** and **Deactivate** buttons in employee self-service for payment information.</span></span>

## <a name="known-issue"></a><span data-ttu-id="5699d-124">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="5699d-124">Known issue</span></span>

-   <span data-ttu-id="5699d-125">**Problema:** ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. **Solução alternativa:** antes de abrir a página do anexo, verifique se os Quadros de Fatos na página **Trabalhador** estão fechados.</span><span class="sxs-lookup"><span data-stu-id="5699d-125">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="5699d-126">Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões **Anexos** serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="5699d-126">If the FactBoxes are closed when the **Worker** page is loaded, the **Attachments** buttons will be enabled.</span></span> <span data-ttu-id="5699d-127">(Esse problema será corrigido na próxima atualização de plataforma.)</span><span class="sxs-lookup"><span data-stu-id="5699d-127">(This issue will be fixed in the next platform update.)</span></span>
