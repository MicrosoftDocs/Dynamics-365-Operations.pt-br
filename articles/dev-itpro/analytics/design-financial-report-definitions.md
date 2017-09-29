---
title: "Definições de relatório no designer de relatório financeiro"
description: "Este artigo fornece informações sobre definições de relatório. Uma definição de relatórios é um componente de relatório (ou bloco de construção) que usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório. Uma definição de relatório também fornece opções e configurações para personalizar um relatório."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Management Reporter, UnifiedOperations, Core
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 96090a3ae15294d98d6207c8eb4a1e58429ca9eb
ms.contentlocale: pt-br
ms.lasthandoff: 07/18/2017

---

# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="69b44-105">Definições de relatório no designer de relatório financeiro</span><span class="sxs-lookup"><span data-stu-id="69b44-105">Report definitions in financial report designer</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="69b44-106">Este artigo fornece informações sobre definições de relatório.</span><span class="sxs-lookup"><span data-stu-id="69b44-106">This article provides information about report definitions.</span></span> <span data-ttu-id="69b44-107">Uma definição de relatórios é um componente de relatório (ou bloco de construção) que usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório.</span><span class="sxs-lookup"><span data-stu-id="69b44-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="69b44-108">Uma definição de relatório também fornece opções e configurações para personalizar um relatório.</span><span class="sxs-lookup"><span data-stu-id="69b44-108">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="69b44-109">Uma definição de relatórios é um componente de relatório (ou bloco de construção) que usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório.</span><span class="sxs-lookup"><span data-stu-id="69b44-109">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="69b44-110">Uma definição de relatório também fornece opções e configurações que você pode usar para personalizar um relatório.</span><span class="sxs-lookup"><span data-stu-id="69b44-110">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="69b44-111">Após especificar definições de linha e de coluna, você deve combiná-las em uma definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="69b44-111">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="69b44-112">Nesse ponto, você também pode especificar outros aspectos das definições, como o nível de detalhe e a data do relatório.</span><span class="sxs-lookup"><span data-stu-id="69b44-112">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="69b44-113">Você pode salvar e gerar um relatório.</span><span class="sxs-lookup"><span data-stu-id="69b44-113">You can then save and generate a report.</span></span> <span data-ttu-id="69b44-114">O relatório financeiro fornece os seguintes níveis de detalhe:</span><span class="sxs-lookup"><span data-stu-id="69b44-114">Financial reporting offers the following levels of detail:</span></span>

-   <span data-ttu-id="69b44-115">Financeiro</span><span class="sxs-lookup"><span data-stu-id="69b44-115">Financial</span></span>
-   <span data-ttu-id="69b44-116">Financeiro e Contas</span><span class="sxs-lookup"><span data-stu-id="69b44-116">Financial and Account</span></span>
-   <span data-ttu-id="69b44-117">Financeiro, Contas e Transações</span><span class="sxs-lookup"><span data-stu-id="69b44-117">Financial, Account, and Transaction</span></span>

<span data-ttu-id="69b44-118">Entretanto, dependendo de como os dados são armazenados no sistema ERP do Microsoft Dynamics, os detalhes da transação podem não estar disponíveis nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="69b44-118">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="69b44-119">Criar uma definição de relatório</span><span class="sxs-lookup"><span data-stu-id="69b44-119">Create a report definition</span></span>
1.  <span data-ttu-id="69b44-120">No Designer de Relatórios, no menu **Arquivo**, clique em **Novo** e selecione **Definição de Relatório**.</span><span class="sxs-lookup"><span data-stu-id="69b44-120">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2.  <span data-ttu-id="69b44-121">Especifique as informações apropriadas nas guias **Relatório**, **Saída e Distribuição**, **Cabeçalhos e Rodapés** e **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="69b44-121">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="69b44-122">Conteúdo de uma definição de relatório</span><span class="sxs-lookup"><span data-stu-id="69b44-122">Contents of a report definition</span></span>
<span data-ttu-id="69b44-123">A tabela a seguir descreve as guias em uma definição de relatório e como as informações são usadas.</span><span class="sxs-lookup"><span data-stu-id="69b44-123">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69b44-124">Guia</span><span class="sxs-lookup"><span data-stu-id="69b44-124">Tab</span></span></th>
<th><span data-ttu-id="69b44-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="69b44-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="69b44-126">Relatório</span><span class="sxs-lookup"><span data-stu-id="69b44-126">Report</span></span></td>
<td><span data-ttu-id="69b44-127">Criar um relatório, configurar um relatório ou modificar um relatório existente.</span><span class="sxs-lookup"><span data-stu-id="69b44-127">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="69b44-128">Saída e Distribuição</span><span class="sxs-lookup"><span data-stu-id="69b44-128">Output and Distribution</span></span></td>
<td><span data-ttu-id="69b44-129">Alterar o tipo de saída e o destino do relatório.</span><span class="sxs-lookup"><span data-stu-id="69b44-129">Change the output type and destination of the report.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="69b44-130">Cabeçalhos e Rodapés</span><span class="sxs-lookup"><span data-stu-id="69b44-130">Headers and Footers</span></span></td>
<td><span data-ttu-id="69b44-131">Definir e formatar os cabeçalhos e os rodapés do relatório.</span><span class="sxs-lookup"><span data-stu-id="69b44-131">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="69b44-132">Por exemplo, você pode adicionar texto ou imagens ao cabeçalho ou ao rodapé.</span><span class="sxs-lookup"><span data-stu-id="69b44-132">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="69b44-133">O relatório financeiro dá suporte a arquivos .bmp, .jpg e .png para imagens.</span><span class="sxs-lookup"><span data-stu-id="69b44-133">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="69b44-134">Você também pode adicionar códigos de autotexto para inserir outras informações, como o nome da empresa, o nome do relatório ou o número de página.</span><span class="sxs-lookup"><span data-stu-id="69b44-134">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="69b44-135">Configurações</span><span class="sxs-lookup"><span data-stu-id="69b44-135">Settings</span></span></td>
<td><span data-ttu-id="69b44-136">Especifique configurações da definição de relatório, como estas:</span><span class="sxs-lookup"><span data-stu-id="69b44-136">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="69b44-137">Formatação e valores de arredondamento</span><span class="sxs-lookup"><span data-stu-id="69b44-137">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="69b44-138">Formatar relatórios de detalhes</span><span class="sxs-lookup"><span data-stu-id="69b44-138">Format detail reports</span></span></li>
<li><span data-ttu-id="69b44-139">Formatar árvores de relatórios</span><span class="sxs-lookup"><span data-stu-id="69b44-139">Format reporting trees</span></span></li>
<li><span data-ttu-id="69b44-140">Gerar um relatório de exceção</span><span class="sxs-lookup"><span data-stu-id="69b44-140">Generate an exception report</span></span></li>
<li><span data-ttu-id="69b44-141">Especificar a conversão de moeda</span><span class="sxs-lookup"><span data-stu-id="69b44-141">Specify currency conversion</span></span></li>
<li><span data-ttu-id="69b44-142">Detalhes de subtotal e conta de filtro</span><span class="sxs-lookup"><span data-stu-id="69b44-142">Subtotal and filter account details</span></span></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a><span data-ttu-id="69b44-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="69b44-143">See also</span></span>
--------

[<span data-ttu-id="69b44-144">Relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="69b44-144">Financial reporting</span></span>](financial-reporting-intro.md)




