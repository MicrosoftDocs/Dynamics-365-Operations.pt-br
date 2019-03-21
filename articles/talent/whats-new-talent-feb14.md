---
title: Novidades ou alterações no Dynamics 365 for Talent (14 de fevereiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
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
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5f96dd60652705de820e0661d417dcaee8143561
ms.sourcegitcommit: 5384200c3e33510c5b3ac31f2b22443e1076251f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2019
ms.locfileid: "390646"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-14-2019"></a><span data-ttu-id="c26c9-103">Novidades ou alterações no Dynamics 365 for Talent (14 de fevereiro de 2019)</span><span class="sxs-lookup"><span data-stu-id="c26c9-103">What's new or changed in Dynamics 365 for Talent (February 14, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c26c9-104">Este tópico descreve os recursos novos ou alterados no Talent.</span><span class="sxs-lookup"><span data-stu-id="c26c9-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="c26c9-105">Alterações no Attract</span><span class="sxs-lookup"><span data-stu-id="c26c9-105">Changes in Attract</span></span>
<span data-ttu-id="c26c9-106">Correção de bug menores estão incluídas nesta versão.</span><span class="sxs-lookup"><span data-stu-id="c26c9-106">There are minor bug fixes included with this release.</span></span>

## <a name="changes-in-onboarding"></a><span data-ttu-id="c26c9-107">Alterações de Integração</span><span class="sxs-lookup"><span data-stu-id="c26c9-107">Changes in Onboarding</span></span>
<span data-ttu-id="c26c9-108">Correção de bug menores estão incluídas nesta versão.</span><span class="sxs-lookup"><span data-stu-id="c26c9-108">There are minor bug fixes included with this release.</span></span>
 
## <a name="changes-in-core-hr"></a><span data-ttu-id="c26c9-109">Alterações no Core HR</span><span class="sxs-lookup"><span data-stu-id="c26c9-109">Changes in Core HR</span></span> 
<span data-ttu-id="c26c9-110">**Compilação 8.1.2146**</span><span class="sxs-lookup"><span data-stu-id="c26c9-110">**Build 8.1.2146**</span></span>

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a><span data-ttu-id="c26c9-111">A entidade de remuneração fixa do funcionário não exportará todos os registros</span><span class="sxs-lookup"><span data-stu-id="c26c9-111">Employee fixed compensation entity doesn't export all records</span></span>
<span data-ttu-id="c26c9-112">Com essa alteração, a entidade **Remuneração fixa do funcionário** agora exportará todos os registros.</span><span class="sxs-lookup"><span data-stu-id="c26c9-112">With this change, the **Employee fixed compensation** entity will now export all records.</span></span> <span data-ttu-id="c26c9-113">A entidade pode ser usada para criar e atualizar registro de remuneração fixa existente para funcionários.</span><span class="sxs-lookup"><span data-stu-id="c26c9-113">The entity can be used to create and update existing fixed compensation records for employees.</span></span> 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a><span data-ttu-id="c26c9-114">A data final do emprego não honra as configurações de fuso horário preferenciais do funcionário</span><span class="sxs-lookup"><span data-stu-id="c26c9-114">Employment end date doesn't honor employee preferred time zone settings</span></span>
<span data-ttu-id="c26c9-115">As datas de término de emprego agora honram o fuso horário de preferência do usuário ao criar ou encerrar o emprego com uma empresa.</span><span class="sxs-lookup"><span data-stu-id="c26c9-115">Employment end dates are now honoring the user-preferred time zone when creating or ending employment with a company.</span></span>
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a><span data-ttu-id="c26c9-116">Endereços do Reino Unido são exibidos no Analytics como endereços no leste da Suíça</span><span class="sxs-lookup"><span data-stu-id="c26c9-116">UK addresses display in Analytics as Eastern Switzerland addresses</span></span>
<span data-ttu-id="c26c9-117">Nessa versão, uma alteração foi feita para corrigir mau alinhamento em endereços no relatório **Gerenciamento de Pessoal** "Número de funcionários por local".</span><span class="sxs-lookup"><span data-stu-id="c26c9-117">In this release, a change has been made to correct misalignment in addresses in the **Personnel Management** "Headcount by location" report.</span></span>
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a><span data-ttu-id="c26c9-118">O código de demissão não foi preenchido no registro de atribuição da posição do trabalhador quando a posição é encerrada</span><span class="sxs-lookup"><span data-stu-id="c26c9-118">Termination code is not populated on the worker position assignment record when ending the position</span></span>
<span data-ttu-id="c26c9-119">Uma alteração foi feita para deixar padrão o código "Motivo da demissão" ao finalizar a atribuição de posição dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="c26c9-119">A change has been made to default the "Termination reason" code when ending the employees position assignment.</span></span>

### <a name="new-entity-created-for-job-compensation-levels"></a><span data-ttu-id="c26c9-120">Nova entidade criada para níveis de remuneração de trabalho</span><span class="sxs-lookup"><span data-stu-id="c26c9-120">New entity created for job compensation levels</span></span>
<span data-ttu-id="c26c9-121">Uma nova entidade de estrutura de gerenciamento de dados (DMF) foi criada.</span><span class="sxs-lookup"><span data-stu-id="c26c9-121">A new data management framework (DMF) entity was created.</span></span> <span data-ttu-id="c26c9-122">A entidade ajuda na criação e atualiza para níveis de compensação, valores de mercado e informações de pesquisa para cada trabalho definido no sistema.</span><span class="sxs-lookup"><span data-stu-id="c26c9-122">The entity provides for creation and updates to compensation levels, market values, and survey information for each job defined in the system.</span></span>
