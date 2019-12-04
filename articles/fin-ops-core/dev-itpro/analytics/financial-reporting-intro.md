---
title: Relatórios financeiros
description: Os relatórios financeiros permitem que profissionais de finanças e negócios criem, mantenham, implementem e visualizem demonstrativos financeiros. Ela vai além das tradicionais restrições de emissão de relatórios para ajudá-lo a projetar com eficiência vários tipos de relatórios.
author: aprilolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinanicalReportingSetup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 68813
ms.assetid: fe8b27e7-a40a-4689-ac6a-7f7401c387f5
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: cdfa9ed24d0456d9beaec03ebac89098131d0675
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771133"
---
# <a name="financial-reporting"></a><span data-ttu-id="f67a6-104">Relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="f67a6-104">Financial reporting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f67a6-105">Os relatórios financeiros do aplicativo permitem que profissionais de finanças e negócios criem, mantenham, implementem e visualizem demonstrativos financeiros.</span><span class="sxs-lookup"><span data-stu-id="f67a6-105">Financial reporting for the application allows financial and business professionals to create, maintain, deploy, and view financial statements.</span></span> <span data-ttu-id="f67a6-106">Ela vai além das tradicionais restrições de emissão de relatórios para ajudá-lo a projetar com eficiência vários tipos de relatórios.</span><span class="sxs-lookup"><span data-stu-id="f67a6-106">It moves beyond traditional reporting constraints to help you efficiently design various types of reports.</span></span>

<span data-ttu-id="f67a6-107">A emissão de relatórios financeiros inclui o suporte de dimensão.</span><span class="sxs-lookup"><span data-stu-id="f67a6-107">Financial reporting includes dimension support.</span></span> <span data-ttu-id="f67a6-108">Portanto, segmentos de conta ou dimensões estão imediatamente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f67a6-108">Therefore, account segments or dimensions are immediately available.</span></span> <span data-ttu-id="f67a6-109">Não há ferramentas adicionais ou etapas de configuração necessárias.</span><span class="sxs-lookup"><span data-stu-id="f67a6-109">No additional tools or configuration steps are required.</span></span>

## <a name="financial-reporting-setup"></a><span data-ttu-id="f67a6-110">Configuração de relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="f67a6-110">Financial reporting setup</span></span>
<span data-ttu-id="f67a6-111">A página **Configuração de relatórios financeiros** possui uma lista de todas as dimensões financeiras no sistema.</span><span class="sxs-lookup"><span data-stu-id="f67a6-111">The **Financial reporting setup** page has a list of all financial dimensions in the system.</span></span> <span data-ttu-id="f67a6-112">**Contabilidade** \> **Configuração do razão** \> **Configuração de relatórios financeiros**.</span><span class="sxs-lookup"><span data-stu-id="f67a6-112">**General ledger** \> **Ledger setup** \> **Financial reporting setup**.</span></span>

<span data-ttu-id="f67a6-113">A página **Configuração de relatórios financeiros** possui duas seções que determinam os dados que você relata no Relatório financeiro:</span><span class="sxs-lookup"><span data-stu-id="f67a6-113">The **Financial reporting setup** page has two sections that determine the data you report on in Financial reporting:</span></span>

- <span data-ttu-id="f67a6-114">**Guia Dimensões** - como empresas diferentes usam dimensões e estruturas de conta diferentes, não há como determinar a ordem em que os usuários desejam exibir todas as dimensões financeiras nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="f67a6-114">**Dimensions tab** - Because different companies use different dimensions and account structures, there is no way to determine the order in which users want to view all financial dimensions on reports.</span></span> <span data-ttu-id="f67a6-115">Esta página permite definir a ordem na qual você deseja que as dimensões financeiras sejam exibidas ao criar e exibir um relatório no Relatório financeiro.</span><span class="sxs-lookup"><span data-stu-id="f67a6-115">This page allows you set the order in which you want financial dimensions to appear when you build and view a report in Financial reporting.</span></span>
- <span data-ttu-id="f67a6-116">**Guia Atributos** - é onde você pode selecionar se deseja a capacidade de usar **Fornecedores** e **Clientes** como atributos para filtragem e design de relatório.</span><span class="sxs-lookup"><span data-stu-id="f67a6-116">**Attributes tab** is where you can select whether you want the ability to use **Vendors** and **Customers** as attributes for filtering and report design.</span></span> <span data-ttu-id="f67a6-117">O relatório de Fornecedor e Cliente será valioso apenas se você não inserir vários fornecedores ou clientes em um único comprovante ao lançar transações.</span><span class="sxs-lookup"><span data-stu-id="f67a6-117">Reporting on Vendor and Customer will only be valuable if you do not enter multiple vendors or customers in a single voucher when posting transactions.</span></span> <span data-ttu-id="f67a6-118">Escolher o Fornecedor e/ou o Cliente adicionará um tempo extra à integração.</span><span class="sxs-lookup"><span data-stu-id="f67a6-118">Choosing Vendor and/or Customer will add additional time to the integration.</span></span>

## <a name="financial-reporting-components"></a><span data-ttu-id="f67a6-119">Componentes de relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="f67a6-119">Financial reporting components</span></span>
<span data-ttu-id="f67a6-120">Os componentes a seguir do relatório financeiro facilitam a criação, exibição e agendamento de relatórios.</span><span class="sxs-lookup"><span data-stu-id="f67a6-120">The following components of financial reporting make it easy to create, view, and schedule reports.</span></span>

| <span data-ttu-id="f67a6-121">Componente</span><span class="sxs-lookup"><span data-stu-id="f67a6-121">Component</span></span>        | <span data-ttu-id="f67a6-122">Funções</span><span class="sxs-lookup"><span data-stu-id="f67a6-122">Functions</span></span> | <span data-ttu-id="f67a6-123">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="f67a6-123">Additional information</span></span> |
|------------------|-----------|------------------------|
| <span data-ttu-id="f67a6-124">Designer de Relatórios</span><span class="sxs-lookup"><span data-stu-id="f67a6-124">Report Designer</span></span>  | <span data-ttu-id="f67a6-125">A criação dos blocos de construção do relatório que podem ser combinados para definir e gerar um relatório.</span><span class="sxs-lookup"><span data-stu-id="f67a6-125">Create report building blocks that can be combined to define and generate a report.</span></span> <span data-ttu-id="f67a6-126">O assistente de relatório orienta usuários menos experientes no processo de design.</span><span class="sxs-lookup"><span data-stu-id="f67a6-126">The report wizard guides less experienced users through the design process.</span></span> <span data-ttu-id="f67a6-127">Os usuários avançados podem criar novos blocos de construção de relatório ou mudar blocos de construção existentes para atender aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="f67a6-127">Advanced users can create new report building blocks or modify existing building blocks to meet their requirements.</span></span> | |
| <span data-ttu-id="f67a6-128">Agendas de relatórios</span><span class="sxs-lookup"><span data-stu-id="f67a6-128">Report schedules</span></span> | <span data-ttu-id="f67a6-129">Agende um relatório único ou um grupo de relatórios para que ele seja gerado em uma base regular.</span><span class="sxs-lookup"><span data-stu-id="f67a6-129">Schedule a single report or a group of reports so that it is generated on a regular basis.</span></span> | [<span data-ttu-id="f67a6-130">Gerar relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="f67a6-130">Generate financial reports</span></span>](generate-financial-report.md) |

## <a name="features"></a><span data-ttu-id="f67a6-131">Recursos</span><span class="sxs-lookup"><span data-stu-id="f67a6-131">Features</span></span>
<table>
<thead>
<tr>
<th><span data-ttu-id="f67a6-132">Recurso</span><span class="sxs-lookup"><span data-stu-id="f67a6-132">Feature</span></span></th>
<th><span data-ttu-id="f67a6-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="f67a6-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f67a6-134">Flexibilidade na criação de relatórios</span><span class="sxs-lookup"><span data-stu-id="f67a6-134">Report design flexibility</span></span></td>
<td><span data-ttu-id="f67a6-135">O Designer de Relatórios fornece as seguintes opções de relatório quando você cria um relatório:</span><span class="sxs-lookup"><span data-stu-id="f67a6-135">Report Designer provides the following reporting options when you design a report:</span></span>
<ul>
<li><span data-ttu-id="f67a6-136">Salvar combinações de dimensões, e reutilizar as dimensões para vários relatórios.</span><span class="sxs-lookup"><span data-stu-id="f67a6-136">Save dimension combinations, and reuse the dimensions for multiple reports.</span></span></li>
<li><span data-ttu-id="f67a6-137">Controlar como as descrições de dimensão são formatadas e exibidas.</span><span class="sxs-lookup"><span data-stu-id="f67a6-137">Control how dimension descriptions are formatted and displayed.</span></span></li>
<li><span data-ttu-id="f67a6-138">Identificar as contas ou dimensões que foram omitidas dos blocos de construção do relatório.</span><span class="sxs-lookup"><span data-stu-id="f67a6-138">Identify accounts or dimensions that have been omitted from report building blocks.</span></span></li>
<li><span data-ttu-id="f67a6-139">Formatar cabeçalhos para previsões contínuas.</span><span class="sxs-lookup"><span data-stu-id="f67a6-139">Format headers for rolling forecasts.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="f67a6-140">Colaboração de relatório financeiro</span><span class="sxs-lookup"><span data-stu-id="f67a6-140">Financial report collaboration</span></span></td>
<td><span data-ttu-id="f67a6-141">Os seguintes recursos ajudam a gerenciar a geração e distribuição de relatórios:</span><span class="sxs-lookup"><span data-stu-id="f67a6-141">The following features help you manage the generation and distribution of reports:</span></span>
<ul>
<li><span data-ttu-id="f67a6-142">Agendar relatórios para que eles possam ser gerados automaticamente de forma diária, semanal, mensal ou anual.</span><span class="sxs-lookup"><span data-stu-id="f67a6-142">Schedule reports so that they are automatically generated on a daily, weekly, monthly, or annual basis.</span></span></li>
<li><span data-ttu-id="f67a6-143">Exportar para o formato XPS somente leitura, que fornece a melhor segurança de documentos por meio de assinaturas digitais.</span><span class="sxs-lookup"><span data-stu-id="f67a6-143">Export to the read-only XPS format, which provides better document security through digital signatures.</span></span></li>
<li><span data-ttu-id="f67a6-144">Exportar para uma planilha do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="f67a6-144">Export to a Microsoft Excel worksheet.</span></span></li>
<li><span data-ttu-id="f67a6-145">Para compartilhar relatórios, você pode criar mensagens de emails contendo links para os relatórios.</span><span class="sxs-lookup"><span data-stu-id="f67a6-145">To share reports, you can create email messages that contain links to the reports.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="f67a6-146">Exibição interativa de relatório</span><span class="sxs-lookup"><span data-stu-id="f67a6-146">Interactive report viewing</span></span></td>
<td><span data-ttu-id="f67a6-147">Os recursos interativos permitem executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="f67a6-147">Interactive features let you perform the following tasks:</span></span>
<ul>
<li><span data-ttu-id="f67a6-148">Altere a data do relatório para o relatório que você está visualizando.</span><span class="sxs-lookup"><span data-stu-id="f67a6-148">Change the report date for the report that you're viewing.</span></span></li>
<li><span data-ttu-id="f67a6-149">Altere a moeda do relatório que você está visualizando.</span><span class="sxs-lookup"><span data-stu-id="f67a6-149">Change the currency of the report that you're viewing.</span></span></li>
<li><span data-ttu-id="f67a6-150">Exiba o relatório em uma exibição de resumo ou uma exibição detalhada.</span><span class="sxs-lookup"><span data-stu-id="f67a6-150">View the report in either a summary view or a detailed view.</span></span></li>
<li><span data-ttu-id="f67a6-151">Adicione filtros de dimensão para limitar o conteúdo do relatório para uma dimensão específica ou uma combinação de dimensões.</span><span class="sxs-lookup"><span data-stu-id="f67a6-151">Add dimension filters to limit the report content to a specific dimension or combination of dimensions.</span></span></li>
<li><span data-ttu-id="f67a6-152">Adicione filtros de atributo para limitar o conteúdo do relatório para um atributo específico ou uma combinação de atributos.</span><span class="sxs-lookup"><span data-stu-id="f67a6-152">Add attribute filters to limit the report content to a specific attribute or combination of attributes.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="f67a6-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f67a6-153">Additional resources</span></span>
[<span data-ttu-id="f67a6-154">Gerar relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="f67a6-154">Generate financial reports</span></span>](generate-financial-report.md)
