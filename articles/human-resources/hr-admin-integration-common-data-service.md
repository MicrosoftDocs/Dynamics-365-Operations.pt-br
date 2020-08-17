---
title: Configurar integração do Common Data Service
description: Você pode ativar ou desativar a integração entre o Common Data Service e Dynamics 365 Human Resources. Também é possível exibir os detalhes da sincronização, limpar dados de rastreamento e ressincronizar uma entidade para ajudar com a solução de problemas de dados entre os dois ambientes.
author: andreabichsel
manager: AnnBe
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8cbead2961c4576a5394080aae2fec109bce3f10
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621295"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="2e828-104">Configurar integração do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="2e828-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="2e828-105">Você pode ativar ou desativar a integração entre o Common Data Service e Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2e828-105">You can turn integration between Common Data Service and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="2e828-106">Também é possível exibir os detalhes da sincronização, limpar dados de rastreamento e ressincronizar uma entidade para ajudar com a solução de problemas de dados entre os dois ambientes.</span><span class="sxs-lookup"><span data-stu-id="2e828-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="2e828-107">Quando você desativa a integração, os usuários podem fazer alterações no Human Resources ou no Common Data Service, mas essas alterações não são sincronizadas entre os dois ambientes.</span><span class="sxs-lookup"><span data-stu-id="2e828-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="2e828-108">Por padrão, a integração de dados entre o Human Resources e o Common Data Service está desativada.</span><span class="sxs-lookup"><span data-stu-id="2e828-108">By default, integration between Human Resources and Common Data Service is turned off.</span></span>

<span data-ttu-id="2e828-109">Talvez você queira desativar a integração nestas situações:</span><span class="sxs-lookup"><span data-stu-id="2e828-109">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="2e828-110">Você está preenchendo dados por meio da Estrutura de Gerenciamento de Dados e deve importar os dados várias vezes para que fiquem no estado correto.</span><span class="sxs-lookup"><span data-stu-id="2e828-110">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="2e828-111">Há problemas com dados no Human Resources ou no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e828-111">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="2e828-112">Se você desativar a integração, será possível excluir um registro em um ambiente sem excluí-lo de outro.</span><span class="sxs-lookup"><span data-stu-id="2e828-112">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="2e828-113">Quando você reativar a integração, o registro no ambiente onde ele não foi excluído sincroniza com o ambiente de onde ele foi excluído.</span><span class="sxs-lookup"><span data-stu-id="2e828-113">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="2e828-114">A sincronização começa na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Common Data Service** for executado.</span><span class="sxs-lookup"><span data-stu-id="2e828-114">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="2e828-115">Ao desativar a integração de dados, certifique-se de não editar o mesmo registro em ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="2e828-115">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="2e828-116">Quando você reativar a integração, o registro que você editou pela última vez será sincronizado.</span><span class="sxs-lookup"><span data-stu-id="2e828-116">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="2e828-117">Portanto, se você não fizer as mesmas alterações no registro em ambos os ambientes, poderá ocorrer perda de dados.</span><span class="sxs-lookup"><span data-stu-id="2e828-117">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="2e828-118">Acessar a página integração do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="2e828-118">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="2e828-119">Na instância do Human Resources onde você deseja ver ou configurar definições para a integração ao Common Data Service, selecione o bloco **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="2e828-119">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="2e828-120">[![Bloco Administração do sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="2e828-120">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="2e828-121">Selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="2e828-121">Select the **Links** tab.</span></span>

    <span data-ttu-id="2e828-122">[![Guia Links](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="2e828-122">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="2e828-123">Em **Integrações**, selecione **Configuração do Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="2e828-123">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="2e828-124">[![Link de configuração do Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="2e828-124">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="2e828-125">Ativar ou desativar a integração de dados entre o Human Resources e o Common Data Service</span><span class="sxs-lookup"><span data-stu-id="2e828-125">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="2e828-126">Para ativar a integração, defina a opção **Ativar a integração ao Common Data Service** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2e828-126">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e828-127">Quando você ativar a integração, os dados serão sincronizados na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Common Data Service** for executado.</span><span class="sxs-lookup"><span data-stu-id="2e828-127">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="2e828-128">Todos os dados deverão estar disponíveis depois que o trabalho em lotes for concluído.</span><span class="sxs-lookup"><span data-stu-id="2e828-128">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="2e828-129">Para desativar a integração, defina a opção como **Não**.</span><span class="sxs-lookup"><span data-stu-id="2e828-129">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="2e828-130">[![Ativando ou desativando a integração do Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="2e828-130">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

> [!WARNING]
> <span data-ttu-id="2e828-131">É altamente recomendável desativar a integração do Common Data Service enquanto as tarefas de migração de dados são executadas.</span><span class="sxs-lookup"><span data-stu-id="2e828-131">We strongly recommend turning off Common Data Service integration while performing data migration tasks.</span></span> <span data-ttu-id="2e828-132">Grandes uploads de dados podem afetar significativamente o desempenho.</span><span class="sxs-lookup"><span data-stu-id="2e828-132">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="2e828-133">Por exemplo, fazer upload de 2000 trabalhadores pode levar várias horas quando a integração estiver habilitada e menos de uma hora quando estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="2e828-133">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="2e828-134">Os números fornecidos neste exemplo são somente para fins de demonstração.</span><span class="sxs-lookup"><span data-stu-id="2e828-134">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="2e828-135">A quantidade exata de tempo necessária para importar registros pode variar bastante com base em vários fatores.</span><span class="sxs-lookup"><span data-stu-id="2e828-135">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="2e828-136">Exibir detalhes da integração de dados</span><span class="sxs-lookup"><span data-stu-id="2e828-136">View data integration details</span></span>

<span data-ttu-id="2e828-137">Na FastTab **Administração** da página **Integração do Common Data Service**, você pode ver como os registros são vinculados juntos entre o Human Resources e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e828-137">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="2e828-138">Para exibir os registros de uma entidade, selecione a entidade no campo **Nome da entidade CDS**.</span><span class="sxs-lookup"><span data-stu-id="2e828-138">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="2e828-139">A grade mostra todos os registros vinculados à entidade selecionada.</span><span class="sxs-lookup"><span data-stu-id="2e828-139">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="2e828-140">[![Exibindo os registros de uma entidade](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="2e828-140">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="2e828-141">Nem todas as entidades do Common Data Service estão listadas atualmente.</span><span class="sxs-lookup"><span data-stu-id="2e828-141">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="2e828-142">Somente as entidades que aceitam o uso de campos personalizados aparecem na grade.</span><span class="sxs-lookup"><span data-stu-id="2e828-142">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="2e828-143">Novas entidades são disponibilizadas por meio de lançamentos contínuos do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2e828-143">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="2e828-144">A grade inclui os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="2e828-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="2e828-145">**Nome da entidade CDS** – o nome da entidade no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e828-145">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="2e828-146">**Referência da entidade CDS** – o identificador que o Common Data Service usa para identificar um registro.</span><span class="sxs-lookup"><span data-stu-id="2e828-146">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="2e828-147">Esse valor é equivalente a um valor **RecId** do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2e828-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="2e828-148">Você pode encontrar o identificador ao abrir a entidade do Common Data Service no Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="2e828-148">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="2e828-149">**Nome da entidade do Human Resources** – a entidade que sincronizou os dados pela última vez com o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e828-149">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="2e828-150">A entidade pode ter o prefixo do Common Data Service ou outro prefixo.</span><span class="sxs-lookup"><span data-stu-id="2e828-150">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="2e828-151">**Referência do Human Resources** – o valor **RecId** que é associado ao registro no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2e828-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="2e828-152">**Foi excluído do CDS** – um valor que indica se o registro foi excluído do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e828-152">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="2e828-153">Remover do Common Data Service a associação de um registro no Human Resources</span><span class="sxs-lookup"><span data-stu-id="2e828-153">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="2e828-154">Se você tiver problemas durante a sincronização de dados entre o Human Resources e o Common Data Service, talvez seja possível resolvê-los limpando o rastreamento e permitindo que a tabela de rastreamento seja ressincronizada.</span><span class="sxs-lookup"><span data-stu-id="2e828-154">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="2e828-155">Se você remover a associação e alterar ou excluir um registro no Common Data Service, as alterações não serão sincronizadas com o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2e828-155">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="2e828-156">Se você fizer alterações no Human Resources, um novo registro de rastreamento será criado e o registro será atualizado no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2e828-156">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="2e828-157">Para remover a associação de um registro entre o Human Resources e o Common Data Service, selecione a entidade no campo **Nome da entidade CDS** e selecione **Limpar informações de rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="2e828-157">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="2e828-158">[![Limpando informações de rastreamento](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="2e828-158">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="2e828-159">Para executar uma sincronização completa na entidade depois de desmarcar o rastreamento, consulte o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="2e828-159">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="2e828-160">Sincronizar uma entidade entre o Human Resources e o Common Data Service</span><span class="sxs-lookup"><span data-stu-id="2e828-160">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="2e828-161">Use este procedimento quando:</span><span class="sxs-lookup"><span data-stu-id="2e828-161">Use this procedure when:</span></span>

- <span data-ttu-id="2e828-162">As alterações de Common Data Service são exibidas de forma muito longa em Human Resources.</span><span class="sxs-lookup"><span data-stu-id="2e828-162">Changes from Common Data Service take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="2e828-163">Você deve atualizar a tabela de controle depois de limpar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="2e828-163">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="2e828-164">Para executar uma sincronização completa em uma entidade entre Human Resources e Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="2e828-164">To run a full synchronization on an entity between Human Resources and Common Data Service:</span></span>

1. <span data-ttu-id="2e828-165">Selecione a entidade no campo **Nome da entidade CDS**.</span><span class="sxs-lookup"><span data-stu-id="2e828-165">Select the entity in the **CDS entity name** field.</span></span>

2. <span data-ttu-id="2e828-166">Selecione **Sincronizar agora**.</span><span class="sxs-lookup"><span data-stu-id="2e828-166">Select **Sync now**.</span></span>

<span data-ttu-id="2e828-167">[![Executando uma sincronização completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="2e828-167">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


