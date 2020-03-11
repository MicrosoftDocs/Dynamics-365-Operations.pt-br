---
title: Política de reserva de dimensão no nível de depósito flexível
description: Este tópico descreve a política de reserva de estoque que permite às empresas que vendem produtos rastreados por lote e executam suas logísticas como operações habilitadas para WMS reservem lotes específicos para ordens de venda do cliente, mesmo que a hierarquia de reservas associada aos produtos não permita a reserva de lotes específicos.
author: omulvad
manager: AnnBe
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: cd6ec1013de757214db99ada02170bb6e2af96c0
ms.sourcegitcommit: f52ddcad105aac4ad2caef709751ff80caf363c0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036920"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a><span data-ttu-id="4c3aa-103">Política de reserva de dimensão no nível de depósito flexível</span><span class="sxs-lookup"><span data-stu-id="4c3aa-103">Flexible warehouse-level dimension reservation policy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c3aa-104">Quando uma hierarquia de reservas de estoque do tipo "Abaixo do lote\[local\]" é associada a produtos, as empresas que vendem produtos rastreados por lote e executam suas logísticas como operações que são habilitadas para o Microsoft Dynamics 365 Warehouse Management System (WMS) não podem reservar lotes específicos desses produtos para ordens de venda do cliente.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-104">When an inventory reservation hierarchy of the "Batch-below\[location\]" type is associated with products, businesses that sell batch-tracked products and run their logistics as operations that are enabled for the Microsoft Dynamics 365 Warehouse Management System (WMS) can't reserve specific batches of those products for customer sales orders.</span></span> <span data-ttu-id="4c3aa-105">Este tópico descreve a política de reserva de estoque que permite a essas empresas reservar lotes específicos, mesmo quando os produtos são associados a uma hierarquia de reservas "Abaixo do lote\[local\].</span><span class="sxs-lookup"><span data-stu-id="4c3aa-105">This topic describes the inventory reservation policy that lets these businesses reserve specific batches, even when the products are associated with a "Batch-below\[location\]" reservation hierarchy.</span></span>

## <a name="inventory-reservation-hierarchy"></a><span data-ttu-id="4c3aa-106">Hierarquia de reservas de estoque</span><span class="sxs-lookup"><span data-stu-id="4c3aa-106">Inventory reservation hierarchy</span></span>

<span data-ttu-id="4c3aa-107">Esta seção resume a hierarquia de reservas de estoque existente.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-107">This section summarizes the existing inventory reservation hierarchy.</span></span> <span data-ttu-id="4c3aa-108">Ela se concentra em como os itens rastreados por lote e por série são manipulados.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-108">It focuses on the way that batch-tracked and serial-tracked items are handled.</span></span>

<span data-ttu-id="4c3aa-109">A hierarquia de reservas de estoque determina que, no que diz respeito às dimensões de armazenamento, a ordem de demanda comporta as dimensões obrigatórias de site, depósito e status do estoque, enquanto a lógica do depósito é responsável por atribuir um local às quantidades solicitadas e reservar o local.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-109">The inventory reservation hierarchy dictates that, as far as storage dimensions are concerned, the demand order carries the mandatory dimensions of site, warehouse, and inventory status, whereas the warehouse logic is responsible for assigning a location to the requested quantities and reserving the location.</span></span> <span data-ttu-id="4c3aa-110">Em outras palavras, nas interações entre a ordem de demanda e as operações de depósito, espera-se que a ordem de demanda indique de onde a ordem deve ser remetida (ou seja, de qual site e depósito).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-110">In other words, in the interactions between the demand order and the warehouse operations, the demand order is expected to indicate where the order must be shipped from (that is, what site and warehouse).</span></span> <span data-ttu-id="4c3aa-111">O depósito conta com sua lógica para encontrar a quantidade necessária no local do depósito.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-111">The warehouse then relies on its logic to find the required quantity in the warehouse premises.</span></span>

<span data-ttu-id="4c3aa-112">No entanto, para refletir o modelo operacional da empresa, as dimensões de rastreamento (números de série e de lote) estão sujeitas a mais flexibilidade.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-112">However, to reflect the operational model of the business, tracking dimensions (batch and serial numbers) are subject to more flexibility.</span></span> <span data-ttu-id="4c3aa-113">Uma hierarquia de reservas de estoque pode acomodar cenários nos quais se aplicam as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-113">An inventory reservation hierarchy can accommodate scenarios where the following conditions apply:</span></span>

- <span data-ttu-id="4c3aa-114">A empresa depende de suas operações de depósito para gerenciar a separação de quantidades que têm números de lote ou de série depois que elas tiverem sido encontradas no espaço de armazenamento do depósito.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-114">The business relies on its warehouse operations to manage picking of quantities that have batch or serial numbers after the quantities have been found in the warehousing storage space.</span></span> <span data-ttu-id="4c3aa-115">Esse modelo geralmente é conhecido como *Abaixo do lote\[local\]*.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-115">This model is often referred to as *Batch-below\[location\]*.</span></span> <span data-ttu-id="4c3aa-116">Normalmente, ele é usado quando a identificação de número de série ou lote de um produto não é importante para os clientes que fazem a demanda com a empresa vendedora.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-116">It's typically used when a product's batch or serial number identification isn't important to the customers who place the demand with the selling company.</span></span>
- <span data-ttu-id="4c3aa-117">Se os números de série ou lote fizerem parte da especificação da ordem de um cliente, e eles forem registrados na ordem de demanda, as operações de depósito que encontrarem as quantidades no depósito serão restringidas pelos números específicos solicitados e não podem alterá-los.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-117">If batch or serial numbers are part of a customer's order specification, and they are recorded on the demand order, the warehouse operations that find the quantities in the warehouse are constrained by the specific requested numbers and aren't allowed to change them.</span></span> <span data-ttu-id="4c3aa-118">Esse modelo geralmente é conhecido como *Acima do lote\[local\]*.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-118">This model is referred to as *Batch-above\[location\]*.</span></span>

<span data-ttu-id="4c3aa-119">Nesses cenários, o desafio é que apenas uma hierarquia de reservas de estoque pode ser atribuída a cada produto liberado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-119">In these scenarios, the challenge is that only one inventory reservation hierarchy can be assigned to each released product.</span></span> <span data-ttu-id="4c3aa-120">Portanto, para que o WMS manipule itens rastreados, depois que a atribuição de hierarquia determinar quando o número de série ou lote deve ser reservado (seja quando a ordem de demanda é retirada, seja durante o trabalho de separação do depósito), esse tempo não pode ser alterado de modo ad hoc.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-120">Therefore, for the WMS to handle tracked items, after the hierarchy assignment determines when the batch or serial number should be reserved (either when the demand order is taken or during the warehouse picking work), this timing can't be changed on an ad-hoc basis.</span></span>

## <a name="flexible-reservation-for-batch-tracked-items"></a><span data-ttu-id="4c3aa-121">Reserva flexível para itens rastreados por lote</span><span class="sxs-lookup"><span data-stu-id="4c3aa-121">Flexible reservation for batch-tracked items</span></span>

### <a name="business-scenario"></a><span data-ttu-id="4c3aa-122">Cenário de negócios</span><span class="sxs-lookup"><span data-stu-id="4c3aa-122">Business scenario</span></span>

<span data-ttu-id="4c3aa-123">Neste cenário, uma empresa usa uma estratégia de estoque em que mercadorias concluídas são rastreadas pelos números de lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-123">In this scenario, a company uses an inventory strategy where finished goods are tracked by batch numbers.</span></span> <span data-ttu-id="4c3aa-124">Essa empresa também usa a carga de trabalho do WMS.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-124">This company also uses the WMS workload.</span></span> <span data-ttu-id="4c3aa-125">Como essa carga de trabalho tem uma lógica bem montada para planejar e executar operações de separação e remessa de depósito dos itens habilitados para lote, a maioria dos itens concluídos é associada a uma hierarquia de reservas de estoque "Abaixo do lote\[local\]".</span><span class="sxs-lookup"><span data-stu-id="4c3aa-125">Because this workload has well-equipped logic for planning and running warehouse picking and shipping operations for batch-enabled items, most of the finished items are associated with a "Batch-below\[location\]" inventory reservation hierarchy.</span></span> <span data-ttu-id="4c3aa-126">A vantagem desse tipo de configuração operacional é que as decisões (que são efetivamente decisões de reserva) sobre quais lotes devem ser separados e onde colocá-los no depósito são adiadas até que as operações de separação de depósito comecem.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-126">The advantage of this type of operational setup is that decisions (which are effectively reservation decisions) about which batches to pick and where to put them in the warehouse are postponed until the warehouse picking operations start.</span></span> <span data-ttu-id="4c3aa-127">Elas não são tomadas quando a ordem do cliente é realizada.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-127">They aren't made when the customer's order is placed.</span></span>

<span data-ttu-id="4c3aa-128">Embora a hierarquia de reservas "Abaixo do lote\[local\]" também atenda às metas de negócios da empresa, muitos dos clientes estabelecidos da empresa exigem o mesmo lote que compraram anteriormente quando repetiram a ordem de produtos.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-128">Although the "Batch-below\[location\]" reservation hierarchy serves the company's business goals well, many of the company's established customers require the same batch that they previously purchased when they reorder products.</span></span> <span data-ttu-id="4c3aa-129">Portanto, a empresa está procurando flexibilidade no tratamento das regras de reserva de lotes para que, dependendo da demanda dos clientes pelo mesmo item, ocorram os seguintes comportamentos:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-129">Therefore, the company is looking for flexibility in the way that the batch reservation rules are handled, so that, depending on the customers' demand for the same item, the following behaviors occur:</span></span>

- <span data-ttu-id="4c3aa-130">Um número de lote pode ser registrado e reservado quando a ordem é realizada pelo processador de vendas e não pode ser alterado durante as operações de depósito e/ou retirado por outras demandas.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-130">A batch number can be recorded and reserved when the order is taken by the sales processor, and it can't be changed during warehouse operations and/or taken by other demands.</span></span> <span data-ttu-id="4c3aa-131">Esse comportamento ajuda a garantir que o número do lote que foi pedido seja enviado ao cliente.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-131">This behavior helps guarantee that the batch number that was ordered is shipped to the customer.</span></span>
- <span data-ttu-id="4c3aa-132">Se o número do lote não for importante para o cliente, as operações de depósito poderão determinar um número de lote durante o trabalho de separação, depois que o registro e a reserva da ordem de venda tiverem sido feitos.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-132">If the batch number isn't important to the customer, the warehouse operations can determine a batch number during picking work, after sales order registration and reservation have been done.</span></span>

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a><span data-ttu-id="4c3aa-133">Permitindo a reserva de um lote específico na ordem de venda</span><span class="sxs-lookup"><span data-stu-id="4c3aa-133">Allowing reservation of a specific batch on the sales order</span></span>

<span data-ttu-id="4c3aa-134">Para acomodar a flexibilidade desejada no comportamento de reserva de lotes para os itens associados a uma hierarquia de reservas de estoque "Abaixo do lote\[local\]", os gerentes de estoque devem marcar a caixa de seleção **Permitir reserva na ordem de demanda** para o nível **Número do lote** na página **Hierarquias de reservas de estoque**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-134">To accommodate the desired flexibility in the batch reservation behavior for items that are associated with a "Batch-below\[location\]" inventory reservation hierarchy, inventory managers must select the **Allow reservation on demand order** check box for the **Batch number** level on the **Inventory reservation hierarchies** page.</span></span>

![Tornando flexível a hierarquia de reservas de estoque](media/Flexible-inventory-reservation-hierarchy.png)

<span data-ttu-id="4c3aa-136">Quando o nível **Número do lote** na hierarquia é selecionado, todas as dimensões acima desse nível e até o nível **Local** são automaticamente selecionadas.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-136">When the **Batch number** level in the hierarchy is selected, all dimensions above that level and up through the **Location** level will be automatically selected.</span></span> <span data-ttu-id="4c3aa-137">(Por padrão, todas as dimensões acima do nível **Local** são pré-selecionadas.) Esse comportamento reflete a lógica em que todas as dimensões no intervalo entre o número do lote e o local também são reservadas automaticamente depois que você reserva um número de lote específico na linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-137">(By default, all dimensions above the **Location** level are preselected.) This behavior reflects the logic where all dimensions in the range between the batch number and location are also automatically reserved after you reserve a specific batch number on the order line.</span></span>

> [!NOTE]
> <span data-ttu-id="4c3aa-138">A caixa de seleção **Permitir reserva na ordem de demanda** se aplica somente aos níveis de hierarquia de reservas que estão abaixo da dimensão de local do depósito.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-138">The **Allow reservation on demand order** check box applies only to reservation hierarchy levels that are below the warehouse location dimension.</span></span>
>
> <span data-ttu-id="4c3aa-139">O **número do lote** é o único nível na hierarquia que está aberto para a política de reserva flexível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-139">**Batch number** is the only level in the hierarchy that is open for the flexible reservation policy.</span></span> <span data-ttu-id="4c3aa-140">Em outras palavras, você não pode marcar a caixa de seleção **Permitir reserva na ordem de demanda** para o nível **Local**, **Placa de licença** ou **Número de série**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-140">In other words, you can't select the **Allow reservation on demand order** check box for the **Location**, **License plate**, or **Serial number** level.</span></span>
>
> <span data-ttu-id="4c3aa-141">Se a hierarquia de reservas incluir a dimensão de número de série (que deve estar sempre abaixo do nível **Número do lote**) e se você tiver ativado a reserva específica do lote para o número do lote, o sistema continuará tratando a reserva de número de série e as operações de separação, com base nas regras que se aplicam à política de reserva "Abaixo da série\[local\].</span><span class="sxs-lookup"><span data-stu-id="4c3aa-141">If your reservation hierarchy includes the serial number dimension (which must always be below the **Batch number** level), and if you've turned on batch-specific reservation for the batch number, the system will continue to handle serial number reservation and picking operations, based on the rules that apply to the "Serial-below\[location\]" reservation policy.</span></span>

<span data-ttu-id="4c3aa-142">A qualquer momento, você pode permitir a reserva específica de lote para uma hierarquia de reservas "Abaixo do lote\[local\]" existente em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-142">At any point, you can allow batch-specific reservation for an existing "Batch-below\[location\]" reservation hierarchy in your deployment.</span></span> <span data-ttu-id="4c3aa-143">Essa alteração não afetará as reservas nem o trabalho de depósito aberto que foram criados antes da alteração.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-143">This change won't affect any reservations and open warehouse work that were created before the change occurred.</span></span> <span data-ttu-id="4c3aa-144">No entanto , a caixa de seleção **Permitir reserva na ordem de demanda** não poderá ser desmarcada se existirem transações de estoque do tipo de saída **Qtd. encomendada**, **Qtd. reservada** ou **Encomendado** para um ou mais itens que são associados a essa hierarquia de reservas.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-144">However, the **Allow reservation on demand order** check box can't be cleared if inventory transactions of the **Reserved ordered**, **Reserved physical**, or **Ordered** issue type exist for one or more items that are associated with that reservation hierarchy.</span></span>

> [!NOTE]
> <span data-ttu-id="4c3aa-145">Se a hierarquia de reservas existente de um item não permitir especificação de lote na ordem, você poderá reatribuí-la a uma hierarquia de reservas que permita a especificação de lote, desde que a estrutura do nível de hierarquia seja a mesma nas duas hierarquias.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-145">If an item's existing reservation hierarchy doesn't allow batch specification on the order, you can reassign it to a reservation hierarchy that does allow batch specification, provided that the hierarchy level structure is the same in both hierarchies.</span></span> <span data-ttu-id="4c3aa-146">Use a função **Alterar hierarquia de reservas de itens** para fazer a reatribuição.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-146">Use the **Change reservation hierarchy for items** function to do the reassignment.</span></span> <span data-ttu-id="4c3aa-147">Essa alteração pode ser relevante quando você deseja impedir a reserva flexível de lote para um subconjunto de itens rastreados por lote, mas permiti-la para o restante do portfólio de produtos.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-147">This change might be relevant when you want to prevent flexible batch reservation for a subset of batch-tracked items but allow it for the rest of the product portfolio.</span></span>

<span data-ttu-id="4c3aa-148">Independentemente de você ter marcado a caixa de seleção **Permitir reserva na ordem de demanda**, se não quiser reservar um número de lote específico para o item em uma linha da ordem, ainda será aplicada a lógica padrão de operações de depósito válida para uma hierarquia de reservas "Abaixo do lote\[local\].</span><span class="sxs-lookup"><span data-stu-id="4c3aa-148">Regardless of whether you've selected the **Allow reservation on demand order** check box, if you don't want to reserve a specific batch number for the item on an order line, default warehouse operations logic that is valid for a "Batch-below\[location\]" reservation hierarchy will still apply.</span></span>

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a><span data-ttu-id="4c3aa-149">Reservar um número de lote específico para uma ordem de cliente</span><span class="sxs-lookup"><span data-stu-id="4c3aa-149">Reserve a specific batch number for a customer order</span></span>

<span data-ttu-id="4c3aa-150">Depois que uma hierarquia de reservas de estoque "Abaixo do lote\[local\]" do item rastreado por lote é configurada para permitir a reserva de números de lote específicos nas ordens de venda, os processadores de ordem de venda podem tirar as ordens do cliente para o mesmo item das seguintes maneiras, dependendo da solicitação do cliente:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-150">After a batch-tracked item's "Batch-below\[location\]" inventory reservation hierarchy is set up to allow reservation of specific batch numbers on sales orders, sales order processors can take customer orders for the same item in one of the following ways, depending on the customer's request:</span></span>

- <span data-ttu-id="4c3aa-151">**Inserir detalhes da ordem sem especificar um número de lote** – essa abordagem deve ser usada quando a especificação de lote do produto não for importante para o cliente.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-151">**Enter order details without specifying a batch number** – This approach should be used when the product's batch specification isn't important to the customer.</span></span> <span data-ttu-id="4c3aa-152">Todos os processos existentes associados ao tratamento de uma ordem desse tipo no sistema permanecerão inalterados.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-152">All existing processes that are associated with handling an order of this type in the system remain unchanged.</span></span> <span data-ttu-id="4c3aa-153">Não são necessárias considerações adicionais sobre a parte dos usuários.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-153">No additional considerations are required on the part of users.</span></span>
- <span data-ttu-id="4c3aa-154">**Inserir detalhes da ordem e reservar um número de lote específico** – essa abordagem deve ser usada quando o cliente solicita um lote específico.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-154">**Enter order details and reserve a specific batch number** – This approach should be used when the customer requests a specific batch.</span></span> <span data-ttu-id="4c3aa-155">Normalmente, os clientes solicitam um lote específico quando estão repetindo a ordem de um produto que compraram anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-155">Typically, customers will request a specific batch when they are reordering a product that they previously purchased.</span></span> <span data-ttu-id="4c3aa-156">Esse tipo de reserva específica do lote é conhecido como *reserva confirmada na ordem*.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-156">This type of batch-specific reservation is referred to as *order-committed reservation*.</span></span>

<span data-ttu-id="4c3aa-157">O conjunto de regras seguinte é válido quando as quantidades são processadas, e um número de lote é confirmado para uma ordem específica:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-157">The following set of rules is valid when quantities are processed, and a batch number is committed to a specific order:</span></span>

- <span data-ttu-id="4c3aa-158">Para permitir a reserva de um número de lote específico para um item na política de reserva "Abaixo do lote\[local\]", o sistema deve reservar todas as dimensões até local.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-158">To allow reservation of a specific batch number for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="4c3aa-159">Esse intervalo normalmente inclui a dimensão da placa de licença.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-159">This range typically includes the license plate dimension.</span></span>
- <span data-ttu-id="4c3aa-160">As diretivas de local não são usadas quando o trabalho de separação é criado para uma linha de venda que usa a reserva de lotes confirmada na ordem.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-160">Location directives aren't used when picking work is created for a sales line that uses order-committed batch reservation.</span></span>
- <span data-ttu-id="4c3aa-161">Durante o processamento de trabalho do depósito para lotes confirmados na ordem, nem o usuário, nem o sistema têm permissão para alterar o número do lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-161">During warehouse processing of work for order-committed batches, neither the user nor the system is allowed to change the batch number.</span></span> <span data-ttu-id="4c3aa-162">(Esse processamento inclui tratamento de exceção.)</span><span class="sxs-lookup"><span data-stu-id="4c3aa-162">(This processing includes exception handling.)</span></span>

<span data-ttu-id="4c3aa-163">O exemplo a seguir mostra o fluxo de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-163">The following example shows the end-to-end flow.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="4c3aa-164">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="4c3aa-164">Example scenario</span></span>

<span data-ttu-id="4c3aa-165">Para este exemplo, os dados de demonstração devem ser instalados, e você deve usar a empresa de dados de demonstração **USMF**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-165">For this example, demo data must be installed, and you must use the **USMF** demo data company.</span></span>

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><span data-ttu-id="4c3aa-166">Configurar uma hierarquia de reservas de estoque para permitir reserva específica de lote</span><span class="sxs-lookup"><span data-stu-id="4c3aa-166">Set up an inventory reservation hierarchy to allow batch-specific reservation</span></span>

1. <span data-ttu-id="4c3aa-167">Vá para **Gerenciamento de depósito** \> **Configuração** \> **Estoque \> Hierarquia de reservas**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-167">Go to **Warehouse management** \> **Setup** \> **Inventory \> Reservation hierarchy**.</span></span>
2. <span data-ttu-id="4c3aa-168">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-168">Select **New**.</span></span>
3. <span data-ttu-id="4c3aa-169">No campo **Nome**, insira um nome (por exemplo, **BatchFlex**).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-169">In the **Name** field, enter a name (for example, **BatchFlex**).</span></span>
4. <span data-ttu-id="4c3aa-170">No campo **Descrição**, insira uma descrição (por exemplo, **Abaixo do lote flexível**).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-170">In the **Description** field, enter a description (for example, **Batch below flexible**).</span></span>
5. <span data-ttu-id="4c3aa-171">No campo **Selecionado**, selecione **Número de série** e **Proprietário**; em seguida, selecione o botão de seta para a esquerda a fim de movê-los para o campo **Disponível**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-171">In the **Selected** field, select **Serial number** and **Owner**, and then select the left arrow button to move them to the **Available** field.</span></span>
6. <span data-ttu-id="4c3aa-172">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-172">Select **OK**.</span></span>
7. <span data-ttu-id="4c3aa-173">Na linha do nível de dimensão **Número do lote**, marque a caixa de seleção **Permitir reserva na ordem de demanda**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-173">In the row for the **Batch number** dimension level, select the **Allow reservation on demand order** check box.</span></span> <span data-ttu-id="4c3aa-174">Os níveis **Placa de licença** e **Local** são selecionados automaticamente, e não é possível desmarcar suas caixas de seleção.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-174">The **License plate** and **Location** levels are automatically selected, and you can't clear the check boxes for them.</span></span>
8. <span data-ttu-id="4c3aa-175">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-175">Select **Save**.</span></span>

### <a name="create-a-new-released-product"></a><span data-ttu-id="4c3aa-176">Crie um novo produto liberado</span><span class="sxs-lookup"><span data-stu-id="4c3aa-176">Create a new released product</span></span>

1. <span data-ttu-id="4c3aa-177">Defina os três parâmetros de dados mestres do produto usando estes valores:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-177">Set the product's three master data parameters by using these values:</span></span>

    - <span data-ttu-id="4c3aa-178">No campo **Grupo de dimensões de armazenamento**, selecione **Ware**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-178">In the **Storage dimension group** field, select **Ware**.</span></span>
    - <span data-ttu-id="4c3aa-179">No campo **Grupo de dimensões de rastreamento**, selecione **Batch-Phy**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-179">In the **Tracking dimension group** field, select **Batch-Phy**.</span></span>
    - <span data-ttu-id="4c3aa-180">No campo **Hierarquia de reservas**, selecione **BatchFlex**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-180">In the **Reservation hierarchy** field, select **BatchFlex**.</span></span>

2. <span data-ttu-id="4c3aa-181">Crie dois números de lote, como **B11** e **B22**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-181">Create two batch numbers, such as **B11** and **B22**.</span></span>
3. <span data-ttu-id="4c3aa-182">Adicione as quantidades de item ao estoque disponível usando os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-182">Add item quantities to on-hand stock by using the following values.</span></span>

    | <span data-ttu-id="4c3aa-183">Depósito</span><span class="sxs-lookup"><span data-stu-id="4c3aa-183">Warehouse</span></span> | <span data-ttu-id="4c3aa-184">Nº do lote</span><span class="sxs-lookup"><span data-stu-id="4c3aa-184">Batch number</span></span> | <span data-ttu-id="4c3aa-185">Local</span><span class="sxs-lookup"><span data-stu-id="4c3aa-185">Location</span></span> | <span data-ttu-id="4c3aa-186">Placa de licença</span><span class="sxs-lookup"><span data-stu-id="4c3aa-186">License plate</span></span> | <span data-ttu-id="4c3aa-187">Quantidade</span><span class="sxs-lookup"><span data-stu-id="4c3aa-187">Quantity</span></span> |
    |-----------|--------------|----------|---------------|----------|
    | <span data-ttu-id="4c3aa-188">24</span><span class="sxs-lookup"><span data-stu-id="4c3aa-188">24</span></span>        | <span data-ttu-id="4c3aa-189">B11</span><span class="sxs-lookup"><span data-stu-id="4c3aa-189">B11</span></span>          | <span data-ttu-id="4c3aa-190">BULK-001</span><span class="sxs-lookup"><span data-stu-id="4c3aa-190">BULK-001</span></span> | <span data-ttu-id="4c3aa-191">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="4c3aa-191">None</span></span>          | <span data-ttu-id="4c3aa-192">10</span><span class="sxs-lookup"><span data-stu-id="4c3aa-192">10</span></span>       |
    | <span data-ttu-id="4c3aa-193">24</span><span class="sxs-lookup"><span data-stu-id="4c3aa-193">24</span></span>        | <span data-ttu-id="4c3aa-194">B11</span><span class="sxs-lookup"><span data-stu-id="4c3aa-194">B11</span></span>          | <span data-ttu-id="4c3aa-195">FL-001</span><span class="sxs-lookup"><span data-stu-id="4c3aa-195">FL-001</span></span>   | <span data-ttu-id="4c3aa-196">LP11</span><span class="sxs-lookup"><span data-stu-id="4c3aa-196">LP11</span></span>          | <span data-ttu-id="4c3aa-197">10</span><span class="sxs-lookup"><span data-stu-id="4c3aa-197">10</span></span>       |
    | <span data-ttu-id="4c3aa-198">24</span><span class="sxs-lookup"><span data-stu-id="4c3aa-198">24</span></span>        | <span data-ttu-id="4c3aa-199">B22</span><span class="sxs-lookup"><span data-stu-id="4c3aa-199">B22</span></span>          | <span data-ttu-id="4c3aa-200">FL-002</span><span class="sxs-lookup"><span data-stu-id="4c3aa-200">FL-002</span></span>   | <span data-ttu-id="4c3aa-201">LP22</span><span class="sxs-lookup"><span data-stu-id="4c3aa-201">LP22</span></span>          | <span data-ttu-id="4c3aa-202">10</span><span class="sxs-lookup"><span data-stu-id="4c3aa-202">10</span></span>       |

### <a name="enter-sales-order-details"></a><span data-ttu-id="4c3aa-203">Inserir detalhes da ordem de venda</span><span class="sxs-lookup"><span data-stu-id="4c3aa-203">Enter sales order details</span></span>

1. <span data-ttu-id="4c3aa-204">Vá para **Vendas e marketing** \> **Ordens de venda** \> **Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-204">Go to **Sales and marketing** \> **Sales orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="4c3aa-205">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-205">Select **New**.</span></span>
3. <span data-ttu-id="4c3aa-206">No cabeçalho da ordem de venda, no campo **Conta de cliente**, digite **US-003**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-206">On the sales order header, in the **Customer account** field, enter **US-003**.</span></span>
4. <span data-ttu-id="4c3aa-207">Adicione uma linha para o novo item e insira **10** como a quantidade.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-207">Add a line for the new item, and enter **10** as the quantity.</span></span> <span data-ttu-id="4c3aa-208">Verifique se o campo **Depósito** está definido como **24**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-208">Make sure that the **Warehouse** field is set to **24**.</span></span>
5. <span data-ttu-id="4c3aa-209">Na FastTab **Linhas da ordem de venda**, selecione **Estoque** e, no grupo **Manter**, selecione **Reserva de lotes**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-209">On the **Sales order lines** FastTab, select **Inventory**, and then, in the **Maintain** group, select **Batch reservation**.</span></span> <span data-ttu-id="4c3aa-210">A página **Reserva de lotes** mostra uma lista de lotes que estão disponíveis para reserva para a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-210">The **Batch reservation** page shows a list of batches that are available for reservation for the order line.</span></span> <span data-ttu-id="4c3aa-211">Neste exemplo, ela mostra uma quantidade de **20** para o número do lote **B11** e uma quantidade de **10** para o número do lote **B22**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-211">For this example, it shows a quantity of **20** for batch number **B11** and a quantity of **10** for batch number **B22**.</span></span> <span data-ttu-id="4c3aa-212">Observe que a página **Reserva de lotes** não poderá ser acessada de uma linha se o item nessa linha estiver associado à hierarquia de reservas "Abaixo do lote\[local\]", a menos que esteja configurada para permitir reserva específica de lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-212">Note that the **Batch reservation** page cannot be accessed from a line if the item on that line is associated with "Batch-below\[location\]" reservation hierarchy unless it is set up to allow batch-specific reservation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c3aa-213">Para reservar um lote específico para uma ordem de venda, você deve usar a página **Reserva de lotes**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-213">To reserve a specific batch for a sales order, you must use the **Batch reservation** page.</span></span>
    >
    > <span data-ttu-id="4c3aa-214">Se você inserir o número do lote diretamente na linha da ordem de venda, o sistema se comportará como se você tivesse inserido um valor de lote específico para um item que está sujeito à política de reserva "Abaixo do lote\[local\]".</span><span class="sxs-lookup"><span data-stu-id="4c3aa-214">If you enter the batch number directly on the sales order line, the system will behave as though you entered a specific batch value for an item that is subject to the "Batch-below\[location\]" reservation policy.</span></span> <span data-ttu-id="4c3aa-215">Ao salvar a linha, você receberá uma mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-215">When you save the line, you will receive a warning message.</span></span> <span data-ttu-id="4c3aa-216">Se você confirmar que o número do lote deve ser especificado diretamente na linha da ordem, a linha não será manipulada pela lógica de gerenciamento de depósito normal.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-216">If you confirm that the batch number should be specified directly on the order line, the line won't be handled by the regular warehouse management logic.</span></span>
    >
    > <span data-ttu-id="4c3aa-217">Se você reservar a quantidade na página **Reserva**, nenhum lote específico será reservado e a execução das operações de depósito para a linha seguirá as regras aplicáveis sob a política de reserva "Abaixo do lote\[local\].</span><span class="sxs-lookup"><span data-stu-id="4c3aa-217">If you reserve the quantity from the **Reservation** page, no specific batch will be reserved, and the execution of warehouse operations for the line will follow the rules that are applicable under the "Batch-below\[location\]" reservation policy.</span></span>

    <span data-ttu-id="4c3aa-218">Em geral, essa página funciona e interage da mesma maneira que funciona e interage para itens que têm uma hierarquia de reservas associada do tipo "Acima do lote\[local\]".</span><span class="sxs-lookup"><span data-stu-id="4c3aa-218">In general, this page works and is interacted with in the same way that it works and is interacted with for items that have an associated reservation hierarchy of the "Batch-above\[location\]" type.</span></span> <span data-ttu-id="4c3aa-219">No entanto, as seguintes exceções se aplicam:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-219">However, the following exceptions apply:</span></span>

    - <span data-ttu-id="4c3aa-220">A FastTab **Números de lote confirmados para linha de origem** mostra os números de lote que são reservados para a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-220">The **Batch numbers committed to source line** FastTab shows the batch numbers that are reserved for the order line.</span></span> <span data-ttu-id="4c3aa-221">Os valores de lote na grade serão mostrados durante todo o ciclo de atendimento da linha da ordem, incluindo as fases de processamento do depósito.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-221">The batch values in the grid will be shown throughout the fulfilment cycle of the order line, including the warehouse processing stages.</span></span> <span data-ttu-id="4c3aa-222">Em contrapartida, na FastTab **Visão Geral**, a reserva regular da linha da ordem (isto é, a reserva que é feita para as dimensões acima do nível **Local**) é mostrada na grade até o ponto em que o trabalho de depósito é criado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-222">By contrast, on the **Overview** FastTab, regular order line reservation (that is, reservation that is done for the dimensions above the **Location** level) is shown in the grid up to the point when warehouse work is created.</span></span> <span data-ttu-id="4c3aa-223">A entidade de trabalho assume a reserva de linha, e a reserva de linha não aparece mais na página.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-223">The work entity then takes over the line reservation, and the line reservation no longer appears on the page.</span></span> <span data-ttu-id="4c3aa-224">A FastTab **Números de lote confirmados para linha de origem** ajuda a garantir que o processador de ordem de venda possa ver os números de lotes que foram confirmados na ordem do cliente em qualquer ponto do seu ciclo de vida, até o faturamento.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-224">The **Batch numbers committed to source line** FastTab helps guarantee that the sales order processor can view the batch numbers that were committed to the customer's order at any point during its lifecycle, up through invoicing.</span></span>
    - <span data-ttu-id="4c3aa-225">Além de reservar um lote específico, um usuário pode selecionar manualmente o local específico e a placa de licença do lote em vez de permitir que o sistema os selecione automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-225">In addition to reserving a specific batch, a user can manually select the batch's specific location and license plate instead of letting the system automatically select them.</span></span> <span data-ttu-id="4c3aa-226">Esse recurso está relacionado ao design do mecanismo de reserva de lotes confirmados na ordem.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-226">This capability is related to the design of the order-committed batch reservation mechanism.</span></span> <span data-ttu-id="4c3aa-227">Como foi mencionado anteriormente, quando um número de lote é reservado para um item de acordo com a política de reserva "Abaixo do lote\[local\]", o sistema deve reservar todas as dimensões até local.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-227">As was mentioned earlier, when a batch number is reserved for an item under the "Batch-below\[location\]" reservation policy, the system must reserve all dimensions up through location.</span></span> <span data-ttu-id="4c3aa-228">Portanto, o trabalho de depósito carregará as mesmas dimensões de armazenamento que foram reservadas pelos usuários que trabalharam com as ordens, e isso nem sempre representará o posicionamento de armazenamento do item que é conveniente, ou mesmo possível, para as operações de separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-228">Therefore, warehouse work will carry the same storage dimensions that were reserved by the users who worked with the orders, and it might not always represent the item storage placement that is convenient, or even possible, for picking operations.</span></span> <span data-ttu-id="4c3aa-229">Se os processadores de ordem estiverem cientes das restrições do depósito, talvez eles queiram selecionar manualmente os locais específicos e as placas de licença quando reservarem um lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-229">If order processors are aware of the warehouse constraints, they might want to manually select the specific locations and license plates when they reserve a batch.</span></span> <span data-ttu-id="4c3aa-230">Nesse caso, o usuário deve usar a funcionalidade **Exibir dimensões** no cabeçalho da página, bem como deve adicionar o local e a placa de licença na grade, na FastTab **Visão Geral**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-230">In this case, the user must use the **Display dimensions** functionality on the page header, and must add the location and license plate in the grid on the **Overview** FastTab.</span></span>

6. <span data-ttu-id="4c3aa-231">Na página **Reserva de lotes**, selecione a linha para o lote **B11** e, em seguida, selecione **Reservar linha**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-231">On the **Batch reservation** page, select the line for batch **B11**, and then select **Reserve line**.</span></span> <span data-ttu-id="4c3aa-232">Não há lógica designada para atribuir locais e placas de licença durante a reserva automática.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-232">There is no designated logic for assigning locations and license plates during automatic reservation.</span></span> <span data-ttu-id="4c3aa-233">Você pode inserir manualmente a quantidade no campo **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-233">You can manually enter the quantity in the **Reservation** field.</span></span> <span data-ttu-id="4c3aa-234">Observe que, na FastTab **Números de lote confirmados para linha de origem**, o lote **B11** é mostrado como **Confirmado**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-234">Notice that, on the **Batch numbers committed to source line** FastTab, batch **B11** is shown as **Committed**.</span></span>

    ![Confirmando um número de lote específico para uma linha da ordem de venda na página Reserva de lotes](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > <span data-ttu-id="4c3aa-236">A reserva da quantidade em uma linha da ordem de venda pode ser realizada em vários lotes.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-236">Reservation of the quantity on a sales order line can be done across multiple batches.</span></span> <span data-ttu-id="4c3aa-237">Da mesma forma, é possível fazer reservas do mesmo lote em vários locais e placas de licença (se as placas de licença estiverem habilitadas para os locais).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-237">Likewise, reservation of the same batch can be done against multiple locations and license plates (if license plates are enabled for the locations).</span></span>
    >
    > <span data-ttu-id="4c3aa-238">A reserva de um lote específico para a quantidade em uma linha da ordem de venda também pode ser parcial.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-238">Reservation of a specific batch for the quantity on a sales order line can also be partial.</span></span> <span data-ttu-id="4c3aa-239">Por exemplo, a quantidade total de 100 unidades pode ser reservada para que um lote específico seja confirmado em 20 unidades, enquanto 80 unidades são reservadas nos níveis de site e depósito para qualquer lote disponível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-239">For example, the total quantity of 100 units can be reserved so that a specific batch is committed to 20 units, whereas 80 units are reserved at the site and warehouse levels for any available batch.</span></span> <span data-ttu-id="4c3aa-240">Nesse caso, o WMS manipulará as operações de separação usando duas linhas de trabalho separadas.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-240">In this case, the WMS will handle picking operations by using two separate work lines.</span></span>

7. <span data-ttu-id="4c3aa-241">Vá para **Gerenciamento de informações do produto** \> **Produtos** \> **Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-241">Go to **Product information management** \> **Products** \> **Released products**.</span></span> <span data-ttu-id="4c3aa-242">Selecione seu item e, em seguida , selecione **Gerenciar estoque** \> **Exibir** \> **Transações**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-242">Select your item, and then select **Manage inventory** \> **View** \> **Transactions**.</span></span>

    ![Reserva confirmada na ordem como um tipo de transação de estoque](media/Inventory-transactions-for-order-committed-reservation.png)

8. <span data-ttu-id="4c3aa-244">Revise as transações de estoque do item relacionadas à reserva da linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-244">Review the item's inventory transactions that are related to the sales order line reservation.</span></span>

    - <span data-ttu-id="4c3aa-245">Uma transação em que o campo **Referência** é definido como **Ordem de venda** e o campo **Saída** é definido como **Qtd. reservada** representa a reserva da linha da ordem para as dimensões de estoque acima do nível **Local**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-245">A transaction where the **Reference** field is set to **Sales order** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the inventory dimensions above the **Location** level.</span></span> <span data-ttu-id="4c3aa-246">De acordo com a hierarquia de reservas de estoque do item, essas dimensões são site, depósito e status do estoque.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-246">According to the item's inventory reservation hierarchy, those dimensions are site, warehouse, and inventory status.</span></span>
    - <span data-ttu-id="4c3aa-247">Uma transação em que o campo **Referência** é definido como **Reserva confirmada na ordem** e o campo **Saída** é definido como **Qtd. reservada** representa a reserva da linha da ordem para o lote específico e todas as dimensões de estoque acima dele.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-247">A transaction where the **Reference** field is set to **Order-committed reservation** and the **Issue** field is set to **Reserved physical** represents the order line reservation for the specific batch and all inventory dimensions above it.</span></span> <span data-ttu-id="4c3aa-248">De acordo com a hierarquia de reservas de estoque do item, essas dimensões são número do lote e local.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-248">According to the item's inventory reservation hierarchy, those dimensions are batch number and location.</span></span> <span data-ttu-id="4c3aa-249">Neste exemplo, o local é **Bulk-001**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-249">In this example, the location is **Bulk-001**.</span></span>

9. <span data-ttu-id="4c3aa-250">No cabeçalho da ordem de venda, selecione **Depósito** \> **Ações** \> **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-250">On the sales order header, select **Warehouse** \> **Actions** \> **Release to warehouse**.</span></span> <span data-ttu-id="4c3aa-251">A linha da ordem agora é ondulada, e são criados uma carga e um trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-251">The order line is now waved, and a load and work are created.</span></span>

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a><span data-ttu-id="4c3aa-252">Revisar e processar trabalho de depósito que tenha números de lote confirmados na ordem</span><span class="sxs-lookup"><span data-stu-id="4c3aa-252">Review and process warehouse work that has order-committed batch numbers</span></span>

1. <span data-ttu-id="4c3aa-253">Na FastTab **Linhas de ordem de venda**, selecione **Depósito** \> **Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-253">On the **Sales order lines** FastTab, select **Warehouse** \> **Work details**.</span></span>

    <span data-ttu-id="4c3aa-254">O trabalho que manipula a operação de separação para quantidades de lote que são confirmadas na linha da ordem de venda tem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-254">The work that handles the picking operation for batch quantities that are committed to the sales order line has the following characteristics:</span></span>

    - <span data-ttu-id="4c3aa-255">Para criar o trabalho, o sistema usa modelos de trabalho, mas não diretivas de local.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-255">To create work, the system uses work templates but not location directives.</span></span> <span data-ttu-id="4c3aa-256">Todas as configurações padrão definidas para modelos de trabalho, como um número máximo de linhas de separação ou uma unidade de medida específica, serão aplicadas para determinar quando um novo trabalho deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-256">All the standard settings that are defined for work templates, such as a maximum number of pick lines or a specific unit of measure, will be applied to determine when new work should be created.</span></span> <span data-ttu-id="4c3aa-257">No entanto, as regras associadas a diretivas de local para identificar locais de separação não são consideradas, pois a reserva confirmada da ordem já especifica todas as dimensões de estoque.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-257">However, the rules that are associated with location directives for identifying pick locations aren't considered, because the order-committed reservation already specifies all the inventory dimensions.</span></span> <span data-ttu-id="4c3aa-258">Essas dimensões de estoque incluem as dimensões no nível de armazenamento do depósito.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-258">Those inventory dimensions include the dimensions at the warehouse storage level.</span></span> <span data-ttu-id="4c3aa-259">Portanto, o trabalho herda essas dimensões sem ter que consultar diretivas de local.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-259">Therefore, the work inherits those dimensions without having to consult location directives.</span></span>
    - <span data-ttu-id="4c3aa-260">O número do lote não é mostrado na linha de separação (como é o caso da linha de trabalho que é criada para um item que tem uma hierarquia de reservas "Acima do lote\[local\]" associada.) Em vez disso, o número do lote "de" e todas as outras dimensões de armazenamento são mostrados na transação de estoque de trabalho da linha de trabalho referenciada a partir das transações de estoque associadas.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-260">The batch number isn't shown on the pick line (as is the case for the work line that is created for an item that has an associated "Batch-above\[location\]" reservation hierarchy.) Instead, the "from" batch number and all other storage dimensions are shown on the work line's work inventory transaction that is referenced from the associated inventory transactions.</span></span>

        ![Transação de estoque de depósito para trabalho que se origina da reserva confirmada na ordem](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - <span data-ttu-id="4c3aa-262">Depois que o trabalho é criado, a transação de estoque do item na qual o campo **Referência** está definido como **Reserva confirmada na ordem** é removida.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-262">After work is created, the item's inventory transaction where the **Reference** field is set to **Order-committed reservation** is removed.</span></span> <span data-ttu-id="4c3aa-263">A transação de estoque na qual o campo **Referência** está definido como **Trabalho** agora contém a reserva física em todas as dimensões de estoque da quantidade.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-263">The inventory transaction where the **Reference** field is set to **Work** now holds the physical reservation on all the quantity's inventory dimensions.</span></span>

        <span data-ttu-id="4c3aa-264">As operações de depósito podem continuar para manipular a execução do trabalho da maneira usual.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-264">Warehouse operations can proceed to handle execution of the work in the usual manner.</span></span> <span data-ttu-id="4c3aa-265">No entanto, as instruções no dispositivo móvel orientarão o trabalhador a separar um número de lote específico.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-265">However, the instructions on the mobile device will instruct the worker to pick a specific batch number.</span></span> <span data-ttu-id="4c3aa-266">Em ambientes de depósito em que os locais são controlados pela placa de licença, depois que um trabalhador chega a um local que armazena o mesmo lote em várias placas de licença, ele pode fazer a separação em qualquer placa de licença que ainda não esteja reservada (por exemplo, por outra reserva confirmada na ordem ou trabalho que se origina de uma reserva desse tipo).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-266">In warehouse environments where locations are license plate–controlled, after a worker reaches a location that stores the same batch on multiple license plates, he or she can pick from any license plate that isn't already reserved (for example, by another order-committed reservation or work that originates from a reservation of that type.)</span></span>

        <span data-ttu-id="4c3aa-267">Se for impraticável fazer a separação no local que é especificado na linha de trabalho, os operadores de depósito poderão usar uma das seguintes ações para redirecionar a separação do lote específico de um local mais conveniente:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-267">If it turns out to be impractical to pick from the location that is specified on the work line, the warehouse operators can use one of the following actions to redirect picking of the specific batch from a more convenient location:</span></span>

        - <span data-ttu-id="4c3aa-268">A ação padrão **Substituir local** em um dispositivo móvel (desde que a configuração **Permitir substituição de local de separação** do trabalhador do depósito esteja ativada)</span><span class="sxs-lookup"><span data-stu-id="4c3aa-268">The standard **Override location** action on a mobile device (provided that the warehouse worker's **Allow pick location override** setting is enabled)</span></span>
        - <span data-ttu-id="4c3aa-269">A ação **Alterar local** na página **Detalhes da lista de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-269">The **Change location** action on the **Work list details** page.</span></span> 

2. <span data-ttu-id="4c3aa-270">No dispositivo móvel, termine a separação e a colocação do trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-270">On the mobile device, finish picking and putting the work.</span></span>

    <span data-ttu-id="4c3aa-271">A quantidade de **10** para o número de lote **B11** agora está separada para a linha da ordem de venda e foi posicionada no local **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-271">The quantity of **10** for batch number **B11** is now picked for the sales order line and put in the **Baydoor** location.</span></span> <span data-ttu-id="4c3aa-272">Neste ponto, ele está pronto para ser carregado no caminhão e enviado para o endereço do cliente.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-272">At this point, it's ready to be loaded onto the truck and dispatched to the customer's address.</span></span>

## <a name="exception-handling-of-warehouse-work-thas-has-order-committed-batch-numbers"></a><span data-ttu-id="4c3aa-273">Tratamento de exceção do trabalho de depósito que tem números de lote confirmados na ordem</span><span class="sxs-lookup"><span data-stu-id="4c3aa-273">Exception handling of warehouse work thas has order-committed batch numbers</span></span>

<span data-ttu-id="4c3aa-274">O trabalho de depósito para separação de números de lote confirmados na ordem está sujeito ao mesmo tratamento de exceção de depósito e às mesmas ações que o trabalho regular.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-274">Warehouse work for picking order-committed batch numbers is subject to the same standard warehouse exception handling and actions as regular work.</span></span> <span data-ttu-id="4c3aa-275">De modo geral, o trabalho em aberto ou linha do trabalho pode ser cancelado, pode ser interrompido porque o local de um usuário está cheio, a quantidade separada é insuficiente e pode ser atualizado devido a uma movimentação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-275">In general, the open work or work line can be canceled, it can be interrupted because a user location is full, it can be short-picked, and it can be updated because of a movement.</span></span> <span data-ttu-id="4c3aa-276">Da mesma forma, a quantidade separada de trabalho que já foi concluída pode ser reduzida, ou o trabalho pode ser revertido.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-276">Likewise, the picked quantity of work that has already been completed can be reduced, or the work can be reversed.</span></span>

<span data-ttu-id="4c3aa-277">A importante regra a seguir é aplicada a todas as ações de tratamento de exceção: o número do lote que foi reservado para o cliente nunca pode ser substituído por outro número de lote, mas suas dimensões de armazenamento (local e placa de licença) podem ser alteradas por uma atualização manual feita pelo usuário ou uma atualização automática feita pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-277">The following key rule is applied to all these exception handling actions: the batch number that was reserved for the customer can never be replaced with a different batch number, but its storage dimensions (location and license plate) can be changed through either a manual update by the user or an automatic update by the system.</span></span> <span data-ttu-id="4c3aa-278">A atualização automática se baseia na mesma atribuição aleatória de dimensões de armazenamento que é aplicada quando um lote específico foi reservado automaticamente, mas nenhuma dimensão de armazenamento foi especificada.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-278">The automatic update is based on the same random assignment of storage dimensions that applied when a specific batch was automatically reserved but no storage dimensions were specified.</span></span>

### <a name="example-scenario"></a><span data-ttu-id="4c3aa-279">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="4c3aa-279">Example scenario</span></span>

<span data-ttu-id="4c3aa-280">Um exemplo desse cenário é uma situação em que o trabalho concluído anteriormente está sendo retirado usando a função **Reduzir quantidade separada**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-280">An example of this scenario is a situation where previously completed work is being unpicked by using the **Reduce picked quantity** function.</span></span> <span data-ttu-id="4c3aa-281">Este exemplo continua o exemplo anterior neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-281">This example continues the previous example in this topic.</span></span>

1. <span data-ttu-id="4c3aa-282">Vá para **Gerenciamento de depósito** \> **Cargas** \> **Cargas ativas**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-282">Go to **Warehouse management** \> **Loads** \> **Active loads**.</span></span>
2. <span data-ttu-id="4c3aa-283">Selecione a carga que foi criada em relação à remessa da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-283">Select the load that was created in connection with the shipment of your sales order.</span></span>
3. <span data-ttu-id="4c3aa-284">Na FastTab **Linhas de ordem da carga**, selecione **Reduzir quantidade separada**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-284">From the **Load order lines** FastTab, select **Reduce picked quantity**.</span></span>
4. <span data-ttu-id="4c3aa-285">Na página **Reduzir quantidade separada**, no campo **Mover para local**, selecione **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-285">On the **Reduce picked quantity** page, in the **Move to location** field, select **FL-001**.</span></span>
5. <span data-ttu-id="4c3aa-286">No campo **Mover para placa de licença**, selecione **LP33**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-286">In the **Move to license plate** field, select **LP33**.</span></span>
6. <span data-ttu-id="4c3aa-287">No campo **Quantidade de estoque para desfazer separação** da grade, digite **10**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-287">In the grid, in the **Inventory quantity to unpick** field, enter **10**.</span></span>
7. <span data-ttu-id="4c3aa-288">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-288">Select **OK**.</span></span>

<span data-ttu-id="4c3aa-289">Veja a seguir os resultados da ação de desfazer a separação:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-289">Here are the results of the unpicking action:</span></span>

- <span data-ttu-id="4c3aa-290">O status do trabalho anteriormente fechado é definido como **Cancelado**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-290">The status of the previously closed work is set to **Canceled**.</span></span>
- <span data-ttu-id="4c3aa-291">O novo trabalho do tipo **Movimento do estoque** é criado para a quantidade não separada de **10** para o número de lote **B11**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-291">New work of the **Inventory movement** type is created for the unpicked quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="4c3aa-292">Esse trabalho representa o movimento do local **Baydoor** para a placa de licença **LP33** no local **FL-001**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-292">This work represents the movement from the **Baydoor** location to license plate **LP33** in location **FL-001**.</span></span> <span data-ttu-id="4c3aa-293">O status é definido como **Fechado**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-293">The status is set to **Closed**.</span></span>
- <span data-ttu-id="4c3aa-294">O sistema reserva novamente o número do lote que foi originalmente pedido e atribui as IDs de local e placa de licença.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-294">The system re-reserves the batch number that was originally ordered, and assigns the location and license plate IDs.</span></span> <span data-ttu-id="4c3aa-295">(Esse processo equivale a executar a função **Reservar linha** para a linha de ordem de um determinado número de lote.)</span><span class="sxs-lookup"><span data-stu-id="4c3aa-295">(This process is equivalent to running the **Reserve line** function for the order line for a given batch number).</span></span> <span data-ttu-id="4c3aa-296">Consequentemente, o lote **B11** é mostrado como confirmado na FastTab **Números de lote confirmados para linha de origem** da página **Reserva de lote**, e o campo **Reserva** contém uma quantidade de **10** para o número de lote **B11**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-296">As a result, batch **B11** is shown as committed on the **Batch numbers committed to source line** FastTab of the **Batch reservation** page, and the **Reservation** field contains a quantity of **10** for batch number **B11**.</span></span> <span data-ttu-id="4c3aa-297">Além disso, o campo **Local** é definido como **FL-001** e o campo **Placa de licença** é definido como **LP11**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-297">Additionally, the **Location** field is set to **FL-001**, and the **License plate** field is set to **LP11**.</span></span> <span data-ttu-id="4c3aa-298">(Você pode adicionar esses campos à grade se eles não estiverem visíveis.)</span><span class="sxs-lookup"><span data-stu-id="4c3aa-298">(You can add these fields to the grid if they aren't visible.)</span></span>

<span data-ttu-id="4c3aa-299">As tabelas a seguir fornecem uma visão geral que mostra como o sistema manipula a reserva de lotes confirmada na ordem para ações de depósito específicas.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-299">The following tables provide an overview that shows how the system handles order-committed batch reservation for specific warehouse actions.</span></span> <span data-ttu-id="4c3aa-300">Para interpretar o conteúdo das tabelas, suponha que cada ação de depósito seja executada no contexto do trabalho de depósito existente que se origina de uma reserva de lotes confirmada na ordem ou que a execução de cada ação de depósito afete trabalhos desse tipo.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-300">To interpret the content in the tables, assume that each warehouse action is run in the context of existing warehouse work that originates from an order-committed batch reservation, or that execution of each warehouse action affects work of that type.</span></span>

> [!NOTE]
> <span data-ttu-id="4c3aa-301">Nessas tabelas, a coluna "Quantidade de lotes disponível" indica se há uma quantidade de lotes disponível além da quantidade já reservada para as atuais reservas confirmadas na ordem ou já reservada pelo trabalho de depósito que se origina das reservas desse tipo.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-301">In these tables, the "Batch quantity is available" column indicates whether a batch quantity is available in addition to the quantity that is either already reserved for the current order-committed reservations or already reserved by the warehouse work that originates from reservations of that type.</span></span>

#### <a name="override-the-pick-location-on-the-open-work"></a><span data-ttu-id="4c3aa-302">Substituir o local de separação no trabalho em aberto</span><span class="sxs-lookup"><span data-stu-id="4c3aa-302">Override the pick location on the open work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4c3aa-303">Principal parâmetro de configuração</span><span class="sxs-lookup"><span data-stu-id="4c3aa-303">Key setup parameter</span></span></th>
<th><span data-ttu-id="4c3aa-304">Quantidade de lotes disponível</span><span class="sxs-lookup"><span data-stu-id="4c3aa-304">Batch quantity is available</span></span></th>
<th><span data-ttu-id="4c3aa-305">Principais etapas do usuário</span><span class="sxs-lookup"><span data-stu-id="4c3aa-305">Key user steps</span></span></th>
<th><span data-ttu-id="4c3aa-306">Trabalho de depósito</span><span class="sxs-lookup"><span data-stu-id="4c3aa-306">Warehouse work</span></span></th>
<th><span data-ttu-id="4c3aa-307">Reserva de lotes confirmada na ordem</span><span class="sxs-lookup"><span data-stu-id="4c3aa-307">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="4c3aa-308">A opção <strong>Permitir substituição de local de separação</strong> está habilitada no trabalhador.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-308">The <strong>Allow pick location override</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="4c3aa-309">Sim</span><span class="sxs-lookup"><span data-stu-id="4c3aa-309">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-310">Selecione o item de menu <strong>Substituir local</strong> no WMA (Aplicativo Móvel de Depósito) quando você iniciar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-310">Select the <strong>Override location</strong> menu item on the Warehouse Mmobile App (WMA) when you start picking work.</span></span></li>
<li><span data-ttu-id="4c3aa-311">Selecione <strong>Sugerir</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-311">Select <strong>Suggest</strong>.</span></span></li>
<li><span data-ttu-id="4c3aa-312">Confirme o novo local que é sugerido com base na disponibilidade da quantidade de lotes.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-312">Confirm the new location that is suggested based on batch quantity availability.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="4c3aa-313">No trabalho atual, ocorrem as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-313">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="4c3aa-314">O local na linha de separação é atualizado para o novo local.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-314">The location on the pick line is updated to the new location.</span></span> <span data-ttu-id="4c3aa-315">(Se o local for controlado pela placa de licença, uma placa de licença aleatória será atribuída à transação de estoque de trabalho, e o trabalhador poderá fazer a separação a partir de qualquer placa de licença que tenha a quantidade disponível.)</span><span class="sxs-lookup"><span data-stu-id="4c3aa-315">(If the location is license plate–controlled, a random license plate is assigned to the work inventory transaction, and the worker can pick from any license plate that has available quantity.)</span></span></li>
<li><span data-ttu-id="4c3aa-316">Se a quantidade for encontrada em mais de uma placa de licença no novo local, a linha de separação original será dividida em várias linhas para correspondência com cada placa de licença.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-316">If the quantity is found on more than one license plate in the new location, the original pick line is split into multiple lines to match each license plate.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="4c3aa-317">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-317">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-318">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-318">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-319">Selecione o item de menu <strong>Substituir local</strong> no WMA quando você iniciar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-319">Select the <strong>Override location</strong> menu item on the WMA when you start picking work.</span></span></li>
<li><span data-ttu-id="4c3aa-320">Insira um local manualmente.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-320">Manually enter a location.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="4c3aa-321">A ação <strong>Substituir local</strong> não é possível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-321">The <strong>Override location</strong> action isn't possible.</span></span> <span data-ttu-id="4c3aa-322">Ela falha e um erro é lançado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-322">It fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="4c3aa-323">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-323">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a><span data-ttu-id="4c3aa-324">Botão Completo – divide uma linha de trabalho devido ao estouro no local do usuário</span><span class="sxs-lookup"><span data-stu-id="4c3aa-324">Full button – Split a work line because of overflow on the user location</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4c3aa-325">Principal parâmetro de configuração</span><span class="sxs-lookup"><span data-stu-id="4c3aa-325">Key setup parameter</span></span></th>
<th><span data-ttu-id="4c3aa-326">Quantidade de lotes disponível</span><span class="sxs-lookup"><span data-stu-id="4c3aa-326">Batch quantity is available</span></span></th>
<th><span data-ttu-id="4c3aa-327">Principais etapas do usuário</span><span class="sxs-lookup"><span data-stu-id="4c3aa-327">Key user steps</span></span></th>
<th><span data-ttu-id="4c3aa-328">Trabalho de depósito</span><span class="sxs-lookup"><span data-stu-id="4c3aa-328">Warehouse work</span></span></th>
<th><span data-ttu-id="4c3aa-329">Reserva de lotes confirmada na ordem</span><span class="sxs-lookup"><span data-stu-id="4c3aa-329">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="4c3aa-330">A opção <strong>Permitir divisão do trabalho</strong> está habilitada no item de menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-330">The <strong>Allow splitting of work</strong> option is enabled on the mobile device menu item.</span></span></td>
<td><span data-ttu-id="4c3aa-331">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-331">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-332">Selecione o item de menu <strong>Completo</strong> no WMA ao processar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-332">Select the <strong>Full</strong> menu item on the WMA when you process picking work.</span></span></li>
<li><span data-ttu-id="4c3aa-333">No campo <strong>Qtd da Separação</strong>, insira uma quantidade parcial da separação necessária para indicar a capacidade total.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-333">In the <strong>Pick Qty</strong> field, enter a partial quantity of the required pick to indicate the full capacity.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="4c3aa-334">No trabalho atual, a quantidade é atualizada para a quantidade restante que deve ser separada.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-334">On the current work, the quantity is updated to the remaining quantity that must be picked.</span></span></li>
<li><span data-ttu-id="4c3aa-335">O novo trabalho para a quantidade separada é criado e fechado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-335">New work for the picked quantity is created and closed.</span></span></li>
</ul></td>
<td><span data-ttu-id="4c3aa-336">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-336">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a><span data-ttu-id="4c3aa-337">Reduzir a quantidade separada de trabalho concluído (de uma carga)</span><span class="sxs-lookup"><span data-stu-id="4c3aa-337">Reduce the picked quantity of completed work (from a load)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4c3aa-338">Principal parâmetro de configuração</span><span class="sxs-lookup"><span data-stu-id="4c3aa-338">Key setup parameter</span></span></th>
<th><span data-ttu-id="4c3aa-339">Quantidade de lotes disponível</span><span class="sxs-lookup"><span data-stu-id="4c3aa-339">Batch quantity is available</span></span></th>
<th><span data-ttu-id="4c3aa-340">Principais etapas do usuário</span><span class="sxs-lookup"><span data-stu-id="4c3aa-340">Key user steps</span></span></th>
<th><span data-ttu-id="4c3aa-341">Trabalho de depósito</span><span class="sxs-lookup"><span data-stu-id="4c3aa-341">Warehouse work</span></span></th>
<th><span data-ttu-id="4c3aa-342">Reserva de lotes confirmada na ordem</span><span class="sxs-lookup"><span data-stu-id="4c3aa-342">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="4c3aa-343">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-343">Not applicable</span></span></td>
<td><span data-ttu-id="4c3aa-344">Sim</span><span class="sxs-lookup"><span data-stu-id="4c3aa-344">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-345">Abra a página <strong>Reduzir quantidade separada</strong> na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-345">Open the <strong>Reduce picked quantity</strong> page from the load line.</span></span></li>
<li><span data-ttu-id="4c3aa-346">Insira a quantidade total para anulação da separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-346">Enter the full quantity to unpick.</span></span></li>
<li><span data-ttu-id="4c3aa-347">Selecione um local/placa de licença "mover para".</span><span class="sxs-lookup"><span data-stu-id="4c3aa-347">Select a "move to" location/license plate.</span></span></li>
</ol>
</td>
<td>
<ul> 
<li><span data-ttu-id="4c3aa-348">O trabalho associado à linha de carga é cancelado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-348">Work that is associated with the load line is canceled.</span></span></li>
<li><span data-ttu-id="4c3aa-349">O novo trabalho o movimento de estoque é criado e fechado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-349">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="4c3aa-350">A quantidade é reservada novamente para o mesmo lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-350">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="4c3aa-351">O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-351">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-352">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-352">No</span></span></td>
<td><span data-ttu-id="4c3aa-353">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-353">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-354">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-354">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-355">A quantidade é reservada novamente para o mesmo lote, assim como para o mesmo local e placa de licença (se o local for controlado pela placa de licença) que foram inseridos durante a anulação da separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-355">The quantity is re-reserved for the same batch, and for the same location and license plate (if the location is license plate–controlled) that were entered during unpicking.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a><span data-ttu-id="4c3aa-356">Mover um item em um depósito</span><span class="sxs-lookup"><span data-stu-id="4c3aa-356">Move an item within a warehouse</span></span>

> [!NOTE]
> <span data-ttu-id="4c3aa-357">Essa ação de depósito se aplica somente ao movimento do tipo **Processo de criação de trabalho**, e não ao movimento por modelo.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-357">This warehouse action is applicable only to movement of the **Work creation process** type, not to movement by template.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4c3aa-358">Principal parâmetro de configuração</span><span class="sxs-lookup"><span data-stu-id="4c3aa-358">Key setup parameter</span></span></th>
<th><span data-ttu-id="4c3aa-359">Quantidade de lotes disponível</span><span class="sxs-lookup"><span data-stu-id="4c3aa-359">Batch quantity is available</span></span></th>
<th><span data-ttu-id="4c3aa-360">Principais etapas do usuário</span><span class="sxs-lookup"><span data-stu-id="4c3aa-360">Key user steps</span></span></th>
<th><span data-ttu-id="4c3aa-361">Trabalho de depósito</span><span class="sxs-lookup"><span data-stu-id="4c3aa-361">Warehouse work</span></span></th>
<th><span data-ttu-id="4c3aa-362">Reserva de lotes confirmada na ordem</span><span class="sxs-lookup"><span data-stu-id="4c3aa-362">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="4c3aa-363">A opção <strong>Permitir movimento de estoque com trabalho associado</strong> está habilitada no trabalhador.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-363">The <strong>Allow movement of inventory with associated work</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="4c3aa-364">Sim</span><span class="sxs-lookup"><span data-stu-id="4c3aa-364">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-365">Inicie um movimento no WMA.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-365">Start a movement on the WMA.</span></span></li>
<li><span data-ttu-id="4c3aa-366">Insira os locais "de" e "para".</span><span class="sxs-lookup"><span data-stu-id="4c3aa-366">Enter "from" and "to" locations.</span></span></li>
</ol></td>
<td>
<ul>
<li><span data-ttu-id="4c3aa-367">Em todo o trabalho existente que é afetado pelo movimento, o local de separação é atualizado para o novo local "para".</span><span class="sxs-lookup"><span data-stu-id="4c3aa-367">On all existing work that is affected by the move, the pick location is updated to the new "to" location.</span></span></li>
<li><span data-ttu-id="4c3aa-368">O novo trabalho o movimento de estoque é criado e fechado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-368">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="4c3aa-369">Todas as reservas existentes que são afetadas pelo movimento da quantidade do local especificado são reservadas novamente para o mesmo lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-369">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch.</span></span> <span data-ttu-id="4c3aa-370">O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-370">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-371">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-371">No</span></span></td>
<td><span data-ttu-id="4c3aa-372">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-372">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-373">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-373">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-374">Todas as reservas existentes que são afetadas pelo movimento da quantidade do local especificado são reservadas novamente para o mesmo lote, assim como para o novo local "para" e a placa de licença (se o local for controlado pela placa de licença).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-374">All existing reservations that are affected by the quantity movement from the given location are re-reserved for the same batch, and for the new "to" location and license plate (if the location is license plate–controlled).</span></span></td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a><span data-ttu-id="4c3aa-375">Reverter a quantidade separada de trabalho concluído (de uma carga ou uma onda)</span><span class="sxs-lookup"><span data-stu-id="4c3aa-375">Reverse the picked quantity of completed work (from a load or a wave)</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4c3aa-376">Principal parâmetro de configuração</span><span class="sxs-lookup"><span data-stu-id="4c3aa-376">Key setup parameter</span></span></th>
<th><span data-ttu-id="4c3aa-377">Quantidade de lotes disponível</span><span class="sxs-lookup"><span data-stu-id="4c3aa-377">Batch quantity is available</span></span></th>
<th><span data-ttu-id="4c3aa-378">Principais etapas do usuário</span><span class="sxs-lookup"><span data-stu-id="4c3aa-378">Key user steps</span></span></th>
<th><span data-ttu-id="4c3aa-379">Trabalho de depósito</span><span class="sxs-lookup"><span data-stu-id="4c3aa-379">Warehouse work</span></span></th>
<th><span data-ttu-id="4c3aa-380">Reserva de lotes confirmada na ordem</span><span class="sxs-lookup"><span data-stu-id="4c3aa-380">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'><span data-ttu-id="4c3aa-381">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-381">Not applicable</span></span></td>
<td><span data-ttu-id="4c3aa-382">Sim</span><span class="sxs-lookup"><span data-stu-id="4c3aa-382">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-383">Abra a página <strong>Reverter trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-383">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="4c3aa-384">Na página de solicitação, selecione a opção <strong>Deixar os itens no local atual</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-384">On the request page, select the <strong>Leave items at current location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="4c3aa-385">Todo o trabalho associado à carga é cancelado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-385">All work that is associated with the load is canceled.</span></span></td>
<td><span data-ttu-id="4c3aa-386">A quantidade é reservada novamente para o mesmo lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-386">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="4c3aa-387">O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-387">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-388">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-388">No</span></span></td>
<td><span data-ttu-id="4c3aa-389">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-389">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-390">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-390">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-391">A quantidade é reservada novamente para o mesmo lote, assim como para o local e a placa de licença onde a quantidade foi deixada no estorno.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-391">The quantity is re-reserved for the same batch, and for the location and license plate where the quantity was left upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-392">Sim</span><span class="sxs-lookup"><span data-stu-id="4c3aa-392">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-393">Abra a página <strong>Reverter trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-393">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="4c3aa-394">Na página de solicitação, selecione a opção <strong>Atribuir itens a este local</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-394">On the request page, select the <strong>Assign items to this location</strong> option.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="4c3aa-395">O trabalho atual é cancelado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-395">The current work is canceled.</span></span></li>
<li><span data-ttu-id="4c3aa-396">O novo trabalho o movimento de estoque é criado e fechado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-396">New work for the inventory movement is created and closed.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="4c3aa-397">A quantidade é reservada novamente para o mesmo lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-397">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="4c3aa-398">O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-398">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-399">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-399">No</span></span></td>
<td><span data-ttu-id="4c3aa-400">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-400">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-401">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-401">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-402">A quantidade é reservada novamente para o mesmo lote, assim como para o local e a placa de licença aos quais a quantidade foi atribuída no estorno.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-402">The quantity is re-reserved for the same batch, and for the location and license plate that the quantity was assigned to upon reversal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-403">Sim/Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-403">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-404">Abra a página <strong>Reverter trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-404">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="4c3aa-405">Na página de solicitação, selecione a opção <strong>Mover itens para este local</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-405">On the request page, select the <strong>Move items to this location</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="4c3aa-406">O estorno não é permitido.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-406">Reversal isn't supported.</span></span></td>
<td><span data-ttu-id="4c3aa-407">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-407">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-408">Sim/Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-408">Yes/No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-409">Abra a página <strong>Reverter trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-409">Open the <strong>Reverse work</strong> page.</span></span></li>
<li><span data-ttu-id="4c3aa-410">Na página de solicitação, selecione a opção <strong>Mover itens com base em diretivas de local</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-410">On the request page, select the <strong>Move items based on location directives</strong> option.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="4c3aa-411">O estorno não é permitido.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-411">Reversal isn't supported.</span></span> </td>
<td><span data-ttu-id="4c3aa-412">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-412">Not applicable</span></span></td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a><span data-ttu-id="4c3aa-413">Separar uma quantidade insuficiente – registre a quantidade como fisicamente não encontrada no local/placa de licença ao executar o trabalho de separação</span><span class="sxs-lookup"><span data-stu-id="4c3aa-413">Short-pick a quantity – Register the quantity as physically not found at the location/license plate while you perform picking work</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4c3aa-414">Principal parâmetro de configuração</span><span class="sxs-lookup"><span data-stu-id="4c3aa-414">Key setup parameter</span></span></th>
<th><span data-ttu-id="4c3aa-415">Quantidade de lotes disponível</span><span class="sxs-lookup"><span data-stu-id="4c3aa-415">Batch quantity is available</span></span></th>
<th><span data-ttu-id="4c3aa-416">Principais etapas do usuário</span><span class="sxs-lookup"><span data-stu-id="4c3aa-416">Key user steps</span></span></th>
<th><span data-ttu-id="4c3aa-417">Trabalho de depósito</span><span class="sxs-lookup"><span data-stu-id="4c3aa-417">Warehouse work</span></span></th>
<th><span data-ttu-id="4c3aa-418">Reserva de lotes confirmada na ordem</span><span class="sxs-lookup"><span data-stu-id="4c3aa-418">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="4c3aa-419">Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Nenhum</strong>, <strong>Ajustar estoque</strong> = <strong>Sim</strong> e <strong>Remover reservas</strong> = <strong>Não</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-419">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span></td>
<td><span data-ttu-id="4c3aa-420">Sim</span><span class="sxs-lookup"><span data-stu-id="4c3aa-420">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-421">Selecione o item de menu <strong>Separação insuficiente</strong> no WMA ao executar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-421">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="4c3aa-422">No campo <strong>Separar quantidade</strong>, digite <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-422">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="4c3aa-423">No campo <strong>Motivo</strong>, insira <strong>Nenhuma realocação</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-423">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="4c3aa-424">O trabalho atual é fechado e a quantidade separada é 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-424">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="4c3aa-425">Uma transação de estoque do tipo <strong>Contagem</strong> e do tipo de saída <strong>Vendido</strong> é criada para representar o ajuste.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-425">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="4c3aa-426">A quantidade é reservada novamente para o mesmo lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-426">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="4c3aa-427">O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-427">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-428">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-428">No</span></span></td>
<td><span data-ttu-id="4c3aa-429">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-429">See the previous row.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4c3aa-430">A ação de separação insuficiente falha e um erro é lançado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-430">The short-picking action fails, and an error is thrown.</span></span></li>
<li><span data-ttu-id="4c3aa-431">O trabalho atual permanece aberto.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-431">The current work remains open.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="4c3aa-432">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-432">Not applicable</span></span></td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="4c3aa-433">Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Nenhum</strong>, <strong>Ajustar estoque</strong> = <strong>Sim</strong> e <strong>Remover reservas</strong> = <strong>Sim</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-433">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>None</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span></td>
<td><span data-ttu-id="4c3aa-434">Sim</span><span class="sxs-lookup"><span data-stu-id="4c3aa-434">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-435">Selecione o item de menu <strong>Separação insuficiente</strong> no WMA ao executar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-435">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="4c3aa-436">No campo <strong>Separar quantidade</strong>, digite <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-436">In the <strong>Pick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="4c3aa-437">No campo <strong>Motivo</strong>, insira <strong>Nenhuma realocação</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-437">In the <strong>Reason</strong> field, enter <strong>No reallocation</strong>.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="4c3aa-438">O trabalho atual é fechado e a quantidade separada é 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-438">The current work is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="4c3aa-439">Uma transação de estoque do tipo <strong>Contagem</strong> e do tipo de saída <strong>Vendido</strong> é criada para representar o ajuste.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-439">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="4c3aa-440">Todas as reservas existentes que são afetadas pelo ajuste da quantidade no local da separação insuficiente são reservadas novamente para o mesmo lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-440">All existing reservations that are affected by the quantity adjustment in the short-picked location are re-reserved for the same batch.</span></span> <span data-ttu-id="4c3aa-441">O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-441">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-442">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-442">No</span></span></td>
<td><span data-ttu-id="4c3aa-443">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-443">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-444">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-444">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-445">Todas as reservas existentes que são afetadas pelo ajuste da quantidade no local da separação insuficiente são removidas.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-445">All existing reservations that are affected by the quantity adjustment in the short-picked location are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-446">Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Manual</strong>, <strong>Ajustar estoque</strong> = <strong>Sim</strong> e <strong>Remover reservas</strong> = <strong>Não/Sim</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-446">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No/Yes</strong>.</span></span> <span data-ttu-id="4c3aa-447">Além disso, a opção <strong>Permitir realocação manual de itens</strong> é habilitada no trabalhador.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-447">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="4c3aa-448">Sim</span><span class="sxs-lookup"><span data-stu-id="4c3aa-448">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-449">Selecione o item de menu <strong>Separação insuficiente</strong> no WMA ao executar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-449">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="4c3aa-450">No campo <strong>Separar Quantidade Insuficiente</strong>, digite <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-450">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="4c3aa-451">No campo <strong>Motivo</strong>, selecione <strong>Separação Insuficiente com realocação manual</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-451">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="4c3aa-452">Selecione o local/placa de licença na lista.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-452">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="4c3aa-453">No trabalho atual, ocorrem as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-453">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="4c3aa-454">A linha de separação é fechada e a quantidade separada é 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-454">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="4c3aa-455">A linha de colocação é cancelada.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-455">The put line is canceled.</span></span></li>
<li><span data-ttu-id="4c3aa-456">Uma nova linha de separação é criada.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-456">A new pick line is created.</span></span> <span data-ttu-id="4c3aa-457">Ela usa o local/placa de licença que o usuário selecionou.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-457">It uses the location/license plate that the user selected.</span></span></li>
<li><span data-ttu-id="4c3aa-458">Uma nova linha de colocação é criada.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-458">A new put line is created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="4c3aa-459">Uma transação de estoque do tipo <strong>Contagem</strong> e do tipo de saída <strong>Vendido</strong> é criada para representar o ajuste.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-459">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="4c3aa-460">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-460">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-461">Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Manual</strong>, <strong>Ajustar estoque</strong> = <strong>Sim</strong> e <strong>Remover reservas</strong> = <strong>Não</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-461">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>No</strong>.</span></span> <span data-ttu-id="4c3aa-462">Além disso, a opção <strong>Permitir realocação manual de itens</strong> é habilitada no trabalhador.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-462">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="4c3aa-463">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-463">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-464">Selecione o item de menu <strong>Separação insuficiente</strong> no WMA ao executar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-464">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="4c3aa-465">No campo <strong>Separar Quantidade Insuficiente</strong>, digite <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-465">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="4c3aa-466">No campo <strong>Motivo</strong>, selecione <strong>Separação Insuficiente com realocação manual</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-466">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="4c3aa-467">A ação de separação insuficiente falha e um erro é lançado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-467">The short-picking action fails, and an error is thrown.</span></span></td>
<td><span data-ttu-id="4c3aa-468">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-468">Not applicable</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-469">Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Manual</strong>, <strong>Ajustar estoque</strong> = <strong>Sim</strong> e <strong>Remover reservas</strong> = <strong>Sim</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-469">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Manual</strong>, <strong>Adjust inventory</strong> = <strong>Yes</strong>, and <strong>Remove reservations</strong> = <strong>Yes</strong>.</span></span> <span data-ttu-id="4c3aa-470">Além disso, a opção <strong>Permitir realocação manual de itens</strong> é habilitada no trabalhador.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-470">Additionally, the <strong>Allow manual item reallocation</strong> option is enabled on the worker.</span></span></td>
<td><span data-ttu-id="4c3aa-471">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-471">No</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-472">Selecione o item de menu <strong>Separação insuficiente</strong> no WMA ao executar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-472">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="4c3aa-473">No campo <strong>Separar Quantidade Insuficiente</strong>, digite <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-473">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="4c3aa-474">No campo <strong>Motivo</strong>, selecione <strong>Separação Insuficiente com realocação manual</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-474">In the <strong>Reason</strong> field, select <strong>Short Picking with manual reallocation</strong>.</span></span></li>
<li><span data-ttu-id="4c3aa-475">Selecione o local/placa de licença na lista.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-475">Select the location/license plate in the list.</span></span></li>
</ol>
</td>
<td>
<ul>
<li><span data-ttu-id="4c3aa-476">No trabalho atual, ocorrem as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-476">On the current work, the following actions occur:</span></span>
<ul>
<li><span data-ttu-id="4c3aa-477">A linha de separação é fechada e a quantidade separada é 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-477">The pick line is closed, and the picked quantity is 0 (zero).</span></span></li>
<li><span data-ttu-id="4c3aa-478">A linha de colocação é cancelada.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-478">The put line is canceled.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="4c3aa-479">Uma transação de estoque do tipo <strong>Contagem</strong> e do tipo de saída <strong>Vendido</strong> é criada para representar o ajuste.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-479">An inventory transaction of the <strong>Counting</strong> type and the <strong>Sold</strong> issue type is created to represent the adjustment.</span></span></li>
</ul>
</td>
<td><span data-ttu-id="4c3aa-480">Todas as reservas existentes que são afetadas pelo ajuste da quantidade no local/placa de licença da separação insuficiente são removidas.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-480">All existing reservations that are affected by the quantity adjustment in the short-picked location/license plate are removed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-481">Uma exceção de trabalho do tipo <strong>Separação insuficiente</strong> é configurada, onde <strong>Realocação de item</strong> = <strong>Automática</strong>, <strong>Ajustar estoque</strong> = <strong>Sim/Não</strong> e <strong>Remover reservas</strong> = <strong>Sim/Não</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-481">A work exception of the <strong>Short pick</strong> type is set up, where <strong>Item reallocation</strong> = <strong>Automatic</strong>, <strong>Adjust inventory</strong> = <strong>Yes/No</strong>, and <strong>Remove reservations</strong> = <strong>Yes/No</strong>.</span></span></td>
<td><span data-ttu-id="4c3aa-482">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-482">Not applicable</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-483">Selecione o item de menu <strong>Separação insuficiente</strong> no WMA ao executar o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-483">Select the <strong>Shortpick</strong> menu item on the WMA when you run picking work.</span></span></li>
<li><span data-ttu-id="4c3aa-484">No campo <strong>Separar Quantidade Insuficiente</strong>, digite <strong>0</strong> (zero).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-484">In the <strong>Shortpick Quantity</strong> field, enter <strong>0</strong> (zero).</span></span></li>
<li><span data-ttu-id="4c3aa-485">No campo <strong>Motivo</strong>, selecione <strong>Separação Insuficiente com realocação automática</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-485">In the <strong>Reason</strong> field, select <strong>Short Picking with automatic reallocation</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="4c3aa-486">A separação insuficiente que envolve a realocação automática não é permitida.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-486">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
<td><span data-ttu-id="4c3aa-487">A separação insuficiente que envolve a realocação automática não é permitida.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-487">Short-picking that involves automatic reallocation isn't supported.</span></span></td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a><span data-ttu-id="4c3aa-488">Alterar o status do estoque</span><span class="sxs-lookup"><span data-stu-id="4c3aa-488">Change the inventory status</span></span>

> [!NOTE]
> <span data-ttu-id="4c3aa-489">Essa ação de depósito pode ser executada a partir de vários pontos de entrada.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-489">This warehouse action can be performed from multiple entry points.</span></span> <span data-ttu-id="4c3aa-490">O exemplo mostrado aqui usa a ação **Alteração do status do estoque** na página **Disponibilidade por local**.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-490">The example that is shown here uses **Inventory status change** action on the **On-hand by location** page.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="4c3aa-491">Principal parâmetro de configuração</span><span class="sxs-lookup"><span data-stu-id="4c3aa-491">Key setup parameter</span></span></th>
<th><span data-ttu-id="4c3aa-492">Quantidade de lotes disponível</span><span class="sxs-lookup"><span data-stu-id="4c3aa-492">Batch quantity is available</span></span></th>
<th><span data-ttu-id="4c3aa-493">Principais etapas do usuário</span><span class="sxs-lookup"><span data-stu-id="4c3aa-493">Key user steps</span></span></th>
<th><span data-ttu-id="4c3aa-494">Trabalho de depósito</span><span class="sxs-lookup"><span data-stu-id="4c3aa-494">Warehouse work</span></span></th>
<th><span data-ttu-id="4c3aa-495">Reserva de lotes confirmada na ordem</span><span class="sxs-lookup"><span data-stu-id="4c3aa-495">Order-committed batch reservation</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><span data-ttu-id="4c3aa-496">Na guia <strong>Depósito</strong>, no registro <strong>Depósito</strong>, o campo <strong>Remover reservas e marcações</strong> está definido como <strong>Reservas</strong> ou <strong>Marcações e reservas</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-496">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>Reservations</strong> or <strong>Markings and reservations</strong>.</span></span></td>
<td><span data-ttu-id="4c3aa-497">Sim</span><span class="sxs-lookup"><span data-stu-id="4c3aa-497">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-498">Selecione um local específico.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-498">Select a specific location.</span></span></li>
<li><span data-ttu-id="4c3aa-499">Selecione uma linha que tenha um item específico, um local e uma placa de licença (se o local for controlado pela placa de licença).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-499">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="4c3aa-500">Selecione <strong>Alteração do status do estoque</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-500">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="4c3aa-501">Defina o campo <strong>Status do estoque</strong> como <strong>Bloqueio</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-501">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="4c3aa-502">As alterações de status do estoque não são permitidas para as quantidades reservadas para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-502">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4c3aa-503">A quantidade é reservada novamente para o mesmo lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-503">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="4c3aa-504">O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-504">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></li>
<li><span data-ttu-id="4c3aa-505">Duas transações de estoque do tipo <strong>Alteração do status do estoque</strong> são criadas para representar a alteração na dimensão de status do estoque.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-505">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="4c3aa-506">Uma transação de estoque do tipo <strong>Bloqueio de estoque</strong> e do tipo de saída <strong>Qtd. reservada</strong> é criada para representar a reservar da quantidade bloqueada.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-506">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-507">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-507">No</span></span></td>
<td><span data-ttu-id="4c3aa-508">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-508">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-509">As alterações de status do estoque não são permitidas para as quantidades reservadas para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-509">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td>
<ul>
<li><span data-ttu-id="4c3aa-510">A reserva é removida.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-510">The reservation is removed.</span></span></li>
<li><span data-ttu-id="4c3aa-511">Duas transações de estoque do tipo <strong>Alteração do status do estoque</strong> são criadas para representar a alteração na dimensão de status do estoque.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-511">Two inventory transactions of the <strong>Inventory status change</strong> type are created to represent the change in the inventory status dimension.</span></span></li>
<li><span data-ttu-id="4c3aa-512">Uma transação de estoque do tipo <strong>Bloqueio de estoque</strong> e do tipo de saída <strong>Qtd. reservada</strong> é criada para representar a reservar da quantidade bloqueada.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-512">An inventory transaction of the <strong>Inventory blocking</strong> type and the <strong>Reserved physical</strong> issue type is created to represent the reservation of the blocked quantity.</span></span></li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'><span data-ttu-id="4c3aa-513">Na guia <strong>Depósito</strong>, no registro <strong>Depósito</strong>, o campo <strong>Remover reservas e marcações</strong> está definido como <strong>Nenhum</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-513">On the <strong>Warehouse</strong> tab, in the <strong>Warehouse</strong> record, the <strong>Remove reservations and markings</strong> field is set to <strong>None</strong>.</span></span></td>
<td><span data-ttu-id="4c3aa-514">Sim</span><span class="sxs-lookup"><span data-stu-id="4c3aa-514">Yes</span></span></td>
<td>
<ol>
<li><span data-ttu-id="4c3aa-515">Selecione um local específico.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-515">Select a specific location.</span></span></li>
<li><span data-ttu-id="4c3aa-516">Selecione uma linha que tenha um item específico, um local e uma placa de licença (se o local for controlado pela placa de licença).</span><span class="sxs-lookup"><span data-stu-id="4c3aa-516">Select a line that has a specific item, location, and license plate (if the location is license plate–controlled).</span></span></li>
<li><span data-ttu-id="4c3aa-517">Selecione <strong>Alteração do status do estoque</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-517">Select <strong>Inventory status change</strong>.</span></span></li>
<li><span data-ttu-id="4c3aa-518">Defina o campo <strong>Status do estoque</strong> como <strong>Bloqueio</strong>.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-518">Set the <strong>Inventory status</strong> field to <strong>Blocking</strong>.</span></span></li>
</ol>
</td>
<td><span data-ttu-id="4c3aa-519">As alterações de status do estoque não são permitidas para as quantidades reservadas para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-519">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="4c3aa-520">A quantidade é reservada novamente para o mesmo lote.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-520">The quantity is re-reserved for the same batch.</span></span> <span data-ttu-id="4c3aa-521">O sistema atribui aleatoriamente um local e uma placa de licença (se o local for controlado pela placa de licença) onde quantidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-521">The system randomly assigns a location and license plate (if the location is license plate–controlled) where the quantity is available.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="4c3aa-522">Não</span><span class="sxs-lookup"><span data-stu-id="4c3aa-522">No</span></span></td>
<td><span data-ttu-id="4c3aa-523">Consulte a linha anterior.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-523">See the previous row.</span></span></td>
<td><span data-ttu-id="4c3aa-524">As alterações de status do estoque não são permitidas para as quantidades reservadas para o trabalho.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-524">Inventory status changes aren't allowed for quantities that are reserved for work.</span></span></td>
<td><span data-ttu-id="4c3aa-525">Alterações de status do estoque não são permitidas.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-525">Inventory status changes aren't allowed.</span></span></td>
</tr>
</tbody>
</table>

## <a name="limitations"></a><span data-ttu-id="4c3aa-526">Limitações</span><span class="sxs-lookup"><span data-stu-id="4c3aa-526">Limitations</span></span>

- <span data-ttu-id="4c3aa-527">A funcionalidade de reserva de dimensão no nível de depósito flexível não oferece suporte aos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="4c3aa-527">The flexible warehouse-level dimension reservation functionality doesn't support the following features:</span></span>

    - <span data-ttu-id="4c3aa-528">Gerenciamento de peso variável</span><span class="sxs-lookup"><span data-stu-id="4c3aa-528">Catch weight management</span></span>
    - <span data-ttu-id="4c3aa-529">Estoque físico negativo</span><span class="sxs-lookup"><span data-stu-id="4c3aa-529">Physical negative inventory</span></span>
    - <span data-ttu-id="4c3aa-530">Reserva em relação ao fornecimento solicitado</span><span class="sxs-lookup"><span data-stu-id="4c3aa-530">Reservation against ordered supply</span></span>
    - <span data-ttu-id="4c3aa-531">Ordens de transferência e separação de matéria-prima</span><span class="sxs-lookup"><span data-stu-id="4c3aa-531">Transfer orders and raw material picking</span></span>

- <span data-ttu-id="4c3aa-532">A regra de consolidação de contêineres para empacotamento por unidade de diretiva tem limitações.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-532">The container consolidation rule for packing by directive unit has limitations.</span></span> <span data-ttu-id="4c3aa-533">Para as reservas confirmadas na ordem, é recomendável não usar os modelos de compilação de contêiner em que o campo **Empacotar por unidade de diretiva** esteja habilitado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-533">For order-committed reservations, we recommend that you not use container build templates where the **Pack by directive unit** field is enabled.</span></span> <span data-ttu-id="4c3aa-534">No design atual, as diretivas de local não são usadas quando o trabalho de depósito é criado.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-534">In the current design, location directives aren't used when warehouse work is created.</span></span> <span data-ttu-id="4c3aa-535">Portanto, somente a menor unidade no grupo de sequências de unidades (a unidade de estoque) é aplicada durante a etapa da onda de transporte em contêineres.</span><span class="sxs-lookup"><span data-stu-id="4c3aa-535">Therefore, only the lowest unit in the unit sequence group (the inventory unit) is applied during the containerization wave step.</span></span>
