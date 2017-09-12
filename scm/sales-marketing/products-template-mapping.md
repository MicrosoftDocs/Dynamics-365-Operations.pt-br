---
title: Sincronizar produtos do Finance and Operations com os produtos no Sales
description: "Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise para o Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2f14b06b57930256f9211f2085512aa589df083e
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a><span data-ttu-id="29d47-103">Sincronizar produtos do Finance and Operations com os produtos no Sales</span><span class="sxs-lookup"><span data-stu-id="29d47-103">Synchronize products from Finance and Operations to products in Sales</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="29d47-104">Antes de usar a solução Prospect to cash, familiarize-se com a [Integração de dados do Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="29d47-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="29d47-105">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise para o Microsoft Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="29d47-105">This topic discusses the templates and underlying tasks that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition to Microsoft Dynamics 365 for Sales.</span></span>

## <a name="template-and-task"></a><span data-ttu-id="29d47-106">Modelo e tarefa</span><span class="sxs-lookup"><span data-stu-id="29d47-106">Template and task</span></span>

<span data-ttu-id="29d47-107">Os modelos e as tarefas subjacentes a seguir são usados para sincronizar produtos do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (Finance and Operations) para o Microsoft Dynamics 365 for Sales (Sales).</span><span class="sxs-lookup"><span data-stu-id="29d47-107">The following templates and underlying tasks are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) to Microsoft Dynamics 365 for Sales (Sales).</span></span>

-   <span data-ttu-id="29d47-108">Nome do modelo: Produtos (Fin and Ops para Sales)</span><span class="sxs-lookup"><span data-stu-id="29d47-108">Name of template: Products (Fin and Ops to Sales)</span></span>

-   <span data-ttu-id="29d47-109">Nome de tarefa no projeto: Produtos</span><span class="sxs-lookup"><span data-stu-id="29d47-109">Name of task in project: Products</span></span>

<span data-ttu-id="29d47-110">Tarefas de sincronização necessárias antes da sincronização de Produtos: nenhuma</span><span class="sxs-lookup"><span data-stu-id="29d47-110">Sync tasks required prior to Product sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="29d47-111">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="29d47-111">Entity set</span></span>

| <span data-ttu-id="29d47-112">**Finance and Operations**</span><span class="sxs-lookup"><span data-stu-id="29d47-112">**Finance and Operations**</span></span> | <span data-ttu-id="29d47-113">**CDS**</span><span class="sxs-lookup"><span data-stu-id="29d47-113">**CDS**</span></span> | <span data-ttu-id="29d47-114">**Vendas**</span><span class="sxs-lookup"><span data-stu-id="29d47-114">**Sales**</span></span>  |
|----------------------------|---------|------------|
| <span data-ttu-id="29d47-115">Produtos liberados comercializáveis</span><span class="sxs-lookup"><span data-stu-id="29d47-115">Sellable released products</span></span> | <span data-ttu-id="29d47-116">Produto</span><span class="sxs-lookup"><span data-stu-id="29d47-116">Product</span></span> | <span data-ttu-id="29d47-117">Produtos</span><span class="sxs-lookup"><span data-stu-id="29d47-117">Products</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="29d47-118">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="29d47-118">Entity flow</span></span>

<span data-ttu-id="29d47-119">Os produtos são gerenciados no Finance and Operations e sincronizados para o Sales.</span><span class="sxs-lookup"><span data-stu-id="29d47-119">Products are managed in Finance and Operations and synchronized to Sales.</span></span> <span data-ttu-id="29d47-120">A entidade de dados **Produtos liberados comercializáveis** do Finance and Operations só exporta produtos comercializáveis, o que significa que os produtos têm as informações que devem ser usadas em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="29d47-120">The data entity **Sellable released products** in Finance and Operations only exports products that are sellable, which means that products have the information required to be used on a sales order.</span></span> <span data-ttu-id="29d47-121">As mesmas regras se aplicam quando um produto é validado com a função **Validar** na página **Produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="29d47-121">The same rules apply when a product is validated with the **Validate** function on the **Released product** page.</span></span>

<span data-ttu-id="29d47-122">O **Número de produto** é usado como chave, o que significa que as grades de produto são sincronizadas para o CDS e o Sales com **IDs de produto** individuais por **Grade de produto**.</span><span class="sxs-lookup"><span data-stu-id="29d47-122">The **Product number** is used as key, meaning that product variants are synchronized to CDS and Sales with individual **Product IDs** per **Product variant**.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="29d47-123">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="29d47-123">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="29d47-124">No Sales, um novo campo sobre os produtos, **É Mantido Externamente**, é adicionado para indicar que um determinado produto é mantido externamente.</span><span class="sxs-lookup"><span data-stu-id="29d47-124">In Sales, a new field on the products **Is Externally Maintained** is added to indicate that a given product is maintained externally.</span></span> <span data-ttu-id="29d47-125">O valor é definido como **Sim** por padrão durante a importação para o Sales.</span><span class="sxs-lookup"><span data-stu-id="29d47-125">The value is set to **Yes** by default during import to Sales.</span></span>

-   <span data-ttu-id="29d47-126">**É Mantido Externamente = Sim**: o produto tem origem no Finance and Operations e não será editável no Sales.</span><span class="sxs-lookup"><span data-stu-id="29d47-126">**Is Externally Maintained = Yes**: Product originates from Finance and Operations and will not be editable in Sales.</span></span>

-   <span data-ttu-id="29d47-127">**É Mantido Externamente = Não**: o produto é inserido diretamente no Sales.</span><span class="sxs-lookup"><span data-stu-id="29d47-127">**Is Externally Maintained = No**: Product is entered directly in Sales.</span></span>

-   <span data-ttu-id="29d47-128">**É Mantido Externamente = em branco**: o produto existia no Sales antes da habilitação da solução Prospect to cash.</span><span class="sxs-lookup"><span data-stu-id="29d47-128">**Is Externally Maintained = Blank**: Product exists in Sales prior to enabling the Prospect to cash solution.</span></span>

<span data-ttu-id="29d47-129">A informação de **É Mantido Externamente** é usada para garantir que somente **Cotações** e **Ordens de venda** com **Produtos mantidos externamente** sejam sincronizados para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="29d47-129">The **Is Externally Maintained** information is used to ensure that only **Quotes** and **Sales orders** with **Externally maintained products** will sync to Finance and Operations.</span></span>

<span data-ttu-id="29d47-130">Os **Produtos mantidos externamente** são adicionados de forma automática à primeira **Lista de preços** válida com a mesma moeda.</span><span class="sxs-lookup"><span data-stu-id="29d47-130">**Externally maintained products** are automatically added to the first valid **Price list** with the same currency.</span></span> <span data-ttu-id="29d47-131">Observe que a lista é organizada alfabeticamente por **Nome**.</span><span class="sxs-lookup"><span data-stu-id="29d47-131">Note that the list is organized alphabetically by **Name**.</span></span> <span data-ttu-id="29d47-132">O preço de venda do produto do Finance and Operations é usado como o preço na **Lista de preços**.</span><span class="sxs-lookup"><span data-stu-id="29d47-132">The product sales price from Finance and Operations is used as price on the **Price list**.</span></span> <span data-ttu-id="29d47-133">Isso significa que é necessário ter uma **Lista de preços** no Sales para cada **Moeda de vendas de produto** no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="29d47-133">This means that it is required to have a **Price list** in Sales for each **Product sales currency** in Finance and Operations.</span></span> <span data-ttu-id="29d47-134">A moeda dos produtos liberados comercializáveis é definida como a moeda contábil da entidade legal da qual o produto é exportado.</span><span class="sxs-lookup"><span data-stu-id="29d47-134">Currency on the released sellable products is set to the accounting currency in the legal entity, from which the product is exported.</span></span>

> [!NOTE]
> <span data-ttu-id="29d47-135">A sincronização de produtos não obterá êxito sem uma **Lista de preços** com a moeda correspondente.</span><span class="sxs-lookup"><span data-stu-id="29d47-135">Product sync will not succeed without a **Price list** with the matching currency.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="29d47-136">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="29d47-136">Preconditions and mapping setup</span></span>

-   <span data-ttu-id="29d47-137">Antes de executar a primeira sincronização, preencha a **Tabela de produtos distintos** para produtos existentes no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="29d47-137">Before you run the very first sync, you must populate the **Distinct product table** for existing products in Finance and Operations.</span></span> <span data-ttu-id="29d47-138">Os produtos existentes não serão sincronizados até que o trabalho seja concluído.</span><span class="sxs-lookup"><span data-stu-id="29d47-138">Existing products will not be synchronized until this job is completed.</span></span>

    -   <span data-ttu-id="29d47-139">No Finance and Operations, use Pesquisar para procurar **Preencher tabela de produtos distintos**.</span><span class="sxs-lookup"><span data-stu-id="29d47-139">In Finance and Operations, use Search to search for **Populate distinct product table**.</span></span>

    -   <span data-ttu-id="29d47-140">Clique na **Preencher tabela de produtos distintos** para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="29d47-140">Click the **Populate distinct product table** to run the job.</span></span> <span data-ttu-id="29d47-141">Este trabalho só precisa ser executado uma vez.</span><span class="sxs-lookup"><span data-stu-id="29d47-141">This job only needs to be run once.</span></span>

-   <span data-ttu-id="29d47-142">Verifique se o **ValueMap** necessário para a **Unidade de Medida** (UDM) de vendas do Finance and Operations existe em **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span><span class="sxs-lookup"><span data-stu-id="29d47-142">Ensure that the needed **ValueMap** for selling **Unit of measure** (UOM) in Finance and Operations exists in the **Source -\> CDS mapping SalesUnitSymbol / DefaultSellingUnitOfMeasure**.</span></span>

-   <span data-ttu-id="29d47-143">Verifique se **Oferece suporte a decimais** para o UDM corresponde aos seus requisitos em **CDS -\> Destination**.</span><span class="sxs-lookup"><span data-stu-id="29d47-143">Ensure that **Decimals supported** for UOM match your requirements in **CDS -\> Destination**.</span></span> <span data-ttu-id="29d47-144">Se você exigir valores diferentes por UDM, isso poderá ser feito com **ValueMap** da Unidade, por exemplo, [Each : 0] & [Pound : 2].</span><span class="sxs-lookup"><span data-stu-id="29d47-144">If you require different values per UOM, this can be done with **ValueMap** from Unit, for example, [Each : 0] & [Pound : 2].</span></span>

    -   <span data-ttu-id="29d47-145">O padrão do valor do modelo é 0.</span><span class="sxs-lookup"><span data-stu-id="29d47-145">Template value is defaulted to 0.</span></span>

-   <span data-ttu-id="29d47-146">Atualize **CDS Organization ID Organization_OrganizationId** em **Source -\> CDS**.</span><span class="sxs-lookup"><span data-stu-id="29d47-146">Update the **CDS Organization ID Organization_OrganizationId** in **Source -\> CDS**.</span></span>

    -   <span data-ttu-id="29d47-147">O padrão do valor do modelo é ORG001.</span><span class="sxs-lookup"><span data-stu-id="29d47-147">Template value is defaulted to ORG001.</span></span>

-   <span data-ttu-id="29d47-148">Atualize **ValueMap** para **Grupo de unidades** (**defaultuomscheduleid.name**) **CDS -\> Destination** para corresponder a **Grupos de unidades** no Sales.</span><span class="sxs-lookup"><span data-stu-id="29d47-148">Update **ValueMap** for **Unit group** (**defaultuomscheduleid.name**) in **CDS -\> Destination** to match the **Unit groups** in Sales.</span></span>

    -   <span data-ttu-id="29d47-149">O padrão do valor do modelo é **Unidade padrão**.</span><span class="sxs-lookup"><span data-stu-id="29d47-149">Template value is defaulted to **Default unit**.</span></span>

-   <span data-ttu-id="29d47-150">Verifique se todas as UDMs de venda de produtos do Finance and Operations existem no Sales com o valor **Listas de separação do CDS**.</span><span class="sxs-lookup"><span data-stu-id="29d47-150">Ensure that all products selling UOMs from Finance and Operations exist in Sales with the **CDS picklists** value.</span></span>

-   <span data-ttu-id="29d47-151">Verifique se existem **Tabelas de preços** no Sales para cada moeda de venda de produto no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="29d47-151">Ensure that **Price lists** exist in Sales for each product sales currency in Finance and Operations.</span></span>

-   <span data-ttu-id="29d47-152">Os produtos podem ser no Sales com o status **Rascunho** ou **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="29d47-152">Products can be created in Sales with status **Draft** or **Active**.</span></span> <span data-ttu-id="29d47-153">Isso é controlado em **Configurações do sistema** em **Vendas** no Sales.</span><span class="sxs-lookup"><span data-stu-id="29d47-153">This is controlled in **System settings** under **Sales** in Sales.</span></span>

    -   <span data-ttu-id="29d47-154">Os produtos criados com o status de rascunho precisam ser ativados antes que possam ser adicionados a **Cotação** ou **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="29d47-154">Products created with draft status need to be activated before they can be added to **Quote** or **Sales order**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="29d47-155">Mapeamento de modelos no integrador de dados</span><span class="sxs-lookup"><span data-stu-id="29d47-155">Template mapping in data integrator</span></span>

<span data-ttu-id="29d47-156">As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="29d47-156">The following illustrations show an example of a template mapping in data integrator.</span></span>

![mapeamento de modelos no integrador de dados](./media/products-template-mapping-data-integrator-1.png)

![mapeamento de modelos para produtos no integrador de dados](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="29d47-159">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="29d47-159">Related topics</span></span>

[<span data-ttu-id="29d47-160">Sincronizar contas do Sales para clientes no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="29d47-160">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="29d47-161">Sincronizar contatos do Sales com contatos ou clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="29d47-161">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="29d47-162">Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="29d47-162">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)


