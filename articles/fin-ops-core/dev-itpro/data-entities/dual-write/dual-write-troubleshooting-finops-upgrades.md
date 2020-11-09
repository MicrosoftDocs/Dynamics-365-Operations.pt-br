---
title: Solucionar problemas relacionados a atualizações de aplicativos do Finance and Operations
description: Este tópico fornece informações sobre como solucionar problemas que são relacionados às atualizações dos aplicativos Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 07d6bd0bab796d7839daa2bad91f7e88c2e881b5
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997909"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a><span data-ttu-id="79040-103">Solucionar problemas relacionados a atualizações de aplicativos do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="79040-103">Troubleshoot issues related to upgrades of Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="79040-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="79040-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="79040-105">Especificamente, ele fornece informações sobre como solucionar problemas que são relacionados às atualizações dos aplicativos Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79040-105">Specifically, it provides information that can help you fix issues that are related to upgrades of Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79040-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="79040-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="79040-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="79040-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="database-synchronization-errors"></a><span data-ttu-id="79040-108">Sincronização de erros de banco de dados</span><span class="sxs-lookup"><span data-stu-id="79040-108">Database synchronization errors</span></span>

<span data-ttu-id="79040-109">**Função necessária para corrigir o problema:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="79040-109">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="79040-110">Você pode receber uma mensagem de erro semelhante à seguinte ao tentar usar a entidade **DualWriteProjectConfiguration** para atualizar um aplicativo Finance and Operations para atualização de plataforma 30.</span><span class="sxs-lookup"><span data-stu-id="79040-110">You might receive an error message that resembles the following example when you try to use the **DualWriteProjectConfiguration** entity to update a Finance and Operations app to Platform update 30.</span></span>

```console
Infolog diagnostic message: 'Cannot select a record in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

<span data-ttu-id="79040-111">Para corrigir o problema, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="79040-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="79040-112">Faça login na máquina virtual (VM) para o aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79040-112">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="79040-113">Abra Visual Studio como um administrador e abra a AOT (árvore de objetos de aplicativo).</span><span class="sxs-lookup"><span data-stu-id="79040-113">Open Visual Studio as an admin, and open the Application Object Tree (AOT).</span></span>
3. <span data-ttu-id="79040-114">Procure **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="79040-114">Search for **DualWriteProjectConfiguration**.</span></span>
4. <span data-ttu-id="79040-115">No AOT, clique com o botão direito em **DualWriteProjectConfiguration** e selecione **Adicionar ao novo projeto**.</span><span class="sxs-lookup"><span data-stu-id="79040-115">In the AOT, right-click **DualWriteProjectConfiguration** , and select **Add to new project**.</span></span> <span data-ttu-id="79040-116">Selecione **OK** para criar o novo projeto que usa opções padrão.</span><span class="sxs-lookup"><span data-stu-id="79040-116">Select **OK** to create the new project that uses default options.</span></span>
5. <span data-ttu-id="79040-117">No Gerenciador de Soluções, clique com o botão direito em **Propriedades de projeto** e defina **Sincronizar banco de dados no Build** como **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="79040-117">In Solution Explorer, right-click **Project properties** , and set **Synchronize Database on Build** to **True**.</span></span>
6. <span data-ttu-id="79040-118">Compile o projeto e confirme se a compilação foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="79040-118">Build the project, and confirm that the build is successful.</span></span>
7. <span data-ttu-id="79040-119">No menu **Dynamics 365** , selecione **Sincronizar banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="79040-119">On the **Dynamics 365** menu, select **Synchronize database**.</span></span>
8. <span data-ttu-id="79040-120">Selecione **Sincronizar** para fazer uma sincronização de banco de dados completa.</span><span class="sxs-lookup"><span data-stu-id="79040-120">Select **Synchronize** to do a full database synchronization.</span></span>
9. <span data-ttu-id="79040-121">Depois que a sincronização completa do banco de dados for bem-sucedida, execute novamente a etapa de sincronização do banco de dados em Microsoft Dynamics Lifecycle Services (LCS) e use os scripts de atualização manual conforme aplicável, para que você possa continuar com a atualização.</span><span class="sxs-lookup"><span data-stu-id="79040-121">After the full database synchronization is successful, rerun the database synchronization step in Microsoft Dynamics Lifecycle Services (LCS) and use the manual upgrade scripts as applicable, so that you can proceed with the update.</span></span>

## <a name="missing-entity-fields-issue-on-maps"></a><span data-ttu-id="79040-122">Ausência de campos de entidade na edição de mapas</span><span class="sxs-lookup"><span data-stu-id="79040-122">Missing entity fields issue on maps</span></span>

<span data-ttu-id="79040-123">**Função necessária para corrigir o problema:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="79040-123">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="79040-124">Na página **Gravação dupla** , você pode receber uma mensagem de erro parecida com o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="79040-124">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="79040-125">*Nome do campo de origem \<field name\> ausente no esquema.*</span><span class="sxs-lookup"><span data-stu-id="79040-125">*Missing source field \<field name\> in the schema.*</span></span>

![Exemplo da mensagem de erro de campo de origem ausente](media/error_missing_field.png)

<span data-ttu-id="79040-127">Para corrigir o problema, primeiro siga estas etapas para verificar se os campos estão na entidade.</span><span class="sxs-lookup"><span data-stu-id="79040-127">To fix the issue, first follow these steps to make sure that the fields are in the entity.</span></span>

1. <span data-ttu-id="79040-128">Faça login na VM para o aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79040-128">Sign in to the VM for the Finance and Operations app.</span></span>
2. <span data-ttu-id="79040-129">Acesse **Espaços de trabalho \> Gerenciamento de dados** , selecione o bloco **Parâmetros de estrutura** e, em seguida, na guia **Configurações da entidade** , selecione **Atualizar lista de entidade** para atualizar as entidades.</span><span class="sxs-lookup"><span data-stu-id="79040-129">Go to **Workspaces \> Data management** , select the **Framework parameters** tile, and then, on the **Entity settings** tab, select **Refresh entity list** to refresh the entities.</span></span>
3. <span data-ttu-id="79040-130">Vá para **Espaços de trabalho \> Gerenciamento de dados** , selecione a guia **Entidades de dados** e certifique-se de que a entidade está listada.</span><span class="sxs-lookup"><span data-stu-id="79040-130">Go to **Workspaces \> Data management** , select the **Data entities** tab, and make sure that the entity is listed.</span></span> <span data-ttu-id="79040-131">Se a entidade não estiver listada, faça login na VM para o aplicativo Finance and Operations e certifique-se de que a entidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="79040-131">If the entity isn't listed, sign in to the VM for the Finance and Operations app, and make sure the entity is available.</span></span>
4. <span data-ttu-id="79040-132">Abra a página **Mapeamento da entidade** na página **Gravação dupla** no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79040-132">Open the **Entity mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="79040-133">Selecione **Atualizar lista de entidades** para preencher automaticamente os campos nos mapeamentos de entidade.</span><span class="sxs-lookup"><span data-stu-id="79040-133">Select **Refresh entity list** to automatically fill the fields in the entity mappings.</span></span>

<span data-ttu-id="79040-134">Se o problema ainda não for solucionado, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="79040-134">If the issue still isn't fixed, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79040-135">Essas etapas o orientam no processo de exclusão de uma entidade e, em seguida, a adiciona novamente.</span><span class="sxs-lookup"><span data-stu-id="79040-135">These steps guide you through the process of deleting an entity and then adding it again.</span></span> <span data-ttu-id="79040-136">Para evitar problemas, certifique-se de seguir as etapas exatamente.</span><span class="sxs-lookup"><span data-stu-id="79040-136">To avoid issues, be sure to follow the steps exactly.</span></span>

1. <span data-ttu-id="79040-137">No aplicativo Finance and Operations, vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Entidades de dados**.</span><span class="sxs-lookup"><span data-stu-id="79040-137">In the Finance and Operations app, go to **Workspaces \> Data management** , and select the **Data entities** tile.</span></span>
2. <span data-ttu-id="79040-138">Encontre a entidade que está sem o atributo.</span><span class="sxs-lookup"><span data-stu-id="79040-138">Find the entity that is missing the attribute.</span></span> <span data-ttu-id="79040-139">Clique em **Modificar mapeamento de destino** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="79040-139">Click **Modify target mapping** in the toolbar.</span></span>
3. <span data-ttu-id="79040-140">No painel **Mapear preparo para destino** , clique em **gerar mapeamento**.</span><span class="sxs-lookup"><span data-stu-id="79040-140">On the **Map staging to target** pane, click **Generate mapping**.</span></span>
4. <span data-ttu-id="79040-141">Abra a página **Mapeamento da entidade** na página **Gravação dupla** no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="79040-141">Open the **Entity mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="79040-142">Se o atributo não estiver preenchido automaticamente no mapa, adicione-o manualmente, clicando no botão **Adicionar atributo** e clicando em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="79040-142">If the attribute is not auto-populated on the map, add it manually by clicking **Add attribute** button and then clicking **Save**.</span></span> 
6. <span data-ttu-id="79040-143">Selecione o mapa e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="79040-143">Select the map and click **Run**.</span></span>
