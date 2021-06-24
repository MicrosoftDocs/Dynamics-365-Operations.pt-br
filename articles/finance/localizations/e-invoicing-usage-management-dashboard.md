---
title: Painel Gerenciamento de uso
description: Este tópico explica como usar o Painel Gerenciamento de uso para monitorar o uso do serviço de Faturamento Eletrônico e permanecer em conformidade.
author: gionoder
ms.date: 06/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 411c2d33c81738dcacfb7c8feec991d0fd06fb78
ms.sourcegitcommit: 9069a8511dfe11d09a2b51d32547ba10fea48bed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2021
ms.locfileid: "6130497"
---
# <a name="usage-management-dashboard"></a><span data-ttu-id="0f2d4-103">Painel de gerenciamento de uso</span><span class="sxs-lookup"><span data-stu-id="0f2d4-103">Usage management dashboard</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0f2d4-104">O painel **Gerenciamento de uso** ajuda você monitorar o uso do serviço de Faturamento Eletrônico e, portanto, ajuda sua organização a permanecer em conformidade em termos de uso mensal.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-104">The **Usage management** dashboard helps you monitor usage of the Electronic Invoicing service, and therefore helps your organization remain compliant in terms of its monthly usage.</span></span> <span data-ttu-id="0f2d4-105">A conformidade é determinada calculando o volume de submissão e comparando-o com o volume de submissões para identificar qualquer desvio entre o volume adquirido e o volume usado.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-105">Compliance is determined by calculating the submission volume and comparing it with the acquired volume of submissions to identify any deviations between the acquired volume and the used volume.</span></span>

<span data-ttu-id="0f2d4-106">O painel inclui os seguintes indicadores:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-106">The dashboard includes the following indicators:</span></span>

- <span data-ttu-id="0f2d4-107">Um indicador de custo que você pode usar para monitorar o consumo para fins de conformidade de licença:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-107">One cost indicator that you can use to monitor consumption for licensing compliance purposes:</span></span>

    - <span data-ttu-id="0f2d4-108">Uso por mês (exportação)</span><span class="sxs-lookup"><span data-stu-id="0f2d4-108">Usage per month (export)</span></span>

- <span data-ttu-id="0f2d4-109">Os três indicadores operacionais que você pode usar para rastrear o uso do serviço de Faturamento Eletrônico para fins de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-109">Three operational indicators that you can use to track usage of the Electronic Invoicing service for management purposes:</span></span>

    - <span data-ttu-id="0f2d4-110">Uso por recurso</span><span class="sxs-lookup"><span data-stu-id="0f2d4-110">Usage by feature</span></span>
    - <span data-ttu-id="0f2d4-111">Uso por ambiente</span><span class="sxs-lookup"><span data-stu-id="0f2d4-111">Usage by environment</span></span>
    - <span data-ttu-id="0f2d4-112">Uso por mês (importação)</span><span class="sxs-lookup"><span data-stu-id="0f2d4-112">Usage per month (import)</span></span>

## <a name="measurement-scope"></a><span data-ttu-id="0f2d4-113">Escopo de medição</span><span class="sxs-lookup"><span data-stu-id="0f2d4-113">Measurement scope</span></span>

- <span data-ttu-id="0f2d4-114">Unidade de medida:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-114">Unit of measure:</span></span> 

    <span data-ttu-id="0f2d4-115">O painel **Gerenciamento de uso** conta o envio de documentos de negócios e faturas eletrônicas importadas.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-115">The **Usage management** dashboard counts the submission of business documents and imported electronic invoices.</span></span>

- <span data-ttu-id="0f2d4-116">Organização:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-116">Organization:</span></span> 

    <span data-ttu-id="0f2d4-117">A conta é resumida pelo ID de locatário da sua organização, não importa o número de instâncias do Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management, nem o número de entidades legais em que o serviço de Faturamento Eletrônico está ativado.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-117">Counting is summarized by the tenant ID of your organization, regardless of the number of instances of Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management, or the number of legal entities where the Electronic Invoicing service is enabled.</span></span>


## <a name="indicator-usage-per-month-export"></a><span data-ttu-id="0f2d4-118">Indicador: uso por mês (exportação)</span><span class="sxs-lookup"><span data-stu-id="0f2d4-118">Indicator: Usage per month (export)</span></span>

<span data-ttu-id="0f2d4-119">Este indicador fornece detalhes sobre os faturamentos eletrônicos que a sua organização emite durante um período definido.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-119">This indicator provides details about the electronic invoices that your organization issues during a defined period.</span></span>

### <a name="scope"></a><span data-ttu-id="0f2d4-120">Escopo</span><span class="sxs-lookup"><span data-stu-id="0f2d4-120">Scope</span></span>
- <span data-ttu-id="0f2d4-121">O número de documentos de negócios que são enviados do Finance and Supply Chain Management para o o serviço de Faturamento de Eletrônico, não importa o número de linhas que esses documentos de negócios contenham.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-121">The number of business documents that are submitted from Finance and Supply Chain Management to the Electronic Invoicing service, regardless of number of lines that those business documents contain.</span></span>
- <span data-ttu-id="0f2d4-122">O número de documentos de negócios enviados que são processados com sucesso pelo serviço de Faturamento Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-122">The number of submitted business documents that are successfully processed by the Electronic Invoicing service.</span></span> <span data-ttu-id="0f2d4-123">Um documento é considerado processado com sucesso quando o fluxo de ações que são definidas na configuração do recurso é concluído.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-123">A document is considered successfully processed when the flow of actions that are defined in the feature setup is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="0f2d4-124">Quando uma fatura eletrônica é enviada para um serviço Web externo, a contagem é independente dos resultados do processamento do serviço Web (aceito, rejeitado ou erro de validação do esquema).</span><span class="sxs-lookup"><span data-stu-id="0f2d4-124">When an electronic invoice is submitted to an external web service, counting is independent of the results of web service processing (accepted, rejected, or schema validation error).</span></span> <span data-ttu-id="0f2d4-125">Se serviço Web tiver recebido e respondido à solicitação do serviço de Faturamento Eletrônico, o envio será considerado uma contagem válida.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-125">If the web service received and responded to the request from the Electronic Invoicing service, the submission is considered a valid counting.</span></span>

- <span data-ttu-id="0f2d4-126">**Exceção:** os documentos de negócios não serão contados se eles forem reenviados do Finance e Supply Chain Management para o serviço de Faturamento Eletrônico, como nos cenários em que um reenvio do mesmo documento de negócio for necessário para alterar o status do faturamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-126">**Exception:** Business documents aren't counted if they are resubmitted from Finance and Supply Chain Management to the Electronic Invoicing service, such as in the scenarios where a resubmission of the same business document is required to change the status of the electronic invoice.</span></span> <span data-ttu-id="0f2d4-127">Por exemplo, a emissão de uma fatura eletrônica brasileira (documento fiscal) é contada como válida, mas a solicitação de cancelamento para ela não.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-127">For example, issuance of a Brazilian electronic invoice (fiscal document) is counted as valid, but the cancellation request for it isn't counted.</span></span>


### <a name="calculation"></a><span data-ttu-id="0f2d4-128">Cálculo</span><span class="sxs-lookup"><span data-stu-id="0f2d4-128">Calculation</span></span>

<span data-ttu-id="0f2d4-129">O cálculo do saldo é feito da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-129">The calculation of the balance is calculated as follows:</span></span>

<span data-ttu-id="0f2d4-130">Saldo = Gratuito + Comprado - Usado</span><span class="sxs-lookup"><span data-stu-id="0f2d4-130">Balance = Free + Purchased – Used</span></span>

<span data-ttu-id="0f2d4-131">Onde:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-131">Where:</span></span>

- <span data-ttu-id="0f2d4-132">Gratuito:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-132">Free:</span></span>
  
    <span data-ttu-id="0f2d4-133">Um volume gratuito dos documentos de negócio que o cliente pode enviar por mês.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-133">A free volume of business documents the customer can submit per month.</span></span> <span data-ttu-id="0f2d4-134">Ele inclui um pacote de 100 documentos negócios enviados que podem ser enviados para o serviço de Faturamento Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-134">It includes a package of 100 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="0f2d4-135">O volume gratuito não é cumulativo e qualquer saldo restante não é passado para o próximo período.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-135">Free volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="0f2d4-136">Adquiridas:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-136">Purchased:</span></span>
  
    <span data-ttu-id="0f2d4-137">Um pacote de 1.000 documentos negócios enviados que podem ser enviados para o serviço de Faturamento Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-137">A package of 1,000 business documents that can be submitted to the Electronic Invoicing service.</span></span> <span data-ttu-id="0f2d4-138">Este pacote deve ser adquirido para sua organização mensalmente.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-138">This package must be acquired for your organization on a monthly basis.</span></span> <span data-ttu-id="0f2d4-139">O volume comprado não é cumulativo e qualquer saldo restante não é passado para o próximo período.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-139">Purchased volume isn't cumulative, and any remaining balance isn't rolled over to the next period.</span></span>
  
- <span data-ttu-id="0f2d4-140">Usado:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-140">Used:</span></span> 

    <span data-ttu-id="0f2d4-141">A contagem dos envios de documento de negócio para o serviço Faturamento Eletrônico de acordo com os critérios definidos.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-141">The count of business document submissions to the Electronic Invoicing service according to defined criteria.</span></span>
   
> [!IMPORTANT]
> <span data-ttu-id="0f2d4-142">Se a sua organização planeja exceder o volume mensal de 100 envios gratuitos, compre o volume máximo para garantir a conformidade com a política de licenciamento da Microsoft para o serviço Faturamento Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-142">If your organization plans to exceed the monthly volume of 100 free submissions, purchase the peak volume to ensure that you remain compliant with the Microsoft licensing policy for the Electronic Invoicing service.</span></span>
>
> <span data-ttu-id="0f2d4-143">Atualmente, o volume comprado deve ser inserido manualmente, de acordo com a data de aquisição, como vários pacotes de 1.000 envios.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-143">Currently, purchased volume must be manually entered, according to the date of acquisition, as multiple packages of 1,000 submissions.</span></span>

## <a name="indicator-usage-by-feature"></a><span data-ttu-id="0f2d4-144">Indicador: uso por recurso</span><span class="sxs-lookup"><span data-stu-id="0f2d4-144">Indicator: Usage by feature</span></span>

<span data-ttu-id="0f2d4-145">Este indicador mostra o uso de recursos de faturamento eletrônico para emissão de faturas eletrônicas durante um período definido.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-145">This indicator shows the usage of electronic invoicing features for issuance of electronic invoices during a defined period.</span></span>

- <span data-ttu-id="0f2d4-146">Cálculo:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-146">Calculation:</span></span>
  
    <span data-ttu-id="0f2d4-147">Usado =-A contagem de quantas vezes cada recurso de faturamento eletrônico foi usado durante o envio dos documentos de negócio para o serviço Faturamento Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-147">Used = The count of how many times each electronic invoicing feature was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-by-environment"></a><span data-ttu-id="0f2d4-148">Indicador: uso por ambiente</span><span class="sxs-lookup"><span data-stu-id="0f2d4-148">Indicator: Usage by environment</span></span>

<span data-ttu-id="0f2d4-149">Este indicador mostra o uso de ambientes do serviço de faturamento eletrônico durante um período definido.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-149">This indicator shows the usage of electronic invoicing service environments during a defined period.</span></span>

- <span data-ttu-id="0f2d4-150">Cálculo:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-150">Calculation:</span></span>
    
    <span data-ttu-id="0f2d4-151">Usado =-A contagem de quantas vezes cada ambiente do serviço de faturamento eletrônico foi usado durante o envio dos documentos de negócio para o serviço Faturamento Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-151">Used = The count of how many times each electronic invoicing service environment was used during the submission of business documents to the Electronic Invoicing service.</span></span>

## <a name="indicator-usage-per-month-import"></a><span data-ttu-id="0f2d4-152">Indicador: uso por mês (importação)</span><span class="sxs-lookup"><span data-stu-id="0f2d4-152">Indicator: Usage per month (import)</span></span>

<span data-ttu-id="0f2d4-153">Este indicador mostra o volume de importação de faturas eletrônicas pelo serviço Faturamento Eletrônico no Finance e Supply Chain Management durante um período definido.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-153">This indicator shows the volume of importation of electronic invoices by Electronic Invoicing service into Finance and Supply Chain Management during a defined period.</span></span>

- <span data-ttu-id="0f2d4-154">Escopo:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-154">Scope:</span></span>

    <span data-ttu-id="0f2d4-155">As faturas eletrônicos que são importados no Finance and Supply Chain Management para o o serviço de Faturamento de Eletrônico, não importa o número de linhas que esses documentos de negócios contenham.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-155">Electronic invoices that are imported into Finance and Supply Chain Management, regardless of the number of lines that those electronic invoices contain.</span></span>

- <span data-ttu-id="0f2d4-156">Cálculo:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-156">Calculation:</span></span>

    <span data-ttu-id="0f2d4-157">Recebido = A contagem de faturas eletrônicas importadas no Finance e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-157">Received = The count of imported electronic invoices into Finance and Supply Chain Management.</span></span>

## <a name="functions"></a><span data-ttu-id="0f2d4-158">Funções</span><span class="sxs-lookup"><span data-stu-id="0f2d4-158">Functions</span></span>
### <a name="purchase"></a><span data-ttu-id="0f2d4-159">Compra</span><span class="sxs-lookup"><span data-stu-id="0f2d4-159">Purchase</span></span>

<span data-ttu-id="0f2d4-160">Na guia **Uso por mês (export)**, selecione **Comprar** para registrar manualmente a quantidade de envios adquiridos.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-160">On the **Usage per month (export)** tab, select **Purchase** to manually register the amount of acquired submissions.</span></span>

<span data-ttu-id="0f2d4-161">Para uma data específica, selecione **Novo** e digite o número de **Pacotes** adquiridos nessa data.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-161">For a given date, select **New** and enter the number of **Packages** acquired for on that date.</span></span>

<span data-ttu-id="0f2d4-162">A **Quantidade** é calculada como:</span><span class="sxs-lookup"><span data-stu-id="0f2d4-162">The **Quantity** is calculated as:</span></span>

<span data-ttu-id="0f2d4-163">Quantidade = Pacotes \* 1.000</span><span class="sxs-lookup"><span data-stu-id="0f2d4-163">Quantity = Packages \* 1.000</span></span>

<span data-ttu-id="0f2d4-164">A **Quantidade** calculada reflete no campo **Comprado** no indicador **Uso por mês (exportar)**.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-164">The calculated **Quantity** reflects in the **Purchased** from the indicator **Usage per month (export)**.</span></span>

### <a name="update"></a><span data-ttu-id="0f2d4-165">Atualização</span><span class="sxs-lookup"><span data-stu-id="0f2d4-165">Update</span></span>

<span data-ttu-id="0f2d4-166">No Painel de ações, selecione **Atualizar** para atualizar o cálculo e atualizar os dados mostrados na página e no gráfico.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-166">On the Action Pane, select **Update** to refresh the calculation and update the data shown on the page and in the chart.</span></span>

### <a name="reset-history-data"></a><span data-ttu-id="0f2d4-167">Redefinir dados do histórico</span><span class="sxs-lookup"><span data-stu-id="0f2d4-167">Reset history data</span></span>

<span data-ttu-id="0f2d4-168">No Painel de ações, selecione **Redefinir dados históricos** para atualizar as bases de dados de onde os indicadores são calculados.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-168">On the Action Pane, select **Reset history data** to refresh the database from where the indicators are calculated.</span></span>




> [!NOTE]
> <span data-ttu-id="0f2d4-169">O painel **Gerenciamento de uso** não mostra as quantidades monetárias.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-169">The **Usage management** dashboard doesn't show monetary amounts.</span></span> <span data-ttu-id="0f2d4-170">Em vez disso, ele mostra somente o volume dos envios contados e documentos e importados.</span><span class="sxs-lookup"><span data-stu-id="0f2d4-170">Instead, it shows only the volume of counted submissions and imported documents.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
