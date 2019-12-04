---
title: Insights de pagamento de cliente (Visualização)
description: Este tópico descreve o recurso de insights de pagamento que ajuda a melhorar a compreensão das práticas típicas de pagamento dos clientes específicos e pode identificar condições que justifiquem iniciar processos de cobrança mais cedo do que você fazia.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f9f1e4ae4270380c88069723e768fd44ecf8c113
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773898"
---
# <a name="customer-payment-insights-preview"></a><span data-ttu-id="7f322-103">Insights de pagamento de cliente (Visualização)</span><span class="sxs-lookup"><span data-stu-id="7f322-103">Customer payment insights (Preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="7f322-104">Este tópico descreve o recurso de insights de pagamento que ajuda a melhorar a compreensão das práticas típicas de pagamento dos clientes específicos e que pode identificar condições que justifiquem iniciar processos de cobrança mais cedo do que talvez você fizesse.</span><span class="sxs-lookup"><span data-stu-id="7f322-104">This topic describes the payment insights capability that helps improve understanding of individual customers' typical payment practices and that can identify circumstances that justify initiating collection processes earlier than you might have done otherwise.</span></span> 

## <a name="overview"></a><span data-ttu-id="7f322-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="7f322-105">Overview</span></span>

<span data-ttu-id="7f322-106">As organizações geralmente acham difícil prever quando os clientes pagarão suas faturas.</span><span class="sxs-lookup"><span data-stu-id="7f322-106">Organizations often find it challenging to predict when customers will pay their invoices.</span></span> <span data-ttu-id="7f322-107">A falta de insight resulta em previsões de fluxo de caixa menos precisas, processos de cobrança que começam muito tarde e ordens liberadas para clientes que podem não cumprir seus pagamentos.</span><span class="sxs-lookup"><span data-stu-id="7f322-107">This lack of insight leads to less accurate cash flow forecasts, collections processes that start too late, and orders that are released to customers who may default on their payment.</span></span> <span data-ttu-id="7f322-108">O Insights de pagamento de cliente (versão prévia) ajuda as organizações a prever quando uma fatura de cliente será paga, ajudando a organização a criar estratégias de cobrança que aumentam a probabilidade de pagamento no prazo.</span><span class="sxs-lookup"><span data-stu-id="7f322-108">Customer payment insights (Preview) helps organizations predict when a customer invoice will be paid, helping organization create collections strategies that improve the probability of being paid on time.</span></span> 

## <a name="predictions"></a><span data-ttu-id="7f322-109">Previsões</span><span class="sxs-lookup"><span data-stu-id="7f322-109">Predictions</span></span>

<span data-ttu-id="7f322-110">As previsões de pagamento permitirão que as organizações melhorem seus processos empresariais ajudando-as a identificar facilmente as faturas que provavelmente serão pagas com atraso e a tomar as medidas apropriadas que aumentem suas chances de serem pagas no prazo.</span><span class="sxs-lookup"><span data-stu-id="7f322-110">Payment predictions will enable organizations to improve their business processes by helping them easily identify the invoices that are likely to be paid late, and to take appropriate measures that improve their chances of getting paid on time.</span></span>

<span data-ttu-id="7f322-111">Usando um modelo de aprendizado de máquina, que aproveita as faturas históricas, os pagamentos e os dados do cliente, o Insights de pagamento de cliente (versão prévia) prevê com maior precisão quando um cliente pagará uma fatura pendente.</span><span class="sxs-lookup"><span data-stu-id="7f322-111">Using a machine learning model, which leverages historical invoices, payments and customer data, Customer payment insights (Preview) more accurately predicts when a customer will pay an outstanding invoice.</span></span>

<span data-ttu-id="7f322-112">Para cada fatura em aberto, o Insights de pagamento de cliente (versão prévia) prevê três probabilidades de pagamento:</span><span class="sxs-lookup"><span data-stu-id="7f322-112">For each open invoice, Customer payment insights (Preview) predicts three payment probabilities:</span></span>

-   <span data-ttu-id="7f322-113">Probabilidade de o pagamento ser feito no prazo</span><span class="sxs-lookup"><span data-stu-id="7f322-113">Probability of payment being made on time</span></span> 
-   <span data-ttu-id="7f322-114">Probabilidade de o pagamento ser feito com atraso</span><span class="sxs-lookup"><span data-stu-id="7f322-114">Probability of payment being made late</span></span>
-   <span data-ttu-id="7f322-115">Probabilidade de o pagamento ser feito com muito atraso</span><span class="sxs-lookup"><span data-stu-id="7f322-115">Probability of payment being made very late</span></span>

<span data-ttu-id="7f322-116">Para ajudar as Organizações a entender o valor total de pagamento que elas podem esperar de um cliente em um dos três buckets, No prazo, Atrasado e Muito atrasado, o Insights de pagamento de cliente (versão prévia) também oferece uma exibição agregada de pagamentos esperados.</span><span class="sxs-lookup"><span data-stu-id="7f322-116">To help Organizations understand the total payment amount they can expect from a customer in one of the three buckets, On time, Late and Very late, Customer payment insights (Preview) also provides an aggregated view of expected payments.</span></span>

<span data-ttu-id="7f322-117">[![Exibição agregada de previsões de pagamento](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span><span class="sxs-lookup"><span data-stu-id="7f322-117">[![Aggregated view of payment predictions](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)</span></span>

<span data-ttu-id="7f322-118">Além disso, cada fatura obtém uma probabilidade de pagamento no prazo.</span><span class="sxs-lookup"><span data-stu-id="7f322-118">Also, each invoice is assigned a probability of payment on time.</span></span> <span data-ttu-id="7f322-119">Se a probabilidade de pagamento no prazo for inferior a 50%, as faturas serão marcadas com um círculo vermelho para indicar que essas faturas podem exigir atenção da cobrança.</span><span class="sxs-lookup"><span data-stu-id="7f322-119">If the probability of payment on time is less than 50%, the invoices are tagged with a red circle to  indicate that these invoices may require collections attention.</span></span> 

<span data-ttu-id="7f322-120">[![Lista de probabilidades de pagamento](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span><span class="sxs-lookup"><span data-stu-id="7f322-120">[![List of payment probabilities](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)</span></span>

<span data-ttu-id="7f322-121">O Insights de pagamento de cliente (versão prévia) também oferece informações contextuais para explicar a previsão, como os principais fatores que influenciaram as previsões, o estado atual dos negócios com o cliente e os detalhes sobre o comportamento histórico de pagamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="7f322-121">Customer Payment Insights (Preview) also provides contextual information to explain the prediction, such as the top factors that influenced the predictions, the current state of business with the customer, and details about the historical customer payment behavior.</span></span> <span data-ttu-id="7f322-122">Em muitas empresas, o processo de cobrança tem sido uma atividade reativa; o processo de cobrança não começa até a fatura ficar vencida.</span><span class="sxs-lookup"><span data-stu-id="7f322-122">In many businesses, the collections process has been a reactive activity; the collections process doesn’t start until invoices come due.</span></span> 

<span data-ttu-id="7f322-123">Com o Insights de pagamento de cliente (versão prévia), as organizações podem ser mais proativas sobre as cobranças.</span><span class="sxs-lookup"><span data-stu-id="7f322-123">With Customer payment insights (Preview), organizations can be more proactive about collections.</span></span> <span data-ttu-id="7f322-124">Elas não precisam mais esperar que as transações fiquem vencidas para iniciar o processo de cobrança.</span><span class="sxs-lookup"><span data-stu-id="7f322-124">They no longer have to wait for the transactions to become due to start the collection process.</span></span> <span data-ttu-id="7f322-125">Em vez disso, podem usar o recurso de previsão de pagamento para determinar se a cobrança proativa aumentará a probabilidade de o pagamento ser feito no prazo.</span><span class="sxs-lookup"><span data-stu-id="7f322-125">Instead, they can use the payment prediction capability to determine whether proactive collections will improve the probability of being paid on time.</span></span> <span data-ttu-id="7f322-126">A previsão de pagamento também oferece às empresas as informações necessárias para justificar o início antecipado do processo de cobrança.</span><span class="sxs-lookup"><span data-stu-id="7f322-126">Payment prediction also gives businesses the information needed to justify starting the collection process early.</span></span>

## <a name="methodology"></a><span data-ttu-id="7f322-127">Metodologia</span><span class="sxs-lookup"><span data-stu-id="7f322-127">Methodology</span></span>

<span data-ttu-id="7f322-128">O desenvolvimento e a implantação de uma solução de IA são difíceis.</span><span class="sxs-lookup"><span data-stu-id="7f322-128">Developing and deploying an AI solution is hard.</span></span> <span data-ttu-id="7f322-129">É necessário ter uma equipe de cientistas de dados, especialistas no assunto e engenheiros trabalhando por um período extenso para formular, desenvolver, implantar e manter uma solução útil de IA.</span><span class="sxs-lookup"><span data-stu-id="7f322-129">It takes a team of data scientists, subject matter experts and engineers, working for an extended period of time to formulate, develop, deploy and maintain a usable AI solution.</span></span> <span data-ttu-id="7f322-130">Estamos facilitando a implantação e o uso de soluções de IA no Finance.</span><span class="sxs-lookup"><span data-stu-id="7f322-130">We are making it easy to deploy and use AI solutions in Finance.</span></span> <span data-ttu-id="7f322-131">Estamos pré-embalando soluções de IA no Finance criadas com base no Microsoft AI Builder.</span><span class="sxs-lookup"><span data-stu-id="7f322-131">We are prepackaging AI solutions in Finance that are built on top of Microsoft AI Builder.</span></span> <span data-ttu-id="7f322-132">Um usuário final, com um único clique de botão, pode implantar a solução de IA e começar a aproveitar os benefícios das previsões inteligentes.</span><span class="sxs-lookup"><span data-stu-id="7f322-132">An end user, with the single click of button, can deploy the AI solution and start leveraging the benefits of intelligent predictions.</span></span> <span data-ttu-id="7f322-133">Se uma organização não estiver satisfeita com a precisão das previsões, um usuário avançado, novamente com um único clique, pode entrar na experiência de extensão do AI builder e então marcar ou desmarcar os campos usados para gerar previsões.</span><span class="sxs-lookup"><span data-stu-id="7f322-133">If an organization isn't satisfied with the accuracy of predictions, a power user, again using a single click, can enter the AI builder extension experience, and then select or deselect the fields used to generate predictions.</span></span> <span data-ttu-id="7f322-134">Quando prontas, elas poderão treinar e publicar as alterações, e o modelo recém-treinado será automaticamente escolhido para previsões no Finance.</span><span class="sxs-lookup"><span data-stu-id="7f322-134">Once ready, they can train and publish the changes, and the newly trained model will be automatically picked up for predictions in Finance.</span></span>

## <a name="how-to-get-customer-payment-insights-preview"></a><span data-ttu-id="7f322-135">Como obter o Insights de pagamento de cliente (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="7f322-135">How to get Customer payment insights (Preview)</span></span>

<span data-ttu-id="7f322-136">Envie um email para [Insights de pagamento de cliente (versão prévia)](mailto:fiap@microsoft.com) se estiver interessado em experimentar o Insights de pagamento de cliente (versão prévia).</span><span class="sxs-lookup"><span data-stu-id="7f322-136">Please send email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in trying the Customer payment insights (Preview).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="7f322-137">Aviso de Privacidade</span><span class="sxs-lookup"><span data-stu-id="7f322-137">Privacy Notice</span></span>

<span data-ttu-id="7f322-138">As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="7f322-138">Previews (1) may utilize less privacy and security measures than the Dynamics 365 Finance and Operations service, (2) are not included in the service level agreement for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) has limited support.</span></span>


