---
title: Configurar integração do Common Data Service
description: Você pode ativar ou desativar a integração entre o Common Data Service e Dynamics 365 Human Resources. Também é possível exibir os detalhes da sincronização, limpar dados de rastreamento e ressincronizar uma entidade para ajudar com a solução de problemas de dados entre os dois ambientes.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 04280aa0908ed6dab86ef87b6c1843e4b4348e08
ms.sourcegitcommit: c9657b44adb9c1a77c7c2f6ab63a58cc848974ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198413"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="e71a7-104">Configurar integração do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="e71a7-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="e71a7-105">Você pode ativar ou desativar a integração entre o Common Data Service e Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e71a7-105">You can turn integration between Common Data Service and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="e71a7-106">Também é possível exibir os detalhes da sincronização, limpar dados de rastreamento e ressincronizar uma entidade para ajudar com a solução de problemas de dados entre os dois ambientes.</span><span class="sxs-lookup"><span data-stu-id="e71a7-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="e71a7-107">Quando você desativa a integração, os usuários podem fazer alterações no Human Resources ou no Common Data Service, mas essas alterações não são sincronizadas entre os dois ambientes.</span><span class="sxs-lookup"><span data-stu-id="e71a7-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="e71a7-108">Por padrão, a integração de dados entre o Human Resources e o Common Data Service está desativada.</span><span class="sxs-lookup"><span data-stu-id="e71a7-108">By default, integration between Human Resources and Common Data Service is turned off.</span></span>

<span data-ttu-id="e71a7-109">Talvez você queira desativar a integração nestas situações:</span><span class="sxs-lookup"><span data-stu-id="e71a7-109">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="e71a7-110">Você está preenchendo dados por meio da Estrutura de Gerenciamento de Dados e deve importar os dados várias vezes para que fiquem no estado correto.</span><span class="sxs-lookup"><span data-stu-id="e71a7-110">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="e71a7-111">Há problemas com dados no Human Resources ou no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e71a7-111">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="e71a7-112">Se você desativar a integração, será possível excluir um registro em um ambiente sem excluí-lo de outro.</span><span class="sxs-lookup"><span data-stu-id="e71a7-112">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="e71a7-113">Quando você reativar a integração, o registro no ambiente onde ele não foi excluído sincroniza com o ambiente de onde ele foi excluído.</span><span class="sxs-lookup"><span data-stu-id="e71a7-113">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="e71a7-114">A sincronização começa na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Common Data Service** for executado.</span><span class="sxs-lookup"><span data-stu-id="e71a7-114">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="e71a7-115">Ao desativar a integração de dados, certifique-se de não editar o mesmo registro em ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="e71a7-115">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="e71a7-116">Quando você reativar a integração, o registro que você editou pela última vez será sincronizado.</span><span class="sxs-lookup"><span data-stu-id="e71a7-116">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="e71a7-117">Portanto, se você não fizer as mesmas alterações no registro em ambos os ambientes, poderá ocorrer perda de dados.</span><span class="sxs-lookup"><span data-stu-id="e71a7-117">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="e71a7-118">Acessar a página integração do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="e71a7-118">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="e71a7-119">Na instância do Human Resources onde você deseja ver ou configurar definições para a integração ao Common Data Service, selecione o bloco **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="e71a7-119">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="e71a7-120">[![Bloco Administração do sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="e71a7-120">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="e71a7-121">Selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="e71a7-121">Select the **Links** tab.</span></span>

    <span data-ttu-id="e71a7-122">[![Guia Links](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="e71a7-122">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="e71a7-123">Em **Integrações**, selecione **Configuração do Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="e71a7-123">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="e71a7-124">[![Link de configuração do Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="e71a7-124">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="e71a7-125">Ativar ou desativar a integração de dados entre o Human Resources e o Common Data Service</span><span class="sxs-lookup"><span data-stu-id="e71a7-125">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="e71a7-126">Para ativar a integração, defina a opção **Ativar a integração ao Common Data Service** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e71a7-126">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e71a7-127">Quando você ativar a integração, os dados serão sincronizados na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Common Data Service** for executado.</span><span class="sxs-lookup"><span data-stu-id="e71a7-127">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="e71a7-128">Todos os dados deverão estar disponíveis depois que o trabalho em lotes for concluído.</span><span class="sxs-lookup"><span data-stu-id="e71a7-128">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="e71a7-129">Para desativar a integração, defina a opção como **Não**.</span><span class="sxs-lookup"><span data-stu-id="e71a7-129">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="e71a7-130">[![Ativando ou desativando a integração do Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="e71a7-130">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="e71a7-131">Exibir detalhes da integração de dados</span><span class="sxs-lookup"><span data-stu-id="e71a7-131">View data integration details</span></span>

<span data-ttu-id="e71a7-132">Na FastTab **Administração** da página **Integração do Common Data Service**, você pode ver como os registros são vinculados juntos entre o Human Resources e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e71a7-132">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="e71a7-133">Para exibir os registros de uma entidade, selecione a entidade no campo **Nome da entidade CDS**.</span><span class="sxs-lookup"><span data-stu-id="e71a7-133">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="e71a7-134">A grade mostra todos os registros vinculados à entidade selecionada.</span><span class="sxs-lookup"><span data-stu-id="e71a7-134">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="e71a7-135">[![Exibindo os registros de uma entidade](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="e71a7-135">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="e71a7-136">Nem todas as entidades do Common Data Service estão listadas atualmente.</span><span class="sxs-lookup"><span data-stu-id="e71a7-136">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="e71a7-137">Somente as entidades que aceitam o uso de campos personalizados aparecem na grade.</span><span class="sxs-lookup"><span data-stu-id="e71a7-137">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="e71a7-138">Novas entidades são disponibilizadas por meio de lançamentos contínuos do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e71a7-138">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="e71a7-139">A grade inclui os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="e71a7-139">The grid includes the following fields:</span></span>

- <span data-ttu-id="e71a7-140">**Nome da entidade CDS** – o nome da entidade no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e71a7-140">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="e71a7-141">**Referência da entidade CDS** – o identificador que o Common Data Service usa para identificar um registro.</span><span class="sxs-lookup"><span data-stu-id="e71a7-141">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="e71a7-142">Esse valor é equivalente a um valor **RecId** do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e71a7-142">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="e71a7-143">Você pode encontrar o identificador ao abrir a entidade do Common Data Service no Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="e71a7-143">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="e71a7-144">**Nome da entidade do Human Resources** – a entidade que sincronizou os dados pela última vez com o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e71a7-144">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="e71a7-145">A entidade pode ter o prefixo do Common Data Service ou outro prefixo.</span><span class="sxs-lookup"><span data-stu-id="e71a7-145">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="e71a7-146">**Referência do Human Resources** – o valor **RecId** que é associado ao registro no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e71a7-146">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="e71a7-147">**Foi excluído do CDS** – um valor que indica se o registro foi excluído do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e71a7-147">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="e71a7-148">Remover do Common Data Service a associação de um registro no Human Resources</span><span class="sxs-lookup"><span data-stu-id="e71a7-148">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="e71a7-149">Se você tiver problemas durante a sincronização de dados entre o Human Resources e o Common Data Service, talvez seja possível resolvê-los limpando o rastreamento e permitindo que a tabela de rastreamento seja ressincronizada.</span><span class="sxs-lookup"><span data-stu-id="e71a7-149">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="e71a7-150">Se você remover a associação e alterar ou excluir um registro no Common Data Service, as alterações não serão sincronizadas com o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e71a7-150">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="e71a7-151">Se você fizer alterações no Human Resources, um novo registro de rastreamento será criado e o registro será atualizado no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e71a7-151">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="e71a7-152">Para remover a associação de um registro entre o Human Resources e o Common Data Service, selecione a entidade no campo **Nome da entidade CDS** e selecione **Limpar informações de rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="e71a7-152">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="e71a7-153">[![Limpando informações de rastreamento](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="e71a7-153">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="e71a7-154">Para executar uma sincronização completa na entidade depois de desmarcar o rastreamento, consulte o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="e71a7-154">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="e71a7-155">Sincronizar uma entidade entre o Human Resources e o Common Data Service</span><span class="sxs-lookup"><span data-stu-id="e71a7-155">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="e71a7-156">Use este procedimento quando:</span><span class="sxs-lookup"><span data-stu-id="e71a7-156">Use this procedure when:</span></span>

- <span data-ttu-id="e71a7-157">As alterações de Common Data Service são exibidas de forma muito longa em Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e71a7-157">Changes from Common Data Service take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="e71a7-158">Você deve atualizar a tabela de controle depois de limpar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="e71a7-158">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="e71a7-159">Para executar uma sincronização completa em uma entidade entre Human Resources e Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="e71a7-159">To run a full synchronization on an entity between Human Resources and Common Data Service:</span></span>

1. <span data-ttu-id="e71a7-160">Selecione a entidade no campo **Nome da entidade CDS**.</span><span class="sxs-lookup"><span data-stu-id="e71a7-160">Select the entity in the **CDS entity name** field.</span></span>

2. <span data-ttu-id="e71a7-161">Selecione **Sincronizar agora**.</span><span class="sxs-lookup"><span data-stu-id="e71a7-161">Select **Sync now**.</span></span>

<span data-ttu-id="e71a7-162">[![Executando uma sincronização completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="e71a7-162">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>

