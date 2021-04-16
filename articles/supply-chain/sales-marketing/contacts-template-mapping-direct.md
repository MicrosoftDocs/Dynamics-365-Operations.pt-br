---
title: Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management
description: Este tópico aborda os modelos e as tarefas subjacentes usados para sincronizar entidades de Contato (Contatos) e Contato (Clientes) entre o Dynamics 365 Sales e o Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 81cf79c866ad70bf5bf2a9475a235bf3135d6e50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840788"
---
# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-supply-chain-management"></a><span data-ttu-id="2fbfb-103">Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2fbfb-103">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="2fbfb-104">Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Microsoft Dataverse para Aplicativos](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="2fbfb-104">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Microsoft Dataverse for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

<span data-ttu-id="2fbfb-105">Este tópico aborda os modelos e as tarefas subjacentes usados para sincronizar entidades de Contato (Contatos) e Contato (Clientes) diretamente do Dynamics 365 Sales para o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) tables directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="2fbfb-106">Fluxo de dados no Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="2fbfb-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="2fbfb-107">A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="2fbfb-108">Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="2fbfb-109">A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="2fbfb-110">[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="2fbfb-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="2fbfb-111">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="2fbfb-111">Templates and tasks</span></span>

<span data-ttu-id="2fbfb-112">Para acessar os modelos disponíveis, abra o [Centro de administração do PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="2fbfb-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="2fbfb-113">Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="2fbfb-114">Os modelos e as tarefas subjacentes a seguir são usados para sincronizar tabelas de Contato (Contatos) no Sales com tabelas de Contato (Clientes) no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) tables in Sales to Contact (Customers) tables in Supply Chain Management.</span></span>

- <span data-ttu-id="2fbfb-115">**Nomes dos modelos na Integração de dados**</span><span class="sxs-lookup"><span data-stu-id="2fbfb-115">**Names of the templates in Data integration**</span></span>

    - <span data-ttu-id="2fbfb-116">Contatos (Sales para Supply Chain Management) - Direto</span><span class="sxs-lookup"><span data-stu-id="2fbfb-116">Contacts (Sales to Supply Chain Management) - Direct</span></span>
    - <span data-ttu-id="2fbfb-117">Contatos para Cliente (Sales para Supply Chain Management) - Direto</span><span class="sxs-lookup"><span data-stu-id="2fbfb-117">Contacts to Customer (Sales to Supply Chain Management) - Direct</span></span>

- <span data-ttu-id="2fbfb-118">**Nomes das tarefas no projeto de Integração de dados**</span><span class="sxs-lookup"><span data-stu-id="2fbfb-118">**Names of the tasks in the Data integration project**</span></span>

    - <span data-ttu-id="2fbfb-119">Contatos</span><span class="sxs-lookup"><span data-stu-id="2fbfb-119">Contacts</span></span>
    - <span data-ttu-id="2fbfb-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="2fbfb-120">ContactToCustomer</span></span>

<span data-ttu-id="2fbfb-121">A tarefa de sincronização a seguir é necessária para que a sincronização de contatos possa ocorrer: Contas (Sales para Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="2fbfb-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Supply Chain Management)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="2fbfb-122">Conjuntos de entidades</span><span class="sxs-lookup"><span data-stu-id="2fbfb-122">Entity sets</span></span>

| <span data-ttu-id="2fbfb-123">Vendas</span><span class="sxs-lookup"><span data-stu-id="2fbfb-123">Sales</span></span>    | <span data-ttu-id="2fbfb-124">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="2fbfb-124">Supply Chain Management</span></span> |
|----------|------------------------|
| <span data-ttu-id="2fbfb-125">Contatos</span><span class="sxs-lookup"><span data-stu-id="2fbfb-125">Contacts</span></span> | <span data-ttu-id="2fbfb-126">Contatos do Dataverse</span><span class="sxs-lookup"><span data-stu-id="2fbfb-126">Dataverse Contacts</span></span>           |
| <span data-ttu-id="2fbfb-127">Contatos</span><span class="sxs-lookup"><span data-stu-id="2fbfb-127">Contacts</span></span> | <span data-ttu-id="2fbfb-128">Clientes V2</span><span class="sxs-lookup"><span data-stu-id="2fbfb-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="2fbfb-129">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="2fbfb-129">Entity flow</span></span>

<span data-ttu-id="2fbfb-130">Os contatos são gerenciados no Sales e sincronizados para o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-130">Contacts are managed in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="2fbfb-131">Um contato no Sales pode se tornar um contato ou um cliente no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-131">A contact in Sales can become either a contact or a customer in Supply Chain Management.</span></span> <span data-ttu-id="2fbfb-132">Para determinar se um contato no Sales deve ser sincronizado com o Supply Chain Management como um contato ou um cliente, o sistema analisa as seguintes propriedades no contato no Sales:</span><span class="sxs-lookup"><span data-stu-id="2fbfb-132">To determine whether a contact in Sales should be synchronized to Supply Chain Management as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="2fbfb-133">**Sincronização com um cliente no Supply Chain Management:** Contatos em que **É Cliente Ativo** está definido como **Sim**</span><span class="sxs-lookup"><span data-stu-id="2fbfb-133">**Synchronization to a customer in Supply Chain Management:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="2fbfb-134">**Sincronização com um contato no Supply Chain Management:** Contatos em que **É Cliente Ativo** está definido como **Não** e **Empresa** (conta/contato primário) aponta para uma conta (e não um contato)</span><span class="sxs-lookup"><span data-stu-id="2fbfb-134">**Synchronization to a contact in Supply Chain Management:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="2fbfb-135">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="2fbfb-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="2fbfb-136">Uma nova coluna **É Cliente Ativo** foi adicionada ao contato.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-136">A new **Is Active Customer** column has been added to the contact.</span></span> <span data-ttu-id="2fbfb-137">Essa coluna é usada para diferenciar os contatos com atividade de venda dos contatos que não têm atividade de venda.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-137">This column is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="2fbfb-138">**É Cliente Ativo** só será definido como **Sim** para os contatos com cotações, ordens ou faturas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="2fbfb-139">Somente esses contatos são sincronizados com o Supply Chain Management como clientes.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-139">Only those contacts are synchronized to Supply Chain Management as customers.</span></span>

<span data-ttu-id="2fbfb-140">Uma nova coluna **IsCompanyAnAccount** foi adicionada ao contato.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-140">A new **IsCompanyAnAccount** column has been added to the contact.</span></span> <span data-ttu-id="2fbfb-141">Essa coluna indica se um contato está vinculado a uma empresa (conta/contato primário) do tipo **Conta**.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-141">This column indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="2fbfb-142">Essa informação é usada para identificar os contatos que devem ser sincronizados com o Supply Chain Management como contatos.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-142">This information is used to identify contacts that should be synchronized to Supply Chain Management as contacts.</span></span>

<span data-ttu-id="2fbfb-143">Uma nova coluna **Número de Contato** foi adicionada ao contato para ajudar a garantir uma chave natural e exclusiva para a integração.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-143">A new **Contact Number** column has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="2fbfb-144">Quando um novo contato é criado, um valor **Número de Contato** é automaticamente gerado usando uma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="2fbfb-145">O valor consiste em **CON** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="2fbfb-146">Veja um exemplo: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="2fbfb-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="2fbfb-147">Quando a solução de integração para o Sales é aplicada, um script de atualização define a coluna **Número de Contato** para os contatos existentes usando a sequência numérica mencionada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** column for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="2fbfb-148">O script de atualização também define a coluna **É Cliente Ativo** como **Sim** para todos os contatos com atividade de venda.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-148">The upgrade script also sets the **Is Active Customer** column to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-supply-chain-management"></a><span data-ttu-id="2fbfb-149">No Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2fbfb-149">In Supply Chain Management</span></span>

<span data-ttu-id="2fbfb-150">Os Contatos são marcados com a propriedade **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="2fbfb-151">Essa propriedade indica que um determinado contato é mantido externamente.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="2fbfb-152">Nesse caso, os contatos mantidos externamente são mantidos no Sales.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="2fbfb-153">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="2fbfb-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="2fbfb-154">Contato para cliente</span><span class="sxs-lookup"><span data-stu-id="2fbfb-154">Contact to customer</span></span>

- <span data-ttu-id="2fbfb-155">**CustomerGroup** é necessário no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-155">**CustomerGroup** is required in Supply Chain Management.</span></span> <span data-ttu-id="2fbfb-156">Para ajudar a evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="2fbfb-157">O valor padrão é usado se a coluna for deixado em branco no Sales.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-157">That default value is then used if the column is left blank in Sales.</span></span>

    <span data-ttu-id="2fbfb-158">O valor do modelo padrão é **10**.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-158">The default template value is **10**.</span></span>

- <span data-ttu-id="2fbfb-159">Ao adicionar os mapeamentos a seguir, você poderá ajudar a reduzir o número de atualizações manuais necessárias no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Supply Chain Management.</span></span> <span data-ttu-id="2fbfb-160">Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="2fbfb-161">**SiteId** – Um site padrão também pode ser definido em produtos no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-161">**SiteId** – A default site can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="2fbfb-162">Um site é necessário para gerar cotações e ordens de venda no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-162">A site is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="2fbfb-163">Não há um valor do modelo definido para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="2fbfb-164">**WarehouseId** – Um depósito padrão também pode ser definido em produtos no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-164">**WarehouseId** – A default warehouse can also be defined on products in Supply Chain Management.</span></span> <span data-ttu-id="2fbfb-165">Um depósito é necessário para gerar cotações e ordens de venda no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-165">A warehouse is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>

        <span data-ttu-id="2fbfb-166">Não há um valor do modelo definido para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="2fbfb-167">**LanguageId** – Um idioma é necessário pra gerar cotações e pedidos de venda no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Supply Chain Management.</span></span>
    
        <span data-ttu-id="2fbfb-168">O valor padrão do modelo é **en-us**.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="2fbfb-169">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="2fbfb-169">Template mapping in Data integration</span></span>

<span data-ttu-id="2fbfb-170">As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="2fbfb-171">O mapeamento mostra quais informações de coluna serão sincronizadas do Sales com o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2fbfb-171">The mapping shows which column information will be synchronized from Sales to Supply Chain Management.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="2fbfb-172">Contato para contato</span><span class="sxs-lookup"><span data-stu-id="2fbfb-172">Contact to contact</span></span>

![Mapeamento de modelo no Integrador de dados](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="2fbfb-174">Contato para cliente</span><span class="sxs-lookup"><span data-stu-id="2fbfb-174">Contact to customer</span></span>

![Mapeamento de modelo no Integrador de dados](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="2fbfb-176">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2fbfb-176">Related topics</span></span>

[<span data-ttu-id="2fbfb-177">Cliente potencial ao pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="2fbfb-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="2fbfb-178">Sincronizar contas diretamente do Sales com clientes no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2fbfb-178">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="2fbfb-179">Sincronizar produtos diretamente do Supply Chain Management com produtos do Sales</span><span class="sxs-lookup"><span data-stu-id="2fbfb-179">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="2fbfb-180">Sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2fbfb-180">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)

[<span data-ttu-id="2fbfb-181">Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management com o Sales</span><span class="sxs-lookup"><span data-stu-id="2fbfb-181">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]