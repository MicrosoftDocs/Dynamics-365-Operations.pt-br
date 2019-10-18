---
title: Importar arquivos no formato XML com atributos opcionais
description: Este tópico fornece informações sobre como criar formatos de ER que especificam atributos XML para analisar documentos eletrônicos de entrada no formato XML.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: eb5d721784f45097ab466f75d43256495aac36ca
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182821"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a><span data-ttu-id="1f2e0-103">Importar arquivos no formato XML com atributos opcionais</span><span class="sxs-lookup"><span data-stu-id="1f2e0-103">Import files in XML format with optional attributes</span></span>

<span data-ttu-id="1f2e0-104">Você pode criar formatos de relatórios eletrônicos (ER) para analisar documentos eletrônicos de entrada no formato XML.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents in XML format.</span></span> <span data-ttu-id="1f2e0-105">Certos atributos de elementos XML podem ser especificados em formato de ER criado como opcional.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-105">Certain attributes of XML elements can be specified in designed ER format as optional.</span></span> <span data-ttu-id="1f2e0-106">Ele permitirá que você trate arquivos de entrada com e sem esses atributos XML corretamente.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-106">It will allow you to handle incoming files with and without such XML attributes properly.</span></span> <span data-ttu-id="1f2e0-107">Você pode usar o conteúdo desses arquivos para atualizar dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-107">You can then use the content from these files to update application data.</span></span>

<span data-ttu-id="1f2e0-108">Para saber mais sobre este recurso, conclua as etapas no tópico [Importação de arquivos RCS em formato XML com atributos opcionais](tasks/import-files-xml-format-optional-attributes.md), que faz parte do processo empresarial 7.5.4.3 Adquirir/Desenvolver componentes de serviço/solução de TI (10677).</span><span class="sxs-lookup"><span data-stu-id="1f2e0-108">To learn more about this feature, complete the steps in the topic, [RCS Import files in XML format with optional attributes](tasks/import-files-xml-format-optional-attributes.md), which is part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process.</span></span> <span data-ttu-id="1f2e0-109">É possível baixar os arquivos desta guia de tarefas e do exemplo associado no [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="1f2e0-109">You can download this task guide and associated sample files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>


| <span data-ttu-id="1f2e0-110">Descrição do conteúdo</span><span class="sxs-lookup"><span data-stu-id="1f2e0-110">Content description</span></span>       | <span data-ttu-id="1f2e0-111">Arquivo</span><span class="sxs-lookup"><span data-stu-id="1f2e0-111">File</span></span>                                                         |
|---------------------------|--------------------------------------------------------------|
| <span data-ttu-id="1f2e0-112">Arquivo de exemplo no formato XML</span><span class="sxs-lookup"><span data-stu-id="1f2e0-112">Sample file in XML format</span></span> | <span data-ttu-id="1f2e0-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span><span class="sxs-lookup"><span data-stu-id="1f2e0-113">IncomingDocumentToLearnHowToHandleOptionalAttributes.xml</span></span>     |
| <span data-ttu-id="1f2e0-114">Guias de tarefas</span><span class="sxs-lookup"><span data-stu-id="1f2e0-114">Task guide</span></span>                | <span data-ttu-id="1f2e0-115">RCS Importar arquivos no formato XML com atributos opcionais.axtr</span><span class="sxs-lookup"><span data-stu-id="1f2e0-115">RCS Import files in XML format with optional attributes.axtr</span></span> |


<span data-ttu-id="1f2e0-116">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato ER para importar arquivos no formato XML contendo atributos opcionais.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-116">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can design ER format configuration to import files in XML format containing optional attributes.</span></span> <span data-ttu-id="1f2e0-117">Para concluir essas etapas, primeiro conclua as etapas do procedimento [Criar um provedor de configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1f2e0-117">To complete these steps, you must first complete the steps in the procedure, [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="1f2e0-118">Antes de começar, baixe e salve localmente o arquivo IncomingDocumentToLearnHowToHandleOptionalAttributes.xml do Centro de Download da Microsoft (https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="1f2e0-118">Before you begin, download and save locally the IncomingDocumentToLearnHowToHandleOptionalAttributes.xml file from Microsoft Download Center (https://go.microsoft.com/fwlink/?linkid=874684 ).</span></span>

1. <span data-ttu-id="1f2e0-119">Vá para **Administração da organização** > **Espaços de trabalho** > **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-119">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span>
2. <span data-ttu-id="1f2e0-120">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-120">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="1f2e0-121">Caso não veja este provedor de configuração, conclua as etapas do tópico, [Criar um provedor de configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="1f2e0-121">If you don’t see this configuration provider, complete the steps in the topic, [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
3. <span data-ttu-id="1f2e0-122">Clique em **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-122">Click **Reporting configurations**.</span></span>

## <a name="create-a-new-data-model-configuration"></a><span data-ttu-id="1f2e0-123">Criar uma nova configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="1f2e0-123">Create a new data model configuration</span></span>
1. <span data-ttu-id="1f2e0-124">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-124">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="1f2e0-125">No campo **Nome**, digite 'Modelo para importar arquivo xml'.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-125">In the **Name** field, type 'Model to import xml file'.</span></span>
3. <span data-ttu-id="1f2e0-126">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-126">Click **Create configuration**.</span></span>
4. <span data-ttu-id="1f2e0-127">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-127">Click **Designer**.</span></span>
5. <span data-ttu-id="1f2e0-128">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-128">Click **New** to open the drop dialog.</span></span>
6. <span data-ttu-id="1f2e0-129">No campo **Nome**, digite 'Raiz'.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-129">In the **Name** field, type 'Root'.</span></span>
7. <span data-ttu-id="1f2e0-130">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-130">Click **Add**.</span></span>
8. <span data-ttu-id="1f2e0-131">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-131">Click **New** to open the drop dialog.</span></span>
9. <span data-ttu-id="1f2e0-132">No campo **Nome**, digite 'Lista'.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-132">In the **Name** field, type 'List'.</span></span>
10. <span data-ttu-id="1f2e0-133">No campo **Tipo de item**, selecione **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-133">In the **Item type** field, select **Record list**.</span></span>
11. <span data-ttu-id="1f2e0-134">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-134">Click **Add**.</span></span>
12. <span data-ttu-id="1f2e0-135">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-135">Click **New** to open the drop dialog.</span></span>
13. <span data-ttu-id="1f2e0-136">No campo **Nome**, digite 'Código'.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-136">In the **Name** field, type 'Code'.</span></span>
14. <span data-ttu-id="1f2e0-137">No campo **Tipo de item**, selecione **String**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-137">In the **Item type** field, select **String**.</span></span>
15. <span data-ttu-id="1f2e0-138">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-138">Click **Add**.</span></span>
16. <span data-ttu-id="1f2e0-139">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-139">Click **Save**.</span></span>
17. <span data-ttu-id="1f2e0-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-140">Close the page.</span></span>
18. <span data-ttu-id="1f2e0-141">Clique em **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-141">Click **Change status**.</span></span>
19. <span data-ttu-id="1f2e0-142">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-142">Click **Complete**.</span></span>
20. <span data-ttu-id="1f2e0-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-143">Click **OK**.</span></span>

## <a name="create-a-format-for-data-import"></a><span data-ttu-id="1f2e0-144">Crie um formato de importação de dados</span><span class="sxs-lookup"><span data-stu-id="1f2e0-144">Create a format for data import</span></span>
1. <span data-ttu-id="1f2e0-145">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-145">Click **Create configuration** to open the drop dialog.</span></span>
2. <span data-ttu-id="1f2e0-146">No campo **Novo**, insira 'Formato baseado no modelo de dados. Modelo para importar arquivo xml'.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-146">In the **New** field, enter 'Format based on data model Model to import xml file'.</span></span>
3. <span data-ttu-id="1f2e0-147">No campo **Nome**, digite 'Formatar para importar arquivo xml'.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-147">In the **Nam**e field, type 'Format to import xml file'.</span></span> 
4. <span data-ttu-id="1f2e0-148">Selecione **Sim** no campo **Dá suporte à importação de dados**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-148">Select **Yes** in the **Supports data import** field.</span></span>
5. <span data-ttu-id="1f2e0-149">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-149">Click **Create configuration**.</span></span>

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a><span data-ttu-id="1f2e0-150">Crie um formato para analisar o arquivo de entrada no formato xml</span><span class="sxs-lookup"><span data-stu-id="1f2e0-150">Design a format to parse incoming file in xml format</span></span>
1. <span data-ttu-id="1f2e0-151">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-151">Click **Designer**.</span></span>
2. <span data-ttu-id="1f2e0-152">Clique em **Adicionar raiz** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-152">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="1f2e0-153">Na árvore, selecione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-153">In the tree, select **XML\Element**.</span></span>
4. <span data-ttu-id="1f2e0-154">No campo **Nome**, digite 'raiz'.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-154">In the **Name** field, type 'root'.</span></span>
5. <span data-ttu-id="1f2e0-155">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-155">Click **OK**.</span></span>
6. <span data-ttu-id="1f2e0-156">Clique em **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-156">Click **Add** to open the drop dialog.</span></span>
7. <span data-ttu-id="1f2e0-157">Na árvore, selecione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-157">In the tree, select **XML\Element**.</span></span>
8. <span data-ttu-id="1f2e0-158">No campo **Nome**, digite 'documento'.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-158">In the **Name** field, type 'document'.</span></span>
9. <span data-ttu-id="1f2e0-159">No campo **Multiplicidade**, selecione **Um muitos**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-159">In the **Multiplicity** field, select **One many**.</span></span>
10. <span data-ttu-id="1f2e0-160">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-160">Click **OK**.</span></span>
11. <span data-ttu-id="1f2e0-161">Na árvore, selecione **raiz\documento**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-161">In the tree, select **root\document**.</span></span>
12. <span data-ttu-id="1f2e0-162">Clique em **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-162">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="1f2e0-163">Na árvore, selecione **XML\Attribute**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-163">In the tree, select **XML\Attribute**.</span></span>
14. <span data-ttu-id="1f2e0-164">No campo **Nome**, digite 'id'.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-164">In the **Name** field, type 'id'.</span></span>
15. <span data-ttu-id="1f2e0-165">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-165">Click **OK**.</span></span>
16. <span data-ttu-id="1f2e0-166">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-166">Click **Save**.</span></span>

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a><span data-ttu-id="1f2e0-167">Crie um mapeamento de formato para salvar informações analisadas modelo de dados</span><span class="sxs-lookup"><span data-stu-id="1f2e0-167">Design a format mapping to save parsed information to data model</span></span>
1.  <span data-ttu-id="1f2e0-168">Clique em **Mapear formato para modelo**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-168">Click **Map format to model**.</span></span>
2.  <span data-ttu-id="1f2e0-169">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-169">Click **New**.</span></span>
3.  <span data-ttu-id="1f2e0-170">No campo **Definição**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-170">In the **Definition** field, enter or select a value.</span></span>
4.  <span data-ttu-id="1f2e0-171">No campo **Nome**, digite 'Mapeamento'.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-171">In the **Name** field, type 'Mapping'.</span></span>
5.  <span data-ttu-id="1f2e0-172">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-172">Click **Save**.</span></span>
6.  <span data-ttu-id="1f2e0-173">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-173">Click **Designer**.</span></span>
7.  <span data-ttu-id="1f2e0-174">Na árvore, expanda **formato**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-174">In the tree, expand **format**.</span></span>
8.  <span data-ttu-id="1f2e0-175">Na árvore, expanda **format\root: XML Element(root)**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-175">In the tree, expand **format\root: XML Element(root)**.</span></span>
9.  <span data-ttu-id="1f2e0-176">Na árvore, selecione \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="1f2e0-176">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="1f2e0-177">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-177">(document)\*\*.</span></span>
10. <span data-ttu-id="1f2e0-178">Clique em **Associar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-178">Click **Bind**.</span></span>
11. <span data-ttu-id="1f2e0-179">Na árvore, expanda \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="1f2e0-179">In the tree, expand \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="1f2e0-180">(documento)\*\*.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-180">(document)\*\*.</span></span>
12. <span data-ttu-id="1f2e0-181">Na árvore, selecione \**format\root: XML Element(root)\document: XML Element 1..*</span><span class="sxs-lookup"><span data-stu-id="1f2e0-181">In the tree, select \**format\root: XML Element(root)\document: XML Element 1..*</span></span> <span data-ttu-id="1f2e0-182">(documento)\id\*\*.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-182">(document)\id\*\*.</span></span>
13. <span data-ttu-id="1f2e0-183">Na árvore, expanda **List = format.root.document**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-183">In the tree, expand **List = format.root.document**.</span></span>
14. <span data-ttu-id="1f2e0-184">Na árvore, selecione **List = format.root.document\Code**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-184">In the tree, select **List = format.root.document\Code**.</span></span>
15. <span data-ttu-id="1f2e0-185">Clique em **Associar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-185">Click **Bind**.</span></span>
16. <span data-ttu-id="1f2e0-186">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-186">Click **Save**.</span></span>
17. <span data-ttu-id="1f2e0-187">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-187">Close the page.</span></span>

## <a name="run-format-mapping"></a><span data-ttu-id="1f2e0-188">Execute o mapeamento de formato</span><span class="sxs-lookup"><span data-stu-id="1f2e0-188">Run format mapping</span></span>
1. <span data-ttu-id="1f2e0-189">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-189">Click **Run**.</span></span>
2. <span data-ttu-id="1f2e0-190">Clique em **Procurar** e selecione o arquivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-190">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
3. <span data-ttu-id="1f2e0-191">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-191">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="1f2e0-192">O arquivo selecionado não foi importado porque o design de formato supõe a existência do atributo 'id' para o elemento 'documento', mas o arquivo importado não contém esse atributo.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-192">The selected file has not been imported as the format design assumes the existence of ‘id’ attribute for the ‘document’ element, but the imported file contains no such attribute.</span></span>

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a><span data-ttu-id="1f2e0-193">Modifique a estrutura do formato para tratar o atributo xml como opcional</span><span class="sxs-lookup"><span data-stu-id="1f2e0-193">Modify format structure to handle xml attribute as optional</span></span>
1. <span data-ttu-id="1f2e0-194">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-194">Close the page.</span></span>
2. <span data-ttu-id="1f2e0-195">Na árvore, expanda **raiz\documento**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-195">In the tree, expand **root\document**.</span></span>
3. <span data-ttu-id="1f2e0-196">Na árvore, selecione **raiz\documento\id**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-196">In the tree, select **root\document\id**.</span></span>
4. <span data-ttu-id="1f2e0-197">No campo **Cadeia de caracteres vazia para atributo ausente**, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-197">In the **Empty string for missing attribute** field, select **Yes**.</span></span>
5. <span data-ttu-id="1f2e0-198">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-198">Click **Save**.</span></span>

## <a name="run-format-mapping-to-test-changes"></a><span data-ttu-id="1f2e0-199">Execute o mapeamento de formato para testar alterações</span><span class="sxs-lookup"><span data-stu-id="1f2e0-199">Run format mapping to test changes</span></span>
1. <span data-ttu-id="1f2e0-200">Clique em **Mapear formato para modelo**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-200">Click **Map format to model**.</span></span>
2. <span data-ttu-id="1f2e0-201">Clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-201">Click **Run**.</span></span>
3. <span data-ttu-id="1f2e0-202">Clique em **Procurar** e selecione o arquivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-202">Click **Browse** and select the file, **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.</span></span>
4. <span data-ttu-id="1f2e0-203">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-203">Click **OK**.</span></span>
5. <span data-ttu-id="1f2e0-204">Revise o arquivo gerado.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-204">Review the generated file.</span></span> <span data-ttu-id="1f2e0-205">Note que o mesmo arquivo foi importado, já que o design do formato agora considera o atributo 'id' para o elemento 'document' como opcional.</span><span class="sxs-lookup"><span data-stu-id="1f2e0-205">Note that same file has been imported as the format design now consider the ‘id’ attribute for the ‘document’ element as optional.</span></span>
