---
title: Gerenciar arrendamentos por meio da estrutura de importação de arrendamento
description: Este tópico explica como usar a Estrutura de importação de arrendamento para ajustar vários arrendamentos ao mesmo tempo.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7df2f55f596cab54315c2da2ec0492422514f49c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971294"
---
# <a name="manage-leases-through-the-lease-import-framework"></a><span data-ttu-id="2cb95-103">Gerenciar arrendamentos por meio da estrutura de importação de arrendamento</span><span class="sxs-lookup"><span data-stu-id="2cb95-103">Manage leases through the Lease import framework</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2cb95-104">Este tópico explica como usar a Estrutura de importação de arrendamento para ajustar vários arrendamentos em uma etapa.</span><span class="sxs-lookup"><span data-stu-id="2cb95-104">This topic explains how to use the Lease import framework to adjust multiple leases in one step.</span></span> <span data-ttu-id="2cb95-105">Ao usar esse recurso, você poderá poupar tempo e também garantir ajustes mais precisos, reduzindo a probabilidade de erro humano.</span><span class="sxs-lookup"><span data-stu-id="2cb95-105">By using this capability, you can save time, and you can also ensure more accurate adjustments by reducing the chance of human error.</span></span> <span data-ttu-id="2cb95-106">Além disso, esse recurso pode conectar o Microsoft Dynamics 365 Finance a entidades de dados externas para carregar dados com eficiência.</span><span class="sxs-lookup"><span data-stu-id="2cb95-106">Additionally, this capability can connect Microsoft Dynamics 365 Finance with external data entities to efficiently upload data.</span></span>

<span data-ttu-id="2cb95-107">As seguintes entidades de dados podem ser usadas para integrar o Arrendamento de ativos a sistemas externos:</span><span class="sxs-lookup"><span data-stu-id="2cb95-107">The following data entities can be used to integrate Asset leasing with external systems:</span></span>

- <span data-ttu-id="2cb95-108">Preparo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="2cb95-108">Lease staging</span></span>
- <span data-ttu-id="2cb95-109">Preparo de contrato de pagamento</span><span class="sxs-lookup"><span data-stu-id="2cb95-109">Payment contract staging</span></span>
- <span data-ttu-id="2cb95-110">Preparo de contrato de execução</span><span class="sxs-lookup"><span data-stu-id="2cb95-110">Executory contract staging</span></span>

<span data-ttu-id="2cb95-111">Você pode usar o processo de importação para ajustar um arrendamento, atualizar informações não financeiras ou adicionar novos arrendamentos.</span><span class="sxs-lookup"><span data-stu-id="2cb95-111">You can use the import process to adjust a lease, update non-financial information, or add new leases.</span></span> <span data-ttu-id="2cb95-112">Você pode exibir e editar os dados de leasing antes de importá-los.</span><span class="sxs-lookup"><span data-stu-id="2cb95-112">You can view and edit the leasing data before you import it.</span></span>

<span data-ttu-id="2cb95-113">O sistema pode executar os três processos a seguir por meio do pacote de importação de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="2cb95-113">The system can run the following three processes through the lease import suite.</span></span>

| <span data-ttu-id="2cb95-114">Tipo de processo</span><span class="sxs-lookup"><span data-stu-id="2cb95-114">Process type</span></span>  | <span data-ttu-id="2cb95-115">descrição</span><span class="sxs-lookup"><span data-stu-id="2cb95-115">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="2cb95-116">Adicionar registro</span><span class="sxs-lookup"><span data-stu-id="2cb95-116">Add record</span></span>    | <span data-ttu-id="2cb95-117">Os arrendamentos migrados com esse tipo de processo criam um arrendamento no sistema.</span><span class="sxs-lookup"><span data-stu-id="2cb95-117">Migrated leases that have this process type create a lease in the system.</span></span> <span data-ttu-id="2cb95-118">O plano de pagamento deve ser confirmado manualmente e a entrada do diário de reconhecimento inicial deve ser lançada manualmente após a migração.</span><span class="sxs-lookup"><span data-stu-id="2cb95-118">The payment schedule must be manually confirmed, and the initial recognition journal entry must be manually posted after the migration.</span></span> |
| <span data-ttu-id="2cb95-119">Atualizar registro</span><span class="sxs-lookup"><span data-stu-id="2cb95-119">Update record</span></span> | <span data-ttu-id="2cb95-120">Os arrendamentos migrados com esse tipo de processo atualizam valores de campo para um arrendamento que já está no sistema.</span><span class="sxs-lookup"><span data-stu-id="2cb95-120">Migrated leases that have this process type update field values for a lease that is already in the system.</span></span> <span data-ttu-id="2cb95-121">Somente os campos selecionados na página **Atualizar seleção de campos** são atualizados.</span><span class="sxs-lookup"><span data-stu-id="2cb95-121">Only the fields that have been selected on the **Update fields selection** page are updated.</span></span> <span data-ttu-id="2cb95-122">É recomendável selecionar campos não financeiros na página **Atualizar seleção de campos**, pois esse tipo de processo não ajusta o arrendamento.</span><span class="sxs-lookup"><span data-stu-id="2cb95-122">We recommended that you select non-financial fields on the **Update fields selection** page, because this process type doesn't adjust the lease.</span></span> |
| <span data-ttu-id="2cb95-123">Ajustar registro</span><span class="sxs-lookup"><span data-stu-id="2cb95-123">Adjust record</span></span> | <span data-ttu-id="2cb95-124">Os arrendamentos migrados com esse tipo de processo ajustam o arrendamento.</span><span class="sxs-lookup"><span data-stu-id="2cb95-124">Migrated leases that have this process type adjust the lease.</span></span> <span data-ttu-id="2cb95-125">Esse ajuste causa uma modificação no arrendamento mercantil do arrendamento.</span><span class="sxs-lookup"><span data-stu-id="2cb95-125">This adjustment causes a financial lease modification of the lease.</span></span> <span data-ttu-id="2cb95-126">Após o processamento do arrendamento, o sistema cria uma nova agenda de pagamento usando os novos dados do pacote de importação de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="2cb95-126">After the lease is processed, the system creates a new payment schedule by using the new data from the lease import suite.</span></span> <span data-ttu-id="2cb95-127">O sistema não confirma a agenda de pagamento ou o lançamento da entrada do diário de ajuste.</span><span class="sxs-lookup"><span data-stu-id="2cb95-127">The system doesn't confirm the payment schedule or post the adjustment journal entry.</span></span> |

<span data-ttu-id="2cb95-128">Depois que as informações forem carregadas por meio do espaço de trabalho **Gerenciamento de dados**, abra a página **Importar cabeçalho** (**Arrendamento de ativos \> Estrutura de importação de arrendamento \> Importar cabeçalho**).</span><span class="sxs-lookup"><span data-stu-id="2cb95-128">After information is uploaded through the **Data management** workspace, open the **Import header** page (**Asset leasing \> Lease import framework \> Import header**).</span></span> <span data-ttu-id="2cb95-129">Esta página lista todas as importações das três entidades de dados listadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2cb95-129">This page lists all imports of the three data entities that were listed earlier.</span></span>

<span data-ttu-id="2cb95-130">Para exibir os dados de preparo de arrendamento antes da execução do processamento, selecione **Dados de preparo**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-130">To view the lease staging data before processing is run, select **Staging data**.</span></span>

<span data-ttu-id="2cb95-131">A função comparar permite comparar um registro que está sendo importado com o registro correspondente que já está no sistema.</span><span class="sxs-lookup"><span data-stu-id="2cb95-131">The compare function lets you compare a record that you're importing with the corresponding record that's already in your system.</span></span> <span data-ttu-id="2cb95-132">Para comparar um registro de arrendamento individual, selecione um arrendamento e depois **Comparar**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-132">To compare an individual lease record, select a lease, and then select **Compare**.</span></span> <span data-ttu-id="2cb95-133">Você deve concluir esta etapa para gerar um relatório **Diferenças** antes de migrar os registros de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="2cb95-133">You should complete this step to generate a **Differences** report before you migrate the lease records.</span></span> <span data-ttu-id="2cb95-134">A funcionalidade Comparar compara os valores dos dados de preparo com os valores para os arrendamentos que estão no sistema no momento.</span><span class="sxs-lookup"><span data-stu-id="2cb95-134">The Compare functionality compares the values in the staging data to the values for leases that are currently in the system.</span></span>

> [!NOTE]
> <span data-ttu-id="2cb95-135">A funcionalidade Comparar não funciona para arrendamentos com o tipo de processo **Adicionar registro**, porque não há nada para comparar ao arrendamento.</span><span class="sxs-lookup"><span data-stu-id="2cb95-135">The Compare functionality doesn't work for leases that have the **Add record** process type, because there is nothing to compare against that lease.</span></span>
>
> <span data-ttu-id="2cb95-136">Para comparar vários arrendamentos ao mesmo tempo, acesse **Arrendamento de ativos \> Estrutura de importação de arrendamento \> Periódico \> Comparar** e selecione **Comparar**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-136">To compare multiple leases at the same time, go to **Asset leasing \> Lease import framework \> Periodic \> Compare**, and select **Compare**.</span></span>

<span data-ttu-id="2cb95-137">Para cada entidade, você pode exibir as diferenças entre o que está atualmente no sistema e o que está nas tabelas de preparo.</span><span class="sxs-lookup"><span data-stu-id="2cb95-137">For each entity, you can view the differences between what is currently in the system and what is in the staging tables.</span></span> <span data-ttu-id="2cb95-138">Para cada entidade nas tabelas de preparo, selecione **Consultar diferenças**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-138">For each entity in the staging tables, select **See differences**.</span></span> <span data-ttu-id="2cb95-139">A caixa de diálogo exibida mostra o valor atual e o valor de preparo proposto.</span><span class="sxs-lookup"><span data-stu-id="2cb95-139">The dialog box that appears shows the current value and the proposed staging value.</span></span>

<span data-ttu-id="2cb95-140">Você também pode atualizar o valor de preparo alterando-o na coluna **Novo Valor** e selecionando **Atualizar preparo**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-140">You can also update the staging value by changing it in the **New Value** column and then selecting **Update staging**.</span></span>

<span data-ttu-id="2cb95-141">Você pode validar arrendamentos para garantir que os registros possam ser trazidos para o sistema sem introduzir erros.</span><span class="sxs-lookup"><span data-stu-id="2cb95-141">You can validate leases to ensure that the records can be brought into the system without introducing errors.</span></span> <span data-ttu-id="2cb95-142">Antes da migração de um registro de arrendamento, o sistema executa várias validações para garantir que o registro seja importado com êxito.</span><span class="sxs-lookup"><span data-stu-id="2cb95-142">Before a lease record is migrated, the system runs several validations to ensure that the record will be successfully imported.</span></span> <span data-ttu-id="2cb95-143">Para validar um arrendamento individual, selecione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-143">To validate an individual lease, select **Validate**.</span></span>

> [!NOTE]
> <span data-ttu-id="2cb95-144">Para validar vários arrendamentos ao mesmo tempo, acesse **Arrendamento de ativos \> Estrutura de importação de arrendamento \> Periódico \> Validar** e selecione **Comparar**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-144">To validate multiple leases at the same time, go to **Asset leasing \> Lease import framework \> Periodic \> Validate**, and select **Compare**.</span></span>

<span data-ttu-id="2cb95-145">Para processar um arrendamento individual, selecione **Migrar registros de arrendamento** na página **Importar cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-145">To process an individual lease, select **Migrate lease records** on the **Import header** page.</span></span> <span data-ttu-id="2cb95-146">Quando um arrendamento é migrado, o sistema executa a ação especificada no campo **Tipo de processo**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-146">When a lease is migrated, the system performs the action that is specified in the **Process type** field.</span></span>

> [!NOTE]
> <span data-ttu-id="2cb95-147">Para validar vários arrendamentos ao mesmo tempo, acesse **Arrendamento de ativos \> Estrutura de importação de arrendamento \> Periódico \> Validar** e selecione **Comparar**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-147">To validate multiple leases at the same time, go to **Asset leasing \> Lease import framework \> Periodic \> Validate**, and select **Compare**.</span></span>

<span data-ttu-id="2cb95-148">Após a comparação dos arrendamentos, você poderá executar um relatório para exibir as diferenças para cada arrendamento incluído na ID de importação.</span><span class="sxs-lookup"><span data-stu-id="2cb95-148">After the leases are compared, you can run a report to view the differences for each lease that is included in the import ID.</span></span> <span data-ttu-id="2cb95-149">Para executar o relatório para um arrendamento, selecione o arrendamento nos dados de preparo e selecione **Comparar e exibir relatório \> Relatório de diferenças**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-149">To run the report for one lease, select that lease in the staging data, and then select **Compare and view report \> Differences report**.</span></span>

> [!NOTE]
> <span data-ttu-id="2cb95-150">Para validar vários arrendamentos ao mesmo tempo, acesse **Arrendamento de ativos \> Consultas e relatórios \> Relatório de diferenças** e selecione **Comparar**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-150">To validate multiple leases at the same time, go to **Asset leasing \> Inquiries and reports \> Differences report**, and select **Compare**.</span></span>

## <a name="set-up-update-fields"></a><span data-ttu-id="2cb95-151">Configurar campos de atualização</span><span class="sxs-lookup"><span data-stu-id="2cb95-151">Set up update fields</span></span>

<span data-ttu-id="2cb95-152">Se estiver usando a estrutura de importação de arrendamento para atualizar arrendamentos e o tipo de processo for **Atualizar registro**, você poderá selecionar campos específicos para atualizar.</span><span class="sxs-lookup"><span data-stu-id="2cb95-152">If you're using the Lease import framework to update leases, and the process type is **Update record**, you can select specific fields to update.</span></span>

1. <span data-ttu-id="2cb95-153">Acesse **Arrendamento de ativos \> Estrutura de importação de arrendamento \> Configuração \> Atualização de seleção de campo**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-153">Go to **Asset leasing \> Lease import framework \> Setup \> Update field selection**.</span></span>
2. <span data-ttu-id="2cb95-154">Na página exibida, selecione os campos a serem atualizados e, em seguida, selecione a seta verde para movê-los para a lista **Campos selecionados**.</span><span class="sxs-lookup"><span data-stu-id="2cb95-154">On the page that appears, select the fields to update, and then select the green arrow to move them to the **Selected fields** list.</span></span> <span data-ttu-id="2cb95-155">Somente os campos na lista de **Campos selecionados** podem ser atualizados com o uso do pacote de importação de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="2cb95-155">Only fields in the **Selected fields** list can be updated by using the lease import suite.</span></span>