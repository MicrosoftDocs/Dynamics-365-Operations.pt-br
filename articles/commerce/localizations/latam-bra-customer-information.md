---
title: Gerenciar informações do cliente no PDV para o Brasil
description: Este tópico descreve como gerenciar informações do cliente no Ponto de Venda (PDV) do Commerce para o Brasil.
author: v-ankvik
manager: annbe
ms.date: 06/10/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2028c8b3f6cdd8818c90daad795d85d587e083d4
ms.sourcegitcommit: cee7887282d372c756c5c11f76684315f249bba5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6303524"
---
# <a name="manage-customer-information-in-pos-for-brazil"></a><span data-ttu-id="fb566-103">Gerenciar informações do cliente no PDV para o Brasil</span><span class="sxs-lookup"><span data-stu-id="fb566-103">Manage customer information in POS for Brazil</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb566-104">Este tópico descreve como gerenciar informações do cliente no Ponto de Venda (PDV) do Commerce para o Brasil.</span><span class="sxs-lookup"><span data-stu-id="fb566-104">This topic describes how to manage customer information in Commerce point of sale (POS) for Brazil.</span></span> <span data-ttu-id="fb566-105">Essas informações incluem números do CNPJ (Cadastro Nacional da Pessoa Jurídica)/CPF (Cadastro de Pessoas Físicas).</span><span class="sxs-lookup"><span data-stu-id="fb566-105">This information includes CNPJ (Cadastro Nacional da Pessoa Jurídica)/CPF (Cadastro de Pessoas Físicas) numbers.</span></span> <span data-ttu-id="fb566-106">Você pode especificar o número de registro de impostos do cliente, o nome e as informações de endereço quando adicionar um cliente nomeado ao carrinho no PDV.</span><span class="sxs-lookup"><span data-stu-id="fb566-106">You can specify customer tax registration number, name, and address information when you add a named customer to the cart in POS.</span></span> <span data-ttu-id="fb566-107">Você também pode inserir informações manualmente para uma transação de vendas.</span><span class="sxs-lookup"><span data-stu-id="fb566-107">You can also manually enter information for a sales transaction.</span></span> <span data-ttu-id="fb566-108">As informações do cliente podem então ser impressas nos recibos fiscais DANFE (Documento Auxiliar de Nota Fiscal Eletrônica) e usadas para fins de faturamento.</span><span class="sxs-lookup"><span data-stu-id="fb566-108">Customer information can then be printed on DANFE (Documento Auxiliar de Nota Fiscal Eletrônica) fiscal receipts and used for invoicing purposes.</span></span>

<span data-ttu-id="fb566-109">Para obter mais informações sobre como configurar esta funcionalidade, consulte [Gerenciamento de informações do cliente](latam-bra-deployment.md#customer-information-management).</span><span class="sxs-lookup"><span data-stu-id="fb566-109">For more information about how to set up this functionality, see [Customer information management](latam-bra-deployment.md#customer-information-management).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="fb566-110">Cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="fb566-110">Example scenarios</span></span>

<span data-ttu-id="fb566-111">Os cenários de exemplo a seguir mostram como gerenciar de informações do cliente no PDV do Commerce para o Brasil.</span><span class="sxs-lookup"><span data-stu-id="fb566-111">The following example scenarios show how to manage customer information in Commerce POS for Brazil.</span></span>

### <a name="scenario-1-make-a-sale-to-an-anonymous-customer"></a><span data-ttu-id="fb566-112">Cenário 1: fazer uma venda para um cliente anônimo</span><span class="sxs-lookup"><span data-stu-id="fb566-112">Scenario 1: Make a sale to an anonymous customer</span></span>

<span data-ttu-id="fb566-113">Para fazer uma venda a um cliente anônimo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="fb566-113">To make a sale to an anonymous customer, follow these steps.</span></span>

1. <span data-ttu-id="fb566-114">Entre no POS.</span><span class="sxs-lookup"><span data-stu-id="fb566-114">Sign in to POS.</span></span>
1. <span data-ttu-id="fb566-115">Adicione itens ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="fb566-115">Add items to the cart.</span></span>
1. <span data-ttu-id="fb566-116">Selecione **Adicionar informações do cliente** e selecione **Digitar manualmente**.</span><span class="sxs-lookup"><span data-stu-id="fb566-116">Select **Add customer information**, and then select **Enter manually**.</span></span>
1. <span data-ttu-id="fb566-117">Digite o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente e então selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb566-117">Enter the customer's CNPJ/CPF number or foreigner ID, name, and address, and then select **OK**.</span></span>
1. <span data-ttu-id="fb566-118">Registre os pagamentos da transação e, em seguida, finalize a transação.</span><span class="sxs-lookup"><span data-stu-id="fb566-118">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="fb566-119">Verifique se o recibo impresso contém o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente.</span><span class="sxs-lookup"><span data-stu-id="fb566-119">Verify that the printed receipt contains the customer's CNPJ/CPF number or foreigner ID, name, and address.</span></span>

### <a name="scenario-2-make-a-sale-to-an-existing-named-customer"></a><span data-ttu-id="fb566-120">Cenário 2: fazer uma venda para um cliente nomeado existente</span><span class="sxs-lookup"><span data-stu-id="fb566-120">Scenario 2: Make a sale to an existing named customer</span></span>

<span data-ttu-id="fb566-121">Para fazer uma venda a um cliente nomeado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="fb566-121">To make a sale to a named customer, follow these steps.</span></span>

1. <span data-ttu-id="fb566-122">Entre no POS.</span><span class="sxs-lookup"><span data-stu-id="fb566-122">Sign in to POS.</span></span>
1. <span data-ttu-id="fb566-123">Adicione itens ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="fb566-123">Add items to the cart.</span></span>
1. <span data-ttu-id="fb566-124">Selecione **Adicionar cliente** e então encontre e selecione o cliente desejado.</span><span class="sxs-lookup"><span data-stu-id="fb566-124">Select **Add customer**, and then find and select the desired customer.</span></span>
1. <span data-ttu-id="fb566-125">Adicione o cliente à transação.</span><span class="sxs-lookup"><span data-stu-id="fb566-125">Add the customer to the transaction.</span></span>
1. <span data-ttu-id="fb566-126">Registre os pagamentos da transação e, em seguida, finalize a transação.</span><span class="sxs-lookup"><span data-stu-id="fb566-126">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="fb566-127">Verifique se o recibo impresso contém o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente.</span><span class="sxs-lookup"><span data-stu-id="fb566-127">Verify that the printed receipt contains the customer's CNPJ/CPF number or foreigner ID, name, and address.</span></span>

### <a name="scenario-3-make-a-sale-to-a-new-named-customer"></a><span data-ttu-id="fb566-128">Cenário 3: fazer uma venda para um novo cliente nomeado</span><span class="sxs-lookup"><span data-stu-id="fb566-128">Scenario 3: Make a sale to a new named customer</span></span>

<span data-ttu-id="fb566-129">Para fazer uma venda a um novo cliente nomeado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="fb566-129">To make a sale to a new named customer, follow these steps.</span></span>

1. <span data-ttu-id="fb566-130">Entre no POS.</span><span class="sxs-lookup"><span data-stu-id="fb566-130">Sign in to POS.</span></span>
1. <span data-ttu-id="fb566-131">Adicione itens ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="fb566-131">Add items to the cart.</span></span>
1. <span data-ttu-id="fb566-132">Selecione **Adicionar cliente** e depois **Criar cliente**.</span><span class="sxs-lookup"><span data-stu-id="fb566-132">Select **Add customer**, and then select **Create customer**.</span></span>
1. <span data-ttu-id="fb566-133">Especifique os atributos do novo cliente.</span><span class="sxs-lookup"><span data-stu-id="fb566-133">Specify the new customer's attributes.</span></span>
1. <span data-ttu-id="fb566-134">No campo **CNPJ/CPF**, digite o número do CNPJ/CPF do cliente.</span><span class="sxs-lookup"><span data-stu-id="fb566-134">In the **CNPJ/CPF** field, enter the customer's CNPJ/CPF number.</span></span>
1. <span data-ttu-id="fb566-135">No campo **ID de estrangeiro**, digite o ID de estrangeiro do cliente, se for necessário.</span><span class="sxs-lookup"><span data-stu-id="fb566-135">In the **Foreigner ID** field, enter the customer's foreigner ID, if it's required.</span></span>
1. <span data-ttu-id="fb566-136">Selecione **Adicionar endereço** e então digite as informações de contato e endereço do novo cliente.</span><span class="sxs-lookup"><span data-stu-id="fb566-136">Select **Add address**, and then enter the new customer's contact information and address.</span></span>
1. <span data-ttu-id="fb566-137">Salve o registro do cliente e o registro de endereço do cliente e então adicione o cliente à transação.</span><span class="sxs-lookup"><span data-stu-id="fb566-137">Save the customer record and the customer address record, and then add the customer to the transaction.</span></span>
1. <span data-ttu-id="fb566-138">Registre os pagamentos da transação e, em seguida, finalize a transação.</span><span class="sxs-lookup"><span data-stu-id="fb566-138">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="fb566-139">Verifique se o recibo impresso contém o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente.</span><span class="sxs-lookup"><span data-stu-id="fb566-139">Verify that the printed receipt contains the customer's CNPJ/CPF number or foreigner ID, name, and address.</span></span>

> [!NOTE]
> <span data-ttu-id="fb566-140">Se você tiver que especificar um cliente diferente para a transação, você deve primeiro limpar as informações do cliente.</span><span class="sxs-lookup"><span data-stu-id="fb566-140">If you have to specify a different customer for the transaction, you must first clear the customer information.</span></span> <span data-ttu-id="fb566-141">Em seguida, selecione outro cliente.</span><span class="sxs-lookup"><span data-stu-id="fb566-141">Then select another customer.</span></span>

### <a name="scenario-4-change-the-customer-information-for-a-sale-to-a-named-customer"></a><span data-ttu-id="fb566-142">Cenário 4: alterar as informações do cliente para uma venda para um cliente nomeado</span><span class="sxs-lookup"><span data-stu-id="fb566-142">Scenario 4: Change the customer information for a sale to a named customer</span></span>

<span data-ttu-id="fb566-143">Para alterar as informações do cliente para uma venda para um cliente nomeado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="fb566-143">To change the customer information for a sale to a named customer, follow these steps.</span></span>

1. <span data-ttu-id="fb566-144">Entre no POS.</span><span class="sxs-lookup"><span data-stu-id="fb566-144">Sign in to POS.</span></span>
1. <span data-ttu-id="fb566-145">Adicione itens ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="fb566-145">Add items to the cart.</span></span>
1. <span data-ttu-id="fb566-146">Selecione **Adicionar cliente** e, em seguida, selecione uma conta do cliente para adicionar à transação.</span><span class="sxs-lookup"><span data-stu-id="fb566-146">Select **Add customer**, and then select a customer account to add to the transaction.</span></span>
1. <span data-ttu-id="fb566-147">Selecione **Adicionar informações do cliente** e então selecione **Limpar** para limpar as informações do cliente da transação.</span><span class="sxs-lookup"><span data-stu-id="fb566-147">Select **Add customer information**, and then select **Clear** to clear the customer information from the transaction.</span></span>
1. <span data-ttu-id="fb566-148">Selecione **Digitar manualmente**.</span><span class="sxs-lookup"><span data-stu-id="fb566-148">Select **Enter manually**.</span></span>
1. <span data-ttu-id="fb566-149">Digite o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente e então selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb566-149">Enter the customer's CNPJ/CPF number or foreigner ID, name, and address, and then select **OK**.</span></span>
1. <span data-ttu-id="fb566-150">Registre os pagamentos da transação e, em seguida, finalize a transação.</span><span class="sxs-lookup"><span data-stu-id="fb566-150">Register payments for the transaction, and then finalize the transaction.</span></span>
1. <span data-ttu-id="fb566-151">Verifique se o recibo impresso contém o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente.</span><span class="sxs-lookup"><span data-stu-id="fb566-151">Verify that the printed receipt contains the customer's CNPJ/CPF number or foreigner ID, name, and address.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb566-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="fb566-152">Additional resources</span></span>

[<span data-ttu-id="fb566-153">Configurar e implantar a localização do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="fb566-153">Set up and deploy Commerce localization for Brazil</span></span>](latam-bra-deployment.md)

[<span data-ttu-id="fb566-154">Localização do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="fb566-154">Commerce localization for Brazil</span></span>](latam-bra-commerce-localization.md)

[<span data-ttu-id="fb566-155">Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil</span><span class="sxs-lookup"><span data-stu-id="fb566-155">NFC-e fiscal document functionality in Commerce POS for Brazil</span></span>](latam-bra-nfce.md)

[<span data-ttu-id="fb566-156">Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil</span><span class="sxs-lookup"><span data-stu-id="fb566-156">Cancellation and return of NFC-e documents in Commerce POS for Brazil</span></span>](latam-bra-nfce-cancel-return.md)

[<span data-ttu-id="fb566-157">Registro adiado de documentos NFC-e emitidos no modo de contingência offline</span><span class="sxs-lookup"><span data-stu-id="fb566-157">Postponed registration of NFC-e documents issued in offline contingency mode</span></span>](latam-bra-nfce-contingency-mode.md)

[<span data-ttu-id="fb566-158">Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce</span><span class="sxs-lookup"><span data-stu-id="fb566-158">Post Brazilian fiscal documents via retail statements in Commerce headquarters</span></span>](latam-bra-retail-statements.md)
