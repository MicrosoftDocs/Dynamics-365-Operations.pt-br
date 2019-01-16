--- 
title: "ER Criar uma configuração de formato (Novembro de 2016)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE)."
author: NickSelin
manager: AnnBe
ms.date: 11/27/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 13469aad7fdcefb3a1706eec0527f29968e007eb
ms.openlocfilehash: 10511fe5b936135471b522fc7152a54686a3be87
ms.contentlocale: pt-br
ms.lasthandoff: 12/18/2018

---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="810ad-103">ER Criar uma configuração de formato (Novembro de 2016)</span><span class="sxs-lookup"><span data-stu-id="810ad-103">ER Create a format configuration (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="810ad-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="810ad-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="810ad-105">Esta configuração de formato irá definir o formato de documentos eletrônicos que são usados para processar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="810ad-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="810ad-106">Neste exemplo, você criará uma configuração de formato para a empresa de exemplo, Litware, Inc. Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento "mapear modelo para as fontes de dados selecionadas".</span><span class="sxs-lookup"><span data-stu-id="810ad-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="810ad-107">Criar uma nova configuração de formato</span><span class="sxs-lookup"><span data-stu-id="810ad-107">Create a new format configuration</span></span>
1. <span data-ttu-id="810ad-108">Vá par **Administração da organização > Espaços de trabalho > Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="810ad-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="810ad-109">Clique em **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="810ad-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="810ad-110">Na árvore, selecione **Pagamentos (modelo simplificado)**.</span><span class="sxs-lookup"><span data-stu-id="810ad-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="810ad-111">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="810ad-111">Click **Create configuration** to open the drop dialog.</span></span>
 > [!NOTE]
 > <span data-ttu-id="810ad-112">Se não aparecer **Criar configuração**, você deverá habilitar o modo de design na página **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="810ad-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
5. <span data-ttu-id="810ad-113">No campo **Novo**, insira **Formato baseado no modelo de dados PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="810ad-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="810ad-114">No campo **Nome**, digite **BACS (Reino Unido fictício)**.</span><span class="sxs-lookup"><span data-stu-id="810ad-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="810ad-115">No campo **Descrição**, digite **Formato de pagamento de fornecedor BACS (Reino Unido fictício)**.</span><span class="sxs-lookup"><span data-stu-id="810ad-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="810ad-116">O provedor de configuração ativo é automaticamente inserido aqui.</span><span class="sxs-lookup"><span data-stu-id="810ad-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="810ad-117">Este provedor será capaz de manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="810ad-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="810ad-118">Outros provedores podem usar esta configuração, mas não poderão mantê-la.</span><span class="sxs-lookup"><span data-stu-id="810ad-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="810ad-119">Um formato específico de documento eletrônico pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="810ad-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="810ad-120">Deixe este campo em branco se desejar selecionar um formato durante a execução.</span><span class="sxs-lookup"><span data-stu-id="810ad-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="810ad-121">No campo **Definição do modelo de dados**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="810ad-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="810ad-122">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="810ad-122">Click **Create configuration**.</span></span> <span data-ttu-id="810ad-123">Uma nova configuração foi criada.</span><span class="sxs-lookup"><span data-stu-id="810ad-123">A new configuration has been created.</span></span> <span data-ttu-id="810ad-124">A versão de rascunho pode ser usada para armazenar o formato de design para gerenciar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="810ad-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  
 > [!NOTE]
 > <span data-ttu-id="810ad-125">Se não aparecer **Criar configuração**, você deverá habilitar o modo de design na página **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="810ad-125">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span>


## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="810ad-126">Projetar o formato de um documento eletrônico</span><span class="sxs-lookup"><span data-stu-id="810ad-126">Design the format of an electronic document</span></span>
1. <span data-ttu-id="810ad-127">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="810ad-127">Click **Designer**.</span></span>
2. <span data-ttu-id="810ad-128">Clique em **Adicionar raiz** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="810ad-128">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="810ad-129">Na árvore, selecione **Comum\Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="810ad-129">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="810ad-130">No campo **Nome**, digite **Xml**.</span><span class="sxs-lookup"><span data-stu-id="810ad-130">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="810ad-131">No campo **Codificação**, digite **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="810ad-131">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="810ad-132">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-132">Click **OK**.</span></span>
7. <span data-ttu-id="810ad-133">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="810ad-133">Click **Add**.</span></span>
8. <span data-ttu-id="810ad-134">Na árvore, selecione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-134">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="810ad-135">No campo **Nome**, digite **Mensagem**.</span><span class="sxs-lookup"><span data-stu-id="810ad-135">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="810ad-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-136">Click **OK**.</span></span>
11. <span data-ttu-id="810ad-137">Na árvore, selecione **Xml\Mensagem**.</span><span class="sxs-lookup"><span data-stu-id="810ad-137">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="810ad-138">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-138">Click **Add Element**.</span></span>
13. <span data-ttu-id="810ad-139">No campo **Nome**, digite **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="810ad-139">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="810ad-140">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-140">Click **OK**.</span></span>
15. <span data-ttu-id="810ad-141">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-141">Click **Add Element**.</span></span>
16. <span data-ttu-id="810ad-142">No campo Nome, digite **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="810ad-142">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="810ad-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-143">Click **OK**.</span></span>
18. <span data-ttu-id="810ad-144">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-144">Click **Add Element**.</span></span>
19. <span data-ttu-id="810ad-145">No campo **Nome**, digite **Pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="810ad-145">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="810ad-146">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-146">Click **OK**.</span></span>
21. <span data-ttu-id="810ad-147">Na árvore, selecione **Xml\Message\Payments**.</span><span class="sxs-lookup"><span data-stu-id="810ad-147">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="810ad-148">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-148">Click **Add Element**.</span></span>
23. <span data-ttu-id="810ad-149">No campo **Nome**, digite **Item**.</span><span class="sxs-lookup"><span data-stu-id="810ad-149">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="810ad-150">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-150">Click **OK**.</span></span>
25. <span data-ttu-id="810ad-151">Na árvore, selecione **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="810ad-151">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="810ad-152">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="810ad-152">Click **Add**.</span></span>
27. <span data-ttu-id="810ad-153">Na árvore, selecione **XML\Attribute**.</span><span class="sxs-lookup"><span data-stu-id="810ad-153">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="810ad-154">No campo Nome, digite **Id**.</span><span class="sxs-lookup"><span data-stu-id="810ad-154">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="810ad-155">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-155">Click **OK**.</span></span>
30. <span data-ttu-id="810ad-156">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="810ad-156">Click **Add**.</span></span>
31. <span data-ttu-id="810ad-157">Na árvore, selecione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-157">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="810ad-158">No campo Nome, digite **Fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="810ad-158">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="810ad-159">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-159">Click **OK**.</span></span>
34. <span data-ttu-id="810ad-160">Na árvore, selecione **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="810ad-160">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="810ad-161">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-161">Click **Add Element**.</span></span>
36. <span data-ttu-id="810ad-162">No campo Nome, digite **Nome**.</span><span class="sxs-lookup"><span data-stu-id="810ad-162">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="810ad-163">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-163">Click **OK**.</span></span>
38. <span data-ttu-id="810ad-164">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-164">Click **Add Element**.</span></span>
39. <span data-ttu-id="810ad-165">No campo **Nome**, digite **Banco**.</span><span class="sxs-lookup"><span data-stu-id="810ad-165">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="810ad-166">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-166">Click **OK**.</span></span>
41. <span data-ttu-id="810ad-167">Na árvore, selecione **Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco**.</span><span class="sxs-lookup"><span data-stu-id="810ad-167">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="810ad-168">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-168">Click **Add Element**.</span></span>
43. <span data-ttu-id="810ad-169">No campo **Nome**, digite **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="810ad-169">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="810ad-170">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-170">Click **OK**.</span></span>
45. <span data-ttu-id="810ad-171">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-171">Click **Add Element**.</span></span>
46. <span data-ttu-id="810ad-172">No campo **Nome**, digite **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="810ad-172">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="810ad-173">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-173">Click **OK**.</span></span>
48. <span data-ttu-id="810ad-174">Na árvore, selecione **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="810ad-174">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="810ad-175">Clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="810ad-175">Click **Copy**.</span></span>
50. <span data-ttu-id="810ad-176">Na árvore, selecione **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="810ad-176">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="810ad-177">Clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="810ad-177">Click **Paste**.</span></span>
52. <span data-ttu-id="810ad-178">No campo **Nome**, digite **Pagador**.</span><span class="sxs-lookup"><span data-stu-id="810ad-178">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="810ad-179">Na árvore, selecione **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="810ad-179">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="810ad-180">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-180">Click **Add Element**.</span></span>
55. <span data-ttu-id="810ad-181">No campo **Nome**, digite **Moeda**.</span><span class="sxs-lookup"><span data-stu-id="810ad-181">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="810ad-182">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-182">Click **OK**.</span></span>
57. <span data-ttu-id="810ad-183">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-183">Click **Add Element**.</span></span>
58. <span data-ttu-id="810ad-184">No campo **Nome**, digite **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="810ad-184">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="810ad-185">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-185">Click **OK**.</span></span>
60. <span data-ttu-id="810ad-186">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-186">Click **Add Element**.</span></span>
61. <span data-ttu-id="810ad-187">No campo Nome, digite **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="810ad-187">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="810ad-188">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-188">Click **OK**.</span></span>
63. <span data-ttu-id="810ad-189">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="810ad-189">Click **Add Element**.</span></span>
64. <span data-ttu-id="810ad-190">No campo Nome, digite **Valor**.</span><span class="sxs-lookup"><span data-stu-id="810ad-190">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="810ad-191">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-191">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="810ad-192">Preparar os componentes do formato para mapeamento aos elementos do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="810ad-192">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="810ad-193">Na árvore, selecione **Xml\Message\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="810ad-193">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="810ad-194">Clique em **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="810ad-194">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="810ad-195">Na árvore, selecione **Texto\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="810ad-195">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="810ad-196">No campo **Formato**, digite **aaaa-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="810ad-196">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="810ad-197">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-197">Click **OK**.</span></span>
6. <span data-ttu-id="810ad-198">Na árvore, selecione **Xml\Message\Payments\Item\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="810ad-198">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="810ad-199">Clique em **Adicionar DateTime.**</span><span class="sxs-lookup"><span data-stu-id="810ad-199">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="810ad-200">No campo **Formato**, digite **aaaa-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="810ad-200">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="810ad-201">No campo do tipo **DateTime**, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="810ad-201">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="810ad-202">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-202">Click **OK**.</span></span>
11. <span data-ttu-id="810ad-203">Na árvore, selecione **Xml\Message\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="810ad-203">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="810ad-204">Clique em **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="810ad-204">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="810ad-205">Na árvore, selecione **Texto\Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="810ad-205">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="810ad-206">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-206">Click **OK**.</span></span>
15. <span data-ttu-id="810ad-207">Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Name**.</span><span class="sxs-lookup"><span data-stu-id="810ad-207">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="810ad-208">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="810ad-208">Click **Add String**.</span></span>
17. <span data-ttu-id="810ad-209">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-209">Click **OK**.</span></span>
18. <span data-ttu-id="810ad-210">Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="810ad-210">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="810ad-211">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="810ad-211">Click **Add String**.</span></span>
20. <span data-ttu-id="810ad-212">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-212">Click **OK**.</span></span>
21. <span data-ttu-id="810ad-213">Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="810ad-213">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="810ad-214">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="810ad-214">Click **Add String**.</span></span>
23. <span data-ttu-id="810ad-215">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-215">Click **OK**.</span></span>
24. <span data-ttu-id="810ad-216">Na árvore, selecione **Xml\Message\Payments\Item\Payer\Name**.</span><span class="sxs-lookup"><span data-stu-id="810ad-216">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="810ad-217">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="810ad-217">Click **Add String**.</span></span>
26. <span data-ttu-id="810ad-218">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-218">Click **OK**.</span></span>
27. <span data-ttu-id="810ad-219">Na árvore, selecione **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="810ad-219">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="810ad-220">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="810ad-220">Click **Add String**.</span></span>
29. <span data-ttu-id="810ad-221">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-221">Click **OK**.</span></span>
30. <span data-ttu-id="810ad-222">Na árvore, selecione **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="810ad-222">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="810ad-223">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="810ad-223">Click **Add String**.</span></span>
32. <span data-ttu-id="810ad-224">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-224">Click **OK**.</span></span>
33. <span data-ttu-id="810ad-225">Na árvore, selecione **Xml\Message\Payments\Item\Currency**.</span><span class="sxs-lookup"><span data-stu-id="810ad-225">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="810ad-226">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="810ad-226">Click **Add String**.</span></span>
35. <span data-ttu-id="810ad-227">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-227">Click **OK**.</span></span>
36. <span data-ttu-id="810ad-228">Na árvore, selecione **Xml\Message\Payments\Item\Description**.</span><span class="sxs-lookup"><span data-stu-id="810ad-228">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="810ad-229">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="810ad-229">Click **Add String**.</span></span>
38. <span data-ttu-id="810ad-230">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-230">Click **OK**.</span></span>
39. <span data-ttu-id="810ad-231">Na árvore, selecione **Xml\Message\Payments\Item\Amount**.</span><span class="sxs-lookup"><span data-stu-id="810ad-231">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="810ad-232">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="810ad-232">Click **Add String**.</span></span>
41. <span data-ttu-id="810ad-233">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="810ad-233">Click **OK**.</span></span>
42. <span data-ttu-id="810ad-234">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="810ad-234">Click **Save**.</span></span>
43. <span data-ttu-id="810ad-235">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="810ad-235">Close the page.</span></span>


