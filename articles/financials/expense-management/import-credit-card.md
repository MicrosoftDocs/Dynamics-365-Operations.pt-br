---
title: "Importar e manter transações de cartão de crédito"
description: "Este tópico explica como importar e manter as transações de cartão de crédito relacionadas a despesa. Essas transações podem ser configuradas de forma que sejam importadas automaticamente em uma agenda recorrente ou podem ser importadas manualmente, conforme necessário."
author: KimANelson
manager: AnnBe
ms.date: 08/29/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e640c9e44add5599be4a2e381b4ffd81f212889c
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="import-and-maintain-credit-card-transactions"></a><span data-ttu-id="ce9a2-104">Importar e manter transações de cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="ce9a2-104">Import and maintain credit card transactions</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ce9a2-105">As transações de cartão de crédito relacionadas à despesa podem ser configuradas de forma que possam ser importadas automaticamente em uma agenda recorrente.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-105">Expense-related credit card transactions can be set up so that they are automatically imported on a recurring schedule.</span></span> <span data-ttu-id="ce9a2-106">Como alternativa, as transações podem ser importadas manualmente, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-106">Alternatively, the transactions can be manually imported as they are required.</span></span> <span data-ttu-id="ce9a2-107">As transações de cartão de crédito são importadas por meio da entidade de dados das transações de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-107">The credit card transactions are imported through the Credit card transactions data entity.</span></span>

<span data-ttu-id="ce9a2-108">Para obter mais informações sobre as entidades de dados, consulte [Entidades de dados](../../dev-itpro/data-entities/data-entities.md).</span><span class="sxs-lookup"><span data-stu-id="ce9a2-108">For more information about data entities, see [Data entities](../../dev-itpro/data-entities/data-entities.md).</span></span>

## <a name="import-credit-card-transactions"></a><span data-ttu-id="ce9a2-109">Importar transações de cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="ce9a2-109">Import credit card transactions</span></span>

1. <span data-ttu-id="ce9a2-110">Na página **Transações de cartão de crédito** , selecione **Transações de importação**.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-110">On the **Credit card transactions** page, select **Import transactions**.</span></span> <span data-ttu-id="ce9a2-111">Se estiver abrindo o gerenciamento de dados pela primeira vez, o sistema deve atualizar a lista de entidades de dados antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-111">If you’re opening data management for the first time, the system must update the list of data entities before you can continue.</span></span>
2. <span data-ttu-id="ce9a2-112">No campo **Nome**, insira uma descrição exclusiva da tarefa de importação.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-112">In the **Name** field, enter a unique description of the import job.</span></span>
3. <span data-ttu-id="ce9a2-113">No campo **Formato de dados de origem**, selecione o formato do arquivo que contém as transações do cartão de crédito para importação.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-113">In the **Source data format** field, select the format of the file that contains the credit card transactions to import.</span></span>
4. <span data-ttu-id="ce9a2-114">Selecione **Carregar** e, em seguida, localize e selecione o arquivo a ser importado.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-114">Select **Upload**, and then find and select the file to import.</span></span>
5. <span data-ttu-id="ce9a2-115">Depois que o arquivo for carregado, valide o mapeamento do arquivo da transação de cartão de crédito e as colunas da entidade de dados das transações de cartão de crédito, selecionando o link **Exibir mapa** no bloco.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-115">After the file has been uploaded, validate the mapping of the credit card transaction file and the columns of the Credit card transactions data entity by selecting the **View map** link on the tile.</span></span> <span data-ttu-id="ce9a2-116">Se houver erros de mapeamento ou se você tiver que alterar o mapeamento, faça as alterações de mapeamento da guia **Visualização de mapeamento** ou na guia **Detalhes de mapeamento**.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-116">If there are mapping errors, or if you must change the mapping, make the mapping changes from either the **Mapping visualization** tab or the **Mapping details** tab.</span></span>
6. <span data-ttu-id="ce9a2-117">Para automatizar as transações de cartão de crédito, selecione **Criar trabalho de dados recorrente**.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-117">To automate the credit card transactions, select **Create recurring data job**.</span></span> <span data-ttu-id="ce9a2-118">Você poderá então definir a recorrência que define a frequência na qual as transações de cartão de crédito devem ser importadas.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-118">You can then set the recurrence that defines how often credit card transactions should be imported.</span></span> <span data-ttu-id="ce9a2-119">Quando terminar, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-119">When you’ve finished, select **OK**.</span></span>
7. <span data-ttu-id="ce9a2-120">Para importar o arquivo selecionado agora, selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-120">To import the selected file now, select **Import**.</span></span>
8. <span data-ttu-id="ce9a2-121">Se houver erros durante a importação, é possível exibir o log de execução ou dados de preparo para ver os erros que você deve corrigir para garantir uma importação bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-121">If errors occur during the import, you can view the execution log or staging data to see the errors that you must fix to help guarantee a successful import.</span></span>

> [!NOTE]
> <span data-ttu-id="ce9a2-122">Se tiver que importar mais de um formato de arquivo, é necessário criar trabalhos de importação separados para cada tipo de formato.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-122">If you must import more than one file format, you must create separate import jobs for each format type.</span></span>

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a><span data-ttu-id="ce9a2-123">Reatribuir as transações de cartão de crédito de funcionários demitidos.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-123">Reassign the credit card transactions for terminated employees</span></span>

<span data-ttu-id="ce9a2-124">Depois que um registro de funcionário foi finalizado, a conta Serviços de domínio Active Directory (AD DS) do funcionário é desativada.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-124">After an employee record is terminated, the employee’s Active Directory Domain Services (AD DS) account is disabled.</span></span> <span data-ttu-id="ce9a2-125">Porém, pode haver transações de cartão de crédito ativa que ainda devem ser despendidas e reembolsadas.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-125">However, there might be active credit card transactions that must still be expensed and reimbursed.</span></span> <span data-ttu-id="ce9a2-126">Na página **Crédito e transações**, é possível reatribuir o funcionário de qualquer transação de cartão de crédito na qual o funcionário associado foi demitido.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-126">From the **Credit card transactions** page, you can reassign the employee for any credit card transaction where the associated employee has been terminated.</span></span>

<span data-ttu-id="ce9a2-127">Selecione uma ou mais transações de cartão de crédito e depois selecione **Reatribuir transações**.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-127">Select one or more credit card transactions, and then select **Reassign transactions**.</span></span> <span data-ttu-id="ce9a2-128">Você pode selecionar outro funcionário para atribuir as transações do cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-128">You can then select another employee to assign the credit card transactions to.</span></span> <span data-ttu-id="ce9a2-129">Depois que as transações do cartão de crédito forem reatribuídas, elas poderão ser selecionadas de um relatório de despesas e pagas pelo processo comum para reembolso do relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="ce9a2-129">After the credit card transactions have been reassigned, they can be selected for an expense report and paid through the usual process for expense report reimbursement.</span></span>

