---
title: Criar uma conta bancária de fornecedor
description: Este procedimento mostra como criar uma conta de banco para um fornecedor.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, LogisticsPostalAddressSingle
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: deb3587667ac13b95617ec219995bfef931df00c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "360615"
---
# <a name="create-a-vendor-bank-account"></a><span data-ttu-id="c6b82-103">Criar uma conta bancária de fornecedor</span><span class="sxs-lookup"><span data-stu-id="c6b82-103">Create a vendor bank account</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c6b82-104">Este procedimento mostra como criar uma conta de banco para um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-104">This procedure shows you how to create a bank account for a vendor.</span></span> <span data-ttu-id="c6b82-105">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="c6b82-105">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="c6b82-106">Vá para Aquisição e fornecimento > Fornecedores > Todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="c6b82-106">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="c6b82-107">Selecione o vendedor para o qual você quer criar uma conta bancária, e clique então no link de identificação da conta do vendedor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-107">Select the vendor that you want to create a bank account for, and then click the link on the Vendor account ID.</span></span>
3. <span data-ttu-id="c6b82-108">No Painel de Ação, clique em Fornecedor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-108">On the Action Pane, click Vendor.</span></span>
4. <span data-ttu-id="c6b82-109">Clique em Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="c6b82-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="c6b82-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c6b82-110">Click New.</span></span>
6. <span data-ttu-id="c6b82-111">No campo Conta bancária, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-111">In the Bank account field, type a value.</span></span>
    * <span data-ttu-id="c6b82-112">Esta identificação será usada para identificar a conta bancária no registro do vendedor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-112">This ID will be used to identify the bank account on the vendor record.</span></span>  
7. <span data-ttu-id="c6b82-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="c6b82-114">No campo Grupos de banco, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-114">In the Bank groups field, enter or select a value.</span></span>
9. <span data-ttu-id="c6b82-115">No campo Tipo de número de roteiro, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="c6b82-115">In the Routing number type field, select an option.</span></span>
    * <span data-ttu-id="c6b82-116">Este é o tipo do número de roteamento usado para pagamentos internacionais.</span><span class="sxs-lookup"><span data-stu-id="c6b82-116">This is the type of routing number that’s used for international payments.</span></span>  
10. <span data-ttu-id="c6b82-117">No campo Número da conta bancária, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-117">In the Bank account number field, type a value.</span></span>
11. <span data-ttu-id="c6b82-118">No campo Código SWIFT, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-118">In the SWIFT code field, type a value.</span></span>
12. <span data-ttu-id="c6b82-119">No campo IBAN, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-119">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="c6b82-120">O número de IBAN deve estar no formato correto.</span><span class="sxs-lookup"><span data-stu-id="c6b82-120">The IBAN number must be in the correct format.</span></span> <span data-ttu-id="c6b82-121">Por exemplo, é possível usar o DE89370400440532013000.</span><span class="sxs-lookup"><span data-stu-id="c6b82-121">For example, you could use DE89370400440532013000.</span></span>  
    * <span data-ttu-id="c6b82-122">O estado da conta bancária é ativo se a data ativa foi alcançada, e a data de validade não esteve excedida.</span><span class="sxs-lookup"><span data-stu-id="c6b82-122">The status of the bank account is Active if the Active date has been reached, and the Expiration date has not been exceeded.</span></span> <span data-ttu-id="c6b82-123">É igualmente ativa se a data ativa e os campos da data de validade estão vazios.</span><span class="sxs-lookup"><span data-stu-id="c6b82-123">It’s also active if both the Active date and Expiration date fields are blank.</span></span> <span data-ttu-id="c6b82-124">Se as datas nos campos Data ativa e Data de vencimento ocorrerem no futuro, os pagamentos eletrônicos não estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c6b82-124">If the dates in both the Active date and Expiration date fields are in the future electronic payments are not available.</span></span> <span data-ttu-id="c6b82-125">Outros tipos de pagamentos estarão disponíveis e a conta bancária estará ativa.</span><span class="sxs-lookup"><span data-stu-id="c6b82-125">Other payment types are available and the bank account is active.</span></span>  
13. <span data-ttu-id="c6b82-126">Expandir a seção Instalação.</span><span class="sxs-lookup"><span data-stu-id="c6b82-126">Expand the Setup section.</span></span>
14. <span data-ttu-id="c6b82-127">No campo Código de texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-127">In the Text code field, type a value.</span></span>
    * <span data-ttu-id="c6b82-128">Este campo especifica um código que aparece na indicação de banco do receptor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-128">This field specifies a code that will appear on the bank statement of the recipient.</span></span>  
15. <span data-ttu-id="c6b82-129">No campo Mensagem ao banco, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-129">In the Message to bank field, type a value.</span></span>
16. <span data-ttu-id="c6b82-130">No campo Referência de troca, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-130">In the Exchange reference field, type a value.</span></span>
    * <span data-ttu-id="c6b82-131">Este é o número de referência de qualquer taxa de câmbio futuro ou de prazo fixo.</span><span class="sxs-lookup"><span data-stu-id="c6b82-131">This is the reference number for any forward-term or fixed-term rate of exchange.</span></span>  
17. <span data-ttu-id="c6b82-132">No campo Moeda, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-132">In the Currency field, enter or select a value.</span></span>
    * <span data-ttu-id="c6b82-133">Quando as pré-notas são emitidas, esta seção fornece uma visão geral de seu estado (pendente ou aprovado).</span><span class="sxs-lookup"><span data-stu-id="c6b82-133">When prenotes are issued, this section provides an overview of their status (pending or approved).</span></span>  
18. <span data-ttu-id="c6b82-134">Expanda a seção Endereço.</span><span class="sxs-lookup"><span data-stu-id="c6b82-134">Expand the Address section.</span></span>
19. <span data-ttu-id="c6b82-135">Expandir a seção Pré-notas.</span><span class="sxs-lookup"><span data-stu-id="c6b82-135">Expand the Prenotes section.</span></span>
20. <span data-ttu-id="c6b82-136">Expandir a seção Informações de contato.</span><span class="sxs-lookup"><span data-stu-id="c6b82-136">Expand the Contact information section.</span></span>
21. <span data-ttu-id="c6b82-137">No campo Telefone, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6b82-137">In the Telephone field, type a value.</span></span>
22. <span data-ttu-id="c6b82-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6b82-138">Close the page.</span></span>
23. <span data-ttu-id="c6b82-139">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="c6b82-139">Click Edit.</span></span>
24. <span data-ttu-id="c6b82-140">Expandir a seção Pagamento.</span><span class="sxs-lookup"><span data-stu-id="c6b82-140">Expand the Payment section.</span></span>
25. <span data-ttu-id="c6b82-141">No campo da conta bancária, selecione a conta que você apenas criou.</span><span class="sxs-lookup"><span data-stu-id="c6b82-141">In the Bank  account field, select the account that you’ve just created.</span></span>
26. <span data-ttu-id="c6b82-142">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c6b82-142">Click Save.</span></span>
    * <span data-ttu-id="c6b82-143">O endereço pode ser herdado do grupo do banco, se for um especificado, ou você pode adicioná-lo aqui.</span><span class="sxs-lookup"><span data-stu-id="c6b82-143">The address may be inherited from the bank group, if one is specified, or you can add it here.</span></span>  

