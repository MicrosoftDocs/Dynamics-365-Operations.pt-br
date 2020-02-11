---
title: Sincronizar classificações de produto no Dynamics 365 Retail
description: Este tópico descreve como sincronizar classificações do produto no Microsoft Dynamics 365 Retail.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: db5a4e1f78797d20ded2274cc99bef422fd50acc
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698156"
---
# <a name="sync-product-ratings-in-dynamics-365-retail"></a><span data-ttu-id="148ad-103">Sincronizar classificações de produto no Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="148ad-103">Sync product ratings in Dynamics 365 Retail</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="148ad-104">Este tópico descreve como sincronizar classificações do produto no Microsoft Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="148ad-104">This topic describes how to sync product ratings in Microsoft Dynamics 365 Retail.</span></span>

## <a name="overview"></a><span data-ttu-id="148ad-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="148ad-105">Overview</span></span>

<span data-ttu-id="148ad-106">Para consumir classificações de produtos em omnicanais, como no ponto de venda (PDV) e em call centers, as classificações de produtos do serviço de classificações e opiniões devem ser importadas para o banco de dados do canal de Varejo.</span><span class="sxs-lookup"><span data-stu-id="148ad-106">To consume product ratings in omnichannels, such as at the point of sale (POS) and in call centers, product ratings from the ratings and reviews service must be imported into the Retail channel database.</span></span> <span data-ttu-id="148ad-107">Quando as classificações de produtos são disponibilizadas nos omnicanais, elas podem ajudar os clientes indiretamente durante suas interações com os representantes de vendas.</span><span class="sxs-lookup"><span data-stu-id="148ad-107">When product ratings are made available in omnichannels, they can help customers indirectly during their interactions with sales associates.</span></span>

<span data-ttu-id="148ad-108">Este tópico descreve as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="148ad-108">This topic describes following tasks:</span></span>

1. <span data-ttu-id="148ad-109">Configure um trabalho em lotes de Varejo para importar classificações de produtos.</span><span class="sxs-lookup"><span data-stu-id="148ad-109">Configure a Retail batch job to import product ratings.</span></span>
1. <span data-ttu-id="148ad-110">Verifique se o trabalho em lotes para sincronização da classificação do produto foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="148ad-110">Verify that the batch job for product rating synchronization was successful.</span></span>
1. <span data-ttu-id="148ad-111">Disponibilizar classificações do produto no PDV.</span><span class="sxs-lookup"><span data-stu-id="148ad-111">Make product ratings available at the POS.</span></span>

## <a name="configure-a-retail-batch-job-to-import-product-ratings"></a><span data-ttu-id="148ad-112">Configure um trabalho em lotes de Varejo para importar classificações de produtos.</span><span class="sxs-lookup"><span data-stu-id="148ad-112">Configure a Retail batch job to import product ratings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="148ad-113">Antes de começar, verifique se a versão 10.0.6 ou posterior do Varejo está instalada.</span><span class="sxs-lookup"><span data-stu-id="148ad-113">Before you start, make sure that version 10.0.6 or later of Retail is installed.</span></span>

### <a name="initialize-the-retail-scheduler"></a><span data-ttu-id="148ad-114">Inicializar o agendador do Retail</span><span class="sxs-lookup"><span data-stu-id="148ad-114">Initialize the retail scheduler</span></span>

<span data-ttu-id="148ad-115">Para inicializar o agendador do Retail, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="148ad-115">To initialize the retail scheduler, follow these steps.</span></span>

1. <span data-ttu-id="148ad-116">Vá para **Retail \> Configuração da sede \> Agendador do Retail \> Inicialize agendador do retail**.</span><span class="sxs-lookup"><span data-stu-id="148ad-116">Go to **Retail \> Headquarters setup \> Retail scheduler \> Initialize retail scheduler**.</span></span> <span data-ttu-id="148ad-117">Como alternativa, procure por "Inicializar agendador do Retail".</span><span class="sxs-lookup"><span data-stu-id="148ad-117">Alternatively, search for "Initialize retail scheduler."</span></span>
1. <span data-ttu-id="148ad-118">Na caixa de diálogo **Inicializar Agendador do Retail**, certifique-se de que a opção **Excluir configuração existente** seja definida como **Não** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="148ad-118">In the **Initialize retail scheduler** dialog box, make sure that the **Delete existing configuration** option is set to **No**, and then select **OK**.</span></span>

### <a name="verify-the-retailproductrating-subjob"></a><span data-ttu-id="148ad-119">Verifique o subtrabalho RetailProductRating</span><span class="sxs-lookup"><span data-stu-id="148ad-119">Verify the RetailProductRating subjob</span></span>

<span data-ttu-id="148ad-120">Para verificar se o subtrabalho **RetailProductRating** existe, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="148ad-120">To verify that the **RetailProductRating** subjob exists, follow these steps.</span></span>

1. <span data-ttu-id="148ad-121">Vá para **Retail \> Configuração da sede \> Agendador do Retail \> Subtrabalhos do agendador**.</span><span class="sxs-lookup"><span data-stu-id="148ad-121">Go to **Retail \> Headquarters setup \> Retail scheduler \> Scheduler subjobs**.</span></span> <span data-ttu-id="148ad-122">Como alternativa, procure por "Subtrabalhos do agendador".</span><span class="sxs-lookup"><span data-stu-id="148ad-122">Alternatively, search for "Scheduler subjobs."</span></span>
1. <span data-ttu-id="148ad-123">Na lista de subtrabalhos, localize ou procure o subtrabalho **RetailProductRating** .</span><span class="sxs-lookup"><span data-stu-id="148ad-123">In the subjob list, find or search for the **RetailProductRating** subjob.</span></span>

<span data-ttu-id="148ad-124">A ilustração a seguir mostra um exemplo dos detalhes do subtrabalho no Retail.</span><span class="sxs-lookup"><span data-stu-id="148ad-124">The following illustration shows an example of the subjob details in Retail.</span></span>

![Detalhes do subtrabalho RetailProductRating](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> <span data-ttu-id="148ad-126">Se você não encontrar o subtrabalho **RetailProductRating**, talvez você já tenha executado o trabalho **Sincronizar classificações de produto** e o trabalho **1040 CDX** antes de inicializar o agendador do Retail.</span><span class="sxs-lookup"><span data-stu-id="148ad-126">If you don't find the **RetailProductRating** subjob, you might already have run the **Sync product ratings** job and the **1040 CDX** job before you initialized the retail scheduler.</span></span> <span data-ttu-id="148ad-127">Neste caso, siga estas etapas para executar o trabalho **Sincronização de dados completa**.</span><span class="sxs-lookup"><span data-stu-id="148ad-127">In this case, follow these steps to run the **Full data sync** job.</span></span>
>
> 1. <span data-ttu-id="148ad-128">Vá para **Retail \> Configuração da sede \> Agendador do Retail \> Banco de dados do canal**.</span><span class="sxs-lookup"><span data-stu-id="148ad-128">Go to **Retail \> Headquarters setup \> Retail scheduler \> Channel database**.</span></span> <span data-ttu-id="148ad-129">Como alternativa, procure por "Banco de dados do canal".</span><span class="sxs-lookup"><span data-stu-id="148ad-129">Alternatively, search for "Channel database."</span></span>
> 1. <span data-ttu-id="148ad-130">Selecione o base de dados do canal para sincronizar.</span><span class="sxs-lookup"><span data-stu-id="148ad-130">Select the channel database to sync.</span></span>
> 1. <span data-ttu-id="148ad-131">No Painel de Ação, selecione **Sincronização de dados completa**.</span><span class="sxs-lookup"><span data-stu-id="148ad-131">On the Action Pane, select **Full data sync**.</span></span>
> 1. <span data-ttu-id="148ad-132">Na caixa de diálogo suspensa **Selecionar uma agenda de distribuição** , selecione **1040 - produtos**, e **OK**.</span><span class="sxs-lookup"><span data-stu-id="148ad-132">In the **Select a distribution schedule** drop-down dialog box, select **1040 - products**, and then select **OK**.</span></span>
> 1. <span data-ttu-id="148ad-133">Repita as etapas do procedimento anterior para verificar se o subtrabalho **RetailProductRating** foi criado.</span><span class="sxs-lookup"><span data-stu-id="148ad-133">Repeat the steps of the previous procedure to verify that the **RetailProductRating** subjob has been created.</span></span>

### <a name="import-product-ratings"></a><span data-ttu-id="148ad-134">Importar classificações de produtos</span><span class="sxs-lookup"><span data-stu-id="148ad-134">Import product ratings</span></span>

<span data-ttu-id="148ad-135">Para importar classificações de produto no Retail do serviço de classificações e opiniões, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="148ad-135">To import product ratings into Retail from the ratings and reviews service, follow these steps.</span></span>

1. <span data-ttu-id="148ad-136">Vá para **Retail \> Configuração da sede \> Agendador do Retail \> Sincronizar trabalho de classificações de produto**.</span><span class="sxs-lookup"><span data-stu-id="148ad-136">Go to **Retail \> Headquarters setup \> Retail scheduler \> Sync product ratings job**.</span></span> <span data-ttu-id="148ad-137">Como alternativa, procure por "Sincronizar trabalho de classificações do produto".</span><span class="sxs-lookup"><span data-stu-id="148ad-137">Alternatively, search for "Sync product ratings job."</span></span>
1. <span data-ttu-id="148ad-138">Na caixa de diálogo **Obter classificações do produto**, na Guia Rápida **Executar em segundo plano**, selecione **Recorrência**.</span><span class="sxs-lookup"><span data-stu-id="148ad-138">In the **Pull product ratings** dialog box, on the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="148ad-139">Na caixa de diálogo **Definir recorrência** , configure um padrão de recorrência.</span><span class="sxs-lookup"><span data-stu-id="148ad-139">In the **Define recurrence** dialog box, set up a recurrence pattern.</span></span> <span data-ttu-id="148ad-140">(O valor sugerido é duas horas.) Não agende uma recorrência inferior a de uma hora.</span><span class="sxs-lookup"><span data-stu-id="148ad-140">(The suggested value is two hours.) Don't schedule a recurrence that is less than one hour.</span></span>
1. <span data-ttu-id="148ad-141">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="148ad-141">Select **OK**.</span></span>
1. <span data-ttu-id="148ad-142">Defina a opção **Processo em lote** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="148ad-142">Set the **Batch process** option to **Yes**.</span></span> <span data-ttu-id="148ad-143">Essa configuração ajuda a garantir que você poderá auditar os logs e verificar o status de execuções do trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="148ad-143">This setting helps guarantee that you will be able to audit the logs and verify the status of batch job runs.</span></span>
1. <span data-ttu-id="148ad-144">Selecione **OK** para programar o trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="148ad-144">Select **OK** to schedule the batch job.</span></span>

<span data-ttu-id="148ad-145">A ilustração a seguir mostra um exemplo da configuração do trabalho em lotes no Retail.</span><span class="sxs-lookup"><span data-stu-id="148ad-145">The following illustration shows an example of batch job configuration in Retail.</span></span>

![Configuração do trabalho em lotes Sincronizar classificações do produto](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a><span data-ttu-id="148ad-147">Verifique se o trabalho em lotes para sincronização da classificação do produto foi bem-sucedido</span><span class="sxs-lookup"><span data-stu-id="148ad-147">Verify that the batch job for product rating synchronization was successful</span></span>

<span data-ttu-id="148ad-148">Para verificar se o trabalho em lotes **Sincronizar classificações de produto** foi bem-sucedido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="148ad-148">To verify that the **Sync product ratings** batch job was successful, follow these steps.</span></span>

1. <span data-ttu-id="148ad-149">Vá para **Retail \> Administrador do sistema \> Consultas \> Trabalho em lotes** ou, se você estiver usando a uma unidade de manutenção de estoque (SKU) do Retail, **Retail \> Consultas e relatórios \> Trabalho em lotes** .</span><span class="sxs-lookup"><span data-stu-id="148ad-149">Go to **Retail \> System administrator \> Inquiries \> Batch jobs** or, if you're using a Retail-only stock keeping unit (SKU), **Retail \> Inquiries and reports \> Batch jobs** instead.</span></span> <span data-ttu-id="148ad-150">Como alternativa, procure "Trabalho em lotes".</span><span class="sxs-lookup"><span data-stu-id="148ad-150">Alternatively, search for "Batch jobs."</span></span>
1. <span data-ttu-id="148ad-151">Para exibir os detalhes do trabalho em lotes, na lista de trabalho em lotes na coluna **Descrição do trabalho**, procure uma descrição que contenha "Obter classificações do produto."</span><span class="sxs-lookup"><span data-stu-id="148ad-151">To view the details of the batch job, in the batch job list, in the **Job description** column, search for a description that contains "Pull product ratings."</span></span>
1. <span data-ttu-id="148ad-152">Selecione a ID do trabalho para visualizar os detalhes do trabalho em lotes, como a data/hora de início agendada e o texto da recorrência.</span><span class="sxs-lookup"><span data-stu-id="148ad-152">Select the job ID to view the batch job details, such as the scheduled start date/time and the recurrence text.</span></span>

<span data-ttu-id="148ad-153">A ilustração a seguir mostra um exemplo detalhes do trabalho em lotes no Retail quando o trabalho em lote for programado para ser executado em intervalos de duas horas.</span><span class="sxs-lookup"><span data-stu-id="148ad-153">The following illustration shows an example of the batch job details in Retail when the batch job is scheduled to run at two-hour intervals.</span></span>

![Detalhes do trabalho em lotes Sincronizar classificação do produto](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a><span data-ttu-id="148ad-155">Disponibilizar classificações do produto no PDV.</span><span class="sxs-lookup"><span data-stu-id="148ad-155">Make product ratings available at the POS</span></span>

<span data-ttu-id="148ad-156">A solução de classificações e opiniões no Dynamics 365 Commerce é uma solução do omnicanal.</span><span class="sxs-lookup"><span data-stu-id="148ad-156">The ratings and reviews solution in Dynamics 365 Commerce is an omnichannel solution.</span></span> <span data-ttu-id="148ad-157">Porém, as classificações de produtos não são mostradas no PDV, por padrão.</span><span class="sxs-lookup"><span data-stu-id="148ad-157">However, products ratings aren't shown at the POS by default.</span></span> <span data-ttu-id="148ad-158">Para ajudar os clientes nas lojas a verem classificações e opiniões quando estiverem sendo ajudados por vendedores, é necessário ativar as classificações de produtos no PDV.</span><span class="sxs-lookup"><span data-stu-id="148ad-158">To help customers in stores see ratings and reviews when they are being helped by sales associates, you must turn on product ratings at the POS.</span></span>

<span data-ttu-id="148ad-159">Para ativar as classificações do produto no PDV, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="148ad-159">To turn on product ratings at the POS, follow these steps.</span></span>

1. <span data-ttu-id="148ad-160">Vá para **Varejo \> Configuração do Varejo \> Parâmetros \> Parâmetros do Varejo**.</span><span class="sxs-lookup"><span data-stu-id="148ad-160">Go to **Retail \> Retail setup \> Parameters \> Retail parameters**.</span></span> <span data-ttu-id="148ad-161">Como alternativa, procure "Parâmetros de Varejo".</span><span class="sxs-lookup"><span data-stu-id="148ad-161">Alternatively, search for "Retail parameters."</span></span>
1. <span data-ttu-id="148ad-162">Na guia **Configurar parâmetros** , selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="148ad-162">On the **Configuration parameters** tab, select **New**.</span></span>
1. <span data-ttu-id="148ad-163">Insira um nome como **RatingsAndReviews.EnableProductRatingsForRetailStores** e defina o valor para **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="148ad-163">Enter a name such as **RatingsAndReviews.EnableProductRatingsForRetailStores**, and set the value to **true**.</span></span>
1. <span data-ttu-id="148ad-164">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="148ad-164">Select **Save**.</span></span>
1. <span data-ttu-id="148ad-165">Vá para **Varejo \> TI de varejo \> Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="148ad-165">Go to **Retail \> Retail IT \> Distribution schedule**.</span></span> <span data-ttu-id="148ad-166">Alternativamente, procure por "Agenda de distribuição".</span><span class="sxs-lookup"><span data-stu-id="148ad-166">Alternatively, search for "Distribution schedule."</span></span>
1. <span data-ttu-id="148ad-167">Na lista de trabalho, selecione **1110** (**Configuração global**) e **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="148ad-167">In the job list, select **1110** (**Global configuration**), and then select **Run now**.</span></span>
1. <span data-ttu-id="148ad-168">Depois que o trabalho for executado com sucesso, verifique se as classificações dos produtos agora são mostradas no PDV.</span><span class="sxs-lookup"><span data-stu-id="148ad-168">After the job has successfully run, verify that products ratings are now shown at the POS.</span></span>

<span data-ttu-id="148ad-169">A ilustração a seguir mostra um exemplo da configuração dos parâmetros de Varejo para ativar as classificações do produto no PDV.</span><span class="sxs-lookup"><span data-stu-id="148ad-169">The following illustration shows an example of the configuration of the Retail parameters to turn on product ratings at the POS.</span></span>

![Configuração de parâmetros de Varejo para classificações de produtos no PDV](media/rnr-hq-enable-ratings-in-pos.png)

<span data-ttu-id="148ad-171">A ilustração a seguir mostra um exemplo de classificações do produto no PDV.</span><span class="sxs-lookup"><span data-stu-id="148ad-171">The following illustration shows an example of product ratings at the POS.</span></span>

![Classificações do produto no PDV](media/rnr-pos-catalog-ratings.png)

<span data-ttu-id="148ad-173">A ilustração a seguir mostra um exemplo de classificações do produto em canais do call center.</span><span class="sxs-lookup"><span data-stu-id="148ad-173">The following illustration shows an example of product ratings in call center channels.</span></span>

![Classificações de produtos em um canal de call center](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a><span data-ttu-id="148ad-175">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="148ad-175">Additional resources</span></span>

[<span data-ttu-id="148ad-176">Visão geral de classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="148ad-176">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="148ad-177">Aceitar usar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="148ad-177">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="148ad-178">Gerenciar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="148ad-178">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="148ad-179">Configurar classificações e opiniões</span><span class="sxs-lookup"><span data-stu-id="148ad-179">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)