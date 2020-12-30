---
title: Tipo de destino de ER do arquivo
description: Este tópico fornece informações sobre como configurar um destino de arquivo para cada componente de PASTA ou ARQUIVO de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída.
author: NickSelin
manager: AnnBe
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 3dee7ec614ec1372feaa1150f5e4ebb14c32f60e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679669"
---
# <a name="archive-er-destination-type"></a><span data-ttu-id="eabe4-103">Tipo de destino de ER do arquivo</span><span class="sxs-lookup"><span data-stu-id="eabe4-103">Archive ER destination type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eabe4-104">Você pode configurar um destino de arquivo para cada componente de **Pasta** ou **Arquivo** de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída.</span><span class="sxs-lookup"><span data-stu-id="eabe4-104">You can configure an archive destination for each **Folder** or **File** component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="eabe4-105">Com base na configuração de destino, um documento gerado é armazenado como um anexo de um registro da lista de trabalhos do ER.</span><span class="sxs-lookup"><span data-stu-id="eabe4-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span> <span data-ttu-id="eabe4-106">Para exibir os resultados, vá para **Administração da organização** \> **Relatório eletrônico** \> **Trabalhos de relatórios eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="eabe4-106">To view the results, go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting jobs**.</span></span>

<span data-ttu-id="eabe4-107">Você pode usar essa opção para enviar o documento gerado para uma pasta do Microsoft SharePoint ou para o Armazenamento do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="eabe4-107">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="eabe4-108">Definir **Habilitado** para **Sim** para enviar a saída para um destino que é definido pelo tipo de documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="eabe4-108">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="eabe4-109">Somente tipos de documento onde o grupo está definido para **Arquivo** estão disponíveis para seleção.</span><span class="sxs-lookup"><span data-stu-id="eabe4-109">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="eabe4-110">Você define os [tipos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) de documento em **Administração da organização** \> **Gerenciamento de documentos** \> **Tipos de documento**.</span><span class="sxs-lookup"><span data-stu-id="eabe4-110">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="eabe4-111">A configuração de destinos de ER é o mesma que a configuração para o sistema de gerenciamento de documentos.</span><span class="sxs-lookup"><span data-stu-id="eabe4-111">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="eabe4-112">[![Página Tipos de documento](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="eabe4-112">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="eabe4-113">O local determina onde o arquivo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="eabe4-113">The location determines where the file is saved.</span></span> <span data-ttu-id="eabe4-114">Depois que o destino do **Arquivo** for ativado, os resultado poderão ser salvos no Arquivo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="eabe4-114">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="eabe4-115">Você pode exibir os resultados em **Administração da organização** \> **Relatório eletrônico** \> **Trabalhos arquivados de relatórios eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="eabe4-115">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="eabe4-116">Selecione um tipo de documento para o Arquivo de trabalho navegando para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico** \> **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="eabe4-116">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="eabe4-117">Para obter mais informações, consulte [Configurar a estrutura do ER (Relatório eletrônico)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="eabe4-117">For more information, see [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="eabe4-118">SharePoint</span><span class="sxs-lookup"><span data-stu-id="eabe4-118">SharePoint</span></span>

<span data-ttu-id="eabe4-119">Você pode salvar um arquivo em uma pasta designada do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="eabe4-119">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="eabe4-120">Para definir o servidor padrão do SharePoint, vá para **Administração da organização** \> **Gerenciamento de documentos** \> **Parâmetros de gerenciamento de documentos**.</span><span class="sxs-lookup"><span data-stu-id="eabe4-120">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="eabe4-121">Na guia **SharePoint**, configure a pasta SharePoint.</span><span class="sxs-lookup"><span data-stu-id="eabe4-121">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="eabe4-122">Em seguida, você pode selecioná-la como a pasta na qual a saída do ER será salva.</span><span class="sxs-lookup"><span data-stu-id="eabe4-122">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="eabe4-123">O local do **SharePoint** deve ser selecionado nesse tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="eabe4-123">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="eabe4-124">[![Selecionando uma pasta do SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="eabe4-124">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="eabe4-125">Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="eabe4-125">Azure Storage</span></span>

<span data-ttu-id="eabe4-126">Quando o local do tipo de documento é definido como **Armazenamento do Azure**, você pode salvar um arquivo no Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="eabe4-126">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

> [!NOTE] 
> <span data-ttu-id="eabe4-127">A estrutura ER armazena arquivos permanentemente no armazenamento de blob do Azure, ao contrário da estrutura de gerenciamento de dados, que aplica a política de retenção de sete dias para documentos que devem ser processados.</span><span class="sxs-lookup"><span data-stu-id="eabe4-127">The ER framework permanently stores files in Azure Blob storage unlike the Data management framework that applies the seven-day retention policy for documents that must be processed.</span></span> <span data-ttu-id="eabe4-128">Para obter mais informações, consulte [API para obter status da mensagem](../data-entities/recurring-integrations.md#api-for-getting-message-status) e [verificar API de status](../data-entities/data-management-api.md#status-check-api).</span><span class="sxs-lookup"><span data-stu-id="eabe4-128">For more information, see [API for getting message status](../data-entities/recurring-integrations.md#api-for-getting-message-status) and [Status check API](../data-entities/data-management-api.md#status-check-api).</span></span> <span data-ttu-id="eabe4-129">Os arquivos relacionados a ER serão armazenados no armazenamento de blob do Azure como anexos de registros da tabela de aplicativos desde que sejam necessários.</span><span class="sxs-lookup"><span data-stu-id="eabe4-129">The ER-related files will be stored in Azure Blob storage as attachments of application table records as long as necessary.</span></span> <span data-ttu-id="eabe4-130">Um único arquivo será excluído do armazenamento de blob do Azure juntamente com o registro da tabela de aplicativos ao qual esse arquivo foi anexado.</span><span class="sxs-lookup"><span data-stu-id="eabe4-130">A single file will be deleted from Azure Blob storage along with the application table record that this file was attached to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eabe4-131">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="eabe4-131">Additional resources</span></span>

- [<span data-ttu-id="eabe4-132">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="eabe4-132">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="eabe4-133">Destinos de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="eabe4-133">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="eabe4-134">Configurar gerenciamento de documentos</span><span class="sxs-lookup"><span data-stu-id="eabe4-134">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
