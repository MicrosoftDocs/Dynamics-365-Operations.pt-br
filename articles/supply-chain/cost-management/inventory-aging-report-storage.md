---
title: Relatório de classificação por vencimento do estoque
description: Este tópico descreve a funcionalidade que permite executar um Relatório de classificação por vencimento de estoque e disponibiliza a saída como um formulário e um gráfico.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 790c8fe3a52bce652227f1cef97eff6496476100
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201608"
---
# <a name="inventory-aging-report"></a><span data-ttu-id="77735-103">Relatório de classificação por vencimento do estoque</span><span class="sxs-lookup"><span data-stu-id="77735-103">Inventory aging report</span></span>


[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="77735-104">No Microsoft Dynamics 365 Supply Chain Management, você pode executar um relatório **Classificação por vencimento de estoque** e disponibilizar a saída como um formulário e um gráfico.</span><span class="sxs-lookup"><span data-stu-id="77735-104">In Microsoft Dynamics 365 Supply Chain Management, you can run an **Inventory aging** report and make the output available as a form and a chart.</span></span> <span data-ttu-id="77735-105">No formulário, as colunas e os saldos agregação são ajustados dinamicamente, dependendo do layout configurado.</span><span class="sxs-lookup"><span data-stu-id="77735-105">In the form, columns and aggregate balances are dynamically adjusted, depending on the layout that is configured.</span></span> <span data-ttu-id="77735-106">O gráfico oferece uma visão geral visual que dá suporte à filtragem e permite que você faça uma busca detalhada.</span><span class="sxs-lookup"><span data-stu-id="77735-106">The chart provides a visual overview that supports filtering and lets you drill down into details.</span></span> <span data-ttu-id="77735-107">Adicionalmente, uma entidade de dados chamada **Relatório de classificação por vencimento de estoque** permite exportar os resultados de uma execução do relatório **Classificação por vencimento de estoque** para um formato como um arquivo do Microsoft Excel ou um arquivo PDF.</span><span class="sxs-lookup"><span data-stu-id="77735-107">Additionally, a data entity that is named **Inventory aging report** lets you export the results of an **Inventory aging** report run to a format such as a Microsoft Excel file or a PDF file.</span></span>

<span data-ttu-id="77735-108">Esse método de execução de um relatório **Classificação por vencimento de estoque** é útil quando as saídas contêm várias linhas.</span><span class="sxs-lookup"><span data-stu-id="77735-108">This method of running an **Inventory aging** report is helpful in cases where the output contains many lines.</span></span> <span data-ttu-id="77735-109">Por exemplo, a saída conterá várias linhas se você tiver 50.000 itens e 300 repositórios criados, como depósitos, e solicitar a classificação por vencimento de estoque por item, local e depósito.</span><span class="sxs-lookup"><span data-stu-id="77735-109">For example, the output will contain many lines if you have 50,000 items and 300 stores that are created as warehouses, and you request inventory aging by item, site, and warehouse.</span></span>

## <a name="run-an-inventory-aging-report"></a><span data-ttu-id="77735-110">Executar um Relatório de classificação por vencimento de estoque</span><span class="sxs-lookup"><span data-stu-id="77735-110">Run an Inventory aging report</span></span>

1. <span data-ttu-id="77735-111">Vá para **Gerenciamento de custos \> Consultas e relatórios \> Armazenamento do relatório de classificação por vencimento de estoque**.</span><span class="sxs-lookup"><span data-stu-id="77735-111">Go to **Cost management \> Inquiries and reports \> Inventory aging report storage**.</span></span>
1. <span data-ttu-id="77735-112">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="77735-112">Select **New**.</span></span>
1. <span data-ttu-id="77735-113">No campo **Identificador do Processo – Nome**, insira um nome exclusivo para o relatório.</span><span class="sxs-lookup"><span data-stu-id="77735-113">In the **Process Identifier – Name** field, enter a unique name for the report.</span></span>
1. <span data-ttu-id="77735-114">Selecione o relatório **Identificação – ID** e filtre-o como necessário.</span><span class="sxs-lookup"><span data-stu-id="77735-114">Select the **Identification – ID** report, and filter it as you require.</span></span>

    <span data-ttu-id="77735-115">A execução do relatório sempre é feita em um trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="77735-115">Report execution is always done in a batch job.</span></span>

1. <span data-ttu-id="77735-116">Depois que o trabalho em lotes for concluído, as saídas serão mostradas na página **Armazenamento do relatório de classificação por vencimento de estoque**.</span><span class="sxs-lookup"><span data-stu-id="77735-116">After the batch job is completed, the output is shown on the **Inventory aging report storage** page.</span></span>
1. <span data-ttu-id="77735-117">Para exibir a saída como um formulário com um layout tradicional de grade, selecione **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="77735-117">To view the output as a form that has a traditional grid layout, select **View details**.</span></span> <span data-ttu-id="77735-118">Para exibir a saída como um gráfico agregado, selecione **Exibir gráfico**.</span><span class="sxs-lookup"><span data-stu-id="77735-118">To view the output as an aggregated chart, select **View chart**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77735-119">O formulário não incluirá os subtotais definidos no layout de relatório.</span><span class="sxs-lookup"><span data-stu-id="77735-119">The form won't include subtotals that are defined in the report layout.</span></span>

<span data-ttu-id="77735-120">A entidade de dados **Relatório de classificação por vencimento de estoque** permite exportar as saídas de um relatório **Classificação por vencimento de estoque** por meio da aplicação de um filtro para o campo **Identificador do processo – Nome** a qualquer formato que dê suporte ao Gerenciamento de dados.</span><span class="sxs-lookup"><span data-stu-id="77735-120">The **Inventory aging report** data entity lets you export the output of an **Inventory aging** report by applying a filter for the **Process Identifier – Name** field to any format that Data management supports.</span></span>
