---
title: Configurar carta de ordem de débito direto SEPA
description: Um débito direto de SEPA (Área Única de Pagamentos em Euros) permite que um credor colete fundos da conta bancária de um cliente, desde que um mandato assinado tenha sido concedido pelo cliente ao credor.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 24803e7157edc87e73eb6c8af404311bdf8fc5c5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245607"
---
# <a name="set-up-sepa-direct-debit-mandate"></a><span data-ttu-id="a3c45-103">Configurar carta de ordem de débito direto SEPA</span><span class="sxs-lookup"><span data-stu-id="a3c45-103">Set up SEPA direct debit mandate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a3c45-104">Um débito direto de SEPA (Área Única de Pagamentos em Euros) permite que um credor colete fundos da conta bancária de um cliente, desde que um mandato assinado tenha sido concedido pelo cliente ao credor.</span><span class="sxs-lookup"><span data-stu-id="a3c45-104">A Single Euro Payment Area (SEPA) direct debit lets a creditor collect funds from a customer's bank account, provided that the customer has granted a signed mandate to the creditor.</span></span> <span data-ttu-id="a3c45-105">O cliente assina um mandato que autoriza o credor a cobrar um pagamento e a instruir o banco do cliente para pagar a cobrança.</span><span class="sxs-lookup"><span data-stu-id="a3c45-105">The mandate that the customer signs authorizes the creditor to collect a payment and instructs the customer's bank to pay the collection.</span></span> <span data-ttu-id="a3c45-106">Este tópico está organizado para mostrar o processo de criação de mandatos de débito direto da SEPA.</span><span class="sxs-lookup"><span data-stu-id="a3c45-106">This topic is organized to show the process for setting up SEPA direct debit mandates.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a3c45-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a3c45-107">Prerequisites</span></span>
<span data-ttu-id="a3c45-108">A tabela a seguir mostra os pré-requisitos que devem estar funcionando antes de começar.</span><span class="sxs-lookup"><span data-stu-id="a3c45-108">The following table shows the prerequisites that must be in place before you start.</span></span>

| <span data-ttu-id="a3c45-109">Categoria</span><span class="sxs-lookup"><span data-stu-id="a3c45-109">Category</span></span>       | <span data-ttu-id="a3c45-110">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="a3c45-110">Prerequisite</span></span>                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="a3c45-111">País/região</span><span class="sxs-lookup"><span data-stu-id="a3c45-111">Country/region</span></span> | <span data-ttu-id="a3c45-112">O endereço principal da entidade legal deve estar nos seguintes países/regiões: Áustria, Bélgica, Alemanha, Espanha, França, Itália, ou Países Baixos.</span><span class="sxs-lookup"><span data-stu-id="a3c45-112">The primary address for the legal entity must be in the following countries/regions: Austria, Belgium, Germany, Spain, France, Italy, or the Netherlands.</span></span> |

1. <span data-ttu-id="a3c45-113">Configurar uma sequência de números para mandatos de débito direto. Cada mandato de débito direto deve ter um número único.</span><span class="sxs-lookup"><span data-stu-id="a3c45-113">Set up a number sequence for direct debit mandates Each direct debit mandate must have a unique number.</span></span> <span data-ttu-id="a3c45-114">Use a página **Sequências numéricas** para criar uma sequência numérica para mandatos de débito direto.</span><span class="sxs-lookup"><span data-stu-id="a3c45-114">Use the **Number sequences** page to create a number sequence for direct debit mandates.</span></span> <span data-ttu-id="a3c45-115">Você usará esse identificador para atribuir a sequência numérica ao sistema de mandato de débito direto na página **Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="a3c45-115">You will use this identifier to assign the number sequence to the direct debit mandate system on the **Accounts receivable parameters** page.</span></span>

2. <span data-ttu-id="a3c45-116">Configurar parâmetros de contas a receber para mandatos de débito direto Use a página **Parâmetros de contas a receber** para definir parâmetros para mandatos de débito direto.</span><span class="sxs-lookup"><span data-stu-id="a3c45-116">Set up Accounts receivable parameters for direct debit mandates Use the **Accounts receivable parameters** page to set up parameters for direct debit mandates.</span></span> <span data-ttu-id="a3c45-117">Para configurar os parâmetros, na guia **Débito direto**, altere os parâmetros padrão conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="a3c45-117">To set up the parameters, on the **Direct debit** tab, change the default parameters as you require.</span></span> <span data-ttu-id="a3c45-118">Em seguida, na guia **Sequências numéricas**, atualize o campo **ID de carta de ordem de débito direto** com a sequência de números que você configurou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a3c45-118">Then, on the **Number sequences** tab, update the **Direct debit mandate ID** field with the number sequence that you set up earlier.</span></span>

3. <span data-ttu-id="a3c45-119">Definir um método de pagamento para mandatos de débito direto. É necessário configurar um método de pagamento para mandatos de débito direto.</span><span class="sxs-lookup"><span data-stu-id="a3c45-119">Set up a method of payment for direct debit mandates You must set up a method of payment for direct debit mandates.</span></span> <span data-ttu-id="a3c45-120">Use esse método de pagamento para consultar faturas para as quais serão gerados pagamentos de débito direto.</span><span class="sxs-lookup"><span data-stu-id="a3c45-120">You use this method of payment to query for invoices to generate direct debit payments for.</span></span> <span data-ttu-id="a3c45-121">Use a página **Métodos de pagamento** para configurar o método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a3c45-121">Use the **Methods of payment** page to set up the method of payment.</span></span> <span data-ttu-id="a3c45-122">Para configurar um método de pagamento para mandatos de débito direto, você deve seguir essas etapas adicionais para um método de pagamento:</span><span class="sxs-lookup"><span data-stu-id="a3c45-122">To set up a method of payment for direct debit mandates, you must follow these additional steps for a method of payment:</span></span>

-   <span data-ttu-id="a3c45-123">No campo **Tipo de pagamento**, selecione **Pagamento eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="a3c45-123">In the **Payment type** field, select **Electronic payment**.</span></span>
-   <span data-ttu-id="a3c45-124">Opcional: se você espera que cada um de seus clientes tenha vários mandatos, no campo **Período**, selecione **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="a3c45-124">Optional: If you expect each of your customers to have multiple mandates, in the **Period** field, select **Invoice**.</span></span> <span data-ttu-id="a3c45-125">Um pagamento separado será criado para cada fatura e cada pagamento usará o mandato especificado para a fatura.</span><span class="sxs-lookup"><span data-stu-id="a3c45-125">A separate payment will be created for each invoice, and each payment will use the mandate that is specified for the invoice.</span></span>
-   <span data-ttu-id="a3c45-126">Selecione a opção **Exigir mandato** para criar pagamentos usando mandatos de débito direto.</span><span class="sxs-lookup"><span data-stu-id="a3c45-126">Select the **Require mandate** option to create payments by using direct debit mandates.</span></span> <span data-ttu-id="a3c45-127">A opção **Exigir mandato** só estará disponível se você selecionar **Pagamento eletrônico** no campo **Tipo de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a3c45-127">The **Require mandate** option is available only if you select **Electronic payment** in the **Payment type** field.</span></span>

<span data-ttu-id="a3c45-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a3c45-128">Additional resources</span></span>

[<span data-ttu-id="a3c45-129">Visão geral de débito direto SEPA</span><span class="sxs-lookup"><span data-stu-id="a3c45-129">SEPA direct debit overview</span></span>](sepa-direct-debit-overview.md) 

[<span data-ttu-id="a3c45-130">Criar um mandato de débito direto para um cliente</span><span class="sxs-lookup"><span data-stu-id="a3c45-130">Create a direct debit mandate for a customer</span></span>](tasks/create-direct-debit-mandate-customer.md) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]