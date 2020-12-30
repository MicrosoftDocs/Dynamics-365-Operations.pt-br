---
title: ER Atualize seu formato adotando uma nova versão com base nesse formato
description: As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode manter uma configuração de formato de Relatório eletrônico (RE).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 17fe6d772040c73959685920743225c128421951
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684250"
---
# <a name="er-upgrade-your-format-by-adopting-a-new-base-version-of-that-format"></a><span data-ttu-id="ac65a-103">ER Atualize seu formato adotando uma nova versão com base nesse formato</span><span class="sxs-lookup"><span data-stu-id="ac65a-103">ER Upgrade your format by adopting a new, base version of that format</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ac65a-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode manter uma configuração de formato de Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="ac65a-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can maintain an Electronic reporting (ER) format configuration.</span></span> <span data-ttu-id="ac65a-105">Este processo explica como uma versão personalizada de um formato pode ser criada com base no formato recebido de um fornecedor de configuração (CP).</span><span class="sxs-lookup"><span data-stu-id="ac65a-105">This procedure explains how a custom version of a format can be created based on the format received from a configuration provider (CP).</span></span> <span data-ttu-id="ac65a-106">Também explica como adotar uma nova versão de base desse formato.</span><span class="sxs-lookup"><span data-stu-id="ac65a-106">It also explains how to adopt a new, base version of that format.</span></span>

<span data-ttu-id="ac65a-107">Para executar estas etapas, primeiro você deve concluir as etapas "Criar um provedor de configuração e marcá-lo como ativo" e procedimentos "Usar o formato criado para gerar documentos eletrônicos para os pagamentos".</span><span class="sxs-lookup"><span data-stu-id="ac65a-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" and "Use created format to generate electronic documents for payments" procedures.</span></span> <span data-ttu-id="ac65a-108">Essas etapas podem ser executadas na empresa GBSI.</span><span class="sxs-lookup"><span data-stu-id="ac65a-108">These steps can be performed in the GBSI company.</span></span>

## <a name="select-format-configuration-for-customization"></a><span data-ttu-id="ac65a-109">Selecione a configuração de formato para a personalização</span><span class="sxs-lookup"><span data-stu-id="ac65a-109">Select format configuration for customization</span></span>
1. <span data-ttu-id="ac65a-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ac65a-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="ac65a-111">Neste exemplo, a empresa exemplo, Litware, Inc. (https://www.litware.com), atuará como um provedor de configuração que oferece suporte a configurações de formato para pagamentos eletrônicos de um país específico.</span><span class="sxs-lookup"><span data-stu-id="ac65a-111">In this example, sample company Litware, Inc. (https://www.litware.com) will act as a configuration provider that supports format configurations for electronic payments for a particular country.</span></span>    <span data-ttu-id="ac65a-112">A empresa exemplo, Proseware, Inc (http://www.proseware.com), atuará como um consumidor da configuração do formato fornecida pela Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="ac65a-112">Sample company Proseware, Inc. (http://www.proseware.com) will act as a consumer of the format configuration that Litware, Inc. provided.</span></span> <span data-ttu-id="ac65a-113">A Proseware, Inc. usa formatos em determinadas regiões desse país.</span><span class="sxs-lookup"><span data-stu-id="ac65a-113">Proseware, Inc. uses formats in certain regions of that country.</span></span>  
2. <span data-ttu-id="ac65a-114">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ac65a-114">Click Reporting configurations.</span></span>
3. <span data-ttu-id="ac65a-115">Clique em Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="ac65a-115">Click Show filters.</span></span>
4. <span data-ttu-id="ac65a-116">Aplique os seguintes filtros: insira um valor de filtro de "BACS (fictício do Reino Unido)", no campo "Nome" usando o operador de filtro "começa com".</span><span class="sxs-lookup"><span data-stu-id="ac65a-116">Apply the following filters: Enter a filter value of "BACS (UK fictitious)" on the "Name" field using the "begins with" filter operator.</span></span>
  
    <span data-ttu-id="ac65a-117">A configuração de formato selecionada BACS (fictício do Reino Unido) pertence ao fornecedor Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="ac65a-117">The selected format configuration BACS (UK fictitious) is owned by provider Litware, Inc.</span></span>  

5. <span data-ttu-id="ac65a-118">Clique em Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="ac65a-118">Click Show filters.</span></span>
6. <span data-ttu-id="ac65a-119">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ac65a-119">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="ac65a-120">A versão do formato com o status de Concluído será usada pela Proseware, Inc. para personalização.</span><span class="sxs-lookup"><span data-stu-id="ac65a-120">The version of the format with the status of Completed will be used by Proseware, Inc. for customization.</span></span>  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a><span data-ttu-id="ac65a-121">Crie uma nova configuração para o formato de documento personalizado eletrônico</span><span class="sxs-lookup"><span data-stu-id="ac65a-121">Create a new configuration for your custom format of electronic document</span></span>
<span data-ttu-id="ac65a-122">A Proseware, Inc. recebeu a configuração da versão 1.1 de BACS (fictício do Reino Unido) que contém o formato inicial para gerar documentos de pagamento eletrônico da Litware, Inc. em conformidade com a subscrição de serviço.</span><span class="sxs-lookup"><span data-stu-id="ac65a-122">Proseware, Inc. received version 1.1 of BACS (UK fictitious) configuration that contains the initial format to generate electronic payment documents from Litware, Inc. in accordance to their service subscription.</span></span> <span data-ttu-id="ac65a-123">A Proseware, Inc. deseja começar a usá-la como um padrão para seu país, mas algumas personalizações são necessárias para oferecer suporte a requisitos regionais específicos.</span><span class="sxs-lookup"><span data-stu-id="ac65a-123">Proseware, Inc. wants to start using this as a standard for their country but some customization is required to support specific regional requirements.</span></span> <span data-ttu-id="ac65a-124">A Proseware, Inc. também deseja manter a capacidade de atualizar um formato personalizado assim que uma nova versão dele (com alterações para oferecer suporte a novos requisitos específicos do país) venha da Litware, Inc. e desejam fazer essa atualização com o menor custo possível.</span><span class="sxs-lookup"><span data-stu-id="ac65a-124">Proseware, Inc. also wants to keep the ability to upgrade a custom format as soon as a new version of it (with changes to support new country-specific requirements) comes from Litware, Inc. and they want to perform this upgrade with the lowest cost.</span></span>  

<span data-ttu-id="ac65a-125">Para isso, a Proseware, Inc. precisa criar uma configuração usando configuração BACS (fictício do Reino Unido) da Litware, Inc. como base.</span><span class="sxs-lookup"><span data-stu-id="ac65a-125">To do this, Proseware, Inc. needs to create a configuration using the Litware, Inc. configuration BACS (UK fictitious) as a base.</span></span>  

1. <span data-ttu-id="ac65a-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ac65a-126">Close the page.</span></span>
2. <span data-ttu-id="ac65a-127">Selecione a Proseware, Inc. para torná-la um provedor ativo.</span><span class="sxs-lookup"><span data-stu-id="ac65a-127">Select Proseware, Inc. to make it an active provider.</span></span>
3. <span data-ttu-id="ac65a-128">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="ac65a-128">Click Set active.</span></span>
4. <span data-ttu-id="ac65a-129">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ac65a-129">Click Reporting configurations.</span></span>
5. <span data-ttu-id="ac65a-130">Na árvore, expanda "Pagamentos (modelo simplificado)".</span><span class="sxs-lookup"><span data-stu-id="ac65a-130">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="ac65a-131">Na árvore, selecione "Pagamentos (modelo simplificado)\BACS (Reino Unido fictício)".</span><span class="sxs-lookup"><span data-stu-id="ac65a-131">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="ac65a-132">Selecione a configuração BACS (fictício do Reino Unido) da Litware, Inc. A Proseware, Inc. usará a versão 1.1 como uma base para a versão personalizada.</span><span class="sxs-lookup"><span data-stu-id="ac65a-132">Select the BACS (UK fictitious) configuration from Litware, Inc. Proseware, Inc. will use version 1.1 as a base for the custom version.</span></span>  

7. <span data-ttu-id="ac65a-133">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ac65a-133">Click Create configuration to open the drop dialog.</span></span>

    <span data-ttu-id="ac65a-134">Isso permite criar uma nova configuração para um formato de pagamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="ac65a-134">This lets you create a new configuration for a custom payment format.</span></span>  

8. <span data-ttu-id="ac65a-135">No campo Novo, insira "Derivar do Nome: BACS (fictício do Reino Unido), Litware, Inc.'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-135">In the New field, enter 'Derive from Name: BACS (UK fictitious), Litware, Inc.'.</span></span>

    <span data-ttu-id="ac65a-136">Selecione Opção de derivação para confirmar o uso de BACS (fictício do Reino Unido) como base para criar a versão personalizada.</span><span class="sxs-lookup"><span data-stu-id="ac65a-136">Select the Derive option to confirm the usage of BACS (UK fictitious) as the base for creating the custom version.</span></span>  

9. <span data-ttu-id="ac65a-137">No campo Nome, digite 'BACS (Reino Unido personalizado)'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-137">In the Name field, type 'BACS (UK fictitious custom)'.</span></span>
10. <span data-ttu-id="ac65a-138">No campo Descrição, digite "Formato de pagamento de fornecedor BACS (personalizado fictício do Reino Unido)".</span><span class="sxs-lookup"><span data-stu-id="ac65a-138">In the Description field, type 'BACS vendor payment (UK fictitious custom)'.</span></span>

    <span data-ttu-id="ac65a-139">O provedor de configuração ativo (Proseware, Inc.) é automaticamente inserido aqui.</span><span class="sxs-lookup"><span data-stu-id="ac65a-139">The active configuration provider (Proseware, Inc.) is automatically entered here.</span></span> <span data-ttu-id="ac65a-140">Este provedor será capaz de manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="ac65a-140">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="ac65a-141">Outros provedores podem usar esta configuração, mas não poderão mantê-la.</span><span class="sxs-lookup"><span data-stu-id="ac65a-141">Other providers can use this configuration, but will not be able to maintain it.</span></span>  

11. <span data-ttu-id="ac65a-142">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="ac65a-142">Click Create configuration.</span></span>

## <a name="customize-your-format-for-the-electronic-document"></a><span data-ttu-id="ac65a-143">Personalizar o formato do documento eletrônico</span><span class="sxs-lookup"><span data-stu-id="ac65a-143">Customize your format for the electronic document</span></span>
1. <span data-ttu-id="ac65a-144">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="ac65a-144">Click Designer.</span></span>
2. <span data-ttu-id="ac65a-145">Clique em Expandir/recolher.</span><span class="sxs-lookup"><span data-stu-id="ac65a-145">Click Expand/collapse.</span></span>
3. <span data-ttu-id="ac65a-146">Clique em Expandir/recolher.</span><span class="sxs-lookup"><span data-stu-id="ac65a-146">Click Expand/collapse.</span></span>
4. <span data-ttu-id="ac65a-147">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco".</span><span class="sxs-lookup"><span data-stu-id="ac65a-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="ac65a-148">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ac65a-148">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="ac65a-149">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-149">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="ac65a-150">No campo Nome, digite 'IBAN'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-150">In the Name field, type 'IBAN'.</span></span>
8. <span data-ttu-id="ac65a-151">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ac65a-151">Click OK.</span></span>
9. <span data-ttu-id="ac65a-152">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\IBAN".</span><span class="sxs-lookup"><span data-stu-id="ac65a-152">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\IBAN'.</span></span>
10. <span data-ttu-id="ac65a-153">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ac65a-153">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="ac65a-154">Na árvore, selecione 'Texto\Cadeia de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-154">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="ac65a-155">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ac65a-155">Click OK.</span></span>
13. <span data-ttu-id="ac65a-156">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Nome\String".</span><span class="sxs-lookup"><span data-stu-id="ac65a-156">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="ac65a-157">No campo Comprimento máximo, insira "60".</span><span class="sxs-lookup"><span data-stu-id="ac65a-157">In the Maximum length field, enter '60'.</span></span>
15. <span data-ttu-id="ac65a-158">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="ac65a-158">Click the Mapping tab.</span></span>
16. <span data-ttu-id="ac65a-159">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-159">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="ac65a-160">Na árvore, expanda 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-160">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="ac65a-161">Na árvore, expanda 'modelo\Pagamentos\Credor'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-161">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="ac65a-162">Na árvore, expanda 'modelo\Pagamentos\Credor\Conta'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-162">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
20. <span data-ttu-id="ac65a-163">Na árvore, selecione "modelo\Pagamentos\Credor\Conta\IBAN".</span><span class="sxs-lookup"><span data-stu-id="ac65a-163">In the tree, select 'model\Payments\Creditor\Account\IBAN'.</span></span>
21. <span data-ttu-id="ac65a-164">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item = modelo.Pagamentos\Fornecedor\Banco\IBAN\String".</span><span class="sxs-lookup"><span data-stu-id="ac65a-164">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\IBAN\String'.</span></span>
22. <span data-ttu-id="ac65a-165">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ac65a-165">Click Bind.</span></span>
23. <span data-ttu-id="ac65a-166">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ac65a-166">Click Save.</span></span>

## <a name="validate-the-customized-format"></a><span data-ttu-id="ac65a-167">Validar o formato personalizado</span><span class="sxs-lookup"><span data-stu-id="ac65a-167">Validate the customized format</span></span>
1. <span data-ttu-id="ac65a-168">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="ac65a-168">Click Validate.</span></span>

    <span data-ttu-id="ac65a-169">Valide o layout do formato personalizado e as alterações de projeção de dados para garantir que todas as associações são aprovadas.</span><span class="sxs-lookup"><span data-stu-id="ac65a-169">Validate the customized format layout and data mapping changes to make sure that all bindings are okay.</span></span>  

2. <span data-ttu-id="ac65a-170">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ac65a-170">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a><span data-ttu-id="ac65a-171">Alterar o status da versão atual da configuração de formato personalizado</span><span class="sxs-lookup"><span data-stu-id="ac65a-171">Change the status of the current version of the custom format configuration</span></span>
<span data-ttu-id="ac65a-172">Altere o status da configuração do formato criado de Rascunho para Concluído para torná-lo disponível e gerar documentação de pagamento.</span><span class="sxs-lookup"><span data-stu-id="ac65a-172">Change the status of the designed format configuration from Draft to Completed to make it available for payment document generation.</span></span>  

1. <span data-ttu-id="ac65a-173">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="ac65a-173">Click Change status.</span></span>

    <span data-ttu-id="ac65a-174">Observe que a versão atual da configuração selecionada está no status Rascunho.</span><span class="sxs-lookup"><span data-stu-id="ac65a-174">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="ac65a-175">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="ac65a-175">Click Complete.</span></span>
3. <span data-ttu-id="ac65a-176">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ac65a-176">In the Description field, type a value.</span></span>
4. <span data-ttu-id="ac65a-177">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ac65a-177">Click OK.</span></span>
5. <span data-ttu-id="ac65a-178">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ac65a-178">In the list, find and select the desired record.</span></span>

    <span data-ttu-id="ac65a-179">Observe que a configuração criada será salva como versão 1.1.1 concluída.</span><span class="sxs-lookup"><span data-stu-id="ac65a-179">Note that the created configuration is saved as completed version 1.1.1.</span></span> <span data-ttu-id="ac65a-180">Isso significa que é a versão 1 do formato de costume BACS (personalizado fictício do Reino Unido), que se baseia na versão 1 do formato de BACS (fictício do Reino Unido), que se baseia na versão 1 do modelo de dados de pagamentos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="ac65a-180">This means it is version 1 of the custom BACS (UK fictitious custom) format, which is based on version 1 of the BACS (UK fictitious) format, which is based on version 1 of the Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-to-generate-payment-files"></a><span data-ttu-id="ac65a-181">Testar o formato personalizado para gerar arquivos de pagamento</span><span class="sxs-lookup"><span data-stu-id="ac65a-181">Test the customized format to generate payment files</span></span>
<span data-ttu-id="ac65a-182">Conclua as etapas no procedimento "Usar formato criado para gerar documentos eletrônicos para pagamentos" em uma sessão do Finance and Operations paralela.</span><span class="sxs-lookup"><span data-stu-id="ac65a-182">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in a parallel Finance and Operations session.</span></span> <span data-ttu-id="ac65a-183">Selecione o formato BACS (personalizado fictício do Reino Unido) nos parâmetros de método de pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ac65a-183">Select the BACS (UK fictitious custom) format in electronic payment method parameters.</span></span> <span data-ttu-id="ac65a-184">Verifique se o arquivo de pagamento criado contém o nó recentemente introduzido ao XML que apresenta o código de IBAN no acordo das exigências regionais.</span><span class="sxs-lookup"><span data-stu-id="ac65a-184">Make sure that the created payment file contains the recently introduced XML node presenting IBAN code in accordance to regional requirements.</span></span>  

## <a name="update-the-existing-country-specific-configuration"></a><span data-ttu-id="ac65a-185">Atualizar a configuração específica existente do país</span><span class="sxs-lookup"><span data-stu-id="ac65a-185">Update the existing country-specific configuration</span></span>
<span data-ttu-id="ac65a-186">A Litware, Inc. precisa atualizar a configuração BACS (fictício do Reino Unido) e adotar novos requisitos de país para o gerenciamento do formato do documento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ac65a-186">Litware, Inc. needs to update the BACS (UK fictitious) configuration and adopt new country requirements for managing the format of the electronic document.</span></span> <span data-ttu-id="ac65a-187">Posteriormente, isso será incluído em uma nova versão dessa configuração que será oferecida para assinantes de serviço, incluindo Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="ac65a-187">Later, this will be enclosed in a new version of this configuration that will be offered for service subscribers, including Proseware, Inc.</span></span>  

<span data-ttu-id="ac65a-188">Nos processos relacionados de provisão de serviço reais, cada nova versão de BACS (fictício do Reino Unido) pode ser importada pela Proseware, Inc. do repositório LCS das configurações da Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="ac65a-188">In real service provision related processes, each new version of BACS (UK fictitious) can be imported by Proseware, Inc. from Litware, Inc. configurations' LCS repository.</span></span> <span data-ttu-id="ac65a-189">Nesse procedimento, simularemos isso atualizando BACS (fictício do Reino Unido) em nome de um prestador de serviço.</span><span class="sxs-lookup"><span data-stu-id="ac65a-189">In this procedure we will simulate this by updating BACS (UK fictitious) on behalf of a service provider.</span></span>  

1. <span data-ttu-id="ac65a-190">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ac65a-190">Close the page.</span></span>
2. <span data-ttu-id="ac65a-191">Selecione o fornecedor "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="ac65a-191">Select Litware, inc. provider.</span></span>
3. <span data-ttu-id="ac65a-192">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="ac65a-192">Click Set active.</span></span>
4. <span data-ttu-id="ac65a-193">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ac65a-193">Click Reporting configurations.</span></span>
5. <span data-ttu-id="ac65a-194">Na árvore, expanda "Pagamentos (modelo simplificado)".</span><span class="sxs-lookup"><span data-stu-id="ac65a-194">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="ac65a-195">Na árvore, selecione "Pagamentos (modelo simplificado)\BACS (Reino Unido fictício)".</span><span class="sxs-lookup"><span data-stu-id="ac65a-195">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>

    <span data-ttu-id="ac65a-196">A versão de rascunho de propriedade do provedor BACS (fictício do Reino Unido) da Litware, Inc. é selecionada para trazer alterações para oferecer suporte aos requisitos específicos do país.</span><span class="sxs-lookup"><span data-stu-id="ac65a-196">The draft version owned by Litware, Inc. provider BACS (UK fictitious) is selected to bring in changes to support new country-specific requirements.</span></span>  

## <a name="localize-the-base-format-of-the-electronic-document"></a><span data-ttu-id="ac65a-197">Localizar o formato base do documento eletrônico</span><span class="sxs-lookup"><span data-stu-id="ac65a-197">Localize the base format of the electronic document</span></span>
<span data-ttu-id="ac65a-198">Suponha que haja novos requisitos específicos de país a serem suportados pela Litware, Inc.:</span><span class="sxs-lookup"><span data-stu-id="ac65a-198">Assume that there are new country-specific requirements to be supported by Litware, Inc.:</span></span>  

- <span data-ttu-id="ac65a-199">Um valor para o código SWIFT do banco credor em cada transação de pagamento.</span><span class="sxs-lookup"><span data-stu-id="ac65a-199">A value for the creditor's bank SWIFT code in each payment transaction.</span></span>
- <span data-ttu-id="ac65a-200">Um limite de 100 caracteres para o comprimento do texto para o nome do fornecedor no arquivo de geração.</span><span class="sxs-lookup"><span data-stu-id="ac65a-200">A limit of 100 characters for the length of text for the vendor's name in a generating file.</span></span>  
- <span data-ttu-id="ac65a-201">Novos requisitos específicos do país</span><span class="sxs-lookup"><span data-stu-id="ac65a-201">New country-specific requirements</span></span>  
- <span data-ttu-id="ac65a-202">Selecione a versão de rascunho de configuração selecionada para apresentar alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="ac65a-202">Select the draft version of the desired configuration to introduce required changes.</span></span>  


1. <span data-ttu-id="ac65a-203">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="ac65a-203">Click Designer.</span></span>
2. <span data-ttu-id="ac65a-204">Clique em Expandir/recolher.</span><span class="sxs-lookup"><span data-stu-id="ac65a-204">Click Expand/collapse.</span></span>
3. <span data-ttu-id="ac65a-205">Clique em Expandir/recolher.</span><span class="sxs-lookup"><span data-stu-id="ac65a-205">Click Expand/collapse.</span></span>
4. <span data-ttu-id="ac65a-206">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco".</span><span class="sxs-lookup"><span data-stu-id="ac65a-206">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
5. <span data-ttu-id="ac65a-207">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ac65a-207">Click Add to open the drop dialog.</span></span>
6. <span data-ttu-id="ac65a-208">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-208">In the tree, select 'XML\Element'.</span></span>
7. <span data-ttu-id="ac65a-209">No campo Nome, digite 'SWIFT'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-209">In the Name field, type 'SWIFT'.</span></span>
8. <span data-ttu-id="ac65a-210">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ac65a-210">Click OK.</span></span>
9. <span data-ttu-id="ac65a-211">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\SWIFT".</span><span class="sxs-lookup"><span data-stu-id="ac65a-211">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\SWIFT'.</span></span>
10. <span data-ttu-id="ac65a-212">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="ac65a-212">Click Add to open the drop dialog.</span></span>
11. <span data-ttu-id="ac65a-213">Na árvore, selecione 'Texto\Cadeia de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-213">In the tree, select 'Text\String'.</span></span>
12. <span data-ttu-id="ac65a-214">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ac65a-214">Click OK.</span></span>
13. <span data-ttu-id="ac65a-215">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Nome\String".</span><span class="sxs-lookup"><span data-stu-id="ac65a-215">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
14. <span data-ttu-id="ac65a-216">No campo Comprimento máximo, insira "100".</span><span class="sxs-lookup"><span data-stu-id="ac65a-216">In the Maximum length field, enter '100'.</span></span>
15. <span data-ttu-id="ac65a-217">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="ac65a-217">Click the Mapping tab.</span></span>
16. <span data-ttu-id="ac65a-218">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-218">In the tree, expand 'model'.</span></span>
17. <span data-ttu-id="ac65a-219">Na árvore, expanda 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-219">In the tree, expand 'model\Payments'.</span></span>
18. <span data-ttu-id="ac65a-220">Na árvore, expanda 'modelo\Pagamentos\Credor'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-220">In the tree, expand 'model\Payments\Creditor'.</span></span>
19. <span data-ttu-id="ac65a-221">Na árvore, expanda 'modelo\Pagamentos\Credor\Agente'.</span><span class="sxs-lookup"><span data-stu-id="ac65a-221">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
20. <span data-ttu-id="ac65a-222">Na árvore, selecione "modelo\Pagamentos\Credor\Agente\SWIFT".</span><span class="sxs-lookup"><span data-stu-id="ac65a-222">In the tree, select 'model\Payments\Creditor\Agent\SWIFT'.</span></span>
21. <span data-ttu-id="ac65a-223">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item = modelo.Pagamentos\Fornecedor\Banco\SWIFT\String".</span><span class="sxs-lookup"><span data-stu-id="ac65a-223">In the tree, select 'Xml\Message\Payments\Item =  model.Payments\Vendor\Bank\SWIFT\String'.</span></span>
22. <span data-ttu-id="ac65a-224">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ac65a-224">Click Bind.</span></span>
23. <span data-ttu-id="ac65a-225">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ac65a-225">Click Save.</span></span>

## <a name="validate-the-localized-format"></a><span data-ttu-id="ac65a-226">Validar o formato localizado</span><span class="sxs-lookup"><span data-stu-id="ac65a-226">Validate the localized format</span></span>
1. <span data-ttu-id="ac65a-227">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="ac65a-227">Click Validate.</span></span>
2. <span data-ttu-id="ac65a-228">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ac65a-228">Close the page.</span></span>

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a><span data-ttu-id="ac65a-229">Altere o status da versão atual da configuração do formato base</span><span class="sxs-lookup"><span data-stu-id="ac65a-229">Change the status of the current version of the base format configuration</span></span>
<span data-ttu-id="ac65a-230">Altere o status da configuração básica atualizada no formato de Rascunho para Concluído para tornar disponível a geração de documentos do pagamento e de atualizações das configurações do formato derivadas dela.</span><span class="sxs-lookup"><span data-stu-id="ac65a-230">Change the status of the updated base format configuration from Draft to Completed to make it available for generation of payment documents and updates of format configurations derived from it.</span></span>  

1. <span data-ttu-id="ac65a-231">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="ac65a-231">Click Change status.</span></span>

    <span data-ttu-id="ac65a-232">Observe que a versão atual da configuração selecionada está no status Rascunho.</span><span class="sxs-lookup"><span data-stu-id="ac65a-232">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="ac65a-233">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="ac65a-233">Click Complete.</span></span>
3. <span data-ttu-id="ac65a-234">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ac65a-234">In the Description field, type a value.</span></span>
4. <span data-ttu-id="ac65a-235">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ac65a-235">Click OK.</span></span>
5. <span data-ttu-id="ac65a-236">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ac65a-236">In the list, find and select the desired record.</span></span>

## <a name="change-the-base-version-for-the-custom-format-configuration"></a><span data-ttu-id="ac65a-237">Versão da alteração para a configuração do formato personalizado</span><span class="sxs-lookup"><span data-stu-id="ac65a-237">Change the base version for the custom format configuration</span></span>

<span data-ttu-id="ac65a-238">A Proseware, Inc. é informada que uma nova versão 1.2 da configuração BACS (fictício do Reino Unido) está disponível para gerar documentos de pagamento eletrônico de acordo com os novos requisitos específicos anunciados.</span><span class="sxs-lookup"><span data-stu-id="ac65a-238">Proseware, Inc. is informed that a new version 1.2 of BACS (UK fictitious) configuration is available to generate electronic payment documents in accordance to recently announced country-specific requirements.</span></span> <span data-ttu-id="ac65a-239">A Proseware, Inc. deseja começar a usá-la como padrão para o país.</span><span class="sxs-lookup"><span data-stu-id="ac65a-239">Proseware, Inc. wants to start using it as a standard for the country.</span></span>  

<span data-ttu-id="ac65a-240">Para isso, a Proseware, Inc. precisa alterar a versão da configuração base para a configuração personalizada BACS (Reino Unido fictício personalizado).</span><span class="sxs-lookup"><span data-stu-id="ac65a-240">To do this, Proseware, Inc. needs to change the base configuration version for the custom configuration BACS (UK fictitious custom).</span></span> <span data-ttu-id="ac65a-241">Em vez da versão 1.1 de BACS (fictício do Reino Unido) use a nova versão 1.2.</span><span class="sxs-lookup"><span data-stu-id="ac65a-241">Instead of version 1.1 of BACS (UK fictitious) use new version 1.2.</span></span>  

1. <span data-ttu-id="ac65a-242">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ac65a-242">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="ac65a-243">Selecione o provedor da Proseware, Inc. para marcá-lo como ativo.</span><span class="sxs-lookup"><span data-stu-id="ac65a-243">Select the Proseware, Inc. provider to mark it as active.</span></span>
3. <span data-ttu-id="ac65a-244">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="ac65a-244">Click Set active.</span></span>
4. <span data-ttu-id="ac65a-245">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="ac65a-245">Click Reporting configurations.</span></span>
5. <span data-ttu-id="ac65a-246">Na árvore, expanda "Pagamentos (modelo simplificado)".</span><span class="sxs-lookup"><span data-stu-id="ac65a-246">In the tree, expand 'Payments (simplified model)'.</span></span>
6. <span data-ttu-id="ac65a-247">Na árvore, expanda "Pagamentos (modelo simplificado)\BACS (Reino Unido fictício)".</span><span class="sxs-lookup"><span data-stu-id="ac65a-247">In the tree, expand 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
7. <span data-ttu-id="ac65a-248">Na árvore, selecione "Pagamentos (modelo simplificado)\BACS (Reino Unido fictício)\BACS (Reino Unido personalizado fictício)".</span><span class="sxs-lookup"><span data-stu-id="ac65a-248">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)\BACS (UK fictitious custom)'.</span></span>

    <span data-ttu-id="ac65a-249">Selecione a configuração de BACS (personalizado fictício do Reino Unido), que pertence ao Proseware, Inc.</span><span class="sxs-lookup"><span data-stu-id="ac65a-249">Select the BACS (UK fictitious custom) configuration, which is owned by Proseware, Inc.</span></span>  

    <span data-ttu-id="ac65a-250">Use a versão de rascunho de configuração selecionada para apresentar alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="ac65a-250">Use the draft version of the selected configuration to introduce required changes.</span></span>  

8. <span data-ttu-id="ac65a-251">Clique em Trocar base.</span><span class="sxs-lookup"><span data-stu-id="ac65a-251">Click Rebase.</span></span>

    <span data-ttu-id="ac65a-252">Selecione a nova versão 1.2 da configuração base a ser aplicada como uma nova base para atualização da configuração.</span><span class="sxs-lookup"><span data-stu-id="ac65a-252">Select the new version 1.2 of the base configuration to be applied as a new base for updating the configuration.</span></span>  

9. <span data-ttu-id="ac65a-253">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ac65a-253">Click OK.</span></span>

    <span data-ttu-id="ac65a-254">Observe que alguns conflitos foram descobertos entre mesclar a versão personalizada e uma nova versão base que representam as alterações do formato que não podem ser mescladas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ac65a-254">Note that some conflicts have been discovered between merging the custom version and a new base version representing some format changes that can't be merged automatically.</span></span>  

## <a name="resolve-rebase-conflicts"></a><span data-ttu-id="ac65a-255">Resolver conflitos de rebase</span><span class="sxs-lookup"><span data-stu-id="ac65a-255">Resolve rebase conflicts</span></span>
1. <span data-ttu-id="ac65a-256">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="ac65a-256">Click Designer.</span></span>
    
    <span data-ttu-id="ac65a-257">Observe que as alterações no limite do tamanho do texto do nome do fornecedor não podem ser resolvidas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ac65a-257">Note that changes to the vendor's name text length limit couldn't be resolved automatically.</span></span> <span data-ttu-id="ac65a-258">Consequentemente, é apresentado em uma lista de conflitos.</span><span class="sxs-lookup"><span data-stu-id="ac65a-258">Therefore, this is presented in a conflicts list.</span></span> <span data-ttu-id="ac65a-259">Para cada conflito do tipo Atualização, as opções a seguir estão disponíveis: – aplicar um valor de base anterior (botão no topo da grade) para trazer o valor da versão base anterior (0 em nosso caso).</span><span class="sxs-lookup"><span data-stu-id="ac65a-259">For each conflict of type Update, the following options are available:  - Apply a prior base value (button on top of the grid) to bring in the previous base version value (0 in our case).</span></span>  <span data-ttu-id="ac65a-260">- Aplicar um valor de base (botão no topo da grade) para trazer no novo valor da versão base (100 em nosso caso).</span><span class="sxs-lookup"><span data-stu-id="ac65a-260">- Apply a base value (button on top of the grid) to bring in the new base version value (100 in our case).</span></span>  <span data-ttu-id="ac65a-261">- Mantenha seu próprio valor (personalizado) (60 em nosso caso).</span><span class="sxs-lookup"><span data-stu-id="ac65a-261">- Keep your own (custom) value (60 in our case).</span></span>  <span data-ttu-id="ac65a-262">Clique em aplica o valor de base para a aplicação do limite do país específico de 100 caracteres de comprimento de texto para nomes do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="ac65a-262">Click Apply base value to apply a country-specific limit of 100 characters for vendor's name text length.</span></span>  

    <span data-ttu-id="ac65a-263">Observe que a Proseware, Inc. e a Litware, Inc. têm versões personalizadas e locais deste formato usando códigos IBAN e SWIFT com componentes relacionados que são automaticamente mesclados no formato gerenciado.</span><span class="sxs-lookup"><span data-stu-id="ac65a-263">Note that Proseware, Inc. and Litware, Inc. have custom and local versions of this format using IBAN and SWIFT codes with related components that are automatically merged in the managing format.</span></span>  

2. <span data-ttu-id="ac65a-264">Clique em Aplicar valor base.</span><span class="sxs-lookup"><span data-stu-id="ac65a-264">Click Apply base value.</span></span>

    <span data-ttu-id="ac65a-265">Clique em Aplicar o valor de base para aplicar o limite do país específico de 100 caracteres para os nomes dos fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ac65a-265">Click Apply base value to apply the country-specific limit of 100 characters for vendor names.</span></span>  

3. <span data-ttu-id="ac65a-266">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ac65a-266">Click Save.</span></span>

    <span data-ttu-id="ac65a-267">Salvar o formato removerá conflitos resolvidos da lista de conflitos.</span><span class="sxs-lookup"><span data-stu-id="ac65a-267">Saving the format will remove resolved conflicts from the conflicts list.</span></span>  

4. <span data-ttu-id="ac65a-268">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ac65a-268">Close the page.</span></span>

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a><span data-ttu-id="ac65a-269">Altere o status da versão nova da configuração do formato personalizado</span><span class="sxs-lookup"><span data-stu-id="ac65a-269">Change the status of the new version of the custom format configuration</span></span>
1. <span data-ttu-id="ac65a-270">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="ac65a-270">Click Change status.</span></span>

    <span data-ttu-id="ac65a-271">Altere o status da configuração atualizada, formato personalizado de Rascunho para Concluído.</span><span class="sxs-lookup"><span data-stu-id="ac65a-271">Change the status of the updated, custom format configuration from Draft to Completed.</span></span> <span data-ttu-id="ac65a-272">Isso criará a configuração de formato disponível para a geração de documentos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="ac65a-272">This will make the format configuration available for generating payment documents.</span></span> <span data-ttu-id="ac65a-273">Observe que a versão atual da configuração selecionada está no status Rascunho.</span><span class="sxs-lookup"><span data-stu-id="ac65a-273">Note that the current version of the selected configuration is in Draft status.</span></span>  

2. <span data-ttu-id="ac65a-274">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="ac65a-274">Click Complete.</span></span>
3. <span data-ttu-id="ac65a-275">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ac65a-275">In the Description field, type a value.</span></span>
4. <span data-ttu-id="ac65a-276">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ac65a-276">Click OK.</span></span>

    <span data-ttu-id="ac65a-277">Observe que a configuração criada é salva como uma versão completa 1.2.2: versão 2 do formato da base BACS (personalizado fictício do Reino Unido), que é baseado na versão 2 do formato da base BACS (fictício do Reino Unido), que é baseada na versão 1 do modelo de dados de Pagamentos (modelo simplificado).</span><span class="sxs-lookup"><span data-stu-id="ac65a-277">Note that the created configuration is saved as completed version 1.2.2: version 2 of base BACS (UK fictitious custom) format, which is based on version 2 of base BACS (UK fictitious) format, which is based on version 1 of Payments (simplified model) data model.</span></span>  

## <a name="test-the-customized-format-for-payment-files-generation"></a><span data-ttu-id="ac65a-278">Teste o formato personalizado para gerar arquivos de pagamento</span><span class="sxs-lookup"><span data-stu-id="ac65a-278">Test the customized format for payment files generation</span></span>
<span data-ttu-id="ac65a-279">Conclua as etapas no procedimento "Usar formato criado para gerar documentos eletrônicos para pagamentos" em uma sessão do Finance and Operations paralela.</span><span class="sxs-lookup"><span data-stu-id="ac65a-279">Complete the steps in the "Use created format to generate electronic documents for payments" procedure in parallel Finance and Operations session.</span></span> <span data-ttu-id="ac65a-280">Selecione o "Formato BACS criado (personalizado fictício do Reino Unido)" nos parâmetros de método de pagamento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ac65a-280">Select the created 'BACS (UK fictitious custom)' format in electronic payment method parameters.</span></span> <span data-ttu-id="ac65a-281">Verifique se o arquivo de pagamento criado contém o nó XML recentemente introduzido pela Proseware, Inc. que apresenta o código de conta IBAN de acordo com as exigências regionais.</span><span class="sxs-lookup"><span data-stu-id="ac65a-281">Make sure that the created payment file contains recently introduced by Proseware, Inc. XML node presenting IBAN account code in accordance to regional requirements.</span></span> <span data-ttu-id="ac65a-282">O arquivo também deve conter o nó XML introduzido recentemente pela Litware, Inc. que apresenta o código bancário SWIFT de acordo os requisitos do país.</span><span class="sxs-lookup"><span data-stu-id="ac65a-282">The file also should contain the recently introduced by Litware, Inc. XML node presenting SWIFT bank code in accordance to country requirements.</span></span>  

