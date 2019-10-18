---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (8 de outubro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
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
ms.openlocfilehash: 330ffebf73c8948a1bbab2ee57acba7b97a93b6f
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008864"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-8-2018"></a><span data-ttu-id="01e9c-103">Novidades ou alterações no Dynamics 365 Talent - Core HR (8 de outubro de 2018)</span><span class="sxs-lookup"><span data-stu-id="01e9c-103">What's new or changed in Dynamics 365 Talent - Core HR (October 8, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="01e9c-104">**Compilação 8.1.1050.0**</span><span class="sxs-lookup"><span data-stu-id="01e9c-104">**Build 8.1.1050.0**</span></span>

<span data-ttu-id="01e9c-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="01e9c-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-other-dates-to-be-used-on-leave-tier-basis-leave-management"></a><span data-ttu-id="01e9c-106">Permita que outras datas sejam usadas com base na camada de licença (gerenciamento da licença)</span><span class="sxs-lookup"><span data-stu-id="01e9c-106">Allow other dates to be used on leave tier basis (Leave Management)</span></span>

<span data-ttu-id="01e9c-107">Para conceder licença a funcionários, a base da camada de concessão determina quanto tempo de licença um funcionário tem.</span><span class="sxs-lookup"><span data-stu-id="01e9c-107">When awarding leave to employees, the award tier basis determines how much time off an employee accrues.</span></span> <span data-ttu-id="01e9c-108">Atualmente, três camadas baseiam-se na data inicial do funcionário e a data de precedência.</span><span class="sxs-lookup"><span data-stu-id="01e9c-108">Currently, these tiers are based on employee start date and seniority date.</span></span> <span data-ttu-id="01e9c-109">Em algumas situações, as organizações precisam que essas três camadas sejam baseadas em outras datas, como data de aniversário ou data original de contratação.</span><span class="sxs-lookup"><span data-stu-id="01e9c-109">In some scenarios, organizations need these tiers to be based on other dates, like anniversary date or original hire date.</span></span> <span data-ttu-id="01e9c-110">Essas datas serão usadas no plano de licença para determinar quando a liberação acontece, a habilidade dessas mesmas datas a serem usadas quando um funcionário é registrado em um plano foram adicionadas para determinar o tamanho da licença.</span><span class="sxs-lookup"><span data-stu-id="01e9c-110">These dates are already used on the leave plan to determine when accruals happen, the ability for these same dates to be used when an employee is enrolled in a plan have been added to determine the accrual amount.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="01e9c-111">Outras alterações</span><span class="sxs-lookup"><span data-stu-id="01e9c-111">Other changes</span></span>
<span data-ttu-id="01e9c-112">Correções diversas foram incluídas nesta versão.</span><span class="sxs-lookup"><span data-stu-id="01e9c-112">Miscellanous fixes have been included in this release.</span></span>

## <a name="known-issue"></a><span data-ttu-id="01e9c-113">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="01e9c-113">Known issue</span></span>

<span data-ttu-id="01e9c-114">**Problema:** ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. **Solução alternativa:** antes de abrir a página do anexo, verifique se os Quadros de Fatos na página **Trabalhador** estão fechados.</span><span class="sxs-lookup"><span data-stu-id="01e9c-114">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="01e9c-115">Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões Anexos serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="01e9c-115">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="01e9c-116">(Esse problema será corrigido na próxima atualização de plataforma.)</span><span class="sxs-lookup"><span data-stu-id="01e9c-116">(This issue will be fixed in the next platform update.)</span></span>
