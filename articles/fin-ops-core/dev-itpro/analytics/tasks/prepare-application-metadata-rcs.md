---
title: Preparar os metadados do aplicativo a serem usados no RCS
description: As etapas deste tópico explicam como um usuário pode criar uma nova configuração de Relatório eletrônico (ER) contendo metadados para criar configurações de mapeamentos do modelo ER no Regulatory Configuration Service (RCS).
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbc1ca45a39f2a5c3309276f9e2f5d2b7d2ba5f7
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684082"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a><span data-ttu-id="002b3-103">Preparar os metadados do aplicativo a serem usados no RCS</span><span class="sxs-lookup"><span data-stu-id="002b3-103">Prepare application metadata to be used in RCS</span></span>
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="002b3-104">As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório eletrônico (ER) contendo metadados do aplicativo para criar configurações de mapeamentos do modelo ER no Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="002b3-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains application metadata for designing ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="002b3-105">Essa configuração será usada para criar uma configuração de mapeamento do modelo ER de exemplo para acessar transações de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="002b3-105">This configuration will be used for designing a sample ER model mapping configuration to access foreign trade transactions.</span></span> <span data-ttu-id="002b3-106">Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="002b3-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company.</span></span> <span data-ttu-id="002b3-107">Para concluir estas etapas, primeiro conclua as etapas do tópico, [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="002b3-107">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="002b3-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="002b3-108">Prerequisites</span></span>
1.    <span data-ttu-id="002b3-109">Vá para **Administração da organização** > **Espaços de trabalho** > **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="002b3-109">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2.    <span data-ttu-id="002b3-110">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="002b3-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="002b3-111">Se você não visualizar este provedor de configuração, conclua as etapas no procedimento [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="002b3-111">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3.    <span data-ttu-id="002b3-112">Clique em **Configurações de metadados**.</span><span class="sxs-lookup"><span data-stu-id="002b3-112">Click **Metadata configurations**.</span></span> 
4.    <span data-ttu-id="002b3-113">Suponha que o RCS seja usado para criar uma solução de ER para um aplicativo do Finance and Operations que gere documentos eletrônicos contendo informações do domínio de negócios de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="002b3-113">Assume that RCS will be used to design an ER solution for a Finance and Operation application that will generate electronic documents that contain information from foreign trade business domain.</span></span> <span data-ttu-id="002b3-114">Para especificar o mapeamento entre o modelo de dados do ER e fontes de dados necessários, no RCS precisamos ter acesso a metadados do aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="002b3-114">To specify the mapping between ER data model and sources of required data, in RCS we need to have access to metadata of the Finance and Operation application.</span></span> <span data-ttu-id="002b3-115">Portanto, como parte da criação da solução de ER, definimos uma nova configuração de metadados de ER contendo todos os metadados atualmente necessários para a geração de relatórios de ER para o domínio comercial selecionado.</span><span class="sxs-lookup"><span data-stu-id="002b3-115">Therefore, as part of designing ER solution we configure a new ER metadata configuration containing all metadata that is currently required for generation ER reports for selected business domain.</span></span> 

## <a name="add-metadata-configuration"></a><span data-ttu-id="002b3-116">Adicione a configuração de metadados</span><span class="sxs-lookup"><span data-stu-id="002b3-116">Add metadata configuration</span></span> 
1.    <span data-ttu-id="002b3-117">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="002b3-117">Click **Create configuration** to open the drop dialog.</span></span> 
2.    <span data-ttu-id="002b3-118">No campo **Nome**, digite 'Metadados de comércio exterior'.</span><span class="sxs-lookup"><span data-stu-id="002b3-118">In the **Name** field, type 'Foreign trade metadata'.</span></span> 
3.    <span data-ttu-id="002b3-119">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="002b3-119">Click **Create configuration**.</span></span> 
4.    <span data-ttu-id="002b3-120">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="002b3-120">Click **Designer**.</span></span> 
5.    <span data-ttu-id="002b3-121">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="002b3-121">Click **Add**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="002b3-122">Você pode selecionar todos os metadados do aplicativo inteiro, modelos selecionados ou módulos selecionados.</span><span class="sxs-lookup"><span data-stu-id="002b3-122">You can select all metadata for the entire application or selected models or selected modules.</span></span> <span data-ttu-id="002b3-123">Lembre-se de que, nesse caso, os seguintes metadados serão adicionados automaticamente: tabelas de registros, enumerações e tipos de dados estendidos.</span><span class="sxs-lookup"><span data-stu-id="002b3-123">Be aware that in this case the following metadata will be automatically added: tables of records, enumerations, and extended data types.</span></span> <span data-ttu-id="002b3-124">Quando tipos adicionais de metadados são necessários, eles devem ser adicionados manualmente.</span><span class="sxs-lookup"><span data-stu-id="002b3-124">When additional types of metadata are needed, they must be added manually.</span></span> 
 
<span data-ttu-id="002b3-125">Temos algumas transações de comércio exterior com metadados relacionados, em que itens de metadados foram selecionados manualmente.</span><span class="sxs-lookup"><span data-stu-id="002b3-125">We have some foreign trade transactions related metadata by selecting metadata items manually.</span></span> 
  
6.    <span data-ttu-id="002b3-126">Clique em **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="002b3-126">Click **Add data source**.</span></span> 
7.    <span data-ttu-id="002b3-127">Clique em **Registros de tabela**.</span><span class="sxs-lookup"><span data-stu-id="002b3-127">Click **Table records**.</span></span> 
8.    <span data-ttu-id="002b3-128">Use o Filtro Rápido para filtrar no campo **Nome** com um valor de 'Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="002b3-128">Use the Quick Filter to filter on the **Name** field with a value of 'Intrastat'.</span></span> 
9.    <span data-ttu-id="002b3-129">Selecione o registro de tabela **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="002b3-129">Select the **Intrastat** table record.</span></span> 
10.    <span data-ttu-id="002b3-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="002b3-130">Click **OK**.</span></span>
  
<span data-ttu-id="002b3-131">Adicionamos informações de metadados sobre a tabela de registros Intrastat.</span><span class="sxs-lookup"><span data-stu-id="002b3-131">We added metadata information about the Intrastat table of records.</span></span> 
  
11.    <span data-ttu-id="002b3-132">Na árvore, expanda **Registros de tabela Intrastat**\>**Relações**.</span><span class="sxs-lookup"><span data-stu-id="002b3-132">In the tree, expand **Table records Intrastat**\>**Relations**.</span></span> 
12.    <span data-ttu-id="002b3-133">Na árvore, selecione **Registros de tabela Intrastat**\>**Relações\IntrastatCommodity (Registros de tabela EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="002b3-133">In the tree, select **Table records Intrastat**\>**Relations\IntrastatCommodity (Table records EcoResCategory)**.</span></span>     
13.    <span data-ttu-id="002b3-134">Clique em **Adicionar metadados**.</span><span class="sxs-lookup"><span data-stu-id="002b3-134">Click **Add metadata**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="002b3-135">Os metadados sobre relações necessárias para a tabela selecionada de registros devem ser adicionados manualmente.</span><span class="sxs-lookup"><span data-stu-id="002b3-135">Metadata about required relations for selected table of records must be added manually.</span></span> 
  
16.    <span data-ttu-id="002b3-136">Clique em **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="002b3-136">Click **Add data source**.</span></span> 
17.    <span data-ttu-id="002b3-137">Clique em **Enumeração**.</span><span class="sxs-lookup"><span data-stu-id="002b3-137">Click **Enumeration**.</span></span> 
18.    <span data-ttu-id="002b3-138">Use o Filtro Rápido para filtrar no campo **Nome** com um valor de 'IntrastatDirection'.</span><span class="sxs-lookup"><span data-stu-id="002b3-138">Use the Quick Filter to filter on the **Name** field with a value of 'IntrastatDirection'.</span></span> 
19.    <span data-ttu-id="002b3-139">Selecione o registro **Enumeração IntrastatDirection**.</span><span class="sxs-lookup"><span data-stu-id="002b3-139">Select the **IntrastatDirection enumeration** record.</span></span> 
20.    <span data-ttu-id="002b3-140">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="002b3-140">Click **OK**.</span></span> 
21.    <span data-ttu-id="002b3-141">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="002b3-141">Click **Save**.</span></span>  
22.    <span data-ttu-id="002b3-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="002b3-142">Close the page.</span></span> 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a><span data-ttu-id="002b3-143">Preencha a versão de rascunho de configuração de metadados</span><span class="sxs-lookup"><span data-stu-id="002b3-143">Complete the draft version of metadata configuration</span></span>
1.    <span data-ttu-id="002b3-144">Clique em **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="002b3-144">Click **Change status**.</span></span> 
2.    <span data-ttu-id="002b3-145">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="002b3-145">Click **Complete**.</span></span> 
3.    <span data-ttu-id="002b3-146">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="002b3-146">Click **OK**.</span></span> 
4.    <span data-ttu-id="002b3-147">Selecione a versão concluída **1**.</span><span class="sxs-lookup"><span data-stu-id="002b3-147">Select the completed version **1**.</span></span> 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a><span data-ttu-id="002b3-148">Exporte a versão concluída da configuração de metadados do aplicativo como o arquivo XML</span><span class="sxs-lookup"><span data-stu-id="002b3-148">Export the completed version of metadata configuration from application as XML file</span></span>
1.    <span data-ttu-id="002b3-149">Clique em **Taxa de câmbio**.</span><span class="sxs-lookup"><span data-stu-id="002b3-149">Click **Exchange**.</span></span> 
2.    <span data-ttu-id="002b3-150">Clique em **Exportar como o arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="002b3-150">Click **Export as XML file**.</span></span> 
3.    <span data-ttu-id="002b3-151">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="002b3-151">Click **OK**.</span></span> 
    
<span data-ttu-id="002b3-152">A configuração de metadados de ER criada foi salva como um arquivo XML que pode ser importado para o RCS e usado como a fonte de informações sobre metadados para o domínio comercial de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="002b3-152">The created ER metadata configuration has been saved as XML file that can be imported to RCS and used as the source of information about metadata for the foreign trade business domain.</span></span> <span data-ttu-id="002b3-153">Com base nessas informações, podemos especificar o mapeamento entre metadados de aplicativos e o modelo de dados do ER.</span><span class="sxs-lookup"><span data-stu-id="002b3-153">Based on this information, we can specify the mapping between application metadata and ER data model.</span></span>
