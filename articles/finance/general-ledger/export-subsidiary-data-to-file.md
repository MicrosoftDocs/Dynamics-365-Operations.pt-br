---
title: Exportar dados da subsidiária para arquivos
description: Este tópico explica como preparar a exportação de dados do Microsoft Dynamics 365 Finance e, depois, importá-los para uma entidade legal consolidada.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: bae0a28c59f327e47378eef6392d5e304bbde9a8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826169"
---
# <a name="export-subsidiary-data-to-files"></a><span data-ttu-id="d9abf-103">Exportar dados da subsidiária para arquivos</span><span class="sxs-lookup"><span data-stu-id="d9abf-103">Export subsidiary data to files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9abf-104">Use a página **Exportar** (**Administração do sistema \> Espaços de trabalho \> Importação/Exportação**) para preparar a exportação de dados da subsidiária para arquivos que podem ser importados em uma entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="d9abf-104">You use the **Export** page (**System administration \> Workspaces \> Import/Export**) to prepare to export subsidiary data to files that can then be imported into a consolidated legal entity.</span></span> <span data-ttu-id="d9abf-105">Para obter mais informações sobre os processos de importação e exportação, consulte [Visão geral de trabalhos de importação e exportação de dados](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="d9abf-105">For more information about the import and export processes, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>

1. <span data-ttu-id="d9abf-106">Crie uma entidade legal para o processo de consolidação.</span><span class="sxs-lookup"><span data-stu-id="d9abf-106">Create a legal entity for the consolidation process.</span></span> <span data-ttu-id="d9abf-107">Para obter informações sobre como criar entidades legais, consulte [Criar uma entidade legal](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span><span class="sxs-lookup"><span data-stu-id="d9abf-107">For information about how to create legal entities, see [Create a legal entity](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span></span> <span data-ttu-id="d9abf-108">Para obter mais informações, consulte [Preparar uma entidade legal para uso no processo de consolidação](prepare-company-for-consolidation.md) e [Configurar uma entidade legal subsidiária para consolidação](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="d9abf-108">For more information, see [Prepare a legal entity for use in the consolidation process](prepare-company-for-consolidation.md) and [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span> 

2. <span data-ttu-id="d9abf-109">Acesse **Consolidações \> Exportar saldos da empresa**.</span><span class="sxs-lookup"><span data-stu-id="d9abf-109">Go to **Consolidations \> Export company balances**.</span></span> <span data-ttu-id="d9abf-110">Na página **Exportar saldos da empresa**, na guia **Critérios**, especifique os detalhes da consolidação definindo os campos a seguir.</span><span class="sxs-lookup"><span data-stu-id="d9abf-110">On the **Export company balances** page, on the **Criteria** tab, specify the details of the consolidation by setting the following fields.</span></span>

    | <span data-ttu-id="d9abf-111">Campo</span><span class="sxs-lookup"><span data-stu-id="d9abf-111">Field</span></span>                             | <span data-ttu-id="d9abf-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="d9abf-112">Description</span></span> |
    |-----------------------------------|-------|
    | <span data-ttu-id="d9abf-113">Conta principal</span><span class="sxs-lookup"><span data-stu-id="d9abf-113">Main account</span></span>                      | <span data-ttu-id="d9abf-114">Especifique as contas a serem consolidadas.</span><span class="sxs-lookup"><span data-stu-id="d9abf-114">Specify the accounts to consolidate.</span></span> <span data-ttu-id="d9abf-115">Para incluir todas as contas, deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="d9abf-115">To include all accounts, leave this field blank.</span></span> |
    | <span data-ttu-id="d9abf-116">Usar conta de consolidação</span><span class="sxs-lookup"><span data-stu-id="d9abf-116">Use consolidation account</span></span>         | <span data-ttu-id="d9abf-117">Se você especificou contas de consolidação, defina esta opção como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d9abf-117">If you've specified consolidation accounts, set this option to **Yes**.</span></span> |
    | <span data-ttu-id="d9abf-118">Selecionar conta de consolidação de</span><span class="sxs-lookup"><span data-stu-id="d9abf-118">Select consolidation account from</span></span> | <span data-ttu-id="d9abf-119">Selecione **Conta principal** ou **Grupo de contas de consolidação**.</span><span class="sxs-lookup"><span data-stu-id="d9abf-119">Select either **Main account** or **Consolidation account group**.</span></span> |
    | <span data-ttu-id="d9abf-120">Grupo de contas de consolidação</span><span class="sxs-lookup"><span data-stu-id="d9abf-120">Consolidation account group</span></span>       | <span data-ttu-id="d9abf-121">Selecione um grupo de contas de consolidação para a conta de consolidação selecionada.</span><span class="sxs-lookup"><span data-stu-id="d9abf-121">Select a consolidation account group for the consolidation account that you selected.</span></span> |
    | <span data-ttu-id="d9abf-122">Período de consolidação</span><span class="sxs-lookup"><span data-stu-id="d9abf-122">Consolidation period</span></span>              | <span data-ttu-id="d9abf-123">Especifique a datas "de" e "até" para a consolidação.</span><span class="sxs-lookup"><span data-stu-id="d9abf-123">Specify "from" and "to" dates for the consolidation.</span></span> |
    | <span data-ttu-id="d9abf-124">Incluir valores reais</span><span class="sxs-lookup"><span data-stu-id="d9abf-124">Include actual amounts</span></span>            | <span data-ttu-id="d9abf-125">Defina esta opção como **Sim** para incluir valores reais.</span><span class="sxs-lookup"><span data-stu-id="d9abf-125">Set this option to **Yes** to include actual amounts.</span></span> |
    | <span data-ttu-id="d9abf-126">Incluir valores de orçamento</span><span class="sxs-lookup"><span data-stu-id="d9abf-126">Include budget amounts</span></span>            | <span data-ttu-id="d9abf-127">Defina esta opção como **Sim** para incluir valores de orçamento em consolidações.</span><span class="sxs-lookup"><span data-stu-id="d9abf-127">Set this option to **Yes** to include budget amounts in consolidations.</span></span> |
    | <span data-ttu-id="d9abf-128">Modelos de orçamento</span><span class="sxs-lookup"><span data-stu-id="d9abf-128">Budget models</span></span>                     | <span data-ttu-id="d9abf-129">Especifique o modelo de orçamento a ser incluído.</span><span class="sxs-lookup"><span data-stu-id="d9abf-129">Specify the budget model to include.</span></span> |

3. <span data-ttu-id="d9abf-130">Na guia **Dimensões financeiras**, especifique os detalhes da consolidação:</span><span class="sxs-lookup"><span data-stu-id="d9abf-130">On the **Financial dimensions** tab, specify the details of the consolidation:</span></span>

    - <span data-ttu-id="d9abf-131">Especifique as informações de dimensão financeira que devem ser transferidas das transações nas contas de subsidiárias para as transações na entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="d9abf-131">Specify the financial dimension information that should be transferred from the transactions in the subsidiary accounts to the transactions in the consolidated legal entity.</span></span>
    - <span data-ttu-id="d9abf-132">Selecione dimensões financeiras na lista.</span><span class="sxs-lookup"><span data-stu-id="d9abf-132">Select financial dimensions in the list.</span></span>
    - <span data-ttu-id="d9abf-133">Identifique a especificação correta para cada dimensão financeira consolidada.</span><span class="sxs-lookup"><span data-stu-id="d9abf-133">Identify the correct specification for each financial dimension that is consolidated.</span></span> <span data-ttu-id="d9abf-134">As opções disponíveis incluem **Dimensão**, **Dimensão do grupo**, **Contas da empresa** e **Conta**.</span><span class="sxs-lookup"><span data-stu-id="d9abf-134">The available options include **Dimension**, **Group dimension**, **Company accounts**, and **Account**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d9abf-135">A opção **Dimensão de grupo** permite definir o valor de dimensão usado pelo grupo de empresas que está sendo consolidado.</span><span class="sxs-lookup"><span data-stu-id="d9abf-135">The **Group dimension** option lets you define the dimension value that is used by the group of companies that is being consolidated.</span></span>

    - <span data-ttu-id="d9abf-136">Especifique a ordem de segmento para consolidação.</span><span class="sxs-lookup"><span data-stu-id="d9abf-136">Specify the segment order to consolidate in.</span></span>

4. <span data-ttu-id="d9abf-137">Na guia **Entidades legais**, siga estas etapas para especificar a entidade legal que você está exportando:</span><span class="sxs-lookup"><span data-stu-id="d9abf-137">On the **Legal entities** tab, follow these steps to specify the legal entity that you're exporting:</span></span>

    1. <span data-ttu-id="d9abf-138">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d9abf-138">Select **New**.</span></span>
    2. <span data-ttu-id="d9abf-139">No campo **Entidade legal de origem**, insira a entidade legal.</span><span class="sxs-lookup"><span data-stu-id="d9abf-139">In the **Source legal entity** field, enter the legal entity.</span></span>

        <span data-ttu-id="d9abf-140">Se os mesmos critérios se aplicarem a várias subsidiárias no mesmo banco de dados, você poderá transferir dados dessas subsidiárias para arquivos de exportação separados em uma única operação:</span><span class="sxs-lookup"><span data-stu-id="d9abf-140">If the same criteria apply to several subsidiaries that are in the same database, you can transfer data from those subsidiaries to separate export files in a single operation:</span></span>

        1. <span data-ttu-id="d9abf-141">Crie uma linha para cada entidade legal subsidiária em que contas devam ser exportadas para arquivos.</span><span class="sxs-lookup"><span data-stu-id="d9abf-141">Create a line for each subsidiary legal entity for which accounts should be exported to files.</span></span> <span data-ttu-id="d9abf-142">Posteriormente, esses arquivos serão importados para a entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="d9abf-142">These files will be imported into the consolidated legal entity later.</span></span>
        2. <span data-ttu-id="d9abf-143">Para cada subsidiária, insira o nome da subsidiária e o nome do arquivo de exportação que será criado durante o trabalho de exportação.</span><span class="sxs-lookup"><span data-stu-id="d9abf-143">For each subsidiary, enter the subsidiary name and the name of the export file that will be created during the export job.</span></span>

    3. <span data-ttu-id="d9abf-144">No campo **Tipo de contas das diferenças de conversão**, selecione **Lucros e perdas** ou **Balanço**.</span><span class="sxs-lookup"><span data-stu-id="d9abf-144">In **Account type of conversion differences** field, Select **Profit and loss** or **Balance sheet**.</span></span>
    4. <span data-ttu-id="d9abf-145">Insira um nome de arquivo para o arquivo de exportação que será criado.</span><span class="sxs-lookup"><span data-stu-id="d9abf-145">Enter a file name for the export file that will be created.</span></span>

5. <span data-ttu-id="d9abf-146">Selecione **OK** para executar a exportação.</span><span class="sxs-lookup"><span data-stu-id="d9abf-146">Select **OK** to run the export.</span></span>

<span data-ttu-id="d9abf-147">Quando a exportação for concluída, você receberá uma mensagem mostrando o número de registros salvos em cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="d9abf-147">When the export is completed, you receive a message that shows the number of records that were saved in each file.</span></span> <span data-ttu-id="d9abf-148">Você poderá importar os arquivos para a entidade legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="d9abf-148">You can then import the files into the consolidated legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]