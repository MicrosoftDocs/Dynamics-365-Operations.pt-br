---
title: Sincronizar cabeçalhos e linhas da cotação de venda diretamente do Sales para o Supply Chain Management
description: O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas da cotação de venda diretamente do Dynamics 365 Sales para o Dynamics 365 Supply Chain Management.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b6b4384e1b5f712c08de55195a738295a36b75e7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204461"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-supply-chain-management"></a><span data-ttu-id="5d1e9-103">Sincronizar cabeçalhos e linhas da cotação de venda diretamente do Sales para o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="5d1e9-103">Synchronize sales quotation headers and lines directly from Sales to Supply Chain Management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d1e9-104">O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas da cotação de venda diretamente do Dynamics 365 Sales para o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Dynamics 365 Sales to Dynamics 365 Supply Chain Management.</span></span>

> [!NOTE]
> <span data-ttu-id="5d1e9-105">Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Common Data Service para Aplicativos](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="5d1e9-105">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/powerapps/administrator/data-integrator).</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="5d1e9-106">Fluxo de dados no Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="5d1e9-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="5d1e9-107">A solução Prospect to cash usa o recurso Integração de dados para sincronizar dados entre as instâncias Supply Chain Management e do Sales.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Supply Chain Management and Sales.</span></span> <span data-ttu-id="5d1e9-108">Os modelos de Prospect to cash que estão disponíveis com o recurso Integração de dados permitem o fluxo de dados para contas, contatos, produtos, cotações de venda, ordens de venda e faturas de venda entre o Supply Chain Management e o Sales.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Supply Chain Management and Sales.</span></span> <span data-ttu-id="5d1e9-109">A ilustração a seguir mostra como os dados são sincronizados entre o Supply Chain Management e o Sales.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-109">The following illustration shows how the data is synchronized between Supply Chain Management and Sales.</span></span>

<span data-ttu-id="5d1e9-110">[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="5d1e9-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="5d1e9-111">Modelo e tarefas</span><span class="sxs-lookup"><span data-stu-id="5d1e9-111">Template and tasks</span></span>

<span data-ttu-id="5d1e9-112">O seguinte modelo e as tarefas subjacentes são usados para sincronizar cabeçalhos e linhas da cotação de venda diretamente do Sales para o Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="5d1e9-112">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Supply Chain Management:</span></span>

- <span data-ttu-id="5d1e9-113">**Nome do modelo na Integração de dados:** Cotações de Venda (Sales para Supply Chain Management) – Direto</span><span class="sxs-lookup"><span data-stu-id="5d1e9-113">**Name of the template in Data integration:** Sales Quotes (Sales to Supply Chain Management) - Direct</span></span>
- <span data-ttu-id="5d1e9-114">**Nomes das tarefas no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="5d1e9-114">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="5d1e9-115">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="5d1e9-115">QuoteHeader</span></span>
    - <span data-ttu-id="5d1e9-116">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="5d1e9-116">QuoteLine</span></span>

<span data-ttu-id="5d1e9-117">As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de cotação de venda possa ocorrer:</span><span class="sxs-lookup"><span data-stu-id="5d1e9-117">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="5d1e9-118">Produtos (Supply Chain Management para Sales) – Direto</span><span class="sxs-lookup"><span data-stu-id="5d1e9-118">Products (Supply Chain Management to Sales) - Direct</span></span>
- <span data-ttu-id="5d1e9-119">Contas (Sales para Supply Chain Management) – Direto (se usado)</span><span class="sxs-lookup"><span data-stu-id="5d1e9-119">Accounts (Sales to Supply Chain Management) - Direct (if used)</span></span>
- <span data-ttu-id="5d1e9-120">Contatos para Clientes (Sales para Supply Chain Management) – Direto (se usado)</span><span class="sxs-lookup"><span data-stu-id="5d1e9-120">Contacts to Customers (Sales to Supply Chain Management) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="5d1e9-121">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="5d1e9-121">Entity set</span></span>

| <span data-ttu-id="5d1e9-122">Vendas</span><span class="sxs-lookup"><span data-stu-id="5d1e9-122">Sales</span></span>        | <span data-ttu-id="5d1e9-123">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="5d1e9-123">Supply Chain Management</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="5d1e9-124">Cotações</span><span class="sxs-lookup"><span data-stu-id="5d1e9-124">Quotes</span></span>       | <span data-ttu-id="5d1e9-125">Cabeçalho de cotação de venda CDS</span><span class="sxs-lookup"><span data-stu-id="5d1e9-125">CDS sales quotation header</span></span> |
| <span data-ttu-id="5d1e9-126">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="5d1e9-126">QuoteDetails</span></span> | <span data-ttu-id="5d1e9-127">Linhas de cotação de venda do CDS</span><span class="sxs-lookup"><span data-stu-id="5d1e9-127">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="5d1e9-128">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="5d1e9-128">Entity flow</span></span>

<span data-ttu-id="5d1e9-129">As cotações de venda são criadas no Sales e sincronizadas para o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-129">Sales quotations are created in Sales and synchronized to Supply Chain Management.</span></span>

<span data-ttu-id="5d1e9-130">As cotações de vendas do Sales são sincronizadas somente se as seguintes condições forem atendidas:</span><span class="sxs-lookup"><span data-stu-id="5d1e9-130">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="5d1e9-131">Todos os produtos de cotação na cotação de vendas são mantidos externamente.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-131">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="5d1e9-132">Após você clicar em **Ativar cotação**, a cotação de venda ficará ativa.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-132">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="5d1e9-133">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="5d1e9-133">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="5d1e9-134">O campo **Tem Somente Produtos Mantidos Externamente** foi adicionado à entidade **Cotação** para rastrear consistentemente se a cotação de vendas consiste inteiramente em produtos mantidos externamente.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-134">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="5d1e9-135">Se uma cotação de venda mantiver somente produtos externamente, os produtos serão mantidos no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-135">If a sales quotation has only externally maintained products, the products are maintained in Supply Chain Management.</span></span> <span data-ttu-id="5d1e9-136">Esse comportamento ajuda a garantir que você não tente sincronizar linhas da cotação de venda que tenham produtos desconhecidos para o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-136">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Supply Chain Management.</span></span>

<span data-ttu-id="5d1e9-137">Todos os produtos de cotação da cotação de venda são atualizados com as informações **Tem Somente Produtos Mantidos Externamente** do cabeçalho de cotação de venda.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-137">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="5d1e9-138">Essas informações se encontram no campo **A Cotação Tem Somente Produtos Mantidos Externamente** na entidade **QuoteDetails**.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-138">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="5d1e9-139">Um desconto pode ser adicionado ao produto de cotação e será sincronizado para o Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-139">A discount can be added to the quote product and will be synchronized to Supply Chain Management.</span></span> <span data-ttu-id="5d1e9-140">Os campos **Desconto**, **Encargos** e **Imposto** no cabeçalho são controlados por uma configuração no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-140">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Supply Chain Management.</span></span> <span data-ttu-id="5d1e9-141">No momento, essa configuração não dá suporte ao mapeamento de integração.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-141">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="5d1e9-142">No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são mantidos e tratados no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-142">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in FSupply Chain Management.</span></span>

<span data-ttu-id="5d1e9-143">No Sales, a solução torna os seguintes campos somente leitura, pois os valores não são sincronizados para o Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="5d1e9-143">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Supply Chain Management:</span></span>

- <span data-ttu-id="5d1e9-144">Campos somente leitura no cabeçalho de cotação de vendas: **% de Desconto**, **Desconto** e **Valor do Frete**</span><span class="sxs-lookup"><span data-stu-id="5d1e9-144">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="5d1e9-145">Campos somente leitura em produtos de cotação: **Imposto**</span><span class="sxs-lookup"><span data-stu-id="5d1e9-145">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="5d1e9-146">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="5d1e9-146">Preconditions and mapping setup</span></span>

<span data-ttu-id="5d1e9-147">Antes de as cotações de venda serem sincronizadas, é importante atualizar as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-147">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="5d1e9-148">Configuração no Sales</span><span class="sxs-lookup"><span data-stu-id="5d1e9-148">Setup in Sales</span></span>

- <span data-ttu-id="5d1e9-149">Verifique se as permissões estão definidas para a equipe na qual o usuário da conexão configurada no Sales está atribuído.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-149">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="5d1e9-150">Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas a equipe não tem acesso admin.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-150">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="5d1e9-151">Se a equipe não tiver acesso de administrador quando você executar o projeto na Integração de dados, você receberá uma mensagem de erro indicando que a Equipe principal está ausente.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-151">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="5d1e9-152">Para configurar as permissões para a equipe, vá para **Configurações** &gt; **Segurança** &gt; **Equipes** e selecione a equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-152">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="5d1e9-153">Selecione **Gerenciar funções** e, em seguida, selecione a função que possui as permissões desejadas, como **Administrador do sistema**.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-153">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="5d1e9-154">Vá para **Configurações** &gt; **Administração** &gt; **Configurações do sistema** &gt; **Vendas** e certifique-se de que as seguintes configurações sejam usadas:</span><span class="sxs-lookup"><span data-stu-id="5d1e9-154">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="5d1e9-155">A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-155">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="5d1e9-156">O campo **Método de cálculo de desconto** está definido como **Item de linha**.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-156">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="5d1e9-157">Configuração no Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="5d1e9-157">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="5d1e9-158">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="5d1e9-158">QuoteHeader</span></span>

- <span data-ttu-id="5d1e9-159">Verifique se o mapeamento exigido existe para **Shipto\_country** para **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-159">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="5d1e9-160">No mapa de valores, você pode definir um valor padrão para ser usado se o valor for deixado em branco.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-160">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="5d1e9-161">Deixe apenas o lado esquerdo em branco e defina o lado direito para o país ou a região desejada.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-161">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="5d1e9-162">Assim, não é necessário digitar o país ou a região de ordens nacionais.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-162">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="5d1e9-163">O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados e um valor em branco é igual a um valor do **EUA**.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-163">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="5d1e9-164">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="5d1e9-164">QuoteLine</span></span>

- <span data-ttu-id="5d1e9-165">Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-165">Make sure that the required value map exists for **SalesUnitSymbol** in Supply Chain Management.</span></span>
- <span data-ttu-id="5d1e9-166">Verifique se as unidades necessários estão definidas no Sales.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-166">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="5d1e9-167">Um valor do modelo que tem um mapa de valores é definido para **oumid.name** como **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-167">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="5d1e9-168">Opcional: Você pode adicionar os seguintes mapeamentos para ajudar a garantir que as linhas da cotação de venda sejam importadas para o Supply Chain Management, caso não haja informações padrão do cliente ou do produto:</span><span class="sxs-lookup"><span data-stu-id="5d1e9-168">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Supply Chain Management if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="5d1e9-169">**SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-169">**SiteId** – A site is required in order to generate quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="5d1e9-170">Não há valor do modelo padrão para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-170">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="5d1e9-171">**WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-171">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Supply Chain Management.</span></span> <span data-ttu-id="5d1e9-172">Não há valor do modelo padrão para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-172">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="5d1e9-173">Mapeamento de modelos no integrador de dados</span><span class="sxs-lookup"><span data-stu-id="5d1e9-173">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="5d1e9-174">Os campos **Desconto**, **Encargos** e **Imposto** são controlados por uma configuração complexa no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-174">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Supply Chain Management.</span></span> <span data-ttu-id="5d1e9-175">No momento, essa configuração não dá suporte ao mapeamento de integração.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-175">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="5d1e9-176">No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são tratados pelo Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-176">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Supply Chain Management.</span></span>
> - <span data-ttu-id="5d1e9-177">Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-177">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="5d1e9-178">Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-178">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="5d1e9-179">As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="5d1e9-179">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="5d1e9-180">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="5d1e9-180">QuoteHeader</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="5d1e9-182">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="5d1e9-182">QuoteLine</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="5d1e9-184">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5d1e9-184">Related topics</span></span>

[<span data-ttu-id="5d1e9-185">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="5d1e9-185">Prospect to cash</span></span>](prospect-to-cash.md)

