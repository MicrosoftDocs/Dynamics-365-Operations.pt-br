---
title: Criar configurações para gerar relatórios em formatos do Office com imagens incorporadas
description: As etapas neste tópico fornecem informações sobre como criar configurações de relatório eletrônico (ER) que geram documentos eletrônicos nos formatos do Microsoft Office (Excel e Word) contendo imagens incorporadas.
author: NickSelin
manager: AnnBe
ms.date: 01/23/2018
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
ms.openlocfilehash: 143782413359d87f3d4c46940f9a699fbf0e8f90
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769800"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="8c365-103">Criar configurações para gerar relatórios em formatos do Office com imagens incorporadas</span><span class="sxs-lookup"><span data-stu-id="8c365-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8c365-104">Para concluir as etapas neste procedimento, você deve primeiro concluir o procedimento, "ER Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="8c365-104">To complete the steps in this procedure, first complete the procedure, “ER Create a configuration provider and mark it as active.”</span></span> <span data-ttu-id="8c365-105">Este procedimento explica como criar configurações de relatório eletrônico (ER) para gerar um documento do Microsoft Excel ou do Word contendo imagens incorporadas.</span><span class="sxs-lookup"><span data-stu-id="8c365-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="8c365-106">Nesse procedimento, você criará as configurações de ER necessárias para a empresa de exemplo, a Litware, Inc. Essas etapas podem ser concluídas usando o conjunto de dados USMF.</span><span class="sxs-lookup"><span data-stu-id="8c365-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="8c365-107">Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8c365-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="8c365-108">Antes de começar, baixe e salve os arquivos listados no tópico da Ajuda [Inserir imagens e formas em documentos gerados usando ER](../electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="8c365-108">Before you begin, download and save the files listed in the Help topic, [Embed images and shapes in documents that you generate by using ER](../electronic-reporting-embed-images-shapes.md).</span></span> <span data-ttu-id="8c365-109">Os arquivos são: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png, e Cheque template Word.docx.</span><span class="sxs-lookup"><span data-stu-id="8c365-109">The files are: Model for cheques.xml, Cheques printing format.xml, Company logo.png, Signature image.png, Signature image 2.png, and Cheque template Word.docx.</span></span>

## <a name="verify-prerequisites"></a><span data-ttu-id="8c365-110">Verificar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8c365-110">Verify prerequisites</span></span>  
 1. <span data-ttu-id="8c365-111">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8c365-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="8c365-112">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo.</span><span class="sxs-lookup"><span data-stu-id="8c365-112">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="8c365-113">Se você não visualizar esse provedor de configuração, conclua as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo."</span><span class="sxs-lookup"><span data-stu-id="8c365-113">If you don’t see this configuration provider, complete the steps in the procedure, “Create a configuration provider and mark it as active.”</span></span>   
 3. <span data-ttu-id="8c365-114">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="8c365-114">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="8c365-115">Adicionar uma nova configuração de modelo de ER</span><span class="sxs-lookup"><span data-stu-id="8c365-115">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="8c365-116">Em vez de criar um novo modelo, você pode carregar o arquivo de configuração do modelo de ER (Model for cheques.xml) que salvou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8c365-116">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="8c365-117">Este arquivo contém o modelo de dados de amostra para cheques de pagamento e o mapeamento do modelo de dados para os componentes de dados do aplicativo Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="8c365-117">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="8c365-118">Na Guia Rápida Versões, clique em Troca.</span><span class="sxs-lookup"><span data-stu-id="8c365-118">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="8c365-119">Clique em Carregar de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="8c365-119">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="8c365-120">Clique em Procurar e selecione Model for cheques.xml.</span><span class="sxs-lookup"><span data-stu-id="8c365-120">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="8c365-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8c365-121">Click OK.</span></span>  
 6. <span data-ttu-id="8c365-122">O modelo carregado será usado como fonte de dados de informações para gerar documentos que contenham imagens no Excel e no Word.</span><span class="sxs-lookup"><span data-stu-id="8c365-122">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="8c365-123">Adicionar uma nova configuração de formato de ER</span><span class="sxs-lookup"><span data-stu-id="8c365-123">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="8c365-124">Em vez de criar um novo formato, você pode carregar o arquivo de configuração do formato de ER (Cheques printing format.xml) que salvou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8c365-124">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="8c365-125">Esse arquivo contém o layout de exemplo do formato para imprimir cheques usando o formulário pré-impresso e o mapeamento desse formato para o modelo de dados 'Modelo de cheques'.</span><span class="sxs-lookup"><span data-stu-id="8c365-125">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the ‘Model for cheques’ data model.</span></span>   
 2. <span data-ttu-id="8c365-126">Clique em Trocar.</span><span class="sxs-lookup"><span data-stu-id="8c365-126">Click Exchange.</span></span>  
 3. <span data-ttu-id="8c365-127">Clique em Carregar de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="8c365-127">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="8c365-128">Clique em Procurar e selecione o arquivo Cheques printing format.xml.</span><span class="sxs-lookup"><span data-stu-id="8c365-128">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="8c365-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8c365-129">Click OK.</span></span>  
 6. <span data-ttu-id="8c365-130">Na árvore, expanda "Modelo de cheques'.</span><span class="sxs-lookup"><span data-stu-id="8c365-130">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="8c365-131">Na árvore, selecione 'Modelo para cheques\Formato de impressão de cheques'.</span><span class="sxs-lookup"><span data-stu-id="8c365-131">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="8c365-132">O formato carregado será usado para gerar documentos que contenham imagens no Excel e no Word.</span><span class="sxs-lookup"><span data-stu-id="8c365-132">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="8c365-133">Configurar parâmetros de usuário de ER</span><span class="sxs-lookup"><span data-stu-id="8c365-133">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="8c365-134">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="8c365-134">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="8c365-135">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="8c365-135">Click User parameters.</span></span>  
 3. <span data-ttu-id="8c365-136">Selecione Sim no campo Executar configurações.</span><span class="sxs-lookup"><span data-stu-id="8c365-136">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="8c365-137">Ative o sinalizador 'Executar rascunho' para iniciar a versão de rascunho do formato selecionado em vez da versão concluída.</span><span class="sxs-lookup"><span data-stu-id="8c365-137">Turn on the ‘Run draft’ flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="8c365-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8c365-138">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="8c365-139">Configurar parâmetros de gerenciamento de banco e caixa</span><span class="sxs-lookup"><span data-stu-id="8c365-139">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="8c365-140">Vá para Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="8c365-140">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="8c365-141">Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'USMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="8c365-141">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="8c365-142">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="8c365-142">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="8c365-143">Clique em Verificar.</span><span class="sxs-lookup"><span data-stu-id="8c365-143">Click Check.</span></span>  
 5. <span data-ttu-id="8c365-144">Expandir a seção Instalação.</span><span class="sxs-lookup"><span data-stu-id="8c365-144">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="8c365-145">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="8c365-145">Click Edit.</span></span>  
 7. <span data-ttu-id="8c365-146">Selecione Sim no campo Logotipo da empresa.</span><span class="sxs-lookup"><span data-stu-id="8c365-146">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="8c365-147">Clique em Logotipo da empresa.</span><span class="sxs-lookup"><span data-stu-id="8c365-147">Click Company logo.</span></span>  
 9. <span data-ttu-id="8c365-148">Clique em Alterar.</span><span class="sxs-lookup"><span data-stu-id="8c365-148">Click Change.</span></span>  
 10. <span data-ttu-id="8c365-149">Clique em Procurar e selecione o arquivo baixado anteriormente, Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="8c365-149">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="8c365-150">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8c365-150">Click Save.</span></span>  
 12. <span data-ttu-id="8c365-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c365-151">Close the page.</span></span>  
 13. <span data-ttu-id="8c365-152">Expanda a seção Assinatura.</span><span class="sxs-lookup"><span data-stu-id="8c365-152">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="8c365-153">Selecione Sim no campo Imprimir primeira assinatura.</span><span class="sxs-lookup"><span data-stu-id="8c365-153">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="8c365-154">Clique em Alterar.</span><span class="sxs-lookup"><span data-stu-id="8c365-154">Click Change.</span></span>  
 16. <span data-ttu-id="8c365-155">Clique em Procurar e selecione o arquivo baixado anteriormente, Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="8c365-155">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="8c365-156">Expanda a seção Cópias.</span><span class="sxs-lookup"><span data-stu-id="8c365-156">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="8c365-157">No campo Marca d'água, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="8c365-157">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="8c365-158">Selecione Sim no campo Formato de exportação eletrônico genérico.</span><span class="sxs-lookup"><span data-stu-id="8c365-158">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="8c365-159">Selecione a configuração 'Formulário de impressão de cheques'.</span><span class="sxs-lookup"><span data-stu-id="8c365-159">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="8c365-160">Agora o formato de ER selecionado será usado para a impressão de cheques.</span><span class="sxs-lookup"><span data-stu-id="8c365-160">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="8c365-161">Clique em Anexar.</span><span class="sxs-lookup"><span data-stu-id="8c365-161">Click Attach.</span></span>  
 23. <span data-ttu-id="8c365-162">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8c365-162">Click New.</span></span>  
 24. <span data-ttu-id="8c365-163">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="8c365-163">Click File.</span></span>  
 25. <span data-ttu-id="8c365-164">Clique em Procurar e selecione o arquivo baixado anteriormente, Signature image 2.png.</span><span class="sxs-lookup"><span data-stu-id="8c365-164">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="8c365-165">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c365-165">Close the page.</span></span>  
 27. <span data-ttu-id="8c365-166">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c365-166">Close the page.</span></span>  
 28. <span data-ttu-id="8c365-167">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c365-167">Close the page.</span></span>  
 29. <span data-ttu-id="8c365-168">Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.</span><span class="sxs-lookup"><span data-stu-id="8c365-168">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="8c365-169">Selecione Sim no campo Permitir a criação do pré-registro em contas bancárias inativas:.</span><span class="sxs-lookup"><span data-stu-id="8c365-169">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="8c365-170">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8c365-170">Click Save.</span></span>  
 32. <span data-ttu-id="8c365-171">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c365-171">Close the page.</span></span>  
