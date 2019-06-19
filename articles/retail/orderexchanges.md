---
title: Configurar e processar uma troca em uma ordem de devolução
description: Este tópico explica como configurar uma troca em uma devolução no Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 43571099727830e81c41416b6fe250dba398b3f8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561378"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a><span data-ttu-id="bd6cc-103">Configurar e processar uma troca em uma ordem de devolução</span><span class="sxs-lookup"><span data-stu-id="bd6cc-103">Configure and process an exchange on a return order</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bd6cc-104">Em versões anteriores do Microsoft Dynamics 365 for Retail, as devoluções de ordens de clientes eram processadas usando-se o documento de ordem de devolução no Retail Headquarters.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-104">In previous versions of Microsoft Dynamics 365 for Retail, returns against customer orders were processed by using the return order document in Retail Headquarters.</span></span> <span data-ttu-id="bd6cc-105">No entanto, o documento de ordem de devolução pode ser usado para processar somente os produtos que estão sendo devolvidos.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-105">However, the return order document can be used to process only products that are being returned.</span></span> <span data-ttu-id="bd6cc-106">Os produtos devolvidos são indicados por uma quantidade negativa nas linhas da ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-106">The returned products are indicated by a negative quantity on the return order lines.</span></span> <span data-ttu-id="bd6cc-107">Em contraste, as vendas são indicadas por uma quantidade positiva.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-107">By contrast, sales are indicated by a positive quantity.</span></span> <span data-ttu-id="bd6cc-108">Entretanto, o documento de ordem de devolução não suporta quantidades positivas.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-108">However, the return order document doesn't support positive quantities.</span></span> <span data-ttu-id="bd6cc-109">Devido a essa limitação, versões anteriores do Retail não oferecem suporte aos cenários em que trocas de produto são feitas usando o documento de ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-109">Because of this limitation, previous versions of Retail didn't support scenarios where product exchanges are done by using the return order document.</span></span>

<span data-ttu-id="bd6cc-110">Entretanto, a funcionalidade foi adicionada para dar suporte a cenários em que as trocas são feitas sobre ordens de devolução.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-110">However, functionality has been added to support scenarios where exchanges are done on return orders.</span></span> <span data-ttu-id="bd6cc-111">O Retail agora usa o documento da ordem de venda em vez do documento da ordem de devolução para processar esses tipos de transações.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-111">Retail now uses the sales order document instead of the return order document to process these types of transactions.</span></span>

## <a name="configure-retail-to-support-exchanges-on-return-orders"></a><span data-ttu-id="bd6cc-112">Configure o Retail para oferecer suporte para trocas sobre ordens de devolução</span><span class="sxs-lookup"><span data-stu-id="bd6cc-112">Configure Retail to support exchanges on return orders</span></span>

<span data-ttu-id="bd6cc-113">Siga as etapas a seguir para configurar o sistema para dar suporte a trocas sobre ordens de devolução.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-113">Follow these steps to configure the system to support exchanges on return orders.</span></span>

1. <span data-ttu-id="bd6cc-114">Vá para **Varejo \> Configuração da sede \> Parâmetros \> Parâmetros de varejo**.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-114">Go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**.</span></span> <span data-ttu-id="bd6cc-115">Na FastTab **Ordens de cliente**, defina a opção **Processar ordens de devolução como ordens de venda** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-115">On the **Customer orders** FastTab, set the **Process return orders as sales orders** option to **Yes**.</span></span>
2. <span data-ttu-id="bd6cc-116">Execute o trabalho **Agenda de distribuição global de configuração** (**1110**).</span><span class="sxs-lookup"><span data-stu-id="bd6cc-116">Run the **Global configuration distribution schedule** job (**1110**).</span></span>

## <a name="make-an-exchange"></a><span data-ttu-id="bd6cc-117">Fazer uma troca</span><span class="sxs-lookup"><span data-stu-id="bd6cc-117">Make an exchange</span></span>

<span data-ttu-id="bd6cc-118">Depois que o sistema for configurado como descrito na seção anterior, o usuário do PDV (ponto de venda) ainda selecionará uma ordem de venda ou fatura de venda para processar uma devolução, como em versões anteriores do Retail.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-118">After the system is configured as described in the previous section, the point of sale (POS) user will still select a sales order or sales invoice to process a return, as in previous versions of Retail.</span></span> <span data-ttu-id="bd6cc-119">No entanto, depois que os itens de devolução forem adicionados ao carrinho, o usuário poderá adicionar novas linhas de venda ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-119">However, after the return items are added to the cart, the user will be able to add new sales lines to the cart.</span></span>

<span data-ttu-id="bd6cc-120">Para essas novas linhas de venda, o usuário deve definir todos os atributos necessários para processar uma linha da ordem de cliente.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-120">For these new sales lines, the user must define all the attributes that are required in order to process a customer order line.</span></span> <span data-ttu-id="bd6cc-121">Esses atributos incluem o método de entrega e o local de atendimento.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-121">These attributes include the delivery method and fulfillment location.</span></span> <span data-ttu-id="bd6cc-122">O pagamento que é devido para a transação será um pagamento líquido das linhas da ordem de devolução e das linhas da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-122">The payment that is due for the transaction will be a net of the return order lines and sales order lines.</span></span> <span data-ttu-id="bd6cc-123">Quando o pagamento for proposto para a transação, a ordem de devolução será lançada como um documento de ordem de venda no Retail Headquarters, e o sistema fará imediatamente o faturamento das linhas de devolução.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-123">When payment is tendered for the transaction, the return order will be posted as a sales order document in Retail Headquarters, and the system will immediately invoice the return lines.</span></span>

<span data-ttu-id="bd6cc-124">Para fornecer uma melhor visibilidade dos vários valores do carrinho, três novos campos de valores foram adicionados ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-124">To provide better visibility into the various amounts for the cart, three new amount fields have been added to the cart.</span></span> <span data-ttu-id="bd6cc-125">Você pode usar o designer de tela para disponibilizar esses novos campos na IU (interface de usuário) do POS.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-125">You can use the screen designer to make these new fields available in the POS user interface (UI).</span></span>

- <span data-ttu-id="bd6cc-126">**Depósito aplicado** – O valor de depósito aplicado em uma transação quando o usuário faz uma retirada por ordem de cliente.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-126">**Deposit applied** – The deposit amount that is applied on a transaction when the user does a customer order pickup.</span></span> <span data-ttu-id="bd6cc-127">Se não houver sobreposição de depósito, e um depósito de 10% estiver configurado, o valor neste campo será de 90% do valor total da ordem do cliente.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-127">If there is no deposit override, and a 10-percent deposit is configured, the amount in this field is 90 percent of the total amount of the customer order.</span></span>
- <span data-ttu-id="bd6cc-128">**Executar valor** – O valor total das linhas em que o modo de entrega foi definido como **Executar** quando a ordem de cliente foi criada ou editada, ou durante uma troca da ordem de cliente.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-128">**Carry out amount** – The total amount for lines where the delivery mode was set to **Carry out** when the customer order was created or edited, or during a customer order exchange.</span></span> <span data-ttu-id="bd6cc-129">O valor neste campo inclui impostos e encargos.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-129">The amount in this field includes taxes and charges.</span></span>
- <span data-ttu-id="bd6cc-130">**Valor da devolução** – O valor total das linhas que têm quantidades negativas durante a troca da ordem do cliente.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-130">**Return amount** – The total amount for lines that have negative quantities during the customer order exchange.</span></span> <span data-ttu-id="bd6cc-131">O valor neste campo inclui impostos e encargos.</span><span class="sxs-lookup"><span data-stu-id="bd6cc-131">The amount in this field includes taxes and charges.</span></span>
