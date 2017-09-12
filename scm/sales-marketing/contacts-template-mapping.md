---
title: Sincronizar contatos do Sales para contatos ou clientes no Finance and Operations
description: "Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar Contato (Contatos) e Contato (Clientes) do Microsoft Dynamics 365 for Sales para o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise."
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
ms.openlocfilehash: 7a856a9460d092925a34a0733f37f89354c2ddf1
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-contacts-from-sales-to-contacts-or-customers-in-finance-and-operations"></a><span data-ttu-id="abd50-103">Sincronizar contatos do Sales para contatos ou clientes no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="abd50-103">Synchronize contacts from Sales to contacts or customers in Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="abd50-104">Antes de usar a solução Prospect to cash, familiarize-se com a [Integração de dados do Dynamics 365](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="abd50-104">Before you can use the Prospect to cash solution, be familiar with [Dynamics 365 Data Integration](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration).</span></span> 

<span data-ttu-id="abd50-105">Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar entidades Contato (Contatos) e Contato (Clientes) do Microsoft Dynamics 365 for Sales (Sales) para o Microsoft Dynamics 365 for Finance and Operations, edição Enterprise (Finance and Operations).</span><span class="sxs-lookup"><span data-stu-id="abd50-105">This topic discusses the templates and underlying tasks that are used to synchronize Contact (Contacts) entities and Contact (Customers) from Microsoft Dynamics 365 for Sales (Sales) to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations).</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="abd50-106">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="abd50-106">Templates and tasks</span></span>

<span data-ttu-id="abd50-107">Os modelos e as tarefas subjacentes a seguir são usados para sincronizar Contato (Contatos) no Sales para Contato (Clientes) no Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="abd50-107">The following templates and underlying tasks are used to synchronize Contact (Contacts) in Sales to Contact (Customers) in Finance and Operations:</span></span>

- <span data-ttu-id="abd50-108">**Nomes dos modelos.**</span><span class="sxs-lookup"><span data-stu-id="abd50-108">**Names of the templates:**</span></span>

    - <span data-ttu-id="abd50-109">Contatos para Contato (Sales para o Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="abd50-109">Contacts to Contact (Sales to Fin and Ops)</span></span>
    - <span data-ttu-id="abd50-110">Contatos para Cliente (Sales para o Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="abd50-110">Contacts to Customer (Sales to Fin and Ops)</span></span>

- <span data-ttu-id="abd50-111">**Nomes das tarefas no projeto:**</span><span class="sxs-lookup"><span data-stu-id="abd50-111">**Names of the tasks in the project:**</span></span>

    - <span data-ttu-id="abd50-112">Contatos</span><span class="sxs-lookup"><span data-stu-id="abd50-112">Contacts</span></span>
    - <span data-ttu-id="abd50-113">ContactToCustomer</span><span class="sxs-lookup"><span data-stu-id="abd50-113">ContactToCustomer</span></span>

<span data-ttu-id="abd50-114">A tarefa de sincronização a seguir será necessária antes da sincronização de Contato: Contas (Sales para o Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="abd50-114">The following synchronization task is required before Contact synchronization: Accounts (Sales to Fin and Ops)</span></span>

## <a name="entity-sets"></a><span data-ttu-id="abd50-115">Conjuntos de entidades</span><span class="sxs-lookup"><span data-stu-id="abd50-115">Entity sets</span></span>

| <span data-ttu-id="abd50-116">Vendas</span><span class="sxs-lookup"><span data-stu-id="abd50-116">Sales</span></span>    | <span data-ttu-id="abd50-117">CDS</span><span class="sxs-lookup"><span data-stu-id="abd50-117">CDS</span></span>     | <span data-ttu-id="abd50-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="abd50-118">Finance and Operations</span></span> |
|----------|---------|------------------------|
| <span data-ttu-id="abd50-119">Contatos</span><span class="sxs-lookup"><span data-stu-id="abd50-119">Contacts</span></span> | <span data-ttu-id="abd50-120">Contato</span><span class="sxs-lookup"><span data-stu-id="abd50-120">Contact</span></span> | <span data-ttu-id="abd50-121">Contatos do CDS</span><span class="sxs-lookup"><span data-stu-id="abd50-121">CDS Contacts</span></span>           |
| <span data-ttu-id="abd50-122">Contatos</span><span class="sxs-lookup"><span data-stu-id="abd50-122">Contacts</span></span> | <span data-ttu-id="abd50-123">Conta</span><span class="sxs-lookup"><span data-stu-id="abd50-123">Account</span></span> | <span data-ttu-id="abd50-124">Clientes V2</span><span class="sxs-lookup"><span data-stu-id="abd50-124">Customers V2</span></span>           |

## <a name="entity-flow"></a><span data-ttu-id="abd50-125">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="abd50-125">Entity flow</span></span>

<span data-ttu-id="abd50-126">Os Contatos são gerenciados no Sales e são sincronizados para o CDS (Common Data Service) e o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-126">Contacts are managed in Sales, and are synchronized to Common Data Service (CDS) and Finance and Operations.</span></span>

<span data-ttu-id="abd50-127">Um Contato no Sales pode se tornar um Contato no CDs e no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-127">A Contact in Sales can become a Contact in CDS and Finance and Operations.</span></span> <span data-ttu-id="abd50-128">Como alternativa, ele poderá se tornar uma Conta no CDS e um Cliente no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-128">Alternatively, it can become an Account in CDS and a Customer in Finance and Operations.</span></span> <span data-ttu-id="abd50-129">Para determinar se um contato deve ser separado no Sales para sincronização para o CDS e o Finance and Operations (por exemplo, Contatos no Sales &gt; Contato no CDS &gt; Contatos no Finance e Operations), o sistema examina as seguintes propriedades no Contato no Sales:</span><span class="sxs-lookup"><span data-stu-id="abd50-129">To determine whether a contact should be picked up in Sales for synchronization to CDS and Finance and Operations (for example, Contacts in Sales &gt; Contact in CDS &gt; Contacts in Finance and Operations), the system looks at the following properties on Contact in Sales:</span></span>

- <span data-ttu-id="abd50-130">**Sincronizar para Conta no CDS e Cliente no Finance and Operations:** Contatos onde **É Cliente Ativo** está definido como **Sim**</span><span class="sxs-lookup"><span data-stu-id="abd50-130">**Sync to Account in CDS and Customer in Finance and Operations:** Contacts where **Is Active Customer** is set to **Yes**</span></span>
- <span data-ttu-id="abd50-131">**Sincronizar para Contato no CDS e Contato no Finance and Operations:** Contatos onde **É Cliente Ativo** está definido com **Não** e **Empresa** (Conta/Contato Principal) apontam para uma Conta (e não um Contato)</span><span class="sxs-lookup"><span data-stu-id="abd50-131">**Sync to Contact in CDS and Contact in Finance and Operations:** Contacts where **Is Active Customer** is set to **No** and **Company** (Parent Account/Contact) points to an Account (not a Contact)</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="abd50-132">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="abd50-132">Prospect to cash solution for Sales</span></span> 

<span data-ttu-id="abd50-133">Um novo campo **É Cliente Ativo** foi adicionado ao Contato.</span><span class="sxs-lookup"><span data-stu-id="abd50-133">A new **Is Active Customer** field has been added to the Contact.</span></span> <span data-ttu-id="abd50-134">Esse campo é usado para diferenciar os Contatos com atividade de venda dos Contatos que não têm atividade de venda.</span><span class="sxs-lookup"><span data-stu-id="abd50-134">This field is used to differentiate Contacts that have sales activity and Contacts that don't have sales activity.</span></span> <span data-ttu-id="abd50-135">**É Cliente Ativo** só será definido como **Sim** para os Contatos com cotações, ordens ou faturas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="abd50-135">**Is Active Customer** is set to **Yes** only for Contacts that have related quotations, orders, or invoices.</span></span> <span data-ttu-id="abd50-136">Somente esses Contatos serão sincronizados para o Finance and Operations como Clientes.</span><span class="sxs-lookup"><span data-stu-id="abd50-136">Only those Contacts are synchronized to Finance and Operations as Customers.</span></span>

<span data-ttu-id="abd50-137">Um novo campo **IsCompanyAnAccount** foi adicionado ao Contato.</span><span class="sxs-lookup"><span data-stu-id="abd50-137">A new **IsCompanyAnAccount** field has been added to the Contact.</span></span> <span data-ttu-id="abd50-138">Esse campo é usado para indicar se um Contato está vinculado a uma Empresa (Conta/Contato Principal) do tipo **Conta**.</span><span class="sxs-lookup"><span data-stu-id="abd50-138">This field is used to indicate whether a Contact is linked to a Company (Parent Account/Contact) of the **Account** type.</span></span> <span data-ttu-id="abd50-139">Essa informação é usada para identificar os Contatos que devem ser sincronizados para o Finance and Operations como Contatos.</span><span class="sxs-lookup"><span data-stu-id="abd50-139">This information is used to identify Contacts that should be synchronized to Finance and Operations as Contacts.</span></span>

<span data-ttu-id="abd50-140">Um novo campo **Número de Contato** foi adicionado ao Contato para ajudar a garantir uma chave natural e exclusiva para a integração.</span><span class="sxs-lookup"><span data-stu-id="abd50-140">A new **Contact Number** field has been added to the Contact to help guarantee a natural and unique key for the integration.</span></span> <span data-ttu-id="abd50-141">Quando um novo Contato é criado, um valor **Número de Contato** é automaticamente gerado usando uma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="abd50-141">When a new Contact is created, a **Contact Number** value is automatically generated by using a number sequence.</span></span> <span data-ttu-id="abd50-142">O valor consiste em **CON** seguido por uma sequência numérica crescente e então um sufixo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="abd50-142">The value consists of **CON**, followed by an increasing number sequence and then a suffix of six characters.</span></span> <span data-ttu-id="abd50-143">Veja um exemplo: **CON-01000-BVRCPS**</span><span class="sxs-lookup"><span data-stu-id="abd50-143">Here is an example: **CON-01000-BVRCPS**</span></span>

<span data-ttu-id="abd50-144">Quando a solução de integração para o Sales é adicionada ao Sales, um script de atualização define o campo **Número de Contato** para os Contatos existentes usando a sequência numérica discutida anteriormente.</span><span class="sxs-lookup"><span data-stu-id="abd50-144">When the integration solution for Sales is added to Sales, an upgrade script sets the **Contact Number** field for existing Contacts by using the number sequence that was discussed earlier.</span></span> <span data-ttu-id="abd50-145">O script de atualização também define o campo **É Cliente Ativo** como **Sim** para todos os Contatos com atividade de venda.</span><span class="sxs-lookup"><span data-stu-id="abd50-145">The upgrade script also sets the **Is Active Customer** field to **Yes** for any Contacts that have sales activity.</span></span>

## <a name="in-finance-and-operations"></a><span data-ttu-id="abd50-146">No Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="abd50-146">In Finance and Operations</span></span> 

<span data-ttu-id="abd50-147">Os Contatos são marcados com a propriedade **IsContactPersonExternallyMaintained**.</span><span class="sxs-lookup"><span data-stu-id="abd50-147">Contacts are tagged by using the **IsContactPersonExternallyMaintained** property.</span></span> <span data-ttu-id="abd50-148">Essa propriedade indica que um determinado Contato é mantido externamente.</span><span class="sxs-lookup"><span data-stu-id="abd50-148">This property indicates that a given Contact is maintained externally.</span></span> <span data-ttu-id="abd50-149">Neste caso, os Contatos mantidos externamente são mantidos no Sales.</span><span class="sxs-lookup"><span data-stu-id="abd50-149">In this case, externally maintained Contacts are maintained in Sales.</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="abd50-150">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="abd50-150">Preconditions and mapping setup</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="abd50-151">Contato para Contato</span><span class="sxs-lookup"><span data-stu-id="abd50-151">Contact to Contact</span></span>

- <span data-ttu-id="abd50-152">Atualize **CDS Organization ID** no mapeamento **Source &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="abd50-152">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span>

    - <span data-ttu-id="abd50-153">O valor do modelo padrão para **Organization_OrganizationId [Organization ID]** é **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="abd50-153">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
    - <span data-ttu-id="abd50-154">O valor do modelo padrão para **PrimaryAccount_Organization_OrganizationId [Organization ID]** é **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="abd50-154">The default template value for **PrimaryAccount_Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>

- <span data-ttu-id="abd50-155">O **código de região País do Endereço** é necessário no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-155">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="abd50-156">Para evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento **CDS &gt; Operations**.</span><span class="sxs-lookup"><span data-stu-id="abd50-156">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Operations** mapping.</span></span> <span data-ttu-id="abd50-157">O valor padrão é usado se o campo for deixado em branco no Sales.</span><span class="sxs-lookup"><span data-stu-id="abd50-157">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="abd50-158">O valor do modelo padrão para **PrimaryAddressCountryRegionISOCode** é **USA**.</span><span class="sxs-lookup"><span data-stu-id="abd50-158">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="abd50-159">Verifique se existe um valor para o campo a seguir no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-159">Make sure that a value for the following field exists in Finance and Operations.</span></span> <span data-ttu-id="abd50-160">Se as informações não forem necessárias no Finance and Operations, você poderá remover o mapeamento do mapeamento **CDS &gt; Destination**.</span><span class="sxs-lookup"><span data-stu-id="abd50-160">If the information isn't required in Finance and Operations, you can remove the mapping from the **CDS &gt; Destination** mapping.</span></span>

    - <span data-ttu-id="abd50-161">**Nome de campo no Finance and Operations:** Decisão</span><span class="sxs-lookup"><span data-stu-id="abd50-161">**Field name in Finance and Operations:** Decision</span></span>
    - <span data-ttu-id="abd50-162">**Mapeamento:** PrimaryAccountRole = DecisionMakingRole</span><span class="sxs-lookup"><span data-stu-id="abd50-162">**Mapping:** PrimaryAccountRole = DecisionMakingRole</span></span>

### <a name="contact-to-customer"></a><span data-ttu-id="abd50-163">Contato para Cliente</span><span class="sxs-lookup"><span data-stu-id="abd50-163">Contact to Customer</span></span>

- <span data-ttu-id="abd50-164">Atualize **CDS Organization ID** no mapeamento **Source &gt; CDS**.</span><span class="sxs-lookup"><span data-stu-id="abd50-164">Update **CDS Organization ID** in the **Source &gt; CDS** mapping.</span></span> <span data-ttu-id="abd50-165">O valor do modelo padrão para **Organization_OrganizationId [Organization ID]** é **ORG001**.</span><span class="sxs-lookup"><span data-stu-id="abd50-165">The default template value for **Organization_OrganizationId [Organization ID]** is **ORG001**.</span></span>
- <span data-ttu-id="abd50-166">O **código de região País do Endereço** é necessário no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-166">**Address Country region code** is required in Finance and Operations.</span></span> <span data-ttu-id="abd50-167">Para evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento **CDS &gt; Destination**.</span><span class="sxs-lookup"><span data-stu-id="abd50-167">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="abd50-168">O valor padrão é usado se o campo for deixado em branco no Sales.</span><span class="sxs-lookup"><span data-stu-id="abd50-168">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="abd50-169">O valor do modelo padrão para **PrimaryAddressCountryRegionISOCode** é **USA**.</span><span class="sxs-lookup"><span data-stu-id="abd50-169">The default template value for **PrimaryAddressCountryRegionISOCode** is **USA**.</span></span>
- <span data-ttu-id="abd50-170">**CustomerGroup** é necessário no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-170">**CustomerGroup** is required in Finance and Operations.</span></span> <span data-ttu-id="abd50-171">Para evitar erros de sincronização, você poderá especificar um valor padrão no mapeamento **CDS &gt; Destination**.</span><span class="sxs-lookup"><span data-stu-id="abd50-171">To avoid synchronization errors, you can specify a default value in the **CDS &gt; Destination** mapping.</span></span> <span data-ttu-id="abd50-172">O valor padrão é usado se o campo for deixado em branco no Sales.</span><span class="sxs-lookup"><span data-stu-id="abd50-172">That default value is then used if the field is left blank in Sales.</span></span> <span data-ttu-id="abd50-173">O valor do modelo padrão para **CustomerGroupId** é **10**.</span><span class="sxs-lookup"><span data-stu-id="abd50-173">The default template value for **CustomerGroupId** is **10**.</span></span>
- <span data-ttu-id="abd50-174">Ao adicionar os mapeamentos a seguir de **CDS &gt; Destination**, você poderá ajudar a reduzir o número de atualizações manuais existentes no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-174">By adding the following mappings from **CDS &gt; Destination**, you can help reduce the number of manual updates that are in Finance and Operations.</span></span> <span data-ttu-id="abd50-175">Você pode usar um valor padrão ou um mapa de valores de, por exemplo, **País/Região** ou **Cidade**.</span><span class="sxs-lookup"><span data-stu-id="abd50-175">You can use a default value or a value map from, for example, **Country/Region** or **City**.</span></span>

    - <span data-ttu-id="abd50-176">**SiteId** - um site padrão também pode ser definido em produtos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-176">**SiteId** - A default site can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="abd50-177">Um site é necessário para gerar cotações e ordens de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-177">A site is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="abd50-178">Não há um valor do modelo definido para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="abd50-178">A template value for **SiteId** isn't defined.</span></span>
    - <span data-ttu-id="abd50-179">**WarehouseId** - um depósito padrão também pode ser definido em produtos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-179">**WarehouseId** - A default warehouse can also be defined on products in Finance and Operations.</span></span> <span data-ttu-id="abd50-180">Um depósito é necessário para gerar cotações e ordens de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-180">A warehouse is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="abd50-181">Não há um valor do modelo definido para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="abd50-181">A template value for **WarehouseId** isn't defined.</span></span>
    - <span data-ttu-id="abd50-182">**LanguageId** - um idioma é necessário para gerar cotações e ordens de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="abd50-182">**LanguageId** - A language is required in order to generate quotations and sales orders in Finance and Operations.</span></span> <span data-ttu-id="abd50-183">O valor do modelo padrão para **LanguageId** é **en-us**.</span><span class="sxs-lookup"><span data-stu-id="abd50-183">The default template value for **LanguageId** is **en-us**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="abd50-184">Mapeamento de modelos no integrador de dados</span><span class="sxs-lookup"><span data-stu-id="abd50-184">Template mapping in data integrator</span></span>

<span data-ttu-id="abd50-185">As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="abd50-185">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="contact-to-contact"></a><span data-ttu-id="abd50-186">Contato para Contato</span><span class="sxs-lookup"><span data-stu-id="abd50-186">Contact to Contact</span></span>

![Mapeamento de modelos no integrador de dados](./media/contacts-template-mapping-data-integrator-1.png)

![Mapeamento de modelos para Contatos no integrador de dados](./media/contacts-template-mapping-data-integrator-2.png)

### <a name="contact-to-customer"></a><span data-ttu-id="abd50-189">Contato para Cliente</span><span class="sxs-lookup"><span data-stu-id="abd50-189">Contact to Customer</span></span>

![Mapeamento de modelos no integrador de dados](./media/contacts-template-mapping-data-integrator-3.png)

![Mapeamento de modelos para Contatos no integrador de dados](./media/contacts-template-mapping-data-integrator-4.png)


## <a name="related-topics"></a><span data-ttu-id="abd50-192">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="abd50-192">Related topics</span></span>

[<span data-ttu-id="abd50-193">Sincronizar produtos do Finance and Operations com produtos do Sales</span><span class="sxs-lookup"><span data-stu-id="abd50-193">Synchronize products from Finance and Operations to products in Sales</span></span>](products-template-mapping.md)

[<span data-ttu-id="abd50-194">Sincronizar contas do Sales para clientes no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="abd50-194">Synchronize accounts from Sales to customers in Finance and Operations</span></span>](accounts-template-mapping.md)

[<span data-ttu-id="abd50-195">Sincronizar cabeçalhos e linhas de cotação de venda do Sales com o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="abd50-195">Synchronize sales quotation headers and lines from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping.md)

