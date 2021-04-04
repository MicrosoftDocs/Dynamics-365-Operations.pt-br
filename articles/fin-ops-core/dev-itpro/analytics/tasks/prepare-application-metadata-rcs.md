---
title: Preparar os metadados do aplicativo a serem usados no RCS
description: Este tópico descreve como criar uma nova configuração de relatório que contenha metadados do aplicativo.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9609da50482f39bafe65d3a7b655e5047c74bdba
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560108"
---
# <a name="prepare-application-metadata-to-be-used-in-rcs"></a><span data-ttu-id="b61bf-103">Preparar os metadados do aplicativo a serem usados no RCS</span><span class="sxs-lookup"><span data-stu-id="b61bf-103">Prepare application metadata to be used in RCS</span></span>
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b61bf-104">As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma nova configuração de Relatório eletrônico (ER) contendo metadados do aplicativo para criar configurações de mapeamentos do modelo ER no Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="b61bf-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a new Electronic reporting (ER) configuration that contains application metadata for designing ER model mapping configurations in Regulatory configuration service (RCS).</span></span> <span data-ttu-id="b61bf-105">Essa configuração será usada para criar uma configuração de mapeamento do modelo ER de exemplo para acessar transações de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="b61bf-105">This configuration will be used for designing a sample ER model mapping configuration to access foreign trade transactions.</span></span> <span data-ttu-id="b61bf-106">Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Estas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="b61bf-106">In this example, you will create a configuration for sample company, Litware, Inc. These steps can be performed in any company.</span></span> <span data-ttu-id="b61bf-107">Para concluir estas etapas, primeiro conclua as etapas do tópico, [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="b61bf-107">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b61bf-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b61bf-108">Prerequisites</span></span>
1.    <span data-ttu-id="b61bf-109">Vá para **Administração da organização** > **Espaços de trabalho** > **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-109">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2.    <span data-ttu-id="b61bf-110">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="b61bf-111">Se você não visualizar este provedor de configuração, conclua as etapas no procedimento [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="b61bf-111">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3.    <span data-ttu-id="b61bf-112">Clique em **Configurações de metadados**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-112">Click **Metadata configurations**.</span></span> 
4.    <span data-ttu-id="b61bf-113">Suponha que o RCS seja usado para criar uma solução de ER para um aplicativo do Finance and Operations que gere documentos eletrônicos contendo informações do domínio de negócios de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="b61bf-113">Assume that RCS will be used to design an ER solution for a Finance and Operation application that will generate electronic documents that contain information from foreign trade business domain.</span></span> <span data-ttu-id="b61bf-114">Para especificar o mapeamento entre o modelo de dados do ER e fontes de dados necessários, no RCS precisamos ter acesso a metadados do aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b61bf-114">To specify the mapping between ER data model and sources of required data, in RCS we need to have access to metadata of the Finance and Operation application.</span></span> <span data-ttu-id="b61bf-115">Portanto, como parte da criação da solução de ER, definimos uma nova configuração de metadados de ER contendo todos os metadados atualmente necessários para a geração de relatórios de ER para o domínio comercial selecionado.</span><span class="sxs-lookup"><span data-stu-id="b61bf-115">Therefore, as part of designing ER solution we configure a new ER metadata configuration containing all metadata that is currently required for generation ER reports for selected business domain.</span></span> 

## <a name="add-metadata-configuration"></a><span data-ttu-id="b61bf-116">Adicione a configuração de metadados</span><span class="sxs-lookup"><span data-stu-id="b61bf-116">Add metadata configuration</span></span> 
1.    <span data-ttu-id="b61bf-117">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="b61bf-117">Click **Create configuration** to open the drop dialog.</span></span> 
2.    <span data-ttu-id="b61bf-118">No campo **Nome**, digite 'Metadados de comércio exterior'.</span><span class="sxs-lookup"><span data-stu-id="b61bf-118">In the **Name** field, type 'Foreign trade metadata'.</span></span> 
3.    <span data-ttu-id="b61bf-119">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-119">Click **Create configuration**.</span></span> 
4.    <span data-ttu-id="b61bf-120">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-120">Click **Designer**.</span></span> 
5.    <span data-ttu-id="b61bf-121">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-121">Click **Add**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b61bf-122">Você pode selecionar todos os metadados do aplicativo inteiro, modelos selecionados ou módulos selecionados.</span><span class="sxs-lookup"><span data-stu-id="b61bf-122">You can select all metadata for the entire application or selected models or selected modules.</span></span> <span data-ttu-id="b61bf-123">Lembre-se de que, nesse caso, os seguintes metadados serão adicionados automaticamente: tabelas de registros, enumerações e tipos de dados estendidos.</span><span class="sxs-lookup"><span data-stu-id="b61bf-123">Be aware that in this case the following metadata will be automatically added: tables of records, enumerations, and extended data types.</span></span> <span data-ttu-id="b61bf-124">Quando tipos adicionais de metadados são necessários, eles devem ser adicionados manualmente.</span><span class="sxs-lookup"><span data-stu-id="b61bf-124">When additional types of metadata are needed, they must be added manually.</span></span> 
 
<span data-ttu-id="b61bf-125">Temos algumas transações de comércio exterior com metadados relacionados, em que itens de metadados foram selecionados manualmente.</span><span class="sxs-lookup"><span data-stu-id="b61bf-125">We have some foreign trade transactions related metadata by selecting metadata items manually.</span></span> 
  
6.    <span data-ttu-id="b61bf-126">Clique em **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-126">Click **Add data source**.</span></span> 
7.    <span data-ttu-id="b61bf-127">Clique em **Registros de tabela**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-127">Click **Table records**.</span></span> 
8.    <span data-ttu-id="b61bf-128">Use o Filtro Rápido para filtrar no campo **Nome** com um valor de 'Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="b61bf-128">Use the Quick Filter to filter on the **Name** field with a value of 'Intrastat'.</span></span> 
9.    <span data-ttu-id="b61bf-129">Selecione o registro de tabela **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-129">Select the **Intrastat** table record.</span></span> 
10.    <span data-ttu-id="b61bf-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-130">Click **OK**.</span></span>
  
<span data-ttu-id="b61bf-131">Adicionamos informações de metadados sobre a tabela de registros Intrastat.</span><span class="sxs-lookup"><span data-stu-id="b61bf-131">We added metadata information about the Intrastat table of records.</span></span> 
  
11.    <span data-ttu-id="b61bf-132">Na árvore, expanda **Registros de tabela Intrastat**\>**Relações**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-132">In the tree, expand **Table records Intrastat**\>**Relations**.</span></span> 
12.    <span data-ttu-id="b61bf-133">Na árvore, selecione **Registros de tabela Intrastat**\>**Relações\IntrastatCommodity (Registros de tabela EcoResCategory)**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-133">In the tree, select **Table records Intrastat**\>**Relations\IntrastatCommodity (Table records EcoResCategory)**.</span></span>     
13.    <span data-ttu-id="b61bf-134">Clique em **Adicionar metadados**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-134">Click **Add metadata**.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b61bf-135">Os metadados sobre relações necessárias para a tabela selecionada de registros devem ser adicionados manualmente.</span><span class="sxs-lookup"><span data-stu-id="b61bf-135">Metadata about required relations for selected table of records must be added manually.</span></span> 
  
16.    <span data-ttu-id="b61bf-136">Clique em **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-136">Click **Add data source**.</span></span> 
17.    <span data-ttu-id="b61bf-137">Clique em **Enumeração**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-137">Click **Enumeration**.</span></span> 
18.    <span data-ttu-id="b61bf-138">Use o Filtro Rápido para filtrar no campo **Nome** com um valor de 'IntrastatDirection'.</span><span class="sxs-lookup"><span data-stu-id="b61bf-138">Use the Quick Filter to filter on the **Name** field with a value of 'IntrastatDirection'.</span></span> 
19.    <span data-ttu-id="b61bf-139">Selecione o registro **Enumeração IntrastatDirection**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-139">Select the **IntrastatDirection enumeration** record.</span></span> 
20.    <span data-ttu-id="b61bf-140">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-140">Click **OK**.</span></span> 
21.    <span data-ttu-id="b61bf-141">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-141">Click **Save**.</span></span>  
22.    <span data-ttu-id="b61bf-142">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b61bf-142">Close the page.</span></span> 
  
## <a name="complete-the-draft-version-of-metadata-configuration"></a><span data-ttu-id="b61bf-143">Preencha a versão de rascunho de configuração de metadados</span><span class="sxs-lookup"><span data-stu-id="b61bf-143">Complete the draft version of metadata configuration</span></span>
1.    <span data-ttu-id="b61bf-144">Clique em **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-144">Click **Change status**.</span></span> 
2.    <span data-ttu-id="b61bf-145">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-145">Click **Complete**.</span></span> 
3.    <span data-ttu-id="b61bf-146">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-146">Click **OK**.</span></span> 
4.    <span data-ttu-id="b61bf-147">Selecione a versão concluída **1**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-147">Select the completed version **1**.</span></span> 
  
## <a name="export-the-completed-version-of-metadata-configuration-from-application-as-xml-file"></a><span data-ttu-id="b61bf-148">Exporte a versão concluída da configuração de metadados do aplicativo como o arquivo XML</span><span class="sxs-lookup"><span data-stu-id="b61bf-148">Export the completed version of metadata configuration from application as XML file</span></span>
1.    <span data-ttu-id="b61bf-149">Clique em **Taxa de câmbio**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-149">Click **Exchange**.</span></span> 
2.    <span data-ttu-id="b61bf-150">Clique em **Exportar como o arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-150">Click **Export as XML file**.</span></span> 
3.    <span data-ttu-id="b61bf-151">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b61bf-151">Click **OK**.</span></span> 
    
<span data-ttu-id="b61bf-152">A configuração de metadados de ER criada foi salva como um arquivo XML que pode ser importado para o RCS e usado como a fonte de informações sobre metadados para o domínio comercial de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="b61bf-152">The created ER metadata configuration has been saved as XML file that can be imported to RCS and used as the source of information about metadata for the foreign trade business domain.</span></span> <span data-ttu-id="b61bf-153">Com base nessas informações, podemos especificar o mapeamento entre metadados de aplicativos e o modelo de dados do ER.</span><span class="sxs-lookup"><span data-stu-id="b61bf-153">Based on this information, we can specify the mapping between application metadata and ER data model.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]