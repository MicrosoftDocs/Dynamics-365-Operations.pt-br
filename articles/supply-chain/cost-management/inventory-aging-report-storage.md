---
title: Armazenamento de relatório de classificação por vencimento do estoque
description: Este tópico descreve a funcionalidade que permite executar um Relatório de classificação por vencimento de estoque e disponibiliza a saída como um formulário e um gráfico.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8a292bd7a7ccbb09af1955e1e253b45e230c1009
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005418"
---
# <a name="inventory-aging-report-storage"></a><span data-ttu-id="205b9-103">Armazenamento de relatório de classificação por vencimento do estoque</span><span class="sxs-lookup"><span data-stu-id="205b9-103">Inventory aging report storage</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="205b9-104">No Microsoft Dynamics 365 Supply Chain Management, você pode executar um relatório **Armazenamento de relatório de classificação por vencimento do estoque** e disponibilizar a saída como um formulário e um gráfico.</span><span class="sxs-lookup"><span data-stu-id="205b9-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging report storage** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="205b9-105">No formulário, as colunas e os saldos agregação são ajustados dinamicamente, dependendo do layout configurado.</span><span class="sxs-lookup"><span data-stu-id="205b9-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="205b9-106">O gráfico oferece uma visão geral visual que dá suporte à filtragem e permite que você faça uma busca detalhada.</span><span class="sxs-lookup"><span data-stu-id="205b9-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="205b9-107">Adicionalmente, uma entidade de dados chamada **Relatório de classificação por vencimento de estoque** permite exportar os resultados de uma execução de um relatório **Armazenamento de relatório de classificação por vencimento do estoque** para um formato como um arquivo do Microsoft Excel ou um arquivo PDF.</span><span class="sxs-lookup"><span data-stu-id="205b9-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging report storage** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="205b9-108">Esse método de execução de um relatório **Armazenamento de relatório de classificação por vencimento do estoque** é útil quando as saídas contêm várias linhas.</span><span class="sxs-lookup"><span data-stu-id="205b9-108">This method of running an **Inventory aging report storage** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="205b9-109">Por exemplo, a saída conterá várias linhas se você tiver 50.000 itens e 300 repositórios criados, como depósitos, e solicitar a classificação por vencimento de estoque por item, local e depósito.</span><span class="sxs-lookup"><span data-stu-id="205b9-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="enable-the-inventory-value-storage-report-feature"></a><span data-ttu-id="205b9-110">Habilitar o recurso de relatório de armazenamento de valor de estoque</span><span class="sxs-lookup"><span data-stu-id="205b9-110">Enable the Inventory value storage report feature</span></span>

<span data-ttu-id="205b9-111">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="205b9-111">Before you can use this feature, you must enable it on your system.</span></span> <span data-ttu-id="205b9-112">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="205b9-112">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the feature status and enable it if needed.</span></span> <span data-ttu-id="205b9-113">Aqui o recurso está listado como:</span><span class="sxs-lookup"><span data-stu-id="205b9-113">Here, the feature is listed as:</span></span>

- <span data-ttu-id="205b9-114">**Módulo** - Gerenciamento de custos</span><span class="sxs-lookup"><span data-stu-id="205b9-114">**Module** - Cost management</span></span>
- <span data-ttu-id="205b9-115">**Nome do recurso** - Armazenamento de relatório de classificação por vencimento do estoque</span><span class="sxs-lookup"><span data-stu-id="205b9-115">**Feature name** - Inventory aging report storage</span></span>

## <a name="run-an-inventory-aging-report-storage"></a><span data-ttu-id="205b9-116">Executar um armazenamento de classificação por vencimento de estoque</span><span class="sxs-lookup"><span data-stu-id="205b9-116">Run an Inventory aging report storage</span></span>

1. <span data-ttu-id="205b9-117">Vá para **Gerenciamento de custos \> Consultas e relatórios \> Armazenamento do relatório de classificação por vencimento de estoque**.</span><span class="sxs-lookup"><span data-stu-id="205b9-117">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="205b9-118">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="205b9-118">Select **New**.</span></span>
1. <span data-ttu-id="205b9-119">No campo **Identificador do Processo – Nome**, insira um nome exclusivo para o relatório.</span><span class="sxs-lookup"><span data-stu-id="205b9-119">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="205b9-120">Selecione o relatório **Identificação – ID** e filtre-o como necessário.</span><span class="sxs-lookup"><span data-stu-id="205b9-120">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="205b9-121">A execução do relatório sempre é feita em um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="205b9-121">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="205b9-122">Depois que o trabalho em lotes for concluído, as saídas serão mostradas na página **Armazenamento do relatório de classificação por vencimento de estoque**.</span><span class="sxs-lookup"><span data-stu-id="205b9-122">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="205b9-123">Para exibir a saída como um formulário com um layout tradicional de grade, selecione **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="205b9-123">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="205b9-124">Para exibir a saída como um gráfico agregado, selecione **Exibir gráfico**.</span><span class="sxs-lookup"><span data-stu-id="205b9-124">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="205b9-125">O formulário não incluirá os subtotais definidos no layout de relatório.</span><span class="sxs-lookup"><span data-stu-id="205b9-125">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="205b9-126">A entidade de dados **Relatório de classificação por vencimento de estoque** permite exportar as saídas de um relatório **Armazenamento de relatório de classificação por vencimento do estoque** por meio da aplicação de um filtro para o campo **Identificador do processo – Nome** a qualquer formato que dê suporte ao Gerenciamento de dados.</span><span class="sxs-lookup"><span data-stu-id="205b9-126">The **Inventory aging report** data entity lets you export the output of an **Inventory aging report storage** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
