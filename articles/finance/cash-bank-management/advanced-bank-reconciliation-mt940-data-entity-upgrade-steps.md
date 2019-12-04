---
title: Importação MT940 de reconciliação bancária avançada – Atualização de entidade de dados composta
description: Necessidades de uma sequência numérica de ser adicionada à entidade de extrato bancário para oferecer suporte ao formato MT940.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221594
ms.assetid: dddc99ae-56ae-48df-856a-131079c17dcb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 91100c3e3c33462e5b19ca239a784cdb720210ab
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771998"
---
# <a name="advanced-bank-reconciliation-mt940-import--composite-data-entity-upgrade"></a><span data-ttu-id="c1a58-103">Importação MT940 de reconciliação bancária avançada – Atualização de entidade de dados composta</span><span class="sxs-lookup"><span data-stu-id="c1a58-103">Advanced bank reconciliation MT940 Import – Composite data entity upgrade</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1a58-104">Necessidades de uma sequência numérica de ser adicionada à entidade de extrato bancário para oferecer suporte ao formato MT940.</span><span class="sxs-lookup"><span data-stu-id="c1a58-104">A sequence number needs to be added to the bank statement import entity to support the MT940 format.</span></span> 

<span data-ttu-id="c1a58-105">Siga as etapas abaixo para adicionar a entidade de extrato bancário para oferecer suporte ao formato MT940.</span><span class="sxs-lookup"><span data-stu-id="c1a58-105">Use the following steps to add the bank statement import entity to support the MT940 format.</span></span>

1.  <span data-ttu-id="c1a58-106">Compilar e sincronizar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1a58-106">Compile and synchronize the following:</span></span>
    -   <span data-ttu-id="c1a58-107">Entidade composta\\BankStatementImportEntity</span><span class="sxs-lookup"><span data-stu-id="c1a58-107">Composite Entity\\BankStatementImportEntity</span></span>
    -   <span data-ttu-id="c1a58-108">Entidade\\BankStatementBalanceEntity</span><span class="sxs-lookup"><span data-stu-id="c1a58-108">Entity\\BankStatementBalanceEntity</span></span>
    -   <span data-ttu-id="c1a58-109">Entidade\\BankStatementDocumentEntity</span><span class="sxs-lookup"><span data-stu-id="c1a58-109">Entity\\BankStatementDocumentEntity</span></span>
    -   <span data-ttu-id="c1a58-110">Entidade\\BankStatementEntity</span><span class="sxs-lookup"><span data-stu-id="c1a58-110">Entity\\BankStatementEntity</span></span>
    -   <span data-ttu-id="c1a58-111">Entidade\\BankStatementLineEntity</span><span class="sxs-lookup"><span data-stu-id="c1a58-111">Entity\\BankStatementLineEntity</span></span>
    -   <span data-ttu-id="c1a58-112">Tabelas\\BankStatementStaging</span><span class="sxs-lookup"><span data-stu-id="c1a58-112">Tables\\BankStatementStaging</span></span>

2.  <span data-ttu-id="c1a58-113">Projetos de dados\\gerenciamento de dados.</span><span class="sxs-lookup"><span data-stu-id="c1a58-113">Data management\\data projects.</span></span>
    1.  <span data-ttu-id="c1a58-114">Projetos de importação de carga MT940</span><span class="sxs-lookup"><span data-stu-id="c1a58-114">Load MT940 import project(s)</span></span>
        1.  <span data-ttu-id="c1a58-115">Alterar XSLT.</span><span class="sxs-lookup"><span data-stu-id="c1a58-115">Change XSLT.</span></span>
            -   <span data-ttu-id="c1a58-116">Clique em **Exibir mapa**.</span><span class="sxs-lookup"><span data-stu-id="c1a58-116">Click **View map**.</span></span>
            -   <span data-ttu-id="c1a58-117">Clique **Mapa de exibição** sobre o documento do extrato bancário.</span><span class="sxs-lookup"><span data-stu-id="c1a58-117">Click **View map** on the bank statement document.</span></span>
            -   <span data-ttu-id="c1a58-118">Clique em **Transformações**</span><span class="sxs-lookup"><span data-stu-id="c1a58-118">Click **Transformations**</span></span>
            -   <span data-ttu-id="c1a58-119">Exclua o arquivo de BankReconiliation-to-Composite.xslt.</span><span class="sxs-lookup"><span data-stu-id="c1a58-119">Delete the BankReconiliation-to-Composite.xslt file.</span></span>
            -   <span data-ttu-id="c1a58-120">Adicionar a nova versão de BankReconiliation-to-Composite.xsl.</span><span class="sxs-lookup"><span data-stu-id="c1a58-120">Add the new version of BankReconiliation-to-Composite.xsl.</span></span>

        2.  <span data-ttu-id="c1a58-121">Exponha o layout **Número de sequência** em **Dados fonte**.</span><span class="sxs-lookup"><span data-stu-id="c1a58-121">Expose the **Sequence Number** on **Source Data** layout.</span></span>
            1.  <span data-ttu-id="c1a58-122">Formato de dados fonte = elemento XML.</span><span class="sxs-lookup"><span data-stu-id="c1a58-122">Source data format = XML-Element.</span></span>
            2.  <span data-ttu-id="c1a58-123">Nome da entidade = Extratos bancários.</span><span class="sxs-lookup"><span data-stu-id="c1a58-123">Entity name = Bank statements.</span></span>
            3.  <span data-ttu-id="c1a58-124">Baixar arquivo de dados = nova versão de SampleBankCompositeEntity.xml.</span><span class="sxs-lookup"><span data-stu-id="c1a58-124">Upload data file = new version SampleBankCompositeEntity.xml.</span></span>
            4.  <span data-ttu-id="c1a58-125">Clique em **Sim** para substituir o arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="c1a58-125">Click **Yes** to overwrite the existing file.</span></span>
            5.  <span data-ttu-id="c1a58-126">Clique em **Sim** para gerar um novo mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c1a58-126">Click **Yes** to generate a new mapping.</span></span>
            6.  <span data-ttu-id="c1a58-127">Verifique se S**equenceNumber** está mapeado.</span><span class="sxs-lookup"><span data-stu-id="c1a58-127">Verify that S**equenceNumber** is mapped.</span></span>
                -   <span data-ttu-id="c1a58-128">Clique **Mapa de exibição** sobre a entidade do extrato.</span><span class="sxs-lookup"><span data-stu-id="c1a58-128">Click **View Map** on the statement entity.</span></span>
                -   <span data-ttu-id="c1a58-129">Verifique se **SequenceNumber** está mapeado de origem para se preparar.</span><span class="sxs-lookup"><span data-stu-id="c1a58-129">Verify that **SequenceNumber** is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="c1a58-130">Importe o novo demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="c1a58-130">Import the new statement.</span></span>



