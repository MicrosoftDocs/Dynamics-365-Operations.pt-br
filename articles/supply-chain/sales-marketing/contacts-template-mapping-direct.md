---
title: Sincronizar contatos diretamente do Sales com contatos ou clientes do Finance and Operations
description: "Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar Contato (Contatos) e Contato (Clientes) de entidades do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition"
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 6e0c95618377685b9c27cf693f5553cf515ce6b1
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---

# <a name="synchronize-contacts-directly-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="afc99-103">Sincronizar contatos diretamente do Sales com contatos ou clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="afc99-103">Synchronize contacts directly from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="afc99-104">Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados do Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="afc99-104">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

<span data-ttu-id="afc99-105">Este tópico discute os modelos e as tarefas subjacentes usadas para sincronizar Contato (Contatos) e Contato (Clientes) de entidades diretamente do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="afc99-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) and Contact (Customers) entities directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="afc99-106">Fluxo de dados no Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="afc99-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="afc99-107">A solução Prospect to cash usa o recurso de integração de dados sincronizar dados nas instâncias do Finance and Operations e do Sales.</span><span class="sxs-lookup"><span data-stu-id="afc99-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="afc99-108">Os modelos Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados sobre contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="afc99-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data about accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="afc99-109">A ilustração a seguir mostra como os dados são sincronizados entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="afc99-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="afc99-110">[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="afc99-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="afc99-111">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="afc99-111">Templates and tasks</span></span>

<span data-ttu-id="afc99-112">Para acessar os modelos disponíveis, abra o [Centro de administração de PowerApps](https://preview.admin.powerapps.com/dataintegration).</span><span class="sxs-lookup"><span data-stu-id="afc99-112">To access the available templates, open [PowerApps Admin Center](https://preview.admin.powerapps.com/dataintegration).</span></span> <span data-ttu-id="afc99-113">Selecione **Projetos** e, no canto superior direito, selecione **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="afc99-113">Select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="afc99-114">Os modelos e as tarefas subjacentes a seguir são usados para sincronizar entidades de Contato (Contatos) no Sales com entidades de Contato (Clientes) no Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="afc99-114">The following templates and underlying tasks are used to synchronize Contact (Contacts) entities in Sales to Contact (Customers) entities in Finance and Operations:</span></span>

- <span data-ttu-id="afc99-115">**Nomes dos modelos na Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="afc99-115">**Names of the templates in Data integration:**</span></span>

    - <span data-ttu-id="afc99-116">Contatos (Sales com o Fin and Ops) – Direto</span><span class="sxs-lookup"><span data-stu-id="afc99-116">Contacts (Sales to Fin and Ops) - Direct</span></span>
    - <span data-ttu-id="afc99-117">Contatos para Cliente (Sales com o Fin and Ops) – Direto</span><span class="sxs-lookup"><span data-stu-id="afc99-117">Contacts to Customer (Sales to Fin and Ops) - Direct</span></span>

- <span data-ttu-id="afc99-118">**Nomes das tarefas no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="afc99-118">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="afc99-119">Contatos</span><span class="sxs-lookup"><span data-stu-id="afc99-119">Contacts</span></span>
    - <span data-ttu-id="afc99-120">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="afc99-120">ContactToCustomer</span></span>

<span data-ttu-id="afc99-121">A tarefa de sincronização a seguir é necessária para que a sincronização de contatos possa ocorrer: Contas (Sales com o Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="afc99-121">The following synchronization task is required before contact synchronization can occur: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="afc99-122">Conjuntos de entidades</span><span class="sxs-lookup"><span data-stu-id="afc99-122">Entity sets</span></span>

| <span data-ttu-id="afc99-123">Vendas</span><span class="sxs-lookup"><span data-stu-id="afc99-123">Sales</span></span>    | <span data-ttu-id="afc99-124">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="afc99-124">Finance and Operations</span></span> |
|----------|------------------------|
| <span data-ttu-id="afc99-125">Contatos</span><span class="sxs-lookup"><span data-stu-id="afc99-125">Contacts</span></span> | <span data-ttu-id="afc99-126">Contatos do CDS</span><span class="sxs-lookup"><span data-stu-id="afc99-126">CDS Contacts</span></span>           |
| <span data-ttu-id="afc99-127">Contatos</span><span class="sxs-lookup"><span data-stu-id="afc99-127">Contacts</span></span> | <span data-ttu-id="afc99-128">Clientes V2</span><span class="sxs-lookup"><span data-stu-id="afc99-128">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="afc99-129">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="afc99-129">Entity flow</span></span>

<span data-ttu-id="afc99-130">Os contatos são gerenciados no Sales e sincronizados com o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="afc99-130">Contacts are managed in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="afc99-131">Um contato no Sales pode se tornar um contato ou um cliente no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="afc99-131">A contact in Sales can become either a contact or a customer in Finance and Operations.</span></span> <span data-ttu-id="afc99-132">Para determinar se um contato no Sales deve ser sincronizado com o Finance and Operations como um contato ou um cliente, o sistema analisa as seguintes propriedades no contato no Sales:</span><span class="sxs-lookup"><span data-stu-id="afc99-132">To determine whether a contact in Sales should be synchronized to Finance and Operations as a contact or a customer, the system looks at the following properties on the contact in Sales:</span></span>

- <span data-ttu-id="afc99-133">**Sincronização com um cliente no Finance and Operations:** Contatos em que **É Cliente Ativo** está definido como **Sim**</span><span class="sxs-lookup"><span data-stu-id="afc99-133">**Synchronization to a customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="afc99-134">**Sincronização com um contato no Finance and Operations:** Contatos em que **É Cliente Ativo** está definido como **Não** e **Empresa** (conta/contato primário) apontam para uma conta (e não um contato)</span><span class="sxs-lookup"><span data-stu-id="afc99-134">**Synchronization to a contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (parent account/contact) points to an account (not a contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="afc99-135">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="afc99-135">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="afc99-136">Um novo campo **É Cliente Ativo** foi adicionado ao contato.</span><span class="sxs-lookup"><span data-stu-id="afc99-136">A new **Is Active Customer** field has been added to the contact.</span></span> <span data-ttu-id="afc99-137">Esse campo é usado para diferenciar os contatos com atividade de venda dos contatos que não têm atividade de venda.</span><span class="sxs-lookup"><span data-stu-id="afc99-137">This field is used to differentiate contacts that have sales activity and contacts that don't have sales activity.</span></span> <span data-ttu-id="afc99-138">**É Cliente Ativo** só será definido como **Sim** para os contatos com cotações, ordens ou faturas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="afc99-138">**Is Active Customer** is set to **Yes** only for contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="afc99-139">Somente esses contatos serão sincronizados com o Finance and Operations como clientes.</span><span class="sxs-lookup"><span data-stu-id="afc99-139">Only those contacts are synchronized to Finance and Operations as customers.</span></span>

<span data-ttu-id="afc99-140">Um novo campo **IsCompanyAnAccount** foi adicionado ao contato.</span><span class="sxs-lookup"><span data-stu-id="afc99-140">A new **IsCompanyAnAccount** field has been added to the contact.</span></span> <span data-ttu-id="afc99-141">Esse campo indica se um contato está vinculado a uma empresa (conta/contato primário) do tipo **Conta**.</span><span class="sxs-lookup"><span data-stu-id="afc99-141">This field indicates whether a contact is linked to a company (parent account/contact) of the **Account** type.</span></span> <span data-ttu-id="afc99-142">Essa informação é usada para identificar os contatos que devem ser sincronizados com o Finance and Operations como contatos.</span><span class="sxs-lookup"><span data-stu-id="afc99-142">This information is used to identify contacts that should be synchronized to Finance and Operations as contacts.</span></span>

<span data-ttu-id="afc99-143">Um novo campo **Número de Contato** foi adicionado ao contato para ajudar a garantir uma chave natural e exclusiva para a integração.</span><span class="sxs-lookup"><span data-stu-id="afc99-143">A new **Contact Number** field has been added to the contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="afc99-144">Quando um novo contato é criado, um valor **Número de Contato** é automaticamente gerado usando uma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="afc99-144">When a new contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="afc99-145">O valor consiste em **CON** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="afc99-145">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="afc99-146">Veja um exemplo: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="afc99-146">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="afc99-147">Quando a solução de integração para o Sales é aplicada, um script de atualização define o campo **Número de Contato** para os contatos existentes usando a sequência numérica mencionada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="afc99-147">When the integration solution for Sales is applied, an upgrade script sets the **Contact Number** field for existing contacts by using the number sequence that was mentioned earlier.</span></span> <span data-ttu-id="afc99-148">O script de atualização também define o campo **É Cliente Ativo** como **Sim** para todos os contatos com atividade de venda.</span><span class="sxs-lookup"><span data-stu-id="afc99-148">The upgrade script also sets the **Is Active Customer** field to **Yes** for any contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="afc99-149">No Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="afc99-149">In Finance and Operations</span></span>

<span data-ttu-id="afc99-150">Os Contatos são marcados com a propriedade **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="afc99-150">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="afc99-151">Essa propriedade indica que um determinado contato é mantido externamente.</span><span class="sxs-lookup"><span data-stu-id="afc99-151">This property indicates that a given contact is maintained externally.</span></span> <span data-ttu-id="afc99-152">Nesse caso, os contatos mantidos externamente são mantidos no Sales.</span><span class="sxs-lookup"><span data-stu-id="afc99-152">In this case, externally maintained contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="afc99-153">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="afc99-153">Preconditions and mapping setup</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="afc99-154">Contato para cliente</span><span class="sxs-lookup"><span data-stu-id="afc99-154">Contact to customer</span></span>

- <span data-ttu-id="afc99-155">**CustomerGroup** é necessário no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="afc99-155">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="afc99-156">Para ajudar a evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento.</span><span class="sxs-lookup"><span data-stu-id="afc99-156">To help prevent synchronization errors, you can specify a default value in the mapping.</span></span> <span data-ttu-id="afc99-157">O valor padrão é usado se o campo for deixado em branco no Sales.</span><span class="sxs-lookup"><span data-stu-id="afc99-157">That default value is then used if the field is left blank in Sales.</span></span>

    <span data-ttu-id="afc99-158">O valor do modelo padrão é **10**.</span><span class="sxs-lookup"><span data-stu-id="afc99-158">The default template value is **10**.</span></span>

- <span data-ttu-id="afc99-159">Ao adicionar os mapeamentos a seguir, você poderá ajudar a reduzir o número de atualizações manuais necessárias no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="afc99-159">By adding the following mappings, you can help reduce the number of manual updates that are required in Finance and Operations.</span></span> <span data-ttu-id="afc99-160">Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.</span><span class="sxs-lookup"><span data-stu-id="afc99-160">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="afc99-161">**SiteId** – um site padrão também pode ser definido em produtos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="afc99-161">**SiteId** – A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="afc99-162">Um site é necessário para gerar cotações e ordens de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="afc99-162">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="afc99-163">Não há um valor do modelo definido para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="afc99-163">A template value for **SiteId** isn't defined.</span></span>

    - <span data-ttu-id="afc99-164">**WarehouseId** – um depósito padrão também pode ser definido em produtos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="afc99-164">**WarehouseId** – A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="afc99-165">Um depósito é necessário para gerar cotações e ordens de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="afc99-165">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span>

        <span data-ttu-id="afc99-166">Não há um valor do modelo definido para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="afc99-166">A template value for **WarehouseId** isn't defined.</span></span>

    - <span data-ttu-id="afc99-167">**LanguageId** – Um idioma é necessário para gerar cotações e ordens de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="afc99-167">**LanguageId** – A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span>
    
        <span data-ttu-id="afc99-168">O valor padrão do modelo é **en-us**.</span><span class="sxs-lookup"><span data-stu-id="afc99-168">The default template value for is **en-us**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="afc99-169">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="afc99-169">Template mapping in Data integration</span></span>

<span data-ttu-id="afc99-170">As ilustrações a seguir mostram um exemplo de um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="afc99-170">The following illustrations show an example of a template mapping in Data integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="afc99-171">O mapeamento mostra quais informações de campo serão sincronizadas do Sales com o Finance and Operations..</span><span class="sxs-lookup"><span data-stu-id="afc99-171">The mapping shows which field information will be synchronized from Sales to Finance and Operations.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="afc99-172">Contato para contato</span><span class="sxs-lookup"><span data-stu-id="afc99-172">Contact to contact</span></span>

![Mapeamento de modelo no Integrador de dados](./media/contacts-direct-template-mapping-data-integrator-1.png)

### <a name="contact-to-customer"></a><span data-ttu-id="afc99-174">Contato para cliente</span><span class="sxs-lookup"><span data-stu-id="afc99-174">Contact to customer</span></span>

![Mapeamento de modelo no Integrador de dados](./media/contacts-direct-template-mapping-data-integrator-2.png)


## <a name="related-topics"></a><span data-ttu-id="afc99-176">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="afc99-176">Related topics</span></span>

[<span data-ttu-id="afc99-177">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="afc99-177">Prospect to cash</span></span>](prospect-to-cash.md)

[<span data-ttu-id="afc99-178">Sincronizar contas diretamente do Sales com clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="afc99-178">Synchronize accounts directly from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping-direct.md)

[<span data-ttu-id="afc99-179">Sincronizar produtos diretamente do Finance and Operations com produtos no Sales</span><span class="sxs-lookup"><span data-stu-id="afc99-179">Synchronize products directly from Finance and Operations to products in Sales</span></span>](products-template-mapping-direct.md)

[<span data-ttu-id="afc99-180">Sincronizar cabeçalhos e linhas de ordem de venda diretamente do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="afc99-180">Synchronize sales order headers and lines directly from Finance and Operations to Sales</span></span>](sales-order-template-mapping-direct.md)

[<span data-ttu-id="afc99-181">Sincronizar cabeçalhos e linhas de fatura diretamente do Finance and Operations com o Sales</span><span class="sxs-lookup"><span data-stu-id="afc99-181">Synchronize sales invoice headers and lines directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)



