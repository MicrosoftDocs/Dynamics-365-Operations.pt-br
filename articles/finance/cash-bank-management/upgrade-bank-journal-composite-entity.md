---
title: Atualizar a entidade composta do diário de banco
description: Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 7e265915cf3f53a8243788b50a9374d521efbbae
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819593"
---
# <a name="update-the-bank-journal-composite-entity"></a><span data-ttu-id="0c706-103">Atualizar a entidade composta do diário de banco</span><span class="sxs-lookup"><span data-stu-id="0c706-103">Update the bank journal composite entity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0c706-104">Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.</span><span class="sxs-lookup"><span data-stu-id="0c706-104">The following steps are needed in order to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

<span data-ttu-id="0c706-105">Siga as etapas abaixo para adicionar um campo adicional de BankTransactionType a BankJournalEntity composto.</span><span class="sxs-lookup"><span data-stu-id="0c706-105">Use the following steps to add the additional BankTransactionType field to the composite BankJournalEntity.</span></span>

1.  <span data-ttu-id="0c706-106">Compilar e sincronize as entidades compostas o próximo diário bancárias, entidades, preparar e tabelas:</span><span class="sxs-lookup"><span data-stu-id="0c706-106">Compile and synchronize the following bank journal composite entities, entities, and staging tables:</span></span>
    -   <span data-ttu-id="0c706-107">Entidade Composta\\BankJournalEntity</span><span class="sxs-lookup"><span data-stu-id="0c706-107">Composite Entity\\BankJournalEntity</span></span>
    -   <span data-ttu-id="0c706-108">Entidade\\BankJournalHeaderEntity</span><span class="sxs-lookup"><span data-stu-id="0c706-108">Entity\\BankJournalHeaderEntity</span></span>
    -   <span data-ttu-id="0c706-109">Entidade\\BankJournalLineEntity</span><span class="sxs-lookup"><span data-stu-id="0c706-109">Entity\\BankJournalLineEntity</span></span>
    -   <span data-ttu-id="0c706-110">Tabela\\BankJournalHeaderStaging</span><span class="sxs-lookup"><span data-stu-id="0c706-110">Table\\BankJournalHeaderStaging</span></span>
    -   <span data-ttu-id="0c706-111">Tabela\\BankJournalLineStaging</span><span class="sxs-lookup"><span data-stu-id="0c706-111">Table\\BankJournalLineStaging</span></span>

2.  <span data-ttu-id="0c706-112">Gerenciamento de dados\\projetos de dados</span><span class="sxs-lookup"><span data-stu-id="0c706-112">Data management\\data projects</span></span>
    -   <span data-ttu-id="0c706-113">O tipo **Transação bancária** expõe o layout **Dados de origem**.</span><span class="sxs-lookup"><span data-stu-id="0c706-113">Expose the **Bank Transaction** type on **Source Data** layout.</span></span>
        -   <span data-ttu-id="0c706-114">Formato de dados fonte = elemento XML</span><span class="sxs-lookup"><span data-stu-id="0c706-114">Source data format = XML-Element</span></span>
        -   <span data-ttu-id="0c706-115">Nome da entidade = Diário bancário</span><span class="sxs-lookup"><span data-stu-id="0c706-115">Entity name = Bank Journal</span></span>
        -   <span data-ttu-id="0c706-116">Baixar arquivo de dados = nova versão de SampleBankJournalCompositeEntity.xml</span><span class="sxs-lookup"><span data-stu-id="0c706-116">Upload data file = new version SampleBankJournalCompositeEntity.xml</span></span>
        -   <span data-ttu-id="0c706-117">Clique em **Sim** para substituir o arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="0c706-117">Click **Yes** to overwrite the existing file.</span></span>
        -   <span data-ttu-id="0c706-118">Clique em **Sim** para gerar um novo mapeamento.</span><span class="sxs-lookup"><span data-stu-id="0c706-118">Click **Yes** to generate mapping from scratch.</span></span>
        -   <span data-ttu-id="0c706-119">Verifique se o tipo de transação bancária está mapeado.</span><span class="sxs-lookup"><span data-stu-id="0c706-119">Verify that the Bank Transaction Type is mapped.</span></span>
            -   <span data-ttu-id="0c706-120">Clique em **Exibir mapa** na linha Entidade.</span><span class="sxs-lookup"><span data-stu-id="0c706-120">Click **View map** on Line entity.</span></span>
            -   <span data-ttu-id="0c706-121">Verifique se o tipo de transação bancária está mapeado de origem para se preparar.</span><span class="sxs-lookup"><span data-stu-id="0c706-121">Verify that Bank Transaction type is mapped from Source to Staging.</span></span>

3.  <span data-ttu-id="0c706-122">Importe o novo demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="0c706-122">Import the new statement.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]