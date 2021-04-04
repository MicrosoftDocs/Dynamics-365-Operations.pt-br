---
title: Prepare metadados específicos do aplicativo para RCS e ER
description: Este tópico explica como preparar metadados específicos do aplicativo para o RCS (Regulatory Configuration Service) e ER (relatório eletrônico).
author: NickSelin
manager: AnnBe
ms.date: 04/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 37da06f4ba86594c6368dcd1049456c58bf87e3a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565456"
---
# <a name="prepare-application-specific-metadata-for-rcs-and-er"></a><span data-ttu-id="e1414-103">Prepare metadados específicos do aplicativo para RCS e ER</span><span class="sxs-lookup"><span data-stu-id="e1414-103">Prepare application-specific metadata for RCS and ER</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e1414-104">Este tópico mostra exemplos das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="e1414-104">This topic walks you through examples of the following tasks:</span></span>

- [<span data-ttu-id="e1414-105">Preparar metadados do aplicativo que podem ser usados no RCS</span><span class="sxs-lookup"><span data-stu-id="e1414-105">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)
- [<span data-ttu-id="e1414-106">Acessar metadados do aplicativo usando uma configuração do ER</span><span class="sxs-lookup"><span data-stu-id="e1414-106">Access application metadata by using an ER configuration</span></span>](#access-application-metadata-by-using-an-er-configuration)
- [<span data-ttu-id="e1414-107">Acessar metadados do aplicativo usando aplicativos conectados</span><span class="sxs-lookup"><span data-stu-id="e1414-107">Access application metadata by using connected applications</span></span>](#access-application-metadata-by-using-connected-applications)

## <a name="prepare-application-metadata-that-can-be-used-in-rcs"></a><span data-ttu-id="e1414-108">Preparar metadados do aplicativo que podem ser usados no RCS</span><span class="sxs-lookup"><span data-stu-id="e1414-108">Prepare application metadata that can be used in RCS</span></span>

<span data-ttu-id="e1414-109">O procedimento a seguir mostra como um usuário com a função de **Administrador do Sistema** ou **Desenvolvedor de Relatório Eletrônico** pode criar uma configuração de relatório eletrônico (ER) que contém metadados do aplicativo e que é usada para criar configurações de mapeamentos do modelo ER no Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="e1414-109">The following procedure shows how a user who has the **System Administrator** or **Electronic Reporting Developer** role can create an Electronic reporting (ER) configuration that contains metadata for the application, and that is used to design ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="e1414-110">A configuração de mapeamento do modelo ER de exemplo que é criada neste exemplo será usada para acessar transações de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="e1414-110">The sample ER model mapping configuration that is created in this example will be used to access foreign trade transactions.</span></span>

<span data-ttu-id="e1414-111">Neste exemplo, você deseja utilizar o RCS para criar uma solução de ER para o aplicativo que será usado para gerar documentos eletrônicos com informações do domínio comercial de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="e1414-111">For this example, you want to use RCS to design an ER solution for the application that will be used to generate electronic documents that contain information from the foreign trade business domain.</span></span> <span data-ttu-id="e1414-112">Para especificar o mapeamento entre o modelo de dados de ER e as fontes de dados necessários, você precisa ter acesso a metadados do aplicativo no RCS.</span><span class="sxs-lookup"><span data-stu-id="e1414-112">To specify the mapping between the ER data model and the sources of required data, you must have access to application metadata in RCS.</span></span> <span data-ttu-id="e1414-113">Portanto, como parte do processo de criação da solução de ER, você precisa definir uma nova configuração de metadados de ER contendo todos os metadados atualmente necessários para gerar relatórios de ER para o domínio comercial selecionado.</span><span class="sxs-lookup"><span data-stu-id="e1414-113">Therefore, as part of the process of designing the ER solution, you must configure a new ER metadata configuration that contains all the metadata that is currently required in order to generate ER reports for the selected business domain.</span></span>

> [!NOTE]
> <span data-ttu-id="e1414-114">Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="e1414-114">In this example, you will create a configuration for the sample company, Litware, Inc. These steps can be performed in any company.</span></span>

1. <span data-ttu-id="e1414-115">Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="e1414-115">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="e1414-116">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="e1414-116">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="e1414-117">Se você não visualizar este provedor de configuração, conclua o procedimento [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e1414-117">If you don't see this configuration provider, complete the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="e1414-118">Selecione **Configurações de metadados**.</span><span class="sxs-lookup"><span data-stu-id="e1414-118">Select **Metadata configurations**.</span></span>
4. <span data-ttu-id="e1414-119">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="e1414-119">Select **Create configuration**.</span></span>
5. <span data-ttu-id="e1414-120">Na caixa de diálogo suspensa, no campo **Nome** , digite um nome.</span><span class="sxs-lookup"><span data-stu-id="e1414-120">In the drop-down dialog box, in the **Name** field, enter a name.</span></span> <span data-ttu-id="e1414-121">Para este exemplo, insira **Metadados de comércio exterior**.</span><span class="sxs-lookup"><span data-stu-id="e1414-121">For this example, enter **Foreign trade metadata**.</span></span>
6. <span data-ttu-id="e1414-122">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="e1414-122">Select **Create configuration**.</span></span>
7. <span data-ttu-id="e1414-123">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e1414-123">Select **Designer**.</span></span>
8. <span data-ttu-id="e1414-124">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-124">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1414-125">Você pode selecionar todos os metadados para o aplicativo inteiro ou para modelos/módulos selecionados.</span><span class="sxs-lookup"><span data-stu-id="e1414-125">You can select all metadata either for the whole application, or for selected models or modules.</span></span> <span data-ttu-id="e1414-126">Nos dois casos, os seguintes metadados serão adicionados automaticamente: tabelas de registros, enumerações e EDTs (tipos de dados estendidos).</span><span class="sxs-lookup"><span data-stu-id="e1414-126">In both cases, be aware that the following metadata will be automatically added: tables of records, enumerations, and extended data types (EDTs).</span></span> <span data-ttu-id="e1414-127">Quando tipos adicionais de metadados são necessários, eles devem ser adicionados manualmente.</span><span class="sxs-lookup"><span data-stu-id="e1414-127">When additional types of metadata are required, they must be manually added.</span></span>

    <span data-ttu-id="e1414-128">Você precisa adicionar alguns metadados que estão relacionados a transações de comércio exterior e selecionar manualmente itens de metadados.</span><span class="sxs-lookup"><span data-stu-id="e1414-128">You must add some metadata that is related to foreign trade transactions and manually select metadata items.</span></span>

9. <span data-ttu-id="e1414-129">Selecione **Adicionar fonte de dados \> Registros da tabela**.</span><span class="sxs-lookup"><span data-stu-id="e1414-129">Select **Add data source \> Table records**.</span></span>
10. <span data-ttu-id="e1414-130">Filtre um valor de **Intrastat** no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="e1414-130">Filter on a value of **Intrastat** in the **Name** field.</span></span>
11. <span data-ttu-id="e1414-131">Selecione o registro de tabela **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="e1414-131">Select the **Intrastat** table record.</span></span>
12. <span data-ttu-id="e1414-132">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1414-132">Select **OK**.</span></span>

    <span data-ttu-id="e1414-133">Você precisa adicionar informações de metadados sobre a tabela de registros Intrastat.</span><span class="sxs-lookup"><span data-stu-id="e1414-133">You must add metadata information about the Intrastat table of records.</span></span>

13. <span data-ttu-id="e1414-134">Na árvore, selecione **Registros de tabela Intrastat \> \>Relações \> IntrastatCommodity (Registros de tabela EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="e1414-134">In the tree, select **Table records Intrastat \> \>Relations \> IntrastatCommodity (Table records EcoResCategory)**.</span></span>
14. <span data-ttu-id="e1414-135">Selecione **Adicionar metadados**.</span><span class="sxs-lookup"><span data-stu-id="e1414-135">Select **Add metadata**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1414-136">Os metadados sobre relações necessárias para a tabela selecionada de registros devem ser adicionados manualmente.</span><span class="sxs-lookup"><span data-stu-id="e1414-136">Metadata about required relations for the selected table of records must be added manually.</span></span>

15. <span data-ttu-id="e1414-137">Selecione **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="e1414-137">Select **Add data source**.</span></span>
16. <span data-ttu-id="e1414-138">Selecione **Enumeração**.</span><span class="sxs-lookup"><span data-stu-id="e1414-138">Select **Enumeration**.</span></span>
17. <span data-ttu-id="e1414-139">Filtre um valor de **IntrastatDirection** no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="e1414-139">Filter on a value of **IntrastatDirection** in the **Name** field.</span></span>
18. <span data-ttu-id="e1414-140">Selecione o registro de enumeração **IntrastatDirection**.</span><span class="sxs-lookup"><span data-stu-id="e1414-140">Select the **IntrastatDirection** enumeration record.</span></span>
19. <span data-ttu-id="e1414-141">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1414-141">Select **OK**.</span></span>
20. <span data-ttu-id="e1414-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-142">Select **Save**.</span></span>
21. <span data-ttu-id="e1414-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e1414-143">Close the page.</span></span>
22. <span data-ttu-id="e1414-144">Preencha a versão de rascunho da configuração de metadados:</span><span class="sxs-lookup"><span data-stu-id="e1414-144">Complete the draft version of the metadata configuration:</span></span>

    1. <span data-ttu-id="e1414-145">Selecione **Alterar status \> Concluir**.</span><span class="sxs-lookup"><span data-stu-id="e1414-145">Select **Change status \> Complete**.</span></span>
    2. <span data-ttu-id="e1414-146">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1414-146">Select **OK**.</span></span>
    3. <span data-ttu-id="e1414-147">Selecione a versão concluída 1.</span><span class="sxs-lookup"><span data-stu-id="e1414-147">Select the completed version 1.</span></span>

23. <span data-ttu-id="e1414-148">Exporte a versão concluída da configuração de metadados do aplicativo como um arquivo XML:</span><span class="sxs-lookup"><span data-stu-id="e1414-148">Export the completed version of the metadata configuration from the application as an XML file:</span></span>

    1. <span data-ttu-id="e1414-149">Selecione **Troca \> Exportar como arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="e1414-149">Select **Exchange \> Export as XML file**.</span></span>
    2. <span data-ttu-id="e1414-150">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1414-150">Select **OK**.</span></span>

<span data-ttu-id="e1414-151">A configuração de metadados de ER que você criou é salva como o arquivo **Metadados de comércio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="e1414-151">The ER metadata configuration that you created is saved as the **Foreign trade metadata.xml** file.</span></span> <span data-ttu-id="e1414-152">Agora você pode importá-lo para o RCS; assim, ele poderá ser usado como a fonte de metadados para o domínio comercial de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="e1414-152">You can now import it into RCS, so that it can be used as the source of metadata for the foreign trade business domain.</span></span> <span data-ttu-id="e1414-153">Com base nessas informações, você pode especificar o mapeamento entre metadados de aplicativos e o modelo de dados do ER.</span><span class="sxs-lookup"><span data-stu-id="e1414-153">Based on this information, you can specify the mapping between application metadata and the ER data model.</span></span>

## <a name="access-application-metadata-by-using-an-er-configuration"></a><span data-ttu-id="e1414-154">Acesse metadados do aplicativo usando uma configuração do ER</span><span class="sxs-lookup"><span data-stu-id="e1414-154">Access application metadata by using an ER configuration</span></span>

<span data-ttu-id="e1414-155">O procedimento a seguir mostra como um usuário do RCS com a função de **Administrador do Sistema** ou **Desenvolvedor de Relatório Eletrônico** pode criar um novo mapeamento de modelos de ER usando metadados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e1414-155">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata from the application.</span></span> <span data-ttu-id="e1414-156">Os metadados do aplicativo serão acessados por meio de uma configuração de metadados de ER contendo um conjunto de exemplo de metadados para acessar transações de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="e1414-156">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span>

<span data-ttu-id="e1414-157">Antes de concluir este procedimento, primeiro conclua os seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e1414-157">Before you can complete this procedure, you must first complete the following procedures:</span></span>

- [<span data-ttu-id="e1414-158">Criar provedores de configuração e marcá-los como ativos</span><span class="sxs-lookup"><span data-stu-id="e1414-158">Create configuration providers and mark them as active</span></span>](tasks/er-configuration-provider-mark-it-active-2016-11.md)
- [<span data-ttu-id="e1414-159">Preparar metadados do aplicativo que podem ser usados no RCS</span><span class="sxs-lookup"><span data-stu-id="e1414-159">Prepare application metadata that can be used in RCS</span></span>](#prepare-application-metadata-that-can-be-used-in-rcs)

1. <span data-ttu-id="e1414-160">Vá para **Todos os espaços de trabalho \> Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="e1414-160">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="e1414-161">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="e1414-161">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="e1414-162">Se você não visualizar este provedor de configuração, conclua o procedimento [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="e1414-162">If you don't see this configuration provider, complete the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> 
3. <span data-ttu-id="e1414-163">Importe a configuração de metadados de ER que contém metadados do aplicativo e que estão configurados para gerar documentos eletrônicos para o domínio comercial de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="e1414-163">Import the ER metadata configuration that contains metadata for the application, and that is configured to generate electronic documents for the foreign trade business domain.</span></span> <span data-ttu-id="e1414-164">Você criou esta configuração de metadados de ER e exportou-a como um arquivo XML no procedimento [Preparar metadados do aplicativo que podem ser usados no RCS](#prepare-application-metadata-that-can-be-used-in-rcs) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e1414-164">You created this ER metadata configuration and exported it as an XML file in the [Prepare application metadata that can be used in RCS](#prepare-application-metadata-that-can-be-used-in-rcs) procedure earlier in this topic.</span></span>

    1. <span data-ttu-id="e1414-165">Selecione **Configurações de metadados**.</span><span class="sxs-lookup"><span data-stu-id="e1414-165">Select **Metadata configurations**.</span></span>
    2. <span data-ttu-id="e1414-166">Selecione **Taxa de câmbio**.</span><span class="sxs-lookup"><span data-stu-id="e1414-166">Select **Exchange**.</span></span>
    3. <span data-ttu-id="e1414-167">Selecione **Carregar do arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="e1414-167">Select **Load from XML file**.</span></span>
    4. <span data-ttu-id="e1414-168">Navegue para selecionar o arquivo **Metadados de comércio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="e1414-168">Browse to select the **Foreign trade metadata.xml** file.</span></span>
    5. <span data-ttu-id="e1414-169">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1414-169">Select **OK**.</span></span>
    6. <span data-ttu-id="e1414-170">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e1414-170">Close the page.</span></span>

4. <span data-ttu-id="e1414-171">Crie uma configuração de modelo de dados:</span><span class="sxs-lookup"><span data-stu-id="e1414-171">Create a data model configuration:</span></span>

    1. <span data-ttu-id="e1414-172">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="e1414-172">Select **Reporting configurations**.</span></span>
    2. <span data-ttu-id="e1414-173">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="e1414-173">Select **Create configuration**.</span></span>
    3. <span data-ttu-id="e1414-174">Na caixa de diálogo suspensa, no campo **Nome** , digite **Modelo de comércio exterior**.</span><span class="sxs-lookup"><span data-stu-id="e1414-174">In the drop-down dialog box, in the **Name** field, enter **Foreign trade model**.</span></span>
    4. <span data-ttu-id="e1414-175">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="e1414-175">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="e1414-176">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e1414-176">Select **Designer**.</span></span>
    6. <span data-ttu-id="e1414-177">Selecione **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e1414-177">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="e1414-178">No campo **Nome**, digite **Raiz**.</span><span class="sxs-lookup"><span data-stu-id="e1414-178">In the **Name** field, type **Root**.</span></span>
        2. <span data-ttu-id="e1414-179">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-179">Select **Add**.</span></span>
    
    7. <span data-ttu-id="e1414-180">Selecione **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e1414-180">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="e1414-181">No campo **Nome**, digite **Transação**.</span><span class="sxs-lookup"><span data-stu-id="e1414-181">In the **Name** field, type **Transaction**.</span></span>
        2. <span data-ttu-id="e1414-182">No campo **Tipo de item**, selecione **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="e1414-182">In the **Item type** field, select **Record list**.</span></span>
        3. <span data-ttu-id="e1414-183">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-183">Select **Add**.</span></span>
 
    8. <span data-ttu-id="e1414-184">Selecione **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e1414-184">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="e1414-185">No campo **Nome**, digite **Código de mercadoria**.</span><span class="sxs-lookup"><span data-stu-id="e1414-185">In the **Name** field, type **Commodity code**.</span></span>
        2. <span data-ttu-id="e1414-186">No campo **Tipo de item**, selecione **String**.</span><span class="sxs-lookup"><span data-stu-id="e1414-186">In the **Item type** field, select **String**.</span></span>
        3. <span data-ttu-id="e1414-187">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-187">Select **Add**.</span></span>

    9. <span data-ttu-id="e1414-188">Selecione **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e1414-188">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="e1414-189">No campo Nome, digite **Valor faturado**.</span><span class="sxs-lookup"><span data-stu-id="e1414-189">In the Name field, type **Invoiced amount**.</span></span>
        2. <span data-ttu-id="e1414-190">No campo **Tipo de item**, selecione **Real**.</span><span class="sxs-lookup"><span data-stu-id="e1414-190">In the **Item type** field, select **Real**.</span></span>
        3. <span data-ttu-id="e1414-191">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-191">Select **Add**.</span></span>

    10. <span data-ttu-id="e1414-192">Selecione **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e1414-192">Select **New** to open the drop dialog.</span></span>

        1. <span data-ttu-id="e1414-193">No campo **Nome**, digite **Data**.</span><span class="sxs-lookup"><span data-stu-id="e1414-193">In the **Name** field, type **Date**.</span></span>
        2. <span data-ttu-id="e1414-194">No campo **Tipo de item**, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="e1414-194">In the **Item type** field, select **Date**.</span></span>
        3. <span data-ttu-id="e1414-195">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-195">Select **Add**.</span></span>
 
    11. <span data-ttu-id="e1414-196">Selecione **Adicionar \> Referência raiz**.</span><span class="sxs-lookup"><span data-stu-id="e1414-196">Select **Add \> Root reference**.</span></span>
    12. <span data-ttu-id="e1414-197">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1414-197">Select **OK**.</span></span>
    13. <span data-ttu-id="e1414-198">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-198">Select **Save**.</span></span>
    14. <span data-ttu-id="e1414-199">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e1414-199">Close the page.</span></span>
    15. <span data-ttu-id="e1414-200">Selecione **Alterar status \> Concluir**.</span><span class="sxs-lookup"><span data-stu-id="e1414-200">Select **Change status \> Complete**.</span></span>
    16. <span data-ttu-id="e1414-201">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1414-201">Select **OK**.</span></span>

5. <span data-ttu-id="e1414-202">Crie uma configuração de mapeamento de modelo:</span><span class="sxs-lookup"><span data-stu-id="e1414-202">Create a model mapping configuration:</span></span>

    1. <span data-ttu-id="e1414-203">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="e1414-203">Select **Create configuration**.</span></span>
    2. <span data-ttu-id="e1414-204">Na caixa de diálogo suspensa, no campo **Novo**, insira **Mapeamento de modelo baseado no modelo de comércio exterior de modelo de dados**.</span><span class="sxs-lookup"><span data-stu-id="e1414-204">In the drop-down dialog box, in the **New** field, enter **Model Mapping based on data model Foreign trade model**.</span></span>
    3. <span data-ttu-id="e1414-205">No campo **Nome**, insira **Mapeamento de comércio exterior**.</span><span class="sxs-lookup"><span data-stu-id="e1414-205">In the **Name** field, enter **Foreign trade mapping**.</span></span>
    4. <span data-ttu-id="e1414-206">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="e1414-206">Select **Create configuration**.</span></span>
    5. <span data-ttu-id="e1414-207">Na Guia Rápida **Pré-requisito**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-207">On the **Prerequisites** FastTab, select **Edit**.</span></span>
    6. <span data-ttu-id="e1414-208">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e1414-208">Select **New**.</span></span>
    7. <span data-ttu-id="e1414-209">No campo **Tipo de componente de pré-requisito**, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="e1414-209">In the **Prerequisite component type** field, select **Configuration**.</span></span>
    8. <span data-ttu-id="e1414-210">Selecione a configuração **Metadados de comércio exterior**.</span><span class="sxs-lookup"><span data-stu-id="e1414-210">Select the **Foreign trade metadata** configuration.</span></span>
    9. <span data-ttu-id="e1414-211">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-211">Select **Save**.</span></span> <span data-ttu-id="e1414-212">Note que a referência foi adicionada à versão 1 da configuração de **Metadados de comércio exterior**.</span><span class="sxs-lookup"><span data-stu-id="e1414-212">Notice that the reference is added to version 1 of the **Foreign trade metadata** configuration.</span></span> <span data-ttu-id="e1414-213">Os metadados de aplicativos dessa configuração serão oferecidos durante a criação do mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="e1414-213">Application metadata from this configuration will be offered while the model mapping is designed.</span></span>
    10. <span data-ttu-id="e1414-214">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e1414-214">Close the page.</span></span>
    11. <span data-ttu-id="e1414-215">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e1414-215">Select **Designer**.</span></span>
    12. <span data-ttu-id="e1414-216">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e1414-216">Select **Designer**.</span></span>
    13. <span data-ttu-id="e1414-217">Na árvore, selecione **Dynamics 365 for Operations \> Registros de tabela**.</span><span class="sxs-lookup"><span data-stu-id="e1414-217">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
    14. <span data-ttu-id="e1414-218">Selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="e1414-218">Select **Add root**.</span></span>
    15. <span data-ttu-id="e1414-219">No campo **Nome**, digite **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="e1414-219">In the **Name** field, enter **Intrastat**.</span></span>
    16. <span data-ttu-id="e1414-220">Selecione registros de tabela **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="e1414-220">Select **Intrastat** table records.</span></span>
    17. <span data-ttu-id="e1414-221">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1414-221">Select **OK**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="e1414-222">Apenas duas tabelas são oferecidas porque somente duas tabelas foram adicionadas ao conjunto de metadados em uso no momento.</span><span class="sxs-lookup"><span data-stu-id="e1414-222">Only two tables are offered, because only two tables were added to the set of metadata that is currently used.</span></span>

    18. <span data-ttu-id="e1414-223">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-223">Select **Bind**.</span></span>
    19. <span data-ttu-id="e1414-224">Na árvore, selecione **Intrastat \> AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="e1414-224">In the tree, select **Intrastat \> AmountMST**.</span></span>
    20. <span data-ttu-id="e1414-225">Na árvore, selecione **Transação = Intrastat \> Valor faturado**.</span><span class="sxs-lookup"><span data-stu-id="e1414-225">In the tree, select **Transaction = Intrastat \> Invoiced amount**.</span></span>
    21. <span data-ttu-id="e1414-226">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-226">Select **Bind**.</span></span>
    22. <span data-ttu-id="e1414-227">Na árvore, selecione **Intrastat \> TransDate**.</span><span class="sxs-lookup"><span data-stu-id="e1414-227">In the tree, select **Intrastat \> TransDate**.</span></span>
    23. <span data-ttu-id="e1414-228">Na árvore, selecione **Transação = Intrastat \> Date**.</span><span class="sxs-lookup"><span data-stu-id="e1414-228">In the tree, select **Transaction = Intrastat \> Date**.</span></span>
    24. <span data-ttu-id="e1414-229">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-229">Select **Bind**.</span></span>
    25. <span data-ttu-id="e1414-230">Na árvore, selecione **Intrastat \> \>Relações \> IntrastatCommodity \> Código**.</span><span class="sxs-lookup"><span data-stu-id="e1414-230">In the tree, select **Intrastat \> \>Relations \> IntrastatCommodity \> Code**.</span></span>
    26. <span data-ttu-id="e1414-231">Na árvore, selecione **Transação = Intrastat \> Código de mercadoria**.</span><span class="sxs-lookup"><span data-stu-id="e1414-231">In the tree, select **Transaction = Intrastat \> Commodity code**.</span></span>
    27. <span data-ttu-id="e1414-232">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-232">Select **Bind**.</span></span>
    28. <span data-ttu-id="e1414-233">Selecione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-233">Select **Validate**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="e1414-234">Após a conclusão da validação, você associa com êxito elementos do modelo de dados a itens das fontes de dados que são descritos usando detalhes dos metadados de aplicativo da configuração de metadados de ER referenciada.</span><span class="sxs-lookup"><span data-stu-id="e1414-234">After validation is completed, you've successfully bound elements of the data model to items of the data sources that are described by using details of the application metadata from the referenced ER metadata configuration.</span></span>

    29. <span data-ttu-id="e1414-235">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-235">Select **Save**.</span></span>

<span data-ttu-id="e1414-236">Conforme necessário, você pode estender o conjunto existente de metadados no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e1414-236">As you require, you can extend the existing set of metadata in the application.</span></span> <span data-ttu-id="e1414-237">Depois, pode exportar a nova versão concluída da configuração de metadados de ER, importá-la para o RCS e atualizar os pré-requisitos de configuração de mapeamento de modelos configurado para referir-se a uma nova versão da configuração de metadados importada.</span><span class="sxs-lookup"><span data-stu-id="e1414-237">You can then export the new completed version of the ER metadata configuration, import it into RCS, and update the prerequisites of the configured model mapping configuration to refer to a new version of the imported metadata configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="e1414-238">Este método de obter informações sobre os metadados do aplicativo é o único método disponível para aplicativos implantados localmente (ou seja, quando dados comerciais locais \[LBD\] ou o modelo de implantação local são usados para o aplicativo).</span><span class="sxs-lookup"><span data-stu-id="e1414-238">This method for getting information about application metadata is the only available method for applications that are locally deployed (that is, when a local business data \[LBD\], or on-premises, deployment model is used for the application).</span></span>

## <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="e1414-239">Acessar metadados do aplicativo usando aplicativos conectados</span><span class="sxs-lookup"><span data-stu-id="e1414-239">Access application metadata by using connected applications</span></span>

<span data-ttu-id="e1414-240">O procedimento a seguir mostra como um usuário do RCS com a função de **Administrador do Sistema** ou **Desenvolvedor de Relatório Eletrônico** pode criar um novo mapeamento de modelos de ER usando metadados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e1414-240">The following procedure shows how an RCS user who has the **System Administrator** or **Electronic Reporting Developer** role can design a new ER model mapping by using metadata of the application.</span></span> <span data-ttu-id="e1414-241">Os metadados do aplicativo serão acessados online usando o aplicativo conectado do RCS.</span><span class="sxs-lookup"><span data-stu-id="e1414-241">Application metadata will be accessed online by using RCS connected application.</span></span> <span data-ttu-id="e1414-242">O mapeamento de modelo ER de exemplo será configurado para acessar transações de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="e1414-242">A sample ER model mapping will be configured to access foreign trade transactions.</span></span>

<span data-ttu-id="e1414-243">Para concluir este procedimento, primeiro você deve concluir o procedimento [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md) no RCS.</span><span class="sxs-lookup"><span data-stu-id="e1414-243">To complete this procedure, you must first complete the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure in RCS.</span></span> <span data-ttu-id="e1414-244">Se você ainda não concluiu o procedimento [Acessar metadados do aplicativo usando a configuração ER](#access-application-metadata-by-using-an-er-configuration) antes neste tópico, vá para a página [Guias de Tarefas de Relatório Eletrônico do Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) para baixar os seguintes arquivos de configuração de ER com antecedência e salvá-los localmente: **Metadados de comércio exterior.xml**, **Modelo de comércio exterior.xml** e **Mapeamento de comércio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="e1414-244">If you haven't yet completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, go to [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page to download the following ER configuration files in advance and save them locally: **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml**.</span></span>


### <a name="get-required-er-configurations"></a><span data-ttu-id="e1414-245">Obtenha configurações de ER necessárias</span><span class="sxs-lookup"><span data-stu-id="e1414-245">Get required ER configurations</span></span>

<span data-ttu-id="e1414-246">Se você já tiver concluído o procedimento [Acessar metadados do aplicativo usando uma configuração ER](#access-application-metadata-by-using-an-er-configuration) antes neste tópico, já terá todas as configurações ER necessárias (as configurações de metadados de comércio exterior, modelo e mapeamento) na instância do RCS atual.</span><span class="sxs-lookup"><span data-stu-id="e1414-246">If you've already completed the [Access application metadata by using an ER configuration](#access-application-metadata-by-using-an-er-configuration) procedure earlier in this topic, you already have all the required ER configurations (the foreign trade metadata, model, and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="e1414-247">Nesse caso, você poderá ignorar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="e1414-247">In that case, you can skip this procedure.</span></span>

1. <span data-ttu-id="e1414-248">Vá para **Todos os espaços de trabalho \> Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="e1414-248">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="e1414-249">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="e1414-249">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="e1414-250">Carregue os arquivos de configuração **Metadados de comércio exterior.xml**, **Modelo de comércio exterior.xml** e **Mapeamento de comércio exterior.xml**, repetindo a seguinte sequência de etapas para cada um deles:</span><span class="sxs-lookup"><span data-stu-id="e1414-250">Load the **Foreign trade metadata.xml**, **Foreign trade model.xml**, and **Foreign trade mapping.xml** configuration files repeating the following chain of steps for each of them:</span></span>

    1. <span data-ttu-id="e1414-251">Selecione **Taxa de câmbio**.</span><span class="sxs-lookup"><span data-stu-id="e1414-251">Select **Exchange**.</span></span>
    2. <span data-ttu-id="e1414-252">Selecione **Carregar do arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="e1414-252">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="e1414-253">Selecione **Procurar** e selecione um arquivo.</span><span class="sxs-lookup"><span data-stu-id="e1414-253">Select **Browse**, and select a file.</span></span>
    4. <span data-ttu-id="e1414-254">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1414-254">Select **OK**.</span></span>

### <a name="register-the-connection-with-the-application"></a><span data-ttu-id="e1414-255">Registrar a conexão com o aplicativo</span><span class="sxs-lookup"><span data-stu-id="e1414-255">Register the connection with the application</span></span>

1. <span data-ttu-id="e1414-256">Vá para **Todos os espaços de trabalho \> Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="e1414-256">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="e1414-257">Selecione **Aplicativos conectados**.</span><span class="sxs-lookup"><span data-stu-id="e1414-257">Select **Connected applications**.</span></span>
3. <span data-ttu-id="e1414-258">Verifique se o aplicativo configurado baseia-se no Microsoft Azure e se está geralmente acessível para usuários no RCS.</span><span class="sxs-lookup"><span data-stu-id="e1414-258">Make sure that the configured application is based on Microsoft Azure, and that it is accessible in general to RCS users.</span></span> <span data-ttu-id="e1414-259">O usuário do RCS atual precisa ter acesso ao aplicativo configurado. Para isso, ele deve estar registrado como um usuário desse aplicativo em uma função que conceda privilégios a ele para acessar metadados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e1414-259">The current RCS user must have access to the configured application being registered as a user of this application in a role that gives them privileges to access the application's metadata.</span></span>
4. <span data-ttu-id="e1414-260">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e1414-260">Select **New**.</span></span>
5. <span data-ttu-id="e1414-261">No campo **Nome**, digite **MyConnectedApp** como o nome do aplicativo associado.</span><span class="sxs-lookup"><span data-stu-id="e1414-261">In the **Name** field, enter **MyConnectedApp** as the name of the connected application.</span></span>
6. <span data-ttu-id="e1414-262">No campo **Aplicativo**, especifique a URL do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e1414-262">In the **Application** field, specify the URL of the application.</span></span>
7. <span data-ttu-id="e1414-263">No campo **Locatário**, especifique a provedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e1414-263">In the **Tenant** field, specify the provider of the application.</span></span>
8. <span data-ttu-id="e1414-264">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-264">Select **Save**.</span></span> 
9. <span data-ttu-id="e1414-265">Quando você verificar a conexão com o aplicativo configurado, na página **Conectar-se ao aplicativo remoto**, selecione o link **Selecione aqui para conectar-se ao aplicativo remoto selecionado**.</span><span class="sxs-lookup"><span data-stu-id="e1414-265">When you check the connection to the configured application, on the **Connect to remote application** page, select the **Select here to connect to selected remote application** link.</span></span> 
10. <span data-ttu-id="e1414-266">Selecione **Verifique a conexão** para validar o acesso ao aplicativo configurado.</span><span class="sxs-lookup"><span data-stu-id="e1414-266">Select **Check connection** to validate access to the configured application.</span></span>
11. <span data-ttu-id="e1414-267">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-267">Select **Close**.</span></span>

<span data-ttu-id="e1414-268">Ao concluir este procedimento e a validação da conexão for bem-sucedida, os detalhes da versão e do locatário serão atualizados para o aplicativo configurado na grade atual.</span><span class="sxs-lookup"><span data-stu-id="e1414-268">After you complete this procedure and validation of the connection succeeds, the version and tenant details for the configured application will be updated in the current grid.</span></span>

### <a name="review-the-existing-model-mapping-configuration"></a><span data-ttu-id="e1414-269">Reveja a configuração de mapeamento do modelo existente</span><span class="sxs-lookup"><span data-stu-id="e1414-269">Review the existing model mapping configuration</span></span>

1. <span data-ttu-id="e1414-270">Vá para **Todos os espaços de trabalho \> Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="e1414-270">Go to **All workspaces \> Electronic reporting**.</span></span>
2. <span data-ttu-id="e1414-271">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="e1414-271">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="e1414-272">Na árvore, selecione **Modelo de comércio exterior \> Mapeamento de comércio exterior**.</span><span class="sxs-lookup"><span data-stu-id="e1414-272">In the tree, select **Foreign trade model \> Foreign trade mapping**.</span></span>
4. <span data-ttu-id="e1414-273">Selecione a Guia Rápida **Pré-requisitos**.</span><span class="sxs-lookup"><span data-stu-id="e1414-273">Select the **Prerequisites** FasTab.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1414-274">Atualmente, o mapeamento se refere à configuração dos metadados.</span><span class="sxs-lookup"><span data-stu-id="e1414-274">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="e1414-275">Os metadados de aplicativos dessa configuração serão oferecidos durante a criação do mapeamento deste modelo.</span><span class="sxs-lookup"><span data-stu-id="e1414-275">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

4. <span data-ttu-id="e1414-276">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e1414-276">Select **Designer**.</span></span>
5. <span data-ttu-id="e1414-277">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e1414-277">Select **Designer**.</span></span>
6. <span data-ttu-id="e1414-278">Na árvore, selecione **Dynamics 365 for Operations \> Registros de tabela**.</span><span class="sxs-lookup"><span data-stu-id="e1414-278">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
7. <span data-ttu-id="e1414-279">Selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="e1414-279">Select **Add root**.</span></span>
8. <span data-ttu-id="e1414-280">No campo **Tabela**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="e1414-280">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1414-281">Atualmente, o mapeamento se refere à configuração dos metadados.</span><span class="sxs-lookup"><span data-stu-id="e1414-281">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="e1414-282">Os metadados de aplicativos dessa configuração serão oferecidos durante a criação do mapeamento deste modelo.</span><span class="sxs-lookup"><span data-stu-id="e1414-282">Application metadata from this configuration will be offered while this model mapping is designed.</span></span>

9. <span data-ttu-id="e1414-283">Selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-283">Select **Cancel**.</span></span>

### <a name="assign-the-connected-application-to-a-model-mapping"></a><span data-ttu-id="e1414-284">Atribua o aplicativo conectado a um mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="e1414-284">Assign the connected application to a model mapping</span></span>

1. <span data-ttu-id="e1414-285">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-285">Select **Edit**.</span></span>
2. <span data-ttu-id="e1414-286">No campo **Aplicativo conectado**, selecione o aplicativo **MyConnectedApp** .</span><span class="sxs-lookup"><span data-stu-id="e1414-286">In the **Connected application field**, select the **MyConnectedApp** application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1414-287">Este mapeamento refere-se aos metadados do aplicativo conectado selecionado.</span><span class="sxs-lookup"><span data-stu-id="e1414-287">This mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="e1414-288">Se um mapeamento referir-se à configuração de metadados e ao aplicativo associado simultaneamente, os metadados do aplicativo conectado serão usados.</span><span class="sxs-lookup"><span data-stu-id="e1414-288">If a mapping refers to the metadata configuration and the connected application at the same time, the metadata of the connected application will be used.</span></span>

3. <span data-ttu-id="e1414-289">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e1414-289">Select **Designer**.</span></span>
4. <span data-ttu-id="e1414-290">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="e1414-290">Select **Designer**.</span></span>
5. <span data-ttu-id="e1414-291">Na árvore, selecione **Dynamics 365 for Operations \> Registros de tabela**.</span><span class="sxs-lookup"><span data-stu-id="e1414-291">In the tree, select **Dynamics 365 for Operations \> Table records**.</span></span>
6. <span data-ttu-id="e1414-292">Selecione **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="e1414-292">Select **Add root**.</span></span>
7. <span data-ttu-id="e1414-293">No campo **Tabela**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="e1414-293">In the **Table** field, enter or select a value.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e1414-294">Nesse ponto, mais de duas tabelas do aplicativo são oferecidas, pois esse mapeamento utiliza todos os metadados do aplicativo conectado que foram atribuídos a ele.</span><span class="sxs-lookup"><span data-stu-id="e1414-294">At this point, more than two application tables are offered, because this mapping uses all the metadata of the connected application that has been assigned to it.</span></span>

8. <span data-ttu-id="e1414-295">Selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-295">Select **Cancel**.</span></span>
9. <span data-ttu-id="e1414-296">Selecione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="e1414-296">Select **Validate**.</span></span>

<span data-ttu-id="e1414-297">Você associou elementos do modelo de dados a itens das fontes de dados que são descritos usando detalhes dos metadados do aplicativo conectado que foram atribuídos a este mapeamento.</span><span class="sxs-lookup"><span data-stu-id="e1414-297">You've now bound elements of the data model to items of the data sources that are described by using details of the metadata of the connected application that has been assigned to this mapping.</span></span>

<span data-ttu-id="e1414-298">Quando você precisar avaliar esse mapeamento de modelo usando os metadados de uma versão diferente do aplicativo, registre outro aplicativo conectado, atribua-o a este mapeamento de modelo e valide-o em relação aos novos metadados.</span><span class="sxs-lookup"><span data-stu-id="e1414-298">When you must evaluate this model mapping by using the metadata of a different version of the application, register another connected application, assign it to this model mapping, and validate it against the new metadata.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e1414-299">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e1414-299">Additional resources</span></span>

<span data-ttu-id="e1414-300">Alternativamente, você pode executar a guia de tarefas **Preparar os metadados de aplicativo que podem ser usados no RCS** no aplicativo, bem como as guias de tarefas **Acessar metadados de aplicativos usando uma configuração de ER** e **Acessar metadados de aplicativos usando aplicativos conectados** no RCS.</span><span class="sxs-lookup"><span data-stu-id="e1414-300">Alternatively, you can play the **Prepare application metadata that can be used in RCS** task guide in the application as as well as the **Access application metadata by using an ER configuration** and **Access application metadata by using connected applications** task guides in RCS.</span></span> <span data-ttu-id="e1414-301">Essas guias de tarefas podem ser baixadas na página [Guias de tarefas de relatórios eletrônicos do Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739).</span><span class="sxs-lookup"><span data-stu-id="e1414-301">These task guides can be downloaded from the [Electronic Reporting Task Guides for Dynamics 365 for Finance and Operations 8.1](https://go.microsoft.com/fwlink/?linkid=2082739) page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]