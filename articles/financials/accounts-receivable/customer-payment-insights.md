---
title: Informações de pagamento do cliente (visualização)
description: Este tópico descreve como as informações de pagamento do cliente podem ajudar a prever quando uma fatura será paga e ajudar as organizações a criar estratégias de otimização que melhorem a probabilidade de serem pagas no prazo.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "344653"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="0f168-103">Informações de pagamento do cliente (visualização)</span><span class="sxs-lookup"><span data-stu-id="0f168-103">Customer payment insights (preview)</span></span>

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="0f168-104">Esse recurso faz parte de uma versão direcionada e está disponível somente para os usuários que optaram pela visualização privada.</span><span class="sxs-lookup"><span data-stu-id="0f168-104">This feature is part of a targeted release and is only available to users who have opted into the Private Preview.</span></span> <span data-ttu-id="0f168-105">Esse recurso estará incluído em uma futura versão de disponibilidade geral.</span><span class="sxs-lookup"><span data-stu-id="0f168-105">This feature will be included in an upcoming general availability release.</span></span>

# <a name="overview"></a><span data-ttu-id="0f168-106">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="0f168-106">Overview</span></span>

<span data-ttu-id="0f168-107">As organizações geralmente acham difícil prever quando um cliente pagará suas faturas.</span><span class="sxs-lookup"><span data-stu-id="0f168-107">Organizations often find it challenging to predict when a customer will pay their invoices.</span></span> <span data-ttu-id="0f168-108">Essa falta de informações pode resultar em previsões de fluxo de caixa imprecisas, em processos de cobrança ineficientes e na possibilidade de liberação de ordens para clientes que podem representar um risco de crédito.</span><span class="sxs-lookup"><span data-stu-id="0f168-108">This lack of insight can lead to inaccurate cash flow forecasts, inefficient collection processes, and the possibility of orders being released to customers who may pose a credit risk.</span></span> <span data-ttu-id="0f168-109">As informações de pagamento do cliente (visualização) usam o aprendizado de máquina para prever quando uma fatura será paga.</span><span class="sxs-lookup"><span data-stu-id="0f168-109">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="0f168-110">Também fornecem estratégias de otimização que podem ser adaptadas para maximizar a probabilidade de os clientes pagarem no prazo.</span><span class="sxs-lookup"><span data-stu-id="0f168-110">It also provides optimization strategies that can be tailored to maximize the probability of customers paying on time.</span></span>

## <a name="predictions"></a><span data-ttu-id="0f168-111">Previsões</span><span class="sxs-lookup"><span data-stu-id="0f168-111">Predictions</span></span>

<span data-ttu-id="0f168-112">As previsões de pagamento permitem que as organizações aperfeiçoem seus processos de negócios, ajudando a:</span><span class="sxs-lookup"><span data-stu-id="0f168-112">Payment predictions allow organizations to improve their business processes by helping to:</span></span>

-   <span data-ttu-id="0f168-113">Identificar facilmente as faturas com previsão de pagamento atrasado.</span><span class="sxs-lookup"><span data-stu-id="0f168-113">Easily identify the invoices that are predicted to be paid late.</span></span>
-   <span data-ttu-id="0f168-114">Tomar medidas apropriadas para melhorar as chances de ser pago no prazo.</span><span class="sxs-lookup"><span data-stu-id="0f168-114">Take appropriate measures to improve chances of getting paid on time.</span></span>

<span data-ttu-id="0f168-115">As informações de pagamento do cliente (visualização) usam o aprendizado de máquina para prever quando uma fatura será paga.</span><span class="sxs-lookup"><span data-stu-id="0f168-115">Customer payment insights (preview) uses machine learning to predict when an invoice will be paid.</span></span> <span data-ttu-id="0f168-116">Usam dados históricos de faturas, pagamentos e clientes para criar um modelo de aprendizado de máquina que é usado para prever quando uma fatura será paga.</span><span class="sxs-lookup"><span data-stu-id="0f168-116">It uses historical invoice, payment, and customer data to create a machine learning model that is used to predict when an invoice will be paid.</span></span>

<span data-ttu-id="0f168-117">Para cada fatura em aberto, as informações de pagamento do cliente (visualização) preveem três probabilidades de pagamento:</span><span class="sxs-lookup"><span data-stu-id="0f168-117">For each open invoice, Customer payment insights (preview) predicts three payment probabilities:</span></span>

-  <span data-ttu-id="0f168-118">Probabilidade de o pagamento ser feito no prazo (dentro da data de vencimento da fatura).</span><span class="sxs-lookup"><span data-stu-id="0f168-118">Probability of payment being made on time (within the invoice due date).</span></span>
-  <span data-ttu-id="0f168-119">Probabilidade de o pagamento ser feito em até 30 dias após a data de vencimento da fatura.</span><span class="sxs-lookup"><span data-stu-id="0f168-119">Probability of payment being made within 30 days of the invoice due date.</span></span>
-  <span data-ttu-id="0f168-120">Probabilidade de o pagamento ser feito além dos 30 dias após a data de vencimento da fatura.</span><span class="sxs-lookup"><span data-stu-id="0f168-120">Probability of payment being made beyond 30 days of the invoice due date.</span></span>

<span data-ttu-id="0f168-121">A probabilidade de pagamentos pode ser visualizada na seção de previsão.</span><span class="sxs-lookup"><span data-stu-id="0f168-121">The probability of payments can be viewed in the prediction section.</span></span>

<span data-ttu-id="0f168-122">[![Previsões de pagamento](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span><span class="sxs-lookup"><span data-stu-id="0f168-122">[![Payment predictions](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)</span></span>

<span data-ttu-id="0f168-123">Também se atribui a cada fatura uma probabilidade de pagamento vencedora usando um dos três cenários de probabilidade de pagamento previstos que foram definidos acima.</span><span class="sxs-lookup"><span data-stu-id="0f168-123">Each invoice is also assigned a winning probability of payment using one of the three predicted payment probabilities scenarios defined above.</span></span> <span data-ttu-id="0f168-124">O cenário com maior probabilidade de pagamento é o cenário vencedor.</span><span class="sxs-lookup"><span data-stu-id="0f168-124">The scenario with the highest probability of payment is the winning scenario.</span></span>


<span data-ttu-id="0f168-125">Por exemplo, vamos supor que a previsão mostre uma probabilidade de 71% de que uma determinada fatura seja paga no prazo, 13% de probabilidade de que ela seja paga em até 30 dias após a data de vencimento e 16% de probabilidade de que ela seja paga além dos 30 dias após a data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="0f168-125">For example, let’s assume for an invoice the prediction shows a 71 percent probability that the invoice will be paid on time, 13 percent probability that the invoice will be paid within 30 days of due date, and 16 percent probability that the invoice will be paid beyond 30 days of the due date.</span></span> <span data-ttu-id="0f168-126">Como a maior probabilidade mostra que a fatura estará no cenário em que o prazo é respeitado, a fatura será marcada com a probabilidade de ser paga a tempo.</span><span class="sxs-lookup"><span data-stu-id="0f168-126">The highest probability shows that the invoice will be in the on-time scenario, so the invoice will be tagged with the probability of being paid on time.</span></span>

<span data-ttu-id="0f168-127">[![Previsões de pagamento](./media/payment-predict.png)](./media/payment-predict.png)</span><span class="sxs-lookup"><span data-stu-id="0f168-127">[![Payment predictions](./media/payment-predict.png)](./media/payment-predict.png)</span></span>

## <a name="optimization-strategies"></a><span data-ttu-id="0f168-128">Estratégias de otimização</span><span class="sxs-lookup"><span data-stu-id="0f168-128">Optimization strategies</span></span>

<span data-ttu-id="0f168-129">Além das previsões de pagamento, as informações de pagamento do cliente (visualização) podem usar estratégias de otimização para aperfeiçoar as chances de receber pagamentos no prazo.</span><span class="sxs-lookup"><span data-stu-id="0f168-129">In addition to payment predictions, the Customer Payment Insights (preview) can use optimization strategies to improve the chances of getting paid on time.</span></span> <span data-ttu-id="0f168-130">Com isso, as organizações podem fazer a análise "E se", permitindo que os usuários ajustem os parâmetros da fatura e do cliente e depois comparem o efeito correspondente sobre a probabilidade de receber o pagamento das faturas no prazo.</span><span class="sxs-lookup"><span data-stu-id="0f168-130">This lets organizations do 'What if' analysis by allowing users to adjust invoice and customer parameters and then compare the corresponding effect on the probability of receiving payment on invoices on time.</span></span>

<span data-ttu-id="0f168-131">Por exemplo, uma organização pode querer avaliar o efeito da atualização do desconto à vista nas faturas sobre a probabilidade de receber o pagamento no prazo.</span><span class="sxs-lookup"><span data-stu-id="0f168-131">For example, an organization may want to evaluate the effect of updating the cash discount on invoices on the probability of receiving the payment on time.</span></span> <span data-ttu-id="0f168-132">Quando as faturas são otimizadas para usar o novo desconto, os usuários podem rever o efeito da aplicação do desconto sobre a probabilidade de receber pagamentos para essas faturas a tempo.</span><span class="sxs-lookup"><span data-stu-id="0f168-132">When the invoices are optimized to use the new discount, the users can review the effect of applying the discount on the probability of receiving payments for those invoices on time.</span></span> <span data-ttu-id="0f168-133">Se o custo de aplicar o desconto for mínimo em comparação ao benefício de cobrar o pagamento no prazo, a organização pode optar por aplicar o desconto selecionado a todas as futuras ordens em aberto.</span><span class="sxs-lookup"><span data-stu-id="0f168-133">If the cost of applying the discount is minimal when compared to the benefit of collecting the payment on time, the organization may choose to apply the selected discount to all future open orders.</span></span>

> [!NOTE] 
> <span data-ttu-id="0f168-134">Atualmente, apenas o desconto está disponível como estratégia de otimização para informações de pagamento do cliente (visualização).</span><span class="sxs-lookup"><span data-stu-id="0f168-134">Currently, only discount is available as an optimization strategy for Customer payment insights (preview).</span></span>

<span data-ttu-id="0f168-135">[![Previsões otimizadas](./media/optimized-pay.png)](./media/optimized-pay.png)</span><span class="sxs-lookup"><span data-stu-id="0f168-135">[![Optimized predictions](./media/optimized-pay.png)](./media/optimized-pay.png)</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="0f168-136">Como obter informações de pagamento do cliente (visualização)</span><span class="sxs-lookup"><span data-stu-id="0f168-136">How to get Customer payment insights (preview)</span></span>

<span data-ttu-id="0f168-137">Se estiver interessado em experimentar informações de pagamento do cliente (visualização), envie um e-mail [Equipe de visualização de informações financeiras](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="0f168-137">If you are interested in trying Customer payment insights (preview), please email [Finance Insights Preview team](mailto:fiap@microsoft.com).</span></span> 

## <a name="privacy-statement"></a><span data-ttu-id="0f168-138">Política de Privacidade</span><span class="sxs-lookup"><span data-stu-id="0f168-138">Privacy Statement</span></span>

<span data-ttu-id="0f168-139">As visualizações armazenam dados de clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="0f168-139">Previews store customer data in the United States.</span></span> <span data-ttu-id="0f168-140">Além disso, as visualizações (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 for Finance and Operations, (2) não estão incluídas no contrato de nível de serviço desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="0f168-140">In addition, previews (1) may utilize less privacy and security measures than the Dynamics 365 for Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>
