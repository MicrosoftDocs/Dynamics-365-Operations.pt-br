---
title: "Configurar parâmetros de RH entre entidades legais"
description: "Você deve configurar parâmetros compartilhados para os registros compartilhados entre empresas, como Registros de posições. Este artigo explica como configurar parâmetros de Recursos humanos entre entidades legais."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 90d348f8b8414d6e31092cdd18760375dd283155
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-hr-parameters-across-legal-entities"></a><span data-ttu-id="c27b6-104">Configurar parâmetros de RH entre entidades legais</span><span class="sxs-lookup"><span data-stu-id="c27b6-104">Set up HR parameters across legal entities</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="c27b6-105">Você deve configurar parâmetros compartilhados para os registros compartilhados entre empresas, como Registros de posições.</span><span class="sxs-lookup"><span data-stu-id="c27b6-105">You must set up shared parameters for records that are shared across companies, such as Position records.</span></span> <span data-ttu-id="c27b6-106">Este artigo explica como configurar parâmetros de Recursos humanos entre entidades legais.</span><span class="sxs-lookup"><span data-stu-id="c27b6-106">This article explains how to set up Human resources parameters across legal entities.</span></span>

<span data-ttu-id="c27b6-107">Alguns tipos de registros, como os registros de posição, são compartilhados entre empresas.</span><span class="sxs-lookup"><span data-stu-id="c27b6-107">Some types of records, such as Position records, are shared across companies.</span></span> <span data-ttu-id="c27b6-108">Para esses registros, é necessário configurar parâmetros compartilhados.</span><span class="sxs-lookup"><span data-stu-id="c27b6-108">For these records, you must set up shared parameters.</span></span> <span data-ttu-id="c27b6-109">Por exemplo, você pode usar a página **Parâmetros compartilhados de recursos humanos** para configurar parâmetros de recursos humanos entre entidades legais.</span><span class="sxs-lookup"><span data-stu-id="c27b6-109">For example, you use the **Human resources shared parameters** page to set up Human resources parameters across legal entities.</span></span> 

<span data-ttu-id="c27b6-110">Na página **Parâmetros compartilhados de recursos humanos**, os parâmetros são agrupados em áreas, com base em sua funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="c27b6-110">On the **Human resources shared parameters** page, parameters are grouped into areas, based on their functionality.</span></span> 

### <a name="previously-released-functionality"></a><span data-ttu-id="c27b6-111">Funcionalidade liberada anteriormente</span><span class="sxs-lookup"><span data-stu-id="c27b6-111">Previously released functionality</span></span>
<span data-ttu-id="c27b6-112">Na guia **Identificação**, selecione os tipos de identificação que representam os números de identificação listados na página.</span><span class="sxs-lookup"><span data-stu-id="c27b6-112">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="c27b6-113">Você deve configurar tipos de identificação para que você possa inserir informações de identificação para trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="c27b6-113">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="c27b6-114">As informações sobre número do seguro social, número de ID nacional, número de ID do estrangeiro e código de ID pessoal são mantidas na página **Tipo de identificação**.</span><span class="sxs-lookup"><span data-stu-id="c27b6-114">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="c27b6-115">Para definir um novo tipo de identificação ou revisar a lista de tipos existentes, clique em **Gerenciamento de pessoal** &gt; **Guia de links** &gt; **Configuração** &gt; **Tipos de identificação**.</span><span class="sxs-lookup"><span data-stu-id="c27b6-115">To define a new identification type or review the list of existing types, click **Personnel management** &gt; **Links tab** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="c27b6-116">Você pode inserir um código simples e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="c27b6-116">You can enter a simple code and description.</span></span> 

### <a name="if-youre-using-dynamics-365-for-talent"></a><span data-ttu-id="c27b6-117">Se estiver usando o Dynamics 365 for Talent</span><span class="sxs-lookup"><span data-stu-id="c27b6-117">If you're using Dynamics 365 for Talent</span></span>
<span data-ttu-id="c27b6-118">Na guia **Identificação**, selecione os tipos de identificação que representam os números de identificação listados na página.</span><span class="sxs-lookup"><span data-stu-id="c27b6-118">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="c27b6-119">Você deve configurar tipos de identificação para que você possa inserir informações de identificação para trabalhadores.</span><span class="sxs-lookup"><span data-stu-id="c27b6-119">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="c27b6-120">As informações sobre número do seguro social, número de ID nacional, número de ID do estrangeiro e código de ID pessoal são mantidas na página **Tipo de identificação**.</span><span class="sxs-lookup"><span data-stu-id="c27b6-120">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="c27b6-121">Para definir um novo tipo de identificação ou revisar a lista de tipos existentes, clique em **Recursos humanos** &gt; **Configuração** &gt; **Tipos de identificação**.</span><span class="sxs-lookup"><span data-stu-id="c27b6-121">To define a new identification type or review the list of existing types, click **Human resources** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="c27b6-122">Você pode inserir um código simples e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="c27b6-122">You can enter a simple code and description.</span></span> 

<span data-ttu-id="c27b6-123">Na guia **Sequências numéricas**, você pode selecionar as sequências numéricas usadas nos seguintes registros: Número da equipe, Posição, ID da solicitação de usuário, Documento I-9, Candidato, Discussão, ID do Benefício e Ação de pessoal (se esse tipo de registro estiver habilitado).</span><span class="sxs-lookup"><span data-stu-id="c27b6-123">On the **Number sequences** tab, you can select the number sequences that are used for the following records: Personnel number, Position, User request ID, I-9 document, Applicant, Discussion, Benefit ID, and Personnel action (if this record type is enabled).</span></span> <span data-ttu-id="c27b6-124">Para manter as referências e os códigos de sequência numérica, use a página de lista **Sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="c27b6-124">To maintain number sequence references and codes, use the **Number sequences** list page.</span></span> <span data-ttu-id="c27b6-125">Para localizar essa página, use o recurso de pesquisa de página.</span><span class="sxs-lookup"><span data-stu-id="c27b6-125">To find this page, use the page search feature.</span></span> 

<span data-ttu-id="c27b6-126">Na guia **Posições**, indique se as novas posições estão disponíveis para atribuição por padrão:</span><span class="sxs-lookup"><span data-stu-id="c27b6-126">On the **Positions** tab, indicate whether new positions are available for assignment by default:</span></span>

-   <span data-ttu-id="c27b6-127">**Sempre** – Você pode atribuir trabalhadores a novas posições quando estas forem criadas.</span><span class="sxs-lookup"><span data-stu-id="c27b6-127">**Always** – You can assign workers to new positions when positions are created.</span></span> <span data-ttu-id="c27b6-128">Quando as posições são criadas, a data e hora **Disponível para a atribuição** na guia **Geral** da página **Posição** são automaticamente definidas para a data e hora de criação.</span><span class="sxs-lookup"><span data-stu-id="c27b6-128">When positions are created, the **Available for assignment** date and time on the **General** tab of the **Position** page are automatically set to the creation date and time.</span></span>
-   <span data-ttu-id="c27b6-129">**Nunca** – Você não pode atribuir trabalhadores a novas posições quando estas forem criadas.</span><span class="sxs-lookup"><span data-stu-id="c27b6-129">**Never** – You can't assign workers to new positions when positions are created.</span></span> <span data-ttu-id="c27b6-130">Se você selecionar essa opção, precisará abrir a página **Posição** para cada nova posição à medida que ela for disponibilizada. Em seguida, na guia **Geral**, insira **Disponível para atribuição** para habilitar a atribuição de trabalhador.</span><span class="sxs-lookup"><span data-stu-id="c27b6-130">If you select this option, you must open the **Position** page for each new position as it becomes available, and then, on the **General** tab, enter the **Available for assignment** date to enable worker assignment.</span></span>


<a name="see-also"></a><span data-ttu-id="c27b6-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c27b6-131">See also</span></span>
--------

[<span data-ttu-id="c27b6-132">Configurar parâmetros de RH específicos da empresa</span><span class="sxs-lookup"><span data-stu-id="c27b6-132">Set up company specific HR parameters</span></span>](set-up-company-specific-hr-parameters.md)




