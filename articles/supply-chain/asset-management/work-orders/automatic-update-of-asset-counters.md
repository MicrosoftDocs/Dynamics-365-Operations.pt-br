---
title: Atualização automática de contadores de ativos
description: Este tópico descreve a atualização automática de contadores de ativos no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875511"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="1953b-103">Atualização automática de contadores de ativos</span><span class="sxs-lookup"><span data-stu-id="1953b-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="1953b-104">O registro manual dos contadores de ativos é descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="1953b-104">In the previous section, manual registration of asset counters is described.</span></span> <span data-ttu-id="1953b-105">A configuração dos contadores de ativos é descrita em [Contadores](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="1953b-105">Setup of asset counters is described in [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="1953b-106">Os valores dos contadores também podem ser atualizados automaticamente usando registros de produção, com base nas horas de produção ou na quantidade de produção.</span><span class="sxs-lookup"><span data-stu-id="1953b-106">Counter values can also be automatically updated from production registrations, based on production hours or production quantity.</span></span> <span data-ttu-id="1953b-107">Isso é feito em **Atualizar contadores de ativos**.</span><span class="sxs-lookup"><span data-stu-id="1953b-107">This is done in **Update asset counters**.</span></span> <span data-ttu-id="1953b-108">É possível atualizar um ou vários ativos inserindo um parâmetro **Data inicial**.</span><span class="sxs-lookup"><span data-stu-id="1953b-108">You can update one or several assets by inserting one parameter, **From date**.</span></span> <span data-ttu-id="1953b-109">Esse parâmetro especifica a data de início dos registros de produção (horas ou quantidade de produção), ou seja, a data de início a partir da qual os valores dos contadores devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="1953b-109">This parameter specifies the start date for production registrations (hours or quantity produced), meaning the start date from which counter values should be updated.</span></span>

<span data-ttu-id="1953b-110">Todos os ativos que estão relacionados a um recurso *e* possuem contadores de ativos, configurados para serem atualizados com base nas horas ou quantidade de produção, serão incluídos em uma atualização automática e novos valores de contador serão criados.</span><span class="sxs-lookup"><span data-stu-id="1953b-110">All assets that are related to a resource *and* have asset counters, which are set up to be updated based on produced quantity or production hours, will be included in an automatic update, and new counter values will be created.</span></span>

<span data-ttu-id="1953b-111">No caso dos contadores com base na quantidade de produção, quantidade sem erros e quantidade de erros registradas estão incluídas na contagem.</span><span class="sxs-lookup"><span data-stu-id="1953b-111">Regarding counters based on production quantity, good quantity as well as error quantity registered are included in the count.</span></span> <span data-ttu-id="1953b-112">Se a unidade usada para registrar a quantidade produzida for diferente da unidade usada no contador, a quantidade será convertida para corresponder à unidade do contador.</span><span class="sxs-lookup"><span data-stu-id="1953b-112">If the unit used for produced quantity registration is different from the unit used on the counter, quantity is converted to correspond with the counter unit.</span></span>

<span data-ttu-id="1953b-113">Como mencionado acima, os contadores automáticos podem ser atualizados por meio de registros de produção.</span><span class="sxs-lookup"><span data-stu-id="1953b-113">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="1953b-114">Sendo assim, o ativo para o qual você deseja atualizar automaticamente os contadores deve estar relacionado a um recurso (máquina).</span><span class="sxs-lookup"><span data-stu-id="1953b-114">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="1953b-115">As descrições a seguir fornecem uma visão geral da configuração e do processamento das ordens de produção (no módulo **Controle de produção**), que é usado como base para a atualização automática de contadores em um ativo no módulo **Gerenciamento de ativos**.</span><span class="sxs-lookup"><span data-stu-id="1953b-115">The following descriptions provide an overview of the setup and processing of production orders (in the **Production control** module), which is used as a basis for automatic update of counters on an asset in the **Asset management** module.</span></span>

<span data-ttu-id="1953b-116">Quando quantidades ou horas de produção tiverem sido registradas no recurso, será possível atualizar os contadores de ativos relacionados.</span><span class="sxs-lookup"><span data-stu-id="1953b-116">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="1953b-117">Clique em **Gerenciamento de ativos** > **Periódico** > **Ativos** > **Atualizar contadores de ativos**.</span><span class="sxs-lookup"><span data-stu-id="1953b-117">Click **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="1953b-118">Selecione a data de início da atualização automática no campo **Data inicial**.</span><span class="sxs-lookup"><span data-stu-id="1953b-118">Select the start date of the automatic update in the **From date** field.</span></span>

>[!NOTE]
><span data-ttu-id="1953b-119">A data nesse campo é a data do "trabalho em andamento" em **Transações de roteiro** ( campo **Controle de produção** > **Consultas e relatórios** > **Produção** > **Transações de roteiro** > **Data física**).</span><span class="sxs-lookup"><span data-stu-id="1953b-119">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="1953b-120">Se quiser selecionar ativos, tipos de ativos ou recursos específicos para a atualização automática, clique em **Filtrar** na Guia Rápida **Registros a serem incluídos** e faça as seleções relevantes.</span><span class="sxs-lookup"><span data-stu-id="1953b-120">If you want to select specific assets, asset types, or resources for the automatic update, click **Filter** on the **Records to include** FastTab, and make the relevant selections.</span></span>

4. <span data-ttu-id="1953b-121">Se necessário, você pode configurar a atualização automática como trabalho em lotes na Guia Rápida **Executar em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="1953b-121">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

![Figura 1](media/12-work-orders.png)

5. <span data-ttu-id="1953b-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1953b-123">Click **OK**.</span></span> <span data-ttu-id="1953b-124">Quando a atualização automática do contador de ativos é concluída, é possível ver os registros do contador relacionados ao ativo em **Contadores de ativos** (**Gerenciamento de ativos** > **Comum** > **Ativos** > **Todos os ativos** > selecione o ativo > botão **Contadores**).</span><span class="sxs-lookup"><span data-stu-id="1953b-124">When the automatic asset counter update is done, you can see the counter registrations related to the asset in **Asset counters** (**Asset management** > **Common** > **Assets** > **All assets** > select asset > **Counters** button).</span></span>

<span data-ttu-id="1953b-125">Em **Totais do contador de ativos**, você pode obter uma visão geral do registro mais recente feito em todos os tipos de contadores em todos os ativos.</span><span class="sxs-lookup"><span data-stu-id="1953b-125">In **Asset counter totals**, you can get an overview of the latest registration made on all counter types on all assets.</span></span> <span data-ttu-id="1953b-126">Clique em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **Valor agregado do ativo**.</span><span class="sxs-lookup"><span data-stu-id="1953b-126">Click **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="1953b-127">A exibição é muito semelhante a **Contadores de ativos**, mas não é possível adicionar ou editar registros no **Valor agregado do ativo**.</span><span class="sxs-lookup"><span data-stu-id="1953b-127">The view is very similar to **Asset counters**, but you cannot add or edit registrations in **Asset aggregated value**.</span></span> <span data-ttu-id="1953b-128">É apenas para visão geral.</span><span class="sxs-lookup"><span data-stu-id="1953b-128">It is for overview only.</span></span>

![Figura 2](media/13-work-orders.png)


- <span data-ttu-id="1953b-130">Ainda é possível criar registros manuais de valores de contador para tipos de contador que são atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1953b-130">It is still possible to create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="1953b-131">Consulte a seção "Atualização manual de contadores de ativo" para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1953b-131">Refer to the "Manual update of asset counters" section for more information.</span></span>
- <span data-ttu-id="1953b-132">Você pode configurar contadores relacionados a outro contador, ou seja, quando um contador é atualizado, os contadores relacionados são atualizados automaticamente ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="1953b-132">You can set up counters related to another counter, which means that when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="1953b-133">Consulte [Contadores](../setup-for-objects/counters.md) para saber mais sobre a configuração de contadores relacionados.</span><span class="sxs-lookup"><span data-stu-id="1953b-133">Refer to [Counters](../setup-for-objects/counters.md) regarding setup of related counters.</span></span>
