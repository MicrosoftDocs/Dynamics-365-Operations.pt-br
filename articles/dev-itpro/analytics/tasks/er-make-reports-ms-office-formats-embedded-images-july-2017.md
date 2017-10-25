--- 
title: "Criar relatórios nos formatos do Microsoft Office com imagens incorporadas para relatório eletrônico (ER) (Parte 1)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de relatório eletrônico pode criar configurações de Relatório Eletrônico (RE) para gerar os documentos eletrônicos nos formatos do MS Office (Excel e Word) que contenham imagens incorporadas."
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 93a40f36e38ef5ea393cf429ad9244b56504bbfc
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="make-reports-in-microsoft-office-formats-with-embedded-images-for-electronic-reporting-er--part-1"></a><span data-ttu-id="9824b-103">Criar relatórios nos formatos do Microsoft Office com imagens incorporadas para relatório eletrônico (ER) (Parte 1)</span><span class="sxs-lookup"><span data-stu-id="9824b-103">Make reports in Microsoft Office formats with embedded images for electronic reporting (ER)  (Part 1)</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9824b-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de relatório eletrônico pode criar configurações de Relatório Eletrônico (RE) para gerar os documentos eletrônicos nos formatos do MS Office (Excel e Word) que contenham imagens incorporadas.</span><span class="sxs-lookup"><span data-stu-id="9824b-104">The following steps explain how a user playing either ‘System administrator’ or ‘Electronic reporting developer’ role can design Electronic reporting (ER) configurations to generate electronic documents in MS office formats (Excel and Word) containing embedded images.</span></span>

<span data-ttu-id="9824b-105">Neste exemplo, você usará as configurações de ER criadas para a empresa exemplo, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="9824b-105">In this example, you will use created ER configurations for sample company, ‘Litware, Inc.’.</span></span>  <span data-ttu-id="9824b-106">Para completar essas etapas, primeiro você deve concluir as etapas no guia de tarefas "ER Fazer relatórios nos formatos do MS Office com imagens incorporadas (Parte 2: Revisar configurações).</span><span class="sxs-lookup"><span data-stu-id="9824b-106">To complete these steps, you must first complete the steps in the “ER Make reports in MS Office formats with embedded images (Part 2: Review configurations)” task guide.</span></span> <span data-ttu-id="9824b-107">Essas etapas podem ser executadas na empresa "USMF".</span><span class="sxs-lookup"><span data-stu-id="9824b-107">These steps can be performed in ‘USMF’ company.</span></span>


## <a name="run-format-with-initial-model-mapping"></a><span data-ttu-id="9824b-108">Executar formato com mapeamento de modelo inicial</span><span class="sxs-lookup"><span data-stu-id="9824b-108">Run format with initial model mapping</span></span>
1. <span data-ttu-id="9824b-109">Vá para Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="9824b-109">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="9824b-110">Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'USMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="9824b-110">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="9824b-111">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="9824b-111">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="9824b-112">Clique em Verificar.</span><span class="sxs-lookup"><span data-stu-id="9824b-112">Click Check.</span></span>
5. <span data-ttu-id="9824b-113">Clique em Imprimir teste.</span><span class="sxs-lookup"><span data-stu-id="9824b-113">Click Print test.</span></span>
    * <span data-ttu-id="9824b-114">Execute o formato para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="9824b-114">Run the format for testing purposes.</span></span>  
6. <span data-ttu-id="9824b-115">Selecione Sim no campo Formato de cheque negociável.</span><span class="sxs-lookup"><span data-stu-id="9824b-115">Select Yes in the Negotiable check format field.</span></span>
7. <span data-ttu-id="9824b-116">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9824b-116">Click OK.</span></span>
    * <span data-ttu-id="9824b-117">Revise a saída criada.</span><span class="sxs-lookup"><span data-stu-id="9824b-117">Review the created output.</span></span> <span data-ttu-id="9824b-118">Observe que o logotipo da empresa é mostrado no relatório, bem como a assinatura da pessoa autorizada.</span><span class="sxs-lookup"><span data-stu-id="9824b-118">Note that the company logo is presented in the report as well as the authorized person’s signature.</span></span> <span data-ttu-id="9824b-119">A imagem de assinatura é obtida do campo do tipo de dados "Contêiner" do registro de layout de cheque que é associado à conta bancária selecionada.</span><span class="sxs-lookup"><span data-stu-id="9824b-119">The signature image is taken from the field of the ‘Container’ data type of the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="9824b-120">Expanda a seção Cópias.</span><span class="sxs-lookup"><span data-stu-id="9824b-120">Expand the Copies section.</span></span>
9. <span data-ttu-id="9824b-121">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="9824b-121">Click Edit.</span></span>
10. <span data-ttu-id="9824b-122">No campo Marca d'água, insira "Imprimir marca d'água como Nula".</span><span class="sxs-lookup"><span data-stu-id="9824b-122">In the Watermark field, enter 'Print watermark as Void'.</span></span>
    * <span data-ttu-id="9824b-123">Modificar a configuração do layout de marca d'água para exibir o texto de marca d'água ao gerar o documento de um elemento do Excel.</span><span class="sxs-lookup"><span data-stu-id="9824b-123">Change the watermark layout setting to show the watermark text in generating document in an Excel shape element.</span></span>  
11. <span data-ttu-id="9824b-124">Clique em Imprimir teste.</span><span class="sxs-lookup"><span data-stu-id="9824b-124">Click Print test.</span></span>
12. <span data-ttu-id="9824b-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9824b-125">Click OK.</span></span>
    * <span data-ttu-id="9824b-126">Revise a saída criada.</span><span class="sxs-lookup"><span data-stu-id="9824b-126">Review the created output.</span></span> <span data-ttu-id="9824b-127">Observe que a marca-d'água é mostrada no relatório criado, de acordo a opção de seleção.</span><span class="sxs-lookup"><span data-stu-id="9824b-127">Note that the watermark is shown in the created report in accordance to the selection option.</span></span>  
13. <span data-ttu-id="9824b-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-128">Close the page.</span></span>
14. <span data-ttu-id="9824b-129">No Painel de Ação, clique em Gerenciar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="9824b-129">On the Action Pane, click Manage payments.</span></span>
15. <span data-ttu-id="9824b-130">Clique em Cheques.</span><span class="sxs-lookup"><span data-stu-id="9824b-130">Click Checks.</span></span>
16. <span data-ttu-id="9824b-131">Clique em Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="9824b-131">Click Show filters.</span></span>
17. <span data-ttu-id="9824b-132">Aplique os seguintes filtros: insira um valor de filtro de "381","385","389" no campo "Número do cheque" usando o operador de filtro "é um de".</span><span class="sxs-lookup"><span data-stu-id="9824b-132">Apply the following filters: Enter a filter value of "381","385","389" on the "Check number" field using the "is one of" filter operator.</span></span>
18. <span data-ttu-id="9824b-133">Na lista, marque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="9824b-133">In the list, mark all rows.</span></span>
19. <span data-ttu-id="9824b-134">Clique em Imprimir cópia de cheque.</span><span class="sxs-lookup"><span data-stu-id="9824b-134">Click Print check copy.</span></span>
    * <span data-ttu-id="9824b-135">Execute o formato para reimprimir os cheques selecionados.</span><span class="sxs-lookup"><span data-stu-id="9824b-135">Run the format to re-print the selected cheques.</span></span>  
    * <span data-ttu-id="9824b-136">Revise a saída criada.</span><span class="sxs-lookup"><span data-stu-id="9824b-136">Review the created output.</span></span> <span data-ttu-id="9824b-137">Observe que os cheques selecionados foram reimpressos.</span><span class="sxs-lookup"><span data-stu-id="9824b-137">Note that the selected cheques have been re-printed.</span></span> <span data-ttu-id="9824b-138">O logotipo e os rótulos empresariais não são impressos de saída, já que são apresentados no formulário pré-impresso.</span><span class="sxs-lookup"><span data-stu-id="9824b-138">The company logo and labels are not printed out since they are presented on the pre-printed form.</span></span>  

## <a name="modify-the-mapping-of-the-imported-data-model"></a><span data-ttu-id="9824b-139">Modifique mapeamento do modelo de dados importados</span><span class="sxs-lookup"><span data-stu-id="9824b-139">Modify the mapping of the imported data model</span></span>
1. <span data-ttu-id="9824b-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-140">Close the page.</span></span>
2. <span data-ttu-id="9824b-141">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-141">Close the page.</span></span>
3. <span data-ttu-id="9824b-142">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="9824b-142">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="9824b-143">Na árvore, selecione "Modelo de cheques'.</span><span class="sxs-lookup"><span data-stu-id="9824b-143">In the tree, select 'Model for cheques'.</span></span>
5. <span data-ttu-id="9824b-144">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="9824b-144">Click Designer.</span></span>
6. <span data-ttu-id="9824b-145">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9824b-145">Click Map model to datasource.</span></span>
7. <span data-ttu-id="9824b-146">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="9824b-146">Click Designer.</span></span>
    * <span data-ttu-id="9824b-147">Alteraremos a associação do item de assinatura do modelo de dados para obter a imagem de assinatura do arquivo que foi anexada ao registro de layout de cheque que está associado à conta bancária selecionada.</span><span class="sxs-lookup"><span data-stu-id="9824b-147">We will change the binding of the data model’s signature item to get the signature image from the file that has been attached to the cheque layout record which is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="9824b-148">Desative Mostrar detalhes.</span><span class="sxs-lookup"><span data-stu-id="9824b-148">Turn Show details off.</span></span>
9. <span data-ttu-id="9824b-149">Na árvore, expanda 'layout'.</span><span class="sxs-lookup"><span data-stu-id="9824b-149">In the tree, expand 'layout'.</span></span>
10. <span data-ttu-id="9824b-150">Na árvore, expanda 'layout\assinatura'.</span><span class="sxs-lookup"><span data-stu-id="9824b-150">In the tree, expand 'layout\signature'.</span></span>
11. <span data-ttu-id="9824b-151">Na árvore, selecione 'layout\assinatura\imagem = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span><span class="sxs-lookup"><span data-stu-id="9824b-151">In the tree, select 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span></span>
12. <span data-ttu-id="9824b-152">Na árvore, expanda 'chequesaccount'.</span><span class="sxs-lookup"><span data-stu-id="9824b-152">In the tree, expand 'chequesaccount'.</span></span>
13. <span data-ttu-id="9824b-153">Na árvore, expanda 'chequesaccount\<Relações'.</span><span class="sxs-lookup"><span data-stu-id="9824b-153">In the tree, expand 'chequesaccount\<Relations'.</span></span>
14. <span data-ttu-id="9824b-154">Na árvore, expanda 'chequesaccount\<Relações\BankChequeLayout'.</span><span class="sxs-lookup"><span data-stu-id="9824b-154">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout'.</span></span>
15. <span data-ttu-id="9824b-155">Na árvore, expanda 'chequesaccount\<Relações\BankChequeLayout\<Relações'.</span><span class="sxs-lookup"><span data-stu-id="9824b-155">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations'.</span></span>
16. <span data-ttu-id="9824b-156">Na árvore, expanda 'chequesaccount\<Relações\BankChequeLayout\<Relações\<Documentos'.</span><span class="sxs-lookup"><span data-stu-id="9824b-156">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents'.</span></span>
17. <span data-ttu-id="9824b-157">Na árvore, selecione 'chequesaccount\<Relações\BankChequeLayout\<Relações\<Documentos\getFileContentAsContainer()'.</span><span class="sxs-lookup"><span data-stu-id="9824b-157">In the tree, select 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'.</span></span>
18. <span data-ttu-id="9824b-158">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="9824b-158">Click Bind.</span></span>
19. <span data-ttu-id="9824b-159">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9824b-159">Click Save.</span></span>
20. <span data-ttu-id="9824b-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-160">Close the page.</span></span>
21. <span data-ttu-id="9824b-161">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-161">Close the page.</span></span>
22. <span data-ttu-id="9824b-162">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-162">Close the page.</span></span>
23. <span data-ttu-id="9824b-163">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-163">Close the page.</span></span>

## <a name="run-format-using-the-adjusted-model-mapping"></a><span data-ttu-id="9824b-164">Execute o formato usando o mapeamento de modelo ajustado</span><span class="sxs-lookup"><span data-stu-id="9824b-164">Run format using the adjusted model mapping</span></span>
1. <span data-ttu-id="9824b-165">Vá para Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="9824b-165">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="9824b-166">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="9824b-166">Use the Quick Filter to find records.</span></span> <span data-ttu-id="9824b-167">Por exemplo, filtre o campo Conta bancária com um valor de 'USMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="9824b-167">For example, filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="9824b-168">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="9824b-168">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="9824b-169">Clique em Verificar.</span><span class="sxs-lookup"><span data-stu-id="9824b-169">Click Check.</span></span>
5. <span data-ttu-id="9824b-170">Clique em Imprimir teste.</span><span class="sxs-lookup"><span data-stu-id="9824b-170">Click Print test.</span></span>
6. <span data-ttu-id="9824b-171">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9824b-171">Click OK.</span></span>
    * <span data-ttu-id="9824b-172">Revise a saída criada.</span><span class="sxs-lookup"><span data-stu-id="9824b-172">Review the created output.</span></span> <span data-ttu-id="9824b-173">Observe que a imagem do anexo de Gerenciamento de documentos é exibida como a assinatura de uma pessoa autorizada.</span><span class="sxs-lookup"><span data-stu-id="9824b-173">Note that the image from the Document Management attachment is presented as the signature of an authorized person.</span></span>  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a><span data-ttu-id="9824b-174">Use o documento do Word MS como um modelo no formato importado</span><span class="sxs-lookup"><span data-stu-id="9824b-174">Use MS Word document as a template in the imported format</span></span>
1. <span data-ttu-id="9824b-175">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-175">Close the page.</span></span>
2. <span data-ttu-id="9824b-176">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-176">Close the page.</span></span>
3. <span data-ttu-id="9824b-177">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="9824b-177">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="9824b-178">Na árvore, expanda "Modelo de cheques'.</span><span class="sxs-lookup"><span data-stu-id="9824b-178">In the tree, expand 'Model for cheques'.</span></span>
5. <span data-ttu-id="9824b-179">Na árvore, selecione 'Modelo para cheques\Formato de impressão de cheques'.</span><span class="sxs-lookup"><span data-stu-id="9824b-179">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
6. <span data-ttu-id="9824b-180">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="9824b-180">Click Designer.</span></span>
7. <span data-ttu-id="9824b-181">Clique em Anexos.</span><span class="sxs-lookup"><span data-stu-id="9824b-181">Click Attachments.</span></span>
8. <span data-ttu-id="9824b-182">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="9824b-182">Click Delete.</span></span>
9. <span data-ttu-id="9824b-183">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="9824b-183">Click Yes.</span></span>
10. <span data-ttu-id="9824b-184">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9824b-184">Click New.</span></span>
11. <span data-ttu-id="9824b-185">Clique em Arquivo.</span><span class="sxs-lookup"><span data-stu-id="9824b-185">Click File.</span></span>
    * <span data-ttu-id="9824b-186">Clique em Pesquisar e selecione o arquivo baixado previamente "Cheque template Word.docx".</span><span class="sxs-lookup"><span data-stu-id="9824b-186">Click Browse and select the downloaded in advance ‘Cheque template Word.docx’ file.</span></span>  
12. <span data-ttu-id="9824b-187">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-187">Close the page.</span></span>
13. <span data-ttu-id="9824b-188">No campo Modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="9824b-188">In the Template field, enter or select a value.</span></span>
14. <span data-ttu-id="9824b-189">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9824b-189">Click Save.</span></span>
15. <span data-ttu-id="9824b-190">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-190">Close the page.</span></span>
16. <span data-ttu-id="9824b-191">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="9824b-191">Click Edit.</span></span>
17. <span data-ttu-id="9824b-192">Selecione Sim no campo Executar Rascunho.</span><span class="sxs-lookup"><span data-stu-id="9824b-192">Select Yes in the Run Draft field.</span></span>
18. <span data-ttu-id="9824b-193">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9824b-193">Close the page.</span></span>
19. <span data-ttu-id="9824b-194">Vá para Gerenciamento de caixa e bancos > Contas bancárias > Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="9824b-194">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
20. <span data-ttu-id="9824b-195">Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'USMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="9824b-195">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
21. <span data-ttu-id="9824b-196">Clique em Verificar.</span><span class="sxs-lookup"><span data-stu-id="9824b-196">Click Check.</span></span>
22. <span data-ttu-id="9824b-197">Clique em Imprimir teste.</span><span class="sxs-lookup"><span data-stu-id="9824b-197">Click Print test.</span></span>
23. <span data-ttu-id="9824b-198">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="9824b-198">Click OK.</span></span>
    * <span data-ttu-id="9824b-199">Revise a saída criada.</span><span class="sxs-lookup"><span data-stu-id="9824b-199">Review the created output.</span></span> <span data-ttu-id="9824b-200">Observe que a saída foi gerada como um documento do MS Word com imagens incorporadas apresentando o logotipo da empresa, a assinatura de uma pessoa autorizada e o texto selecionado da marca d'água.</span><span class="sxs-lookup"><span data-stu-id="9824b-200">Note that the output has been generated as a MS Word document with embedded images presenting the company logo, the signature of an authorized person and the selected text of the watermark.</span></span>  

