---
title: Novidades ou alterações no aplicativo Dynamics AX versão 7.0.1 (maio de 2016)
description: Este artigo descreve os recursos novos ou alterados no aplicativo Microsoft Dynamics AX versão 7.0.1. Esta versão foi lançada em maio de 2016 e tem um número de compilação 7.0.1265.23014.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 91213
ms.assetid: f0bbc78f-87fc-40e9-b46a-6655893f69be
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: c830952b5d9e4887a816b5ab66d0944bddf5b505
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1561634"
---
# <a name="whats-new-or-changed-in-dynamics-ax-application-version-701-may-2016"></a><span data-ttu-id="bce0b-104">Novidades ou alterações no aplicativo Dynamics AX versão 7.0.1 (maio de 2016)</span><span class="sxs-lookup"><span data-stu-id="bce0b-104">What's new or changed in Dynamics AX application version 7.0.1 (May 2016)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bce0b-105">Este artigo descreve os recursos novos ou alterados no aplicativo Microsoft Dynamics AX versão 7.0.1.</span><span class="sxs-lookup"><span data-stu-id="bce0b-105">This article describes features that are either new or changed in Microsoft Dynamics AX application version 7.0.1.</span></span> <span data-ttu-id="bce0b-106">Esta versão foi lançada em maio de 2016 e tem um número de compilação 7.0.1265.23014.</span><span class="sxs-lookup"><span data-stu-id="bce0b-106">This version was released in May 2016 and has a build number of 7.0.1265.23014.</span></span>

## <a name="electronic-reporting-er"></a><span data-ttu-id="bce0b-107">Relatório eletrônico (RE)</span><span class="sxs-lookup"><span data-stu-id="bce0b-107">Electronic reporting (ER)</span></span>

| <span data-ttu-id="bce0b-108">O que você pode fazer?</span><span class="sxs-lookup"><span data-stu-id="bce0b-108">What can you do?</span></span> | <span data-ttu-id="bce0b-109">Por que isso é importante?</span><span class="sxs-lookup"><span data-stu-id="bce0b-109">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="bce0b-110">Configure uma caixa de diálogo de tempo de execução para a criação de relatórios através do Relatório Eletrônico (RE), para que os usuários possam selecionar as dimensões financeiras desejadas.</span><span class="sxs-lookup"><span data-stu-id="bce0b-110">Configure a run-time dialog box for designing Electronic reporting (ER) reports, so that users can select the financial dimensions that they want.</span></span> | <span data-ttu-id="bce0b-111">Em tempo de execução, na caixa de diálogo para executar um relatório de RE, os usuários podem selecionar várias dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="bce0b-111">At run time, in the dialog box for running an ER report, users can select multiple financial dimensions.</span></span> <span data-ttu-id="bce0b-112">Os detalhes das dimensões financeiras selecionadas serão exibidos no documento eletrônico gerado.</span><span class="sxs-lookup"><span data-stu-id="bce0b-112">The details of the selected financial dimensions will be displayed in the electronic document that is generated.</span></span> |
| <span data-ttu-id="bce0b-113">Configure o acesso a múltiplas dimensões financeiras durante o design de um relatório de RE, através de um único mapeamento para a fonte de dados desejada.</span><span class="sxs-lookup"><span data-stu-id="bce0b-113">Configure access to multiple financial dimensions during the design of an ER report, via a single mapping to the desired data source.</span></span> | <span data-ttu-id="bce0b-114">A mesma configuração de relatório de ER pode ser usada para gerar documentos eletrônicos que apresentam dados transacionais com detalhes de dimensões financeiras, independentemente do número de dimensões financeiras que são selecionadas tanto pelo usuário quanto configuradas para a entidade legal atual ou instância.</span><span class="sxs-lookup"><span data-stu-id="bce0b-114">The same ER report configuration can be used to generate electronic documents that present transactional data together with details of financial dimensions, regardless of the number of financial dimensions that are either selected by the user or configured for the current legal entity or instance.</span></span> |
| <span data-ttu-id="bce0b-115">Configure um relatório do RE para inserir dados em colunas geradas dinamicamente de um documento eletrônico que é criado no formato de planilha OPENXML.</span><span class="sxs-lookup"><span data-stu-id="bce0b-115">Configure an ER report to enter data in dynamically generated columns of an electronic document that is created in OPENXML worksheet format.</span></span> | <span data-ttu-id="bce0b-116">Um relatório de RE pode inserir dados em uma planilha OPENXML gerada, por meio de replicação horizontal de colunas.</span><span class="sxs-lookup"><span data-stu-id="bce0b-116">An ER report can enter data in an OPENXML worksheet that is generated, via horizontally replicating columns.</span></span> <span data-ttu-id="bce0b-117">Portanto, a mesma configuração de relatório de RE pode ser reutilizada para gerar documentos eletrônicos que possuem um número diferente de colunas geradas dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="bce0b-117">Therefore, the same ER report configuration can be reused to generate electronic documents that have a different number of dynamically generated columns.</span></span> |
| <span data-ttu-id="bce0b-118">Configure destinos do RE para que o resultado de saída de um formato seja direcionado para um destino específico: arquivo, e-mail ou arquivamento (pasta do Microsoft SharePoint ou Microsoft Azure Storage).</span><span class="sxs-lookup"><span data-stu-id="bce0b-118">Configure ER destinations so that the output result of a format is directed to specific destination: file, email, or archive (Microsoft SharePoint folder or Microsoft Azure Storage).</span></span> | <span data-ttu-id="bce0b-119">Anteriormente, ao executar uma configuração de RE, uma caixa de mensagem aparecia, solicitando uma ação de usuário para salvar ou abrir um arquivo.</span><span class="sxs-lookup"><span data-stu-id="bce0b-119">Previously, when you ran an ER configuration, a message box appeared that required user action to save or open a file.</span></span> <span data-ttu-id="bce0b-120">Agora é possível pré-configurar um destino para cada configuração de formato e para cada componente de saída (uma pasta ou um arquivo) separadamente.</span><span class="sxs-lookup"><span data-stu-id="bce0b-120">You can now pre-configure a destination for each format configuration and for each output component (a folder or a file) separately.</span></span> <span data-ttu-id="bce0b-121">Os usuários que têm direitos de acesso apropriados também podem modificar as configurações de destino em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="bce0b-121">Users who have appropriate access rights can also modify destination settings at run time.</span></span> |

## <a name="pos--microsoft-dynamics-ax-retail"></a><span data-ttu-id="bce0b-122">POS – Microsoft Dynamics AX Retail</span><span class="sxs-lookup"><span data-stu-id="bce0b-122">POS – Microsoft Dynamics AX Retail</span></span>

| <span data-ttu-id="bce0b-123">O que você pode fazer?</span><span class="sxs-lookup"><span data-stu-id="bce0b-123">What can you do?</span></span> | <span data-ttu-id="bce0b-124">Por que isso é importante?</span><span class="sxs-lookup"><span data-stu-id="bce0b-124">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="bce0b-125">Use o navegador Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="bce0b-125">Use the Google Chrome browser.</span></span> | <span data-ttu-id="bce0b-126">Os varejistas agora podem iniciar o Cloud POS através do navegador Chrome, podendo desfrutar de todas as funcionalidades disponíveis nas versões do Microsoft Edge e Internet Explorer do Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="bce0b-126">Retailers can now start Cloud POS from the Chrome browser, and can experience all the functionality that is available in the Microsoft Edge and Internet Explorer version of Cloud POS.</span></span> |

## <a name="financial-reporting"></a><span data-ttu-id="bce0b-127">Relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="bce0b-127">Financial reporting</span></span>

| <span data-ttu-id="bce0b-128">O que você pode fazer?</span><span class="sxs-lookup"><span data-stu-id="bce0b-128">What can you do?</span></span> | <span data-ttu-id="bce0b-129">Por que isso é importante?</span><span class="sxs-lookup"><span data-stu-id="bce0b-129">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="bce0b-130">Reconstrua o mercado de dados de Relatórios financeiros.</span><span class="sxs-lookup"><span data-stu-id="bce0b-130">Rebuild the Financial reporting data mart.</span></span> | <span data-ttu-id="bce0b-131">Quando você move bancos de dados do Dynamics AX entre ambientes ou faz outras alterações invasivas ao ambiente, o banco de dados de relatórios financeiros pode ter que ser reconstruído.</span><span class="sxs-lookup"><span data-stu-id="bce0b-131">When you move Dynamics AX databases between environments or make other invasive changes to the environment, the Financial reporting database might have to be rebuilt.</span></span> <span data-ttu-id="bce0b-132">Um script do Windows PowerShell agora é fornecido para reconstruir o banco de dados para você.</span><span class="sxs-lookup"><span data-stu-id="bce0b-132">A Windows PowerShell script is now provided to rebuild the database for you.</span></span> |
| <span data-ttu-id="bce0b-133">Não é mais possível selecionar opções de designer de relatório que não são válidas.</span><span class="sxs-lookup"><span data-stu-id="bce0b-133">You can no longer select report designer options that aren't valid.</span></span> | <span data-ttu-id="bce0b-134">Diversas opções de designer de relatório que foram usadas nas versões de mercado do Management reporter não se aplicam a esta versão do Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="bce0b-134">Several report designer options that were used in the in-market versions of Management reporter don't apply to this version of Dynamics AX.</span></span> <span data-ttu-id="bce0b-135">Essas opções estavam relacionadas ao projeto, saída e vinculação do relatório financeiro.</span><span class="sxs-lookup"><span data-stu-id="bce0b-135">These options were related to financial report design, output, and linking.</span></span> <span data-ttu-id="bce0b-136">Essas opções foram removidas do designer de relatório financeiro para evitar erros de usuário.</span><span class="sxs-lookup"><span data-stu-id="bce0b-136">These options have been removed from the financial report designer to prevent user errors.</span></span> |

## <a name="financial-management"></a><span data-ttu-id="bce0b-137">Gerenciamento financeiro</span><span class="sxs-lookup"><span data-stu-id="bce0b-137">Financial management</span></span>

| <span data-ttu-id="bce0b-138">O que você pode fazer?</span><span class="sxs-lookup"><span data-stu-id="bce0b-138">What can you do?</span></span> | <span data-ttu-id="bce0b-139">Por que isso é importante?</span><span class="sxs-lookup"><span data-stu-id="bce0b-139">Why is this important?</span></span> |
|------------------|------------------------|
| <span data-ttu-id="bce0b-140">Gerar arquivos de pagamento positivos para pagamentos de contas a pagar.</span><span class="sxs-lookup"><span data-stu-id="bce0b-140">Generate positive pay files for accounts payable payments.</span></span> | <span data-ttu-id="bce0b-141">Arquivos de pagamento positivos podem ser gerados para ajudar a evitar fraude de cheque.</span><span class="sxs-lookup"><span data-stu-id="bce0b-141">Positive pay files can be generated to help prevent check fraud.</span></span> |

## <a name="warehouse-and-production"></a><span data-ttu-id="bce0b-142">Depósito e produção</span><span class="sxs-lookup"><span data-stu-id="bce0b-142">Warehouse and production</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="bce0b-143">O que você pode fazer?</span><span class="sxs-lookup"><span data-stu-id="bce0b-143">What can you do?</span></span></th>
<th><span data-ttu-id="bce0b-144">Por que isso é importante?</span><span class="sxs-lookup"><span data-stu-id="bce0b-144">Why is this important?</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bce0b-145">Defina uma política de trabalho do depósito que controla a criação de trabalho para um conjunto de produtos em locais específicos.</span><span class="sxs-lookup"><span data-stu-id="bce0b-145">Define a warehouse work policy that controls the creation of work for a set of products at specific locations.</span></span></td>
<td><span data-ttu-id="bce0b-146">Os processos do depósito nem sempre incluem o trabalho.</span><span class="sxs-lookup"><span data-stu-id="bce0b-146">Warehouse processes don't always include work.</span></span> <span data-ttu-id="bce0b-147">Ao usar a nova política de trabalho do depósito, você pode impedir a criação de trabalho para a separação de matéria-prima e organização de mercadorias concluídas para um conjunto de produtos em locais específicos.</span><span class="sxs-lookup"><span data-stu-id="bce0b-147">By using the new warehouse work policy, you can prevent work from being created for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bce0b-148">Especifique que um local de saída da produção não é controlado pela placa do carro.</span><span class="sxs-lookup"><span data-stu-id="bce0b-148">Specify that a production output location isn't license plate–controlled.</span></span></td>
<td><span data-ttu-id="bce0b-149">Agora é possível especificar que um local de saída da produção não é controlado pela placa do carro.</span><span class="sxs-lookup"><span data-stu-id="bce0b-149">You can now specify that a product output location isn't license plate–controlled.</span></span> <span data-ttu-id="bce0b-150">Por exemplo, esse recurso é útil quando uma ordem de produção reversa relata itens como concluídos diretamente para um local que atua como um local de entrada de produção para uma ordem de produção direta.</span><span class="sxs-lookup"><span data-stu-id="bce0b-150">For example, this feature is useful when an upstream production order reports items as finished directly to a location that acts as production input location for a downstream production order.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bce0b-151">Suporte para BOMs que incluem itens com dimensões de produto diferentes para o mesmo item.</span><span class="sxs-lookup"><span data-stu-id="bce0b-151">Support BOMs that include items with different product dimensions of the same item.</span></span></td>
<td><span data-ttu-id="bce0b-152">Ao usar uma ou várias dimensões de produto na produção, podem ocorrer situações onde você gostaria de produzir um item, com base em uma variante diferente do mesmo item.</span><span class="sxs-lookup"><span data-stu-id="bce0b-152">When using one or multiple of the product dimensions in production, you can have situations where you would like to produce an item, based on a different variant of the same item.</span></span> <span data-ttu-id="bce0b-153">Para obter mais informações, acesse <a href="https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/">esse blog</a>.</span><span class="sxs-lookup"><span data-stu-id="bce0b-153">For more information, see <a href="https://blogs.msdn.microsoft.com/axmfg/2015/12/22/support-for-boms-that-includes-items-with-different-product-dimensions-of-the-same-item/">this blog</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bce0b-154">Ordens de produção com estruturas circulares no primeiro nível das suas BOMs são excluídas do cálculo de nível da BOM para o planejamento de recursos materiais.</span><span class="sxs-lookup"><span data-stu-id="bce0b-154">Production orders with circular structures at the first level of their BOMs are excluded from BOM level calculation for material resource planning.</span></span></td>
<td><span data-ttu-id="bce0b-155">Não é possível atribuir níveis corretos da BOM para variantes de produto em ordens de produção que causam circularidade na hierarquia da BOM.</span><span class="sxs-lookup"><span data-stu-id="bce0b-155">It is not possible to assign correct BOM levels to product variants for production orders that cause circularity in the BOM hierarchy.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bce0b-156">Calcule níveis da BOM separados para o planejamento de recursos materiais e cálculo de custo:</span><span class="sxs-lookup"><span data-stu-id="bce0b-156">Calculate separate BOM levels for material resource planning and cost calculation:</span></span>
<ul>
<li><span data-ttu-id="bce0b-157">Para o planejamento de recursos materiais, os níveis da BOM são calculados na nova tabela <strong>ReqItemLevel</strong>.</span><span class="sxs-lookup"><span data-stu-id="bce0b-157">For material resource planning, BOM levels are calculated in the new <strong>ReqItemLevel</strong> table.</span></span> <span data-ttu-id="bce0b-158">Ordens de produção finalizadas são ignoradas no cálculo.</span><span class="sxs-lookup"><span data-stu-id="bce0b-158">Ended production orders are ignored in the calculation.</span></span></li>
<li><span data-ttu-id="bce0b-159">Para o cálculo do custo de produção, os níveis da BOM são calculados em <strong>InventTable</strong>.</span><span class="sxs-lookup"><span data-stu-id="bce0b-159">For production cost calculation, BOM levels are calculated in the <strong>InventTable</strong>.</span></span> <span data-ttu-id="bce0b-160">Ordens de produção finalizadas são incluídas no cálculo.</span><span class="sxs-lookup"><span data-stu-id="bce0b-160">Ended production orders are included in the calculation.</span></span></li>
</ul>
</td>
<td>
<ul>
<li><span data-ttu-id="bce0b-161">Ao executar o planejamento de recurso material, por exemplo, explosão e agendamento do plano de planejamento mestre, somente os níveis da BOM usados no planejamento de recurso material precisam ser recalculados.</span><span class="sxs-lookup"><span data-stu-id="bce0b-161">When running material resource planning, for example, master planning plan scheduling and explosion, only BOM levels used for material resource planning need to be recalculated.</span></span> <span data-ttu-id="bce0b-162">Em outras palavras, não é necessário calcular níveis da BOM usados no cálculo de custos de produção.</span><span class="sxs-lookup"><span data-stu-id="bce0b-162">In other words, there is no need to calculate BOM levels used for production costing calculation.</span></span></li>
<li><span data-ttu-id="bce0b-163">Ao executar operações de custos, por exemplo, fechamento de estoque, somente os níveis da BOM usados no cálculo de custos de produção precisam ser recalculados.</span><span class="sxs-lookup"><span data-stu-id="bce0b-163">When running costing operations, for example, inventory closing, only BOM levels used for production costing calculation need to be recalculated.</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="bce0b-164">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bce0b-164">Additional resources</span></span>

[<span data-ttu-id="bce0b-165">Novidades ou alterações</span><span class="sxs-lookup"><span data-stu-id="bce0b-165">What's new or changed</span></span>](whats-new-changed.md)

[<span data-ttu-id="bce0b-166">Guias de tarefas novos ou atualizados (maio de 2016)</span><span class="sxs-lookup"><span data-stu-id="bce0b-166">New or updated task guides (May 2016)</span></span>](new-updated-task-guides-available-may-2016.md)
