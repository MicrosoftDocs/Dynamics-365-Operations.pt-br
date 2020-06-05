---
title: Habilitar a impressão da etiqueta da placa de licença
description: Este tópico mostra como habilitar a impressão automática de um rótulo (SSCC) do código de série do contêiner de remessa depois que o último item for separado do estoque em um processo de trabalho de separação de vendas.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 43dc913e84fa53179855d7ab8dbbf4d179e2cc63
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383035"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="2f0aa-103">Habilitar a impressão da etiqueta da placa de licença</span><span class="sxs-lookup"><span data-stu-id="2f0aa-103">Enable license plate label printing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2f0aa-104">Este tópico mostra como habilitar a impressão automática de um rótulo (SSCC) do código de série do contêiner de remessa depois que o último item for separado do estoque em um processo de trabalho de separação de vendas.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-104">This topic shows how to enable the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="2f0aa-105">Você pode executar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="2f0aa-106">Se sua execução está usando seus próprios dados, você precisa ter uma sequência numérica configurada para matrículas.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-106">If you're run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="2f0aa-107">Será preciso configurar uma impressora de rótulo antes de iniciar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="2f0aa-108">Ir para Administração de organização > Configuração > Impressoras de rede.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="2f0aa-109">No Painel de Ações, clique em Opções, depois clique no botão de instalação de download do agente de roteiro do documento.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-109">On the Action Pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="2f0aa-110">Execute o instalador e verifique se você tem uma impressora de rede trabalhando definida como ativa antes de continuar com o procedimento.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="2f0aa-111">Configurar o prefixo da empresa GS1</span><span class="sxs-lookup"><span data-stu-id="2f0aa-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="2f0aa-112">Vá para **Painel de navegação > Módulos > Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-112">Go to **Navigation pane > Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="2f0aa-113">No campo **prefixo da empresa GS1**, insira os 7 números da empresa GS1.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-113">In the **GS1 company prefix** field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="2f0aa-114">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-114">Select **Save**.</span></span>
4. <span data-ttu-id="2f0aa-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="2f0aa-116">Configuração da sequência numérica de matrícula de SSCC</span><span class="sxs-lookup"><span data-stu-id="2f0aa-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="2f0aa-117">Vá para **Painel de navegação > Módulos > Administração da organização > Sequências numéricas > Sequências numéricas**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-117">Go to **Navigation pane > Modules > Organization administration > Number sequences > Number sequences**.</span></span>
2. <span data-ttu-id="2f0aa-118">No campo **Área**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-118">In the **Area** field, select an option.</span></span>
3. <span data-ttu-id="2f0aa-119">No campo **Referência**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-119">In the **Reference** field, select an option.</span></span>
4. <span data-ttu-id="2f0aa-120">No campo **Empresa**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-120">In the **Company** field, type a value.</span></span>
5. <span data-ttu-id="2f0aa-121">Expanda a seção **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-121">Expand the **Segments** section.</span></span>
6. <span data-ttu-id="2f0aa-122">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-122">Select **Edit**.</span></span>
7. <span data-ttu-id="2f0aa-123">Na tabela **Segmentos**, selecione a primeira linha</span><span class="sxs-lookup"><span data-stu-id="2f0aa-123">In the **Segments** table, select the first row</span></span>
8. <span data-ttu-id="2f0aa-124">Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-124">Select **Remove**.</span></span>
9. <span data-ttu-id="2f0aa-125">Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-125">Select **Remove**.</span></span>
10. <span data-ttu-id="2f0aa-126">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-126">Select **Save**.</span></span>
11. <span data-ttu-id="2f0aa-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-127">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="2f0aa-128">Crie o layout de roteiro do documento</span><span class="sxs-lookup"><span data-stu-id="2f0aa-128">Create the document route layout</span></span>
1. <span data-ttu-id="2f0aa-129">Vá para **painel de Navegação > Módulos > Gerenciamento de depósito > Configuração > Roteamento de documentos > Layouts de roteamento de documentos**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-129">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing layouts**.</span></span> <span data-ttu-id="2f0aa-130">Habilitar o layout SSCC.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-130">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="2f0aa-131">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-131">Select **New**.</span></span>
3. <span data-ttu-id="2f0aa-132">No campo **ID de Layout**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-132">In the **Layout ID** field, type a value.</span></span>
4. <span data-ttu-id="2f0aa-133">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-133">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="2f0aa-134">Selecione **Inserir no final do texto**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-134">Select **Insert at end of text**.</span></span>
6. <span data-ttu-id="2f0aa-135">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-135">Select **Save**.</span></span>
7. <span data-ttu-id="2f0aa-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-136">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="2f0aa-137">Configurar o roteamento de documentos</span><span class="sxs-lookup"><span data-stu-id="2f0aa-137">Set up the document routing</span></span>
1. <span data-ttu-id="2f0aa-138">Vá para **painel de Navegação > Módulos > Gerenciamento de depósito > Configuração > Roteamento de documentos > Roteamento de documentos**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-138">Go to **Navigation pane > Modules > Warehouse management > Setup > Document routing > Document routing**.</span></span>
2. <span data-ttu-id="2f0aa-139">No campo **Tipo de ordem de serviço**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-139">In the **Work order type** field, select an option.</span></span>
3. <span data-ttu-id="2f0aa-140">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-140">Select **New**.</span></span>
4. <span data-ttu-id="2f0aa-141">No campo **Depósito**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-141">In the **Warehouse** field, type a value.</span></span>
5. <span data-ttu-id="2f0aa-142">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-142">In the **Name** field, type a value.</span></span>
6. <span data-ttu-id="2f0aa-143">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-143">Select **New**.</span></span>
7. <span data-ttu-id="2f0aa-144">No campo **ID do Layout**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-144">In the **Layout ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="2f0aa-145">No campo **Nome**, digite o nome da impressora que você quer usar.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-145">In the **Name** field, enter the printer name that you want to use.</span></span>
9. <span data-ttu-id="2f0aa-146">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-146">Select **Save**.</span></span>
10. <span data-ttu-id="2f0aa-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-147">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="2f0aa-148">Criar o menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="2f0aa-148">Create mobile device menu</span></span>
1. <span data-ttu-id="2f0aa-149">Vá para **Painel de navegação > Módulos > Gerenciamento de depósito > Configuração > Dispositivo móvel > Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-149">Go to **Navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="2f0aa-150">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-150">Select **New**.</span></span>
3. <span data-ttu-id="2f0aa-151">No campo **Nome do item de menu**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-151">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="2f0aa-152">No campo **Título**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-152">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="2f0aa-153">No campo **Modo**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-153">In the **Mode** field, select an option.</span></span>
6. <span data-ttu-id="2f0aa-154">Selecione **Sim** no campo **Usar trabalho existente**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-154">Select **Yes** in the **Use existing work** field.</span></span>
7. <span data-ttu-id="2f0aa-155">Selecione **Sim** no campo **Gerar placa de licença**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-155">Select **Yes** in the **Generate license plate** field.</span></span>
8. <span data-ttu-id="2f0aa-156">Expanda a seção **Classes de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-156">Expand the **Work classes** section.</span></span>
9. <span data-ttu-id="2f0aa-157">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-157">Select **New**.</span></span>
10. <span data-ttu-id="2f0aa-158">No campo **ID da classe de trabalho**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-158">In the **Work class ID** field, type a value.</span></span>
11. <span data-ttu-id="2f0aa-159">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-159">Select **Save**.</span></span>
12. <span data-ttu-id="2f0aa-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-160">Close the page.</span></span>
13. <span data-ttu-id="2f0aa-161">Vá para **painel de navegação > Módulos > Gerenciamento de depósito > Configuração > Dispositivo móvel > Menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-161">Go to **navigation pane > Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
14. <span data-ttu-id="2f0aa-162">Na árvore, selecione o item de menu que você criou antes.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-162">In the tree, select the menu item that you created before.</span></span>
15. <span data-ttu-id="2f0aa-163">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-163">Select **Edit**.</span></span>
16. <span data-ttu-id="2f0aa-164">Selecione a seta para adicionar o item de menu ao menu.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-164">Select the arrow to add the menu item to the menu.</span></span>
17. <span data-ttu-id="2f0aa-165">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-165">Select **Save**.</span></span>
18. <span data-ttu-id="2f0aa-166">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-166">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="2f0aa-167">Atualizar um modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="2f0aa-167">Update a work template</span></span>
1. <span data-ttu-id="2f0aa-168">Vá para **Painel de navegação > Módulos > Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-168">Go to **Navigation pane > Modules > Warehouse management > Setup > Work > Work templates**.</span></span>
2. <span data-ttu-id="2f0aa-169">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-169">Select **Edit**.</span></span>
3. <span data-ttu-id="2f0aa-170">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-170">Select **New**.</span></span>
4. <span data-ttu-id="2f0aa-171">No campo **Tipo de trabalho**, selecione **Imprimir**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-171">In the **Work type** field, select **Print**.</span></span>
5. <span data-ttu-id="2f0aa-172">No campo **ID da classe de trabalho**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-172">In the **Work class ID** field, enter or select a value.</span></span>
6. <span data-ttu-id="2f0aa-173">Selecione **Mover para cima**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-173">Select **Move up**.</span></span>
7. <span data-ttu-id="2f0aa-174">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-174">Select **Save**.</span></span>
8. <span data-ttu-id="2f0aa-175">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-175">Close the page.</span></span>

