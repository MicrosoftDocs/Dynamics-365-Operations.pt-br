---
title: Configurar assinaturas eletrônicas
description: Utilize esse procedimento para configurar assinaturas eletrônicas.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysConfiguration, SIGParameters, SIGReasonCode, SIGProcSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 314f48fcac32793c96466ee807d5685e596193b1
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4796649"
---
# <a name="set-up-electronic-signatures"></a><span data-ttu-id="5e252-103">Configurar assinaturas eletrônicas</span><span class="sxs-lookup"><span data-stu-id="5e252-103">Set up electronic signatures</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5e252-104">Utilize esse procedimento para configurar assinaturas eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="5e252-104">Use this procedure to set up electronic signatures.</span></span> <span data-ttu-id="5e252-105">Uma assinatura eletrônica confirma a identidade de uma pessoa que está prestes a iniciar ou aprovar um processo de computação.</span><span class="sxs-lookup"><span data-stu-id="5e252-105">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="5e252-106">A empresa de dados demonstrativos utilizada para criar esse procedimento é a DAT.</span><span class="sxs-lookup"><span data-stu-id="5e252-106">The demo data company used to create this procedure is DAT.</span></span>


## <a name="enable-the-electronic-signature-configuration-key"></a><span data-ttu-id="5e252-107">Habilitar a chave de configuração da Assinatura eletrônica</span><span class="sxs-lookup"><span data-stu-id="5e252-107">Enable the Electronic signature configuration key</span></span>
1. <span data-ttu-id="5e252-108">Vá para Administração de sistema > Configuração > Configuração de licença.</span><span class="sxs-lookup"><span data-stu-id="5e252-108">Go to System administration > Setup > License configuration.</span></span>
2. <span data-ttu-id="5e252-109">Na árvore, expanda 'Administração'.</span><span class="sxs-lookup"><span data-stu-id="5e252-109">In the tree, expand 'Administration'.</span></span>
    * <span data-ttu-id="5e252-110">Verifique se a caixa de seleção Assinatura eletrônica está selecionada.</span><span class="sxs-lookup"><span data-stu-id="5e252-110">Verify that the Electronic signature check box is selected.</span></span>  
    * <span data-ttu-id="5e252-111">Se a caixa de seleção Assinatura eletrônica não estiver selecionada, você deve habilitar o modo de manutenção.</span><span class="sxs-lookup"><span data-stu-id="5e252-111">If the Electronic signature check box is not selected, you must enable maintenance mode.</span></span> <span data-ttu-id="5e252-112">O modo de manutenção pode ser habilitado nesse ambiente através da execução de um trabalho de manutenção da Lifecycle Services, ou utilizando a ferramenta Deployment.Setup localmente.</span><span class="sxs-lookup"><span data-stu-id="5e252-112">Maintenance mode can be enabled in this environment by running a maintenance job from Lifecycle Services, or by using the Deployment.Setup tool locally.</span></span>  
3. <span data-ttu-id="5e252-113">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5e252-113">Close the page.</span></span>

## <a name="set-up-electronic-signature-parameters"></a><span data-ttu-id="5e252-114">Configurar parâmetros de assinatura eletrônica</span><span class="sxs-lookup"><span data-stu-id="5e252-114">Set up electronic signature parameters</span></span>
1. <span data-ttu-id="5e252-115">Vá para Administração da organização > Configuração > Assinatura eletrônica > Parâmetros da assinatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="5e252-115">Go to Organization administration > Setup > Electronic signature > Electronic signature parameters.</span></span>
2. <span data-ttu-id="5e252-116">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="5e252-116">Click Edit.</span></span>
3. <span data-ttu-id="5e252-117">No campo Aviso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5e252-117">In the Notice field, type a value.</span></span>
    * <span data-ttu-id="5e252-118">Insira o aviso que os signatários receberão quando uma assinatura for exigida.</span><span class="sxs-lookup"><span data-stu-id="5e252-118">Enter the notice that signers will receive when a signature is requested.</span></span> <span data-ttu-id="5e252-119">Você pode inserir qualquer texto.</span><span class="sxs-lookup"><span data-stu-id="5e252-119">You can enter any text.</span></span> <span data-ttu-id="5e252-120">Normalmente, esse texto informa sobre o que significa assinar um documento eletronicamente.</span><span class="sxs-lookup"><span data-stu-id="5e252-120">Typically, this text tells the user what it means to sign a document electronically.</span></span>  
    * <span data-ttu-id="5e252-121">Se você deseja inserir Texto de alerta em outros idiomas, clique no botão Traduções.</span><span class="sxs-lookup"><span data-stu-id="5e252-121">If you want to enter the Notice text in additional languages, click the Translations button.</span></span>  
4. <span data-ttu-id="5e252-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5e252-122">Click Save.</span></span>
5. <span data-ttu-id="5e252-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5e252-123">Close the page.</span></span>

## <a name="set-up-reason-codes-for-electronic-signatures"></a><span data-ttu-id="5e252-124">Configurar códigos de motivos para assinaturas eletrônicas</span><span class="sxs-lookup"><span data-stu-id="5e252-124">Set up reason codes for electronic signatures</span></span>
1. <span data-ttu-id="5e252-125">Vá para Administração da organização > Configuração > Assinatura eletrônica > Códigos de motivo da assinatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="5e252-125">Go to Organization administration > Setup > Electronic signature > Electronic signature reason codes.</span></span>
2. <span data-ttu-id="5e252-126">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5e252-126">Click New.</span></span>
    * <span data-ttu-id="5e252-127">Você deve configurar códigos de motivos antes de usar assinaturas eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="5e252-127">You must set up reason codes before using electronic signatures.</span></span> <span data-ttu-id="5e252-128">Um código de motivo válido é necessário para assinar um documento.</span><span class="sxs-lookup"><span data-stu-id="5e252-128">A valid reason code is required when signing a document.</span></span>     <span data-ttu-id="5e252-129">Um signatário seleciona um código de motivo para indicar a finalidade da assinatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="5e252-129">A signer selects a reason code to indicate the purpose of an electronic signature.</span></span> <span data-ttu-id="5e252-130">Por exemplo, um código de motivo pode ser usado para indicar aprovação legal.</span><span class="sxs-lookup"><span data-stu-id="5e252-130">For example, a reason code could be used to indicate legal approval.</span></span>  
3. <span data-ttu-id="5e252-131">No campo Código de motivo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5e252-131">In the Reason code field, type a value.</span></span>
4. <span data-ttu-id="5e252-132">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5e252-132">In the Description field, type a value.</span></span>
    * <span data-ttu-id="5e252-133">Insira códigos de motivo adicionais, se necessário.</span><span class="sxs-lookup"><span data-stu-id="5e252-133">Enter additional reason codes, if needed.</span></span>  
5. <span data-ttu-id="5e252-134">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5e252-134">Click Save.</span></span>
6. <span data-ttu-id="5e252-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5e252-135">Close the page.</span></span>

## <a name="require-electronic-signatures-for-existing-processes"></a><span data-ttu-id="5e252-136">Solicitar assinaturas eletrônicas para processos existentes</span><span class="sxs-lookup"><span data-stu-id="5e252-136">Require electronic signatures for existing processes</span></span>
1. <span data-ttu-id="5e252-137">Vá para Administração da organização > Configuração > Assinatura eletrônica > Requisitos da assinatura eletrônica.</span><span class="sxs-lookup"><span data-stu-id="5e252-137">Go to Organization administration > Setup > Electronic signature > Electronic signature requirements.</span></span>
2. <span data-ttu-id="5e252-138">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="5e252-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="5e252-139">Selecione um processo que exija assinaturas eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="5e252-139">Select a process that requires electronic signatures.</span></span>  
3. <span data-ttu-id="5e252-140">Marque ou desmarque a caixa de seleção Assinatura necessária.</span><span class="sxs-lookup"><span data-stu-id="5e252-140">Select or clear the Signature required check box.</span></span>
    * <span data-ttu-id="5e252-141">Repita essas etapas para cada processo que exigir assinaturas eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="5e252-141">Repeat these steps for each process that requires electronic signatures.</span></span>  
4. <span data-ttu-id="5e252-142">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5e252-142">Click Save.</span></span>

## <a name="create-a-custom-requirement-for-electronic-signatures"></a><span data-ttu-id="5e252-143">Criar um requisito personalizado para assinaturas eletrônicas</span><span class="sxs-lookup"><span data-stu-id="5e252-143">Create a custom requirement for electronic signatures</span></span>
1. <span data-ttu-id="5e252-144">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5e252-144">Click New.</span></span>
2. <span data-ttu-id="5e252-145">Marque ou desmarque a caixa de seleção Assinatura necessária.</span><span class="sxs-lookup"><span data-stu-id="5e252-145">Select or clear the Signature required check box.</span></span>
3. <span data-ttu-id="5e252-146">No campo Nome, insira um nome para o processo que exige assinaturas eletrônicas.</span><span class="sxs-lookup"><span data-stu-id="5e252-146">In the Name field, enter a name for the process that requires electronic signatures.</span></span>
4. <span data-ttu-id="5e252-147">No campo Nome da tabela, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5e252-147">In the Table name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="5e252-148">Na lista, localize e selecione a tabela onde os dados que devem ser assinados estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="5e252-148">In the list, find and select the table where the data that must be signed is stored.</span></span>
6. <span data-ttu-id="5e252-149">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5e252-149">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="5e252-150">No campo Nome do campo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5e252-150">In the Field name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="5e252-151">Na lista, localize e selecione o campo da tabela que você deseja monitorar.</span><span class="sxs-lookup"><span data-stu-id="5e252-151">In the list, find and select the field in the table that you want to monitor.</span></span>
9. <span data-ttu-id="5e252-152">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5e252-152">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5e252-153">Especifique quando uma assinatura é necessária.</span><span class="sxs-lookup"><span data-stu-id="5e252-153">Specify when a signature is required.</span></span>     <span data-ttu-id="5e252-154">Selecione Sempre se uma assinatura for necessária quando os dados do campo forem alterados.</span><span class="sxs-lookup"><span data-stu-id="5e252-154">Select Always if a signature is required when the data in the field changes.</span></span>     <span data-ttu-id="5e252-155">Selecione Apenas se uma assinatura é necessária somente sob certas condições.</span><span class="sxs-lookup"><span data-stu-id="5e252-155">Select Only if a signature is required only under certain conditions.</span></span> <span data-ttu-id="5e252-156">Se você selecionar Apenas, você também deverá selecionar uma das seguintes opções: Quando um registro é inserido, Quando um registro é atualizado, ou Quando um registro é excluído.</span><span class="sxs-lookup"><span data-stu-id="5e252-156">If you select Only, you must also select one of the following options: When a record is inserted, When a record is updated, or When a record is deleted.</span></span>  
10. <span data-ttu-id="5e252-157">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5e252-157">Click Save.</span></span>
11. <span data-ttu-id="5e252-158">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5e252-158">Close the page.</span></span>

