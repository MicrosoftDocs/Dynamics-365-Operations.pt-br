---
title: Criar configurações para gerar relatórios em formatos do Office com imagens incorporadas
description: Este tópico descreve como criar configurações de relatório eletrônico (ER) que gerem documentos eletrônicos nos formatos Excel e Word que contenham imagens incorporadas.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5eea178a351716425706f481ae66c5b5183a52e5
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944548"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="e70de-103">Criar configurações para gerar relatórios em formatos do Office com imagens incorporadas</span><span class="sxs-lookup"><span data-stu-id="e70de-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e70de-104">Para concluir as etapas neste procedimento, você deve primeiro concluir o procedimento, "ER Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="e70de-104">To complete the steps in this procedure, first complete the procedure, "ER Create a configuration provider and mark it as active."</span></span> <span data-ttu-id="e70de-105">Este procedimento explica como criar configurações de relatório eletrônico (ER) para gerar um documento do Microsoft Excel ou do Word contendo imagens incorporadas.</span><span class="sxs-lookup"><span data-stu-id="e70de-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="e70de-106">Nesse procedimento, você criará as configurações de ER necessárias para a empresa de exemplo, a Litware, Inc. Essas etapas podem ser concluídas usando o conjunto de dados USMF.</span><span class="sxs-lookup"><span data-stu-id="e70de-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="e70de-107">Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="e70de-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="e70de-108">Antes de começar, baixe e salve os seguintes arquivos:</span><span class="sxs-lookup"><span data-stu-id="e70de-108">Before you begin, download and save the following files:</span></span> 

| <span data-ttu-id="e70de-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="e70de-109">Description</span></span>                                          | <span data-ttu-id="e70de-110">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="e70de-110">File name</span></span>                   |
|------------------------------------------------------|-----------------------------|
| <span data-ttu-id="e70de-111">Configuração do modelo de dados de ER</span><span class="sxs-lookup"><span data-stu-id="e70de-111">ER data model configuration</span></span>                          | [<span data-ttu-id="e70de-112">Modelo para cheques.xml</span><span class="sxs-lookup"><span data-stu-id="e70de-112">Model for cheques.xml</span></span>](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| <span data-ttu-id="e70de-113">Configuração de formato ER</span><span class="sxs-lookup"><span data-stu-id="e70de-113">ER format configuration</span></span>                              | [<span data-ttu-id="e70de-114">Formato de impressão de cheques.xml</span><span class="sxs-lookup"><span data-stu-id="e70de-114">Cheques printing format.xml</span></span>](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| <span data-ttu-id="e70de-115">Imagem do logotipo da empresa</span><span class="sxs-lookup"><span data-stu-id="e70de-115">Company logo image</span></span>                                   | [<span data-ttu-id="e70de-116">Company logo.png</span><span class="sxs-lookup"><span data-stu-id="e70de-116">Company logo.png</span></span>](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| <span data-ttu-id="e70de-117">Imagem de assinatura</span><span class="sxs-lookup"><span data-stu-id="e70de-117">Signature image</span></span>                                      | [<span data-ttu-id="e70de-118">Signature image.png</span><span class="sxs-lookup"><span data-stu-id="e70de-118">Signature image.png</span></span>](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| <span data-ttu-id="e70de-119">Imagem de assinatura alternativa</span><span class="sxs-lookup"><span data-stu-id="e70de-119">Alternative signature image</span></span>                          | [<span data-ttu-id="e70de-120">Signature image 2.png</span><span class="sxs-lookup"><span data-stu-id="e70de-120">Signature image 2.png</span></span>](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| <span data-ttu-id="e70de-121">Modelo do Microsoft Word para imprimir cheques de pagamento</span><span class="sxs-lookup"><span data-stu-id="e70de-121">Microsoft Word template for printing payment checks</span></span>  | [<span data-ttu-id="e70de-122">Cheque template Word.docx</span><span class="sxs-lookup"><span data-stu-id="e70de-122">Cheque template Word.docx</span></span>](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a><span data-ttu-id="e70de-123">Verificar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e70de-123">Verify prerequisites</span></span>  
 1. <span data-ttu-id="e70de-124">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="e70de-124">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="e70de-125">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo.</span><span class="sxs-lookup"><span data-stu-id="e70de-125">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="e70de-126">Se não visualizar este provedor de configuração, conclua as etapas no procedimento "Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="e70de-126">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>   
 3. <span data-ttu-id="e70de-127">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="e70de-127">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="e70de-128">Adicionar uma nova configuração de modelo de ER</span><span class="sxs-lookup"><span data-stu-id="e70de-128">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="e70de-129">Em vez de criar um novo modelo, você pode carregar o arquivo de configuração do modelo de ER (Model for cheques.xml) que salvou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e70de-129">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="e70de-130">Este arquivo contém o modelo de dados de amostra para cheques de pagamento e o mapeamento do modelo de dados para os componentes de dados do aplicativo Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="e70de-130">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="e70de-131">Na Guia Rápida Versões, clique em Troca.</span><span class="sxs-lookup"><span data-stu-id="e70de-131">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="e70de-132">Clique em Carregar de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="e70de-132">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="e70de-133">Clique em Procurar e selecione Model for cheques.xml.</span><span class="sxs-lookup"><span data-stu-id="e70de-133">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="e70de-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e70de-134">Click OK.</span></span>  
 6. <span data-ttu-id="e70de-135">O modelo carregado será usado como fonte de dados de informações para gerar documentos que contenham imagens no Excel e no Word.</span><span class="sxs-lookup"><span data-stu-id="e70de-135">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="e70de-136">Adicionar uma nova configuração de formato de ER</span><span class="sxs-lookup"><span data-stu-id="e70de-136">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="e70de-137">Em vez de criar um novo formato, você pode carregar o arquivo de configuração do formato de ER (Cheques printing format.xml) que salvou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e70de-137">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="e70de-138">Esse arquivo contém o layout de exemplo do formato para imprimir cheques usando o formulário pré-impresso e o mapeamento desse formato para o modelo de dados "Modelo de cheques".</span><span class="sxs-lookup"><span data-stu-id="e70de-138">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the 'Model for cheques' data model.</span></span>   
 2. <span data-ttu-id="e70de-139">Clique em Trocar.</span><span class="sxs-lookup"><span data-stu-id="e70de-139">Click Exchange.</span></span>  
 3. <span data-ttu-id="e70de-140">Clique em Carregar de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="e70de-140">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="e70de-141">Clique em Procurar e selecione o arquivo Cheques printing format.xml.</span><span class="sxs-lookup"><span data-stu-id="e70de-141">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="e70de-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e70de-142">Click OK.</span></span>  
 6. <span data-ttu-id="e70de-143">Na árvore, expanda "Modelo de cheques'.</span><span class="sxs-lookup"><span data-stu-id="e70de-143">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="e70de-144">Na árvore, selecione 'Modelo para cheques\Formato de impressão de cheques'.</span><span class="sxs-lookup"><span data-stu-id="e70de-144">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="e70de-145">O formato carregado será usado para gerar documentos que contenham imagens no Excel e no Word.</span><span class="sxs-lookup"><span data-stu-id="e70de-145">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="e70de-146">Configurar parâmetros de usuário de ER</span><span class="sxs-lookup"><span data-stu-id="e70de-146">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="e70de-147">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="e70de-147">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="e70de-148">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="e70de-148">Click User parameters.</span></span>  
 3. <span data-ttu-id="e70de-149">Selecione Sim no campo Executar configurações.</span><span class="sxs-lookup"><span data-stu-id="e70de-149">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="e70de-150">Ative o sinalizador "Executar rascunho" para iniciar a versão de rascunho do formato selecionado em vez da versão concluída.</span><span class="sxs-lookup"><span data-stu-id="e70de-150">Turn on the 'Run draft' flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="e70de-151">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e70de-151">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="e70de-152">Configurar parâmetros de gerenciamento de banco e caixa</span><span class="sxs-lookup"><span data-stu-id="e70de-152">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="e70de-153">Vá para Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="e70de-153">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="e70de-154">Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'USMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="e70de-154">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="e70de-155">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="e70de-155">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="e70de-156">Clique em Verificar.</span><span class="sxs-lookup"><span data-stu-id="e70de-156">Click Check.</span></span>  
 5. <span data-ttu-id="e70de-157">Expandir a seção Instalação.</span><span class="sxs-lookup"><span data-stu-id="e70de-157">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="e70de-158">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="e70de-158">Click Edit.</span></span>  
 7. <span data-ttu-id="e70de-159">Selecione Sim no campo Logotipo da empresa.</span><span class="sxs-lookup"><span data-stu-id="e70de-159">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="e70de-160">Clique em Logotipo da empresa.</span><span class="sxs-lookup"><span data-stu-id="e70de-160">Click Company logo.</span></span>  
 9. <span data-ttu-id="e70de-161">Clique em Alterar.</span><span class="sxs-lookup"><span data-stu-id="e70de-161">Click Change.</span></span>  
 10. <span data-ttu-id="e70de-162">Clique em Procurar e selecione o arquivo baixado anteriormente, Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="e70de-162">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="e70de-163">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="e70de-163">Click Save.</span></span>  
 12. <span data-ttu-id="e70de-164">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e70de-164">Close the page.</span></span>  
 13. <span data-ttu-id="e70de-165">Expanda a seção Assinatura.</span><span class="sxs-lookup"><span data-stu-id="e70de-165">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="e70de-166">Selecione Sim no campo Imprimir primeira assinatura.</span><span class="sxs-lookup"><span data-stu-id="e70de-166">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="e70de-167">Clique em Alterar.</span><span class="sxs-lookup"><span data-stu-id="e70de-167">Click Change.</span></span>  
 16. <span data-ttu-id="e70de-168">Clique em Procurar e selecione o arquivo baixado anteriormente, Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="e70de-168">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="e70de-169">Expanda a seção Cópias.</span><span class="sxs-lookup"><span data-stu-id="e70de-169">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="e70de-170">No campo Marca d'água, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="e70de-170">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="e70de-171">Selecione Sim no campo Formato de exportação eletrônico genérico.</span><span class="sxs-lookup"><span data-stu-id="e70de-171">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="e70de-172">Selecione a configuração 'Formulário de impressão de cheques'.</span><span class="sxs-lookup"><span data-stu-id="e70de-172">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="e70de-173">Agora o formato de ER selecionado será usado para a impressão de cheques.</span><span class="sxs-lookup"><span data-stu-id="e70de-173">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="e70de-174">Clique em Anexar.</span><span class="sxs-lookup"><span data-stu-id="e70de-174">Click Attach.</span></span>  
 23. <span data-ttu-id="e70de-175">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="e70de-175">Click New.</span></span>  
 24. <span data-ttu-id="e70de-176">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="e70de-176">Click File.</span></span>  
 25. <span data-ttu-id="e70de-177">Clique em Procurar e selecione o arquivo baixado anteriormente, Signature image 2.png.</span><span class="sxs-lookup"><span data-stu-id="e70de-177">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="e70de-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e70de-178">Close the page.</span></span>  
 27. <span data-ttu-id="e70de-179">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e70de-179">Close the page.</span></span>  
 28. <span data-ttu-id="e70de-180">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e70de-180">Close the page.</span></span>  
 29. <span data-ttu-id="e70de-181">Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.</span><span class="sxs-lookup"><span data-stu-id="e70de-181">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="e70de-182">Selecione Sim no campo Permitir a criação do pré-registro em contas bancárias inativas:.</span><span class="sxs-lookup"><span data-stu-id="e70de-182">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="e70de-183">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="e70de-183">Click Save.</span></span>  
 32. <span data-ttu-id="e70de-184">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e70de-184">Close the page.</span></span>  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
