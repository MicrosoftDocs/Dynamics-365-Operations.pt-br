---
title: Posição de pagamento à vista (Versão preliminar)
description: Este tópico descreve como o recurso de previsão de fluxo de caixa prevê a posição de pagamento à vista de uma organização para horários específicos. Também descreve as opções disponíveis para mostrar previsões para períodos diferentes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 5cf1ac4de07cb6357493a0b2c84f6a6ee591d4bc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990554"
---
# <a name="cash-position-preview"></a><span data-ttu-id="4b9a6-104">Posição de pagamento à vista (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="4b9a6-104">Cash position (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="4b9a6-105">Posição de pagamento à vista é a projeção do fluxo de caixa que é a previsão para o próximo termo.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-105">Cash position is the projection of cash flow that is forecast for the near term.</span></span> <span data-ttu-id="4b9a6-106">Ele se baseia na projeção de recebimentos à vista de clientes que pagam faturas e ordens pendentes, e também na projeção de pagamentos à vista que são pagos para fornecedores para faturas e ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-106">It's based on the projection of cash receipts from customers that pay outstanding invoices and orders, and also on the projection cash disbursements that are paid to vendors for purchase invoices and orders.</span></span>

<span data-ttu-id="4b9a6-107">Quando o sistema prevê os pagamentos do cliente, ele usa as previsões de pagamento do recurso de previsão de pagamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-107">When the system predicts customer payments, it uses the payment predictions from the customer payment prediction feature.</span></span> <span data-ttu-id="4b9a6-108">Sem previsões de pagamento, o tempo médio necessário para converter uma fatura de cliente para um pagamento para cada cliente é usado para calcular uma data de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-108">Without payment predictions, the average time that is required to convert a customer invoice to a payment for each customer is used to calculate a payment date.</span></span> <span data-ttu-id="4b9a6-109">Para ordens de cliente em aberto, o sistema calcula a data da fatura usando o número médio de dias para que as linhas de ordem por cliente sejam faturadas.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-109">For open customer orders, the system calculates the invoice date by using the average number of days for order lines per customer to be invoiced.</span></span> <span data-ttu-id="4b9a6-110">Em seguida, ele usa a data da fatura como entrada para a funcionalidade de previsão de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-110">It then uses the invoice date as an input for the payment prediction functionality.</span></span> <span data-ttu-id="4b9a6-111">A funcionalidade de previsão de pagamento do cliente calcula uma data de pagamento para cada linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-111">The customer payment prediction functionality calculates a payment date for each order line.</span></span> 

<span data-ttu-id="4b9a6-112"><*Texto necessário de Jarek ou Dave sobre como as previsões de pagamento são convertidas em uma data*> a data de pagamento para faturas pendentes é aproximada [*estimada*] a partir das previsões de pagamento, selecionando uma data que corresponda ao quinquagésimo percentil da função de distribuição cumulativa que é obtida das probabilidades do período previsto.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-112"><*Need text from Jarek or Dave on how payment predictions are converted to a date*> The payment date for outstanding invoices is approximated [*estimated*] from the payment predictions by picking a date that corresponds to fiftieth percentile of the cumulative distribution function that's obtained from the predicted bucket's probabilities.</span></span>

<span data-ttu-id="4b9a6-113">Uma abordagem semelhante é usada para prever pagamentos para fornecedores.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-113">A similar approach is used to predict payments to vendors.</span></span> <span data-ttu-id="4b9a6-114">Para cada fornecedor, o sistema calcula o tempo médio necessário para converter uma fatura de fornecedor para um pagamento.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-114">For each vendor, the system calculates the average time that is required to convert a vendor invoice to a payment.</span></span> <span data-ttu-id="4b9a6-115">Esse número de dias é usado para calcular a data de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-115">That number of days is then used to calculate the payment date.</span></span> <span data-ttu-id="4b9a6-116">Para ordens de fornecedor abertas, o sistema calcula a data da fatura considerando o número médio de dias necessário para converter as linhas de ordem em uma fatura para cada fornecedor.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-116">For open vendor orders, the system calculates the invoice date by considering the average number of days that is required to convert order lines to an invoice for each vendor.</span></span> <span data-ttu-id="4b9a6-117">O sistema calcula a data de pagamento usando o tempo médio necessário para converter uma fatura de fornecedor para um pagamento para cada fornecedor.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-117">The system then calculates the payment date by using the average time to convert a vendor invoice to a payment for each vendor.</span></span>

<span data-ttu-id="4b9a6-118">A seção superior da guia **Posição de pagamento à vista** inclui um gráfico de posição de pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-118">The upper section of the **Cash position** tab includes a cash position chart.</span></span> <span data-ttu-id="4b9a6-119">Esse gráfico mostra fluxos de entrada e saída de caixa e seu impacto no saldo de liquidez total.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-119">This chart shows cash inflows and outflows, and their impact on the total liquidity balance.</span></span> <span data-ttu-id="4b9a6-120">Os detalhes no gráfico de posição de pagamento à vista podem ser exibidos em períodos diários, semanais, mensais ou trimestrais.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-120">The details in the cash position chart can be viewed in daily, weekly, monthly, or quarterly periods.</span></span> <span data-ttu-id="4b9a6-121">Ao selecionar **Diariamente**, você pode exibir previsões para os próximos 21 dias.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-121">When you select **Daily**, you can view forecasts for the next 21 days.</span></span> <span data-ttu-id="4b9a6-122">Ao selecionar **Semanalmente**, você pode exibir previsões para as próximas 20 semanas.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-122">When you select **Weekly**, you can view forecasts for the next 20 weeks.</span></span> <span data-ttu-id="4b9a6-123">Ao selecionar **Mensalmente**, você pode exibir previsões para os próximos 12 meses.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-123">When you select **Monthly**, you can view forecasts for the next 12 months.</span></span> <span data-ttu-id="4b9a6-124">Ao selecionar **Trimestralmente**, você pode exibir previsões para os próximos 12 trimestres.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-124">When you select **Quarterly**, you can view forecasts for the next 12 quarters.</span></span> <span data-ttu-id="4b9a6-125">Você pode ocultar o gráfico se precisar de espaço adicional na tela para exibir o conteúdo na guia **Posição de pagamento à vista**.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-125">You can hide the chart if you require additional space on your screen to view content on the **Cash position** tab.</span></span>

<span data-ttu-id="4b9a6-126">A seção inferior da guia **Posição de pagamento à vista** mostra detalhes da posição, do fluxo de caixa, dos pagamentos projetados e da conta bancária.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-126">The lower section of the **Cash position** tab shows details for the position, cash flow, projected payments, and bank account.</span></span>

- <span data-ttu-id="4b9a6-127">As informações na grade **Detalhes da posição** são apresentadas em três seções: uma lista de contas de liquidez, uma lista de documentos que compõem fluxos de entrada de caixa e uma lista de documentos que compõem saídas de caixa.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-127">Information in the **Position details** grid is presented in three sections: a list of liquidity accounts, a list of documents that make up cash inflows, and a list of documents that make up cash outflows.</span></span> <span data-ttu-id="4b9a6-128">A grade também mostra saldos de posição de pagamento à vista.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-128">The grid also shows cash position balances.</span></span> <span data-ttu-id="4b9a6-129">Para o primeiro período que você está exibindo, o saldo das contas de liquidez é o saldo inicial.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-129">For the first period that you're viewing, the balance for the liquidity accounts is the opening balance.</span></span> <span data-ttu-id="4b9a6-130">Para períodos subsequentes, os saldos para as contas de liquidez são calculados com base na adição de entrada de caixa e na subtração de saídas de caixa de períodos anteriores.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-130">For subsequent periods, the balances for the liquidity accounts are calculated based on the addition of cash inflows and the subtraction of cash outflows from previous periods.</span></span> <span data-ttu-id="4b9a6-131">Para exibir detalhes das transações que compõem o saldo, selecione o link **Saldo**.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-131">To view details of the transactions that make up the balance, select the **Balance** link.</span></span>
- <span data-ttu-id="4b9a6-132">A grade **Fluxo de caixa** mostra entradas de caixa, saídas de caixa agregadas por período e seu impacto nos saldos de conta de liquidez.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-132">The **Cash flow** grid shows cash inflows, cash outflows aggregated per period, and their impact on liquidity account balances.</span></span> <span data-ttu-id="4b9a6-133">Para o primeiro período, o saldo das contas de liquidez é o saldo inicial.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-133">For the first period, the balance for the liquidity accounts is the opening balance.</span></span> <span data-ttu-id="4b9a6-134">Para períodos subsequentes, os saldos para as contas de liquidez são calculados com base na adição de entrada de caixa e na subtração de saídas de caixa de períodos anteriores.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-134">For subsequent periods, the balances for the liquidity accounts are calculated based on the addition of cash inflows and the subtraction of cash outflows from previous periods.</span></span>
- <span data-ttu-id="4b9a6-135">A grade **Saldo bancário projetado** mostra saídas de caixa esperadas e seu impacto nas contas de liquidez.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-135">The **Projected bank balance** grid show expected cash outflows and their impact on liquidity accounts.</span></span>
- <span data-ttu-id="4b9a6-136">A grade **Conta bancária** mostra o impacto de entradas e saídas de caixa esperada no saldo do banco.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-136">The **Bank account** grid shows the impact of expected cash inflows and outflows on the bank balance.</span></span>

<span data-ttu-id="4b9a6-137">Para salvar e editar a posição de pagamento à vista, crie um instantâneo.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-137">To save and edit the cash position, create a snapshot.</span></span> <span data-ttu-id="4b9a6-138">FoPara obter mais informações sobre como trabalhar instantâneos, consulte [Visão geral de instantâneos](payment-snapshots.md).</span><span class="sxs-lookup"><span data-stu-id="4b9a6-138">For more information about how to work with snapshots, see [Snapshots overview](payment-snapshots.md).</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="4b9a6-139">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="4b9a6-139">Privacy notice</span></span>
<span data-ttu-id="4b9a6-140">As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="4b9a6-140">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>