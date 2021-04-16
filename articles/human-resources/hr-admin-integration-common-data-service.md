---
title: Configurar integração do Dataverse
description: Você pode ativar ou desativar a integração entre o Microsoft Dataverse e Dynamics 365 Human Resources. Também é possível exibir os detalhes da sincronização, limpar dados de acompanhamento e ressincronizar uma tabela para ajudar na solução de problemas de dados entre os dois ambientes.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 080f66e4e13df44a77f0499c6d69686f0e3d7021
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801182"
---
# <a name="configure-dataverse-integration"></a><span data-ttu-id="11748-104">Configurar integração do Dataverse</span><span class="sxs-lookup"><span data-stu-id="11748-104">Configure Dataverse integration</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="11748-105">Você pode ativar ou desativar a integração entre o Microsoft Dataverse e Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="11748-105">You can turn integration between Microsoft Dataverse and Dynamics 365 Human Resources on or off.</span></span> <span data-ttu-id="11748-106">Também é possível exibir os detalhes da sincronização, limpar dados de acompanhamento e ressincronizar uma tabela para ajudar na solução de problemas de dados entre os dois ambientes.</span><span class="sxs-lookup"><span data-stu-id="11748-106">You can also view the synchronization details, clear tracking data, and resync a table to help troubleshoot data issues between the two environments.</span></span>

> [!NOTE]
> <span data-ttu-id="11748-107">Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="11748-107">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

<span data-ttu-id="11748-108">Quando você desativa a integração, os usuários podem fazer alterações no Human Resources ou no Dataverse, mas essas alterações não são sincronizadas entre os dois ambientes.</span><span class="sxs-lookup"><span data-stu-id="11748-108">When you turn off integration, users can make changes in Human Resources or Dataverse, but those changes aren't synced between the two environments.</span></span>

<span data-ttu-id="11748-109">Por padrão, a integração de dados entre o Human Resources e o Dataverse está desativada.</span><span class="sxs-lookup"><span data-stu-id="11748-109">By default, integration between Human Resources and Dataverse is turned off.</span></span>

<span data-ttu-id="11748-110">Talvez você queira desativar a integração nestas situações:</span><span class="sxs-lookup"><span data-stu-id="11748-110">You might want to turn off integration in these situations:</span></span>

- <span data-ttu-id="11748-111">Você está preenchendo dados por meio da Estrutura de Gerenciamento de Dados e deve importar os dados várias vezes para que fiquem no estado correto.</span><span class="sxs-lookup"><span data-stu-id="11748-111">You're filling in data through the Data Management Framework and must import the data multiple times to get it into a correct state.</span></span>

- <span data-ttu-id="11748-112">Há problemas com dados no Human Resources ou no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11748-112">There are issues with data in either Human Resources or Dataverse.</span></span> <span data-ttu-id="11748-113">Se você desativar a integração, será possível excluir um registro em um ambiente sem excluí-lo de outro.</span><span class="sxs-lookup"><span data-stu-id="11748-113">If you turn off integration, you can delete a record in one environment without deleting it in the other.</span></span> <span data-ttu-id="11748-114">Quando você reativar a integração, o registro no ambiente onde ele não foi excluído sincroniza com o ambiente de onde ele foi excluído.</span><span class="sxs-lookup"><span data-stu-id="11748-114">When you turn integration back on, the record in the environment where it wasn't deleted sync to the environment where it was deleted.</span></span> <span data-ttu-id="11748-115">A sincronização começa na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Dataverse** for executado.</span><span class="sxs-lookup"><span data-stu-id="11748-115">Synchronization begins the next time the **Dataverse integration missed request sync** batch job runs.</span></span>

> [!WARNING]
> <span data-ttu-id="11748-116">Ao desativar a integração de dados, certifique-se de não editar o mesmo registro em ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="11748-116">When you turn off data integration, make sure that you don't edit the same record in both environments.</span></span> <span data-ttu-id="11748-117">Quando você reativar a integração, o registro que você editou pela última vez será sincronizado.</span><span class="sxs-lookup"><span data-stu-id="11748-117">When you turn integration back on, the record that you last edited will be synced.</span></span> <span data-ttu-id="11748-118">Portanto, se você não fizer as mesmas alterações no registro em ambos os ambientes, poderá ocorrer perda de dados.</span><span class="sxs-lookup"><span data-stu-id="11748-118">Therefore, if you didn't make the same changes to the record in both environments, data loss can occur.</span></span>

## <a name="access-the-dataverse-integration-page"></a><span data-ttu-id="11748-119">Acessar a página integração do Dataverse</span><span class="sxs-lookup"><span data-stu-id="11748-119">Access the Dataverse integration page</span></span>

1. <span data-ttu-id="11748-120">Na instância do Human Resources onde você deseja ver ou configurar definições para a integração ao Dataverse, selecione o bloco **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="11748-120">In the Human Resources instance where you want to view or configure settings for the integration with Dataverse, select the **System administration** tile.</span></span>

    <span data-ttu-id="11748-121">[![Bloco Administração do sistema](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span><span class="sxs-lookup"><span data-stu-id="11748-121">[![System administration tile](./media/hr-select-system-administration.png)](./media/hr-select-system-administration.png)</span></span>

2. <span data-ttu-id="11748-122">Selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="11748-122">Select the **Links** tab.</span></span>

    <span data-ttu-id="11748-123">[![Guia Links](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span><span class="sxs-lookup"><span data-stu-id="11748-123">[![Links tab](./media/hr-system-administration-links.png)](./media/hr-system-administration-links.png)</span></span>

3. <span data-ttu-id="11748-124">Em **Integrações**, selecione **Configuração do Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="11748-124">Under **Integrations**, select **Dataverse configuration**.</span></span>

    <span data-ttu-id="11748-125">[![Link de configuração do Dataverse](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span><span class="sxs-lookup"><span data-stu-id="11748-125">[![Dataverse configuration link](./media/hr-admin-integration-dataverse-select.png)](./media/hr-admin-integration-dataverse-select.png)</span></span>

## <a name="turn-data-integration-between-human-resources-and-dataverse-on-or-off"></a><span data-ttu-id="11748-126">Ativar ou desativar a integração de dados entre o Human Resources e o Dataverse</span><span class="sxs-lookup"><span data-stu-id="11748-126">Turn data integration between Human Resources and Dataverse on or off</span></span>

- <span data-ttu-id="11748-127">Para ativar a integração, defina a opção **Habilitar a integração ao Dataverse** como **Sim** na página **Integração ao Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="11748-127">To turn on integration, set the **Enable Dataverse integration** option to **Yes** on the **Microsoft Dataverse integration** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="11748-128">Quando você ativar a integração, os dados serão sincronizados na próxima vez que o trabalho em lotes **Sincronização da solicitação perdida da integração do Dataverse** for executado.</span><span class="sxs-lookup"><span data-stu-id="11748-128">When you turn on integration, data will be synced the next time that the **Dataverse integration missed request sync** batch job runs.</span></span> <span data-ttu-id="11748-129">Todos os dados deverão estar disponíveis depois que o trabalho em lotes for concluído.</span><span class="sxs-lookup"><span data-stu-id="11748-129">All data should be available after the batch job is completed.</span></span>

- <span data-ttu-id="11748-130">Para desativar a integração, defina a opção como **Não**.</span><span class="sxs-lookup"><span data-stu-id="11748-130">To turn off integration, set the option to **No**.</span></span>

<span data-ttu-id="11748-131">[![Ativando ou desativando a integração do Dataverse](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span><span class="sxs-lookup"><span data-stu-id="11748-131">[![Turning the Dataverse integration on or off](./media/hr-admin-integration-dataverse-enable-disable.png)](./media/hr-admin-integration-dataverse-enable-disable.png)</span></span>

> [!WARNING]
> <span data-ttu-id="11748-132">É altamente recomendável desativar a integração do Dataverse enquanto as tarefas de migração de dados são executadas.</span><span class="sxs-lookup"><span data-stu-id="11748-132">We strongly recommend turning off Dataverse integration while performing data migration tasks.</span></span> <span data-ttu-id="11748-133">Grandes uploads de dados podem afetar significativamente o desempenho.</span><span class="sxs-lookup"><span data-stu-id="11748-133">Large data uploads can significantly impact performance.</span></span> <span data-ttu-id="11748-134">Por exemplo, fazer upload de 2000 trabalhadores pode levar várias horas quando a integração estiver habilitada e menos de uma hora quando estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="11748-134">For example, uploading 2000 workers can take several hours when integration is enabled, and less than one hour when it's disabled.</span></span> <span data-ttu-id="11748-135">Os números fornecidos neste exemplo são somente para fins de demonstração.</span><span class="sxs-lookup"><span data-stu-id="11748-135">The numbers provided in this example are for demonstration purposes only.</span></span> <span data-ttu-id="11748-136">A quantidade exata de tempo necessária para importar registros pode variar bastante com base em vários fatores.</span><span class="sxs-lookup"><span data-stu-id="11748-136">The exact amount of time it takes to import records can vary greatly based on many factors.</span></span>

## <a name="view-data-integration-details"></a><span data-ttu-id="11748-137">Exibir detalhes da integração de dados</span><span class="sxs-lookup"><span data-stu-id="11748-137">View data integration details</span></span>

<span data-ttu-id="11748-138">Na FastTab **Administração** da página **Integração ao Microsoft Dataverse**, você pode ver como linhas são vinculadas juntas entre o Human Resources e o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11748-138">On the **Administration** FastTab of the **Microsoft Dataverse integration** page, you can see how rows are linked together between Human Resources and Dataverse.</span></span>

- <span data-ttu-id="11748-139">Para exibir as linhas de uma tabela, selecione a tabela no campo **Tabela do Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="11748-139">To view the rows for a table, select the table in the **Dataverse table** field.</span></span> <span data-ttu-id="11748-140">A grade mostra todas as linhas vinculadas à tabela selecionada.</span><span class="sxs-lookup"><span data-stu-id="11748-140">The grid shows all the rows that are linked to the selected table.</span></span>

> [!NOTE]
> <span data-ttu-id="11748-141">Nem todas as tabelas do Dataverse estão listadas atualmente.</span><span class="sxs-lookup"><span data-stu-id="11748-141">Not all Dataverse tables are currently listed.</span></span> <span data-ttu-id="11748-142">Somente as tabelas que aceitam o uso de campos personalizados aparecem na grade.</span><span class="sxs-lookup"><span data-stu-id="11748-142">Only tables that support the use of custom fields appear in the grid.</span></span> <span data-ttu-id="11748-143">Novas tabelas são disponibilizadas por meio de lançamentos contínuos do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="11748-143">New tables become available through continuous releases of Human Resources.</span></span>

<span data-ttu-id="11748-144">A grade inclui os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="11748-144">The grid includes the following fields:</span></span>

- <span data-ttu-id="11748-145">**Tabela do Dataverse** – o nome da tabela no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11748-145">**Dataverse table** – The name of the table in Dataverse.</span></span>
- <span data-ttu-id="11748-146">**Referência da tabela do Dataverse** – o identificador que o Dataverse usa para identificar um registro.</span><span class="sxs-lookup"><span data-stu-id="11748-146">**Dataverse table reference** – The identifier that Dataverse uses to identify a record.</span></span> <span data-ttu-id="11748-147">Esse valor é equivalente a um valor **RecId** do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="11748-147">This value is equivalent to a Human Resources **RecId** value.</span></span> <span data-ttu-id="11748-148">Você pode encontrar o identificador ao abrir a tabela do Dataverse no Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="11748-148">You can find the identifier when you open the Dataverse table in Microsoft Excel.</span></span>
- <span data-ttu-id="11748-149">**Nome da entidade do Human Resources** – a entidade do Human Resources que sincronizou dados pela última vez para o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11748-149">**Human Resources entity name** – The Human Resources entity that last synced data to Dataverse.</span></span> <span data-ttu-id="11748-150">A entidade pode ter o prefixo do Dataverse ou outro prefixo.</span><span class="sxs-lookup"><span data-stu-id="11748-150">The entity can have either the Dataverse prefix or another prefix.</span></span>
- <span data-ttu-id="11748-151">**Referência do Human Resources** – o valor **RecId** que é associado ao registro no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="11748-151">**Human Resources reference** – The **RecId** value that is associated with the record in Human Resources.</span></span>
- <span data-ttu-id="11748-152">**Excluído do Dataverse** – um valor que indica se a linha foi excluída do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11748-152">**Deleted from Dataverse** – A value that indicates whether the row was deleted from Dataverse.</span></span>

> [!NOTE]
> <span data-ttu-id="11748-153">Os registros no Human Resources correspondem a linhas no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11748-153">Records in Human Resources correspond to rows in Dataverse.</span></span>

## <a name="remove-the-association-of-a-human-resources-record-from-a-dataverse-row"></a><span data-ttu-id="11748-154">Remover a associação de um registro do Human Resources de uma linha do Dataverse</span><span class="sxs-lookup"><span data-stu-id="11748-154">Remove the association of a Human Resources record from a Dataverse row</span></span>

<span data-ttu-id="11748-155">Se você tiver problemas durante a sincronização de dados entre o Human Resources e o Dataverse, talvez seja possível resolvê-los limpando o rastreamento e permitindo que a tabela de rastreamento seja ressincronizada.</span><span class="sxs-lookup"><span data-stu-id="11748-155">If you experience issues during data synchronization between Human Resources and Dataverse, you might be able to resolve them by clearing the tracking and letting the tracking table be resynced.</span></span> <span data-ttu-id="11748-156">Se você remover a associação e alterar ou excluir uma linha no Dataverse, as alterações não serão sincronizadas com o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="11748-156">If you remove the association, and then change or delete a row in Dataverse, the changes won't be synced to Human Resources.</span></span> <span data-ttu-id="11748-157">Se você fizer alterações no Human Resources, um novo registro de acompanhamento será criado e a linha será atualizada no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="11748-157">If you make changes in Human Resources, a new tracking record is created, and the row is updated in Dataverse.</span></span>

- <span data-ttu-id="11748-158">Para remover a associação de um registro do Human Resources e uma linha do Dataverse, selecione a tabela no campo **Tabela do Dataverse** e selecione **Limpar informações de acompanhamento**.</span><span class="sxs-lookup"><span data-stu-id="11748-158">To remove the association of a Human Resources record and a Dataverse row, select the table in the **Dataverse table** field, and then select **Clear tracking information**.</span></span>

<span data-ttu-id="11748-159">[![Limpando informações de rastreamento](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span><span class="sxs-lookup"><span data-stu-id="11748-159">[![Clearing tracking information](./media/hr-admin-integration-dataverse-clear-tracking.png)](./media/hr-admin-integration-dataverse-clear-tracking.png)</span></span>

<span data-ttu-id="11748-160">Para executar uma sincronização completa na tabela após limpar o acompanhamento, consulte o próximo procedimento.</span><span class="sxs-lookup"><span data-stu-id="11748-160">To run a full synchronization on the table after you clear the tracking, see the next procedure.</span></span>

## <a name="sync-a-table-between-human-resources-and-dataverse"></a><span data-ttu-id="11748-161">Sincronizar uma tabela entre o Human Resources e o Dataverse</span><span class="sxs-lookup"><span data-stu-id="11748-161">Sync a table between Human Resources and Dataverse</span></span>

<span data-ttu-id="11748-162">Use este procedimento quando:</span><span class="sxs-lookup"><span data-stu-id="11748-162">Use this procedure when:</span></span>

- <span data-ttu-id="11748-163">As alterações de Dataverse são exibidas de forma muito longa em Human Resources.</span><span class="sxs-lookup"><span data-stu-id="11748-163">Changes from Dataverse take too long to appear in Human Resources.</span></span>

- <span data-ttu-id="11748-164">Você deve atualizar a tabela de controle depois de limpar o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="11748-164">You must refresh the tracking table after clearing the tracking.</span></span>

<span data-ttu-id="11748-165">Para executar uma sincronização completa em uma tabela entre o Human Resources e o Dataverse:</span><span class="sxs-lookup"><span data-stu-id="11748-165">To run a full synchronization on a table between Human Resources and Dataverse:</span></span>

1. <span data-ttu-id="11748-166">Selecione a tabela no campo **Tabela do Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="11748-166">Select the table in the **Dataverse table** field.</span></span>

2. <span data-ttu-id="11748-167">Selecione **Sincronizar agora**.</span><span class="sxs-lookup"><span data-stu-id="11748-167">Select **Sync now**.</span></span>

<span data-ttu-id="11748-168">[![Executando uma sincronização completa](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span><span class="sxs-lookup"><span data-stu-id="11748-168">[![Running a full synchronization](./media/hr-admin-integration-dataverse-sync-now.png)](./media/hr-admin-integration-dataverse-sync-now.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="11748-169">Consulte também</span><span class="sxs-lookup"><span data-stu-id="11748-169">See also</span></span>

[<span data-ttu-id="11748-170">Tabelas do Dataverse</span><span class="sxs-lookup"><span data-stu-id="11748-170">Dataverse tables</span></span>](hr-developer-entities.md)<br>
[<span data-ttu-id="11748-171">Configurar tabelas virtuais do Dataverse</span><span class="sxs-lookup"><span data-stu-id="11748-171">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="11748-172">Perguntas frequentes de tabelas virtuais do Human Resources</span><span class="sxs-lookup"><span data-stu-id="11748-172">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)<br>
[<span data-ttu-id="11748-173">O que é o Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="11748-173">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[<span data-ttu-id="11748-174">Atualizações de terminologia</span><span class="sxs-lookup"><span data-stu-id="11748-174">Terminology updates</span></span>](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]