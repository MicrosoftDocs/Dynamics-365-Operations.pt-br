---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (8 de outubro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/07/2018
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
ms.search.validFrom: 2018-10-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 34216e2181915cf615e6e77fa2a10d06a4e9db85
ms.sourcegitcommit: aec1dcd44274e9b8d0770836598fde5533b7b569
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2019
ms.locfileid: "1617263"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-8-2018"></a><span data-ttu-id="406e8-103">Novidades ou alterações no Dynamics 365 for Talent Core HR (8 de outubro de 2018)</span><span class="sxs-lookup"><span data-stu-id="406e8-103">What's new or changed in Dynamics 365 for Talent Core HR (October 8, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="406e8-104">**Compilação 8.1.1050.0**</span><span class="sxs-lookup"><span data-stu-id="406e8-104">**Build 8.1.1050.0**</span></span>

<span data-ttu-id="406e8-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="406e8-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-other-dates-to-be-used-on-leave-tier-basis-leave-management"></a><span data-ttu-id="406e8-106">Permita que outras datas sejam usadas com base na camada de licença (gerenciamento da licença)</span><span class="sxs-lookup"><span data-stu-id="406e8-106">Allow other dates to be used on leave tier basis (Leave Management)</span></span>

<span data-ttu-id="406e8-107">Para conceder licença a funcionários, a base da camada de concessão determina quanto tempo de licença um funcionário tem.</span><span class="sxs-lookup"><span data-stu-id="406e8-107">When awarding leave to employees, the award tier basis determines how much time off an employee accrues.</span></span> <span data-ttu-id="406e8-108">Atualmente, três camadas baseiam-se na data inicial do funcionário e a data de precedência.</span><span class="sxs-lookup"><span data-stu-id="406e8-108">Currently, these tiers are based on employee start date and seniority date.</span></span> <span data-ttu-id="406e8-109">Em algumas situações, as organizações precisam que essas três camadas sejam baseadas em outras datas, como data de aniversário ou data original de contratação.</span><span class="sxs-lookup"><span data-stu-id="406e8-109">In some scenarios, organizations need these tiers to be based on other dates, like anniversary date or original hire date.</span></span> <span data-ttu-id="406e8-110">Essas datas serão usadas no plano de licença para determinar quando a liberação acontece, a habilidade dessas mesmas datas a serem usadas quando um funcionário é registrado em um plano foram adicionadas para determinar o tamanho da licença.</span><span class="sxs-lookup"><span data-stu-id="406e8-110">These dates are already used on the leave plan to determine when accruals happen, the ability for these same dates to be used when an employee is enrolled in a plan have been added to determine the accrual amount.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="406e8-111">Outras alterações</span><span class="sxs-lookup"><span data-stu-id="406e8-111">Other changes</span></span>
<span data-ttu-id="406e8-112">Correções diversas foram incluídas nesta versão.</span><span class="sxs-lookup"><span data-stu-id="406e8-112">Miscellanous fixes have been included in this release.</span></span>

## <a name="known-issue"></a><span data-ttu-id="406e8-113">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="406e8-113">Known issue</span></span>

<span data-ttu-id="406e8-114">**Problema:** ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. **Solução alternativa:** antes de abrir a página do anexo, verifique se os Quadros de Fatos na página **Trabalhador** estão fechados.</span><span class="sxs-lookup"><span data-stu-id="406e8-114">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="406e8-115">Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões Anexos serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="406e8-115">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="406e8-116">(Esse problema será corrigido na próxima atualização de plataforma.)</span><span class="sxs-lookup"><span data-stu-id="406e8-116">(This issue will be fixed in the next platform update.)</span></span>
