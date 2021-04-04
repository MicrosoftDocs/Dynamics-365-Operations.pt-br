---
title: Atualização automática de contadores de ativos
description: Este tópico descreve a atualização automática de contadores de ativos no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9911d5b96bb58b5def3e7dfee0f36826d99f6ba1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263677"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="b3f44-103">Atualização automática de contadores de ativo</span><span class="sxs-lookup"><span data-stu-id="b3f44-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b3f44-104">Para obter informações sobre o registro manual dos contadores de ativos, consulte [Atualização manual de contadores de ativos](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="b3f44-104">For information about manual registration of asset counters, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span> <span data-ttu-id="b3f44-105">Para obter mais informações sobre como configurar contadores de ativos, consulte [Contadores](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="b3f44-105">For information on how to set up asset counters, see [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="b3f44-106">Os valores dos contadores também podem ser atualizados automaticamente usando registros de produção, com base nas horas de produção ou na quantidade de produção (ou seja, a quantidade produzida).</span><span class="sxs-lookup"><span data-stu-id="b3f44-106">Counter values can also be automatically updated from production registrations, based on the production hours or production quantity (that is, the quantity that is produced).</span></span> <span data-ttu-id="b3f44-107">A atualização é feita na página **Atualizar contadores de ativos**.</span><span class="sxs-lookup"><span data-stu-id="b3f44-107">This update is done on the **Update asset counters** page.</span></span> <span data-ttu-id="b3f44-108">É possível atualizar um ou vários ativos configurando um parâmetro **Data inicial**.</span><span class="sxs-lookup"><span data-stu-id="b3f44-108">You can update one or several assets by setting one parameter, **From date**.</span></span> <span data-ttu-id="b3f44-109">Este parâmetro especifica a data inicial para registros de produção (horas de produção ou quantidades de produção).</span><span class="sxs-lookup"><span data-stu-id="b3f44-109">This parameter specifies the start date for production registrations (production hours or production quantities).</span></span> <span data-ttu-id="b3f44-110">Em outras palavras, especifica a partir de que data os valores de contador devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="b3f44-110">In other words, it specifies the date that counter values should be updated from.</span></span>

<span data-ttu-id="b3f44-111">Todos os ativos relacionados a um recurso *e* com contadores de ativos configurados para serem atualizados com base nas horas ou na quantidade de produção serão incluídos em uma atualização automática.</span><span class="sxs-lookup"><span data-stu-id="b3f44-111">All assets that are related to a resource, *and* that have asset counters that are set up to be updated based on the production hours or production quantity, will be included in an automatic update.</span></span> <span data-ttu-id="b3f44-112">Os novos valores de contador serão criados.</span><span class="sxs-lookup"><span data-stu-id="b3f44-112">New counter values will be created.</span></span>

<span data-ttu-id="b3f44-113">Para os contadores baseados na quantidade de produção, a contagem incluirá a quantidade de acertos e a quantidade de erros registradas.</span><span class="sxs-lookup"><span data-stu-id="b3f44-113">For counters that are based on the production quantity, the count includes both the good quantity and the error quantity that are registered.</span></span> <span data-ttu-id="b3f44-114">Se a unidade usada para registrar a quantidade produzida for diferente da unidade usada para o contador, a quantidade será convertida de forma a corresponder à unidade do contador.</span><span class="sxs-lookup"><span data-stu-id="b3f44-114">If the unit that is used for production quantity registration differs from the unit that is used for the counter, the quantity is converted so that it corresponds to the counter unit.</span></span>

<span data-ttu-id="b3f44-115">Como mencionado acima, os contadores automáticos podem ser atualizados por meio de registros de produção.</span><span class="sxs-lookup"><span data-stu-id="b3f44-115">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="b3f44-116">Sendo assim, o ativo para o qual você deseja atualizar automaticamente os contadores deve estar relacionado a um recurso (máquina).</span><span class="sxs-lookup"><span data-stu-id="b3f44-116">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="b3f44-117">Quando quantidades ou horas de produção tiverem sido registradas no recurso, será possível atualizar os contadores de ativos relacionados.</span><span class="sxs-lookup"><span data-stu-id="b3f44-117">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="b3f44-118">Selecione **Gerenciamento de ativos** > **Periódico** > **Ativos** > **Atualizar contadores de ativos**.</span><span class="sxs-lookup"><span data-stu-id="b3f44-118">Select **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="b3f44-119">No campo **Data inicial**, selecione a data de início da atualização automática.</span><span class="sxs-lookup"><span data-stu-id="b3f44-119">In the **From date** field, select the start date of the automatic update.</span></span>

    >[!NOTE]
    ><span data-ttu-id="b3f44-120">A data nesse campo é a data do "trabalho em andamento" em **Transações de roteiro** ( campo **Controle de produção** > **Consultas e relatórios** > **Produção** > **Transações de roteiro** > **Data física**).</span><span class="sxs-lookup"><span data-stu-id="b3f44-120">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="b3f44-121">Na Guia Rápida **Registros a incluir**, você pode selecionar ativos, tipos de ativo ou recursos específicos para a atualização automática.</span><span class="sxs-lookup"><span data-stu-id="b3f44-121">On the **Records to include** FastTab, you can select specific assets, asset types, or resources for the automatic update.</span></span> <span data-ttu-id="b3f44-122">Selecione **Filtro** e faça as seleções relevantes.</span><span class="sxs-lookup"><span data-stu-id="b3f44-122">Select **Filter**, and make the relevant selections.</span></span>

4. <span data-ttu-id="b3f44-123">Na Guia Rápida **Executar em segundo plano**, você pode configurar a atualização automática como um trabalho em lote, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b3f44-123">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

    <span data-ttu-id="b3f44-124">A ilustração a seguir mostra um exemplo do diálogo **Atualizar contadores de ativos**.</span><span class="sxs-lookup"><span data-stu-id="b3f44-124">The illustration below shows an example of the **Update asset counters** dialog.</span></span>

    ![Figura 1](media/12-work-orders.png)

5. <span data-ttu-id="b3f44-126">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3f44-126">Select **OK**.</span></span> 

<span data-ttu-id="b3f44-127">Após a conclusão da atualização automática de contador de ativos, você poderá exibir os registros de contador relacionados a ativos na **Contadores de ativos**.</span><span class="sxs-lookup"><span data-stu-id="b3f44-127">After the automatic asset counter update is done, you can view the counter registrations that are related to the asset on the **Asset counters** page.</span></span> <span data-ttu-id="b3f44-128">Selecione **Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos**, selecione o ativo e, em seguida, no Painel de Ação, na guia **Ativo**, no grupo **Preventivo** , selecione **Contadores**.</span><span class="sxs-lookup"><span data-stu-id="b3f44-128">Select **Asset management** > **Common** > **Assets** > **All assets**, select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span>

<span data-ttu-id="b3f44-129">Na página **Valor agregado de ativo**, você pode obter uma visão geral do registro mais recente feito em todos os tipos de contadores em todos os ativos.</span><span class="sxs-lookup"><span data-stu-id="b3f44-129">On the **Asset aggregated value** page, you can get an overview of the latest registration that have been made on all counter types on all assets.</span></span> <span data-ttu-id="b3f44-130">Selecione **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Valor agregado do ativo**.</span><span class="sxs-lookup"><span data-stu-id="b3f44-130">Select **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="b3f44-131">Essa página se assemelha à página **Contadores de ativos**, mas você não poderá adicionar ou editar registros.</span><span class="sxs-lookup"><span data-stu-id="b3f44-131">This page resembles the **Asset counters** page, but you can't add or edit registrations.</span></span> <span data-ttu-id="b3f44-132">É apenas para visão geral.</span><span class="sxs-lookup"><span data-stu-id="b3f44-132">It's for overview only.</span></span>

<span data-ttu-id="b3f44-133">A ilustração a seguir mostra um exemplo da página **Valor agregado do ativo**.</span><span class="sxs-lookup"><span data-stu-id="b3f44-133">The illustration below shows an example of the **Asset aggregated value** page.</span></span>

![Figura 2](media/13-work-orders.png)

<span data-ttu-id="b3f44-135">Observe os seguintes pontos:</span><span class="sxs-lookup"><span data-stu-id="b3f44-135">Note the following points:</span></span>

- <span data-ttu-id="b3f44-136">Você ainda pode criar registros manuais de valores de contador para os tipos de contador que são atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b3f44-136">You can still create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="b3f44-137">Para obter mais informações, consulte [Atualização manual de contadores de ativos](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="b3f44-137">For more information, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span>

- <span data-ttu-id="b3f44-138">Você pode configurar os contadores relacionados a outro contador.</span><span class="sxs-lookup"><span data-stu-id="b3f44-138">You can set up counters that are related to another counter.</span></span> <span data-ttu-id="b3f44-139">Nesse caso, quando um contador é atualizado, os contadores relacionados são atualizados automaticamente ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b3f44-139">In this case, when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="b3f44-140">Para obter mais informações sobre como configurar contadores relacionados, consulte [Contadores](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="b3f44-140">For more information about how to set up related counters, see [Counters](../setup-for-objects/counters.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]