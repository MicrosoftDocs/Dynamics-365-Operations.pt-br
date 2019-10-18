---
title: Novidades ou alterações no Dynamics 365 Talent (7 de fevereiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
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
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c4005a8745e46a23fe16b94cab7b7aeb20f84035
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009753"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-february-7-2019"></a><span data-ttu-id="5b881-103">Novidades ou alterações no Dynamics 365 Talent (7 de fevereiro de 2019)</span><span class="sxs-lookup"><span data-stu-id="5b881-103">What's new or changed in Dynamics 365 Talent (February 7, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5b881-104">Este tópico descreve os recursos novos ou alterados no Talent.</span><span class="sxs-lookup"><span data-stu-id="5b881-104">This topic describes features that are either new or changed in Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="5b881-105">Alterações no Attract</span><span class="sxs-lookup"><span data-stu-id="5b881-105">Changes in Attract</span></span>

### <a name="interview-scheduling-enhancements"></a><span data-ttu-id="5b881-106">Aprimoramentos de agendamento de entrevista</span><span class="sxs-lookup"><span data-stu-id="5b881-106">Interview scheduling enhancements</span></span>
<span data-ttu-id="5b881-107">Melhorias foram feitas para a experiência de agendamento da entrevista de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="5b881-107">Improvements have been made to the end-to-end interview scheduling experience.</span></span> <span data-ttu-id="5b881-108">Agora você pode ver a disponibilidade do calendário de um candidato interno e usar o calendário do candidato interno para agendar recomendações.</span><span class="sxs-lookup"><span data-stu-id="5b881-108">You can now see the calendar availability of an internal candidate and use the internal candidate’s calendar for schedule recommendations.</span></span> <span data-ttu-id="5b881-109">Para obter mais informações, consulte [Agendamento de entrevistas e comentários](interview-scheduling-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="5b881-109">For more information, see [Interview scheduling and feedback](interview-scheduling-feedback.md).</span></span>

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a><span data-ttu-id="5b881-110">Postagem de vagas no LinkedIn – erro de incompatibilidade de empresa corrigido</span><span class="sxs-lookup"><span data-stu-id="5b881-110">Job posting to LinkedIn – company mismatch issue fixed</span></span>
<span data-ttu-id="5b881-111">Um problema foi corrigido onde trabalhos postados no LinkedIn do Attract estavam aparecendo no nome de empresa errado.</span><span class="sxs-lookup"><span data-stu-id="5b881-111">An issue has been fixed where jobs posted to LinkedIn from Attract were appearing under the wrong company name.</span></span> <span data-ttu-id="5b881-112">Para obter mais informações, consulte [Criar, aprovar e postar trabalhos no Attract](creating-jobs-attract.md).</span><span class="sxs-lookup"><span data-stu-id="5b881-112">For more information, see [Create, approve, and post jobs in Attract](creating-jobs-attract.md).</span></span>

### <a name="career-site-url-displayed-in-admin-settings"></a><span data-ttu-id="5b881-113">URL do site de carreira exibida nas configurações do administrador</span><span class="sxs-lookup"><span data-stu-id="5b881-113">Career site URL displayed in Admin settings</span></span>
<span data-ttu-id="5b881-114">A URL da página inicial do site de carreira agora é exibida nas **Configurações do administrados** em **gerenciamento de sites de carreira**.</span><span class="sxs-lookup"><span data-stu-id="5b881-114">The career site home page URL is now displayed in **Admin Settings** under **Career Site management**.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="5b881-115">Alterações no Core HR</span><span class="sxs-lookup"><span data-stu-id="5b881-115">Changes in Core HR</span></span>

<span data-ttu-id="5b881-116">**Compilação 8.1.2134**</span><span class="sxs-lookup"><span data-stu-id="5b881-116">**Build 8.1.2134**</span></span>

### <a name="multiple-compensation-levels-supported-on-jobs"></a><span data-ttu-id="5b881-117">Vários níveis de remuneração suportados em trabalhos</span><span class="sxs-lookup"><span data-stu-id="5b881-117">Multiple compensation levels supported on jobs</span></span>
<span data-ttu-id="5b881-118">Esta alteração permite que mais de um nível de compensação seja definido em um trabalho, habilitando as variações de remuneração fixa de funcionário, que podem ser diferentes entre planos usando o mesmo trabalho.</span><span class="sxs-lookup"><span data-stu-id="5b881-118">This change allows for more than one compensation level to be defined on a job, enabling employee fixed compensation ranges which may differ between plans when using the same job.</span></span> 

<span data-ttu-id="5b881-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5b881-119">For example:</span></span>    
<span data-ttu-id="5b881-120">*Trabalho* - Gerente de conta *Níveis de compensação associados:* B1 e B2 - Cada nível tem uma variação definida de valores.</span><span class="sxs-lookup"><span data-stu-id="5b881-120">*Job* - Account Manager *Associated compensation levels:* B1 and B2 - Each level has a defined range of values.</span></span> <span data-ttu-id="5b881-121">B1 = Mín 50.000, Méd 60.000, Máx 75.000 e B2 = Mín 65.000, Méd 74.000, Máx 85.000.</span><span class="sxs-lookup"><span data-stu-id="5b881-121">B1 = Min 50,000, Mid 60,000, Max 75,000 and B2 = Min 65,000, Mid 74,000, Max 85,000.</span></span> <span data-ttu-id="5b881-122">Ao criar remuneração fixa para funcionários, com base nas regras de elegibilidade definidas, cada plano fixo agora aponta para o mesmo trabalho e para níveis diferentes no trabalho.</span><span class="sxs-lookup"><span data-stu-id="5b881-122">When creating fixed compensation for employees, based on the eligibility rules defined, each fixed plan can now point to the same job and to different levels on the job.</span></span> <span data-ttu-id="5b881-123">Isso permite que planos sejam definidos em regiões/empresas diferentes e apontem para o mesmo trabalho, mas em variações diferentes sem duplicar trabalhos que tenham essas diferenças.</span><span class="sxs-lookup"><span data-stu-id="5b881-123">This allows for plans to be defined in different regions/companies and point to the same job but different ranges without duplicating jobs to account for these differences.</span></span>

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a><span data-ttu-id="5b881-124">O campo de nível de compensação foi adicionado à entidade de remuneração fixa de funcionário</span><span class="sxs-lookup"><span data-stu-id="5b881-124">Compensation level field has been added to the Employee fixed compensation entity</span></span> 
<span data-ttu-id="5b881-125">Com essa atualização, a entidade de remuneração fixa de funcionários foi atualizada para incluir o campo **Nível de remuneração**.</span><span class="sxs-lookup"><span data-stu-id="5b881-125">With this update, the employee fixed compensation entity has been updated to include the **Compensation level** field.</span></span> <span data-ttu-id="5b881-126">Essa adição facilita a atualização de planos de remuneração fixa de funcionário.</span><span class="sxs-lookup"><span data-stu-id="5b881-126">This addition makes it easier to update employee fixed compensation plans.</span></span> 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a><span data-ttu-id="5b881-127">Atualize a família de trabalho ao atualizar e criar novas posições</span><span class="sxs-lookup"><span data-stu-id="5b881-127">Update Job family when updating and creating new positions</span></span>
<span data-ttu-id="5b881-128">Ao alterar o trabalho em uma posição, **Família de trabalho** agora será padrão com base no trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="5b881-128">When changing the job on a position, **Job family** will now default based on the job selected.</span></span>

### <a name="performance-improvements-when-rendering-workspaces"></a><span data-ttu-id="5b881-129">Melhorias de desempenho ao renderizar espaços de trabalho</span><span class="sxs-lookup"><span data-stu-id="5b881-129">Performance improvements when rendering workspaces</span></span>
<span data-ttu-id="5b881-130">Guias de análise em espaços de trabalho agora carregarão ao acessar essas páginas.</span><span class="sxs-lookup"><span data-stu-id="5b881-130">Analytics tabs on workspaces will now load only when accessing those pages.</span></span> <span data-ttu-id="5b881-131">Um indicador será exibido durante a renderização inicial da página no canto superior esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="5b881-131">An indicator will display during the initial rendering of the page in the upper-left corner of the page.</span></span>
