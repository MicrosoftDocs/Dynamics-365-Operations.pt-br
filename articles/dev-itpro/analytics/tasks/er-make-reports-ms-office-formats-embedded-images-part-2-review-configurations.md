---
title: Revisar configurações para criar relatórios em formatos do Office com imagens incorporadas
description: Para concluir essas etapas, primeiro você deve concluir as etapas no guia de tarefas "ER Criar relatórios nos formatos do MS Office com imagens incorporadas (Parte 1 – Configurar parâmetros)".
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f3462f16ad7638071ab0aa2175d0bc291eeae89
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "331405"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="0adee-103">Revisar configurações para criar relatórios em formatos do Office com imagens incorporadas</span><span class="sxs-lookup"><span data-stu-id="0adee-103">Review configurations to generate reports in Office format that have embedded images</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0adee-104">Para completar essas etapas, primeiro você deve concluir as etapas no guia de tarefas "ER Fazer relatórios nos formatos do MS Office com imagens incorporadas (Parte 1: Configurar parâmetros)".</span><span class="sxs-lookup"><span data-stu-id="0adee-104">To complete these steps, you must first complete the steps in the “ER Make reports in MS Office formats with embedded images (Part 1: Set up parameters)” task guide.</span></span>

<span data-ttu-id="0adee-105">Este procedimento mostra como criar configurações de relatório eletrônico (ER) para gerar documentos eletrônicos contendo imagens incorporadas no Microsoft Excel e no Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="0adee-105">This procedure shows how to design Electronic reporting (ER) configurations to generate electronic documents that contain embedded images in Microsoft Excel and Microsoft Word.</span></span> <span data-ttu-id="0adee-106">Neste exemplo, você revisará as configurações de ER para a empresa exemplo, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="0adee-106">In this example, you will review ER configurations for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="0adee-107">Esse procedimento é destinado a usuários com a função de Administrador do sistema ou Desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0adee-107">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="0adee-108">As etapas podem ser concluídas usando o conjunto de dados de USMF.</span><span class="sxs-lookup"><span data-stu-id="0adee-108">The steps can be completed by using the USMF data set.</span></span>


## <a name="review-the-imported-data-model"></a><span data-ttu-id="0adee-109">Revise o modelo de dados importados</span><span class="sxs-lookup"><span data-stu-id="0adee-109">Review the imported data model</span></span>
1. <span data-ttu-id="0adee-110">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="0adee-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="0adee-111">Na árvore, selecione "Modelo de cheques'.</span><span class="sxs-lookup"><span data-stu-id="0adee-111">In the tree, select 'Model for cheques'.</span></span>
3. <span data-ttu-id="0adee-112">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="0adee-112">Click Designer.</span></span>
    * <span data-ttu-id="0adee-113">Esse modelo é criado para representar cheques de pagamento do ponto de vista comercial e do mapeamento desse modelo para fontes de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0adee-113">This model is designed to represent payment cheques from the business standpoint and the mapping of this model to the application’s data sources.</span></span> <span data-ttu-id="0adee-114">Examine este modelo através do Designer de operações do ER.</span><span class="sxs-lookup"><span data-stu-id="0adee-114">Review this model by the ER Operations designer.</span></span> <span data-ttu-id="0adee-115">Observe os atributos dos elementos do modelo que são apresentados: estrutura, nome, descrição, tipo de dados etc.</span><span class="sxs-lookup"><span data-stu-id="0adee-115">Note the attributes of the model elements that are presented: structure, name, description, data type, and so on.</span></span>   
4. <span data-ttu-id="0adee-116">Na árvore, expanda 'raiz'.</span><span class="sxs-lookup"><span data-stu-id="0adee-116">In the tree, expand 'root'.</span></span>
5. <span data-ttu-id="0adee-117">Na árvore, selecione 'raiz\cheques'.</span><span class="sxs-lookup"><span data-stu-id="0adee-117">In the tree, select 'root\cheques'.</span></span>
6. <span data-ttu-id="0adee-118">Na árvore, expanda 'raiz\cheques'.</span><span class="sxs-lookup"><span data-stu-id="0adee-118">In the tree, expand 'root\cheques'.</span></span>
7. <span data-ttu-id="0adee-119">Na árvore, expanda 'raiz\cheques\atributos'.</span><span class="sxs-lookup"><span data-stu-id="0adee-119">In the tree, expand 'root\cheques\attributes'.</span></span>
8. <span data-ttu-id="0adee-120">Na árvore, expanda 'raiz\pagador'.</span><span class="sxs-lookup"><span data-stu-id="0adee-120">In the tree, expand 'root\payer'.</span></span>
9. <span data-ttu-id="0adee-121">Na árvore, selecione 'raiz\istestrun'.</span><span class="sxs-lookup"><span data-stu-id="0adee-121">In the tree, select 'root\istestrun'.</span></span>
10. <span data-ttu-id="0adee-122">Na árvore, selecione 'raiz\layout'.</span><span class="sxs-lookup"><span data-stu-id="0adee-122">In the tree, select 'root\layout'.</span></span>
    * <span data-ttu-id="0adee-123">O elemento do layout deste modelo representa os detalhes do layout de impressão do formulário de cheque da conta bancária selecionada.</span><span class="sxs-lookup"><span data-stu-id="0adee-123">The layout element of this model represents the details of the printing cheque form layout for the selected bank account.</span></span> <span data-ttu-id="0adee-124">Também inclui dois nós do tipo de dados de contêiner para armazenar imagens.</span><span class="sxs-lookup"><span data-stu-id="0adee-124">It also includes two nodes of the Container data type to store images.</span></span>   
11. <span data-ttu-id="0adee-125">Na árvore, expanda 'raiz\layout'.</span><span class="sxs-lookup"><span data-stu-id="0adee-125">In the tree, expand 'root\layout'.</span></span>
12. <span data-ttu-id="0adee-126">Na árvore, selecione 'raiz\layout\logotipo da empresa'.</span><span class="sxs-lookup"><span data-stu-id="0adee-126">In the tree, select 'root\layout\company logo'.</span></span>
13. <span data-ttu-id="0adee-127">Na árvore, expanda 'raiz\layout\logotipo da empresa'.</span><span class="sxs-lookup"><span data-stu-id="0adee-127">In the tree, expand 'root\layout\company logo'.</span></span>
14. <span data-ttu-id="0adee-128">Na árvore, selecione 'raiz\layout\logotipo da empresa\imagem'.</span><span class="sxs-lookup"><span data-stu-id="0adee-128">In the tree, select 'root\layout\company logo\image'.</span></span>
15. <span data-ttu-id="0adee-129">Na árvore, selecione 'raiz\layout\logotipo da empresa\isprinted'.</span><span class="sxs-lookup"><span data-stu-id="0adee-129">In the tree, select 'root\layout\company logo\isprinted'.</span></span>
16. <span data-ttu-id="0adee-130">Na árvore, selecione 'raiz\layout\assinatura'.</span><span class="sxs-lookup"><span data-stu-id="0adee-130">In the tree, select 'root\layout\signature'.</span></span>
17. <span data-ttu-id="0adee-131">Na árvore, expanda 'raiz\layout\assinatura'.</span><span class="sxs-lookup"><span data-stu-id="0adee-131">In the tree, expand 'root\layout\signature'.</span></span>
18. <span data-ttu-id="0adee-132">Na árvore, selecione 'raiz\layout\assinatura\imagem'.</span><span class="sxs-lookup"><span data-stu-id="0adee-132">In the tree, select 'root\layout\signature\image'.</span></span>
19. <span data-ttu-id="0adee-133">Na árvore, selecione 'raiz\layout\assinatura\isprinted'.</span><span class="sxs-lookup"><span data-stu-id="0adee-133">In the tree, select 'root\layout\signature\isprinted'.</span></span>
    * <span data-ttu-id="0adee-134">Observe que dois elementos do modelo de dados de imagem estão associados aos campos das tabelas que contêm imagens do logotipo da empresa e da assinatura da pessoa autorizada no formato binário.</span><span class="sxs-lookup"><span data-stu-id="0adee-134">Note that two image data model elements are bound to the fields of the tables that contain images of the company logo and the authorized person’s signature in binary format.</span></span>  
20. <span data-ttu-id="0adee-135">Na árvore, expanda 'raiz\layout\marca d'água'.</span><span class="sxs-lookup"><span data-stu-id="0adee-135">In the tree, expand 'root\layout\watermark'.</span></span>
21. <span data-ttu-id="0adee-136">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0adee-136">Click Map model to datasource.</span></span>
22. <span data-ttu-id="0adee-137">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="0adee-137">Click Designer.</span></span>
23. <span data-ttu-id="0adee-138">Na árvore, expanda 'chequesselected'.</span><span class="sxs-lookup"><span data-stu-id="0adee-138">In the tree, expand 'chequesselected'.</span></span>
24. <span data-ttu-id="0adee-139">Na árvore, expanda 'layout'.</span><span class="sxs-lookup"><span data-stu-id="0adee-139">In the tree, expand 'layout'.</span></span>
25. <span data-ttu-id="0adee-140">Na árvore, expanda 'layout\logotipo da empresa'.</span><span class="sxs-lookup"><span data-stu-id="0adee-140">In the tree, expand 'layout\company logo'.</span></span>
26. <span data-ttu-id="0adee-141">Na árvore, expanda 'layout\assinatura'.</span><span class="sxs-lookup"><span data-stu-id="0adee-141">In the tree, expand 'layout\signature'.</span></span>
27. <span data-ttu-id="0adee-142">Na árvore, expanda 'layout\marca d'água'.</span><span class="sxs-lookup"><span data-stu-id="0adee-142">In the tree, expand 'layout\watermark'.</span></span>
28. <span data-ttu-id="0adee-143">Ative "Mostrar detalhes".</span><span class="sxs-lookup"><span data-stu-id="0adee-143">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="0adee-144">Observe que o elemento de modelo de dados de cheques é associado à tabela de TmpChequePrintout que, em tempo de execução, conterá os registros dos cheques que o usuário selecionou para impressão.</span><span class="sxs-lookup"><span data-stu-id="0adee-144">Note that the cheques data model element is bound to the TmpChequePrintout table that, at runtime, will contain records for cheques that the user has selected for printing.</span></span>   
29. <span data-ttu-id="0adee-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0adee-145">Close the page.</span></span>
30. <span data-ttu-id="0adee-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0adee-146">Close the page.</span></span>
31. <span data-ttu-id="0adee-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0adee-147">Close the page.</span></span>

## <a name="review-the-imported-format"></a><span data-ttu-id="0adee-148">Examine o formato importado</span><span class="sxs-lookup"><span data-stu-id="0adee-148">Review the imported format</span></span>
1. <span data-ttu-id="0adee-149">Na árvore, expanda "Modelo de cheques'.</span><span class="sxs-lookup"><span data-stu-id="0adee-149">In the tree, expand 'Model for cheques'.</span></span>
2. <span data-ttu-id="0adee-150">Na árvore, selecione 'Modelo para cheques\Formato de impressão de cheques'.</span><span class="sxs-lookup"><span data-stu-id="0adee-150">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
3. <span data-ttu-id="0adee-151">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="0adee-151">Click Designer.</span></span>
4. <span data-ttu-id="0adee-152">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="0adee-152">Click Attachments.</span></span>
5. <span data-ttu-id="0adee-153">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="0adee-153">Click Open.</span></span>
    * <span data-ttu-id="0adee-154">Abra o modelo de relatório anexado no Excel.</span><span class="sxs-lookup"><span data-stu-id="0adee-154">Open the attached report’s template in Excel.</span></span>  
    * <span data-ttu-id="0adee-155">Revise o modelo de relatório do Excel anexado que será usado para imprimir os cheques.</span><span class="sxs-lookup"><span data-stu-id="0adee-155">Review the attached report’s Excel template that will be used to print cheques.</span></span> <span data-ttu-id="0adee-156">O modelo contém dois cheques por página e é criado para imprimir cheques no formulário pré-impresso.</span><span class="sxs-lookup"><span data-stu-id="0adee-156">The template contains two cheques per page and is designed to print cheques to the preprinted form.</span></span> <span data-ttu-id="0adee-157">Observe que duas imagens em branco são inseridas.</span><span class="sxs-lookup"><span data-stu-id="0adee-157">Note that two blank images are embedded.</span></span> <span data-ttu-id="0adee-158">Essas imagens em branco são para o logotipo da empresa e a assinatura da pessoa que está autorizando um pagamento.</span><span class="sxs-lookup"><span data-stu-id="0adee-158">These blank images are for the company logo and the signature of the person who is authorizing a payment.</span></span> <span data-ttu-id="0adee-159">Verifique que as imagens são denominadas CompLogo e SignatureImage, respectivamente, no Excel.</span><span class="sxs-lookup"><span data-stu-id="0adee-159">Verify that the images are named CompLogo and SignatureImage, respectively, in Excel.</span></span>   
6. <span data-ttu-id="0adee-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0adee-160">Close the page.</span></span>
7. <span data-ttu-id="0adee-161">Na árvore, expanda 'Relatório'.</span><span class="sxs-lookup"><span data-stu-id="0adee-161">In the tree, expand 'Report'.</span></span>
8. <span data-ttu-id="0adee-162">Na árvore, expanda 'Relatório\ChequeLines'.</span><span class="sxs-lookup"><span data-stu-id="0adee-162">In the tree, expand 'Report\ChequeLines'.</span></span>
9. <span data-ttu-id="0adee-163">Na árvore, selecione 'Relatório\ChequeLines\CompLogo'.</span><span class="sxs-lookup"><span data-stu-id="0adee-163">In the tree, select 'Report\ChequeLines\CompLogo'.</span></span>
10. <span data-ttu-id="0adee-164">Ative "Mostrar detalhes".</span><span class="sxs-lookup"><span data-stu-id="0adee-164">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="0adee-165">Observe que o elemento da célula de formato "CompLogo" representa o item do Excel que é usado para preencher a imagem do logotipo da empresa no relatório.</span><span class="sxs-lookup"><span data-stu-id="0adee-165">Note that the ‘CompLogo’ format’s cell element represents the Excel item that is used to populate the company logo image in the report.</span></span> <span data-ttu-id="0adee-166">Esse elemento de formato está associado ao elemento de modelo de dados de imagem que, em tempo de execução, contém uma imagem de logotipo da empresa no formato binário.</span><span class="sxs-lookup"><span data-stu-id="0adee-166">This format element is bound to the image data model element that, at runtime, contains a company logo image in binary format.</span></span>   
11. <span data-ttu-id="0adee-167">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="0adee-167">Click the Mapping tab.</span></span>
12. <span data-ttu-id="0adee-168">Clique em Edição habilitada.</span><span class="sxs-lookup"><span data-stu-id="0adee-168">Click Edit enabled.</span></span>
    * <span data-ttu-id="0adee-169">Observe que você pode criar o elemento da célula de formato “CompLogo”, de modo que ele não seja mais habilitado.</span><span class="sxs-lookup"><span data-stu-id="0adee-169">Note that you can make the ‘CompLogo’ format’s cell element so that it’s no longer enabled.</span></span> <span data-ttu-id="0adee-170">Nesse caso, o elemento de imagem associado do Excel ocultará um logotipo da empresa no relatório gerado.</span><span class="sxs-lookup"><span data-stu-id="0adee-170">In this case, the associated Excel image element will hide a company logo in the generated report.</span></span> <span data-ttu-id="0adee-171">Se a expressão habilitada retornar TRUE e a associação definida não mostrar nenhuma imagem, o elemento de imagem associado do Excel mostrará uma imagem que foi salva no modelo do Excel.</span><span class="sxs-lookup"><span data-stu-id="0adee-171">If the enabled expression returns TRUE and the defined binding brings no image, the associated Excel image element will show an image that has been saved in the Excel template.</span></span>   
13. <span data-ttu-id="0adee-172">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0adee-172">Close the page.</span></span>
14. <span data-ttu-id="0adee-173">Na árvore, expanda “rótulos: Contêiner”.</span><span class="sxs-lookup"><span data-stu-id="0adee-173">In the tree, expand 'labels: Container'.</span></span>
    * <span data-ttu-id="0adee-174">Alguns rótulos que são apresentados no formulário pré-impresso do cheque serão incluídos no relatório quando ele for criado para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="0adee-174">Some labels that are presented in the preprinted cheque form will be included in the report when it’s created for testing purposes.</span></span> <span data-ttu-id="0adee-175">Entretanto, esses rótulos não serão impressos durante a impressão real porque o formulário pré-impresso já os inclui.</span><span class="sxs-lookup"><span data-stu-id="0adee-175">However, those labels won’t be printed during real printing, because the preprinted form already includes them.</span></span>  
15. <span data-ttu-id="0adee-176">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0adee-176">Close the page.</span></span>

