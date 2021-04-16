---
title: Criar faturas de pagamento
description: Este tópico explica como criar faturas de arrendamento mensais. Você pode criar faturas para arrendamentos individuais ou então usar um processo em lote para criá-las para vários arrendamentos.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 51e4c44cf192754a832132ea1942baf18b43a755
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815995"
---
# <a name="create-payment-invoices"></a><span data-ttu-id="62823-104">Criar faturas de pagamento</span><span class="sxs-lookup"><span data-stu-id="62823-104">Create payment invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62823-105">Você pode criar faturas mensais para arrendamentos individuais ou então usar um processo em lote para criá-las para vários arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="62823-105">You can create monthly invoices for individual leases, or you can use a batch process to create them for multiple leases.</span></span> <span data-ttu-id="62823-106">O procedimento a seguir mostra como criar uma entrada de pagamento de arrendamento individual quando o parâmetro **Pagar ao fornecedor** na página **Configuração do registro de arrendamento** está ativado.</span><span class="sxs-lookup"><span data-stu-id="62823-106">The following procedure shows how to create an individual lease payment entry when the **Pay to Vendor** parameter on the **Lease book setup** page is turned on.</span></span>

1. <span data-ttu-id="62823-107">Na página **Resumo do arrendamento**, selecione um arrendamento e selecione **Registros \> Agendamento de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="62823-107">On the **Lease summary** page, select a lease, and then select **Books \> Payment schedule**.</span></span>
2. <span data-ttu-id="62823-108">Selecione o pagamento que deve ser feito e selecione **Criar diário**.</span><span class="sxs-lookup"><span data-stu-id="62823-108">Select the payment that must be made, and then select **Create journal**.</span></span> <span data-ttu-id="62823-109">Você recebe uma mensagem que informa que um diário foi criado com base no pagamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="62823-109">You receive a message that states that a journal was created against the selected payment.</span></span>
3. <span data-ttu-id="62823-110">Selecione **Diários de faturas** e, em seguida, selecione a fatura que deve ser paga.</span><span class="sxs-lookup"><span data-stu-id="62823-110">Select **Invoice journals**, and then select the invoice that must be paid.</span></span>
4. <span data-ttu-id="62823-111">Na guia **Linhas**, revise a entrada de diário antes de lançá-la na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="62823-111">On the **Lines** tab, review the journal entry before you post it to the general ledger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="62823-112">Por padrão, as linhas da fatura do fornecedor criadas usam o perfil de lançamento do fornecedor na página **Parâmetros de contas a pagar**.</span><span class="sxs-lookup"><span data-stu-id="62823-112">By default, the vendor invoice lines that are created use the vendor posting profile from the **Accounts payable parameters** page.</span></span>

5. <span data-ttu-id="62823-113">Selecione o diário correto e então a fatura que deve ser paga.</span><span class="sxs-lookup"><span data-stu-id="62823-113">Select the correct journal, and then select the invoice that must be paid.</span></span>

    <span data-ttu-id="62823-114">Para este exemplo, o parâmetro **Pagar ao fornecedor** no registro de arrendamento é ativado.</span><span class="sxs-lookup"><span data-stu-id="62823-114">For this example, the **Pay to Vendor** parameter on the lease book is turned on.</span></span> <span data-ttu-id="62823-115">Portanto, a fatura estará no diário de faturas.</span><span class="sxs-lookup"><span data-stu-id="62823-115">Therefore, the invoice will be in the invoice journal.</span></span> <span data-ttu-id="62823-116">A seção **Visão geral** mostra um resumo da entrada de diário e a seção **Linhas** mostra detalhes das linhas do próprio diário.</span><span class="sxs-lookup"><span data-stu-id="62823-116">The **Overview** section shows a summary of the journal entry, and the **Lines** section shows details of the actual journal lines.</span></span>

    > [!NOTE]
    > <span data-ttu-id="62823-117">Se o parâmetro **Pagar ao fornecedor** estiver desativado, as entradas do diário de pagamento serão listadas na página **Arrendamento de ativos** para o registro de arrendamento, e o sistema criará uma entrada de arrendamento de ativos em vez de uma fatura.</span><span class="sxs-lookup"><span data-stu-id="62823-117">If the **Pay to Vendor** parameter is turned off, payment journal entries will be listed on the **Asset leasing** page for the lease book, and the system will create an asset leasing entry instead of an invoice.</span></span> <span data-ttu-id="62823-118">A entrada de pagamento do arrendamento será lançada no nome do diário especificado no campo **Diário de arrendamento mensal**.</span><span class="sxs-lookup"><span data-stu-id="62823-118">The lease payment entry will be posted to the journal name that is specified in the **Monthly lease journal** field.</span></span>

6. <span data-ttu-id="62823-119">Depois que a transação é lançada, você pode exibir as informações de transação e o valor de transporte da responsabilidade com arrendamento selecionando **Transações de responsabilidade** no registro de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="62823-119">After the transaction is posted, you can view the transaction information and the carrying value of the lease liability by selecting **Liability transactions** in the lease book.</span></span>

    <span data-ttu-id="62823-120">No agendamento de pagamento, a caixa de seleção **Diário lançado** será marcada, e a linha mostrará o número do diário de faturas.</span><span class="sxs-lookup"><span data-stu-id="62823-120">In the payment schedule, the **Journal posted** check box will be selected, and the line will show the invoice journal number.</span></span> <span data-ttu-id="62823-121">Depois que um diário de pagamentos e uma entrada desse diário tiverem sido criados, você deverá reverter a entrada para que ela possa ser criada novamente.</span><span class="sxs-lookup"><span data-stu-id="62823-121">After a payment journal and an entry for that journal have been created, you must reverse the entry before it can be re-created.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]