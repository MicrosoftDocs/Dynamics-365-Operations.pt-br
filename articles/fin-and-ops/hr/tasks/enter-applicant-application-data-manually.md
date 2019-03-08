---
title: Inserir dados do candidato e da solicitação de emprego manualmente
description: Este procedimento mostra como manter manualmente as informações sobre os candidatos e a solicitação de emprego.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60b3d155826d234744c9805b18edf0226e237ed3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "364525"
---
# <a name="enter-applicant-and-application-data-manually"></a><span data-ttu-id="7b0f1-103">Inserir dados do candidato e da solicitação de emprego manualmente</span><span class="sxs-lookup"><span data-stu-id="7b0f1-103">Enter applicant and application data manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7b0f1-104">Este procedimento mostra como manter manualmente as informações sobre os candidatos e a solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-104">This procedure shows how to manually maintain information about applicants and their application.</span></span>   <span data-ttu-id="7b0f1-105">Você pode inserir e manter as informações pessoais, as datas e os horários de entrevista, as referências, as competências e as solicitações de acomodação para candidatos.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-105">You can enter and maintain personal information, interview dates and times, references, competencies, and accommodation requests for applicants.</span></span> <span data-ttu-id="7b0f1-106">Você também pode atualizar o status das ordens de candidatos de emprego e criar cartas ou mensagens de email para comunicar-se com os candidatos.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-106">You can also update the status of applicants’ applications for employment and create letters or email messages to communicate with applicants.</span></span> <span data-ttu-id="7b0f1-107">Quando você criar um registro do candidato, um registro para o candidato é criado no catálogo de endereços global.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-107">When you create an applicant record, a person record for that applicant is created in the global address book.</span></span>       <span data-ttu-id="7b0f1-108">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-new-applicant-record"></a><span data-ttu-id="7b0f1-109">Criar um novo registro de candidato</span><span class="sxs-lookup"><span data-stu-id="7b0f1-109">Create a new applicant record</span></span>
1. <span data-ttu-id="7b0f1-110">Vá para Recursos humanos > Recrutamento > Candidatos > Candidatos.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-110">Go to Human resources > Recruitment > Applicants > Applicants.</span></span>
2. <span data-ttu-id="7b0f1-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-111">Click New.</span></span>
3. <span data-ttu-id="7b0f1-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-112">In the First name field, type a value.</span></span>
4. <span data-ttu-id="7b0f1-113">No campo Sobrenome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-113">In the Last name field, type a value.</span></span>
    * <span data-ttu-id="7b0f1-114">Você pode inserir informações adicionais do candidato se estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-114">You can enter additional applicant information if it's available.</span></span> <span data-ttu-id="7b0f1-115">Por exemplo, as informações podem incluir o nível mais alto do candidato, o cargo atual ou o empregador anterior.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-115">For example, information can include the applicant's highest degree, current job title, or previous employer.</span></span>  
5. <span data-ttu-id="7b0f1-116">Alternar a expansão da seção Informações de contato.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-116">Toggle the expansion of the Contact information section.</span></span>
6. <span data-ttu-id="7b0f1-117">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-117">Click Add.</span></span>
7. <span data-ttu-id="7b0f1-118">No campo Descrição, digite 'Email de comunicação'.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-118">In the Description field, type 'Communications email'.</span></span>
8. <span data-ttu-id="7b0f1-119">No campo Tipo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-119">In the Type field, select an option.</span></span>
9. <span data-ttu-id="7b0f1-120">No campo Número/endereço de contato, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-120">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="7b0f1-121">Este endereço de email será usado para gerar comunicação de email com o candidato.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-121">This email address will be used to generate email communication with the applicant.</span></span>  
10. <span data-ttu-id="7b0f1-122">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-122">Click Add.</span></span>
11. <span data-ttu-id="7b0f1-123">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-123">In the Description field, type a value.</span></span>
12. <span data-ttu-id="7b0f1-124">No campo Número/endereço de contato, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-124">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="7b0f1-125">Informações pessoais do candidato.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-125">Applicant personal information.</span></span>  
    * <span data-ttu-id="7b0f1-126">Você pode inserir as informações pessoais adicionais do candidato, se necessário.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-126">You can enter additional personal information for the applicant, if needed.</span></span> <span data-ttu-id="7b0f1-127">Por exemplo, isso pode incluir a data de nascimento, a origem étnica, o gênero ou o estado civil.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-127">For example, this can include birth date, ethnic origin, gender, or marital status.</span></span>  
13. <span data-ttu-id="7b0f1-128">No Painel de Ação, clique em Competências.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-128">On the Action Pane, click Competencies.</span></span>
    * <span data-ttu-id="7b0f1-129">Você pode inserir o perfil de competência do candidato, incluindo suas experiências, habilidades profissionais, formação educacional, testes ou os certificados.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-129">You can enter the applicant's competency profile, including their skills, professional experiences, education, tests, or certificates.</span></span>  
    * <span data-ttu-id="7b0f1-130">Essas informações podem ser usadas para mapear habilidades do candidato às habilidades associadas ao trabalho definidas nos dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-130">This information can be used to map the applicant's skills to the skills associated with the jobs defined in your company's data.</span></span>   

## <a name="create-an-application-for-the-applicant"></a><span data-ttu-id="7b0f1-131">Crie uma solicitação de emprego para o candidato</span><span class="sxs-lookup"><span data-stu-id="7b0f1-131">Create an application for the applicant</span></span>
1. <span data-ttu-id="7b0f1-132">Clique em Solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-132">Click Applications.</span></span>
2. <span data-ttu-id="7b0f1-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-133">Click New.</span></span>
3. <span data-ttu-id="7b0f1-134">No campo Projeto de recrutamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-134">In the Recruitment project field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="7b0f1-135">Selecionando um projeto de recrutamento, o candidato será associado a uma determinada abertura incluída no projeto de recrutamento.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-135">By selecting a recruitment project, the applicant will be associated with a specific opening included in that recruitment project.</span></span>  
4. <span data-ttu-id="7b0f1-136">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-136">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="7b0f1-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7b0f1-138">Por padrão, os trabalhos e o departamento são baseados no projeto de recrutamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-138">By default, the job and department are based on the selected recruitment project.</span></span>  
6. <span data-ttu-id="7b0f1-139">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-139">Click Save.</span></span>
    * <span data-ttu-id="7b0f1-140">Após salvar a solicitação de emprego, você pode anexar documentos, inclusive a experiência do candidato, os prêmios e a carta de apresentação.</span><span class="sxs-lookup"><span data-stu-id="7b0f1-140">After saving the application, you can attach documents to it, including the applicant's experience, awards, and cover letter.</span></span>  

