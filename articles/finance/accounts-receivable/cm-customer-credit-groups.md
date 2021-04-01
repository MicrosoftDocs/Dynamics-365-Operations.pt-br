---
title: Grupos de crédito de cliente
description: Este tópico fornece informações sobre grupos de crédito de cliente.
author: mikefalkner
manager: AnnBe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76b1e93d562e66cb8d4c5819a749459ea8783b1e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237533"
---
# <a name="customer-credit-groups"></a><span data-ttu-id="342a0-103">Grupos de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="342a0-103">Customer credit groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="342a0-104">Você pode definir grupos de clientes que têm um limite de crédito compartilhado.</span><span class="sxs-lookup"><span data-stu-id="342a0-104">You can define groups of customers who have a shared credit limit.</span></span> <span data-ttu-id="342a0-105">O limite de crédito individual definido na conta de fatura de cliente também é considerado.</span><span class="sxs-lookup"><span data-stu-id="342a0-105">The individual credit limit that is defined on the customer invoice account is also considered.</span></span>

<span data-ttu-id="342a0-106">É possível selecionar membros de um grupo de crédito de cliente de diferentes entidades legais.</span><span class="sxs-lookup"><span data-stu-id="342a0-106">Members of a customer credit group can be selected from different legal entities.</span></span> <span data-ttu-id="342a0-107">Quando você adiciona um cliente à lista de clientes no grupo de crédito de cliente, a data de vencimento do limite de crédito de cada cliente é alterada para a data de vencimento atribuída ao grupo.</span><span class="sxs-lookup"><span data-stu-id="342a0-107">When you add a customer to the list of customers in the customer credit group, the expiration date of the credit limit for each customer is changed to the expiration date that is assigned to the group.</span></span>

<span data-ttu-id="342a0-108">Você pode configurar grupos de crédito de cliente na página **Grupos de crédito de cliente** (**Gerenciamento de crédito \> Grupos de crédito de cliente \> Grupos de crédito de cliente**).</span><span class="sxs-lookup"><span data-stu-id="342a0-108">You can set up customer credit groups on the **Customer credit groups** page (**Credit management \> Customer credit groups \> Customer credit groups**).</span></span>

1. <span data-ttu-id="342a0-109">Nos campos **Número do grupo** e **Descrição**, insira um identificador e uma descrição para o grupo.</span><span class="sxs-lookup"><span data-stu-id="342a0-109">In the **Group number** and **Description** fields, enter an identifier and description for the group.</span></span>
2. <span data-ttu-id="342a0-110">Nos campos **Limite de crédito** e **Moeda**, insira o limite de crédito e a moeda que deverão ser usados quando o sistema verificar o limite de crédito de qualquer membro do grupo.</span><span class="sxs-lookup"><span data-stu-id="342a0-110">In the **Credit limit** and **Currency** fields, enter the credit limit and currency that should be used when the system checks the credit limit for any member of the group.</span></span>
3. <span data-ttu-id="342a0-111">No campo **Limite de crédito até a data**, insira a data em que vence o limite de crédito.</span><span class="sxs-lookup"><span data-stu-id="342a0-111">In the **Credit limit to date** field, enter the date when the credit limit expires.</span></span> <span data-ttu-id="342a0-112">Os grupos de crédito de cliente devem ter uma data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="342a0-112">Customer credit groups must have an expiration date.</span></span>

<span data-ttu-id="342a0-113">Depois de concluir a configuração de um grupo de crédito de cliente, você poderá adicionar clientes especificando a entidade legal e a ID de conta de cliente deles.</span><span class="sxs-lookup"><span data-stu-id="342a0-113">After you've finished setting up a customer credit group, you can add customers to it by specifying their legal entity and customer account ID.</span></span> <span data-ttu-id="342a0-114">Ao adicionar um novo cliente a um grupo de crédito de cliente, o sistema procura a mesma conta de cliente em todas as entidades legais e solicita que você a adicione ao grupo de crédito de cliente.</span><span class="sxs-lookup"><span data-stu-id="342a0-114">When you add a new customer to a customer credit group, the system searches for the same customer account across all legal entities and prompts you to add it to the customer credit group.</span></span>

<span data-ttu-id="342a0-115">Use o menu **Saldos antigos** para ver os detalhes do saldo antigo de todos os clientes da fatura em um grupo de crédito de cliente.</span><span class="sxs-lookup"><span data-stu-id="342a0-115">Use the **Aged balances** menu to view the details of the aging balance for all invoice customers in a customer credit group.</span></span> <span data-ttu-id="342a0-116">A página **Saldo antigo** mostra um resumo dos saldos antigos das contas de cliente da fatura.</span><span class="sxs-lookup"><span data-stu-id="342a0-116">The **Aging balance** page shows a summary of the aged balances for the invoice customer accounts.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]