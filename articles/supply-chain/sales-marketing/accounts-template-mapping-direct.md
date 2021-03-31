---
title: Sincronizar contas diretamente do Sales com clientes no Supply Chain Management
description: Este tópico aborda os modelos e as tarefas subjacentes usados para sincronizar contas do Dynamics 365 Sales com o Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: adde8975c709b8037a05e8edf6da8574c7b3cc55
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215808"
---
# <a name="synchronize-accounts-directly-from-sales-to-customers-in-supply-chain-management"></a><span data-ttu-id="b6a6b-103">Sincronizar contas diretamente do Sales com clientes no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="b6a6b-103">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="b6a6b-104">Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Microsoft Dataverse para Aplicativos](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="b6a6b-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="b6a6b-105">Este tópico aborda os modelos e as tarefas subjacentes usados para sincronizar contas diretamente do Dynamics 365 Sales com o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-105">This topic discusses the templates and underlying tasks that are used to synchronize accounts directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="b6a6b-106">Fluxo de dados no Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="b6a6b-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="b6a6b-107">A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span>  <span data-ttu-id="b6a6b-108">Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="b6a6b-109">A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="b6a6b-110">[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="b6a6b-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="b6a6b-111">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="b6a6b-111">Templates and tasks</span></span>

<span data-ttu-id="b6a6b-112">Para acessar os modelos disponíveis, abra o [Centro de administração do Power Apps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="b6a6b-112">To access the available templates, open [Power Apps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="b6a6b-113">Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="b6a6b-114">O modelo e as tarefas subjacentes a seguir são usados para sincronizar contas do Sales com o Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="b6a6b-114">The following template and underlying task are used to synchronize accounts from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="b6a6b-115">**Nome do modelo na Integração de dados:** Contas (Sales para Fin and Ops) – Direto</span><span class="sxs-lookup"><span data-stu-id="b6a6b-115">**Name of the template in Data integration:** Accounts (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="b6a6b-116">**Nome da tarefa no projeto:** Contas – Clientes</span><span class="sxs-lookup"><span data-stu-id="b6a6b-116">**Name of the task in the project:** Accounts - Customers</span></span>

<span data-ttu-id="b6a6b-117">Nenhuma tarefa de sincronização é necessária para que a sincronização de conta/cliente ocorra.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-117">No synchronization tasks are required before Account/Customer synchronization can occur.</span></span>

## <a name="entity-set"></a><span data-ttu-id="b6a6b-118">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="b6a6b-118">Entity set</span></span>

| <span data-ttu-id="b6a6b-119">Vendas</span><span class="sxs-lookup"><span data-stu-id="b6a6b-119">Sales</span></span>    | <span data-ttu-id="b6a6b-120">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="b6a6b-120">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="b6a6b-121">Contas</span><span class="sxs-lookup"><span data-stu-id="b6a6b-121">Accounts</span></span> | <span data-ttu-id="b6a6b-122">Clientes V2</span><span class="sxs-lookup"><span data-stu-id="b6a6b-122">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="b6a6b-123">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="b6a6b-123">Entity flow</span></span>

<span data-ttu-id="b6a6b-124">As contas são gerenciadas no Sales e sincronizadas com o Supply Chain Management como clientes.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-124">Accounts are managed in Sales and synchronized to Supply Chain Management as customers.</span></span> <span data-ttu-id="b6a6b-125">A propriedade **É Mantido Externamente** nesses clientes é definida como **Sim** para rastrear clientes originários do Sales.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-125">The **Is Externally Maintained** property on these customers is set to **Yes** to track customers that originate from Sales.</span></span> <span data-ttu-id="b6a6b-126">Durante o faturamento, essas informações são usadas para filtrar faturas sincronizadas com o Sales.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-126">During invoicing, this information is used to filter invoices that are synchronized to Sales.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="b6a6b-127">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="b6a6b-127">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="b6a6b-128">A coluna **Número da Conta** está disponível na página **Conta**.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-128">The **Account Number** column is available on the **Account** page.</span></span> <span data-ttu-id="b6a6b-129">Criou-se uma chave natural e exclusiva para oferecer suporte à integração.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-129">It has been made a natural and unique key in order to support the integration.</span></span> <span data-ttu-id="b6a6b-130">O recurso de chave natural da solução Gerenciamento de Relacionamento com o Cliente (CRM) pode afetar clientes que já usam a coluna **Número da conta**, mas que não utilizam os valores exclusivos **Número da conta** por conta.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-130">The natural key feature of the Customer Relationship Management (CRM) solution might affect customers who already use the **Account Number** column, but who don't use unique **Account Number** values per account.</span></span> <span data-ttu-id="b6a6b-131">Atualmente, a solução de integração não é compatível nesse caso.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-131">Currently, the integration solution doesn't support this case.</span></span>

<span data-ttu-id="b6a6b-132">Quando uma nova conta é criada, se um valor **Número da Conta** ainda não existe, ele é automaticamente gerado com uma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-132">When a new account is created, if an **Account Number** value doesn't already exist, it's automatically generated by using a number sequence.</span></span> <span data-ttu-id="b6a6b-133">O valor consiste em **ACC** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-133">The value consists of **ACC**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="b6a6b-134">Veja um exemplo: **ACC-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="b6a6b-134">Here is an example: **ACC-01000-BVRCPS**</span></span>

<span data-ttu-id="b6a6b-135">Quando a solução de integração para o Sales é aplicada, um script de atualização define a coluna **Número da Conta** para as contas existentes no Sales.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-135">When the integration solution for Sales is applied, an upgrade script sets the **Account Number** column for existing accounts in Sales.</span></span> <span data-ttu-id="b6a6b-136">Se não houver valores de **Número da Conta**, a sequência numérica mencionada anteriormente será usada.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-136">If there are no **Account Number** values, the number sequence that was mentioned earlier is used.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="b6a6b-137">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="b6a6b-137">Preconditions and mapping setup</span></span>

- <span data-ttu-id="b6a6b-138">O mapeamento de **CustomerGroupId** deve ser atualizado para um valor válido no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-138">The **CustomerGroupId** mapping must be updated to a valid value in Supply Chain Management.</span></span> <span data-ttu-id="b6a6b-139">É possível especificar um valor padrão ou definir o valor usando um mapa de valores.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-139">You can specify a default value, or you can set the value by using a value map.</span></span>

    <span data-ttu-id="b6a6b-140">O valor do modelo padrão é **10**.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-140">The default template value is **10**.</span></span>

- <span data-ttu-id="b6a6b-141">Ao adicionar os mapeamentos a seguir, você poderá ajudar a reduzir o número de atualizações manuais necessárias no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-141">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="b6a6b-142">Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-142">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="b6a6b-143">**SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-143">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="b6a6b-144">Um site padrão pode ser obtido do produto ou cliente no cabeçalho da ordem.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-144">A default site can be taken either from the product, or from the customer from the order header.</span></span>

        <span data-ttu-id="b6a6b-145">O valor do modelo padrão é **1**.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-145">The default template value is **1**.</span></span>

    - <span data-ttu-id="b6a6b-146">**WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-146">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="b6a6b-147">Um depósito padrão pode ser obtido do produto ou do cliente no cabeçalho da ordem do Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-147">A default warehouse can be taken either from the product, or from the customer from the order header in Supply Chain Management.</span></span>

        <span data-ttu-id="b6a6b-148">O valor do modelo padrão é **13**.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-148">The default template value is **13**.</span></span>

    - <span data-ttu-id="b6a6b-149">**LanguageId** – Um idioma é necessário pra gerar cotações e pedidos de venda no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-149">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span> <span data-ttu-id="b6a6b-150">Por padrão, o idioma no cabeçalho da ordem do cliente é usado.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-150">By default, the language from the order header from the customer is used.</span></span>

        <span data-ttu-id="b6a6b-151">O valor padrão do modelo é **en-us**.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-151">The default template value is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="b6a6b-152">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="b6a6b-152">Template mapping in Data integration</span></span>

> [!NOTE]
> <span data-ttu-id="b6a6b-153">As colunas **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de remessa** e **Modo de entrega** não estão incluídas no mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-153">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** columns aren't included in the default mappings.</span></span> <span data-ttu-id="b6a6b-154">Para mapear essas colunas, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a tabela está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-154">To map these columns, you must set up a value mapping that is specific to the data in the organizations that the table is synchronized between.</span></span>

<span data-ttu-id="b6a6b-155">As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-155">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="b6a6b-156">O mapeamento mostra quais informações de coluna serão sincronizadas do Sales com o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b6a6b-156">The mapping shows which column information will be synchronized from Sales to Supply Chain Management.</span></span>

![Mapeamento de modelo na Integração de dados](./media/accounts-direct-template-mapping-data-integrator-1.png)

## <a name="related-topics"></a><span data-ttu-id="b6a6b-158">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b6a6b-158">Related topics</span></span>


[<span data-ttu-id="b6a6b-159">Cliente potencial ao pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="b6a6b-159">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="b6a6b-160">Sincronizar contas diretamente do Sales com clientes no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="b6a6b-160">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="b6a6b-161">Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="b6a6b-161">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)

[<span data-ttu-id="b6a6b-162">Sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="b6a6b-162">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="b6a6b-163">Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management com o Sales</span><span class="sxs-lookup"><span data-stu-id="b6a6b-163">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]