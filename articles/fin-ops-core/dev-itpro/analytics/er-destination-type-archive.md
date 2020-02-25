---
title: Tipo de destino de ER do arquivo
description: Este tópico fornece informações sobre como configurar um destino de arquivo para cada componente de PASTA ou ARQUIVO de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 15611a4f0000ca5ccb0ac3f4012251d5bf5689ec
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019628"
---
# <span data-ttu-id="da7d8-103"><a name="ArchiveDestinationType">Local do arquivo morto</a></span><span class="sxs-lookup"><span data-stu-id="da7d8-103"><a name="ArchiveDestinationType">Archive destination</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da7d8-104">Você pode configurar um destino de arquivo para cada componente de PASTA ou ARQUIVO de um formato de ER (Relatório eletrônico) que está configurado para gerar documentos de saída.</span><span class="sxs-lookup"><span data-stu-id="da7d8-104">You can configure an archive destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="da7d8-105">Com base na configuração de destino, um documento gerado é armazenado como um anexo de um registro da lista de trabalhos do ER.</span><span class="sxs-lookup"><span data-stu-id="da7d8-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span>

<span data-ttu-id="da7d8-106">Você pode usar essa opção para enviar o documento gerado para uma pasta do Microsoft SharePoint ou para o Armazenamento do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="da7d8-106">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="da7d8-107">Definir **Habilitado** para **Sim** para enviar a saída para um destino que é definido pelo tipo de documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="da7d8-107">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="da7d8-108">Somente tipos de documento onde o grupo está definido para **Arquivo** estão disponíveis para seleção.</span><span class="sxs-lookup"><span data-stu-id="da7d8-108">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="da7d8-109">Você define os [tipos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) de documento em **Administração da organização** \> **Gerenciamento de documentos** \> **Tipos de documento**.</span><span class="sxs-lookup"><span data-stu-id="da7d8-109">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="da7d8-110">A configuração de destinos de ER é o mesma que a configuração para o sistema de gerenciamento de documentos.</span><span class="sxs-lookup"><span data-stu-id="da7d8-110">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="da7d8-111">[![Página Tipos de documento](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="da7d8-111">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="da7d8-112">O local determina onde o arquivo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="da7d8-112">The location determines where the file is saved.</span></span> <span data-ttu-id="da7d8-113">Depois que o destino do **Arquivo** for ativado, os resultado poderão ser salvos no Arquivo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="da7d8-113">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="da7d8-114">Você pode exibir os resultados em **Administração da organização** \> **Relatório eletrônico** \> **Trabalhos arquivados de relatórios eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="da7d8-114">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="da7d8-115">Selecione um tipo de documento para o Arquivo de trabalho navegando para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico** \> **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="da7d8-115">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="da7d8-116">Para obter mais informações, consulte [Configurar a estrutura do ER (Relatório eletrônico)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="da7d8-116">For more information, [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="da7d8-117">SharePoint</span><span class="sxs-lookup"><span data-stu-id="da7d8-117">SharePoint</span></span>

<span data-ttu-id="da7d8-118">Você pode salvar um arquivo em uma pasta designada do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="da7d8-118">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="da7d8-119">Para definir o servidor padrão do SharePoint, vá para **Administração da organização** \> **Gerenciamento de documentos** \> **Parâmetros de gerenciamento de documentos**.</span><span class="sxs-lookup"><span data-stu-id="da7d8-119">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="da7d8-120">Na guia **SharePoint**, configure a pasta SharePoint.</span><span class="sxs-lookup"><span data-stu-id="da7d8-120">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="da7d8-121">Em seguida, você pode selecioná-la como a pasta na qual a saída do ER será salva.</span><span class="sxs-lookup"><span data-stu-id="da7d8-121">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="da7d8-122">O local do **SharePoint** deve ser selecionado nesse tipo de documento.</span><span class="sxs-lookup"><span data-stu-id="da7d8-122">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="da7d8-123">[![Selecionando uma pasta do SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="da7d8-123">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="da7d8-124">Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="da7d8-124">Azure Storage</span></span>

<span data-ttu-id="da7d8-125">Quando o local do tipo de documento é definido como **Armazenamento do Azure**, você pode salvar um arquivo no Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="da7d8-125">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da7d8-126">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="da7d8-126">Additional resources</span></span>

- [<span data-ttu-id="da7d8-127">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="da7d8-127">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="da7d8-128">Destinos de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="da7d8-128">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="da7d8-129">Configurar gerenciamento de documentos</span><span class="sxs-lookup"><span data-stu-id="da7d8-129">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
