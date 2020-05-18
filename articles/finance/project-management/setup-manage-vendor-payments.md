---
title: Configurar e usar pagamentos de fornecedor de pagamento quando pago
description: Este tópico explica como criar condições de pagamento quando pago (PWP) para que você possa liberar pagamentos parciais de fornecedor, com base nos pagamentos de cliente.
author: RadhikaRS
manager: AnnBe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 390cec62d2790ed10892669e283f2283c6b8e686
ms.sourcegitcommit: 399f128d90b71bd836a1c8c0c8c257b7f9eeb39a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284104"
---
# <a name="set-up-and-use-pay-when-paid-vendor-payments"></a><span data-ttu-id="0d519-103">Configurar e usar pagamentos de fornecedor de pagamento quando pago</span><span class="sxs-lookup"><span data-stu-id="0d519-103">Set up and use pay-when-paid vendor payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d519-104">Quando você aprova um fornecedor para trabalhar como subcontratado, pode reter o pagamento ao fornecedor até que seu cliente pague pelo projeto.</span><span class="sxs-lookup"><span data-stu-id="0d519-104">When you approve a vendor to work as a subcontractor, you might want to withhold payment to the vendor until your customer pays you for the project.</span></span> <span data-ttu-id="0d519-105">Para oferecer suporte a esse cenário, você pode configurar as condições de pagamento quando pago (PWP) ao configurar a ordem de compra (OC) com o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0d519-105">To support this scenario, you can set up pay-when-paid (PWP) terms when you set up the purchase order (PO) with the vendor.</span></span>

<span data-ttu-id="0d519-106">Por exemplo, quando um cliente paga um valor em uma fatura de projeto, você pode liberar parte ou todo o valor da fatura do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0d519-106">For example, when a customer pays an amount on a project invoice, you can release some or all of the vendor invoice amount.</span></span> <span data-ttu-id="0d519-107">Basta configurar as condições de PWP que especificam que o fornecedor será pago depois que você receber uma porcentagem do pagamento relacionado do cliente.</span><span class="sxs-lookup"><span data-stu-id="0d519-107">Just set up PWP terms that specify that the vendor will be paid after you receive a percentage of the related payment from the customer.</span></span> <span data-ttu-id="0d519-108">Se você receber o pagamento parcial de um cliente, você pode liberar manualmente algumas das faturas de fornecedores relacionadas para pagamento.</span><span class="sxs-lookup"><span data-stu-id="0d519-108">If you receive partial payment from a customer, you can manually release some of the related vendor invoices for payment.</span></span>

<span data-ttu-id="0d519-109">O exemplo a seguir descreve o processo quando as condições de PWP são usadas.</span><span class="sxs-lookup"><span data-stu-id="0d519-109">The following example outlines the process when PWP terms are used.</span></span>

## <a name="example"></a><span data-ttu-id="0d519-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0d519-110">Example</span></span>

<span data-ttu-id="0d519-111">Sua organização concorda em fornecer a um cliente 100 computadores com software instalado, por um preço de 150,00 dólares americanos (USD) por computador.</span><span class="sxs-lookup"><span data-stu-id="0d519-111">Your organization agrees to provide a customer with 100 computers that have software installed, for a price of 150.00 US dollars (USD) per computer.</span></span> <span data-ttu-id="0d519-112">Você contrata um fornecedor para fornecer os computadores com o software instalado.</span><span class="sxs-lookup"><span data-stu-id="0d519-112">You then hire a vendor to provide you with the computers that have software installed.</span></span> <span data-ttu-id="0d519-113">De acordo com o contrato, o cliente deve aprovar a qualidade dos computadores antes de pagar à sua organização.</span><span class="sxs-lookup"><span data-stu-id="0d519-113">According to the agreement, the customer must approve the quality of the computers before it pays your organization.</span></span> <span data-ttu-id="0d519-114">A política da sua organização é reter o pagamento aos fornecedores até que o cliente pague.</span><span class="sxs-lookup"><span data-stu-id="0d519-114">Your organization's policy is to withhold payment to vendors until the customer has paid you.</span></span> <span data-ttu-id="0d519-115">Portanto, configure o projeto para que ele tenha uma porcentagem de PWP de 100%.</span><span class="sxs-lookup"><span data-stu-id="0d519-115">Therefore, you set up the project so that it has a PWP percentage of 100 percent.</span></span>

<span data-ttu-id="0d519-116">O fornecedor envia a você os 100 computadores que possuem software instalado, juntamente com uma fatura de US$ 10.000,00.</span><span class="sxs-lookup"><span data-stu-id="0d519-116">The vendor sends you the 100 computers that have software installed, together with an invoice for 10,000.00 USD.</span></span> <span data-ttu-id="0d519-117">Como as condições de PWP estão configuradas para o seu projeto, você não paga o fornecedor após o recebimento dos computadores.</span><span class="sxs-lookup"><span data-stu-id="0d519-117">Because PWP terms are set up for your project, you don't pay the vendor upon receipt of the computers.</span></span> <span data-ttu-id="0d519-118">Em vez disso, você envia os computadores ao cliente, juntamente com uma fatura de 15.000,00.</span><span class="sxs-lookup"><span data-stu-id="0d519-118">Instead, you send the computers to the customer, together with an invoice for 15,000.00.</span></span> <span data-ttu-id="0d519-119">O cliente inspeciona os computadores e aprova o valor total da fatura do projeto.</span><span class="sxs-lookup"><span data-stu-id="0d519-119">The customer inspects the computers and approves the full amount of the project invoice.</span></span>

<span data-ttu-id="0d519-120">Depois de receber o pagamento total do cliente, você paga ao fornecedor 10.000,00, o valor total da fatura do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0d519-120">After you receive the full payment from the customer, you pay the vendor 10,000.00, the full amount of the vendor invoice.</span></span>

## <a name="set-up-pwp-terms-for-a-project"></a><span data-ttu-id="0d519-121">Estabelecer condições PWP de um projeto</span><span class="sxs-lookup"><span data-stu-id="0d519-121">Set up PWP terms for a project</span></span>

<span data-ttu-id="0d519-122">Ao configurar as condições de PWP de um projeto, você deve especificar, como porcentagem, o valor mínimo que um cliente deve pagar pelo projeto antes de você pagar ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0d519-122">When you set up PWP terms for a project, you must specify, as a percentage, the minimum amount that a customer must pay you for the project before you will pay the vendor.</span></span> <span data-ttu-id="0d519-123">O valor limite é calculado automaticamente nas faturas de cliente do projeto.</span><span class="sxs-lookup"><span data-stu-id="0d519-123">The threshold amount is automatically calculated on the customer invoices for the project.</span></span> <span data-ttu-id="0d519-124">Siga estas etapas para configurar a porcentagem limite das condições de PWP.</span><span class="sxs-lookup"><span data-stu-id="0d519-124">Follow these steps to set up the threshold percentage for PWP terms.</span></span>

1. <span data-ttu-id="0d519-125">Vá para **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="0d519-125">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="0d519-126">Localize e abra o projeto para o qual deseja configurar as condições de PWP.</span><span class="sxs-lookup"><span data-stu-id="0d519-126">Find and open the project that you want to set up PWP terms for.</span></span>
3. <span data-ttu-id="0d519-127">Na guia rápida **Contratos de fornecedor**, selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="0d519-127">On the **Vendor agreements** FastTab, select **Add line**.</span></span>
3. <span data-ttu-id="0d519-128">No campo **Código da conta**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0d519-128">In the **Account code** field, select one of the following options:</span></span>

    - <span data-ttu-id="0d519-129">**Tabela** – as condições PWP se aplicam a um único fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0d519-129">**Table** – The PWP terms apply to a single vendor.</span></span>
    - <span data-ttu-id="0d519-130">**Grupo** – as condições PWP se aplicam a todos os fornecedores em um grupo de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="0d519-130">**Group** – The PWP terms apply to all vendors in a vendor group.</span></span>
    - <span data-ttu-id="0d519-131">**Todos** – as condições PWP se aplicam a todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="0d519-131">**All** – The PWP terms apply to all vendors.</span></span>

4. <span data-ttu-id="0d519-132">Se você selecionou **Tabela** ou **Grupo** na etapa anterior, no campo **Fornecedor/grupo de fornecedores**, selecione o fornecedor ou grupo de fornecedores aos quais as condições de PWP se aplicam.</span><span class="sxs-lookup"><span data-stu-id="0d519-132">If you selected **Table** or **Group** in the previous step, in the **Vendor/Vendor group** field, select the vendor or vendor group that the PWP terms apply to.</span></span> <span data-ttu-id="0d519-133">Se você selecionou **Tudo** na etapa anterior, o campo **Fornecedor/grupo de fornecedores** não poderá ser editado.</span><span class="sxs-lookup"><span data-stu-id="0d519-133">If you selected **All** in the previous step, the **Vendor/Vendor group** field can't be edited.</span></span>
5. <span data-ttu-id="0d519-134">Se as condições de retenção de fornecedor estiverem estabelecidas para o fornecedor no projeto, no campo **Condições de retenção de fornecedor**, selecione a ID de regra das condições de retenção.</span><span class="sxs-lookup"><span data-stu-id="0d519-134">If vendor retention terms are set up for the vendor in the project, in the **Vendor retention terms** field, select the rule ID for the retention terms.</span></span>
6. <span data-ttu-id="0d519-135">No campo **Porcentagem de limite PWP**, digite a porcentagem de limite para o projeto.</span><span class="sxs-lookup"><span data-stu-id="0d519-135">In the **PWP threshold percentage** field, enter the threshold percentage for the project.</span></span> <span data-ttu-id="0d519-136">A porcentagem que você insere para o projeto define o valor mínimo que o cliente deve pagar antes de você pagar o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0d519-136">The percentage that you enter for the project defines the minimum amount that the customer must pay you before you will pay the vendor.</span></span>

## <a name="create-a-po-that-has-pwp-terms"></a><span data-ttu-id="0d519-137">Criar uma OC com condições de PWP</span><span class="sxs-lookup"><span data-stu-id="0d519-137">Create a PO that has PWP terms</span></span>

<span data-ttu-id="0d519-138">Quando você lança uma fatura de um fornecedor, se o fornecedor estiver sujeito às condições de PWP, essas condições serão mostradas nas linhas de OC.</span><span class="sxs-lookup"><span data-stu-id="0d519-138">When you post an invoice from a vendor, if the vendor is subject to PWP terms, those terms are shown on the PO lines.</span></span> <span data-ttu-id="0d519-139">Para criar uma OC com condições de PWP, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0d519-139">To create a PO that has PWP terms, follow these steps.</span></span>

1. <span data-ttu-id="0d519-140">Acesse **Compras e fornecimento** \> **Ordens de compra** \> **Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="0d519-140">Go to **Procurement and sourcing** \> **Purchase orders** \> **All purchase orders**.</span></span>
2. <span data-ttu-id="0d519-141">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0d519-141">On the Action Pane, select **New**.</span></span> <span data-ttu-id="0d519-142">Em seguida, na caixa de diálogo **Criar ordem de compra**, insira as informações necessárias e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0d519-142">Then, in the **Create purchase order** dialog box, enter the required information, and select **OK**.</span></span>

    <span data-ttu-id="0d519-143">Como alternativa, abra uma OC existente na página da lista **Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="0d519-143">Alternatively, open an existing PO on the **All purchase orders** list page.</span></span>

4. <span data-ttu-id="0d519-144">Na página **Ordem de compra**, na FastTab **Linhas de ordem de compra**, examine os detalhes da linha da OC do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="0d519-144">On the **Purchase order** page, on the **Purchase order lines** FastTab, review the details of the PO line for the vendor.</span></span> <span data-ttu-id="0d519-145">A opção **Pagar quando pago** é selecionada automaticamente e o valor no campo **Porcentagem de limite PWP** é automaticamente copiado do campo **Porcentagem de limite PWP** na página **Projetos**.</span><span class="sxs-lookup"><span data-stu-id="0d519-145">The **Pay when paid** option is automatically selected, and the value in the **PWP threshold percentage** field is automatically copied from the **PWP threshold percentage** field on the **Projects** page.</span></span>
6. <span data-ttu-id="0d519-146">Se você não deseja aplicar as condições de PWP ao fornecedor para uma linha de OC, desmarque a opção **Pagar quando pago**.</span><span class="sxs-lookup"><span data-stu-id="0d519-146">If you don't want to apply PWP terms to the vendor for a PO line, clear the **Pay when paid** option.</span></span> <span data-ttu-id="0d519-147">Nesse caso, o campo **Porcentagem de limite PWP** para a linha de OC será redefinido como 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="0d519-147">In this case, the **PWP threshold percentage** field for the PO line will be reset to 0 (zero).</span></span>

## <a name="update-a-customer-payment-and-pay-the-vendor"></a><span data-ttu-id="0d519-148">Atualizar o pagamento do cliente e pagar o fornecedor</span><span class="sxs-lookup"><span data-stu-id="0d519-148">Update a customer payment and pay the vendor</span></span>

<span data-ttu-id="0d519-149">Quando um fornecedor concluir seu trabalho em um projeto e enviar uma fatura, você deve analisar o status do projeto e as faturas do cliente para determinar se as condições de PWP foram atendidas para o projeto.</span><span class="sxs-lookup"><span data-stu-id="0d519-149">When a vendor completes its work on a project and sends you an invoice, you must review the project status and customer invoices to determine whether the PWP terms have been met for the project.</span></span> <span data-ttu-id="0d519-150">Se as condições PWP do fornecedor foram atendidas, você pode determinar quais linhas da fatura de fornecedor serão pagas, com base nos pagamentos do cliente pelo projeto.</span><span class="sxs-lookup"><span data-stu-id="0d519-150">If the PWP terms for the vendor were met, you can determine which lines on the vendor invoice to pay, based on the customer payments for the project.</span></span> <span data-ttu-id="0d519-151">Se você decidir pagar ao fornecedor, mesmo que as condições de PWP não tenham sido atendidas, poderá substituí-las na página **Faturas de fornecedor com pagamento quando pagas**.</span><span class="sxs-lookup"><span data-stu-id="0d519-151">If you decide to pay the vendor even though the PWP terms weren't met, you can override the PWP terms on the **Vendor invoice with pay when paid** page.</span></span>

1. <span data-ttu-id="0d519-152">Acesse **Gerenciamento e contabilidade do projeto** \> **Consultas e relatórios** \> **Consultas de retenção** \> **Faturas de fornecedor com pagamento quando pagas**.</span><span class="sxs-lookup"><span data-stu-id="0d519-152">Go to **Project management and accounting** \> **Inquiries and reports** \> **Retention inquiries** \> **Vendor invoice with pay when paid**.</span></span>
2. <span data-ttu-id="0d519-153">Na página **Faturas de fornecedor com pagamento quando pagas**, no campo de pesquisa, insira valores para localizar a fatura do fornecedor que você deseja revisar e selecione **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="0d519-153">On the **Vendor invoices with pay when paid** page, in the search field, enter values to find the vendor invoice that you want to review, and then select **Search**.</span></span>
3. <span data-ttu-id="0d519-154">Na FastTab **Linhas da fatura de fornecedor**, selecione as linhas que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="0d519-154">On the **Vendor invoice lines** FastTab, select the lines that you want to change.</span></span>
4. <span data-ttu-id="0d519-155">Se as condições de **Pagar quando pago** forem atendidas para a linha da fatura, selecione **Liberar pagamento do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="0d519-155">If the **Pay when paid** conditions are met for the invoice line, select **Release vendor payment**.</span></span> <span data-ttu-id="0d519-156">A opção **Pagar quando pago** estará desmarcada, e o valor do campo **Pronto para pagamento** será alterada como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="0d519-156">The **Pay when paid** option is cleared, and the value of the **Ready for payment** field is changed to **Yes**.</span></span>