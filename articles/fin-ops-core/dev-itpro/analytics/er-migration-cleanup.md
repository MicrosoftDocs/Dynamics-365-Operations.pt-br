---
title: Limpeza de migração ER
description: Este tópico explica como você pode usar a função de limpeza de migração ER para resolver problemas com modelos ER.
author: NickSelin
manager: AnnBe
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, ERParameters, ERMigrationCleanup
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 090badd48785dfacf5942426d0fe53629f3c0cda
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321793"
---
# <a name="er-migration-cleanup"></a><span data-ttu-id="d0481-103">Limpeza de migração ER</span><span class="sxs-lookup"><span data-stu-id="d0481-103">ER migration cleanup</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d0481-104">Quando você gerencia as instâncias do Finance, pode decidir migrar sua instância atual para outro local.</span><span class="sxs-lookup"><span data-stu-id="d0481-104">When you manage your Finance instances, you might decide to migrate your current instance to another location.</span></span> <span data-ttu-id="d0481-105">Por exemplo, você poderá migrar sua instância de produção para um novo do ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="d0481-105">For example, you might migrate your production instance to a new sandbox environment.</span></span> <span data-ttu-id="d0481-106">Se você configurou a estrutura de Relatório eletrônico (ER) para armazenar modelos no Armazenamento de Blob Microsoft Azure, a tabela **DocuValue** no novo ambiente de área restrita refere-se à instância de Armazenamento de Blob no ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="d0481-106">If you configured the Electronic reporting (ER) framework to store templates in Microsoft Azure Blob storage, the **DocuValue** table in the new sandbox environment refers to the instance of Blob storage in the production environment.</span></span> <span data-ttu-id="d0481-107">Entretanto, essa instância não pode ser acessada do ambiente de área restrita, pois o processo de migração não dá suporte à migração de artefatos no Armazenamento de Blob.</span><span class="sxs-lookup"><span data-stu-id="d0481-107">However, this instance can't be accessed from the sandbox environment because the migration process doesn't support the migration of artifacts in Blob storage.</span></span> <span data-ttu-id="d0481-108">Em vez disso, é esperado que no novo ambiente de área de armazenamento, você consulte a instância do armazenamento de Blob no ambiente de área restrita que ainda não obteve os modelos ER.</span><span class="sxs-lookup"><span data-stu-id="d0481-108">Rather, it's expected that in the new sandbox environment, you refer to the instance of Blob storage in the sandbox environment that does not yet obtain the ER templates.</span></span>

<span data-ttu-id="d0481-109">Se você tentar executar um formato de ER que usa um modelo para gerar documentos comerciais, ocorrerá uma exceção, e você será notificado sobre o modelo ausente.</span><span class="sxs-lookup"><span data-stu-id="d0481-109">If you try to run an ER format that uses a template to generate business documents, an exception occurs, and you're notified about the missing template.</span></span> <span data-ttu-id="d0481-110">Você também é orientado a usar a opção de limpeza de migração ER para excluir e depois reimportar a configuração de formato de ER que contém o modelo.</span><span class="sxs-lookup"><span data-stu-id="d0481-110">You're also guided to use the ER migration cleanup option to delete and then re-import the ER format configuration that contains the template.</span></span>

<span data-ttu-id="d0481-111">[![Executando um formato ER](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)</span><span class="sxs-lookup"><span data-stu-id="d0481-111">[![Running an ER format](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)</span></span>

<span data-ttu-id="d0481-112">Você receberá um erro semelhante se navegar até a página **Configurações** (**Administração da organização** \> **Relatório eletrônico** \> **Configurações**) e na árvore de configurações, tente excluir uma configuração de formato ER que usa um modelo.</span><span class="sxs-lookup"><span data-stu-id="d0481-112">You will receive a similar error if you navigate to the **Configurations** page (**Organization administration** \> **Electronic reporting** \> **Configurations**) and in the configurations tree, try to delete an ER format configuration that uses a template.</span></span>

<span data-ttu-id="d0481-113">[![Exclusão um formato ER](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)</span><span class="sxs-lookup"><span data-stu-id="d0481-113">[![Deletion an ER format](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)</span></span>

<span data-ttu-id="d0481-114">Conclua as etapas a seguir para solucionar problemas com modelos ER que não podem ser acessados.</span><span class="sxs-lookup"><span data-stu-id="d0481-114">Complete the following steps to resolve issues with ER templates that you are unable to access.</span></span>

1.  <span data-ttu-id="d0481-115">Vá para a página **Administração da organização** \> **Periódico** \> **Limpeza de migração**.</span><span class="sxs-lookup"><span data-stu-id="d0481-115">Go to **Organization administration** \> **Periodic** \> **Migration cleanup** page.</span></span>
2.  <span data-ttu-id="d0481-116">Selecione uma configuração de formato ER que não pode ser executada ou excluída.</span><span class="sxs-lookup"><span data-stu-id="d0481-116">Select an ER format configuration that can’t be executed or deleted.</span></span>
3.  <span data-ttu-id="d0481-117">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d0481-117">Select **Delete**.</span></span>
4.  <span data-ttu-id="d0481-118">Confirme a exclusão da configuração de formato ER selecionado.</span><span class="sxs-lookup"><span data-stu-id="d0481-118">Confirm the deletion of the selected ER format configuration.</span></span>
5.  <span data-ttu-id="d0481-119">[Importar](download-electronic-reporting-configuration-lcs.md) a configuração de formato ER excluído para a instância Finance atual.</span><span class="sxs-lookup"><span data-stu-id="d0481-119">[Import](download-electronic-reporting-configuration-lcs.md) the deleted ER format configuration to the current Finance instance.</span></span>

## <a name="applicability"></a><span data-ttu-id="d0481-120">Aplicabilidade</span><span class="sxs-lookup"><span data-stu-id="d0481-120">Applicability</span></span>

> <span data-ttu-id="d0481-121">[Importante] A opção **Limpeza de migração** destina-se apenas a configurações de formato ER que contêm modelos ER não acessíveis.</span><span class="sxs-lookup"><span data-stu-id="d0481-121">[Important] The **Migration cleanup** option is targeted only for ER format configurations that contain non-accessible ER templates.</span></span> <span data-ttu-id="d0481-122">Quando você exclui uma configuração de formato ER usando a opção **Limpeza de migração**, o ER exclui os modelos relacionados aos artefatos de configuração no único banco de dados de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d0481-122">When you delete an ER format configuration by using the **Migration cleanup** option, ER deletes the templates that are related to the configuration artifacts in the only application database.</span></span> <span data-ttu-id="d0481-123">A existência dos arquivos físicos apropriados no armazenamento de Blob não é validada.</span><span class="sxs-lookup"><span data-stu-id="d0481-123">The existence of the appropriate physical files in Blob storage are not validated.</span></span> <span data-ttu-id="d0481-124">Em vez disso, pressupõe-se que não há nenhum.</span><span class="sxs-lookup"><span data-stu-id="d0481-124">Instead, it is assumed that there are none.</span></span> <span data-ttu-id="d0481-125">Portanto, não use a opção **Limpeza de migração** como uma alternativa para a opção de exclusão da configuração ER na página **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="d0481-125">Therefore, do not use the **Migration cleanup** option as an alternative to the ER configuration deletion option on the **Configurations** page.</span></span> <span data-ttu-id="d0481-126">Use a opção **Limpeza de migração** apenas quando uma opção de exclusão da configuração ER na página **Configurações** falhar.</span><span class="sxs-lookup"><span data-stu-id="d0481-126">Use the **Migration cleanup** option only when the ER configuration deletion option on the **Configurations** page failed.</span></span>
>
> <span data-ttu-id="d0481-127">Se você usar a opção **Limpeza de migração** para excluir uma configuração de formato ER quando o modelo conhecido está disponível no armazenamento do Blob, você exclui somente artefatos de configuração relacionados no banco de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d0481-127">If you use the **Migration cleanup** option to delete an ER format configuration when the referred template is available in the Blob storage, you only delete related configuration artifacts in the application database.</span></span> <span data-ttu-id="d0481-128">O arquivo físico do modelo no armazenamento de Blob permanece.</span><span class="sxs-lookup"><span data-stu-id="d0481-128">The physical file of the template in the Blob storage remains.</span></span> <span data-ttu-id="d0481-129">Não é mais permitido substituir o arquivo no armazenamento de Blob.</span><span class="sxs-lookup"><span data-stu-id="d0481-129">File overwriting in Blob storage is no longer allowed.</span></span> <span data-ttu-id="d0481-130">Para obter mais informações, consulte [KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217).</span><span class="sxs-lookup"><span data-stu-id="d0481-130">For more information, see [KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217).</span></span> <span data-ttu-id="d0481-131">Além disso, não será mais possível importar novamente as configurações excluídas usando a limpeza da migração neste ambiente.</span><span class="sxs-lookup"><span data-stu-id="d0481-131">Additionally, you will no longer be able to re-import the configurations deleted by using the Migration cleanup in this environment.</span></span> <span data-ttu-id="d0481-132">Para resolver esse problema, você precisa encontrar o arquivo correspondente no armazenamento Blob e excluí-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="d0481-132">To resolve this issue, you need to find the corresponding file in Blob storage and manually delete it.</span></span>

<span data-ttu-id="d0481-133">[![Importação de um formato ER](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)</span><span class="sxs-lookup"><span data-stu-id="d0481-133">[![Importing an ER format](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)</span></span>

<span data-ttu-id="d0481-134">Um problema semelhante pode ocorrer se você migrar sua instância do aplicativo para outro local que foi usado como um destino de migração mais de uma vez e para o qual o armazenamento de Blob já contém arquivos de modelo ER.</span><span class="sxs-lookup"><span data-stu-id="d0481-134">A similar issue may occur if you migrate your application instance to another location that has been used as a migration target more than once and for which the Blob storage already contains ER template files.</span></span>

<span data-ttu-id="d0481-135">Como você pode ter várias configurações de formato de ER, esse processo pode ser demorado.</span><span class="sxs-lookup"><span data-stu-id="d0481-135">Because you can have several ER format configurations, this process can be time consuming.</span></span> <span data-ttu-id="d0481-136">Portanto, o uso do recurso [Armazenamento de backup do modelo ER](er-backup-storage-templates.md) para recuperar automaticamente os modelos com referências quebradas é preferível.</span><span class="sxs-lookup"><span data-stu-id="d0481-136">Therefore, using the [Backup storage of ER templates](er-backup-storage-templates.md) feature to automatically recover templates with broken references is preferred.</span></span>