---
title: Configurar nomes de campo de aplicativo no aplicativo de depósito
description: Este tópico descreve como definir e configurar os nomes e prioridades de campos do aplicativo de depósito no Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f9b02b93895757580b323a4cd891909d5551ea55
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205750"
---
# <a name="configure-app-field-names-in-warehousing-app"></a><span data-ttu-id="46ff3-103">Configurar nomes de campo de aplicativo no aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="46ff3-103">Configure app field names in Warehousing app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46ff3-104">Este tópico descreve como definir e configurar os nomes e prioridades de campos do aplicativo de depósito no Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="46ff3-104">This topic describes how to define and configure warehouse app field names and priorities in Dynamics 365 Supply Chain Management.</span></span> 

> [!NOTE]
> <span data-ttu-id="46ff3-105">Este tópico se aplica a recursos do Gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="46ff3-105">This topic applies to features in Warehouse management.</span></span> <span data-ttu-id="46ff3-106">Ele não se aplica aos recursos do Gerenciamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="46ff3-106">It doesn’t apply to features in Inventory management.</span></span> <span data-ttu-id="46ff3-107">O Warehousing é um aplicativo que você pode usar para realizar tarefas de depósito.</span><span class="sxs-lookup"><span data-stu-id="46ff3-107">Warehousing is an application that you can use to perform warehouse tasks.</span></span> <span data-ttu-id="46ff3-108">Você pode definir e configurar os nomes de campo usados no aplicativo, bem como configurar a prioridade à qual os nomes de campo devem ser atribuídos.</span><span class="sxs-lookup"><span data-stu-id="46ff3-108">You can define and configure the field names that are used in the app, as well as configure the priority to which the field names should be assigned.</span></span> <span data-ttu-id="46ff3-109">Este tópico explica como definir e configurar esses nomes e prioridades de campos do aplicativo de depósito e como eles são usados no Warehousing.</span><span class="sxs-lookup"><span data-stu-id="46ff3-109">This topic explains how to define and configure these warehouse app field names and priorities, and how they are used in Warehousing.</span></span> <span data-ttu-id="46ff3-110">Para obter informações detalhadas sobre como configurar a conexão com o Warehousing, consulte o tutorial [Visão geral da instalação e configuração do aplicativo de depósito](install-configure-warehousing-app.md).</span><span class="sxs-lookup"><span data-stu-id="46ff3-110">For detailed information about how to configure the connection to FWarehousing, refer to the tutorial [Install and configure the Warehousing app overview](install-configure-warehousing-app.md).</span></span>

## <a name="configure-warehouse-app-field-names"></a><span data-ttu-id="46ff3-111">Configurar nomes de campo do aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="46ff3-111">Configure warehouse app field names</span></span>

<span data-ttu-id="46ff3-112">Ao usar o Warehousing em seu dispositivo móvel, você pode configurar como os metadados devem ser exibidos no dispositivo na página **Nomes de campo de aplicativo de depósito**.</span><span class="sxs-lookup"><span data-stu-id="46ff3-112">When you use Warehousing on your mobile device, you can configure how metadata should be displayed on your device on the **Warehouse app field names** page.</span></span> <span data-ttu-id="46ff3-113">Em uma nova empresa, selecione **Criar configuração padrão** para gerar todos os nomes de campo que serão usados nos fluxos de trabalho do dispositivo móvel do depósito e depois atribuir um modo e tipo de entrada preferenciais para eles.</span><span class="sxs-lookup"><span data-stu-id="46ff3-113">In a new company, select **Create default setup** to generate all field names that will be used in the warehouse mobile device workflows, and then assign a preferred input mode and input type to them.</span></span> <span data-ttu-id="46ff3-114">Após a criação de todos os nomes de campo, você pode selecionar as seguintes opções de saída.</span><span class="sxs-lookup"><span data-stu-id="46ff3-114">After you have generated all field names, you can select the following input options.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46ff3-115">Opção</span><span class="sxs-lookup"><span data-stu-id="46ff3-115">Option</span></span></th>
<th><span data-ttu-id="46ff3-116">descrição</span><span class="sxs-lookup"><span data-stu-id="46ff3-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="46ff3-117">Modo de entrada preferencial</span><span class="sxs-lookup"><span data-stu-id="46ff3-117">Preferred input mode</span></span></td>
<td><span data-ttu-id="46ff3-118">Essa opção define se um campo de digitalização ou um campo de saída de entrada manual deve ser mostrado para o nome de campo selecionado.</span><span class="sxs-lookup"><span data-stu-id="46ff3-118">This option defines whether a scanning field or a manual entry input field should be shown for the selected field name.</span></span> <span data-ttu-id="46ff3-119">Isso é útil para diferenciar campos, o que dependerá da utilidade dos códigos de barras para o campo.</span><span class="sxs-lookup"><span data-stu-id="46ff3-119">This is useful to distinguish fields depending on if barcodes are used for the field.</span></span> <span data-ttu-id="46ff3-120"><strong>Observação:</strong> para nomes de campo com modo de saída preferencial definido como <strong>Digitalizando</strong>, você pode inserir informações manualmente se o código de barras for ilegível ou estiver danificado.</span><span class="sxs-lookup"><span data-stu-id="46ff3-120"><strong>Note:</strong> For field names with preferred input mode set to <strong>Scanning</strong>, you can enter information manually if the barcode is unreadable or damaged.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="46ff3-121">Tipo de Entrada</span><span class="sxs-lookup"><span data-stu-id="46ff3-121">Input type</span></span></td>
<td><span data-ttu-id="46ff3-122">Essa opção define qual tipo de saída deve ser usado para o nome do campo selecionado.</span><span class="sxs-lookup"><span data-stu-id="46ff3-122">This option defines what input type should be used for the selected field name.</span></span> <span data-ttu-id="46ff3-123">Quatro opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="46ff3-123">Four options are available:</span></span>
<ul>
<li><span data-ttu-id="46ff3-124"><strong>Seleção</strong> - Contém uma lista de opções para escolha.</span><span class="sxs-lookup"><span data-stu-id="46ff3-124"><strong>Selection</strong> - Contains a list of options to choose from.</span></span> <span data-ttu-id="46ff3-125">Nomes de campo com essa opção não são editáveis.</span><span class="sxs-lookup"><span data-stu-id="46ff3-125">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="46ff3-126"><strong>Data</strong> - Nomes de campo especificados como data mostrarão um formato de data com o rótulo.</span><span class="sxs-lookup"><span data-stu-id="46ff3-126"><strong>Date</strong> - Field names specified as date will show a date format with the label.</span></span> <span data-ttu-id="46ff3-127">Com isso, os trabalhadores de depósito podem ver em qual formato inserir a data.</span><span class="sxs-lookup"><span data-stu-id="46ff3-127">This helps warehouse workers see in which format to enter the date.</span></span> <span data-ttu-id="46ff3-128">Nomes de campo com essa opção não são editáveis.</span><span class="sxs-lookup"><span data-stu-id="46ff3-128">Field names with this option are not editable.</span></span></li>
<li><span data-ttu-id="46ff3-129"><strong>Alfa</strong> - Se selecionado, o teclado do dispositivo será usado na inserção manual de informações no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="46ff3-129"><strong>Alpha</strong> - If selected, the device keyboard will be used when entering information manually in the app.</span></span> <span data-ttu-id="46ff3-130">A experiência de teclado pode ser alterada dependendo de qual dispositivo é usado.</span><span class="sxs-lookup"><span data-stu-id="46ff3-130">The keyboard experience can be changed depending on which device is used.</span></span></li>
<li><span data-ttu-id="46ff3-131"><strong>Numérico</strong> - Para nomes de campo que usam apenas saída numérica, você pode selecionar essa opção para exibir um teclado numérico personalizado com o campo de saída em vez do teclado do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="46ff3-131"><strong>Numeric</strong> - For field names that use numeric input only, you can select this option to display a custom numeric keypad with the input field instead of the device keyboard.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a><span data-ttu-id="46ff3-132">Configurar a prioridade de campo do aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="46ff3-132">Configure warehouse app field priority</span></span>

<span data-ttu-id="46ff3-133">Na página **Prioridade de campo de aplicativo de depósito**, você pode colocar nomes de campo em grupos de prioridade diferentes.</span><span class="sxs-lookup"><span data-stu-id="46ff3-133">On the **Warehouse app field priority** page, you can put field names into different priority groups.</span></span> <span data-ttu-id="46ff3-134">Com isso, é possível decidir quais informações devem ser exibidas na página de tarefa principal quando os trabalhadores de depósito realizam tarefas usando o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="46ff3-134">This makes it possible to decide what information should be displayed on the main task page when warehouse workers perform tasks using the app.</span></span> <span data-ttu-id="46ff3-135">Se clicar em **Criar configuração padrão**, um conjunto padrão de grupos de prioridades será gerado.</span><span class="sxs-lookup"><span data-stu-id="46ff3-135">If you click **Create default setup**, a default set of priority groups will be generated.</span></span> <span data-ttu-id="46ff3-136">É possível criar tantos grupos de prioridade quantos forem necessários, mas apenas três grupos de prioridades serão mostrados na página de tarefas.</span><span class="sxs-lookup"><span data-stu-id="46ff3-136">It is possible to create as many priority groups as needed, but only three priority groups will be shown on the task page.</span></span> <span data-ttu-id="46ff3-137">Ao enviar os metadados ao aplicativo, o sistema atribuirá a cada campo uma prioridade relativa de acordo com seu grupo de prioridades, e o aplicativo exibirá os três primeiros grupos de prioridades contidos nos metadados na página da tarefa.</span><span class="sxs-lookup"><span data-stu-id="46ff3-137">When the system sends metadata to the app, it will assign each field a relative priority depending on its priority group, and the app will display the first three priority groups contained in the metadata on the task page.</span></span> <span data-ttu-id="46ff3-138">O resto dos metadados transbordantes serão exibidos em uma página de detalhes secundária.</span><span class="sxs-lookup"><span data-stu-id="46ff3-138">The rest of the overflowing metadata will be displayed on a secondary details page.</span></span> <span data-ttu-id="46ff3-139">A tabela a seguir mostra um exemplo de cinco grupos de prioridades.</span><span class="sxs-lookup"><span data-stu-id="46ff3-139">The following table shows an example of five priority groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46ff3-140">Grupo de prioridades</span><span class="sxs-lookup"><span data-stu-id="46ff3-140">Priority group</span></span></th>
<th><span data-ttu-id="46ff3-141">Campos atribuídos</span><span class="sxs-lookup"><span data-stu-id="46ff3-141">Assigned fields</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> <span data-ttu-id="46ff3-142">Prioridade 10</span><span class="sxs-lookup"><span data-stu-id="46ff3-142">Priority 10</span></span></td>
<td><ul>
<li><span data-ttu-id="46ff3-143">Item</span><span class="sxs-lookup"><span data-stu-id="46ff3-143">Item</span></span></li>
<li><span data-ttu-id="46ff3-144">Quantidade</span><span class="sxs-lookup"><span data-stu-id="46ff3-144">Quantity</span></span></li>
<li><span data-ttu-id="46ff3-145">Unidade de medida</span><span class="sxs-lookup"><span data-stu-id="46ff3-145">Unit of measure</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="46ff3-146">Prioridade 20</span><span class="sxs-lookup"><span data-stu-id="46ff3-146">Priority 20</span></span></td>
<td><ul>
<li><span data-ttu-id="46ff3-147">Posição de cluster</span><span class="sxs-lookup"><span data-stu-id="46ff3-147">Cluster position</span></span></li>
<li><span data-ttu-id="46ff3-148">Cluster</span><span class="sxs-lookup"><span data-stu-id="46ff3-148">Cluster</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="46ff3-149">Prioridade 30</span><span class="sxs-lookup"><span data-stu-id="46ff3-149">Priority 30</span></span></td>
<td><ul>
<li><span data-ttu-id="46ff3-150">Descrição do item</span><span class="sxs-lookup"><span data-stu-id="46ff3-150">Item description</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td> <span data-ttu-id="46ff3-151">Prioridade 40</span><span class="sxs-lookup"><span data-stu-id="46ff3-151">Priority 40</span></span></td>
<td><ul>
<li><span data-ttu-id="46ff3-152">Configuração</span><span class="sxs-lookup"><span data-stu-id="46ff3-152">Configuration</span></span></li>
<li><span data-ttu-id="46ff3-153">Cor</span><span class="sxs-lookup"><span data-stu-id="46ff3-153">Color</span></span></li>
<li><span data-ttu-id="46ff3-154">Tamanho</span><span class="sxs-lookup"><span data-stu-id="46ff3-154">Size</span></span></li>
<li><span data-ttu-id="46ff3-155">Estilo</span><span class="sxs-lookup"><span data-stu-id="46ff3-155">Style</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td> <span data-ttu-id="46ff3-156">Prioridade 50</span><span class="sxs-lookup"><span data-stu-id="46ff3-156">Priority 50</span></span></td>
<td><ul>
<li><span data-ttu-id="46ff3-157">Local</span><span class="sxs-lookup"><span data-stu-id="46ff3-157">Location</span></span></li>
<li><span data-ttu-id="46ff3-158">Placa de licença</span><span class="sxs-lookup"><span data-stu-id="46ff3-158">License plate</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="46ff3-159">Por exemplo, quando um trabalhador de depósito está realizando uma tarefa em um dispositivo móvel, se os metadados que serão exibidos no aplicativo consistirem nos seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="46ff3-159">For example, when a warehouse worker is performing a task on a mobile device, if the metadata that will be displayed in the app consists of the following fields:</span></span>

-   <span data-ttu-id="46ff3-160">Item</span><span class="sxs-lookup"><span data-stu-id="46ff3-160">Item</span></span>
-   <span data-ttu-id="46ff3-161">Quantidade</span><span class="sxs-lookup"><span data-stu-id="46ff3-161">Quantity</span></span>
-   <span data-ttu-id="46ff3-162">Unidade de medida</span><span class="sxs-lookup"><span data-stu-id="46ff3-162">Unit of measure</span></span>
-   <span data-ttu-id="46ff3-163">Descrição do item</span><span class="sxs-lookup"><span data-stu-id="46ff3-163">Item description</span></span>
-   <span data-ttu-id="46ff3-164">Tamanho e local</span><span class="sxs-lookup"><span data-stu-id="46ff3-164">Size and Location</span></span>

<span data-ttu-id="46ff3-165">Com base na prioridade de campo do aplicativo de depósito configurada na tabela acima, as 3 linhas de informação a seguir serão exibidas na página de tarefas:</span><span class="sxs-lookup"><span data-stu-id="46ff3-165">Based on the warehouse app field priority set up in the table above, the following 3 rows of information will be displayed on the task page:</span></span>

-   <span data-ttu-id="46ff3-166">Linha 1: Item, quantidade, unidade de medida</span><span class="sxs-lookup"><span data-stu-id="46ff3-166">Row 1: Item, Quantity, Unit of measure</span></span>
-   <span data-ttu-id="46ff3-167">Linha 2: descrição do item</span><span class="sxs-lookup"><span data-stu-id="46ff3-167">Row 2: Item description</span></span>
-   <span data-ttu-id="46ff3-168">Linha 3: tamanho</span><span class="sxs-lookup"><span data-stu-id="46ff3-168">Row 3: Size</span></span>

<span data-ttu-id="46ff3-169">Os metadados restantes, como Local, não serão exibidos na página de tarefas, mas o serão em uma página de detalhes.</span><span class="sxs-lookup"><span data-stu-id="46ff3-169">The remaining metadata, for example, Location, will not be displayed on the task page, but will be displayed on a details page.</span></span> <span data-ttu-id="46ff3-170">Para saber mais e ver exemplos da interface do usuário, consulte a postagem do blog [Anúncio do Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span><span class="sxs-lookup"><span data-stu-id="46ff3-170">To learn more and see examples of the user interface, refer to the blog post [Announcing Finance and Operations - Warehousing](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).</span></span>

<a name="additional-resources"></a><span data-ttu-id="46ff3-171">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="46ff3-171">Additional resources</span></span>
--------

[<span data-ttu-id="46ff3-172">Visão geral da instalação e configuração do aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="46ff3-172">Install and configure the Warehousing app overview</span></span>](install-configure-warehousing-app.md)
