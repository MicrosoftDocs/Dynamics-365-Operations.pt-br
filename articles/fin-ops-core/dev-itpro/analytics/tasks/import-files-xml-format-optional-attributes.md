---
title: (RCS) Importar arquivos no formato XML com atributos opcionais
description: Este tópico fornece informações sobre como um usuário pode criar a configuração de formato de ER para importar arquivos em formato XML que contêm atributos opcionais.
author: NickSelin
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 25ced72bc1bb1b18996c8bab986270fde0557ed3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744858"
---
# <a name="rcs-import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="0cb3b-103">(RCS) Importar arquivos no formato XML com atributos opcionais</span><span class="sxs-lookup"><span data-stu-id="0cb3b-103">(RCS) Import files in XML format with optional attributes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0cb3b-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato ER para importar arquivos no formato XML contendo atributos opcionais.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="0cb3b-105">Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="0cb3b-105">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span> <span data-ttu-id="0cb3b-106">Antes de começar, faça download e salve localmente o arquivo IncomingDocumentToLearnHowToHandleOptionalAttributes.xml do [Centro de Download da Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="0cb3b-106">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

1.    <span data-ttu-id="0cb3b-107">Vá para **Todos os espaços de trabalho** > **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-107">Go to **All workspaces** > **Electronic reporting**.</span></span>
2.    <span data-ttu-id="0cb3b-108">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-108">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="0cb3b-109">Se você não visualizar este provedor de configuração, conclua as etapas no procedimento [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="0cb3b-109">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3.    <span data-ttu-id="0cb3b-110">Clique em **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-110">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="0cb3b-111">Criar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="0cb3b-111">Create a new data model configuration</span></span>
1.    <span data-ttu-id="0cb3b-112">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-112">Click **Create configuration** to open the drop dialog.</span></span>
2.    <span data-ttu-id="0cb3b-113">No campo **Nome**, digite 'Modelo para importar arquivo xml'.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-113">In the **Name** field, type 'Model to import xml file'.</span></span>
3.    <span data-ttu-id="0cb3b-114">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-114">Click **Create configuration**.</span></span>
4.    <span data-ttu-id="0cb3b-115">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-115">Click **Designer**.</span></span>
5.    <span data-ttu-id="0cb3b-116">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-116">Click **New** to open the drop dialog.</span></span>
6.    <span data-ttu-id="0cb3b-117">No campo **Nome**, digite 'Raiz'.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-117">In the **Name** field, type 'Root'.</span></span>
7.    <span data-ttu-id="0cb3b-118">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-118">Click **Add**.</span></span>
8.    <span data-ttu-id="0cb3b-119">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-119">Click **New** to open the drop dialog.</span></span>
9.    <span data-ttu-id="0cb3b-120">No campo **Nome**, digite 'Lista'.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-120">In the **Name** field, type 'List'.</span></span>
10.    <span data-ttu-id="0cb3b-121">No campo **Tipo de item**, selecione **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-121">In the **Item type** field, select **Record list**.</span></span>
11.    <span data-ttu-id="0cb3b-122">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-122">Click **Add**.</span></span>
12.    <span data-ttu-id="0cb3b-123">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-123">Click **New** to open the drop dialog.</span></span>
13.    <span data-ttu-id="0cb3b-124">No campo **Nome**, digite 'Código'.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-124">In the **Name** field, type 'Code'.</span></span>
14.    <span data-ttu-id="0cb3b-125">No campo **Tipo de item**, selecione **String**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-125">In the **Item type** field, select **String**.</span></span>
15.    <span data-ttu-id="0cb3b-126">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-126">Click **Add**.</span></span>
16.    <span data-ttu-id="0cb3b-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-127">Click **Save**.</span></span>
17.    <span data-ttu-id="0cb3b-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-128">Close the page.</span></span>
18.    <span data-ttu-id="0cb3b-129">Clique em **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-129">Click **Change status**.</span></span>
19.    <span data-ttu-id="0cb3b-130">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-130">Click **Complete**.</span></span>
20.    <span data-ttu-id="0cb3b-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-131">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="0cb3b-132">Crie um formato de importação de dados</span><span class="sxs-lookup"><span data-stu-id="0cb3b-132">Create a format for data import</span></span>
1.    <span data-ttu-id="0cb3b-133">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-133">Click **Create configuration** to open the drop dialog.</span></span>
2.    <span data-ttu-id="0cb3b-134">No campo **Novo**, insira 'Formato baseado no modelo de dados. Modelo para importar arquivo xml'.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-134">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3.    <span data-ttu-id="0cb3b-135">No campo **Nome**, digite 'Formatar para importar arquivo xml'.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-135">In the **Name** field, type 'Format to import xml file'.</span></span>
4.    <span data-ttu-id="0cb3b-136">Selecione **Sim** no campo **Dá suporte à importação de dados**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-136">Select **Yes** in the **Supports data import** field.</span></span>
5.    <span data-ttu-id="0cb3b-137">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-137">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="0cb3b-138">Crie um formato para analisar o arquivo de entrada no formato xml</span><span class="sxs-lookup"><span data-stu-id="0cb3b-138">Design a format to parse incoming file in xml format</span></span>
1.    <span data-ttu-id="0cb3b-139">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-139">Click **Designer**.</span></span>
2.    <span data-ttu-id="0cb3b-140">Clique em **Adicionar raiz** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-140">Click **Add root** to open the drop dialog.</span></span>
3.    <span data-ttu-id="0cb3b-141">Na árvore, selecione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-141">In the tree, select **XML\Element**.</span></span>
4.    <span data-ttu-id="0cb3b-142">No campo **Nome**, digite 'raiz'.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-142">In the **Name** field, type 'root'.</span></span>
5.    <span data-ttu-id="0cb3b-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-143">Click **OK**.</span></span>
6.    <span data-ttu-id="0cb3b-144">Clique em **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-144">Click **Add** to open the drop dialog.</span></span>
7.    <span data-ttu-id="0cb3b-145">Na árvore, selecione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-145">In the tree, select **XML\Element**.</span></span>
8.    <span data-ttu-id="0cb3b-146">No campo **Nome**, digite 'documento'.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-146">In the **Name** field, type 'document'.</span></span>
9.    <span data-ttu-id="0cb3b-147">No campo **Multiplicidade**, selecione **Um muitos**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-147">In the **Multiplicity** field, select **One many**.</span></span>
10.    <span data-ttu-id="0cb3b-148">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-148">Click **OK**.</span></span>
11.    <span data-ttu-id="0cb3b-149">Na árvore, selecione **raiz\documento**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-149">In the tree, select **root\document**.</span></span>
12.    <span data-ttu-id="0cb3b-150">Clique em **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-150">Click **Add** to open the drop dialog.</span></span>
13.    <span data-ttu-id="0cb3b-151">Na árvore, selecione **XML\Attribute**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-151">In the tree, select **XML\Attribute**.</span></span>
14.    <span data-ttu-id="0cb3b-152">No campo **Nome**, digite 'ID'.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-152">In the **Name** field, type 'ID'.</span></span>
15.    <span data-ttu-id="0cb3b-153">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-153">Click **OK**.</span></span>
16.    <span data-ttu-id="0cb3b-154">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-154">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="0cb3b-155">Crie um mapeamento de formato para salvar informações analisadas modelo de dados</span><span class="sxs-lookup"><span data-stu-id="0cb3b-155">Design a format mapping to save parsed information to data model</span></span>
1. <span data-ttu-id="0cb3b-156">Clique em **Mapear formato para modelo**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-156">Click **Map format to model**.</span></span>
2. <span data-ttu-id="0cb3b-157">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-157">Click **New**.</span></span>
3. <span data-ttu-id="0cb3b-158">No campo **Definição**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-158">In the **Definition** field, enter or select a value.</span></span>
4. <span data-ttu-id="0cb3b-159">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-159">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="0cb3b-160">No campo **Nome**, digite 'Mapeamento'.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-160">In the **Name** field, type 'Mapping'.</span></span>
6. <span data-ttu-id="0cb3b-161">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-161">Click **Save**.</span></span>
7. <span data-ttu-id="0cb3b-162">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-162">Click **Designer**.</span></span>
8. <span data-ttu-id="0cb3b-163">Na árvore, expanda **formato**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-163">In the tree, expand **format**.</span></span>
9. <span data-ttu-id="0cb3b-164">Na árvore, expanda **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-164">In the tree, expand **format\root: XML Element(root)**.</span></span>
10.    <span data-ttu-id="0cb3b-165">Na árvore, selecione \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="0cb3b-165">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="0cb3b-166">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-166">(document)\*\*.</span></span>
11.    <span data-ttu-id="0cb3b-167">Clique em **Associar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-167">Click **Bind**.</span></span>
12.    <span data-ttu-id="0cb3b-168">Na árvore, expanda \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="0cb3b-168">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="0cb3b-169">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-169">(document)\*\*.</span></span>
13.    <span data-ttu-id="0cb3b-170">Na árvore, selecione \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="0cb3b-170">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="0cb3b-171">(documento)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-171">(document)\id\*\*.</span></span>
14.    <span data-ttu-id="0cb3b-172">Na árvore, expanda **List = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-172">In the tree, expand **List = format.root.document**.</span></span>
15.    <span data-ttu-id="0cb3b-173">Na árvore, selecione **List = format.root.document\Code**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-173">In the tree, select **List = format.root.document\Code**.</span></span>
16.    <span data-ttu-id="0cb3b-174">Clique em **Associar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-174">Click **Bind**.</span></span>
17.    <span data-ttu-id="0cb3b-175">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-175">Click **Save**.</span></span>
18.    <span data-ttu-id="0cb3b-176">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-176">Close the page.</span></span>
 
## <a name="run-format-mapping"></a><span data-ttu-id="0cb3b-177">Execute o mapeamento de formato</span><span class="sxs-lookup"><span data-stu-id="0cb3b-177">Run format mapping</span></span>
1. <span data-ttu-id="0cb3b-178">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-178">Click **Run**.</span></span>
2. <span data-ttu-id="0cb3b-179">Clique em **Procurar** e selecione **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-179">Click **Browse** and select **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="0cb3b-180">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-180">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="0cb3b-181">O arquivo selecionado não foi importado porque o design de formato supõe a existência do atributo 'id' para o elemento 'documento', mas o arquivo importado não contém esse atributo.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-181">The selected file has not been imported as the format design assumes the existence of 'id' attribute for the 'document' element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="0cb3b-182">Modifique a estrutura do formato para tratar o atributo xml como opcional</span><span class="sxs-lookup"><span data-stu-id="0cb3b-182">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="0cb3b-183">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-183">Close the page.</span></span>
2. <span data-ttu-id="0cb3b-184">Na árvore, expanda **raiz\documento**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-184">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="0cb3b-185">Na árvore, selecione **raiz\documento\id**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-185">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="0cb3b-186">Selecione **Sim** no campo **Cadeia de caracteres vazia para atributo ausente** .</span><span class="sxs-lookup"><span data-stu-id="0cb3b-186">Select **Yes** in the **Empty string for missing attribute** field.</span></span>
5. <span data-ttu-id="0cb3b-187">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-187">Click **Save**.</span></span>
 
## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="0cb3b-188">Execute o mapeamento de formato para testar alterações</span><span class="sxs-lookup"><span data-stu-id="0cb3b-188">Run format mapping to test changes</span></span>
1. <span data-ttu-id="0cb3b-189">Clique em **Mapear formato para modelo**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-189">Click **Map format to model**.</span></span>
2. <span data-ttu-id="0cb3b-190">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-190">Click **Run**.</span></span>
3. <span data-ttu-id="0cb3b-191">Clique em **Procurar** e selecione o arquivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-191">Click **Browse** and select the **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml** file.</span></span>
4. <span data-ttu-id="0cb3b-192">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-192">Click **OK**.</span></span>
5. <span data-ttu-id="0cb3b-193">Revise o arquivo gerado.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-193">Review the generated file.</span></span> 

> [!NOTE]
> <span data-ttu-id="0cb3b-194">O mesmo arquivo foi importado, já que o design do formato agora considera o atributo "id" para o elemento "document", como opcional.</span><span class="sxs-lookup"><span data-stu-id="0cb3b-194">The same file has been imported as the format design now consider the 'id' attribute for the 'document' element as optional.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]