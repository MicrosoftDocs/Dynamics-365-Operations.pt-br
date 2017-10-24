--- 
title: "Configurar regras de comissão de vendas"
description: "Este procedimento mostra como configurar e habilitar cálculo e controle de vendas."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8d81765884f741443d1c0f5b0cb8bc545945e1a1
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-sales-commission-rules"></a><span data-ttu-id="23eaa-103">Configurar regras de comissão de vendas</span><span class="sxs-lookup"><span data-stu-id="23eaa-103">Set up sales commission rules</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="23eaa-104">Este procedimento mostra como configurar e habilitar cálculo e controle de vendas.</span><span class="sxs-lookup"><span data-stu-id="23eaa-104">This procedure shows you how to set up and enable sales commission calculation and tracking.</span></span> <span data-ttu-id="23eaa-105">Este procedimento mostra como criar grupos de comissão de cliente e item e depois como vincular um cliente e produto selecionado aos respectivos grupos.</span><span class="sxs-lookup"><span data-stu-id="23eaa-105">The procedure shows how to create both customer and item commission groups, and then how to link a selected customer and product to the respective groups.</span></span> <span data-ttu-id="23eaa-106">Esses grupos são usados na configuração do cálculo da comissão para criar uma combinação de cliente, item e representantes de venda que deve ser correspondida pela ordem de venda para que os vendedores tenham direito à comissão.</span><span class="sxs-lookup"><span data-stu-id="23eaa-106">Those groups are then used in the commission calculation setup to create a customer, item, and sales representatives combination that must be matched by the sales order to entitle the sales people to a commission.</span></span> <span data-ttu-id="23eaa-107">A criação de grupos de comissões de cliente e item é opcional, pois o cálculo da comissão também pode ser feito para um cliente e/ou item individuais.</span><span class="sxs-lookup"><span data-stu-id="23eaa-107">Creating customer and item commission groups are optional, as the calculation of commission can also be done for an individual customer and/or item.</span></span> <span data-ttu-id="23eaa-108">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="23eaa-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-commission-groups-and-commission-rates"></a><span data-ttu-id="23eaa-109">Defina grupos de comissões e taxas de comissões.</span><span class="sxs-lookup"><span data-stu-id="23eaa-109">Set up commission groups and commission rates</span></span>
1. <span data-ttu-id="23eaa-110">Vá para Vendas e marketing > Comissões > Grupos de cliente para comissão.</span><span class="sxs-lookup"><span data-stu-id="23eaa-110">Go to Sales and marketing > Commissions > Customer groups for commission.</span></span>
2. <span data-ttu-id="23eaa-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="23eaa-111">Click New.</span></span>
3. <span data-ttu-id="23eaa-112">No campo Grupo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="23eaa-112">In the Group field, type a value.</span></span>
4. <span data-ttu-id="23eaa-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="23eaa-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="23eaa-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="23eaa-114">Click Save.</span></span>
6. <span data-ttu-id="23eaa-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="23eaa-115">Close the page.</span></span>
7. <span data-ttu-id="23eaa-116">Vá para Vendas e marketing > Comissões > Grupos de itens.</span><span class="sxs-lookup"><span data-stu-id="23eaa-116">Go to Sales and marketing > Commissions > Item groups.</span></span>
8. <span data-ttu-id="23eaa-117">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="23eaa-117">Click New.</span></span>
9. <span data-ttu-id="23eaa-118">No campo Grupo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="23eaa-118">In the Group field, type a value.</span></span>
10. <span data-ttu-id="23eaa-119">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="23eaa-119">In the Name field, type a value.</span></span>
11. <span data-ttu-id="23eaa-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="23eaa-120">Close the page.</span></span>
12. <span data-ttu-id="23eaa-121">Vá para Vendas e marketing > Comissões > Grupos de vendas.</span><span class="sxs-lookup"><span data-stu-id="23eaa-121">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="23eaa-122">Um grupo de vendas por comissão especifica os funcionários em funções de representante de vendas que têm o direito a receber uma comissão quando um cliente associado ao grupo de vendas relevante compra determinados itens.</span><span class="sxs-lookup"><span data-stu-id="23eaa-122">A Commission sales group specifies the employees in sales representative roles who are eligible to receive a commission when a customer associated with the relevant sales group buys certain items.</span></span>  
    * <span data-ttu-id="23eaa-123">Na empresa de dados de demonstração USMF, há um grupo de vendas chamado "Reps de vendas EUA".</span><span class="sxs-lookup"><span data-stu-id="23eaa-123">In the USMF demo data company, there is a sales group called "Sales reps US."</span></span>  
13. <span data-ttu-id="23eaa-124">No Painel de Ação, clique em Geral.</span><span class="sxs-lookup"><span data-stu-id="23eaa-124">On the Action Pane, click General.</span></span>
14. <span data-ttu-id="23eaa-125">Clique em Rep. de vendas.</span><span class="sxs-lookup"><span data-stu-id="23eaa-125">Click Sales rep..</span></span>
    * <span data-ttu-id="23eaa-126">A página Rep. de vendas exibe uma lista de vendedores da empresa que estão associados a um grupo de comissões específico.</span><span class="sxs-lookup"><span data-stu-id="23eaa-126">The Sales rep. page displays a list of the company's sales people who are associated with a specific commission group.</span></span> <span data-ttu-id="23eaa-127">Você pode atribuir vários representantes de vendas ao mesmo grupo e definir suas respectivas cotas da taxa de comissão total como um valor percentual.</span><span class="sxs-lookup"><span data-stu-id="23eaa-127">You can assign multiple sales representatives to the same group and define their respective share of the total commission fee as a percentage value.</span></span> <span data-ttu-id="23eaa-128">A cota de comissão total de todos os funcionários não deve exceder 100.</span><span class="sxs-lookup"><span data-stu-id="23eaa-128">The total commission share across all employees must not exceed 100.</span></span>  
15. <span data-ttu-id="23eaa-129">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="23eaa-129">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="23eaa-130">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="23eaa-130">Click Edit.</span></span>
17. <span data-ttu-id="23eaa-131">Defina a Cota de comissão como '50'.</span><span class="sxs-lookup"><span data-stu-id="23eaa-131">Set Commission share to '50'.</span></span>
18. <span data-ttu-id="23eaa-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="23eaa-132">Click New.</span></span>
19. <span data-ttu-id="23eaa-133">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="23eaa-133">In the Name field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="23eaa-134">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="23eaa-134">Use the Quick Filter to find records.</span></span> <span data-ttu-id="23eaa-135">Por exemplo, filtre no campo Nome com um valor de 'Susan Burk'.</span><span class="sxs-lookup"><span data-stu-id="23eaa-135">For example, filter on the Name field with a value of 'Susan Burk'.</span></span>
21. <span data-ttu-id="23eaa-136">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="23eaa-136">Click Select.</span></span>
22. <span data-ttu-id="23eaa-137">Defina a Cota de comissão como '50'.</span><span class="sxs-lookup"><span data-stu-id="23eaa-137">Set Commission share to '50'.</span></span>
23. <span data-ttu-id="23eaa-138">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="23eaa-138">Click Save.</span></span>
24. <span data-ttu-id="23eaa-139">Vá para Vendas e marketing > Comissões > Cálculo de comissão.</span><span class="sxs-lookup"><span data-stu-id="23eaa-139">Go to Sales and marketing > Commissions > Commission calculation.</span></span>
    * <span data-ttu-id="23eaa-140">Na página Cálculo de comissão, você define a taxa de comissão que o funcionário receberá por transações de vendas quando elas contêm a combinação predefinida de cliente e produto.</span><span class="sxs-lookup"><span data-stu-id="23eaa-140">In the Commission calculation page you define the commission rate that the employee is to receive for a sales transaction when it contains the pre-set combination of customer and product.</span></span> <span data-ttu-id="23eaa-141">Como parte da configuração da taxa de comissão, você precisa especificar a base do cálculo de comissões e se descontos devem ser incluídos ou excluídos.</span><span class="sxs-lookup"><span data-stu-id="23eaa-141">As part of the commission rate setup, you must specify the commission calculation basis and whether it should include or exclude discounts.</span></span> <span data-ttu-id="23eaa-142">Você também pode inserir um período de validade para quando a comissão está ativa.</span><span class="sxs-lookup"><span data-stu-id="23eaa-142">You can also enter a validity period for when the commission rate is active.</span></span>  
25. <span data-ttu-id="23eaa-143">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="23eaa-143">Click New.</span></span>
26. <span data-ttu-id="23eaa-144">No campo Código de item, selecione 'Grupo'.</span><span class="sxs-lookup"><span data-stu-id="23eaa-144">In the Item code field, select 'Group'.</span></span>
27. <span data-ttu-id="23eaa-145">No campo Relação do item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="23eaa-145">In the Item relation field, click the drop-down button to open the lookup.</span></span>
28. <span data-ttu-id="23eaa-146">Na lista, localize e selecione o grupo que você criou antes.</span><span class="sxs-lookup"><span data-stu-id="23eaa-146">In the list, find and select the group that you created earlier.</span></span>
29. <span data-ttu-id="23eaa-147">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="23eaa-147">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="23eaa-148">No campo Código de cliente, selecione 'Grupo'.</span><span class="sxs-lookup"><span data-stu-id="23eaa-148">In the Customer code field, select 'Group'.</span></span>
31. <span data-ttu-id="23eaa-149">No campo Relação de cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="23eaa-149">In the Customer relation field, click the drop-down button to open the lookup.</span></span>
32. <span data-ttu-id="23eaa-150">Na lista, selecione o grupo que você definiu antes.</span><span class="sxs-lookup"><span data-stu-id="23eaa-150">In the list, select the group that you set up earlier.</span></span>
33. <span data-ttu-id="23eaa-151">No campo Relação de rep. de vendas, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="23eaa-151">In the Sales rep. relation field, click the drop-down button to open the lookup.</span></span>
34. <span data-ttu-id="23eaa-152">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="23eaa-152">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="23eaa-153">Mantenha a opção "Antes de desconto de linha".</span><span class="sxs-lookup"><span data-stu-id="23eaa-153">Keep the "Before line discount" option.</span></span>  
    * <span data-ttu-id="23eaa-154">Mantenha a opção "Receita" como a base para o cálculo do valor da comissão.</span><span class="sxs-lookup"><span data-stu-id="23eaa-154">Keep the "Revenue" option as the basis for commission value calculation.</span></span>    
35. <span data-ttu-id="23eaa-155">No campo Porcentagem de comissão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="23eaa-155">In the Commission percentage field, enter a number.</span></span>
36. <span data-ttu-id="23eaa-156">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="23eaa-156">Click Save.</span></span>

## <a name="setting-up-commission-posting"></a><span data-ttu-id="23eaa-157">Configuração de lançamento de comissões</span><span class="sxs-lookup"><span data-stu-id="23eaa-157">Setting up commission posting</span></span>
1. <span data-ttu-id="23eaa-158">Vá para Vendas e marketing > Comissões > Lançamento de comissão.</span><span class="sxs-lookup"><span data-stu-id="23eaa-158">Go to Sales and marketing > Commissions > Commission posting.</span></span>
    * <span data-ttu-id="23eaa-159">Taxas de comissão são pagáveis aos funcionários e, portanto, devem ser configuradas para assegurar um lançamento financeiro correto nas contas apropriadas da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="23eaa-159">Commission fees are payable to the employees and must therefore be set up to ensure correct financial posting to the appropriate accounts in the General ledger.</span></span> <span data-ttu-id="23eaa-160">Isso é feito na página Lançamento de comissão.</span><span class="sxs-lookup"><span data-stu-id="23eaa-160">This is done in the Commission posting page.</span></span> <span data-ttu-id="23eaa-161">Revise a configuração que está disponível para a empresa atual.</span><span class="sxs-lookup"><span data-stu-id="23eaa-161">Review the setup that is available for the current company.</span></span> <span data-ttu-id="23eaa-162">Normalmente, os valores de comissão são lançados em uma conta de despesas exclusiva e são compensados em uma conta a pagar exclusiva.</span><span class="sxs-lookup"><span data-stu-id="23eaa-162">Typically, the commission amounts are posted to a dedicated expense account and are offset to a dedicated payable account.</span></span> <span data-ttu-id="23eaa-163">Se não houver regras de lançamento de comissão configuradas, o sistema não poderá concluir o faturamento de uma ordem de venda com comissões elegíveis.</span><span class="sxs-lookup"><span data-stu-id="23eaa-163">If you don't have the commission posting rules set up, the system will fail to complete invoicing of a sales order which has eligible commissions.</span></span>  
2. <span data-ttu-id="23eaa-164">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="23eaa-164">Close the page.</span></span>

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a><span data-ttu-id="23eaa-165">Atribua um grupo de comissões a um cliente e produto</span><span class="sxs-lookup"><span data-stu-id="23eaa-165">Assign a commission group to a customer and a product</span></span>
1. <span data-ttu-id="23eaa-166">Vá para Vendas e marketing > Clientes >Todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="23eaa-166">Go to Sales and marketing > Customers > All customers.</span></span>
2. <span data-ttu-id="23eaa-167">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="23eaa-167">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="23eaa-168">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="23eaa-168">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="23eaa-169">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="23eaa-169">Click Edit.</span></span>
5. <span data-ttu-id="23eaa-170">Expanda a seção Padrões da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="23eaa-170">Expand the Sales order defaults section.</span></span>
6. <span data-ttu-id="23eaa-171">No campo Grupo de comissões, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="23eaa-171">In the Commission group field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="23eaa-172">Na lista, selecione o grupo que você criou antes.</span><span class="sxs-lookup"><span data-stu-id="23eaa-172">In the list, select the group that you created earlier.</span></span>
8. <span data-ttu-id="23eaa-173">No campo Grupo de vendas, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="23eaa-173">In the Sales group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="23eaa-174">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="23eaa-174">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="23eaa-175">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="23eaa-175">Click Save.</span></span>
11. <span data-ttu-id="23eaa-176">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="23eaa-176">Go to Product information management > Products > Released products.</span></span>
12. <span data-ttu-id="23eaa-177">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="23eaa-177">Use the Quick Filter to find records.</span></span> <span data-ttu-id="23eaa-178">Por exemplo, filtre no campo Número do item com um valor de 'T0020'.</span><span class="sxs-lookup"><span data-stu-id="23eaa-178">For example, filter on the Item number field with a value of 'T0020 '.</span></span>
13. <span data-ttu-id="23eaa-179">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="23eaa-179">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="23eaa-180">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="23eaa-180">Click Edit.</span></span>
15. <span data-ttu-id="23eaa-181">Expanda a seção Venda.</span><span class="sxs-lookup"><span data-stu-id="23eaa-181">Expand the Sell section.</span></span>
16. <span data-ttu-id="23eaa-182">No campo Grupo de comissões, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="23eaa-182">In the Commission group field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="23eaa-183">Na lista, selecione o grupo de comissões que você criou antes.</span><span class="sxs-lookup"><span data-stu-id="23eaa-183">In the list, select the commission group that you created earlier.</span></span>


