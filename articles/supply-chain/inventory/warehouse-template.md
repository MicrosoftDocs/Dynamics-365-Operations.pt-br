---
title: "Configurar um depósito usando um modelo de configuração de depósito"
description: "Este tópico explica como configurar um depósito usando um modelo de configuração de depósito."
author: perlynne
manager: AnnBe
ms.date: 11/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DataManagementWorkspace, DMFQuickImportExportEnhanced, DMFDefinitionGroupTemplate, DMFEntityTemplateDefinitionLoadDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0b54e7f6f4b0dfb994d271aaeb547e27bf03e294
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="set-up-a-warehouse-by-using-a-warehouse-configuration-template"></a><span data-ttu-id="57d82-103">Configurar um depósito usando um modelo de configuração de depósito</span><span class="sxs-lookup"><span data-stu-id="57d82-103">Set up a warehouse by using a warehouse configuration template</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57d82-104">Este tópico explica como configurar um depósito usando um modelo de configuração de depósito.</span><span class="sxs-lookup"><span data-stu-id="57d82-104">This topic explains how to set up a warehouse by using a warehouse configuration template.</span></span> <span data-ttu-id="57d82-105">Há vários modelos predefinidos de configuração que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="57d82-105">There are several predefined configuration templates that you can use.</span></span> <span data-ttu-id="57d82-106">Para obter informações sobre como usar esses modelos, consulte [Modelos de dados de configuração](../../dev-itpro/data-entities/configuration-data-templates.md).</span><span class="sxs-lookup"><span data-stu-id="57d82-106">For information about how to use these templates, see [Configuration data templates](../../dev-itpro/data-entities/configuration-data-templates.md).</span></span>

## <a name="scenarios-where-configuration-templates-can-be-helpful"></a><span data-ttu-id="57d82-107">Cenários onde os modelos de configuração podem ser úteis</span><span class="sxs-lookup"><span data-stu-id="57d82-107">Scenarios where configuration templates can be helpful</span></span>

<span data-ttu-id="57d82-108">Os modelos de configuração podem ser úteis em vários cenários.</span><span class="sxs-lookup"><span data-stu-id="57d82-108">Configuration templates can be helpful in many scenarios.</span></span> <span data-ttu-id="57d82-109">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="57d82-109">Here are some examples:</span></span>

- <span data-ttu-id="57d82-110">Você concluiu e testou uma definição de configuração em um ambiente de teste e agora quer copiar a configuração para um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="57d82-110">You've completed and tested a configuration setup in a test environment, and you now want to copy the setup to a production environment.</span></span>
- <span data-ttu-id="57d82-111">Você quer implementar a configuração do depósito para várias entidades legais ou criar um novo depósito na mesma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="57d82-111">You want to roll the warehouse setup out to several legal entities or create a new warehouse in the same legal entity.</span></span>
- <span data-ttu-id="57d82-112">Você quer preparar rapidamente uma demonstração de funcionalidade de depósito.</span><span class="sxs-lookup"><span data-stu-id="57d82-112">You want to quickly prepare for a demo of the warehouse functionality.</span></span>
- <span data-ttu-id="57d82-113">Você quer que os itens e depósitos existentes usem a funcionalidade no Gerenciamento de depósito, em vez da funcionalidade no gerenciamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="57d82-113">You want existing items and warehouses to use the functionality in Warehouse management instead of the functionality in Inventory management.</span></span>

<span data-ttu-id="57d82-114">Esse tópico concentra-se no primeiro desses cenários.</span><span class="sxs-lookup"><span data-stu-id="57d82-114">This topic focuses on the first of these scenarios.</span></span> <span data-ttu-id="57d82-115">Ele mostra como é possível usar um modelo de configuração para copiar uma definição de configuração de um ambiente de teste para um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="57d82-115">It shows how you can use a configuration template to copy a configuration setup from a test environment to a production environment.</span></span>

## <a name="copy-a-configuration-setup-from-a-test-environment-to-a-production-environment"></a><span data-ttu-id="57d82-116">Copiar uma definição de configuração de um ambiente de teste para um ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="57d82-116">Copy a configuration setup from a test environment to a production environment</span></span>

<span data-ttu-id="57d82-117">Para esse cenário, a definição de configuração para um depósito e alguns processos de transação já existem em um ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="57d82-117">For this scenario, the configuration setup for a warehouse and some transaction processes already exist in a test environment.</span></span> <span data-ttu-id="57d82-118">Agora você deseja copiar a definição de configuração do depósito do ambiente de teste para um ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="57d82-118">You now want to copy the configuration setup for the warehouse from the test environment to a production environment.</span></span>

> [!NOTE]
> <span data-ttu-id="57d82-119">É importante que você inclua outros dados relacionados à configuração ao copiar uma definição de configuração.</span><span class="sxs-lookup"><span data-stu-id="57d82-119">It's important that you include other related setup data when you copy a configuration setup.</span></span> <span data-ttu-id="57d82-120">Por exemplo, você quer configurar produtos copiando a definição de um ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="57d82-120">For example, you want to set up products by copying the setup from a test environment.</span></span> <span data-ttu-id="57d82-121">Porém, você não pode configurar uma localização fixa de separação para um produto antes de o produto ser criado.</span><span class="sxs-lookup"><span data-stu-id="57d82-121">However, you can't set up a fixed picking location for a product before that product is created.</span></span> <span data-ttu-id="57d82-122">Embora os modelos de configuração individuais não ofereçam suporte a esse tipo de dependência, há modelos de dados padrão que oferecem.</span><span class="sxs-lookup"><span data-stu-id="57d82-122">Although individual configuration templates don't support this type of dependency, there are default data templates that support it.</span></span> <span data-ttu-id="57d82-123">Você pode incluir facilmente esses modelos de dados padrão em um processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="57d82-123">You can easily include these default data templates in a configuration process.</span></span>

### <a name="export-a-default-warehouse-template"></a><span data-ttu-id="57d82-124">Exportar um modelo padrão do depósito</span><span class="sxs-lookup"><span data-stu-id="57d82-124">Export a default warehouse template</span></span> 

1. <span data-ttu-id="57d82-125">Abra o espaço de trabalho **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="57d82-125">Open the **Data management** workspace.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57d82-126">Se estiver usando esse espaço de trabalho pela primeira vez, você deve carregar todas as entidades de dados antes de você prosseguir.</span><span class="sxs-lookup"><span data-stu-id="57d82-126">If you're using this workspace for the first time, you must load all the data entities before you continue.</span></span>

2. <span data-ttu-id="57d82-127">Selecione o bloco **Modelos** e, em seguida, selecione **Carregar modelos padrão** para carregar os modelos padrão.</span><span class="sxs-lookup"><span data-stu-id="57d82-127">Select the **Templates** tile, and then select **Load default templates** to load the default templates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57d82-128">**Carregar modelos padrão** está disponível apenas na exibição **Avançada**.</span><span class="sxs-lookup"><span data-stu-id="57d82-128">**Load default templates** is available only in the **Enhanced** view.</span></span> <span data-ttu-id="57d82-129">Selecione **Parâmetros de estrutura**e, depois, no campo **Padrões de exibição**, selecione **Exibição avançada**.</span><span class="sxs-lookup"><span data-stu-id="57d82-129">Select **Framework parameters**, and then, in the **View defaults** field, select **Enhanced view**.</span></span>

3. <span data-ttu-id="57d82-130">Depois que os modelos padrão forem carregados, você pode alterá-los, de forma que eles atendam seus requisitos de negócios.</span><span class="sxs-lookup"><span data-stu-id="57d82-130">After the default templates are loaded, you can change them so that they meet your business requirements.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57d82-131">Para carregar modelos padrão e importar modelos, você deve ter o acesso de administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="57d82-131">To load default templates and import templates, you must have system administrator access.</span></span> <span data-ttu-id="57d82-132">Esse requisito ajuda a garantir de que todas as entidades serão carregadas corretamente no modelo.</span><span class="sxs-lookup"><span data-stu-id="57d82-132">This requirement helps guarantee that all entities are correctly loaded into the template.</span></span>

4. <span data-ttu-id="57d82-133">Certifique-se de que está na entidade legal da qual você deseja exportar os dados específicos da empresa.</span><span class="sxs-lookup"><span data-stu-id="57d82-133">Make sure that you're in the legal entity that you want to export the company-specific data from.</span></span>
5. <span data-ttu-id="57d82-134">No espaço de trabalho, selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="57d82-134">In the workspace, select **Export**.</span></span>
6. <span data-ttu-id="57d82-135">Criar um novo projeto de exportação.</span><span class="sxs-lookup"><span data-stu-id="57d82-135">Create a new export project.</span></span>
7. <span data-ttu-id="57d82-136">Selecione **+ Adicionar modelo** e localize o modelo de depósito padrão **400 - WMS**.</span><span class="sxs-lookup"><span data-stu-id="57d82-136">Select **+ Add template**, and find the **400 - WMS** default warehouse template.</span></span> <span data-ttu-id="57d82-137">Esse modelo adiciona as entidades de dados à configuração de depósito.</span><span class="sxs-lookup"><span data-stu-id="57d82-137">This template adds data entities for warehouse configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57d82-138">Se os dados que você está exportando tiverem que ser filtrados (por exemplo, você quiser exportar somente dados relacionados a um depósito específico), você deve avaliar cada entidade de dados e adicionar a filtragem por meio de uma consulta.</span><span class="sxs-lookup"><span data-stu-id="57d82-138">If the data that you're exporting must be filtered (for example, you want to export only the data that is related to a specific warehouse), you must evaluate each data entity and add filtering via a query.</span></span> <span data-ttu-id="57d82-139">Se preferir, você pode exportar os dados e excluir os registros que não são necessários nos arquivos de destino.</span><span class="sxs-lookup"><span data-stu-id="57d82-139">Alternatively, you can export all data and then delete the records that aren't required in the destination files.</span></span>

8. <span data-ttu-id="57d82-140">Selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="57d82-140">Select **Export**.</span></span> <span data-ttu-id="57d82-141">Os dados relacionados a todas as entidades de dados no projeto serão exportados.</span><span class="sxs-lookup"><span data-stu-id="57d82-141">Data that is related to all the data entities in the project is exported.</span></span>

<span data-ttu-id="57d82-142">Podem baixar um arquivo zip para o pacote de dados.</span><span class="sxs-lookup"><span data-stu-id="57d82-142">You can download a zip file for the data package.</span></span> <span data-ttu-id="57d82-143">Este arquivo contém todos os dados no formato selecionado (por exemplo, formato Excel).</span><span class="sxs-lookup"><span data-stu-id="57d82-143">This file contains all the data in the selected format (for example, Excel format).</span></span> <span data-ttu-id="57d82-144">Como foi mencionado, alguns registros nos arquivos do pacote de dados precisam ser atualizados antes para que possa importá-los no ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="57d82-144">As has been mentioned, some records in the data package files might have to be updated before you can import them into the production environment.</span></span> <span data-ttu-id="57d82-145">Se você atualizar um registro, certifique-se de que não alterou o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="57d82-145">If you update a record, make sure that you don't change the file name.</span></span>

### <a name="import-a-warehouse-configuration-setup"></a><span data-ttu-id="57d82-146">Importar uma definição de configuração do depósito</span><span class="sxs-lookup"><span data-stu-id="57d82-146">Import a warehouse configuration setup</span></span>

1. <span data-ttu-id="57d82-147">No ambiente de destino, verifique se você está na empresa na qual deseja importar os dados de depósito.</span><span class="sxs-lookup"><span data-stu-id="57d82-147">In the destination environment, make sure that you're in the company that you want to import the warehouse data into.</span></span>

    > [!NOTE]
    > <span data-ttu-id="57d82-148">Antes de fazer a importação, é preciso identificar todas as dependências de dados.</span><span class="sxs-lookup"><span data-stu-id="57d82-148">Before you do the import, you should identify any data dependencies.</span></span> <span data-ttu-id="57d82-149">Por exemplo, o modelo **Gerenciamento de depósito** inclui uma entidade de dados que é chamada **Códigos de disposição de depósito**.</span><span class="sxs-lookup"><span data-stu-id="57d82-149">For example, the **Warehouse management** template includes a data entity that is named **Warehouse disposition codes**.</span></span> <span data-ttu-id="57d82-150">Esta entidade contém dados relacionados à página de configuração **Códigos de disposição** (**Gerenciamento de depósito** > **Configuração** > **Dispositivo móvel** > **Códigos de disposição**).</span><span class="sxs-lookup"><span data-stu-id="57d82-150">This entity contains data that is related to the **Disposition codes** setup page (**Warehouse management** > **Setup** > **Mobile device** > **Disposition codes**).</span></span> <span data-ttu-id="57d82-151">Se uma configuração existente já trata o processo de devoluções para ordens de venda, o campo **Código de disposição de devolução** conterá um valor.</span><span class="sxs-lookup"><span data-stu-id="57d82-151">If an existing setup already handles the return process for sales orders, the **Return disposition code** field contains a value.</span></span> <span data-ttu-id="57d82-152">O código de disposição neste campo está relacionado à entidade de dados **Código de disposição**, que faz parte do modelo **Vendas e marketing**.</span><span class="sxs-lookup"><span data-stu-id="57d82-152">The disposition code in this field is related to the **Disposition code** data entity, which is part of the **Sales and marketing** template.</span></span> <span data-ttu-id="57d82-153">Se os dados da entidade de dados **Código de disposição** não forem importados antes de os dados do campo **Códigos de disposição de depósito**, haverá falha na importação.</span><span class="sxs-lookup"><span data-stu-id="57d82-153">If the data from the **Disposition code** data entity isn't imported before the data from the **Warehouse disposition codes** field, the import will fail.</span></span>

2. <span data-ttu-id="57d82-154">No espaço de trabalho **Gerenciamento de dados**, selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="57d82-154">In the **Data management** workspace, select **Import**.</span></span>
3. <span data-ttu-id="57d82-155">Criar um novo projeto de importação.</span><span class="sxs-lookup"><span data-stu-id="57d82-155">Create a new import project.</span></span>
4. <span data-ttu-id="57d82-156">Selecione **+ Adicionar arquivo** e carregue o arquivo zip para o pacote de dados.</span><span class="sxs-lookup"><span data-stu-id="57d82-156">Select **+ Add file**, and upload the zip file for the data package.</span></span>
5. <span data-ttu-id="57d82-157">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="57d82-157">Select **Import**.</span></span> <span data-ttu-id="57d82-158">Na exibição **Avançada**, você pode usar a opção **Filtro** rapidamente obter uma visão geral de problemas que podem ocorrer durante a importação.</span><span class="sxs-lookup"><span data-stu-id="57d82-158">In the **Enhanced** view, you can use the **Filter** option to quickly get an overview of issues that might occur during the import.</span></span>

<span data-ttu-id="57d82-159">O log **Exibir execução** fornece informações detalhadas sobre cada entidade de dados que é importada.</span><span class="sxs-lookup"><span data-stu-id="57d82-159">The **View execution** log provides detailed information about each data entity that is imported.</span></span> <span data-ttu-id="57d82-160">Você pode usar a exibição de preparação de dados para obter dados de destino rapidamente.</span><span class="sxs-lookup"><span data-stu-id="57d82-160">You can use the staging data view to quickly get to the target data.</span></span> <span data-ttu-id="57d82-161">Assim, você pode ver os dados importados nas páginas relacionadas no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="57d82-161">In this way, you can see what the imported data looks like on the related pages in the application.</span></span> <span data-ttu-id="57d82-162">Ao usar os modelos de dados padrão, a sequência de importação de cada entidade de dados em forma predefinida, ajuda a garantir que os dados dependentes são importados primeiro.</span><span class="sxs-lookup"><span data-stu-id="57d82-162">When you use the default data templates, the import sequence for each data entity works in the predefined manner, to help guarantee that all dependent data is imported first.</span></span> <span data-ttu-id="57d82-163">Se as entidades de dados personalizados fizerem parte do projeto, você deve garantir que a sequência correta foi definida.</span><span class="sxs-lookup"><span data-stu-id="57d82-163">If custom data entities are part of the project, you must make sure that the correct sequence is defined.</span></span> <span data-ttu-id="57d82-164">Para obter mais informações, consulte [Modelos de dados de configuração](../../dev-itpro/data-entities/configuration-data-templates.md).</span><span class="sxs-lookup"><span data-stu-id="57d82-164">For more information, see [Configuration data templates](../../dev-itpro/data-entities/configuration-data-templates.md).</span></span>

<span data-ttu-id="57d82-165">Para saber mais sobre como usar o modelo de depósito para copiar a configuração de um depósito de uma empresa para uma nova empresa na mesma a instância, assista a este vídeo de 3 minutos de duração no YouTube.</span><span class="sxs-lookup"><span data-stu-id="57d82-165">To learn more about how to use warehouse template to copy the configuration of a warehouse from one company to a new company within the same instance, see this 3-minute video on YouTube.</span></span>

> [!Video https://www.youtube.com/embed/K2WIfFlqJYs]


## <a name="related-topic"></a><span data-ttu-id="57d82-166">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="57d82-166">Related topic</span></span>

[<span data-ttu-id="57d82-167">Modelos de dados de configuração</span><span class="sxs-lookup"><span data-stu-id="57d82-167">Configuration data templates</span></span>](../../dev-itpro/data-entities/configuration-data-templates.md)

