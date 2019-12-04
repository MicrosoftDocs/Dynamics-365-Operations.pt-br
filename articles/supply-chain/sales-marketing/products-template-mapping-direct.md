---
title: Sincronizar produtos diretamente do Supply Chain Management com produtos do Sales
description: Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos do Dynamics 365 Supply Chain Management para o Dynamics 365 Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 1a96fda4e7f7b6407c51ee4056088d05027462cf
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813238"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a><span data-ttu-id="28f12-103">Sincronizar produtos diretamente do Supply Chain Management com produtos do Sales</span><span class="sxs-lookup"><span data-stu-id="28f12-103">Synchronize products directly from Supply Chain Management to products in Sales</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="28f12-104">Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Common Data Service para Aplicativos](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="28f12-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="28f12-105">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos diretamente do Dynamics 365 Supply Chain Management para o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-105">This topic discusses the templates and underlying tasks that are used to synchronize products directly from Dynamics 365 Supply Chain Management to Dynamics 365 Sales.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="28f12-106">Fluxo de dados no Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="28f12-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="28f12-107">A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="28f12-108">Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="28f12-109">A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="28f12-110">[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="28f12-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="28f12-111">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="28f12-111">Templates and tasks</span></span>

<span data-ttu-id="28f12-112">Para acessar os modelos disponíveis, abra o [Centro de administração do Power Apps](https://admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="28f12-112">To access the available templates, open [Power Apps Admin Center](https://admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="28f12-113">Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="28f12-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="28f12-114">O modelo e as tarefas subjacentes a seguir são usados para sincronizar produtos do Supply Chain Management para o Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-114">The following template and underlying tasks are used to synchronize products from Supply Chain Management to Sales.</span></span>

- <span data-ttu-id="28f12-115">**Nome do modelo na Integração de dados:** Produtos (Supply Chain Management para Sales) — Direto</span><span class="sxs-lookup"><span data-stu-id="28f12-115">**Name of the template in Data integration:** Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="28f12-116">**Nome da tarefa no projeto de Integração de dados:** Produtos</span><span class="sxs-lookup"><span data-stu-id="28f12-116">**Name of the task in the Data integration project:** Products</span></span>

<span data-ttu-id="28f12-117">Nenhuma tarefa de sincronização é necessária para que a sincronização de produtos ocorra.</span><span class="sxs-lookup"><span data-stu-id="28f12-117">No synchronization tasks are required before product synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="28f12-118">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="28f12-118">Entity set</span></span>

| <span data-ttu-id="28f12-119">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="28f12-119">Supply Chain Management</span></span>    | <span data-ttu-id="28f12-120">Vendas</span><span class="sxs-lookup"><span data-stu-id="28f12-120">Sales</span></span>    |
|----------------------------|----------|
| <span data-ttu-id="28f12-121">Produtos liberados comercializáveis</span><span class="sxs-lookup"><span data-stu-id="28f12-121">Sellable released products</span></span> | <span data-ttu-id="28f12-122">Produtos</span><span class="sxs-lookup"><span data-stu-id="28f12-122">Products</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="28f12-123">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="28f12-123">Entity flow</span></span>

<span data-ttu-id="28f12-124">Os produtos são gerenciados no Supply Chain Management e sincronizados para o Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-124">Products are managed in Supply Chain Management and synchronized to Sales.</span></span> <span data-ttu-id="28f12-125">A entidade de dados **Produtos liberados comercializáveis** no Supply Chain Management só exporta produtos *comercializáveis*.</span><span class="sxs-lookup"><span data-stu-id="28f12-125">The **Sellable released products** data entity in Supply Chain Management exports only products that are *sellable*.</span></span> <span data-ttu-id="28f12-126">Os produtos comercializáveis são produtos contendo as informações necessárias para serem usados em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="28f12-126">Sellable products are products that have the information that they require in order to be used on a sales order.</span></span> <span data-ttu-id="28f12-127">As mesmas regras se aplicam quando um produto é validado usando a função **Validar** na página **Produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="28f12-127">The same rules apply when a product is validated by using the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="28f12-128">O número do produto é usado como uma chave.</span><span class="sxs-lookup"><span data-stu-id="28f12-128">The product number is used as a key.</span></span> <span data-ttu-id="28f12-129">Portanto, quando variantes do produto são sincronizadas para o Sales, cada variante do produto tem uma ID de produto individual.</span><span class="sxs-lookup"><span data-stu-id="28f12-129">Therefore, when product variants are synchronized to Sales, each product variant has an individual product ID.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="28f12-130">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="28f12-130">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="28f12-131">No Sales, um novo campo **É Mantido Externamente** foi adicionado em produtos para indicar que determinado produto é mantido externamente.</span><span class="sxs-lookup"><span data-stu-id="28f12-131">In Sales, a new **Is Externally Maintained** field has been added on products to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="28f12-132">Por padrão, o valor é definido como **Sim** durante uma importação para o Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-132">By default, the value is set to **Yes** during an import to Sales.</span></span> <span data-ttu-id="28f12-133">Os valores a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="28f12-133">The following values are available:</span></span>

- <span data-ttu-id="28f12-134">**Sim** — O produto foi originado do Supply Chain Management e não será editável no Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-134">**Yes** – The product originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="28f12-135">**Não** – O produto foi inserido diretamente no Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-135">**No** – The product was entered directly in Sales.</span></span>
- <span data-ttu-id="28f12-136">**(Em branco)** – O produto existia no Sales antes de a solução Prospect to cash ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="28f12-136">**(Blank)** – The product existed in Sales before the Prospect to cash solution was enabled.</span></span>

<span data-ttu-id="28f12-137">O campo **É Mantido Externamente** ajuda a garantir que somente as cotações e ordens de venda com produtos mantidos externamente serão sincronizadas para o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="28f12-137">The **Is Externally Maintained** field helps ensure that only quotations and sales orders that have externally maintained products will be synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="28f12-138">Os Produtos mantidos externamente são adicionados de forma automática à primeira lista de preços válida com a mesma moeda.</span><span class="sxs-lookup"><span data-stu-id="28f12-138">Externally maintained products are automatically added to the first valid price list that has the same currency.</span></span> <span data-ttu-id="28f12-139">Listas de preços são organizadas em ordem alfabética por nome.</span><span class="sxs-lookup"><span data-stu-id="28f12-139">Price lists are organized alphabetically by name.</span></span> <span data-ttu-id="28f12-140">O preço de venda do produto do Supply Chain Management é usado como o preço na lista de preços.</span><span class="sxs-lookup"><span data-stu-id="28f12-140">The product sales price from Supply Chain Management is used as the price on the price list.</span></span> <span data-ttu-id="28f12-141">Portanto, é preciso existir uma lista de preços no Sales para cada moeda de venda de produto no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="28f12-141">Therefore, there must be a price list in Sales for every product sales currency in Supply Chain Management.</span></span> <span data-ttu-id="28f12-142">A moeda dos produtos liberados comercializáveis é definida como a moeda contábil da entidade legal da qual o produto é exportado.</span><span class="sxs-lookup"><span data-stu-id="28f12-142">The currency on the released sellable products is set to the accounting currency in the legal entity that the product is exported from.</span></span>

> [!NOTE]
> - <span data-ttu-id="28f12-143">A sincronização de produto só terá êxito se houver uma lista de preços com uma moeda correspondente.</span><span class="sxs-lookup"><span data-stu-id="28f12-143">Product synchronization will not succeed unless there is a price list that has a matching currency.</span></span>
> - <span data-ttu-id="28f12-144">Você pode controlar a lista de preços usada com a integração mapeando o pricelevelid.name [Lista de Preços Padrão (Nome)] no projeto de Integração de Dados.</span><span class="sxs-lookup"><span data-stu-id="28f12-144">You can control the used price list with the integration by mapping the pricelevelid.name [Default Price List (Name)] in the Data Integration project.</span></span> <span data-ttu-id="28f12-145">A entrada deve ser toda em letras minúsculas.</span><span class="sxs-lookup"><span data-stu-id="28f12-145">The input has to be in all lowercase letters.</span></span> <span data-ttu-id="28f12-146">Por exemplo, o padrão de uma lista de preços no “Sales” chamada 'Padrão' seria: Campo de destino: pricelevelid.name [Lista de Preços Padrão (Nome]) e Tipo de mapa: [ { "transformType": "Padrão ", "defaultValue": "padrão" } ].</span><span class="sxs-lookup"><span data-stu-id="28f12-146">For example, the default for a price list in Sales named ‘Standard’ would be: Destination field: pricelevelid.name [Default Price List (Name)] and Map type: [ { "transformType": "Default", "defaultValue": "standard" } ].</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="28f12-147">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="28f12-147">Preconditions and mapping setup</span></span>

- <span data-ttu-id="28f12-148">Antes de executar a sincronização pela primeira vez, preencha a Tabela de produtos distintos para os produtos existentes no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="28f12-148">Before you run the synchronization for the first time, you must fill the Distinct product table for existing products in Supply Chain Management.</span></span> <span data-ttu-id="28f12-149">Os produtos existentes não serão sincronizados até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="28f12-149">Existing products won't be synchronized until this job is completed.</span></span>

    1. <span data-ttu-id="28f12-150">No Supply Chain Management, use Pesquisar para procurar **Preencher tabela de produtos distintos**.</span><span class="sxs-lookup"><span data-stu-id="28f12-150">In Supply Chain Management, use Search to search for **Populate distinct product table**.</span></span>
    2. <span data-ttu-id="28f12-151">Selecione **Preencher tabela de produtos distintos** para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="28f12-151">Select **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="28f12-152">Este trabalho deve ser executado apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="28f12-152">This job must be run only one time.</span></span>

- <span data-ttu-id="28f12-153">Verifique se existe o mapa de valores obrigatório para a unidade de medida (UDM) de vendas entre o Supply Chain Management e o Sales no mapeamento de **SalesUnitSymbol** para **DefaultUnit (Name)**.</span><span class="sxs-lookup"><span data-stu-id="28f12-153">Make sure that the required value map for the selling unit of measure (UOM) between Supply Chain Management and Sales exists in the mapping of **SalesUnitSymbol** to **DefaultUnit (Name)**.</span></span>
- <span data-ttu-id="28f12-154">Atualize o mapa de valores para **Grupo de unidades** (**defaultuomscheduleid.name**) para que corresponda a **Grupos de unidades** no Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-154">Update the value map for **Unit group** (**defaultuomscheduleid.name**) so that it matches **Unit groups** in Sales.</span></span>

    <span data-ttu-id="28f12-155">O valor do modelo padrão é **Unidade padrão**.</span><span class="sxs-lookup"><span data-stu-id="28f12-155">The default template value is **Default unit**.</span></span>

- <span data-ttu-id="28f12-156">Verifique se as UDMs de venda para todos os produtos do Supply Chain Management existem no Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-156">Make sure that the selling UOMs for all products from Supply Chain Management exist in Sales.</span></span>
- <span data-ttu-id="28f12-157">Verifique se existem listas de preços no Sales para cada moeda de venda de produto no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="28f12-157">Make sure that price lists exist in Sales for every product sales currency in Supply Chain Management.</span></span>
- <span data-ttu-id="28f12-158">Quando os produtos são criados no Sales, eles podem ter um status **Rascunho** ou **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="28f12-158">When products are created in Sales, they can have a status of **Draft** or **Active**.</span></span> <span data-ttu-id="28f12-159">O comportamento é controlado em **Configurações** > **Administração** > **Configurações do sistema** > **Vendas** no Sales.</span><span class="sxs-lookup"><span data-stu-id="28f12-159">The behavior is controlled at **Settings** > **Administration** > **System settings** > **Sales** in Sales.</span></span>

    <span data-ttu-id="28f12-160">Produtos com o status **Rascunho** quando são criados devem ser ativados antes de serem adicionados às cotações ou ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="28f12-160">Products that have **Draft** status when they are created must be activated before they can be added to quotations or sales orders.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="28f12-161">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="28f12-161">Template mapping in Data integration</span></span>

<span data-ttu-id="28f12-162">A ilustração a seguir mostra um exemplo de um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="28f12-162">The following illustration shows an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="28f12-163">O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="28f12-163">The mapping shows which field information will be synchronized from Sales to Supply Chain Management.</span></span>

![Mapeamento de modelo no Integrador de dados](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a><span data-ttu-id="28f12-165">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="28f12-165">Related topics</span></span>

[<span data-ttu-id="28f12-166">Cliente potencial ao pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="28f12-166">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="28f12-167">Sincronizar contas diretamente do Sales com clientes no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="28f12-167">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="28f12-168">Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="28f12-168">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="28f12-169">Sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="28f12-169">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="28f12-170">Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management com o Sales</span><span class="sxs-lookup"><span data-stu-id="28f12-170">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)



