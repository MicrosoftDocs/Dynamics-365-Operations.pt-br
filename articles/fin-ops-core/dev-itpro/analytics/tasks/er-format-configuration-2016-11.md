---
title: ER Criar uma configuração de formato (Novembro de 2016)
description: Este tópico explica como criar uma configuração de formato para relatórios eletrônicos (ER).
author: NickSelin
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46686b9e4f6197f565a324a9d03cbb695b6a933b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749060"
---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="4a5ee-103">ER Criar uma configuração de formato (Novembro de 2016)</span><span class="sxs-lookup"><span data-stu-id="4a5ee-103">ER Create a format configuration (November 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4a5ee-104">Este tópico explica como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="4a5ee-104">This topic explains how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="4a5ee-105">Esta configuração de formato irá definir o formato de documentos eletrônicos que são usados para processar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="4a5ee-106">Neste exemplo, você criará uma configuração de formato para a empresa de exemplo, Litware, Inc. Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento "Mapear modelo para as fontes de dados selecionadas".</span><span class="sxs-lookup"><span data-stu-id="4a5ee-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Map model to selected datasources" procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="4a5ee-107">Criar uma nova configuração de formato</span><span class="sxs-lookup"><span data-stu-id="4a5ee-107">Create a new format configuration</span></span>
1. <span data-ttu-id="4a5ee-108">Vá par **Administração da organização > Espaços de trabalho > Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="4a5ee-109">Clique em **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="4a5ee-110">Na árvore, selecione **Pagamentos (modelo simplificado)**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="4a5ee-111">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="4a5ee-112">Se não aparecer **Criar configuração**, você deverá habilitar o modo de design na página **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="4a5ee-113">No campo **Novo**, insira **Formato baseado no modelo de dados PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="4a5ee-114">No campo **Nome**, digite **BACS (Reino Unido fictício)**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="4a5ee-115">No campo **Descrição**, digite **Formato de pagamento de fornecedor BACS (Reino Unido fictício)**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="4a5ee-116">O provedor de configuração ativo é automaticamente inserido aqui.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="4a5ee-117">Este provedor será capaz de manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="4a5ee-118">Outros provedores podem usar esta configuração, mas não poderão mantê-la.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="4a5ee-119">Um formato específico de documento eletrônico pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="4a5ee-120">Deixe este campo em branco se desejar selecionar um formato durante a execução.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="4a5ee-121">No campo **Definição do modelo de dados**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="4a5ee-122">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-122">Click **Create configuration**.</span></span> <span data-ttu-id="4a5ee-123">Uma nova configuração foi criada.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-123">A new configuration has been created.</span></span> <span data-ttu-id="4a5ee-124">A versão de rascunho pode ser usada para armazenar o formato de design para gerenciar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="4a5ee-125">Projetar o formato de um documento eletrônico</span><span class="sxs-lookup"><span data-stu-id="4a5ee-125">Design the format of an electronic document</span></span>
1. <span data-ttu-id="4a5ee-126">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-126">Click **Designer**.</span></span>
2. <span data-ttu-id="4a5ee-127">Clique em **Adicionar raiz** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-127">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="4a5ee-128">Na árvore, selecione **Comum\Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-128">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="4a5ee-129">No campo **Nome**, digite **Xml**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-129">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="4a5ee-130">No campo **Codificação**, digite **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-130">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="4a5ee-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-131">Click **OK**.</span></span>
7. <span data-ttu-id="4a5ee-132">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-132">Click **Add**.</span></span>
8. <span data-ttu-id="4a5ee-133">Na árvore, selecione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-133">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="4a5ee-134">No campo **Nome**, digite **Mensagem**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-134">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="4a5ee-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-135">Click **OK**.</span></span>
11. <span data-ttu-id="4a5ee-136">Na árvore, selecione **Xml\Mensagem**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-136">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="4a5ee-137">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-137">Click **Add Element**.</span></span>
13. <span data-ttu-id="4a5ee-138">No campo **Nome**, digite **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-138">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="4a5ee-139">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-139">Click **OK**.</span></span>
15. <span data-ttu-id="4a5ee-140">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-140">Click **Add Element**.</span></span>
16. <span data-ttu-id="4a5ee-141">No campo Nome, digite **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-141">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="4a5ee-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-142">Click **OK**.</span></span>
18. <span data-ttu-id="4a5ee-143">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-143">Click **Add Element**.</span></span>
19. <span data-ttu-id="4a5ee-144">No campo **Nome**, digite **Pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-144">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="4a5ee-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-145">Click **OK**.</span></span>
21. <span data-ttu-id="4a5ee-146">Na árvore, selecione **Xml\Message\Payments**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-146">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="4a5ee-147">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-147">Click **Add Element**.</span></span>
23. <span data-ttu-id="4a5ee-148">No campo **Nome**, digite **Item**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-148">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="4a5ee-149">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-149">Click **OK**.</span></span>
25. <span data-ttu-id="4a5ee-150">Na árvore, selecione **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-150">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="4a5ee-151">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-151">Click **Add**.</span></span>
27. <span data-ttu-id="4a5ee-152">Na árvore, selecione **XML\Attribute**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-152">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="4a5ee-153">No campo Nome, digite **Id**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-153">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="4a5ee-154">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-154">Click **OK**.</span></span>
30. <span data-ttu-id="4a5ee-155">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-155">Click **Add**.</span></span>
31. <span data-ttu-id="4a5ee-156">Na árvore, selecione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-156">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="4a5ee-157">No campo Nome, digite **Fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-157">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="4a5ee-158">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-158">Click **OK**.</span></span>
34. <span data-ttu-id="4a5ee-159">Na árvore, selecione **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-159">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="4a5ee-160">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-160">Click **Add Element**.</span></span>
36. <span data-ttu-id="4a5ee-161">No campo Nome, digite **Nome**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-161">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="4a5ee-162">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-162">Click **OK**.</span></span>
38. <span data-ttu-id="4a5ee-163">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-163">Click **Add Element**.</span></span>
39. <span data-ttu-id="4a5ee-164">No campo **Nome**, digite **Banco**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-164">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="4a5ee-165">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-165">Click **OK**.</span></span>
41. <span data-ttu-id="4a5ee-166">Na árvore, selecione **Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-166">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="4a5ee-167">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-167">Click **Add Element**.</span></span>
43. <span data-ttu-id="4a5ee-168">No campo **Nome**, digite **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-168">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="4a5ee-169">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-169">Click **OK**.</span></span>
45. <span data-ttu-id="4a5ee-170">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-170">Click **Add Element**.</span></span>
46. <span data-ttu-id="4a5ee-171">No campo **Nome**, digite **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-171">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="4a5ee-172">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-172">Click **OK**.</span></span>
48. <span data-ttu-id="4a5ee-173">Na árvore, selecione **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-173">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="4a5ee-174">Clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-174">Click **Copy**.</span></span>
50. <span data-ttu-id="4a5ee-175">Na árvore, selecione **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-175">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="4a5ee-176">Clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-176">Click **Paste**.</span></span>
52. <span data-ttu-id="4a5ee-177">No campo **Nome**, digite **Pagador**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-177">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="4a5ee-178">Na árvore, selecione **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-178">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="4a5ee-179">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-179">Click **Add Element**.</span></span>
55. <span data-ttu-id="4a5ee-180">No campo **Nome**, digite **Moeda**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-180">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="4a5ee-181">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-181">Click **OK**.</span></span>
57. <span data-ttu-id="4a5ee-182">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-182">Click **Add Element**.</span></span>
58. <span data-ttu-id="4a5ee-183">No campo **Nome**, digite **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-183">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="4a5ee-184">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-184">Click **OK**.</span></span>
60. <span data-ttu-id="4a5ee-185">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-185">Click **Add Element**.</span></span>
61. <span data-ttu-id="4a5ee-186">No campo Nome, digite **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-186">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="4a5ee-187">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-187">Click **OK**.</span></span>
63. <span data-ttu-id="4a5ee-188">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-188">Click **Add Element**.</span></span>
64. <span data-ttu-id="4a5ee-189">No campo Nome, digite **Valor**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-189">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="4a5ee-190">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-190">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="4a5ee-191">Preparar os componentes do formato para mapeamento aos elementos do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="4a5ee-191">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="4a5ee-192">Na árvore, selecione **Xml\Message\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-192">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="4a5ee-193">Clique em **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-193">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="4a5ee-194">Na árvore, selecione **Texto\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-194">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="4a5ee-195">No campo **Formato**, digite **aaaa-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-195">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="4a5ee-196">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-196">Click **OK**.</span></span>
6. <span data-ttu-id="4a5ee-197">Na árvore, selecione **Xml\Message\Payments\Item\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-197">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="4a5ee-198">Clique em **Adicionar DateTime.**</span><span class="sxs-lookup"><span data-stu-id="4a5ee-198">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="4a5ee-199">No campo **Formato**, digite **aaaa-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-199">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="4a5ee-200">No campo do tipo **DateTime**, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-200">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="4a5ee-201">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-201">Click **OK**.</span></span>
11. <span data-ttu-id="4a5ee-202">Na árvore, selecione **Xml\Message\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-202">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="4a5ee-203">Clique em **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-203">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="4a5ee-204">Na árvore, selecione **Texto\Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-204">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="4a5ee-205">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-205">Click **OK**.</span></span>
15. <span data-ttu-id="4a5ee-206">Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Name**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-206">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="4a5ee-207">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-207">Click **Add String**.</span></span>
17. <span data-ttu-id="4a5ee-208">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-208">Click **OK**.</span></span>
18. <span data-ttu-id="4a5ee-209">Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-209">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="4a5ee-210">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-210">Click **Add String**.</span></span>
20. <span data-ttu-id="4a5ee-211">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-211">Click **OK**.</span></span>
21. <span data-ttu-id="4a5ee-212">Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-212">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="4a5ee-213">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-213">Click **Add String**.</span></span>
23. <span data-ttu-id="4a5ee-214">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-214">Click **OK**.</span></span>
24. <span data-ttu-id="4a5ee-215">Na árvore, selecione **Xml\Message\Payments\Item\Payer\Name**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-215">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="4a5ee-216">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-216">Click **Add String**.</span></span>
26. <span data-ttu-id="4a5ee-217">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-217">Click **OK**.</span></span>
27. <span data-ttu-id="4a5ee-218">Na árvore, selecione **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-218">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="4a5ee-219">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-219">Click **Add String**.</span></span>
29. <span data-ttu-id="4a5ee-220">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-220">Click **OK**.</span></span>
30. <span data-ttu-id="4a5ee-221">Na árvore, selecione **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-221">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="4a5ee-222">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-222">Click **Add String**.</span></span>
32. <span data-ttu-id="4a5ee-223">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-223">Click **OK**.</span></span>
33. <span data-ttu-id="4a5ee-224">Na árvore, selecione **Xml\Message\Payments\Item\Currency**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-224">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="4a5ee-225">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-225">Click **Add String**.</span></span>
35. <span data-ttu-id="4a5ee-226">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-226">Click **OK**.</span></span>
36. <span data-ttu-id="4a5ee-227">Na árvore, selecione **Xml\Message\Payments\Item\Description**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-227">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="4a5ee-228">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-228">Click **Add String**.</span></span>
38. <span data-ttu-id="4a5ee-229">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-229">Click **OK**.</span></span>
39. <span data-ttu-id="4a5ee-230">Na árvore, selecione **Xml\Message\Payments\Item\Amount**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-230">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="4a5ee-231">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-231">Click **Add String**.</span></span>
41. <span data-ttu-id="4a5ee-232">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-232">Click **OK**.</span></span>
42. <span data-ttu-id="4a5ee-233">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-233">Click **Save**.</span></span>
43. <span data-ttu-id="4a5ee-234">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4a5ee-234">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]