---
title: Habilitar a impressão da etiqueta da placa de licença
description: Este procedimento permite a impressão automática de um rótulo (SSCC) do código de série do contêiner de remessa depois que o último item é separado do estoque em um processo de trabalho de separação de vendas.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed74806e5e037570f3ed7f59725eed494c829d34
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1847249"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="76812-103">Habilitar a impressão da etiqueta da placa de licença</span><span class="sxs-lookup"><span data-stu-id="76812-103">Enable license plate label printing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="76812-104">Este procedimento permite a impressão automática de um rótulo (SSCC) do código de série do contêiner de remessa depois que o último item é separado do estoque em um processo de trabalho de separação de vendas.</span><span class="sxs-lookup"><span data-stu-id="76812-104">This procedure enables the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="76812-105">Você pode executar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="76812-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="76812-106">Se sua execução está usando seus próprios dados, você precisa ter uma sequência numérica configurada para matrículas.</span><span class="sxs-lookup"><span data-stu-id="76812-106">If you’re run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="76812-107">Será preciso configurar uma impressora de rótulo antes de iniciar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="76812-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="76812-108">Ir para Administração de organização > Configuração > Impressoras de rede.</span><span class="sxs-lookup"><span data-stu-id="76812-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="76812-109">No painel de ações, clique em Opções, depois clique no botão de instalação de download do agente de roteiro do documento.</span><span class="sxs-lookup"><span data-stu-id="76812-109">On the Action pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="76812-110">Execute o instalador e verifique se você tem uma impressora de rede trabalhando definida como ativa antes de continuar com o procedimento.</span><span class="sxs-lookup"><span data-stu-id="76812-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="76812-111">Configurar o prefixo da empresa GS1</span><span class="sxs-lookup"><span data-stu-id="76812-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="76812-112">Vá para Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="76812-112">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="76812-113">No campo prefixo da empresa GS1, insira os 7 números do número de sua empresa GS1.</span><span class="sxs-lookup"><span data-stu-id="76812-113">In the GS1 company prefix field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="76812-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="76812-114">Click Save.</span></span>
4. <span data-ttu-id="76812-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="76812-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="76812-116">Configuração da sequência numérica de matrícula de SSCC</span><span class="sxs-lookup"><span data-stu-id="76812-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="76812-117">Vá para Administração da organização > Sequências numéricas > Sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="76812-117">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="76812-118">No campo Área, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="76812-118">In the Area field, select an option.</span></span>
3. <span data-ttu-id="76812-119">No campo Referência, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="76812-119">In the Reference field, select an option.</span></span>
4. <span data-ttu-id="76812-120">No campo Empresa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76812-120">In the Company field, type a value.</span></span>
5. <span data-ttu-id="76812-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="76812-121">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="76812-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="76812-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="76812-123">Expandir a seção Segmentos.</span><span class="sxs-lookup"><span data-stu-id="76812-123">Expand the Segments section.</span></span>
8. <span data-ttu-id="76812-124">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="76812-124">Click Edit.</span></span>
9. <span data-ttu-id="76812-125">Na tabela Segmentos, selecione a primeira linha</span><span class="sxs-lookup"><span data-stu-id="76812-125">In the Segments table, select the first row</span></span>
10. <span data-ttu-id="76812-126">Clique em Remover.</span><span class="sxs-lookup"><span data-stu-id="76812-126">Click Remove.</span></span>
11. <span data-ttu-id="76812-127">Clique em Remover.</span><span class="sxs-lookup"><span data-stu-id="76812-127">Click Remove.</span></span>
12. <span data-ttu-id="76812-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="76812-128">Click Save.</span></span>
13. <span data-ttu-id="76812-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="76812-129">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="76812-130">Crie o layout de roteiro do documento</span><span class="sxs-lookup"><span data-stu-id="76812-130">Create the document route layout</span></span>
1. <span data-ttu-id="76812-131">Vá para Gerenciamento de depósito > Configuração > Roteiro de documento > Layouts de roteiro de documento.</span><span class="sxs-lookup"><span data-stu-id="76812-131">Go to Warehouse management > Setup > Document routing > Document routing layouts.</span></span>
    * <span data-ttu-id="76812-132">Habilitar o layout SSCC.</span><span class="sxs-lookup"><span data-stu-id="76812-132">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="76812-133">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="76812-133">Click New.</span></span>
3. <span data-ttu-id="76812-134">No campo ID de layout, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76812-134">In the Layout ID field, type a value.</span></span>
4. <span data-ttu-id="76812-135">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76812-135">In the Description field, type a value.</span></span>
5. <span data-ttu-id="76812-136">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="76812-136">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="76812-137">Clique em Inserir no final do texto.</span><span class="sxs-lookup"><span data-stu-id="76812-137">Click Insert at end of text.</span></span>
7. <span data-ttu-id="76812-138">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="76812-138">Click Save.</span></span>
8. <span data-ttu-id="76812-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="76812-139">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="76812-140">Configurar o roteamento de documentos</span><span class="sxs-lookup"><span data-stu-id="76812-140">Set up the document routing</span></span>
1. <span data-ttu-id="76812-141">Vá para Gerenciamento de depósito > Configuração > Roteiro de documento > Roteiro de documento.</span><span class="sxs-lookup"><span data-stu-id="76812-141">Go to Warehouse management > Setup > Document routing > Document routing.</span></span>
2. <span data-ttu-id="76812-142">No campo Tipo de ordem de trabalho, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="76812-142">In the Work order type field, select an option.</span></span>
3. <span data-ttu-id="76812-143">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="76812-143">Click New.</span></span>
4. <span data-ttu-id="76812-144">No campo Depósito, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76812-144">In the Warehouse field, type a value.</span></span>
5. <span data-ttu-id="76812-145">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76812-145">In the Name field, type a value.</span></span>
6. <span data-ttu-id="76812-146">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="76812-146">Click New.</span></span>
7. <span data-ttu-id="76812-147">No campo ID de layout, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="76812-147">In the Layout ID field, enter or select a value.</span></span>
8. <span data-ttu-id="76812-148">No campo Nome, insira o nome da impressora que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="76812-148">In the Name field, enter the printer name that you want to use..</span></span>
9. <span data-ttu-id="76812-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="76812-149">Click Save.</span></span>
10. <span data-ttu-id="76812-150">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="76812-150">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="76812-151">Criar o menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="76812-151">Create mobile device menu</span></span>
1. <span data-ttu-id="76812-152">Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Itens de menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="76812-152">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="76812-153">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="76812-153">Click New.</span></span>
3. <span data-ttu-id="76812-154">No campo Item de menu, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76812-154">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="76812-155">No campo Título, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76812-155">In the Title field, type a value.</span></span>
5. <span data-ttu-id="76812-156">No campo Modo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="76812-156">In the Mode field, select an option.</span></span>
6. <span data-ttu-id="76812-157">Selecione Sim no campo Usar trabalho existente.</span><span class="sxs-lookup"><span data-stu-id="76812-157">Select Yes in the Use existing work field.</span></span>
7. <span data-ttu-id="76812-158">Selecione Sim no campo Gerar placa de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="76812-158">Select Yes in the Generate license plate field.</span></span>
8. <span data-ttu-id="76812-159">Expanda a seção Classes de trabalho.</span><span class="sxs-lookup"><span data-stu-id="76812-159">Expand the Work classes section.</span></span>
9. <span data-ttu-id="76812-160">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="76812-160">Click New.</span></span>
10. <span data-ttu-id="76812-161">No campo ID de classe de trabalho, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="76812-161">In the Work class ID field, type a value.</span></span>
11. <span data-ttu-id="76812-162">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="76812-162">Click Save.</span></span>
12. <span data-ttu-id="76812-163">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="76812-163">Close the page.</span></span>
13. <span data-ttu-id="76812-164">Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="76812-164">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
14. <span data-ttu-id="76812-165">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="76812-165">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="76812-166">Na árvore, selecione 'Na árvore, selecione o item de menu que você criou antes'.</span><span class="sxs-lookup"><span data-stu-id="76812-166">In the tree, select 'In the tree, select the menu item that you created before.'.</span></span>
16. <span data-ttu-id="76812-167">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="76812-167">Click Edit.</span></span>
17. <span data-ttu-id="76812-168">Clique na seta para adicionar o item de menu ao menu.</span><span class="sxs-lookup"><span data-stu-id="76812-168">Click on the arrow to add the menu item to the menu.</span></span>
18. <span data-ttu-id="76812-169">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="76812-169">Click Save.</span></span>
19. <span data-ttu-id="76812-170">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="76812-170">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="76812-171">Atualizar um modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="76812-171">Update a work template</span></span>
1. <span data-ttu-id="76812-172">Vá para Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="76812-172">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="76812-173">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="76812-173">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="76812-174">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="76812-174">Click Edit.</span></span>
4. <span data-ttu-id="76812-175">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="76812-175">Click New.</span></span>
5. <span data-ttu-id="76812-176">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="76812-176">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="76812-177">No campo Tipo de trabalho, selecione 'Imprimir'.</span><span class="sxs-lookup"><span data-stu-id="76812-177">In the Work type field, select 'Print'.</span></span>
7. <span data-ttu-id="76812-178">No campo ID de classe de trabalho, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="76812-178">In the Work class ID field, enter or select a value.</span></span>
8. <span data-ttu-id="76812-179">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="76812-179">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="76812-180">Clique em Mover para cima.</span><span class="sxs-lookup"><span data-stu-id="76812-180">Click Move up.</span></span>
10. <span data-ttu-id="76812-181">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="76812-181">Click Save.</span></span>
11. <span data-ttu-id="76812-182">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="76812-182">Close the page.</span></span>

