---
title: Sincronizar contas do Sales com clientes do Finance and Operations
description: "O tópico discute os modelos e as tarefas subjacentes usadas para sincronizar contas do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise."
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
ms.openlocfilehash: b497f078d9786a5c7630e924da6bb04cad37f5e9
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-accounts-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="32eee-103">Sincronizar contas do Sales com clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="32eee-103">Synchronize accounts from Sales to customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="32eee-104">Antes de usar a solução Prospect to cash, familiarize-se com a [Integração de dados do Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="32eee-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="32eee-105">O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar contas do Microsoft Dynamics 365 for Sales (Vendas) com o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="32eee-105">The topic discusses the templates and underlying tasks that are used to synchronize accounts from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="template-and-task"></a><span data-ttu-id="32eee-106">Modelo e tarefa</span><span class="sxs-lookup"><span data-stu-id="32eee-106">Template and task</span></span>

<span data-ttu-id="32eee-107">Os modelos e as tarefas subjacentes a seguir são usados para sincronizar contas do Sales com o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="32eee-107">The following templates and underlying tasks are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="32eee-108">**Nome do modelo:** contas (Sales com Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="32eee-108">**Name of the template:** Accounts (Sales to Fin and Ops)</span></span>
- <span data-ttu-id="32eee-109">**Nome da tarefa no projeto:** Contas - Conta - Clientes</span><span class="sxs-lookup"><span data-stu-id="32eee-109">**Name of the task in the project:** Accounts - Account - Customers</span></span>

<span data-ttu-id="32eee-110">Tarefas de sincronização necessárias antes da sincronização de conta/cliente: nenhuma</span><span class="sxs-lookup"><span data-stu-id="32eee-110">Sync tasks required prior to Account / Customer sync: None</span></span>

## <a name="entity-set"></a><span data-ttu-id="32eee-111">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="32eee-111">Entity set</span></span>

| <span data-ttu-id="32eee-112">Vendas</span><span class="sxs-lookup"><span data-stu-id="32eee-112">Sales</span></span>    | <span data-ttu-id="32eee-113">CDS</span><span class="sxs-lookup"><span data-stu-id="32eee-113">CDS</span></span>     | <span data-ttu-id="32eee-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="32eee-114">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="32eee-115">Contas</span><span class="sxs-lookup"><span data-stu-id="32eee-115">Accounts</span></span> | <span data-ttu-id="32eee-116">Conta</span><span class="sxs-lookup"><span data-stu-id="32eee-116">Account</span></span> | <span data-ttu-id="32eee-117">Clientes</span><span class="sxs-lookup"><span data-stu-id="32eee-117">Customers</span></span>              |

## <a name="entity-flow"></a><span data-ttu-id="32eee-118">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="32eee-118">Entity flow</span></span>

<span data-ttu-id="32eee-119">As contas são gerenciadas no Sales e sincronizados com o Finance and Operations como clientes.</span><span class="sxs-lookup"><span data-stu-id="32eee-119">Accounts are managed in Sales and synchronized to Finance and Operations as Customers.</span></span> <span data-ttu-id="32eee-120">A propriedade **É Mantido Externamente** nesses clientes é definida como **Sim** para rastrear clientes originários de Sales.</span><span class="sxs-lookup"><span data-stu-id="32eee-120">The **Is Externally Maintained** property on these Customers is set to **Yes** to track Customers that originate from Sales.</span></span> <span data-ttu-id="32eee-121">Durante o faturamento, essas informações são usadas para filtrar faturas sincronizadas com o Sales.</span><span class="sxs-lookup"><span data-stu-id="32eee-121">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="32eee-122">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="32eee-122">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="32eee-123">O campo **Número da Conta** está disponível na página **Conta**.</span><span class="sxs-lookup"><span data-stu-id="32eee-123">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="32eee-124">Criou-se uma chave natural e exclusiva para oferecer suporte à integração.</span><span class="sxs-lookup"><span data-stu-id="32eee-124">It has been made a natural and unique key to support the integration.</span></span> <span data-ttu-id="32eee-125">O recurso de chave natural da solução Gerenciamento de Relacionamento com o Cliente (CRM) pode afetar clientes que já usam o campo **Número da Conta**, mas que não utilizam os valores exclusivos **Número da Conta** por conta.</span><span class="sxs-lookup"><span data-stu-id="32eee-125">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="32eee-126">Atualmente, a solução de integração não é compatível nesse caso.</span><span class="sxs-lookup"><span data-stu-id="32eee-126">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="32eee-127">Quando uma nova conta é criada, se um valor **Número da Conta** ainda não existe, ele é automaticamente gerado com uma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="32eee-127">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="32eee-128">O valor consiste em **ACC** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="32eee-128">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="32eee-129">Veja um exemplo: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="32eee-129">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="32eee-130">Quando a solução de integração para o Sales é aplicada, um script de atualização define o campo **Número da Conta** para as contas existentes no Sales.</span><span class="sxs-lookup"><span data-stu-id="32eee-130">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="32eee-131">Se não houver valores **Número da Conta**, a sequência numérica descrita antes será usada.</span><span class="sxs-lookup"><span data-stu-id="32eee-131">If there are no **Account Number** values, the number sequence that was described earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="32eee-132">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="32eee-132">Preconditions and mapping setup</span></span>

- <span data-ttu-id="32eee-133">**CustomerGroupId** deve ser atualizado para um valor válido no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="32eee-133">**CustomerGroupId** must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="32eee-134">É possível especificar um valor padrão ou definir o valor usando um mapa de valores.</span><span class="sxs-lookup"><span data-stu-id="32eee-134">You can specify a default value, or you can set the value by using a value map.</span></span> <span data-ttu-id="32eee-135">O valor do modelo padrão é **10**.</span><span class="sxs-lookup"><span data-stu-id="32eee-135">The default template value is **10**.</span></span>
- <span data-ttu-id="32eee-136">O **código de região do país do Endereço** é necessário no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="32eee-136">**Address country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="32eee-137">Para evitar erros de sincronização, você poderá especificar um valor padrão.</span><span class="sxs-lookup"><span data-stu-id="32eee-137">To avoid synchronization errors, you can specify a default value.</span></span> <span data-ttu-id="32eee-138">O valor padrão é usado se o campo for deixado em branco no Sales.</span><span class="sxs-lookup"><span data-stu-id="32eee-138">That default value is then used if the field is left blank in Sales.</span></span>

    - <span data-ttu-id="32eee-139">O valor do modelo padrão para **AddressCountryRegionISOCode** é **USA**.</span><span class="sxs-lookup"><span data-stu-id="32eee-139">The default template value for **AddressCountryRegionISOCode** is **USA**.</span></span>
    - <span data-ttu-id="32eee-140">O valor do modelo padrão para **DeliveryAddressCountryRegionISOCode** é **USA**.</span><span class="sxs-lookup"><span data-stu-id="32eee-140">The default template value for **DeliveryAddressCountryRegionISOCode** is **USA**.</span></span>

- <span data-ttu-id="32eee-141">Ao adicionar os mapeamentos a seguir de **CDS &gt; Destino**, você poderá ajudar a reduzir o número de atualizações manuais necessário no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="32eee-141">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="32eee-142">Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.</span><span class="sxs-lookup"><span data-stu-id="32eee-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="32eee-143">**SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="32eee-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="32eee-144">Um site padrão pode ser obtido do produto ou cliente no cabeçalho da ordem.</span><span class="sxs-lookup"><span data-stu-id="32eee-144">A default site can be taken either from the product, or from the customer from the order header.</span></span> <span data-ttu-id="32eee-145">O valor do modelo padrão para **SiteId** é **1**.</span><span class="sxs-lookup"><span data-stu-id="32eee-145">The default template value for **SiteId** is **1**.</span></span>
    - <span data-ttu-id="32eee-146">**WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="32eee-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="32eee-147">Um depósito padrão pode ser obtido do produto ou cliente no cabeçalho da ordem do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="32eee-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span> <span data-ttu-id="32eee-148">O valor do modelo padrão para **WarehouseId** é **13**.</span><span class="sxs-lookup"><span data-stu-id="32eee-148">The default template value for **WarehouseId** is **13**.</span></span>
    - <span data-ttu-id="32eee-149">**LanguageId** – Um idioma é necessário para gerar cotações e ordens de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="32eee-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="32eee-150">Por padrão, o idioma no cabeçalho da ordem do cliente é usado.</span><span class="sxs-lookup"><span data-stu-id="32eee-150">By default, the language from the order header from the customer is used.</span></span> <span data-ttu-id="32eee-151">O valor do modelo padrão para **LanguageId** é **en-us**.</span><span class="sxs-lookup"><span data-stu-id="32eee-151">The default template value for **LanguageId** is **en-us**.</span></span>

- <span data-ttu-id="32eee-152">Atualize a ID da organização do CDS (**Organization_OrganizationId**) no mapeamento **Fonte &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="32eee-152">Update the CDS organization ID (**Organization_OrganizationId**) in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="32eee-153">O valor do modelo padrão é **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="32eee-153">The default template value is **ORG001**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="32eee-154">Mapeamento de modelos no integrador de dados</span><span class="sxs-lookup"><span data-stu-id="32eee-154">Template mapping in data integrator</span></span>

> [!NOTE]
> <span data-ttu-id="32eee-155">Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não estão incluídos no mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="32eee-155">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="32eee-156">Para mapear esses campos, é preciso configurar uma mapeamento de valores.</span><span class="sxs-lookup"><span data-stu-id="32eee-156">To map these fields, you must set up a value mapping.</span></span> <span data-ttu-id="32eee-157">Os mapeamentos de valores são específicos para os dados nas organizações entre as quais a entidade está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="32eee-157">Value mappings are specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="32eee-158">As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="32eee-158">The following illustrations show an example of a template mapping in data integrator.</span></span>

![Mapeamento de modelos no integrador de dados](./media/accounts-template-mapping-data-integrator-1.png)

![Mapeamento de modelos para contas no integrador de dados](./media/accounts-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="32eee-161">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="32eee-161">Related topics</span></span>

[<span data-ttu-id="32eee-162">Sincronizar produtos do Finance and Operations com produtos do Sales</span><span class="sxs-lookup"><span data-stu-id="32eee-162">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="32eee-163">Sincronizar contatos do Sales com contatos ou clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="32eee-163">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping.md)

[<span data-ttu-id="32eee-164">Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="32eee-164">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)




