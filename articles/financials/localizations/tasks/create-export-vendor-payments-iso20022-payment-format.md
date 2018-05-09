--- 
title: Criar e exportar pagamentos de fornecedores usando o formato de pagamento ISO20022
description: "Este procedimento mostra como criar linhas de pagamento no diário de pagamentos do fornecedor e gerar um arquivo de pagamento de fornecedor usando o exemplo de Transferência de Crédito ISO2022."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 906f9611370e19ad4f063d15608d3564c5292c96
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="249c7-103">Criar e exportar pagamentos de fornecedores usando o formato de pagamento ISO20022</span><span class="sxs-lookup"><span data-stu-id="249c7-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="249c7-104">Este procedimento mostra como criar linhas de pagamento no diário de pagamentos do fornecedor e gerar um arquivo de pagamento de fornecedor usando o exemplo de Transferência de Crédito ISO2022.</span><span class="sxs-lookup"><span data-stu-id="249c7-104">This procedure shows how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span> 

<span data-ttu-id="249c7-105">A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.</span><span class="sxs-lookup"><span data-stu-id="249c7-105">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="249c7-106">Este é o quinto dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="249c7-106">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="249c7-107">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="249c7-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-payment-lines"></a><span data-ttu-id="249c7-108">Criar linhas de pagamento</span><span class="sxs-lookup"><span data-stu-id="249c7-108">Create payment lines</span></span>
1. <span data-ttu-id="249c7-109">Vá para Contas a pagar > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="249c7-109">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="249c7-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="249c7-110">Click New.</span></span>
3. <span data-ttu-id="249c7-111">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="249c7-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="249c7-112">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="249c7-112">In the Name field, enter or select a value.</span></span>
5. <span data-ttu-id="249c7-113">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="249c7-113">Click Lines.</span></span>
6. <span data-ttu-id="249c7-114">Clique em Proposta de pagamento.</span><span class="sxs-lookup"><span data-stu-id="249c7-114">Click Payment proposal.</span></span>
7. <span data-ttu-id="249c7-115">Clique em Criar proposta de pagamento.</span><span class="sxs-lookup"><span data-stu-id="249c7-115">Click Create payment proposal.</span></span>
8. <span data-ttu-id="249c7-116">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="249c7-116">Expand the Records to include section.</span></span>
9. <span data-ttu-id="249c7-117">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="249c7-117">Click Filter.</span></span>
10. <span data-ttu-id="249c7-118">Na lista, selecione a linha para Tabela de fornecedores e o campo Conta de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="249c7-118">In the list, select the row for Vendors table and Vendor account field.</span></span>
11. <span data-ttu-id="249c7-119">No campo Critérios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="249c7-119">In the Criteria field, enter or select a value.</span></span>
    * <span data-ttu-id="249c7-120">Você pode aplicar quaisquer critérios para selecionar transações de fornecedor para pagamento. Para este exemplo, use DE-001 como uma conta de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="249c7-120">You can apply any criteria for selecting vendor transactions to pay, for this example use DE-001 as a vendor account.</span></span>  
12. <span data-ttu-id="249c7-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="249c7-121">Click OK.</span></span>
13. <span data-ttu-id="249c7-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="249c7-122">Click OK.</span></span>
14. <span data-ttu-id="249c7-123">Clique em Criar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="249c7-123">Click Create payments.</span></span>

## <a name="generate-an-iso20022-payment-file"></a><span data-ttu-id="249c7-124">Gerar um arquivo de pagamento ISO20022</span><span class="sxs-lookup"><span data-stu-id="249c7-124">Generate an ISO20022 payment file</span></span>


