---
title: Inserir dados do candidato e da solicitação de emprego manualmente
description: Este procedimento mostra como manter manualmente as informações sobre os candidatos e a solicitação de emprego.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea61e3c1d76ade6e0d694b4b521e4be76fc8799d
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "855858"
---
# <a name="enter-applicant-and-application-data-manually"></a><span data-ttu-id="9f241-103">Inserir dados do candidato e da solicitação de emprego manualmente</span><span class="sxs-lookup"><span data-stu-id="9f241-103">Enter applicant and application data manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9f241-104">Este procedimento mostra como manter manualmente as informações sobre os candidatos e a solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="9f241-104">This procedure shows how to manually maintain information about applicants and their application.</span></span>   <span data-ttu-id="9f241-105">Você pode inserir e manter as informações pessoais, as datas e os horários de entrevista, as referências, as competências e as solicitações de acomodação para candidatos.</span><span class="sxs-lookup"><span data-stu-id="9f241-105">You can enter and maintain personal information, interview dates and times, references, competencies, and accommodation requests for applicants.</span></span> <span data-ttu-id="9f241-106">Você também pode atualizar o status das ordens de candidatos de emprego e criar cartas ou mensagens de email para comunicar-se com os candidatos.</span><span class="sxs-lookup"><span data-stu-id="9f241-106">You can also update the status of applicants’ applications for employment and create letters or email messages to communicate with applicants.</span></span> <span data-ttu-id="9f241-107">Quando você criar um registro do candidato, um registro para o candidato é criado no catálogo de endereços global.</span><span class="sxs-lookup"><span data-stu-id="9f241-107">When you create an applicant record, a person record for that applicant is created in the global address book.</span></span>       <span data-ttu-id="9f241-108">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="9f241-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-new-applicant-record"></a><span data-ttu-id="9f241-109">Criar um novo registro de candidato</span><span class="sxs-lookup"><span data-stu-id="9f241-109">Create a new applicant record</span></span>
1. <span data-ttu-id="9f241-110">Vá para Recursos humanos > Recrutamento > Candidatos > Candidatos.</span><span class="sxs-lookup"><span data-stu-id="9f241-110">Go to Human resources > Recruitment > Applicants > Applicants.</span></span>
2. <span data-ttu-id="9f241-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9f241-111">Click New.</span></span>
3. <span data-ttu-id="9f241-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9f241-112">In the First name field, type a value.</span></span>
4. <span data-ttu-id="9f241-113">No campo Sobrenome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9f241-113">In the Last name field, type a value.</span></span>
    * <span data-ttu-id="9f241-114">Você pode inserir informações adicionais do candidato se estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="9f241-114">You can enter additional applicant information if it's available.</span></span> <span data-ttu-id="9f241-115">Por exemplo, as informações podem incluir o nível mais alto do candidato, o cargo atual ou o empregador anterior.</span><span class="sxs-lookup"><span data-stu-id="9f241-115">For example, information can include the applicant's highest degree, current job title, or previous employer.</span></span>  
5. <span data-ttu-id="9f241-116">Alternar a expansão da seção Informações de contato.</span><span class="sxs-lookup"><span data-stu-id="9f241-116">Toggle the expansion of the Contact information section.</span></span>
6. <span data-ttu-id="9f241-117">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="9f241-117">Click Add.</span></span>
7. <span data-ttu-id="9f241-118">No campo Descrição, digite 'Email de comunicação'.</span><span class="sxs-lookup"><span data-stu-id="9f241-118">In the Description field, type 'Communications email'.</span></span>
8. <span data-ttu-id="9f241-119">No campo Tipo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="9f241-119">In the Type field, select an option.</span></span>
9. <span data-ttu-id="9f241-120">No campo Número/endereço de contato, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9f241-120">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="9f241-121">Este endereço de email será usado para gerar comunicação de email com o candidato.</span><span class="sxs-lookup"><span data-stu-id="9f241-121">This email address will be used to generate email communication with the applicant.</span></span>  
10. <span data-ttu-id="9f241-122">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="9f241-122">Click Add.</span></span>
11. <span data-ttu-id="9f241-123">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9f241-123">In the Description field, type a value.</span></span>
12. <span data-ttu-id="9f241-124">No campo Número/endereço de contato, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9f241-124">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="9f241-125">Informações pessoais do candidato.</span><span class="sxs-lookup"><span data-stu-id="9f241-125">Applicant personal information.</span></span>  
    * <span data-ttu-id="9f241-126">Você pode inserir as informações pessoais adicionais do candidato, se necessário.</span><span class="sxs-lookup"><span data-stu-id="9f241-126">You can enter additional personal information for the applicant, if needed.</span></span> <span data-ttu-id="9f241-127">Por exemplo, isso pode incluir a data de nascimento, a origem étnica, o gênero ou o estado civil.</span><span class="sxs-lookup"><span data-stu-id="9f241-127">For example, this can include birth date, ethnic origin, gender, or marital status.</span></span>  
13. <span data-ttu-id="9f241-128">No Painel de Ação, clique em Competências.</span><span class="sxs-lookup"><span data-stu-id="9f241-128">On the Action Pane, click Competencies.</span></span>
    * <span data-ttu-id="9f241-129">Você pode inserir o perfil de competência do candidato, incluindo suas experiências, habilidades profissionais, formação educacional, testes ou os certificados.</span><span class="sxs-lookup"><span data-stu-id="9f241-129">You can enter the applicant's competency profile, including their skills, professional experiences, education, tests, or certificates.</span></span>  
    * <span data-ttu-id="9f241-130">Essas informações podem ser usadas para mapear habilidades do candidato às habilidades associadas ao trabalho definidas nos dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="9f241-130">This information can be used to map the applicant's skills to the skills associated with the jobs defined in your company's data.</span></span>   

## <a name="create-an-application-for-the-applicant"></a><span data-ttu-id="9f241-131">Crie uma solicitação de emprego para o candidato</span><span class="sxs-lookup"><span data-stu-id="9f241-131">Create an application for the applicant</span></span>
1. <span data-ttu-id="9f241-132">Clique em Solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="9f241-132">Click Applications.</span></span>
2. <span data-ttu-id="9f241-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9f241-133">Click New.</span></span>
3. <span data-ttu-id="9f241-134">No campo Projeto de recrutamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9f241-134">In the Recruitment project field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="9f241-135">Selecionando um projeto de recrutamento, o candidato será associado a uma determinada abertura incluída no projeto de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="9f241-135">By selecting a recruitment project, the applicant will be associated with a specific opening included in that recruitment project.</span></span>  
4. <span data-ttu-id="9f241-136">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="9f241-136">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="9f241-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9f241-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9f241-138">Por padrão, os trabalhos e o departamento são baseados no projeto de recrutamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="9f241-138">By default, the job and department are based on the selected recruitment project.</span></span>  
6. <span data-ttu-id="9f241-139">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9f241-139">Click Save.</span></span>
    * <span data-ttu-id="9f241-140">Após salvar a solicitação de emprego, você pode anexar documentos, inclusive a experiência do candidato, os prêmios e a carta de apresentação.</span><span class="sxs-lookup"><span data-stu-id="9f241-140">After saving the application, you can attach documents to it, including the applicant's experience, awards, and cover letter.</span></span>  

