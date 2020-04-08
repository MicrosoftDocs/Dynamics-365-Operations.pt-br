---
title: ER Criar uma configuração de formato (Novembro de 2016)
description: Este tópico explica como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE).
author: NickSelin
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af2899da843967bfaaa8f3c66906fc8e3765b573
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142492"
---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="4c027-103">ER Criar uma configuração de formato (Novembro de 2016)</span><span class="sxs-lookup"><span data-stu-id="4c027-103">ER Create a format configuration (November 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4c027-104">Este tópico explica como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="4c027-104">This topic explains how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="4c027-105">Esta configuração de formato irá definir o formato de documentos eletrônicos que são usados para processar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="4c027-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="4c027-106">Neste exemplo, você criará uma configuração de formato para a empresa de exemplo, Litware, Inc. Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento "Mapear modelo para as fontes de dados selecionadas".</span><span class="sxs-lookup"><span data-stu-id="4c027-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the "Map model to selected datasources" procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="4c027-107">Criar uma nova configuração de formato</span><span class="sxs-lookup"><span data-stu-id="4c027-107">Create a new format configuration</span></span>
1. <span data-ttu-id="4c027-108">Vá par **Administração da organização > Espaços de trabalho > Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="4c027-108">Go to **Organization administration > Workspaces > Electronic reporting**.</span></span>
2. <span data-ttu-id="4c027-109">Clique em **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="4c027-109">Click **Reporting configurations**.</span></span>
3. <span data-ttu-id="4c027-110">Na árvore, selecione **Pagamentos (modelo simplificado)**.</span><span class="sxs-lookup"><span data-stu-id="4c027-110">In the tree, select **Payments (simplified model)**.</span></span>
4. <span data-ttu-id="4c027-111">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4c027-111">Click **Create configuration** to open the drop dialog.</span></span>

 > [!NOTE]
 > <span data-ttu-id="4c027-112">Se não aparecer **Criar configuração**, você deverá habilitar o modo de design na página **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="4c027-112">If you don't see **Create configuration**, you must enable design mode on the **Electronic reporting parameters** page.</span></span> 
 
5. <span data-ttu-id="4c027-113">No campo **Novo**, insira **Formato baseado no modelo de dados PaymentModel**.</span><span class="sxs-lookup"><span data-stu-id="4c027-113">In the **New** field, enter **Format based on data model PaymentModel**.</span></span>
6. <span data-ttu-id="4c027-114">No campo **Nome**, digite **BACS (Reino Unido fictício)**.</span><span class="sxs-lookup"><span data-stu-id="4c027-114">In the **Name** field, type **BACS (UK fictitious)**.</span></span>
7. <span data-ttu-id="4c027-115">No campo **Descrição**, digite **Formato de pagamento de fornecedor BACS (Reino Unido fictício)**.</span><span class="sxs-lookup"><span data-stu-id="4c027-115">In the **Description** field, type **BACS vendor payment format (UK fictitious)**.</span></span>
    * <span data-ttu-id="4c027-116">O provedor de configuração ativo é automaticamente inserido aqui.</span><span class="sxs-lookup"><span data-stu-id="4c027-116">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="4c027-117">Este provedor será capaz de manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="4c027-117">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="4c027-118">Outros provedores podem usar esta configuração, mas não poderão mantê-la.</span><span class="sxs-lookup"><span data-stu-id="4c027-118">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="4c027-119">Um formato específico de documento eletrônico pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="4c027-119">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="4c027-120">Deixe este campo em branco se desejar selecionar um formato durante a execução.</span><span class="sxs-lookup"><span data-stu-id="4c027-120">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="4c027-121">No campo **Definição do modelo de dados**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4c027-121">In the **Data model definition** field, enter or select a value.</span></span>
9. <span data-ttu-id="4c027-122">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="4c027-122">Click **Create configuration**.</span></span> <span data-ttu-id="4c027-123">Uma nova configuração foi criada.</span><span class="sxs-lookup"><span data-stu-id="4c027-123">A new configuration has been created.</span></span> <span data-ttu-id="4c027-124">A versão de rascunho pode ser usada para armazenar o formato de design para gerenciar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="4c027-124">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-the-format-of-an-electronic-document"></a><span data-ttu-id="4c027-125">Projetar o formato de um documento eletrônico</span><span class="sxs-lookup"><span data-stu-id="4c027-125">Design the format of an electronic document</span></span>
1. <span data-ttu-id="4c027-126">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="4c027-126">Click **Designer**.</span></span>
2. <span data-ttu-id="4c027-127">Clique em **Adicionar raiz** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4c027-127">Click **Add root** to open the drop dialog.</span></span>
3. <span data-ttu-id="4c027-128">Na árvore, selecione **Comum\Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="4c027-128">In the tree, select **Common\File**.</span></span>
4. <span data-ttu-id="4c027-129">No campo **Nome**, digite **Xml**.</span><span class="sxs-lookup"><span data-stu-id="4c027-129">In the **Name** field, type **Xml**.</span></span>
5. <span data-ttu-id="4c027-130">No campo **Codificação**, digite **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="4c027-130">In the **Encoding** field, type **UTF-8**.</span></span>
6. <span data-ttu-id="4c027-131">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-131">Click **OK**.</span></span>
7. <span data-ttu-id="4c027-132">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4c027-132">Click **Add**.</span></span>
8. <span data-ttu-id="4c027-133">Na árvore, selecione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-133">In the tree, select **XML\Element**.</span></span>
9. <span data-ttu-id="4c027-134">No campo **Nome**, digite **Mensagem**.</span><span class="sxs-lookup"><span data-stu-id="4c027-134">In the **Name** field, type **Message**.</span></span>
10. <span data-ttu-id="4c027-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-135">Click **OK**.</span></span>
11. <span data-ttu-id="4c027-136">Na árvore, selecione **Xml\Mensagem**.</span><span class="sxs-lookup"><span data-stu-id="4c027-136">In the tree, select **Xml\Message**.</span></span>
12. <span data-ttu-id="4c027-137">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-137">Click **Add Element**.</span></span>
13. <span data-ttu-id="4c027-138">No campo **Nome**, digite **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="4c027-138">In the **Name** field, type **ProcessingDate**.</span></span>
14. <span data-ttu-id="4c027-139">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-139">Click **OK**.</span></span>
15. <span data-ttu-id="4c027-140">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-140">Click **Add Element**.</span></span>
16. <span data-ttu-id="4c027-141">No campo Nome, digite **MessageId**.</span><span class="sxs-lookup"><span data-stu-id="4c027-141">In the Name field, type **MessageId**.</span></span>
17. <span data-ttu-id="4c027-142">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-142">Click **OK**.</span></span>
18. <span data-ttu-id="4c027-143">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-143">Click **Add Element**.</span></span>
19. <span data-ttu-id="4c027-144">No campo **Nome**, digite **Pagamentos**.</span><span class="sxs-lookup"><span data-stu-id="4c027-144">In the **Name** field, type **Payments**.</span></span>
20. <span data-ttu-id="4c027-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-145">Click **OK**.</span></span>
21. <span data-ttu-id="4c027-146">Na árvore, selecione **Xml\Message\Payments**.</span><span class="sxs-lookup"><span data-stu-id="4c027-146">In the tree, select **Xml\Message\Payments**.</span></span>
22. <span data-ttu-id="4c027-147">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-147">Click **Add Element**.</span></span>
23. <span data-ttu-id="4c027-148">No campo **Nome**, digite **Item**.</span><span class="sxs-lookup"><span data-stu-id="4c027-148">In the **Name** field, type **Item**.</span></span>
24. <span data-ttu-id="4c027-149">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-149">Click **OK**.</span></span>
25. <span data-ttu-id="4c027-150">Na árvore, selecione **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="4c027-150">In the tree, select **Xml\Message\Payments\Item**.</span></span>
26. <span data-ttu-id="4c027-151">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4c027-151">Click **Add**.</span></span>
27. <span data-ttu-id="4c027-152">Na árvore, selecione **XML\Attribute**.</span><span class="sxs-lookup"><span data-stu-id="4c027-152">In the tree, select **XML\Attribute**.</span></span>
28. <span data-ttu-id="4c027-153">No campo Nome, digite **Id**.</span><span class="sxs-lookup"><span data-stu-id="4c027-153">In the Name field, type **Id**.</span></span>
29. <span data-ttu-id="4c027-154">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-154">Click **OK**.</span></span>
30. <span data-ttu-id="4c027-155">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4c027-155">Click **Add**.</span></span>
31. <span data-ttu-id="4c027-156">Na árvore, selecione **XML\Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-156">In the tree, select **XML\Element**.</span></span>
32. <span data-ttu-id="4c027-157">No campo Nome, digite **Fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="4c027-157">In the Name field, type **Vendor**.</span></span>
33. <span data-ttu-id="4c027-158">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-158">Click **OK**.</span></span>
34. <span data-ttu-id="4c027-159">Na árvore, selecione **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="4c027-159">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
35. <span data-ttu-id="4c027-160">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-160">Click **Add Element**.</span></span>
36. <span data-ttu-id="4c027-161">No campo Nome, digite **Nome**.</span><span class="sxs-lookup"><span data-stu-id="4c027-161">In the Name field, type **Name**.</span></span>
37. <span data-ttu-id="4c027-162">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-162">Click **OK**.</span></span>
38. <span data-ttu-id="4c027-163">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-163">Click **Add Element**.</span></span>
39. <span data-ttu-id="4c027-164">No campo **Nome**, digite **Banco**.</span><span class="sxs-lookup"><span data-stu-id="4c027-164">In the **Name** field, type **Bank**.</span></span>
40. <span data-ttu-id="4c027-165">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-165">Click **OK**.</span></span>
41. <span data-ttu-id="4c027-166">Na árvore, selecione **Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco**.</span><span class="sxs-lookup"><span data-stu-id="4c027-166">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank**.</span></span>
42. <span data-ttu-id="4c027-167">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-167">Click **Add Element**.</span></span>
43. <span data-ttu-id="4c027-168">No campo **Nome**, digite **RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="4c027-168">In the **Name** field, type **RoutingNumber**.</span></span>
44. <span data-ttu-id="4c027-169">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-169">Click **OK**.</span></span>
45. <span data-ttu-id="4c027-170">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-170">Click **Add Element**.</span></span>
46. <span data-ttu-id="4c027-171">No campo **Nome**, digite **AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="4c027-171">In the **Name** field, type **AccountNumber**.</span></span>
47. <span data-ttu-id="4c027-172">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-172">Click **OK**.</span></span>
48. <span data-ttu-id="4c027-173">Na árvore, selecione **Xml\Message\Payments\Item\Vendor**.</span><span class="sxs-lookup"><span data-stu-id="4c027-173">In the tree, select **Xml\Message\Payments\Item\Vendor**.</span></span>
49. <span data-ttu-id="4c027-174">Clique em **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="4c027-174">Click **Copy**.</span></span>
50. <span data-ttu-id="4c027-175">Na árvore, selecione **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="4c027-175">In the tree, select **Xml\Message\Payments\Item**.</span></span>
51. <span data-ttu-id="4c027-176">Clique em **Colar**.</span><span class="sxs-lookup"><span data-stu-id="4c027-176">Click **Paste**.</span></span>
52. <span data-ttu-id="4c027-177">No campo **Nome**, digite **Pagador**.</span><span class="sxs-lookup"><span data-stu-id="4c027-177">In the **Name** field, type **Payer**.</span></span>
53. <span data-ttu-id="4c027-178">Na árvore, selecione **Xml\Message\Payments\Item**.</span><span class="sxs-lookup"><span data-stu-id="4c027-178">In the tree, select **Xml\Message\Payments\Item**.</span></span>
54. <span data-ttu-id="4c027-179">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-179">Click **Add Element**.</span></span>
55. <span data-ttu-id="4c027-180">No campo **Nome**, digite **Moeda**.</span><span class="sxs-lookup"><span data-stu-id="4c027-180">In the **Name** field, type **Currency**.</span></span>
56. <span data-ttu-id="4c027-181">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-181">Click **OK**.</span></span>
57. <span data-ttu-id="4c027-182">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-182">Click **Add Element**.</span></span>
58. <span data-ttu-id="4c027-183">No campo **Nome**, digite **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="4c027-183">In the **Name** field, type **Description**.</span></span>
59. <span data-ttu-id="4c027-184">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-184">Click **OK**.</span></span>
60. <span data-ttu-id="4c027-185">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-185">Click **Add Element**.</span></span>
61. <span data-ttu-id="4c027-186">No campo Nome, digite **TransDate**.</span><span class="sxs-lookup"><span data-stu-id="4c027-186">In the Name field, type **TransDate**.</span></span>
62. <span data-ttu-id="4c027-187">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-187">Click **OK**.</span></span>
63. <span data-ttu-id="4c027-188">Clique em **Adicionar Elemento**.</span><span class="sxs-lookup"><span data-stu-id="4c027-188">Click **Add Element**.</span></span>
64. <span data-ttu-id="4c027-189">No campo Nome, digite **Valor**.</span><span class="sxs-lookup"><span data-stu-id="4c027-189">In the Name field, type **Amount**.</span></span>
65. <span data-ttu-id="4c027-190">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-190">Click **OK**.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="4c027-191">Preparar os componentes do formato para mapeamento aos elementos do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="4c027-191">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="4c027-192">Na árvore, selecione **Xml\Message\ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="4c027-192">In the tree, select **Xml\Message\ProcessingDate**.</span></span>
2. <span data-ttu-id="4c027-193">Clique em **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4c027-193">Click **Add** to open the drop dialog.</span></span>
3. <span data-ttu-id="4c027-194">Na árvore, selecione **Texto\DateTime**.</span><span class="sxs-lookup"><span data-stu-id="4c027-194">In the tree, select **Text\DateTime**.</span></span>
4. <span data-ttu-id="4c027-195">No campo **Formato**, digite **aaaa-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="4c027-195">In the **Format** field, type **yyyy-MM-dd**.</span></span>
5. <span data-ttu-id="4c027-196">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-196">Click **OK**.</span></span>
6. <span data-ttu-id="4c027-197">Na árvore, selecione **Xml\Message\Payments\Item\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="4c027-197">In the tree, select **Xml\Message\Payments\Item\TransDate**.</span></span>
7. <span data-ttu-id="4c027-198">Clique em **Adicionar DateTime.**</span><span class="sxs-lookup"><span data-stu-id="4c027-198">Click **Add DateTime**.</span></span>
8. <span data-ttu-id="4c027-199">No campo **Formato**, digite **aaaa-MM-dd**.</span><span class="sxs-lookup"><span data-stu-id="4c027-199">In the **Format** field, type **yyyy-MM-dd**.</span></span>
9. <span data-ttu-id="4c027-200">No campo do tipo **DateTime**, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="4c027-200">In the **DateTime** type field, select **Date**.</span></span>
10. <span data-ttu-id="4c027-201">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-201">Click **OK**.</span></span>
11. <span data-ttu-id="4c027-202">Na árvore, selecione **Xml\Message\MessageId**.</span><span class="sxs-lookup"><span data-stu-id="4c027-202">In the tree, select **Xml\Message\MessageId**.</span></span>
12. <span data-ttu-id="4c027-203">Clique em **Adicionar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="4c027-203">Click **Add** to open the drop dialog.</span></span>
13. <span data-ttu-id="4c027-204">Na árvore, selecione **Texto\Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4c027-204">In the tree, select **Text\String**.</span></span>
14. <span data-ttu-id="4c027-205">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-205">Click **OK**.</span></span>
15. <span data-ttu-id="4c027-206">Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Name**.</span><span class="sxs-lookup"><span data-stu-id="4c027-206">In the tree, select **Xml\Message\Payments\Item\Vendor\Name**.</span></span>
16. <span data-ttu-id="4c027-207">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4c027-207">Click **Add String**.</span></span>
17. <span data-ttu-id="4c027-208">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-208">Click **OK**.</span></span>
18. <span data-ttu-id="4c027-209">Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="4c027-209">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.</span></span>
19. <span data-ttu-id="4c027-210">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4c027-210">Click **Add String**.</span></span>
20. <span data-ttu-id="4c027-211">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-211">Click **OK**.</span></span>
21. <span data-ttu-id="4c027-212">Na árvore, selecione **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="4c027-212">In the tree, select **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.</span></span>
22. <span data-ttu-id="4c027-213">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4c027-213">Click **Add String**.</span></span>
23. <span data-ttu-id="4c027-214">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-214">Click **OK**.</span></span>
24. <span data-ttu-id="4c027-215">Na árvore, selecione **Xml\Message\Payments\Item\Payer\Name**.</span><span class="sxs-lookup"><span data-stu-id="4c027-215">In the tree, select **Xml\Message\Payments\Item\Payer\Name**.</span></span>
25. <span data-ttu-id="4c027-216">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4c027-216">Click **Add String**.</span></span>
26. <span data-ttu-id="4c027-217">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-217">Click **OK**.</span></span>
27. <span data-ttu-id="4c027-218">Na árvore, selecione **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span><span class="sxs-lookup"><span data-stu-id="4c027-218">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.</span></span>
28. <span data-ttu-id="4c027-219">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4c027-219">Click **Add String**.</span></span>
29. <span data-ttu-id="4c027-220">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-220">Click **OK**.</span></span>
30. <span data-ttu-id="4c027-221">Na árvore, selecione **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="4c027-221">In the tree, select **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.</span></span>
31. <span data-ttu-id="4c027-222">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4c027-222">Click **Add String**.</span></span>
32. <span data-ttu-id="4c027-223">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-223">Click **OK**.</span></span>
33. <span data-ttu-id="4c027-224">Na árvore, selecione **Xml\Message\Payments\Item\Currency**.</span><span class="sxs-lookup"><span data-stu-id="4c027-224">In the tree, select **Xml\Message\Payments\Item\Currency**.</span></span>
34. <span data-ttu-id="4c027-225">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4c027-225">Click **Add String**.</span></span>
35. <span data-ttu-id="4c027-226">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-226">Click **OK**.</span></span>
36. <span data-ttu-id="4c027-227">Na árvore, selecione **Xml\Message\Payments\Item\Description**.</span><span class="sxs-lookup"><span data-stu-id="4c027-227">In the tree, select **Xml\Message\Payments\Item\Description**.</span></span>
37. <span data-ttu-id="4c027-228">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4c027-228">Click **Add String**.</span></span>
38. <span data-ttu-id="4c027-229">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-229">Click **OK**.</span></span>
39. <span data-ttu-id="4c027-230">Na árvore, selecione **Xml\Message\Payments\Item\Amount**.</span><span class="sxs-lookup"><span data-stu-id="4c027-230">In the tree, select **Xml\Message\Payments\Item\Amount**.</span></span>
40. <span data-ttu-id="4c027-231">Clique em **Adicionar cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="4c027-231">Click **Add String**.</span></span>
41. <span data-ttu-id="4c027-232">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c027-232">Click **OK**.</span></span>
42. <span data-ttu-id="4c027-233">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4c027-233">Click **Save**.</span></span>
43. <span data-ttu-id="4c027-234">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4c027-234">Close the page.</span></span>

