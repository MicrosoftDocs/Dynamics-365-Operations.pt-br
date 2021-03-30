---
title: Reverter transações de arrendamento lançadas
description: Este tópico explica como reverter uma transação de arrendamento lançada. Qualquer transação criada por meio do Arrendamento de ativos pode ser revertida.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 22d8eee22221efaf5e7a715c8b95dff261bee62f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249716"
---
# <a name="reverse-posted-lease-transactions"></a><span data-ttu-id="de19c-104">Reverter transações de arrendamento lançadas</span><span class="sxs-lookup"><span data-stu-id="de19c-104">Reverse posted lease transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de19c-105">Qualquer transação criada por meio do Arrendamento de ativos pode ser revertida.</span><span class="sxs-lookup"><span data-stu-id="de19c-105">Any transaction that is created through Asset leasing can be reversed.</span></span> <span data-ttu-id="de19c-106">As transações revertidas por meio de Arrendamento de ativo atualizam os dados do arrendamento.</span><span class="sxs-lookup"><span data-stu-id="de19c-106">Transactions that are reversed through Asset leasing update your lease data.</span></span> <span data-ttu-id="de19c-107">Portanto, eles também atualizam os valores de transporte da responsabilidade com arrendamento e do ativo de direito de uso (DDU).</span><span class="sxs-lookup"><span data-stu-id="de19c-107">Therefore, they also update the carrying values of the lease liability and right-of-use (ROU) asset.</span></span>

<span data-ttu-id="de19c-108">Para criar uma transação de reversão para um arrendamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="de19c-108">To create a reversing transaction for a lease, follow these steps.</span></span>

1. <span data-ttu-id="de19c-109">Na página **Transações de ativo** ou na página **Transações de passivo**, selecione a transação e, em seguida, selecione **Reverter transação**.</span><span class="sxs-lookup"><span data-stu-id="de19c-109">On either the **Asset transactions** page or the **Liability transactions** page, select the transaction, and then select **Reverse transaction**.</span></span>
2. <span data-ttu-id="de19c-110">Na caixa de diálogo exibida, você pode editar a data em que a entrada de reversão será lançada.</span><span class="sxs-lookup"><span data-stu-id="de19c-110">In the dialog box that appears, you can edit the date when the reversing entry will be posted.</span></span> <span data-ttu-id="de19c-111">Por padrão, o campo de **Data** é definido como a data de lançamento da transação selecionada.</span><span class="sxs-lookup"><span data-stu-id="de19c-111">By default, the **Date** field is set to the transaction posting date of the transaction that you selected.</span></span> <span data-ttu-id="de19c-112">A entrada de reversão não pode ser lançada antes da data de lançamento original da transação selecionada.</span><span class="sxs-lookup"><span data-stu-id="de19c-112">The reversing entry can't be posted earlier than the original posting date of the selected transaction.</span></span>
3. <span data-ttu-id="de19c-113">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="de19c-113">Select **OK**.</span></span> <span data-ttu-id="de19c-114">Uma entrada de diário é lançada para reverter a entrada selecionada.</span><span class="sxs-lookup"><span data-stu-id="de19c-114">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="de19c-115">A reversão é mostrada na página **Transações de ativo** ou **Transações de passivo** e o total líquido do saldo atual mostrado na página é atualizado.</span><span class="sxs-lookup"><span data-stu-id="de19c-115">The reversal is shown on the **Asset transactions** or **Liability transactions** page, and the net total of the current balance that is shown on the page is updated.</span></span>

<span data-ttu-id="de19c-116">Quando você seleciona o **Rastreamento da reversão**, é exibida uma caixa de diálogo mostrando as transações originais e as transações revertidas, juntamente com um número vinculado, que é conhecido como um *número de rastreamento*.</span><span class="sxs-lookup"><span data-stu-id="de19c-116">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked number that is known as a *trace number*.</span></span> <span data-ttu-id="de19c-117">Para que os estornos possam ser mais fáceis de compreender e para aprimorar a visibilidade, você também pode rastrear estornos usando as agendas de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="de19c-117">To make the reversals easier to understand and to improve visibility, you can also track reversals by using the lease schedules.</span></span>

<span data-ttu-id="de19c-118">O campo **Número do diário mais recente** na página **Agenda** mostra os números do diário de transações.</span><span class="sxs-lookup"><span data-stu-id="de19c-118">The **Latest journal number** field on the **Schedule** page shows the journal numbers of transactions.</span></span> <span data-ttu-id="de19c-119">Quando uma transação é revertida, esse campo é atualizado com o número do diário de uma transação de reversão.</span><span class="sxs-lookup"><span data-stu-id="de19c-119">When a transaction is reversed, this field is updated with the journal number of a reversing transaction.</span></span> <span data-ttu-id="de19c-120">Além disso, a caixa de seleção **Revertida** é marcada para indicar que a transação foi revertida e o campo **Lançada** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="de19c-120">Additionally, the **Reversed** check box is selected to indicate that the transaction is reversed, and the **Posted** field is selected.</span></span>

## <a name="revoke-a-reversed-transaction"></a><span data-ttu-id="de19c-121">Revogar uma transação revertida</span><span class="sxs-lookup"><span data-stu-id="de19c-121">Revoke a reversed transaction</span></span>

<span data-ttu-id="de19c-122">Para revogar uma transação revertida, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="de19c-122">To revoke a reversed transaction, follow these steps.</span></span>

1. <span data-ttu-id="de19c-123">Na página **Agenda** ou na página **Transações**, selecione a transação original.</span><span class="sxs-lookup"><span data-stu-id="de19c-123">On either the **Schedule** page or the **Transactions** page, select the original transaction.</span></span>
2. <span data-ttu-id="de19c-124">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="de19c-124">Follow one of these steps:</span></span>

    - <span data-ttu-id="de19c-125">Se você tiver selecionado a transação na página **Agenda**, siga as etapas para criar um diário em [Criar entradas de diário mensal em um lote](create-monthly-journals-batch.md).</span><span class="sxs-lookup"><span data-stu-id="de19c-125">If you selected the transaction on the **Schedule** page, follow the steps for creating a journal in [Create monthly journal entries in a batch](create-monthly-journals-batch.md).</span></span> <span data-ttu-id="de19c-126">Você deve lançar o diário manualmente.</span><span class="sxs-lookup"><span data-stu-id="de19c-126">You must manually post the journal.</span></span>
    - <span data-ttu-id="de19c-127">Se você tiver selecionado a transação na página **Transações**, selecione **Reverter transação**.</span><span class="sxs-lookup"><span data-stu-id="de19c-127">If you selected the transaction on the **Transactions** page, select **Reverse transaction**.</span></span> <span data-ttu-id="de19c-128">Você receberá uma mensagem informando que a revogação é uma revogação de uma reversão anterior e que é possível editar a data de lançamento dessa revogação.</span><span class="sxs-lookup"><span data-stu-id="de19c-128">You receive a message that states that this revocation is a revocation of an earlier reversal, and that you can edit the posting date for this revocation.</span></span> <span data-ttu-id="de19c-129">No entanto, as validações gerais de negócios afetam as datas que podem ser inseridas no campo **Data**.</span><span class="sxs-lookup"><span data-stu-id="de19c-129">However, general business validations affect the dates that can be entered in the **Date** field.</span></span> 

3. <span data-ttu-id="de19c-130">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="de19c-130">Select **OK**.</span></span> <span data-ttu-id="de19c-131">Uma entrada de diário é lançada para reverter a entrada selecionada.</span><span class="sxs-lookup"><span data-stu-id="de19c-131">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="de19c-132">A reversão é mostrada na página **Transações** e o saldo líquido atual total é restaurado para o que era antes da primeira reversão.</span><span class="sxs-lookup"><span data-stu-id="de19c-132">The reversal is shown on the **Transactions** page, and the net total current balance is restored to what it was before the first reversal.</span></span> <span data-ttu-id="de19c-133">Portanto, o impacto que a reversão tinha nos saldos é negado.</span><span class="sxs-lookup"><span data-stu-id="de19c-133">Therefore, the impact that the reversal had on the balances is negated.</span></span>

<span data-ttu-id="de19c-134">Quando você seleciona **Rastreamento da reversão**, é exibida uma caixa de diálogo mostrando as transações originais e as transações revertidas, juntamente com um número vinculado, que é conhecido como um número de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="de19c-134">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked trace number.</span></span>

<span data-ttu-id="de19c-135">Você também pode rastrear as revogações usando a página **Agendas** apropriadas.</span><span class="sxs-lookup"><span data-stu-id="de19c-135">You can also track revocations by using the appropriate **Schedules** page.</span></span> <span data-ttu-id="de19c-136">O campo **Reverter** é limpo, enquanto o campo **Lançado no diário** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="de19c-136">The **Reverse** field is cleared, whereas the **Journal posted** field is selected.</span></span> <span data-ttu-id="de19c-137">Além disso, o campo **Número do diário mais recente** é atualizado com o número do diário da transação de revogação e o campo **Número do diário** é atualizado com o número do diário de estorno.</span><span class="sxs-lookup"><span data-stu-id="de19c-137">Additionally, the **Latest journal number** field is updated with the journal number of the revocation transaction, and the **Journal number** field is updated with the reversal journal number.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]