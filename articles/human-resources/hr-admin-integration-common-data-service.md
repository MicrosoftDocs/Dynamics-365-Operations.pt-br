---
title: Configurar integração do Common Data Service
description: Você pode ativar ou desativar a integração entre o Common Data Service e a instância do Microsoft Dynamics 365 Human Resources. Também é possível exibir os detalhes da sincronização, limpar dados de rastreamento e ressincronizar uma entidade para ajudar com a solução de problemas de dados entre os dois ambientes.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 042daf3fdf7a906086af726472da050467d217e3
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008064"
---
# <a name="configure-common-data-service-integration"></a><span data-ttu-id="965a2-104">Configurar integração do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="965a2-104">Configure Common Data Service integration</span></span>

<span data-ttu-id="965a2-105">Você pode ativar ou desativar a integração entre o Common Data Service e a instância do Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="965a2-105">You can turn integration between Common Data Service and an instance of Microsoft Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="965a2-106">Também é possível exibir os detalhes da sincronização, limpar dados de rastreamento e ressincronizar uma entidade para ajudar com a solução de problemas de dados entre os dois ambientes.</span><span class="sxs-lookup"><span data-stu-id="965a2-106">You can also view the synchronization details, clear tracking data, and resync an entity to help troubleshoot data issues between the two environments.</span></span>

<span data-ttu-id="965a2-107">Quando você desativa a integração, os usuários podem fazer alterações no Human Resources ou no Common Data Service, mas essas alterações não são sincronizadas entre os dois ambientes.</span><span class="sxs-lookup"><span data-stu-id="965a2-107">When you turn off integration, users can make changes in Human Resources or Common Data Service, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="965a2-108">Por padrão, a integração entre o Human Resources e o Common Data Service é desativada ou ativada, dependendo da presença de dados de demonstração nos ambientes:</span><span class="sxs-lookup"><span data-stu-id="965a2-108">By default, integration between Human Resources and Common Data Service is turned either off or on, depending on the presence of demo data in the environments:</span></span>

- <span data-ttu-id="965a2-109">**Desativada** para novos ambientes que não incluem dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="965a2-109">**Off** for new environments that don't include demo data</span></span>
- <span data-ttu-id="965a2-110">**Ativada** para novos ambientes que incluem dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="965a2-110">**On** for new environments that include demo data</span></span>

<span data-ttu-id="965a2-111">Novos ambientes que incluem dados de demonstração começarão a sincronizar dados quando eles forem provisionados.</span><span class="sxs-lookup"><span data-stu-id="965a2-111">New environments that include demo data will start to sync data when they are provisioned.</span></span>

<span data-ttu-id="965a2-112">Talvez você queira desativar a integração nestas situações:</span><span class="sxs-lookup"><span data-stu-id="965a2-112">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="965a2-113">Você está preenchendo dados por meio da Estrutura de Gerenciamento de Dados e deve importar os dados várias vezes para que fiquem no estado correto.</span><span class="sxs-lookup"><span data-stu-id="965a2-113">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="965a2-114">Há problemas com dados no Human Resources ou no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="965a2-114">There are issues with data in either Human Resources or Common Data Service.</span></span> <span data-ttu-id="965a2-115">Se você desativar a integração, será possível excluir um registro em um ambiente sem excluí-lo de outro.</span><span class="sxs-lookup"><span data-stu-id="965a2-115">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="965a2-116">Quando você reativar a integração, o registro no ambiente onde ele não foi excluído será sincronizado com o ambiente de onde ele foi excluído.</span><span class="sxs-lookup"><span data-stu-id="965a2-116">When you turn integration back on, the record in the environment where it wasn't deleted will be synced back to the environment where it was deleted.</span></span> <span data-ttu-id="965a2-117">A sincronização começa na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Common Data Service** for executado.</span><span class="sxs-lookup"><span data-stu-id="965a2-117">Synchronization begins the next time the **Common Data Service integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="965a2-118">Ao desativar a integração de dados, certifique-se de não editar o mesmo registro em ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="965a2-118">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="965a2-119">Quando você reativar a integração, o registro que você editou pela última vez será sincronizado.</span><span class="sxs-lookup"><span data-stu-id="965a2-119">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="965a2-120">Portanto, se você não fizer as mesmas alterações no registro em ambos os ambientes, poderá ocorrer perda de dados.</span><span class="sxs-lookup"><span data-stu-id="965a2-120">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-common-data-service-integration-page"></a><span data-ttu-id="965a2-121">Acessar a página integração do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="965a2-121">Access the Common Data Service integration page</span></span>

1. <span data-ttu-id="965a2-122">Na instância do Human Resources onde você deseja ver ou configurar definições para a integração ao Common Data Service, selecione o bloco **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="965a2-122">In the Human Resources instance where you want to view or configure settings for the integration with Common Data Service, select the **System administration** tile.</span></span>

    <span data-ttu-id="965a2-123">[![Bloco Administração do sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="965a2-123">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="965a2-124">Selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="965a2-124">Select the **Links** tab.</span></span>

    <span data-ttu-id="965a2-125">[![Guia Links](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="965a2-125">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="965a2-126">Em **Integrações**, selecione **Configuração do Common Data Service**.</span><span class="sxs-lookup"><span data-stu-id="965a2-126">Under **Integrations**, select **Common Data Service configuration**.</span></span>

    <span data-ttu-id="965a2-127">[![Link de configuração do Common Data Service](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="965a2-127">[![Common Data Service configuration link](./media/hr-select-common-data-service-configuration.png)](./media/hr-select-common-data-service-configuration.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-common-data-service-on-or-off"></a><span data-ttu-id="965a2-128">Ativar ou desativar a integração de dados entre o Human Resources e o Common Data Service</span><span class="sxs-lookup"><span data-stu-id="965a2-128">Turn data integration between Human Resources and Common Data Service on or off</span></span>

- <span data-ttu-id="965a2-129">Para ativar a integração, defina a opção **Ativar a integração ao Common Data Service** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="965a2-129">To turn on integration, set the **Enable the integration to the Common Data Service** option to **Yes**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="965a2-130">Quando você ativar a integração, os dados serão sincronizados na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Common Data Service** for executado.</span><span class="sxs-lookup"><span data-stu-id="965a2-130">When you turn on integration, data will be synced the next time that the **Common Data Service integration missed request sync** batch job runs.</span></span> <span data-ttu-id="965a2-131">Todos os dados deverão estar disponíveis depois que o trabalho em lotes for concluído.</span><span class="sxs-lookup"><span data-stu-id="965a2-131">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="965a2-132">Para desativar a integração, defina a opção como **Não**.</span><span class="sxs-lookup"><span data-stu-id="965a2-132">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="965a2-133">[![Ativando ou desativando a integração do Common Data Service](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="965a2-133">[![Turning the Common Data Service integration on or off](./media/hr-enable-or-disable-common-data-service-integration.png)](./media/hr-enable-or-disable-common-data-service-integration.png)</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="965a2-134">Exibir detalhes da integração de dados</span><span class="sxs-lookup"><span data-stu-id="965a2-134">View data integration details</span></span>

<span data-ttu-id="965a2-135">Na FastTab **Administração** da página **Integração do Common Data Service**, você pode ver como os registros são vinculados juntos entre o Human Resources e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="965a2-135">On the **Administration** FastTab of the **Common Data Service integration** page, you can see how records are linked together between Human Resources and Common Data Service.</span></span>

- <span data-ttu-id="965a2-136">Para exibir os registros de uma entidade, selecione a entidade no campo **Nome da entidade CDS**.</span><span class="sxs-lookup"><span data-stu-id="965a2-136">To view the records for an entity, select the entity in the **CDS entity name** field.</span></span> <span data-ttu-id="965a2-137">A grade mostra todos os registros vinculados à entidade selecionada.</span><span class="sxs-lookup"><span data-stu-id="965a2-137">The grid shows all the records that are linked to the selected entity.</span></span>

<span data-ttu-id="965a2-138">[![Exibindo os registros de uma entidade](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span><span class="sxs-lookup"><span data-stu-id="965a2-138">[![Viewing the records for an entity](./media/hr-common-data-service-configuration-view-entity.png)](./media/hr-common-data-service-configuration-view-entity.png)</span></span>

> [!NOTE]
> <span data-ttu-id="965a2-139">Nem todas as entidades do Common Data Service estão listadas atualmente.</span><span class="sxs-lookup"><span data-stu-id="965a2-139">Not all Common Data Service entities are currently listed.</span></span> <span data-ttu-id="965a2-140">Somente as entidades que aceitam o uso de campos personalizados aparecem na grade.</span><span class="sxs-lookup"><span data-stu-id="965a2-140">Only entities that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="965a2-141">Novas entidades são disponibilizadas por meio de lançamentos contínuos do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="965a2-141">New entities become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="965a2-142">A grade inclui os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="965a2-142">The grid includes the following fields:</span></span>

- <span data-ttu-id="965a2-143">**Nome da entidade CDS** – o nome da entidade no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="965a2-143">**CDS entity name** – The name of the entity in Common Data Service.</span></span>
- <span data-ttu-id="965a2-144">**Referência da entidade CDS** – o identificador que o Common Data Service usa para identificar um registro.</span><span class="sxs-lookup"><span data-stu-id="965a2-144">**CDS entity reference** – The identifier that Common Data Service uses to identify a record.</span></span> <span data-ttu-id="965a2-145">Esse valor é equivalente a um valor **RecId** do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="965a2-145">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="965a2-146">Você pode encontrar o identificador ao abrir a entidade do Common Data Service no Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="965a2-146">You can find the identifier when you open the Common Data Service entity in Microsoft Excel.</span></span>
- <span data-ttu-id="965a2-147">**Nome da entidade do Human Resources** – a entidade que sincronizou os dados pela última vez com o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="965a2-147">**Human Resources entity name** – The entity that last synced data to Common Data Service.</span></span> <span data-ttu-id="965a2-148">A entidade pode ter o prefixo do Common Data Service ou outro prefixo.</span><span class="sxs-lookup"><span data-stu-id="965a2-148">The entity can have either the Common Data Service prefix or another prefix.</span></span>
- <span data-ttu-id="965a2-149">**Referência do Human Resources** – o valor **RecId** que é associado ao registro no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="965a2-149">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="965a2-150">**Foi excluído do CDS** – um valor que indica se o registro foi excluído do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="965a2-150">**Was deleted from CDS** – A value that indicates whether the record was deleted from Common Data Service.</span></span>

## <a name="remove-the-association-of-a-record-in-human-resources-from-common-data-service"></a><span data-ttu-id="965a2-151">Remover do Common Data Service a associação de um registro no Human Resources</span><span class="sxs-lookup"><span data-stu-id="965a2-151">Remove the association of a record in Human Resources from Common Data Service</span></span>

<span data-ttu-id="965a2-152">Se você tiver problemas durante a sincronização de dados entre o Human Resources e o Common Data Service, talvez seja possível resolvê-los limpando o rastreamento e permitindo que a tabela de rastreamento seja ressincronizada.</span><span class="sxs-lookup"><span data-stu-id="965a2-152">If you experience issues during data synchronization between Human Resources and Common Data Service, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="965a2-153">Se você remover a associação e alterar ou excluir um registro no Common Data Service, as alterações não serão sincronizadas com o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="965a2-153">If you remove the association, and then change or delete a record in Common Data Service, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="965a2-154">Se você fizer alterações no Human Resources, um novo registro de rastreamento será criado e o registro será atualizado no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="965a2-154">If you make changes in Human Resources, a new tracking record is created, and the record is updated in Common Data Service.</span></span>

- <span data-ttu-id="965a2-155">Para remover a associação de um registro entre o Human Resources e o Common Data Service, selecione a entidade no campo **Nome da entidade CDS** e selecione **Limpar informações de rastreamento**.</span><span class="sxs-lookup"><span data-stu-id="965a2-155">To remove the association of a record between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="965a2-156">[![Limpando informações de rastreamento](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="965a2-156">[![Clearing tracking information](./media/hr-common-data-service-configuration-clear-tracking.png)](./media/hr-common-data-service-configuration-clear-tracking.png)</span></span>

<span data-ttu-id="965a2-157">Para executar uma sincronização completa na entidade depois de desmarcar o rastreamento, consulte o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="965a2-157">To run a full synchronization on the entity after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-an-entity-between-human-resources-and-common-data-service"></a><span data-ttu-id="965a2-158">Sincronizar uma entidade entre o Human Resources e o Common Data Service</span><span class="sxs-lookup"><span data-stu-id="965a2-158">Sync an entity between Human Resources and Common Data Service</span></span>

<span data-ttu-id="965a2-159">Use este procedimento se as alterações do Common Data Service estiverem demorando muito para aparecer no Human Resources ou se você precisar atualizar a tabela de rastreamento depois de limpar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="965a2-159">Use this procedure if changes from Common Data Service are taking too long to appear in Human Resources, or if you must refresh the tracking table after you clear the tracking.</span></span>

- <span data-ttu-id="965a2-160">Para executar uma sincronização completa em uma entidade entre o Human Resources e o Common Data Service, selecione a entidade no campo **Nome da entidade CDS** e, em seguida, selecione **Sincronizar agora**.</span><span class="sxs-lookup"><span data-stu-id="965a2-160">To run a full synchronization on an entity between Human Resources and Common Data Service, select the entity in the **CDS entity name** field, and then select **Sync now**.</span></span>

<span data-ttu-id="965a2-161">[![Executando uma sincronização completa](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="965a2-161">[![Running a full synchronization](./media/hr-common-data-service-configuration-sync-now.png)](./media/hr-common-data-service-configuration-sync-now.png)</span></span>


