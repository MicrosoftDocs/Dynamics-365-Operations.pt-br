---
title: Previsão de fluxo de caixa (versão preliminar)
description: Este tópico descreve o recurso de previsão de fluxo de caixa.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/19/2020
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
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f97b8fc0896f0f7b95bf5609f94367b3a8230ca7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645239"
---
# <a name="cash-flow-forecast-preview"></a><span data-ttu-id="4504c-103">Previsão de fluxo de caixa (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="4504c-103">Cash flow forecast (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="4504c-104">O fluxo de caixa é fundamental para qualquer negócio.</span><span class="sxs-lookup"><span data-stu-id="4504c-104">Cash flow is critical to any business.</span></span> <span data-ttu-id="4504c-105">Mesmo empresas lucrativas podem enfrentar insolvência se não mantiverem o fluxo de caixa para atender às necessidades imediatas.</span><span class="sxs-lookup"><span data-stu-id="4504c-105">Even profitable companies can face insolvency if they don't maintain the cash flow to meet immediate needs.</span></span> <span data-ttu-id="4504c-106">O recurso de previsão de fluxo de caixa nos insights de finanças pode ajudar as empresas a monitorar e gerenciar seus saldos de caixa com eficácia.</span><span class="sxs-lookup"><span data-stu-id="4504c-106">The cash flow forecasting capability in Finance insights can help companies monitor and manage their cash balances effectively.</span></span> <span data-ttu-id="4504c-107">Esse recurso usa o aprendizado de máquina para ajudar as empresas a prever fluxos de caixa com mais precisão do que antes.</span><span class="sxs-lookup"><span data-stu-id="4504c-107">This feature uses machine learning to help businesses forecast cash flows more accurately than they have previously.</span></span> <span data-ttu-id="4504c-108">Também pode ajudar os gerentes a tomar decisões que otimizam as oportunidades no contexto da posição de caixa atual.</span><span class="sxs-lookup"><span data-stu-id="4504c-108">It can also help managers make decisions that optimize opportunities in the context of their current cash position.</span></span> 

<span data-ttu-id="4504c-109">Para a maioria das empresas, o gerenciamento de fluxo de caixa e a execução de previsões de fluxo de caixa é um processo tedioso, repetitivo e manual.</span><span class="sxs-lookup"><span data-stu-id="4504c-109">For most companies, managing cash flow and running cash flow forecasting is a tedious, repetitive, and manual process.</span></span> <span data-ttu-id="4504c-110">A maioria das empresas confia em soluções do Microsoft Excel que têm graus de complexidade variáveis.</span><span class="sxs-lookup"><span data-stu-id="4504c-110">Most companies rely on Microsoft Excel solutions that have varying degrees of complexity.</span></span> <span data-ttu-id="4504c-111">Os desafios da previsão de fluxo de caixa com precisão incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4504c-111">The challenges of accurately forecasting cash flow include the following:</span></span>

- <span data-ttu-id="4504c-112">Os dados não estão disponíveis para tomadores de decisão porque estão dispersos em vários lugares, incluindo:</span><span class="sxs-lookup"><span data-stu-id="4504c-112">Data isn't available to decision makers because it's scattered in multiple places, including:</span></span> 
  - <span data-ttu-id="4504c-113">O sistema de planejamento de recursos corporativos ou contábeis</span><span class="sxs-lookup"><span data-stu-id="4504c-113">The accounting or enterprise resource planning system</span></span>
  - <span data-ttu-id="4504c-114">Software de planejamento financeiro</span><span class="sxs-lookup"><span data-stu-id="4504c-114">Financial planning software</span></span>
  - <span data-ttu-id="4504c-115">Excel</span><span class="sxs-lookup"><span data-stu-id="4504c-115">Excel</span></span>
  - <span data-ttu-id="4504c-116">Aplicativos de software adicionais</span><span class="sxs-lookup"><span data-stu-id="4504c-116">Additional software applications</span></span> 
- <span data-ttu-id="4504c-117">A previsão se baseia no conhecimento interno que reside em "silos" em cada domínio ou departamento.</span><span class="sxs-lookup"><span data-stu-id="4504c-117">Forecasting is based on internal knowledge that resides in "silos" within each domain or department.</span></span>
- <span data-ttu-id="4504c-118">Medir a precisão da previsão de fluxo de caixa depois que as finanças são concretizadas é incerto e difícil.</span><span class="sxs-lookup"><span data-stu-id="4504c-118">Measuring the accuracy of cash flow forecasting after the financials have been realized is uncertain and difficult.</span></span>
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a><span data-ttu-id="4504c-119">Detalhes do recurso de previsões de fluxo de caixa</span><span class="sxs-lookup"><span data-stu-id="4504c-119">Details of the Cash flow forecasts capability</span></span>
<span data-ttu-id="4504c-120">O recurso de previsões de fluxo de caixa inclui a funcionalidade a seguir.</span><span class="sxs-lookup"><span data-stu-id="4504c-120">The Cash flow forecasts feature includes the following functionality.</span></span> 

- <span data-ttu-id="4504c-121">Facilita a integração de dados de fluxo de caixa de sistemas externos para o Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="4504c-121">Makes it easy to integrate cash flow data from external systems to Dynamics 365 Finance.</span></span> <span data-ttu-id="4504c-122">As previsões de fluxo de caixa também podem usar a estrutura de importação-exportação de dados.</span><span class="sxs-lookup"><span data-stu-id="4504c-122">Cash flow forecasts can also use the data import-export framework.</span></span> <span data-ttu-id="4504c-123">Esta estrutura facilita a integração com o Excel/OData.</span><span class="sxs-lookup"><span data-stu-id="4504c-123">This framework makes it easy to integrate with Excel OData.</span></span> <span data-ttu-id="4504c-124">Também é possível combinar dados de várias fontes para criar uma solução de fluxo de caixa abrangente.</span><span class="sxs-lookup"><span data-stu-id="4504c-124">You can also combine data from multiple sources to create a comprehensive cash flow solution.</span></span> 

- <span data-ttu-id="4504c-125">Introduz a posição de caixa à vista inteligente.</span><span class="sxs-lookup"><span data-stu-id="4504c-125">Introduces intelligent cash position.</span></span> <span data-ttu-id="4504c-126">A posição de pagamento à vista é criada com base no comportamento de pagamento do cliente para prever quando uma empresa pode esperar dinheiro chegar em suas contas.</span><span class="sxs-lookup"><span data-stu-id="4504c-126">Cash position is created  based on customer’s payment behavior to predict when a company can expect cash to arrive in their accounts.</span></span> <span data-ttu-id="4504c-127">Ele também analisa os padrões históricos de fornecedores de pagamento para prever quando futuras faturas e ordens futuras provavelmente devem ser pagas.</span><span class="sxs-lookup"><span data-stu-id="4504c-127">It also analyzes the historical patterns of paying vendors, to predict when future invoices and orders are likely to be paid.</span></span> 

- <span data-ttu-id="4504c-128">Introduz a previsão de fluxo de caixa inteligente para previsões de longo prazo, usando a previsão de série de tempo por meio da integração automatizada com o AI Builder.</span><span class="sxs-lookup"><span data-stu-id="4504c-128">Introduces intelligent cash flow forecasting for long-term forecasting, using time series forecasting through automated integration with AI Builder.</span></span>

- <span data-ttu-id="4504c-129">Oferece a capacidade de salvar as previsões ou posições de fluxo de caixa específicas, editá-las e comparar e medir facilmente o desempenho de previsão para os dados financeiro reais.</span><span class="sxs-lookup"><span data-stu-id="4504c-129">Provides the ability to save specific cash flow position or forecasts, edit them, and then easily compare and measure the forecast performance to the actual financials.</span></span>

- <span data-ttu-id="4504c-130">Habilita o análise hipotética por meio da comparação de instantâneo.</span><span class="sxs-lookup"><span data-stu-id="4504c-130">Enables what-if analysis through snapshot comparison.</span></span> <span data-ttu-id="4504c-131">Por exemplo, você pode criar vários instantâneos que representem os modos de exibição otimista, pessimista e mais realista do fluxo de caixa e depois comparar e exibir as diferenças.</span><span class="sxs-lookup"><span data-stu-id="4504c-131">For example, you can create multiple snapshots that represent optimistic, pessimistic, and the most realistic views of your cash flow, and then compare and view the differences.</span></span>

- <span data-ttu-id="4504c-132">Fornece a capacidade de exibir a previsão de fluxo de caixa em várias moedas, entre as entidades legais e filtrar e exibir o fluxo de caixa relacionado a uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="4504c-132">Provides the ability to view the cash flow forecast in multiple currencies, across legal entities, and filter and view cash flow related to a bank account.</span></span> 

- <span data-ttu-id="4504c-133">Permite filtrar e exibir contas bancárias relacionadas a dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="4504c-133">Lets you filter and view bank accounts that are related to financial dimensions.</span></span>

<span data-ttu-id="4504c-134">A funcionalidade de previsão de fluxo de caixa no Dynamics 365 Finance permitirá que sua organização transforme uma projeção de fluxo de caixa tediosa, complexa e repetitiva a um processo simples e automatizado.</span><span class="sxs-lookup"><span data-stu-id="4504c-134">The cash flow forecasting functionality in Dynamics 365 Finance will empower your organization to transform tedious, complex, yet repetitive cash flow projection to a simple, automated process.</span></span> <span data-ttu-id="4504c-135">Automatizar os aspectos mais tediosos da previsão de fluxo de caixa permite que você se concentre na tomada de decisões críticas para impulsionar os resultados comerciais desejados.</span><span class="sxs-lookup"><span data-stu-id="4504c-135">Automating the most tedious aspects of cash flow forecasting lets you focus on critical decision making to drive desired business outcomes.</span></span>

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a><span data-ttu-id="4504c-136">Configurando dimensões para previsão de fluxo de caixa</span><span class="sxs-lookup"><span data-stu-id="4504c-136">Setting up Dimensions for Cash flow forecasting</span></span>
<span data-ttu-id="4504c-137">Uma nova guia na página **Configuração de previsão de fluxo de caixa** permite controlar as dimensões financeiras a serem usadas para filtragem no espaço de trabalho **Previsão de fluxo de caixa**.</span><span class="sxs-lookup"><span data-stu-id="4504c-137">A new tab on the **Cash flow forecasting setup** page lets you control what financial dimensions to use for filtering in the **Cash flow forecasting** workspace.</span></span> <span data-ttu-id="4504c-138">Esta guia só será exibida quando o recurso de previsões de fluxo de caixa estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="4504c-138">This tab will only appear when the Cash flow forecasts feature is enabled.</span></span> 

<span data-ttu-id="4504c-139">Na guia **Dimensões**, escolha na lista de dimensões a ser usada para filtragem e use as teclas de seta para movê-las para a coluna à direita.</span><span class="sxs-lookup"><span data-stu-id="4504c-139">On the **Dimensions** tab, choose from the list of dimensions to use for filtering, and use the arrow keys to move them to the right-hand column.</span></span> <span data-ttu-id="4504c-140">Somente duas dimensões podem ser selecionadas para filtrar dados de previsão de fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="4504c-140">Only two dimensions can be selected for filtering cash flow forecast data.</span></span> 

#### <a name="privacy-notice"></a><span data-ttu-id="4504c-141">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="4504c-141">Privacy notice</span></span>
<span data-ttu-id="4504c-142">As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="4504c-142">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
