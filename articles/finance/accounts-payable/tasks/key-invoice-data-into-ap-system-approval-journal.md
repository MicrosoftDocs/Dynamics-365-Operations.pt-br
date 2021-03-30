---
title: Dados-chave de fatura em contas a pagar usando um diário de aprovações
description: Este tópico explica como usar o registro de fatura para criar faturas e usar no diário de aprovações para atualizar as contas de despesas.
author: abruer
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f0fee32d9fd1ab89b1a8cedb2e1965674586d4e7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227175"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="5867b-103">Dados-chave de fatura em contas a pagar usando um diário de aprovações</span><span class="sxs-lookup"><span data-stu-id="5867b-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5867b-104">Este tópico explica como usar o registro de fatura para criar faturas e usar no diário de aprovações para atualizar as contas de despesas.</span><span class="sxs-lookup"><span data-stu-id="5867b-104">This topic explains how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="5867b-105">Criar e lançar e faturar</span><span class="sxs-lookup"><span data-stu-id="5867b-105">Create and post and invoice</span></span>
1. <span data-ttu-id="5867b-106">No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Registro de faturas**.</span><span class="sxs-lookup"><span data-stu-id="5867b-106">In the navigation pan, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="5867b-107">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5867b-107">Select **New**.</span></span>
3. <span data-ttu-id="5867b-108">Selecione o nome do registro de fatura que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="5867b-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="5867b-109">Selecione **Linhas** para abrir o registro e inserir as linhas de despesa.</span><span class="sxs-lookup"><span data-stu-id="5867b-109">Select **Lines** to open the register and enter expense lines.</span></span>
5. <span data-ttu-id="5867b-110">Selecione um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5867b-110">Select a vendor.</span></span> <span data-ttu-id="5867b-111">Por exemplo, digite ou selecione `US-104`.</span><span class="sxs-lookup"><span data-stu-id="5867b-111">For example, enter or select `US-104`.</span></span>
6. <span data-ttu-id="5867b-112">No campo **Fatura**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5867b-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="5867b-113">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5867b-113">In the **Description** field, type a value.</span></span>
8. <span data-ttu-id="5867b-114">No campo **Crédito**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="5867b-114">In the **Credit** field, enter a number.</span></span>
9. <span data-ttu-id="5867b-115">No campo **Aprovado por**, selecione um aprovador do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="5867b-115">In the **Approved by** field, select an approver from the drop-down menu.</span></span>
10. <span data-ttu-id="5867b-116">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="5867b-116">Select **Post**.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="5867b-117">Aprovar uma fatura</span><span class="sxs-lookup"><span data-stu-id="5867b-117">Approve an invoice</span></span>
1. <span data-ttu-id="5867b-118">No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Aprovação da fatura**.</span><span class="sxs-lookup"><span data-stu-id="5867b-118">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice approval**.</span></span>
2. <span data-ttu-id="5867b-119">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5867b-119">Select **New**.</span></span>
3. <span data-ttu-id="5867b-120">Selecione o nome do diário de aprovação de fatura que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="5867b-120">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="5867b-121">Selecione **Linhas** para exibir a página na qual você poderá selecionar as faturas que deseja aprovar.</span><span class="sxs-lookup"><span data-stu-id="5867b-121">Select **Lines** to display a page where you will be able to select the invoices that you want to approve.</span></span>
5. <span data-ttu-id="5867b-122">Selecione **Localizar comprovantes** para exibir todas as faturas que estão prontas para aprovação.</span><span class="sxs-lookup"><span data-stu-id="5867b-122">Select **Find Vouchers** to display all of the invoices that are ready for approval.</span></span>
6. <span data-ttu-id="5867b-123">Marque a fatura que criou, depois clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="5867b-123">Mark the invoice that you created, then click **Select**.</span></span> <span data-ttu-id="5867b-124">Os comprovantes que tiver selecionado acima são movidos para esta lista depois que você os seleciona.</span><span class="sxs-lookup"><span data-stu-id="5867b-124">The vouchers that you selected above are moved to this list after you select them.</span></span>  
7. <span data-ttu-id="5867b-125">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5867b-125">Select **OK**.</span></span>
8. <span data-ttu-id="5867b-126">Selecione o campo **número da conta** para adicionar uma conta de despesa à fatura.</span><span class="sxs-lookup"><span data-stu-id="5867b-126">Select the **account number** field to add an expense account to the invoice.</span></span>
9. <span data-ttu-id="5867b-127">Insira um número de conta e desmarque o campo.</span><span class="sxs-lookup"><span data-stu-id="5867b-127">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="5867b-128">Por exemplo, insira `600120`.</span><span class="sxs-lookup"><span data-stu-id="5867b-128">For example, enter `600120`.</span></span>
10. <span data-ttu-id="5867b-129">Selecione **Lançar**.</span><span class="sxs-lookup"><span data-stu-id="5867b-129">Select **Post**.</span></span>
11. <span data-ttu-id="5867b-130">Selecione **Comprovante** para exibir as entradas lançadas.</span><span class="sxs-lookup"><span data-stu-id="5867b-130">Select **Voucher** to view the entries that were posted.</span></span> <span data-ttu-id="5867b-131">A nota fiscal durante a conta de aprovação é revertida e substituída pela conta de despesa real.</span><span class="sxs-lookup"><span data-stu-id="5867b-131">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]