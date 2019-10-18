---
title: Atualizar a entidade composta do diário de banco
description: Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 974d6b3b11df92debdec26860fd9eea00a9f2313
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188018"
---
# <a name="update-the-bank-journal-composite-entity"></a><span data-ttu-id="daf58-103">Atualizar a entidade composta do diário de banco</span><span class="sxs-lookup"><span data-stu-id="daf58-103">Update the bank journal composite entity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="daf58-104">Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.</span><span class="sxs-lookup"><span data-stu-id="daf58-104">The following steps are needed in order to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

<span data-ttu-id="daf58-105">Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.</span><span class="sxs-lookup"><span data-stu-id="daf58-105">Use the following steps to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

1.  <span data-ttu-id="daf58-106">Compilar e sincronize as entidades compostas o próximo diário bancárias, entidades, preparar e tabelas:</span><span class="sxs-lookup"><span data-stu-id="daf58-106">Compile and synchronize the following bank journal composite entities, entities, and staging tables:</span></span>
    -   <span data-ttu-id="daf58-107">Entidade Composta\\BankJournalEntity</span><span class="sxs-lookup"><span data-stu-id="daf58-107">Composite Entity\\BankJournalEntity</span></span>
    -   <span data-ttu-id="daf58-108">Entidade\\BankJournalHeaderEntity</span><span class="sxs-lookup"><span data-stu-id="daf58-108">Entity\\BankJournalHeaderEntity</span></span>
    -   <span data-ttu-id="daf58-109">Entidade\\BankJournalLineEntity</span><span class="sxs-lookup"><span data-stu-id="daf58-109">Entity\\BankJournalLineEntity</span></span>
    -   <span data-ttu-id="daf58-110">Tabela\\BankJournalHeaderStaging</span><span class="sxs-lookup"><span data-stu-id="daf58-110">Table\\BankJournalHeaderStaging</span></span>
    -   <span data-ttu-id="daf58-111">Tabela\\BankJournalLineStaging</span><span class="sxs-lookup"><span data-stu-id="daf58-111">Table\\BankJournalLineStaging</span></span>

2.  <span data-ttu-id="daf58-112">Gerenciamento de dados\\projetos de dados</span><span class="sxs-lookup"><span data-stu-id="daf58-112">Data management\\data projects</span></span>
    -   <span data-ttu-id="daf58-113">O tipo **Transação bancária**expõe o layout **Dados de origem**.</span><span class="sxs-lookup"><span data-stu-id="daf58-113">Expose the **Bank Transaction** type on **Source Data** layout.</span></span>
        -   <span data-ttu-id="daf58-114">Formato de dados fonte = elemento XML</span><span class="sxs-lookup"><span data-stu-id="daf58-114">Source data format = XML-Element</span></span>
        -   <span data-ttu-id="daf58-115">Nome da entidade = Diário bancário</span><span class="sxs-lookup"><span data-stu-id="daf58-115">Entity name = Bank Journal</span></span>
        -   <span data-ttu-id="daf58-116">Baixar arquivo de dados = nova versão de SampleBankJournalCompositeEntity.xml</span><span class="sxs-lookup"><span data-stu-id="daf58-116">Upload data file = new version SampleBankJournalCompositeEntity.xml</span></span>
        -   <span data-ttu-id="daf58-117">Clique em **Sim** para substituir o arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="daf58-117">Click **Yes** to overwrite the existing file.</span></span>
        -   <span data-ttu-id="daf58-118">Clique em **Sim** para gerar um novo mapeamento.</span><span class="sxs-lookup"><span data-stu-id="daf58-118">Click **Yes** to generate mapping from scratch.</span></span>
        -   <span data-ttu-id="daf58-119">Verifique se o tipo de transação bancária está mapeado.</span><span class="sxs-lookup"><span data-stu-id="daf58-119">Verify that the Bank Transaction Type is mapped.</span></span>
            -   <span data-ttu-id="daf58-120">Clique em **Exibir mapa** na linha Entidade.</span><span class="sxs-lookup"><span data-stu-id="daf58-120">Click **View map** on Line entity.</span></span>
            -   <span data-ttu-id="daf58-121">Verifique se o tipo de transação bancária está mapeado de origem para se preparar.</span><span class="sxs-lookup"><span data-stu-id="daf58-121">Verify that Bank Transaction type is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="daf58-122">Importe o novo demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="daf58-122">Import the new statement.</span></span>




