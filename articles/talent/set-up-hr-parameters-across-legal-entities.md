---
title: Configurar parâmetros de RH entre entidades legais
description: Você deve configurar parâmetros compartilhados para os registros compartilhados entre empresas, como Registros de posições. Este artigo explica como configurar parâmetros de Recursos humanos entre entidades legais.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: a8167545864a1cc2fc22f044f7d16ca590d59b43
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "859197"
---
# <a name="set-up-human-resources-hr-parameters-across-legal-entities"></a><span data-ttu-id="d485c-104">Configurar parâmetros de RH entre entidades legais</span><span class="sxs-lookup"><span data-stu-id="d485c-104">Set up Human resources (HR) parameters across legal entities</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d485c-105">Você deve configurar parâmetros compartilhados para os registros compartilhados entre empresas, como Registros de posições.</span><span class="sxs-lookup"><span data-stu-id="d485c-105">You must set up shared parameters for records that are shared across companies, such as Position records.</span></span> <span data-ttu-id="d485c-106">Este artigo explica como configurar parâmetros de Recursos humanos entre entidades legais.</span><span class="sxs-lookup"><span data-stu-id="d485c-106">This article explains how to set up Human resources parameters across legal entities.</span></span>

<span data-ttu-id="d485c-107">Alguns tipos de registros, como os registros de posição, são compartilhados entre empresas.</span><span class="sxs-lookup"><span data-stu-id="d485c-107">Some types of records, such as Position records, are shared across companies.</span></span> <span data-ttu-id="d485c-108">Para esses registros, é necessário configurar parâmetros compartilhados.</span><span class="sxs-lookup"><span data-stu-id="d485c-108">For these records, you must set up shared parameters.</span></span> <span data-ttu-id="d485c-109">Por exemplo, você pode usar a página **Parâmetros compartilhados de recursos humanos** para configurar parâmetros de recursos humanos entre entidades legais.</span><span class="sxs-lookup"><span data-stu-id="d485c-109">For example, you use the **Human resources shared parameters** page to set up Human resources parameters across legal entities.</span></span> 

<span data-ttu-id="d485c-110">Na página **Parâmetros compartilhados de recursos humanos**, os parâmetros são agrupados em áreas, com base em sua funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="d485c-110">On the **Human resources shared parameters** page, parameters are grouped into areas, based on their functionality.</span></span> 

### <a name="previously-released-functionality"></a><span data-ttu-id="d485c-111">Funcionalidade liberada anteriormente</span><span class="sxs-lookup"><span data-stu-id="d485c-111">Previously released functionality</span></span>
<span data-ttu-id="d485c-112">Na guia **Identificação**, selecione os tipos de identificação que representam os números de identificação listados na página.</span><span class="sxs-lookup"><span data-stu-id="d485c-112">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="d485c-113">Você deve configurar tipos de identificação para que você possa inserir informações de identificação para trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="d485c-113">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="d485c-114">As informações sobre número do seguro social, número de ID nacional, número de ID do estrangeiro e código de ID pessoal são mantidas na página **Tipo de identificação**.</span><span class="sxs-lookup"><span data-stu-id="d485c-114">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="d485c-115">Para definir um novo tipo de identificação ou revisar a lista de tipos existentes, clique em **Gerenciamento de pessoal** &gt; **Guia de links** &gt; **Configuração** &gt; **Tipos de identificação**.</span><span class="sxs-lookup"><span data-stu-id="d485c-115">To define a new identification type or review the list of existing types, click **Personnel management** &gt; **Links tab** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="d485c-116">Você pode inserir um código simples e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="d485c-116">You can enter a simple code and description.</span></span> 

### <a name="if-youre-using-dynamics-365-for-talent"></a><span data-ttu-id="d485c-117">Se você estiver usando o Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="d485c-117">If you're using Dynamics 365 for Talent</span></span>
<span data-ttu-id="d485c-118">Na guia **Identificação**, selecione os tipos de identificação que representam os números de identificação listados na página.</span><span class="sxs-lookup"><span data-stu-id="d485c-118">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="d485c-119">Você deve configurar tipos de identificação para que você possa inserir informações de identificação para trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="d485c-119">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="d485c-120">As informações sobre número do seguro social, número de ID nacional, número de ID do estrangeiro e código de ID pessoal são mantidas na página **Tipo de identificação**.</span><span class="sxs-lookup"><span data-stu-id="d485c-120">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="d485c-121">Para definir um novo tipo de identificação ou revisar a lista de tipos existentes, clique em **Recursos humanos** &gt; **Configuração** &gt; **Tipos de identificação**.</span><span class="sxs-lookup"><span data-stu-id="d485c-121">To define a new identification type or review the list of existing types, click **Human resources** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="d485c-122">Você pode inserir um código simples e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="d485c-122">You can enter a simple code and description.</span></span> 

<span data-ttu-id="d485c-123">Na guia **Sequências numéricas**, você pode selecionar as sequências numéricas usadas nos seguintes registros: Número da equipe, Posição, ID da solicitação de usuário, Documento I-9, Candidato, Discussão, ID do Benefício e Ação de pessoal (se esse tipo de registro estiver habilitado).</span><span class="sxs-lookup"><span data-stu-id="d485c-123">On the **Number sequences** tab, you can select the number sequences that are used for the following records: Personnel number, Position, User request ID, I-9 document, Applicant, Discussion, Benefit ID, and Personnel action (if this record type is enabled).</span></span> <span data-ttu-id="d485c-124">Para manter as referências e os códigos de sequência numérica, use a página de lista **Sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="d485c-124">To maintain number sequence references and codes, use the **Number sequences** list page.</span></span> <span data-ttu-id="d485c-125">Para localizar essa página, use o recurso de pesquisa de página.</span><span class="sxs-lookup"><span data-stu-id="d485c-125">To find this page, use the page search feature.</span></span> 

<span data-ttu-id="d485c-126">Na guia **Posições**, indique se as novas posições estão disponíveis para atribuição por padrão:</span><span class="sxs-lookup"><span data-stu-id="d485c-126">On the **Positions** tab, indicate whether new positions are available for assignment by default:</span></span>

-   <span data-ttu-id="d485c-127">**Sempre** – Você pode atribuir trabalhadores a novas posições quando estas forem criadas.</span><span class="sxs-lookup"><span data-stu-id="d485c-127">**Always** – You can assign workers to new positions when positions are created.</span></span> <span data-ttu-id="d485c-128">Quando as posições são criadas, a data e hora **Disponível para a atribuição** na guia **Geral** da página **Posição** são automaticamente definidas para a data e hora de criação.</span><span class="sxs-lookup"><span data-stu-id="d485c-128">When positions are created, the **Available for assignment** date and time on the **General** tab of the **Position** page are automatically set to the creation date and time.</span></span>
-   <span data-ttu-id="d485c-129">**Nunca** – Você não pode atribuir trabalhadores a novas posições quando estas forem criadas.</span><span class="sxs-lookup"><span data-stu-id="d485c-129">**Never** – You can't assign workers to new positions when positions are created.</span></span> <span data-ttu-id="d485c-130">Se você selecionar essa opção, precisará abrir a página **Posição** para cada nova posição à medida que ela for disponibilizada. Em seguida, na guia **Geral**, insira **Disponível para atribuição** para habilitar a atribuição de trabalhador.</span><span class="sxs-lookup"><span data-stu-id="d485c-130">If you select this option, you must open the **Position** page for each new position as it becomes available, and then, on the **General** tab, enter the **Available for assignment** date to enable worker assignment.</span></span>


<a name="additional-resources"></a><span data-ttu-id="d485c-131">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d485c-131">Additional resources</span></span>
--------

[<span data-ttu-id="d485c-132">Configurar parâmetros de RH específicos da empresa</span><span class="sxs-lookup"><span data-stu-id="d485c-132">Set up company specific HR parameters</span></span>](set-up-company-specific-hr-parameters.md)



