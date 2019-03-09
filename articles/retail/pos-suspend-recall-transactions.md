---
title: Suspender e continuar uma transação no ponto de venda (PDV)
description: Este tópico explica como os usuários podem suspender transações em andamento e retomá-las, posteriormente, ou iniciar um registro diferente, usando o Microsoft Dynamics 365 for Retail.
author: jblucher
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ffb04609318c7de4b9ef729a8e03a7f9395806b8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "333889"
---
# <a name="suspend-and-resume-transactions-in-the-point-of-sale-pos"></a><span data-ttu-id="762ee-103">Suspender e continuar transações no ponto de venda (PDV)</span><span class="sxs-lookup"><span data-stu-id="762ee-103">Suspend and resume transactions in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="762ee-104">Os usuários de ponto de venda (PDV) podem suspender transações em andamento e retomá-las posteriormente ou iniciar um registro diferente.</span><span class="sxs-lookup"><span data-stu-id="762ee-104">Point of sale (POS) users can suspend in-progress transactions, and then resume them later or on a different register.</span></span> <span data-ttu-id="762ee-105">As transações costumam ser suspensas para liberar rapidamente um registro para uma tarefa diferente sem perder o progresso da transação atual.</span><span class="sxs-lookup"><span data-stu-id="762ee-105">Transactions are often suspended to quickly free up a register for a different task without losing any progress on the current transaction.</span></span> <span data-ttu-id="762ee-106">Por exemplo, um associado da loja começa a processar transações de um cliente em um dispositivo móvel, mas precisa concluí-la em um registro com uma caixa registradora.</span><span class="sxs-lookup"><span data-stu-id="762ee-106">For example, a store associate starts to process a customer's transaction on a mobile device but must complete it on a register that has a cash drawer.</span></span> <span data-ttu-id="762ee-107">Nesse caso, o associado da loja pode suspender a transação no dispositivo celular e, depois, recuperá-la e retomá-la em um registro.</span><span class="sxs-lookup"><span data-stu-id="762ee-107">In this case, the store associate can suspend the transaction on the mobile device, and then recall and resume it on a register.</span></span>

## <a name="configure-suspend-and-resume-functionality"></a><span data-ttu-id="762ee-108">Configure a funcionalidade de suspensão e retomada</span><span class="sxs-lookup"><span data-stu-id="762ee-108">Configure suspend and resume functionality</span></span>

### <a name="pos-operations"></a><span data-ttu-id="762ee-109">Operações de PDV</span><span class="sxs-lookup"><span data-stu-id="762ee-109">POS operations</span></span>

<span data-ttu-id="762ee-110">Duas [operações de PDV](pos-operations.md) permitiram a suspensão e a retomada de cenários pelo PDV.</span><span class="sxs-lookup"><span data-stu-id="762ee-110">Two [POS operations](pos-operations.md) let the POS support suspend and resume scenarios.</span></span> <span data-ttu-id="762ee-111">Você pode atribuir essas operações a [grades de botões](pos-screen-layouts.md) na página da transação ou na página de boas-vindas.</span><span class="sxs-lookup"><span data-stu-id="762ee-111">You can assign these operations to [button grids](pos-screen-layouts.md) on the transaction page or the welcome page.</span></span>

- <span data-ttu-id="762ee-112">503: Suspender Transação</span><span class="sxs-lookup"><span data-stu-id="762ee-112">503: Suspend transaction</span></span>
- <span data-ttu-id="762ee-113">504: Recuperar Transação</span><span class="sxs-lookup"><span data-stu-id="762ee-113">504: Recall transaction</span></span>

### <a name="receipt-template"></a><span data-ttu-id="762ee-114">Modelo de recebimento</span><span class="sxs-lookup"><span data-stu-id="762ee-114">Receipt template</span></span>

<span data-ttu-id="762ee-115">O PDV pode ser configurado para gerar uma guia impressa quando uma transação é suspensa.</span><span class="sxs-lookup"><span data-stu-id="762ee-115">The POS can be configured to generate a printed slip when a transaction is suspended.</span></span> <span data-ttu-id="762ee-116">Essa guia pode ser usada para identificar rapidamente e recuperar a transação posteriormente.</span><span class="sxs-lookup"><span data-stu-id="762ee-116">That slip can then be used to quickly identify and recall the transaction later.</span></span>

<span data-ttu-id="762ee-117">Para habilitar o PDV para imprimir uma guia, você deve adicionar o formato de recebimento **Transação suspensa** ao perfil de recebimento da loja.</span><span class="sxs-lookup"><span data-stu-id="762ee-117">To enable the POS to print a slip, you must add the **Suspended transaction** receipt format to the store's receipt profile.</span></span> <span data-ttu-id="762ee-118">Você pode criar o formato de recebimento de modo que ele inclua ou exclua detalhes específicos sobre a transação.</span><span class="sxs-lookup"><span data-stu-id="762ee-118">You can design the receipt format so that it includes or excludes specific details about the transaction.</span></span> <span data-ttu-id="762ee-119">Por exemplo, o formato pode incluir um código de barras para oferecer suporte à digitalização.</span><span class="sxs-lookup"><span data-stu-id="762ee-119">For example, the format can include a barcode to support scanning.</span></span>

### <a name="receipt-numbering"></a><span data-ttu-id="762ee-120">Numeração de recibo</span><span class="sxs-lookup"><span data-stu-id="762ee-120">Receipt numbering</span></span>

<span data-ttu-id="762ee-121">Quanto a outros tipos de transação PDV que geram um recibo impresso, você pode definir uma sequência numérica para transações suspensas na seção **Numeração de recibo** do perfil de funcionalidade da loja.</span><span class="sxs-lookup"><span data-stu-id="762ee-121">As for other POS transaction types that generate a printed receipt, you can define a number sequence for suspended transactions in the **Receipt numbering** section of the store's functionality profile.</span></span>

### <a name="void-when-closing-shift"></a><span data-ttu-id="762ee-122">Anular no fechamento do turno</span><span class="sxs-lookup"><span data-stu-id="762ee-122">Void when closing shift</span></span>

<span data-ttu-id="762ee-123">Você pode usar a opção **Anular ao fechar turno** para exigir que os usuários concluam ou anulem transações suspensas antes de fechar seu turno.</span><span class="sxs-lookup"><span data-stu-id="762ee-123">You can use the **Void when closing shift** option to require that users either complete or void any suspended transactions before they close their shift.</span></span> <span data-ttu-id="762ee-124">Durante a operação **Fechar turno**, o PDV solicitará que os usuários exibam ou anulem transações suspensas pendentes.</span><span class="sxs-lookup"><span data-stu-id="762ee-124">During the **Close shift** operation, the POS will prompt users to either view or void any outstanding suspended transactions.</span></span>

## <a name="suspend-and-resume-a-transaction"></a><span data-ttu-id="762ee-125">Suspender e retomar uma transação</span><span class="sxs-lookup"><span data-stu-id="762ee-125">Suspend and resume a transaction</span></span>

### <a name="suspend-a-transaction"></a><span data-ttu-id="762ee-126">Suspenda uma transação</span><span class="sxs-lookup"><span data-stu-id="762ee-126">Suspend a transaction</span></span>

<span data-ttu-id="762ee-127">Os usuários com privilégios suficientes e aqueles com um layout de tela que inclua a operação **Suspender transação** poderão suspender uma transação para que ela possa ser recuperada posteriormente ou em outro registro.</span><span class="sxs-lookup"><span data-stu-id="762ee-127">Users who have sufficient privileges, and who have a screen layout that includes the **Suspend transaction** operation, can suspend a transaction so that it can be recalled later or on a different register.</span></span>

<span data-ttu-id="762ee-128">Transações só poderão ser suspensas se **não** contiverem os seguintes tipos de linhas:</span><span class="sxs-lookup"><span data-stu-id="762ee-128">Transactions can be suspended only if they do **not** contain the following types of lines:</span></span>

- <span data-ttu-id="762ee-129">Linhas de pagamento ativas</span><span class="sxs-lookup"><span data-stu-id="762ee-129">Active payment lines</span></span>
- <span data-ttu-id="762ee-130">Linhas de vale-presente (para emitir um vale-presente ou para adicionar ao saldo do vale-presente)</span><span class="sxs-lookup"><span data-stu-id="762ee-130">Gift card lines (either to issue a gift card or to add to the gift card balance)</span></span>

<span data-ttu-id="762ee-131">Uma transação suspensa não afeta informações de vendas nem informações de disponibilidade do estoque.</span><span class="sxs-lookup"><span data-stu-id="762ee-131">A suspended transaction doesn't affect sales information or inventory availability information for the store.</span></span>

### <a name="resume-a-suspended-transaction"></a><span data-ttu-id="762ee-132">Retomar uma transação suspensa</span><span class="sxs-lookup"><span data-stu-id="762ee-132">Resume a suspended transaction</span></span>

<span data-ttu-id="762ee-133">As transações suspensas podem ser recuperadas e retomadas na mesma loja por qualquer usuário com privilégios suficientes, e também que tenham um layout que inclua a operação **Recuperar transação**.</span><span class="sxs-lookup"><span data-stu-id="762ee-133">Suspended transactions can be recalled and resumed in the same store by any user who has sufficient privileges, and who also has a layout that includes the **Recall transaction** operation.</span></span>

<span data-ttu-id="762ee-134">Para recuperar uma transação suspensa com rapidez e facilidade, digitalize o código de barras na guia impressa enquanto você estiver exibindo a lista de transações da operação **Recuperar transação**.</span><span class="sxs-lookup"><span data-stu-id="762ee-134">To quickly and easily recall a suspended transaction, scan the barcode on the printed slip while you're viewing the list of transactions from the **Recall transaction** operation.</span></span>

### <a name="considerations-for-offline-mode"></a><span data-ttu-id="762ee-135">Considerações sobre o modo offline</span><span class="sxs-lookup"><span data-stu-id="762ee-135">Considerations for offline mode</span></span>

- <span data-ttu-id="762ee-136">Qualquer transação suspensa enquanto o PDV estiver em modo online não poderá ser retomada em modo offline, pois os dados não estão sincronizados no banco de dados offline.</span><span class="sxs-lookup"><span data-stu-id="762ee-136">Any transaction that is suspended while the POS is in online mode can't be resumed in offline mode, because the data isn't synced to the offline database.</span></span>
- <span data-ttu-id="762ee-137">Se você suspender uma transação enquanto o PDV estiver em modo offline, poderá recuperá-la em modo offline, desde que o PDV não volte ao modo online a qualquer momento, pois você suspendeu a transação.</span><span class="sxs-lookup"><span data-stu-id="762ee-137">If you suspend a transaction while the POS is in offline mode, you can recall it in offline mode, provided that the POS wasn't switched back to online mode at any time since you suspended the transaction.</span></span> <span data-ttu-id="762ee-138">Quando o PDV é alternado para o modo online, os dados sobre transações suspensas são movidos para o banco de dados online e removidos do banco de dados offline.</span><span class="sxs-lookup"><span data-stu-id="762ee-138">When the POS is switched back to online mode, data about suspended transactions is moved to the online database and removed from the offline database.</span></span> <span data-ttu-id="762ee-139">Portanto, as transações só podem ser retomadas em modo online.</span><span class="sxs-lookup"><span data-stu-id="762ee-139">Therefore, the transactions can be resumed only in online mode.</span></span> <span data-ttu-id="762ee-140">Se você alternar o PDV para o modo offline, não poderá retomar essas transações suspensas, pois elas já foram removidas do banco de dados offline.</span><span class="sxs-lookup"><span data-stu-id="762ee-140">If you switch the POS back to offline mode, you won't be able to resume those suspended transaction, because they have already been removed from the offline database.</span></span>

### <a name="void-a-suspended-transaction"></a><span data-ttu-id="762ee-141">Anular a transação suspensa</span><span class="sxs-lookup"><span data-stu-id="762ee-141">Void a suspended transaction</span></span>

<span data-ttu-id="762ee-142">Você pode anular transações suspensas recuperando a transação e, depois, executando a operação, **Anular transação** ou pode selecionar a transação na lista **Recuperar transação** e selecionar **Anular** na barra de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="762ee-142">You can void suspended transactions either by recalling the transaction and then performing the **Void transaction** operation, or by selecting the transaction in the **Recall transaction** list and selecting **Void** on the app bar.</span></span> <span data-ttu-id="762ee-143">Como alternativa, a loja pode ser configurada para solicitar aos usuários que anulem transações suspensas ao fecharem o turno.</span><span class="sxs-lookup"><span data-stu-id="762ee-143">Alternatively, the store can be configured to prompt users to void suspended transactions when they close their shift.</span></span>