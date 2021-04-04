---
title: Definições de relatório no designer de relatório financeiro
description: Este artigo fornece informações sobre definições de relatório.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59131
ms.assetid: 966a3f1d-c59c-4a84-acd4-5bb7e65144c8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 073df430892e01d4842b2af147b0ae2765b1c66a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570333"
---
# <a name="report-definitions-in-financial-report-designer"></a><span data-ttu-id="d8d04-103">Definições de relatório no designer de relatório financeiro</span><span class="sxs-lookup"><span data-stu-id="d8d04-103">Report definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8d04-104">Este artigo fornece informações sobre definições de relatório.</span><span class="sxs-lookup"><span data-stu-id="d8d04-104">This article provides information about report definitions.</span></span> <span data-ttu-id="d8d04-105">Uma definição de relatórios é um componente de relatório (ou bloco de construção) que usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório.</span><span class="sxs-lookup"><span data-stu-id="d8d04-105">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="d8d04-106">Uma definição de relatório também fornece opções e configurações para personalizar um relatório.</span><span class="sxs-lookup"><span data-stu-id="d8d04-106">A report definition also provides options and settings that for customizing a report.</span></span> 

<span data-ttu-id="d8d04-107">Uma definição de relatórios é um componente de relatório (ou bloco de construção) que usa uma definição de linha, uma definição de coluna e uma definição de árvore de relatórios opcional para criar um relatório.</span><span class="sxs-lookup"><span data-stu-id="d8d04-107">A report definition is a report component (or building block) that uses a row definition, a column definition, and an optional reporting tree definition to create a report.</span></span> <span data-ttu-id="d8d04-108">Uma definição de relatório também fornece opções e configurações que você pode usar para personalizar um relatório.</span><span class="sxs-lookup"><span data-stu-id="d8d04-108">A report definition also provides options and settings that you can use to customize a report.</span></span> <span data-ttu-id="d8d04-109">Depois de estabelecer as definições de linha e de coluna, você deverá combiná-las em uma definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="d8d04-109">After you define row definitions and column definitions, you must combine them in a report definition.</span></span> <span data-ttu-id="d8d04-110">Nesse ponto, você também pode especificar outros aspectos das definições, como o nível de detalhe e a data do relatório.</span><span class="sxs-lookup"><span data-stu-id="d8d04-110">At this point, you also define other aspects of the definitions, such as the detail level and report date.</span></span> <span data-ttu-id="d8d04-111">Você pode salvar e gerar um relatório.</span><span class="sxs-lookup"><span data-stu-id="d8d04-111">You can then save and generate a report.</span></span> <span data-ttu-id="d8d04-112">O relatório financeiro fornece os seguintes níveis de detalhe:</span><span class="sxs-lookup"><span data-stu-id="d8d04-112">Financial reporting offers the following levels of detail:</span></span>

- <span data-ttu-id="d8d04-113">Financeiro</span><span class="sxs-lookup"><span data-stu-id="d8d04-113">Financial</span></span>
- <span data-ttu-id="d8d04-114">Financeiro e Contas</span><span class="sxs-lookup"><span data-stu-id="d8d04-114">Financial and Account</span></span>
- <span data-ttu-id="d8d04-115">Financeiro, Contas e Transações</span><span class="sxs-lookup"><span data-stu-id="d8d04-115">Financial, Account, and Transaction</span></span>

<span data-ttu-id="d8d04-116">Entretanto, dependendo de como os dados são armazenados no sistema de ERP do Microsoft Dynamics, os detalhes da transação podem não estar disponíveis nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="d8d04-116">However, depending on how data is stored in the Microsoft Dynamics ERP system, transaction details might not be available in reports.</span></span>

## <a name="create-a-report-definition"></a><span data-ttu-id="d8d04-117">Criar uma definição de relatório</span><span class="sxs-lookup"><span data-stu-id="d8d04-117">Create a report definition</span></span>
1. <span data-ttu-id="d8d04-118">No Designer de Relatórios, no menu **Arquivo**, clique em **Novo** e selecione **Definição de Relatório**.</span><span class="sxs-lookup"><span data-stu-id="d8d04-118">In Report Designer, on the **File** menu, click **New**, and then select **Report Definition**.</span></span>
2. <span data-ttu-id="d8d04-119">Especifique as informações apropriadas nas guias **Relatório**, **Saída e Distribuição**, **Cabeçalhos e Rodapés** e **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="d8d04-119">Specify the appropriate information on the **Report**, **Output and Distribution**, **Headers and Footers**, and **Settings** tabs.</span></span>

## <a name="contents-of-a-report-definition"></a><span data-ttu-id="d8d04-120">Conteúdos para uma definição de relatório</span><span class="sxs-lookup"><span data-stu-id="d8d04-120">Contents of a report definition</span></span>
<span data-ttu-id="d8d04-121">A tabela a seguir descreve as guias em uma definição de relatório e como as informações são usadas.</span><span class="sxs-lookup"><span data-stu-id="d8d04-121">The following table describes the tabs in a report definition and how the information is used.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="d8d04-122">Guia</span><span class="sxs-lookup"><span data-stu-id="d8d04-122">Tab</span></span></th>
<th><span data-ttu-id="d8d04-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="d8d04-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="d8d04-124">Relatório</span><span class="sxs-lookup"><span data-stu-id="d8d04-124">Report</span></span></td>
<td><span data-ttu-id="d8d04-125">Criar, configurar ou alterar um relatório existente.</span><span class="sxs-lookup"><span data-stu-id="d8d04-125">Create a report, configure a report, or modify an existing report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d8d04-126">Saída e Distribuição</span><span class="sxs-lookup"><span data-stu-id="d8d04-126">Output and Distribution</span></span></td>
<td><span data-ttu-id="d8d04-127">Alterar o tipo de saída e o destino do relatório.</span><span class="sxs-lookup"><span data-stu-id="d8d04-127">Change the output type and destination of the report.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d8d04-128">Cabeçalhos e Rodapés</span><span class="sxs-lookup"><span data-stu-id="d8d04-128">Headers and Footers</span></span></td>
<td><span data-ttu-id="d8d04-129">Definir e formatar os cabeçalhos e rodapés do relatório.</span><span class="sxs-lookup"><span data-stu-id="d8d04-129">Define and format the headers and footers for the report.</span></span> <span data-ttu-id="d8d04-130">Por exemplo, você pode adicionar texto ou imagens ao cabeçalho ou ao rodapé.</span><span class="sxs-lookup"><span data-stu-id="d8d04-130">For example, you can add text or images to the header or footer.</span></span> <span data-ttu-id="d8d04-131">O relatório financeiro dá suporte a arquivos .bmp, .jpg e .png para imagens.</span><span class="sxs-lookup"><span data-stu-id="d8d04-131">Financial reporting supports .bmp, .jpg, and .png files for images.</span></span> <span data-ttu-id="d8d04-132">Você também pode adicionar códigos de autotexto para inserir outras informações, como o nome da empresa, o nome do relatório ou o número de página.</span><span class="sxs-lookup"><span data-stu-id="d8d04-132">You can also add autotext codes to insert other information, such as a company name, report name, or page number.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="d8d04-133">Configurações</span><span class="sxs-lookup"><span data-stu-id="d8d04-133">Settings</span></span></td>
<td><span data-ttu-id="d8d04-134">Especificar configurações da definição de relatório, como as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="d8d04-134">Specify report definition settings, such as the following settings:</span></span>
<ul>
<li><span data-ttu-id="d8d04-135">Formatação e valores de arredondamento</span><span class="sxs-lookup"><span data-stu-id="d8d04-135">Formatting and rounding amounts</span></span></li>
<li><span data-ttu-id="d8d04-136">Relatórios de detalhe do formato</span><span class="sxs-lookup"><span data-stu-id="d8d04-136">Format detail reports</span></span></li>
<li><span data-ttu-id="d8d04-137">Formatar hierarquias organizacionais</span><span class="sxs-lookup"><span data-stu-id="d8d04-137">Format reporting trees</span></span></li>
<li><span data-ttu-id="d8d04-138">Gerar um relatório de exceção</span><span class="sxs-lookup"><span data-stu-id="d8d04-138">Generate an exception report</span></span></li>
<li><span data-ttu-id="d8d04-139">Especificar conversão de moeda</span><span class="sxs-lookup"><span data-stu-id="d8d04-139">Specify currency conversion</span></span></li>
<li><span data-ttu-id="d8d04-140">Gerar um subtotal e filtrar detalhes da conta</span><span class="sxs-lookup"><span data-stu-id="d8d04-140">Subtotal and filter account details</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="d8d04-141">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d8d04-141">Additional resources</span></span>

[<span data-ttu-id="d8d04-142">Relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="d8d04-142">Financial reporting</span></span>](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]