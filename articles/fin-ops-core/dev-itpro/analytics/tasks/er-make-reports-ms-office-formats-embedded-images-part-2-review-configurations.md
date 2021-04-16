---
title: Revisar configurações para criar relatórios em formatos do Office com imagens incorporadas
description: Este tópico descreve como criar configurações de relatório para gerar documentos eletrônicos que contenham imagens incorporadas. (Parte 1 - Configurar parâmetros).
author: NickSelin
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: de815b363daa9135b50a2f5c9c4ac19e87b6b7ee
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751573"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="95ac8-104">Revisar configurações para criar relatórios em formatos do Office com imagens incorporadas</span><span class="sxs-lookup"><span data-stu-id="95ac8-104">Review configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="95ac8-105">Para concluir essas etapas, primeiro você deve concluir as etapas no guia de tarefas "ER Criar relatórios nos formatos do MS Office com imagens incorporadas (Parte 1: Configurar parâmetros)".</span><span class="sxs-lookup"><span data-stu-id="95ac8-105">To complete these steps, you must first complete the steps in the "ER Make reports in MS Office formats with embedded images (Part 1: Set up parameters)" task guide.</span></span>

<span data-ttu-id="95ac8-106">Este procedimento mostra como criar configurações de relatório eletrônico (ER) para gerar documentos eletrônicos contendo imagens incorporadas no Microsoft Excel e no Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="95ac8-106">This procedure shows how to design Electronic reporting (ER) configurations to generate electronic documents that contain embedded images in Microsoft Excel and Microsoft Word.</span></span> <span data-ttu-id="95ac8-107">Neste exemplo, você revisará as configurações de ER para a empresa exemplo, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="95ac8-107">In this example, you will review ER configurations for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="95ac8-108">Esse procedimento é destinado a usuários com a função de Administrador do sistema ou Desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="95ac8-108">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="95ac8-109">As etapas podem ser concluídas usando o conjunto de dados de USMF.</span><span class="sxs-lookup"><span data-stu-id="95ac8-109">The steps can be completed by using the USMF data set.</span></span>


## <a name="review-the-imported-data-model"></a><span data-ttu-id="95ac8-110">Revise o modelo de dados importados</span><span class="sxs-lookup"><span data-stu-id="95ac8-110">Review the imported data model</span></span>
1. <span data-ttu-id="95ac8-111">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="95ac8-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="95ac8-112">Na árvore, selecione "Modelo de cheques'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-112">In the tree, select 'Model for cheques'.</span></span>
3. <span data-ttu-id="95ac8-113">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="95ac8-113">Click Designer.</span></span>
    * <span data-ttu-id="95ac8-114">Esse modelo é criado para representar cheques de pagamento do ponto de vista comercial e do mapeamento desse modelo para fontes de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="95ac8-114">This model is designed to represent payment cheques from the business standpoint and the mapping of this model to the application's data sources.</span></span> <span data-ttu-id="95ac8-115">Examine este modelo através do Designer de operações do ER.</span><span class="sxs-lookup"><span data-stu-id="95ac8-115">Review this model by the ER Operations designer.</span></span> <span data-ttu-id="95ac8-116">Observe os atributos dos elementos do modelo que são apresentados: estrutura, nome, descrição, tipo de dados etc.</span><span class="sxs-lookup"><span data-stu-id="95ac8-116">Note the attributes of the model elements that are presented: structure, name, description, data type, and so on.</span></span>   
4. <span data-ttu-id="95ac8-117">Na árvore, expanda 'raiz'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-117">In the tree, expand 'root'.</span></span>
5. <span data-ttu-id="95ac8-118">Na árvore, selecione 'raiz\cheques'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-118">In the tree, select 'root\cheques'.</span></span>
6. <span data-ttu-id="95ac8-119">Na árvore, expanda 'raiz\cheques'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-119">In the tree, expand 'root\cheques'.</span></span>
7. <span data-ttu-id="95ac8-120">Na árvore, expanda 'raiz\cheques\atributos'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-120">In the tree, expand 'root\cheques\attributes'.</span></span>
8. <span data-ttu-id="95ac8-121">Na árvore, expanda 'raiz\pagador'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-121">In the tree, expand 'root\payer'.</span></span>
9. <span data-ttu-id="95ac8-122">Na árvore, selecione 'raiz\istestrun'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-122">In the tree, select 'root\istestrun'.</span></span>
10. <span data-ttu-id="95ac8-123">Na árvore, selecione 'raiz\layout'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-123">In the tree, select 'root\layout'.</span></span>
    * <span data-ttu-id="95ac8-124">O elemento do layout deste modelo representa os detalhes do layout de impressão do formulário de cheque da conta bancária selecionada.</span><span class="sxs-lookup"><span data-stu-id="95ac8-124">The layout element of this model represents the details of the printing cheque form layout for the selected bank account.</span></span> <span data-ttu-id="95ac8-125">Também inclui dois nós do tipo de dados de contêiner para armazenar imagens.</span><span class="sxs-lookup"><span data-stu-id="95ac8-125">It also includes two nodes of the Container data type to store images.</span></span>   
11. <span data-ttu-id="95ac8-126">Na árvore, expanda 'raiz\layout'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-126">In the tree, expand 'root\layout'.</span></span>
12. <span data-ttu-id="95ac8-127">Na árvore, selecione 'raiz\layout\logotipo da empresa'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-127">In the tree, select 'root\layout\company logo'.</span></span>
13. <span data-ttu-id="95ac8-128">Na árvore, expanda 'raiz\layout\logotipo da empresa'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-128">In the tree, expand 'root\layout\company logo'.</span></span>
14. <span data-ttu-id="95ac8-129">Na árvore, selecione 'raiz\layout\logotipo da empresa\imagem'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-129">In the tree, select 'root\layout\company logo\image'.</span></span>
15. <span data-ttu-id="95ac8-130">Na árvore, selecione 'raiz\layout\logotipo da empresa\isprinted'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-130">In the tree, select 'root\layout\company logo\isprinted'.</span></span>
16. <span data-ttu-id="95ac8-131">Na árvore, selecione 'raiz\layout\assinatura'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-131">In the tree, select 'root\layout\signature'.</span></span>
17. <span data-ttu-id="95ac8-132">Na árvore, expanda 'raiz\layout\assinatura'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-132">In the tree, expand 'root\layout\signature'.</span></span>
18. <span data-ttu-id="95ac8-133">Na árvore, selecione 'raiz\layout\assinatura\imagem'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-133">In the tree, select 'root\layout\signature\image'.</span></span>
19. <span data-ttu-id="95ac8-134">Na árvore, selecione 'raiz\layout\assinatura\isprinted'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-134">In the tree, select 'root\layout\signature\isprinted'.</span></span>
    * <span data-ttu-id="95ac8-135">Observe que dois elementos do modelo de dados de imagem estão associados aos campos das tabelas que contêm imagens do logotipo da empresa e da assinatura da pessoa autorizada no formato binário.</span><span class="sxs-lookup"><span data-stu-id="95ac8-135">Note that two image data model elements are bound to the fields of the tables that contain images of the company logo and the authorized person's signature in binary format.</span></span>  
20. <span data-ttu-id="95ac8-136">Na árvore, expanda 'raiz\layout\marca d'água'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-136">In the tree, expand 'root\layout\watermark'.</span></span>
21. <span data-ttu-id="95ac8-137">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="95ac8-137">Click Map model to datasource.</span></span>
22. <span data-ttu-id="95ac8-138">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="95ac8-138">Click Designer.</span></span>
23. <span data-ttu-id="95ac8-139">Na árvore, expanda 'chequesselected'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-139">In the tree, expand 'chequesselected'.</span></span>
24. <span data-ttu-id="95ac8-140">Na árvore, expanda 'layout'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-140">In the tree, expand 'layout'.</span></span>
25. <span data-ttu-id="95ac8-141">Na árvore, expanda 'layout\logotipo da empresa'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-141">In the tree, expand 'layout\company logo'.</span></span>
26. <span data-ttu-id="95ac8-142">Na árvore, expanda 'layout\assinatura'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-142">In the tree, expand 'layout\signature'.</span></span>
27. <span data-ttu-id="95ac8-143">Na árvore, expanda 'layout\marca d'água'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-143">In the tree, expand 'layout\watermark'.</span></span>
28. <span data-ttu-id="95ac8-144">Ative "Mostrar detalhes".</span><span class="sxs-lookup"><span data-stu-id="95ac8-144">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="95ac8-145">Observe que o elemento de modelo de dados de cheques é associado à tabela de TmpChequePrintout que, em tempo de execução, conterá os registros dos cheques que o usuário selecionou para impressão.</span><span class="sxs-lookup"><span data-stu-id="95ac8-145">Note that the cheques data model element is bound to the TmpChequePrintout table that, at runtime, will contain records for cheques that the user has selected for printing.</span></span>   
29. <span data-ttu-id="95ac8-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="95ac8-146">Close the page.</span></span>
30. <span data-ttu-id="95ac8-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="95ac8-147">Close the page.</span></span>
31. <span data-ttu-id="95ac8-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="95ac8-148">Close the page.</span></span>

## <a name="review-the-imported-format"></a><span data-ttu-id="95ac8-149">Examine o formato importado</span><span class="sxs-lookup"><span data-stu-id="95ac8-149">Review the imported format</span></span>
1. <span data-ttu-id="95ac8-150">Na árvore, expanda "Modelo de cheques'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-150">In the tree, expand 'Model for cheques'.</span></span>
2. <span data-ttu-id="95ac8-151">Na árvore, selecione 'Modelo para cheques\Formato de impressão de cheques'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-151">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
3. <span data-ttu-id="95ac8-152">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="95ac8-152">Click Designer.</span></span>
4. <span data-ttu-id="95ac8-153">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="95ac8-153">Click Attachments.</span></span>
5. <span data-ttu-id="95ac8-154">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="95ac8-154">Click Open.</span></span>
    * <span data-ttu-id="95ac8-155">Abra o modelo de relatório anexado no Excel.</span><span class="sxs-lookup"><span data-stu-id="95ac8-155">Open the attached report's template in Excel.</span></span>  
    * <span data-ttu-id="95ac8-156">Revise o modelo de relatório do Excel anexado que será usado para imprimir os cheques.</span><span class="sxs-lookup"><span data-stu-id="95ac8-156">Review the attached report's Excel template that will be used to print cheques.</span></span> <span data-ttu-id="95ac8-157">O modelo contém dois cheques por página e é criado para imprimir cheques no formulário pré-impresso.</span><span class="sxs-lookup"><span data-stu-id="95ac8-157">The template contains two cheques per page and is designed to print cheques to the preprinted form.</span></span> <span data-ttu-id="95ac8-158">Observe que duas imagens em branco são inseridas.</span><span class="sxs-lookup"><span data-stu-id="95ac8-158">Note that two blank images are embedded.</span></span> <span data-ttu-id="95ac8-159">Essas imagens em branco são para o logotipo da empresa e a assinatura da pessoa que está autorizando um pagamento.</span><span class="sxs-lookup"><span data-stu-id="95ac8-159">These blank images are for the company logo and the signature of the person who is authorizing a payment.</span></span> <span data-ttu-id="95ac8-160">Verifique que as imagens são denominadas CompLogo e SignatureImage, respectivamente, no Excel.</span><span class="sxs-lookup"><span data-stu-id="95ac8-160">Verify that the images are named CompLogo and SignatureImage, respectively, in Excel.</span></span>   
6. <span data-ttu-id="95ac8-161">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="95ac8-161">Close the page.</span></span>
7. <span data-ttu-id="95ac8-162">Na árvore, expanda 'Relatório'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-162">In the tree, expand 'Report'.</span></span>
8. <span data-ttu-id="95ac8-163">Na árvore, expanda 'Relatório\ChequeLines'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-163">In the tree, expand 'Report\ChequeLines'.</span></span>
9. <span data-ttu-id="95ac8-164">Na árvore, selecione 'Relatório\ChequeLines\CompLogo'.</span><span class="sxs-lookup"><span data-stu-id="95ac8-164">In the tree, select 'Report\ChequeLines\CompLogo'.</span></span>
10. <span data-ttu-id="95ac8-165">Ative "Mostrar detalhes".</span><span class="sxs-lookup"><span data-stu-id="95ac8-165">Toggle 'Show details' on.</span></span>
    * <span data-ttu-id="95ac8-166">Observe que o elemento da célula de formato "CompLogo" representa o item do Excel que é usado para preencher a imagem do logotipo da empresa no relatório.</span><span class="sxs-lookup"><span data-stu-id="95ac8-166">Note that the 'CompLogo' format's cell element represents the Excel item that is used to populate the company logo image in the report.</span></span> <span data-ttu-id="95ac8-167">Esse elemento de formato está associado ao elemento de modelo de dados de imagem que, em tempo de execução, contém uma imagem de logotipo da empresa no formato binário.</span><span class="sxs-lookup"><span data-stu-id="95ac8-167">This format element is bound to the image data model element that, at runtime, contains a company logo image in binary format.</span></span>   
11. <span data-ttu-id="95ac8-168">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="95ac8-168">Click the Mapping tab.</span></span>
12. <span data-ttu-id="95ac8-169">Clique em Edição habilitada.</span><span class="sxs-lookup"><span data-stu-id="95ac8-169">Click Edit enabled.</span></span>
    * <span data-ttu-id="95ac8-170">Observe que você pode criar o elemento da célula de formato "CompLogo", de modo que ele não seja mais habilitado.</span><span class="sxs-lookup"><span data-stu-id="95ac8-170">Note that you can make the 'CompLogo' format's cell element so that it's no longer enabled.</span></span> <span data-ttu-id="95ac8-171">Nesse caso, o elemento de imagem associado do Excel ocultará um logotipo da empresa no relatório gerado.</span><span class="sxs-lookup"><span data-stu-id="95ac8-171">In this case, the associated Excel image element will hide a company logo in the generated report.</span></span> <span data-ttu-id="95ac8-172">Se a expressão habilitada retornar TRUE e a associação definida não mostrar nenhuma imagem, o elemento de imagem associado do Excel mostrará uma imagem que foi salva no modelo do Excel.</span><span class="sxs-lookup"><span data-stu-id="95ac8-172">If the enabled expression returns TRUE and the defined binding brings no image, the associated Excel image element will show an image that has been saved in the Excel template.</span></span>   
13. <span data-ttu-id="95ac8-173">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="95ac8-173">Close the page.</span></span>
14. <span data-ttu-id="95ac8-174">Na árvore, expanda “rótulos: Contêiner”.</span><span class="sxs-lookup"><span data-stu-id="95ac8-174">In the tree, expand 'labels: Container'.</span></span>
    * <span data-ttu-id="95ac8-175">Alguns rótulos que são apresentados no formulário pré-impresso do cheque serão incluídos no relatório quando ele for criado para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="95ac8-175">Some labels that are presented in the preprinted cheque form will be included in the report when it's created for testing purposes.</span></span> <span data-ttu-id="95ac8-176">Entretanto, esses rótulos não serão impressos durante a impressão real porque o formulário pré-impresso já os inclui.</span><span class="sxs-lookup"><span data-stu-id="95ac8-176">However, those labels won't be printed during real printing, because the preprinted form already includes them.</span></span>  
15. <span data-ttu-id="95ac8-177">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="95ac8-177">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]