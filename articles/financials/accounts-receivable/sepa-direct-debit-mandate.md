---
title: "Configurar cartas de ordem de débito direto SEPA"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8b50c2d585c7e0bcd8dc15aa70446cd7346ad33c
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-sepa-direct-debit-mandate"></a><span data-ttu-id="5d4a2-102">Configurar cartas de ordem de débito direto SEPA</span><span class="sxs-lookup"><span data-stu-id="5d4a2-102">Set up SEPA direct debit mandate</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="5d4a2-103">Um débito direto de SEPA (Área Única de Pagamentos em Euros) permite que um credor colete fundos da conta bancária de um cliente, desde que um mandato assinado tenha sido concedido pelo cliente ao credor.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-103">A Single Euro Payment Area (SEPA) direct debit lets a creditor collect funds from a customer's bank account, provided that the customer has granted a signed mandate to the creditor.</span></span> <span data-ttu-id="5d4a2-104">O cliente assina um mandato que autoriza o credor a cobrar um pagamento e a instruir o banco do cliente para pagar a cobrança.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-104">The mandate that the customer signs authorizes the creditor to collect a payment and instructs the customer's bank to pay the collection.</span></span> <span data-ttu-id="5d4a2-105">Este tópico está organizado para mostrar o processo de criação de mandatos de débito direto da SEPA.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-105">This topic is organized to show the process for setting up SEPA direct debit mandates.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d4a2-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5d4a2-106">Prerequisites</span></span>
<span data-ttu-id="5d4a2-107">A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-107">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="5d4a2-108">Categoria</span><span class="sxs-lookup"><span data-stu-id="5d4a2-108">Category</span></span>       | <span data-ttu-id="5d4a2-109">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="5d4a2-109">Prerequisite</span></span>                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="5d4a2-110">País/região</span><span class="sxs-lookup"><span data-stu-id="5d4a2-110">Country/region</span></span> | <span data-ttu-id="5d4a2-111">O endereço principal da entidade legal deve estar nos seguintes países/regiões: Áustria, Bélgica, Alemanha, Espanha, França, Itália, ou Países Baixos.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-111">The primary address for the legal entity must be in the following countries/regions: Austria, Belgium, Germany, Spain, France, Italy, or the Netherlands.</span></span> |

1. <span data-ttu-id="5d4a2-112">Configurar uma sequência de números para mandatos de débito direto. Cada mandato de débito direto deve ter um número único.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-112">Set up a number sequence for direct debit mandates Each direct debit mandate must have a unique number.</span></span> <span data-ttu-id="5d4a2-113">Use a página **Sequências numéricas** para criar uma sequência numérica para mandatos de débito direto.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-113">Use the **Number sequences** page to create a number sequence for direct debit mandates.</span></span> <span data-ttu-id="5d4a2-114">Você usará esse identificador para atribuir a sequência numérica ao sistema de mandato de débito direto na página **Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-114">You will use this identifier to assign the number sequence to the direct debit mandate system on the **Accounts receivable parameters** page.</span></span>

2. <span data-ttu-id="5d4a2-115">Configurar parâmetros de contas a receber para mandatos de débito direto Use a página **Parâmetros de contas a receber** para definir parâmetros para mandatos de débito direto.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-115">Set up Accounts receivable parameters for direct debit mandates Use the **Accounts receivable parameters** page to set up parameters for direct debit mandates.</span></span> <span data-ttu-id="5d4a2-116">Para configurar os parâmetros, na guia **Débito direto**, altere os parâmetros padrão conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-116">To set up the parameters, on the **Direct debit** tab, change the default parameters as you require.</span></span> <span data-ttu-id="5d4a2-117">Em seguida, na guia **Sequências numéricas**, atualize o campo **ID de carta de ordem de débito direto** com a sequência de números que você configurou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-117">Then, on the **Number sequences** tab, update the **Direct debit mandate ID** field with the number sequence that you set up earlier.</span></span>

3. <span data-ttu-id="5d4a2-118">Definir um método de pagamento para mandatos de débito direto. É necessário configurar um método de pagamento para mandatos de débito direto.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-118">Set up a method of payment for direct debit mandates You must set up a method of payment for direct debit mandates.</span></span> <span data-ttu-id="5d4a2-119">Use esse método de pagamento para consultar faturas para as quais serão gerados pagamentos de débito direto.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-119">You use this method of payment to query for invoices to generate direct debit payments for.</span></span> <span data-ttu-id="5d4a2-120">Use a página **Métodos de pagamento** para configurar o método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-120">Use the **Methods of payment** page to set up the method of payment.</span></span> <span data-ttu-id="5d4a2-121">Para configurar um método de pagamento para mandatos de débito direto, você deve seguir essas etapas adicionais para um método de pagamento:</span><span class="sxs-lookup"><span data-stu-id="5d4a2-121">To set up a method of payment for direct debit mandates, you must follow these additional steps for a method of payment:</span></span>

-   <span data-ttu-id="5d4a2-122">No campo **Tipo de pagamento**, selecione **Pagamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-122">In the **Payment type** field, select **Electronic payment**.</span></span>
-   <span data-ttu-id="5d4a2-123">Opcional: se você espera que cada um de seus clientes tenha vários mandatos, no campo **Período**, selecione **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-123">Optional: If you expect each of your customers to have multiple mandates, in the **Period** field, select **Invoice**.</span></span> <span data-ttu-id="5d4a2-124">Um pagamento separado será criado para cada fatura e cada pagamento usará o mandato especificado para a fatura.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-124">A separate payment will be created for each invoice, and each payment will use the mandate that is specified for the invoice.</span></span>
-   <span data-ttu-id="5d4a2-125">Selecione a opção **Exigir mandato** para criar pagamentos usando mandatos de débito direto.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-125">Select the **Require mandate** option to create payments by using direct debit mandates.</span></span> <span data-ttu-id="5d4a2-126">A opção **Exigir mandato** só estará disponível se você selecionar **Pagamento eletrônico** no campo **Tipo de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="5d4a2-126">The **Require mandate** option is available only if you select **Electronic payment** in the **Payment type** field.</span></span>

<span data-ttu-id="5d4a2-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5d4a2-127">See Also</span></span>

[<span data-ttu-id="5d4a2-128">Visão geral do débito direto</span><span class="sxs-lookup"><span data-stu-id="5d4a2-128">Direct debit overview</span></span>](sepa-direct-debit-overview.md) 

[<span data-ttu-id="5d4a2-129">Criar um mandato de débito direto para um cliente</span><span class="sxs-lookup"><span data-stu-id="5d4a2-129">Create a direct debit mandate for a customer</span></span>](tasks/create-direct-debit-mandate-customer.md) 


