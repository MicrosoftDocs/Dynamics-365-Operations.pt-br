---
title: ER Componentes do mapa do formato criado para elementos do modelo de dados (Novembro de 2016)
description: O seguinte procedimento mostra como um usuário na função de Administrador do sistema ou desenvolvedor de Relatório eletrônico pode mapear elementos do modelo de dados para componentes da configuração de Relatório eletrônico (ER) criada, que define um formato de documento eletrônico para o domínio da empresa de pagamentos.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9a033853be17d6013daa5550ca9c061198bb0330
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184729"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a><span data-ttu-id="a7bf0-103">ER Componentes do mapa do formato criado para elementos do modelo de dados (Novembro de 2016)</span><span class="sxs-lookup"><span data-stu-id="a7bf0-103">ER Map components of the created format to data model elements (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a7bf0-104">O seguinte procedimento mostra como um usuário na função de Administrador do sistema ou desenvolvedor de Relatório eletrônico pode mapear elementos do modelo de dados para componentes da configuração de Relatório eletrônico (ER) criada, que define um formato de documento eletrônico para o domínio da empresa de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-104">The following procedure shows how a user in either the System administrator or Electronic reporting developer role can map data model elements to components of the created Electronic reporting (ER) configuration, which defines an electronic document format for the payments business domain.</span></span> <span data-ttu-id="a7bf0-105">Este formato será usado posteriormente para gerar documentos eletrônicos para processar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-105">This format will be used later to generate electronic documents for processing payments.</span></span> <span data-ttu-id="a7bf0-106">Neste exemplo, você irá criar uma configuração de formato para a empresa exemplo, ‘Litware, Inc.’.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-106">In this example, you will create a format configuration for the sample company, ‘Litware, Inc.’.</span></span> <span data-ttu-id="a7bf0-107">Essas etapas podem ser realizadas em qualquer empresa uma vez que configurações de RE são compartilhadas para todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-107">These steps can be performed in any company as ER configurations are shared for all companies.</span></span> <span data-ttu-id="a7bf0-108">Para concluir estas etapas, você deve primeiro concluir as etapas no guia de tarefas "Criar uma configuração de formato".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-108">To complete these steps, you must first complete the steps in the “Create a format configuration” task guide.</span></span>


## <a name="select-a-format-configuration"></a><span data-ttu-id="a7bf0-109">Selecione uma configuração de formato</span><span class="sxs-lookup"><span data-stu-id="a7bf0-109">Select a format configuration</span></span>
1. <span data-ttu-id="a7bf0-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="a7bf0-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="a7bf0-112">Na árvore, expanda "Pagamentos (modelo simplificado)".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-112">In the tree, expand 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="a7bf0-113">Na árvore, selecione "Pagamentos (modelo simplificado)\BACS (Reino Unido fictício)".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-113">In the tree, select 'Payments (simplified model)\BACS (UK fictitious)'.</span></span>
5. <span data-ttu-id="a7bf0-114">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-114">Click Designer.</span></span>

## <a name="map-format-components-to-data-model-elements"></a><span data-ttu-id="a7bf0-115">Mapear componentes do formato aos elementos do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="a7bf0-115">Map format components to data model elements</span></span>
1. <span data-ttu-id="a7bf0-116">Clique em Expandir/recolher.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-116">Click Expand/collapse.</span></span>
2. <span data-ttu-id="a7bf0-117">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-117">Click the Mapping tab.</span></span>
3. <span data-ttu-id="a7bf0-118">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-118">In the tree, expand 'model'.</span></span>
4. <span data-ttu-id="a7bf0-119">Na árvore, selecione "Xml\Mensagem\ProcessingDate\DateTime".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-119">In the tree, select 'Xml\Message\ProcessingDate\DateTime'.</span></span>
5. <span data-ttu-id="a7bf0-120">Na árvore, selecione "modelo\ProcessingDateTime".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-120">In the tree, select 'model\ProcessingDateTime'.</span></span>
6. <span data-ttu-id="a7bf0-121">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-121">Click Bind.</span></span>
7. <span data-ttu-id="a7bf0-122">Na árvore, selecione "Xml\Mensagem\MessageId\String".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-122">In the tree, select 'Xml\Message\MessageId\String'.</span></span>
8. <span data-ttu-id="a7bf0-123">Na árvore, selecione "modelo\MessageIdentification".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-123">In the tree, select 'model\MessageIdentification'.</span></span>
9. <span data-ttu-id="a7bf0-124">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-124">Click Bind.</span></span>
10. <span data-ttu-id="a7bf0-125">Na árvore, expanda 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-125">In the tree, expand 'model\Payments'.</span></span>
11. <span data-ttu-id="a7bf0-126">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Valor\String".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-126">In the tree, select 'Xml\Message\Payments\Item\Amount\String'.</span></span>
12. <span data-ttu-id="a7bf0-127">Na árvore, selecione "modelo\Pagamentos\InstructedAmount".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-127">In the tree, select 'model\Payments\InstructedAmount'.</span></span>
13. <span data-ttu-id="a7bf0-128">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-128">Click Bind.</span></span>
14. <span data-ttu-id="a7bf0-129">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\TransDate\DateTime".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-129">In the tree, select 'Xml\Message\Payments\Item\TransDate\DateTime'.</span></span>
15. <span data-ttu-id="a7bf0-130">Na árvore, selecione "modelo\Pagamentos\TransactionDate".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-130">In the tree, select 'model\Payments\TransactionDate'.</span></span>
16. <span data-ttu-id="a7bf0-131">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-131">Click Bind.</span></span>
17. <span data-ttu-id="a7bf0-132">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Descrição\String".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-132">In the tree, select 'Xml\Message\Payments\Item\Description\String'.</span></span>
18. <span data-ttu-id="a7bf0-133">Na árvore, selecione 'modelo\Pagamentos\Descrição'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-133">In the tree, select 'model\Payments\Description'.</span></span>
19. <span data-ttu-id="a7bf0-134">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-134">Click Bind.</span></span>
20. <span data-ttu-id="a7bf0-135">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Moeda\String".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-135">In the tree, select 'Xml\Message\Payments\Item\Currency\String'.</span></span>
21. <span data-ttu-id="a7bf0-136">Na árvore, selecione 'modelo\Pagamentos\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-136">In the tree, select 'model\Payments\Currency'.</span></span>
22. <span data-ttu-id="a7bf0-137">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-137">Click Bind.</span></span>
23. <span data-ttu-id="a7bf0-138">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Id".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-138">In the tree, select 'Xml\Message\Payments\Item\Id'.</span></span>
24. <span data-ttu-id="a7bf0-139">Na árvore, selecione "modelo\Pagamentos\End2EndID".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-139">In the tree, select 'model\Payments\End2EndID'.</span></span>
25. <span data-ttu-id="a7bf0-140">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-140">Click Bind.</span></span>
26. <span data-ttu-id="a7bf0-141">Na árvore, expanda 'modelo\Pagamentos\Credor'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-141">In the tree, expand 'model\Payments\Creditor'.</span></span>
27. <span data-ttu-id="a7bf0-142">Na árvore, expanda 'modelo\Pagamentos\Credor\Conta'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-142">In the tree, expand 'model\Payments\Creditor\Account'.</span></span>
28. <span data-ttu-id="a7bf0-143">Na árvore, expanda 'modelo\Pagamentos\Credor\Agente'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-143">In the tree, expand 'model\Payments\Creditor\Agent'.</span></span>
29. <span data-ttu-id="a7bf0-144">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Nome\String".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-144">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name\String'.</span></span>
30. <span data-ttu-id="a7bf0-145">Na árvore, selecione 'modelo\Pagamentos\Credor\Nome'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-145">In the tree, select 'model\Payments\Creditor\Name'.</span></span>
31. <span data-ttu-id="a7bf0-146">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-146">Click Bind.</span></span>
32. <span data-ttu-id="a7bf0-147">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\RoutingNumber\String".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-147">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\String'.</span></span>
33. <span data-ttu-id="a7bf0-148">Na árvore, selecione "modelo\Pagamentos\Credor\Agente\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-148">In the tree, select 'model\Payments\Creditor\Agent\RoutingNumber'.</span></span>
34. <span data-ttu-id="a7bf0-149">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-149">Click Bind.</span></span>
35. <span data-ttu-id="a7bf0-150">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\AccountNumber\String".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-150">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\String'.</span></span>
36. <span data-ttu-id="a7bf0-151">Na árvore, selecione 'modelo\Pagamentos\Credor\Conta\Número'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-151">In the tree, select 'model\Payments\Creditor\Account\Number'.</span></span>
37. <span data-ttu-id="a7bf0-152">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-152">Click Bind.</span></span>
38. <span data-ttu-id="a7bf0-153">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Nome\String".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-153">In the tree, select 'Xml\Message\Payments\Item\Payer\Name\String'.</span></span>
39. <span data-ttu-id="a7bf0-154">Na árvore, expanda 'modelo\Pagamentos\Devedor'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-154">In the tree, expand 'model\Payments\Debtor'.</span></span>
40. <span data-ttu-id="a7bf0-155">Na árvore, expanda 'modelo\Pagamentos\Devedor\Conta'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-155">In the tree, expand 'model\Payments\Debtor\Account'.</span></span>
41. <span data-ttu-id="a7bf0-156">Na árvore, expanda 'modelo\Pagamentos\Devedor\Agente'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-156">In the tree, expand 'model\Payments\Debtor\Agent'.</span></span>
42. <span data-ttu-id="a7bf0-157">Na árvore, selecione 'modelo\Pagamentos\Devedor\Nome'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-157">In the tree, select 'model\Payments\Debtor\Name'.</span></span>
43. <span data-ttu-id="a7bf0-158">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-158">Click Bind.</span></span>
44. <span data-ttu-id="a7bf0-159">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Banco\RoutingNumber\String".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-159">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\String'.</span></span>
45. <span data-ttu-id="a7bf0-160">Na árvore, selecione "modelo\Pagamentos\Devedor\Agente\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-160">In the tree, select 'model\Payments\Debtor\Agent\RoutingNumber'.</span></span>
46. <span data-ttu-id="a7bf0-161">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-161">Click Bind.</span></span>
47. <span data-ttu-id="a7bf0-162">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Banco\AccountNumber\String".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-162">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber\String'.</span></span>
48. <span data-ttu-id="a7bf0-163">Na árvore, selecione 'modelo\Pagamentos\Devedor\Conta\Número'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-163">In the tree, select 'model\Payments\Debtor\Account\Number'.</span></span>
49. <span data-ttu-id="a7bf0-164">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-164">Click Bind.</span></span>
50. <span data-ttu-id="a7bf0-165">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-165">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="a7bf0-166">Na árvore, selecione 'modelo\Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-166">In the tree, select 'model\Payments'.</span></span>
52. <span data-ttu-id="a7bf0-167">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-167">Click Bind.</span></span>
53. <span data-ttu-id="a7bf0-168">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-168">Click Save.</span></span>

## <a name="validate-format-mapping"></a><span data-ttu-id="a7bf0-169">Valide o mapeamento de formato</span><span class="sxs-lookup"><span data-stu-id="a7bf0-169">Validate format mapping</span></span>
1. <span data-ttu-id="a7bf0-170">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-170">Click Validate.</span></span>
    * <span data-ttu-id="a7bf0-171">Valide o novo mapeamento para garantir que todas as associações são aprovadas.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-171">Validate the new mapping to ensure that all bindings are okay.</span></span>  
2. <span data-ttu-id="a7bf0-172">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-172">Close the page.</span></span>

## <a name="change-status-of-the-current-version-of-format-configuration"></a><span data-ttu-id="a7bf0-173">Altere o status da versão atual da configuração de formato</span><span class="sxs-lookup"><span data-stu-id="a7bf0-173">Change status of the current version of format configuration</span></span>
    * <span data-ttu-id="a7bf0-174">Nas próximas etapas, você irá alterar o status da configuração de formato de Rascunho para Concluído para torná-la disponível para geração de documento de pagamento.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-174">In the next steps, you’ll change the status of the format configuration from Draft to Completed to make it available for payment document generation.</span></span>  
1. <span data-ttu-id="a7bf0-175">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-175">Click Change status.</span></span>
2. <span data-ttu-id="a7bf0-176">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-176">Click Complete.</span></span>
3. <span data-ttu-id="a7bf0-177">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-177">In the Description field, type a value.</span></span>
    * <span data-ttu-id="a7bf0-178">Por exemplo, "versão 1".</span><span class="sxs-lookup"><span data-stu-id="a7bf0-178">For example, 'version 1'.</span></span>  
4. <span data-ttu-id="a7bf0-179">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-179">Click OK.</span></span>
5. <span data-ttu-id="a7bf0-180">Selecione a versão concluída da configuração atual.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-180">Select completed version of the current configuration.</span></span>
    * <span data-ttu-id="a7bf0-181">Observe que a configuração será salva como versão concluída 1.1: versão 1 do formato baseado na versão 1 do modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-181">Note that the configuration is saved as completed version 1.1: version 1 of the format based on the version 1 of the data model.</span></span>  

## <a name="define-effective-date-for-completed-version-of-format"></a><span data-ttu-id="a7bf0-182">Definir a data efetiva para a versão concluída do formato</span><span class="sxs-lookup"><span data-stu-id="a7bf0-182">Define effective date for completed version of format</span></span>
    * <span data-ttu-id="a7bf0-183">Cada versão do formato pode ser configurada como disponível para uso a partir de uma data determinada.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-183">Each format version can be configured as available for usage starting from a certain date.</span></span> <span data-ttu-id="a7bf0-184">Quando mais de uma versão do formato estiver ativa em uma determinada data, o formato mais recente (com base no número de versão) será selecionado para o uso.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-184">When more than one format version is active on a certain date, the latest format (based on version number) will be selected for usage.</span></span> <span data-ttu-id="a7bf0-185">O valor da data da sessão é utilizado na seleção da versão apropriada.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-185">The session date value is used for proper version selection.</span></span>  

## <a name="restrict-access-to-created-format-from-companies"></a><span data-ttu-id="a7bf0-186">Restrinja o acesso ao formato criado pelas empresas</span><span class="sxs-lookup"><span data-stu-id="a7bf0-186">Restrict access to created format from companies</span></span>
1. <span data-ttu-id="a7bf0-187">Expanda a seção Códigos ISO de país/região.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-187">Expand the ISO Country/region codes section.</span></span>
    * <span data-ttu-id="a7bf0-188">Cada acesso ao formato pode ser restringido através da identificação de países/regiões específicos nos quais um formato é aplicável.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-188">Each format access can be restricted by identifying particular countries/regions in which a format is applicable.</span></span> <span data-ttu-id="a7bf0-189">Quando a lista de países/regiões de um formato específico estiver vazia, esse formato poderá ser usado em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-189">When the list of countries/regions for particular format is empty, this format can be used in any company.</span></span> <span data-ttu-id="a7bf0-190">Quando alguns códigos de países/regiões ISO forem inseridos na lista de países/regiões, o formato somente pode ser usado nas empresas, se os endereços principais estiverem no país/região.</span><span class="sxs-lookup"><span data-stu-id="a7bf0-190">When some ISO country/region codes are inserted in the list of countries/regions, the format can only be use in companies if the primary address is in the country/region.</span></span>  
