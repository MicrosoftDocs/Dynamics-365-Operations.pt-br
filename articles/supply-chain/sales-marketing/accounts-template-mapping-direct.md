---
title: Sincronizar contas diretamente do Sales com clientes do Finance and Operations
description: "Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar contas do Microsoft Dynamics 365 for Sales para o Microsoft Dynamics 365 for Finance and Operations."
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: a0cabdab63d4d44010e52303d6f487db1e910059
ms.contentlocale: pt-br
ms.lasthandoff: 11/01/2018

---

# <a name="synchronize-accounts-directly-from-sales-to-customers-in-finance-and-operations"></a><span data-ttu-id="cf759-103">Sincronizar contas diretamente do Sales com clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cf759-103">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="cf759-104">Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Common Data Service para Aplicativos](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="cf759-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="cf759-105">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar contas diretamente do Microsoft Dynamics 365 for Sales para o Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cf759-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="cf759-106">Fluxo de dados no Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="cf759-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="cf759-107">A solução Prospect to cash usa o recurso de integração de dados sincronizar dados nas instâncias do Finance and Operations e do Sales.</span><span class="sxs-lookup"><span data-stu-id="cf759-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span>  <span data-ttu-id="cf759-108">Os modelos Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="cf759-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="cf759-109">A ilustração a seguir mostra como os dados são sincronizados entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="cf759-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="cf759-110">[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="cf759-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="cf759-111">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="cf759-111">Templates and tasks</span></span>

<span data-ttu-id="cf759-112">Para acessar os modelos disponíveis, abra o [Centro de administração de PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="cf759-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="cf759-113">Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="cf759-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="cf759-114">O modelo e a tarefa subjacente a seguir são usados para sincronizar contas do Sales com o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="cf759-114">The following template and underlying task are used to synchronize accounts from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="cf759-115">**Nome do modelo na Integração de dados:** Contas (Sales para Fin and Ops) – Direto</span><span class="sxs-lookup"><span data-stu-id="cf759-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="cf759-116">**Nome da tarefa no projeto:** Contas – Clientes</span><span class="sxs-lookup"><span data-stu-id="cf759-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="cf759-117">Nenhuma tarefa de sincronização é necessária para que a sincronização de conta/cliente ocorra.</span><span class="sxs-lookup"><span data-stu-id="cf759-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="cf759-118">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="cf759-118">Entity set</span></span>

| <span data-ttu-id="cf759-119">Vendas</span><span class="sxs-lookup"><span data-stu-id="cf759-119">Sales</span></span>    | <span data-ttu-id="cf759-120">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cf759-120">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="cf759-121">Contas</span><span class="sxs-lookup"><span data-stu-id="cf759-121">Accounts</span></span> | <span data-ttu-id="cf759-122">Clientes V2</span><span class="sxs-lookup"><span data-stu-id="cf759-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="cf759-123">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="cf759-123">Entity flow</span></span>

<span data-ttu-id="cf759-124">As contas são gerenciadas no Sales e sincronizadas com o Finance and Operations como clientes.</span><span class="sxs-lookup"><span data-stu-id="cf759-124">Accounts are managed in Sales and synchronized to Finance and Operations as customers.</span></span> <span data-ttu-id="cf759-125">A propriedade **É Mantido Externamente** nesses clientes é definida como **Sim** para rastrear clientes originários do Sales.</span><span class="sxs-lookup"><span data-stu-id="cf759-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="cf759-126">Durante o faturamento, essas informações são usadas para filtrar faturas sincronizadas com o Sales.</span><span class="sxs-lookup"><span data-stu-id="cf759-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="cf759-127">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="cf759-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="cf759-128">O campo **Número da Conta** está disponível na página **Conta**.</span><span class="sxs-lookup"><span data-stu-id="cf759-128">The **Account Number** field is available on the **Account** page.</span></span> <span data-ttu-id="cf759-129">Criou-se uma chave natural e exclusiva para oferecer suporte à integração.</span><span class="sxs-lookup"><span data-stu-id="cf759-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="cf759-130">O recurso de chave natural da solução Gerenciamento de Relacionamento com o Cliente (CRM) pode afetar clientes que já usam o campo **Número da Conta**, mas que não utilizam os valores exclusivos **Número da Conta** por conta.</span><span class="sxs-lookup"><span data-stu-id="cf759-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** field, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="cf759-131">Atualmente, a solução de integração não é compatível nesse caso.</span><span class="sxs-lookup"><span data-stu-id="cf759-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="cf759-132">Quando uma nova conta é criada, se um valor **Número da Conta** ainda não existe, ele é automaticamente gerado com uma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="cf759-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="cf759-133">O valor consiste em **ACC** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="cf759-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="cf759-134">Veja um exemplo: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="cf759-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="cf759-135">Quando a solução de integração para o Sales é aplicada, um script de atualização define o campo **Número da Conta** para as contas existentes no Sales.</span><span class="sxs-lookup"><span data-stu-id="cf759-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** field for existing accounts in Sales.</span></span> <span data-ttu-id="cf759-136">Se não houver valores de **Número da Conta**, a sequência numérica mencionada anteriormente será usada.</span><span class="sxs-lookup"><span data-stu-id="cf759-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="cf759-137">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="cf759-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="cf759-138">O mapeamento **CustomerGroupId** deve ser atualizado para um valor válido no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cf759-138">The **CustomerGroupId** mapping must be updated to a valid value in Finance and Operations.</span></span> <span data-ttu-id="cf759-139">É possível especificar um valor padrão ou definir o valor usando um mapa de valores.</span><span class="sxs-lookup"><span data-stu-id="cf759-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="cf759-140">O valor do modelo padrão é **10**.</span><span class="sxs-lookup"><span data-stu-id="cf759-140">The default template value is **10**.</span></span>

- <span data-ttu-id="cf759-141">Ao adicionar os mapeamentos a seguir, você poderá ajudar a reduzir o número de atualizações manuais necessárias no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cf759-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="cf759-142">Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.</span><span class="sxs-lookup"><span data-stu-id="cf759-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="cf759-143">**SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cf759-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="cf759-144">Um site padrão pode ser obtido do produto ou cliente no cabeçalho da ordem.</span><span class="sxs-lookup"><span data-stu-id="cf759-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="cf759-145">O valor do modelo padrão é **1**.</span><span class="sxs-lookup"><span data-stu-id="cf759-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="cf759-146">**WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cf759-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="cf759-147">Um depósito padrão pode ser obtido do produto ou cliente no cabeçalho da ordem do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cf759-147">A default warehouse can be taken either from the product, or from the customer from the order header in Finance and Operations.</span></span>

        <span data-ttu-id="cf759-148">O valor do modelo padrão é **13**.</span><span class="sxs-lookup"><span data-stu-id="cf759-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="cf759-149">**LanguageId** – Um idioma é necessário para gerar cotações e ordens de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="cf759-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="cf759-150">Por padrão, o idioma no cabeçalho da ordem do cliente é usado.</span><span class="sxs-lookup"><span data-stu-id="cf759-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="cf759-151">O valor padrão do modelo é **en-us**.</span><span class="sxs-lookup"><span data-stu-id="cf759-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="cf759-152">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="cf759-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="cf759-153">Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não estão incluídos no mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="cf759-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't included in the default mappings.</span></span> <span data-ttu-id="cf759-154">Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="cf759-154">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="cf759-155">As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="cf759-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="cf759-156">O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Finance and Operations..</span><span class="sxs-lookup"><span data-stu-id="cf759-156">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

![Mapeamento de modelo na Integração de dados](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="cf759-158">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cf759-158">Related topics</span></span>


[<span data-ttu-id="cf759-159">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="cf759-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="cf759-160">Sincronizar contas diretamente do Sales com clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cf759-160">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="cf759-161">Sincronizar contatos diretamente do Sales com contatos ou clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="cf759-161">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="cf759-162">Sincronizar cabeçalhos e linhas de ordem de venda diretamente do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="cf759-162">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="cf759-163">Sincronizar cabeçalhos e linhas de fatura diretamente do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="cf759-163">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)


