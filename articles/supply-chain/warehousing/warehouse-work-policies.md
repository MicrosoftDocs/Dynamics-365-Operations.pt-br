---
title: "Políticas de trabalho de depósito"
description: "As políticas de trabalho de depósito determinam se o trabalho de depósito é criado por processos de depósito na fabricação, com base em tipo de ordem de trabalho, local do estoque e produto."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c2d72509b0dc4d0cea5b4f2478ae7f8fc163e78c
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="warehouse-work-policies"></a><span data-ttu-id="7d94c-103">Políticas de trabalho de depósito</span><span class="sxs-lookup"><span data-stu-id="7d94c-103">Warehouse work policies</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="7d94c-104">As políticas de trabalho de depósito no Microsoft Dynamics 365 for Finance and Operations determinam se o trabalho de depósito é criado por processos de depósito na fabricação, com base em tipo de ordem de trabalho, local do estoque e produto.</span><span class="sxs-lookup"><span data-stu-id="7d94c-104">Warehouse work policies in Microsoft Dynamics 365 for Finance and Operations control whether warehouse work is created by warehouse processes in manufacturing, based on work order type, inventory location, and product.</span></span>

<span data-ttu-id="7d94c-105">Esta política de trabalho controla se o trabalho de depósito é criado para os processos de depósito na fabricação.</span><span class="sxs-lookup"><span data-stu-id="7d94c-105">This work policy controls whether warehouse work is created for warehouse processes in manufacturing.</span></span> <span data-ttu-id="7d94c-106">Você pode configurar a política de trabalho usando uma combinação de **tipos de ordem de trabalho**, **localização de estoque** e um **produto**.</span><span class="sxs-lookup"><span data-stu-id="7d94c-106">You can set up the work policy by using a combination of **work order types**, an **inventory location**, and a **product**.</span></span> <span data-ttu-id="7d94c-107">Por exemplo, o produto L0101 é reportado como terminado para o local de saída 001.</span><span class="sxs-lookup"><span data-stu-id="7d94c-107">For example, product L0101 is reported as finished to output location 001.</span></span> <span data-ttu-id="7d94c-108">O bem acabado é posteriormente consumido noutra ordem de produção no local de saída 001.</span><span class="sxs-lookup"><span data-stu-id="7d94c-108">The finished good is later consumed in another production order at output location 001.</span></span> <span data-ttu-id="7d94c-109">Nesse caso, você pode configurar uma política de trabalho para impedir que o trabalho para produtos terminados colocados de lado seja criado quando você relata o produto L0101 como concluído para o local de saída 001.</span><span class="sxs-lookup"><span data-stu-id="7d94c-109">In this case, you can set up a work policy to prevent the work for finished goods put-away from being created when you report product L0101 as finished to output location 001.</span></span> <span data-ttu-id="7d94c-110">A política de trabalho é uma entidade individual que pode ser descrita pelas seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="7d94c-110">The work policy is an individual entity that can be described through the following information:</span></span>

-   <span data-ttu-id="7d94c-111">**Nome da política de trabalho**(o identificador exclusivo da política de trabalho)</span><span class="sxs-lookup"><span data-stu-id="7d94c-111">**Work policy name** (the unique identifier of the work policy)</span></span>
-   <span data-ttu-id="7d94c-112">**Tipos de ordem de trabalho** e **Método de criação de trabalho**</span><span class="sxs-lookup"><span data-stu-id="7d94c-112">**Work order types** and **Work creation method**</span></span>
-   <span data-ttu-id="7d94c-113">**Localizações de estoque**</span><span class="sxs-lookup"><span data-stu-id="7d94c-113">**Inventory locations**</span></span>
-   <span data-ttu-id="7d94c-114">**Produtos**</span><span class="sxs-lookup"><span data-stu-id="7d94c-114">**Products**</span></span>

## <a name="work-order-types"></a><span data-ttu-id="7d94c-115">Tipos de ordem de trabalho</span><span class="sxs-lookup"><span data-stu-id="7d94c-115">Work order types</span></span>
<span data-ttu-id="7d94c-116">Você pode selecionar os seguintes tipos de ordem de trabalho:</span><span class="sxs-lookup"><span data-stu-id="7d94c-116">You can select the following work order types:</span></span>

-   <span data-ttu-id="7d94c-117">Armazenamento de mercadorias acabadas</span><span class="sxs-lookup"><span data-stu-id="7d94c-117">Finished goods put away</span></span>
-   <span data-ttu-id="7d94c-118">Armazenamento de coproduto e subproduto</span><span class="sxs-lookup"><span data-stu-id="7d94c-118">Co-product and by-product put away</span></span>
-   <span data-ttu-id="7d94c-119">Separação de matéria-prima</span><span class="sxs-lookup"><span data-stu-id="7d94c-119">Raw material picking</span></span>

<span data-ttu-id="7d94c-120">O campo **Método de criação de trabalho** tem o valor **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="7d94c-120">The **Work creation method** field has the value **Never**.</span></span> <span data-ttu-id="7d94c-121">Esse valor indica que a política de trabalho impedirá que o trabalho de depósito seja criado para o tipo de ordem de trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="7d94c-121">This value indicates that the work policy will prevent warehouse work from being created for the selected work order type.</span></span>

## <a name="inventory-locations"></a><span data-ttu-id="7d94c-122">Localizações de estoque</span><span class="sxs-lookup"><span data-stu-id="7d94c-122">Inventory locations</span></span>
<span data-ttu-id="7d94c-123">Você pode selecionar uma localização à qual a política de trabalho seja aplicável.</span><span class="sxs-lookup"><span data-stu-id="7d94c-123">You can select a location that the work policy applies to.</span></span> <span data-ttu-id="7d94c-124">Se nenhuma localização for associada à política de trabalho, a política de trabalho não será aplicável a nenhum processo.</span><span class="sxs-lookup"><span data-stu-id="7d94c-124">If no location is associated with a work policy, the work policy doesn’t apply to any processes.</span></span> <span data-ttu-id="7d94c-125">Na página **Localizações**, é possível marcar ou cancelar a seleção da política de trabalho para uma localização específica.</span><span class="sxs-lookup"><span data-stu-id="7d94c-125">On the **Locations** page, you can also select or cancel the selection of the work policy for a specific location.</span></span>

## <a name="products"></a><span data-ttu-id="7d94c-126">Produtos</span><span class="sxs-lookup"><span data-stu-id="7d94c-126">Products</span></span>
<span data-ttu-id="7d94c-127">Você pode selecionar um produto ao qual a política de trabalho seja aplicável.</span><span class="sxs-lookup"><span data-stu-id="7d94c-127">You can select a product that the work policy applies to.</span></span> <span data-ttu-id="7d94c-128">Você pode aplicar a política de trabalho a todos os produtos ou a produtos selecionados.</span><span class="sxs-lookup"><span data-stu-id="7d94c-128">You can apply the work policy to either all products or selected products.</span></span>

## <a name="example"></a><span data-ttu-id="7d94c-129">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7d94c-129">Example</span></span>
<span data-ttu-id="7d94c-130">No exemplo a seguir, há duas ordens de produção, PRD-001 e PRD-00*2*.</span><span class="sxs-lookup"><span data-stu-id="7d94c-130">In the following example, there are two production orders, PRD-001 and PRD-00*2*.</span></span> <span data-ttu-id="7d94c-131">A ordem de produção PRD-001 tem uma operação que é chamada **Montagem**, em que o produto SC1 está sendo relatado como acabado para a localização O1.</span><span class="sxs-lookup"><span data-stu-id="7d94c-131">Production order PRD-001 has an operation that is named **Assembly**, where product SC1 is being reported as finished to location O1.</span></span> <span data-ttu-id="7d94c-132">A ordem de produção PRD-002 tem uma operação que é chamada **Pintura** e consome o produto SC1 da localização O1.</span><span class="sxs-lookup"><span data-stu-id="7d94c-132">Production order PRD-002 has an operation that is named **Painting** and consumes product SC1 from location O1.</span></span> <span data-ttu-id="7d94c-133">A ordem de produção PRD-002 também consome a matéria-prima RM1 da localização O1.</span><span class="sxs-lookup"><span data-stu-id="7d94c-133">Production order PRD-002 also consumes raw material RM1 from location O1.</span></span> <span data-ttu-id="7d94c-134">A RM1 é armazenada na localização BULK-001 e será separada para a localização O1 pelo trabalho de depósito para a separação de matéria-prima.</span><span class="sxs-lookup"><span data-stu-id="7d94c-134">RM1 is stored in warehouse location BULK-001 and will be picked to location O1 by warehouse work for raw material picking.</span></span> <span data-ttu-id="7d94c-135">O trabalho de separação será gerado quando a produção PRD-002 for liberada.</span><span class="sxs-lookup"><span data-stu-id="7d94c-135">The picking work is generated when production PRD-002 is released.</span></span> 

<span data-ttu-id="7d94c-136">[![Políticas de trabalho de depósito](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span><span class="sxs-lookup"><span data-stu-id="7d94c-136">[![Warehouse work policies](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)</span></span> 

<span data-ttu-id="7d94c-137">Quando você planejar configurar uma política de trabalho de depósito para este cenário, considere as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="7d94c-137">When you plan to configure a warehouse work policy for this scenario, you should consider the following information:</span></span>

-   <span data-ttu-id="7d94c-138">O trabalho de depósito para o armazenamento de mercadorias acabadas não é necessário quando você relatar o produto SC1 como acabado da ordem de produção PRD-001 para a localização O1.</span><span class="sxs-lookup"><span data-stu-id="7d94c-138">Warehouse work for finished goods put-away isn’t required when you report product SC1 as finished from production order PRD-001 to location O1.</span></span> <span data-ttu-id="7d94c-139">Isso ocorre porque a operação **Pintura** para a ordem de produção PRD-002 consome o produto SC1 na mesma localização.</span><span class="sxs-lookup"><span data-stu-id="7d94c-139">This is because the **Painting** operation for production order PRD-002 consumes SC1 at the same location.</span></span>
-   <span data-ttu-id="7d94c-140">O trabalho de depósito para a separação de matérias-primas é necessário para mover a matéria-prima RM1 da localização de depósito BULK-001 para a localização O1.</span><span class="sxs-lookup"><span data-stu-id="7d94c-140">Warehouse work for raw material picking is required in order to move raw material RM1 from warehouse location BULK-001 to location O1.</span></span>

<span data-ttu-id="7d94c-141">Veja um exemplo da política de trabalho que você pode configurar com base nestas considerações.</span><span class="sxs-lookup"><span data-stu-id="7d94c-141">Here is an example of the work policy that you can set up, based on these considerations.</span></span>


|                                       |                                       |
|---------------------------------------|---------------------------------------|
| <span data-ttu-id="7d94c-142"><strong>Nome da política de trabalho</strong></span><span class="sxs-lookup"><span data-stu-id="7d94c-142"><strong>Work policy name</strong></span></span><br> | <span data-ttu-id="7d94c-143"><strong>Tipos de ordem de trabalho</strong></span><span class="sxs-lookup"><span data-stu-id="7d94c-143"><strong>Work order types</strong></span></span><br> |
|         <span data-ttu-id="7d94c-144">Nenhum armazenamento de 01</span><span class="sxs-lookup"><span data-stu-id="7d94c-144">No put away 01     \`</span></span>          |     <span data-ttu-id="7d94c-145">- Armazenamento de mercadorias acabadas</span><span class="sxs-lookup"><span data-stu-id="7d94c-145">- Finished good put away</span></span><br>      |
|                                       |    <span data-ttu-id="7d94c-146"><strong>Localizações</strong></span><span class="sxs-lookup"><span data-stu-id="7d94c-146"><strong>Locations</strong></span></span><br>     |
|                                       |                 <span data-ttu-id="7d94c-147">- O1</span><span class="sxs-lookup"><span data-stu-id="7d94c-147">- O1</span></span>                  |
|                                       |    <span data-ttu-id="7d94c-148"><strong>Produtos</strong></span><span class="sxs-lookup"><span data-stu-id="7d94c-148"><strong>Products</strong></span></span> <br>     |
|                                       |                 <span data-ttu-id="7d94c-149">- SC1</span><span class="sxs-lookup"><span data-stu-id="7d94c-149">- SC1</span></span>                 |

<span data-ttu-id="7d94c-150">Os procedimentos a seguir fornecem instruções passo a passo sobre como configurar a política de trabalho de depósito para este cenário.</span><span class="sxs-lookup"><span data-stu-id="7d94c-150">The following procedures provide step-by-step instructions about how to set up the warehouse work policy for this scenario.</span></span> <span data-ttu-id="7d94c-151">Uma configuração de exemplo mostrando como relatar uma ordem de produção como acabada para uma localização que não seja controlada por placa de licença também é descrita.</span><span class="sxs-lookup"><span data-stu-id="7d94c-151">A sample setup showing how to report a production order as finished to a location that isn’t license plate–controlled is also described.</span></span>

## <a name="set-up-a-warehouse-work-policy"></a><span data-ttu-id="7d94c-152">Configurar uma política de trabalho de depósito</span><span class="sxs-lookup"><span data-stu-id="7d94c-152">Set up a warehouse work policy</span></span>
<span data-ttu-id="7d94c-153">Os processos de depósito nem sempre incluem o trabalho do depósito.</span><span class="sxs-lookup"><span data-stu-id="7d94c-153">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="7d94c-154">Ao definir uma diretiva de trabalho, você pode impedir a criação de trabalho para a separação de matéria-prima e o separar as mercadorias concluídas para um conjunto de produtos em locais específicos.</span><span class="sxs-lookup"><span data-stu-id="7d94c-154">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="7d94c-155">A empresa de dados de demonstração USMF foi usada para criar este procedimento.</span><span class="sxs-lookup"><span data-stu-id="7d94c-155">The USMF demo data company was used to create this procedure.</span></span> 

<span data-ttu-id="7d94c-156">ETAPAS (21)</span><span class="sxs-lookup"><span data-stu-id="7d94c-156">STEPS (21)</span></span>

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| <span data-ttu-id="7d94c-157">1.</span><span class="sxs-lookup"><span data-stu-id="7d94c-157">1.</span></span>  | <span data-ttu-id="7d94c-158">Vá para Gerenciamento de depósito &gt; Configuração &gt; Trabalho &gt; Políticas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7d94c-158">Go to Warehouse management &gt; Setup &gt; Work &gt; Work policies.</span></span>        |
| <span data-ttu-id="7d94c-159">2.</span><span class="sxs-lookup"><span data-stu-id="7d94c-159">2.</span></span>  | <span data-ttu-id="7d94c-160">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7d94c-160">Click New.</span></span>                                                                 |
| <span data-ttu-id="7d94c-161">3.</span><span class="sxs-lookup"><span data-stu-id="7d94c-161">3.</span></span>  | <span data-ttu-id="7d94c-162">No campo Nome de política de trabalho, digite "Sem trabalhos ausentes".</span><span class="sxs-lookup"><span data-stu-id="7d94c-162">In the Work policy name field, type 'No put-away work'.</span></span>                    |
| <span data-ttu-id="7d94c-163">4.</span><span class="sxs-lookup"><span data-stu-id="7d94c-163">4.</span></span>  | <span data-ttu-id="7d94c-164">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7d94c-164">Click Save.</span></span>                                                                |
| <span data-ttu-id="7d94c-165">5.</span><span class="sxs-lookup"><span data-stu-id="7d94c-165">5.</span></span>  | <span data-ttu-id="7d94c-166">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7d94c-166">Click Add.</span></span>                                                                 |
| <span data-ttu-id="7d94c-167">6.</span><span class="sxs-lookup"><span data-stu-id="7d94c-167">6.</span></span>  | <span data-ttu-id="7d94c-168">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7d94c-168">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="7d94c-169">7.</span><span class="sxs-lookup"><span data-stu-id="7d94c-169">7.</span></span>  | <span data-ttu-id="7d94c-170">No campo Tipo de ordem de trabalho, selecione as mercadorias “Concluiu mercadorias dadas”.</span><span class="sxs-lookup"><span data-stu-id="7d94c-170">In the Work order type field, select 'Finished goods put away'.</span></span>            |
| <span data-ttu-id="7d94c-171">8.</span><span class="sxs-lookup"><span data-stu-id="7d94c-171">8.</span></span>  | <span data-ttu-id="7d94c-172">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7d94c-172">Click Add.</span></span>                                                                 |
| <span data-ttu-id="7d94c-173">9.</span><span class="sxs-lookup"><span data-stu-id="7d94c-173">9.</span></span>  | <span data-ttu-id="7d94c-174">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7d94c-174">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="7d94c-175">10.</span><span class="sxs-lookup"><span data-stu-id="7d94c-175">10.</span></span> | <span data-ttu-id="7d94c-176">No campo Tipo de ordem de trabalho, selecione "Coproduto e subproduto cedido".</span><span class="sxs-lookup"><span data-stu-id="7d94c-176">In the Work order type field, select 'Co-product and by-product put away'.</span></span> |
| <span data-ttu-id="7d94c-177">11.</span><span class="sxs-lookup"><span data-stu-id="7d94c-177">11.</span></span> | <span data-ttu-id="7d94c-178">Expanda a seção Localizações de estoque.</span><span class="sxs-lookup"><span data-stu-id="7d94c-178">Expand the Inventory locations section.</span></span>                                    |
| <span data-ttu-id="7d94c-179">12.</span><span class="sxs-lookup"><span data-stu-id="7d94c-179">12.</span></span> | <span data-ttu-id="7d94c-180">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7d94c-180">Click Add.</span></span>                                                                 |
| <span data-ttu-id="7d94c-181">13.</span><span class="sxs-lookup"><span data-stu-id="7d94c-181">13.</span></span> | <span data-ttu-id="7d94c-182">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7d94c-182">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="7d94c-183">14.</span><span class="sxs-lookup"><span data-stu-id="7d94c-183">14.</span></span> | <span data-ttu-id="7d94c-184">Na lista Depósito, insira "51".</span><span class="sxs-lookup"><span data-stu-id="7d94c-184">In the Warehouse list, enter '51'.</span></span>                                         |
| <span data-ttu-id="7d94c-185">15.</span><span class="sxs-lookup"><span data-stu-id="7d94c-185">15.</span></span> | <span data-ttu-id="7d94c-186">No campo Local, insira ou selecione "001".</span><span class="sxs-lookup"><span data-stu-id="7d94c-186">In the Location field, enter or select '001'.</span></span>                              |
| <span data-ttu-id="7d94c-187">16.</span><span class="sxs-lookup"><span data-stu-id="7d94c-187">16.</span></span> | <span data-ttu-id="7d94c-188">Expanda a seção Produtos.</span><span class="sxs-lookup"><span data-stu-id="7d94c-188">Expand the Products section.</span></span>                                               |
| <span data-ttu-id="7d94c-189">17.</span><span class="sxs-lookup"><span data-stu-id="7d94c-189">17.</span></span> | <span data-ttu-id="7d94c-190">No campo Seleção do produto, selecione "Selecionado".</span><span class="sxs-lookup"><span data-stu-id="7d94c-190">In the Product selection field, select 'Selected'.</span></span>                         |
| <span data-ttu-id="7d94c-191">18.</span><span class="sxs-lookup"><span data-stu-id="7d94c-191">18.</span></span> | <span data-ttu-id="7d94c-192">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7d94c-192">Click Add.</span></span>                                                                 |
| <span data-ttu-id="7d94c-193">19.</span><span class="sxs-lookup"><span data-stu-id="7d94c-193">19.</span></span> | <span data-ttu-id="7d94c-194">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7d94c-194">In the list, mark the selected row.</span></span>                                        |
| <span data-ttu-id="7d94c-195">20.</span><span class="sxs-lookup"><span data-stu-id="7d94c-195">20.</span></span> | <span data-ttu-id="7d94c-196">No campo Número do item, insira ou selecione "L0101".</span><span class="sxs-lookup"><span data-stu-id="7d94c-196">In the Item number field, enter or select 'L0101'.</span></span>                         |
| <span data-ttu-id="7d94c-197">21.</span><span class="sxs-lookup"><span data-stu-id="7d94c-197">21.</span></span> | <span data-ttu-id="7d94c-198">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7d94c-198">Click Save.</span></span>                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a><span data-ttu-id="7d94c-199">Relatar uma ordem de produção como acabada para uma localização que não seja controlada por placa de licença</span><span class="sxs-lookup"><span data-stu-id="7d94c-199">Report a production order as finished to a location that isn’t license plate–controlled</span></span>
<span data-ttu-id="7d94c-200">Este procedimento mostra um exemplo de como relatar uma ordem de produção como acabada para uma localização que não seja controlada por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="7d94c-200">This procedure shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="7d94c-201">Uma diretiva de trabalho aplicável é o pré-requisito para esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="7d94c-201">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="7d94c-202">O procedimento anterior mostra a configuração da política de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7d94c-202">The previous procedure shows the setup of the work policy.</span></span> 

<span data-ttu-id="7d94c-203">ETAPAS (25)</span><span class="sxs-lookup"><span data-stu-id="7d94c-203">STEPS (25)</span></span>

<table>
<tbody>
<tr>
<td colspan="3"><span data-ttu-id="7d94c-204"><strong>Subtarefa: Configurar uma localização de saída.</strong></span><span class="sxs-lookup"><span data-stu-id="7d94c-204"><strong>Sub-task: Set up an output location.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="7d94c-205">Vá para Administração da organização &gt; Recursos &gt; Grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="7d94c-205">Go to Organization administration &gt; Resources &gt; Resource groups.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="7d94c-206">Na lista, selecione grupo de recursos &#39;5102&#39;.</span><span class="sxs-lookup"><span data-stu-id="7d94c-206">In the list, select resource group &#39;5102&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="7d94c-207">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="7d94c-207">Click Edit.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="7d94c-208">No campo Depósito de saída, insira &#39;51&#39;.</span><span class="sxs-lookup"><span data-stu-id="7d94c-208">In the Output warehouse field, enter &#39;51&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="7d94c-209">No campo Local de saída, insira &#39;001&#39;.</span><span class="sxs-lookup"><span data-stu-id="7d94c-209">In the Output location field, enter &#39;001&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="7d94c-210">O local 001 não é um local controlado por código de licença.</span><span class="sxs-lookup"><span data-stu-id="7d94c-210">Location 001 isn&#39;t a license plate–controlled location.</span></span> <span data-ttu-id="7d94c-211">Você pode configurar um local de saída em branco da licença não aplicável somente se uma diretiva de trabalho existir para o local.</span><span class="sxs-lookup"><span data-stu-id="7d94c-211">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span></td>
</tr>
<tr>
<td colspan="3"><span data-ttu-id="7d94c-212"><strong>Subtarefa: Criar uma ordem de produção e relatar como concluída.</strong></span><span class="sxs-lookup"><span data-stu-id="7d94c-212"><strong>Sub-task: Create a production order and report it as finished.</strong></span></span></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td><span data-ttu-id="7d94c-213">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7d94c-213">Close the page.</span></span></td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td><span data-ttu-id="7d94c-214">Vá para Controle de produção &gt; Ordens de produção &gt; Todas ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="7d94c-214">Go to Production control &gt; Production orders &gt; All production orders.</span></span></td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td><span data-ttu-id="7d94c-215">Clique em Nova ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="7d94c-215">Click New production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td><span data-ttu-id="7d94c-216">No campo Número do item, insira &#39;L0101&#39;.</span><span class="sxs-lookup"><span data-stu-id="7d94c-216">In the Item number field, enter &#39;L0101&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td><span data-ttu-id="7d94c-217">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="7d94c-217">Click Create.</span></span></td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td><span data-ttu-id="7d94c-218">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="7d94c-218">On the Action Pane, click Production order.</span></span></td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td><span data-ttu-id="7d94c-219">Clique em Estimar.</span><span class="sxs-lookup"><span data-stu-id="7d94c-219">Click Estimate.</span></span></td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td><span data-ttu-id="7d94c-220">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7d94c-220">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td><span data-ttu-id="7d94c-221">Clique em Iniciar.</span><span class="sxs-lookup"><span data-stu-id="7d94c-221">Click Start.</span></span></td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td><span data-ttu-id="7d94c-222">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="7d94c-222">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td><span data-ttu-id="7d94c-223">No campo Consumo automático de BOM, selecione &#39;Nunca&#39;.</span><span class="sxs-lookup"><span data-stu-id="7d94c-223">In the Automatic BOM consumption field, select &#39;Never&#39;.</span></span></td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td><span data-ttu-id="7d94c-224">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7d94c-224">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td><span data-ttu-id="7d94c-225">Clique em Relatar como concluído.</span><span class="sxs-lookup"><span data-stu-id="7d94c-225">Click Report as finished.</span></span></td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td><span data-ttu-id="7d94c-226">Clique na guia Geral.</span><span class="sxs-lookup"><span data-stu-id="7d94c-226">Click the General tab.</span></span></td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td><span data-ttu-id="7d94c-227">Selecione Sim no campo Aceitar erro.</span><span class="sxs-lookup"><span data-stu-id="7d94c-227">Select Yes in the Accept error field.</span></span></td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td><span data-ttu-id="7d94c-228">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7d94c-228">Click OK.</span></span></td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td><span data-ttu-id="7d94c-229">No Painel de Ação, clique em Depósito.</span><span class="sxs-lookup"><span data-stu-id="7d94c-229">On the Action Pane, click Warehouse.</span></span></td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td><span data-ttu-id="7d94c-230">Clique em Detalhes do trabalho.</span><span class="sxs-lookup"><span data-stu-id="7d94c-230">Click Work details.</span></span></td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td><span data-ttu-id="7d94c-231">Quando a ordem de produção foi informada como concluída, nenhum trabalho foi gerado para ser colocado de lado.</span><span class="sxs-lookup"><span data-stu-id="7d94c-231">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="7d94c-232">Isso ocorre porque uma diretiva de trabalho que é definida impede que o trabalho seja gerado quando o produto L0101 é relatado como concluídos no local 001.</span><span class="sxs-lookup"><span data-stu-id="7d94c-232">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span></td>
</tr>
</tbody>
</table>




