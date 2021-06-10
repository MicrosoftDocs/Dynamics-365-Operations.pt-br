---
title: Mapear habilidades
description: Você pode criar uma pesquisa de mapeamento de habilidades para encontrar uma pessoa qualificada no Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 03b7860fbde89097141cfe48f2c240dc127aa9c3
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076577"
---
# <a name="map-skills"></a><span data-ttu-id="0f888-103">Mapear habilidades</span><span class="sxs-lookup"><span data-stu-id="0f888-103">Map skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0f888-104">Você pode criar uma pesquisa de mapeamento de habilidades para encontrar uma pessoa qualificada no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0f888-104">You can create a skill-mapping search to find a qualified person in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="0f888-105">As pesquisas de mapeamento de habilidades retornam resultados para os critérios inseridos consultando as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="0f888-105">Skill-mapping searches return results for criteria you enter by looking through the following information:</span></span>

- <span data-ttu-id="0f888-106">Habilidades</span><span class="sxs-lookup"><span data-stu-id="0f888-106">Skills</span></span>
- <span data-ttu-id="0f888-107">Formação</span><span class="sxs-lookup"><span data-stu-id="0f888-107">Education</span></span>
- <span data-ttu-id="0f888-108">Certificados</span><span class="sxs-lookup"><span data-stu-id="0f888-108">Certificates</span></span>
- <span data-ttu-id="0f888-109">Posições</span><span class="sxs-lookup"><span data-stu-id="0f888-109">Positions</span></span>
- <span data-ttu-id="0f888-110">Experiência em Projetos</span><span class="sxs-lookup"><span data-stu-id="0f888-110">Project experience</span></span>

<span data-ttu-id="0f888-111">Por exemplo, você pode encontrar pessoas em sua organização que receberam o CPA.</span><span class="sxs-lookup"><span data-stu-id="0f888-111">For example, you can find people in your organization who have earned their CPA.</span></span>

<span data-ttu-id="0f888-112">Os perfis de mapeamento de habilidades permitem que você encontre funcionários atuais ou candidatos com qualificações que correspondam diretamente às necessidades do negócio.</span><span class="sxs-lookup"><span data-stu-id="0f888-112">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>

> [!NOTE]
> <span data-ttu-id="0f888-113">Somente os trabalhadores, os candidatos e as pessoas de contato selecionados para serem incluídos em pesquisas de mapeamento de habilidade serão exibidos em uma lista dos resultados de um mapeamento de habilidades ou serem incluídos em um perfil de habilidades.</span><span class="sxs-lookup"><span data-stu-id="0f888-113">Only workers, applicants, and contact persons who are selected to be included in skill-mapping searches will display in a skill-mapping results list, or be included in a skill profile.</span></span> <span data-ttu-id="0f888-114">Para incluir uma pessoa nas pesquisas de mapeamento de habilidades, defina a seleção **Incluir no mapeamento de habilidades** como **Sim** nas seguintes páginas:</span><span class="sxs-lookup"><span data-stu-id="0f888-114">To include a person in skill mapping searches, set the **Include in skill mapping** selection to **Yes** in the following pages:</span></span><br>
> - <span data-ttu-id="0f888-115">Trabalhador</span><span class="sxs-lookup"><span data-stu-id="0f888-115">Worker</span></span><br>
> - <span data-ttu-id="0f888-116">Funcionário</span><span class="sxs-lookup"><span data-stu-id="0f888-116">Employee</span></span><br>
> - <span data-ttu-id="0f888-117">Candidato</span><span class="sxs-lookup"><span data-stu-id="0f888-117">Applicant</span></span><br>
> - <span data-ttu-id="0f888-118">Contatos</span><span class="sxs-lookup"><span data-stu-id="0f888-118">Contacts</span></span><br>

<span data-ttu-id="0f888-119">Para criar um mapeamento de habilidades, vá para **Desenvolvimento do funcionário > Links > Mapeamento de habilidades**.</span><span class="sxs-lookup"><span data-stu-id="0f888-119">To create a skill mapping, go to **Employee development > Links > Skill mapping**.</span></span> <span data-ttu-id="0f888-120">Para criar um perfil de mapeamento de habilidades, vá para **Desenvolvimento do funcionário > Links > Perfis de mapeamento de habilidades**.</span><span class="sxs-lookup"><span data-stu-id="0f888-120">To create a skill-mapping profile, go to **Employee development > Links > Skill mapping profiles**.</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="0f888-121">Análise da lacuna de habilidades e análise do perfil de habilidades</span><span class="sxs-lookup"><span data-stu-id="0f888-121">Skill gap analysis and skill profile analysis</span></span>

<span data-ttu-id="0f888-122">Você pode criar uma análise de perfil de habilidade para exibir uma lista das competências de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="0f888-122">You can create a skill profile analysis to view a list of a person's competencies.</span></span> <span data-ttu-id="0f888-123">Você pode criar uma análise de lacuna de habilidades para comparar as habilidades de uma pessoa e as habilidades necessárias para um trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f888-123">You can create a skill gap analysis to compare a person’s skills and the skills required for a job.</span></span>

<span data-ttu-id="0f888-124">Para criar uma análise de lacunas, vá para **Desenvolvimento do funcionário > Links > Trabalho de análise de lacuna de habilidades - pessoa**.</span><span class="sxs-lookup"><span data-stu-id="0f888-124">To create a gap analysis, go to **Employee development > Links > Skill gap analysis job - person**.</span></span> <span data-ttu-id="0f888-125">Para criar uma análise de perfil de habilidades, vá para **Desenvolvimento do funcionários > Links > Análise do perfil de habilidades**.</span><span class="sxs-lookup"><span data-stu-id="0f888-125">To create a skill profile analysis, go to **Employee development > Links > Skill profile analysis**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0f888-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0f888-126">See also</span></span>

[<span data-ttu-id="0f888-127">Configurar habilidades</span><span class="sxs-lookup"><span data-stu-id="0f888-127">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="0f888-128">Inserir habilidades</span><span class="sxs-lookup"><span data-stu-id="0f888-128">Enter skills</span></span>](hr-develop-enter-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]