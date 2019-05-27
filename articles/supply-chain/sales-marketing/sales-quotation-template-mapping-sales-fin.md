---
title: Sincronizar cabeçalhos e linhas de cotação de venda diretamente do Sales para o Finance and Operations
description: O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de cotação de venda diretamente do Microsoft Dynamics 365 for Sales para o Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 10/25/2018
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
ms.openlocfilehash: efe943f5c874ed041ce7984272ebc19f57cca6ef
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572572"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a><span data-ttu-id="1ee0f-103">Sincronizar cabeçalhos e linhas de cotação de venda diretamente do Sales para o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1ee0f-103">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ee0f-104">O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de cotação de venda diretamente do Microsoft Dynamics 365 for Sales para o Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="1ee0f-105">Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados no Common Data Service para Aplicativos](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="1ee0f-105">Before you can use the Prospect to cash solution, you should be familiar with [Integrate data into Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).</span></span>

## <a name="data-flow-in-prospect-to-cash"></a><span data-ttu-id="1ee0f-106">Fluxo de dados no Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="1ee0f-106">Data flow in Prospect to cash</span></span>

<span data-ttu-id="1ee0f-107">A solução Prospect to cash usa o recurso de integração de dados sincronizar dados nas instâncias do Finance and Operations e do Sales.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-107">The Prospect to cash solution uses the Data integration feature to synchronize data across instances of Finance and Operations and Sales.</span></span> <span data-ttu-id="1ee0f-108">Os modelos Prospect to cash que estão disponíveis com o recurso Integração de Dados permitem o fluxo de dados para contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-108">The Prospect to cash templates that are available with the Data integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="1ee0f-109">A ilustração a seguir mostra como os dados são sincronizados entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-109">The following illustration shows how the data is synchronized between Finance and Operations and Sales.</span></span>

<span data-ttu-id="1ee0f-110">[![Fluxo de dados em Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-110">[![Data flow in Prospect to cash](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="1ee0f-111">Modelo e tarefas</span><span class="sxs-lookup"><span data-stu-id="1ee0f-111">Template and tasks</span></span>

<span data-ttu-id="1ee0f-112">O seguinte modelo e as tarefas subjacentes são usados para sincronizar cabeçalhos e linhas de cotação de venda diretamente do Sales para o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="1ee0f-112">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="1ee0f-113">**Nome do modelo na Integração de dados:** cotações de venda (Sales para Fin and Ops) – Direto</span><span class="sxs-lookup"><span data-stu-id="1ee0f-113">**Name of the template in Data integration:** Sales Quotes (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="1ee0f-114">**Nomes das tarefas no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-114">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="1ee0f-115">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="1ee0f-115">QuoteHeader</span></span>
    - <span data-ttu-id="1ee0f-116">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="1ee0f-116">QuoteLine</span></span>

<span data-ttu-id="1ee0f-117">As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de cotação de venda possa ocorrer:</span><span class="sxs-lookup"><span data-stu-id="1ee0f-117">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="1ee0f-118">Produtos (Fin and Ops para Sales) – Direto</span><span class="sxs-lookup"><span data-stu-id="1ee0f-118">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="1ee0f-119">Contas (Sales para Fin and Ops) - Direto (se usado)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-119">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="1ee0f-120">Contatos para Clientes (Sales para Fin and Ops) – Direto (se usados)</span><span class="sxs-lookup"><span data-stu-id="1ee0f-120">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="1ee0f-121">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="1ee0f-121">Entity set</span></span>

| <span data-ttu-id="1ee0f-122">Vendas</span><span class="sxs-lookup"><span data-stu-id="1ee0f-122">Sales</span></span>        | <span data-ttu-id="1ee0f-123">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1ee0f-123">Finance and Operations</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="1ee0f-124">Cotações</span><span class="sxs-lookup"><span data-stu-id="1ee0f-124">Quotes</span></span>       | <span data-ttu-id="1ee0f-125">Cabeçalho de cotação de venda CDS</span><span class="sxs-lookup"><span data-stu-id="1ee0f-125">CDS sales quotation header</span></span> |
| <span data-ttu-id="1ee0f-126">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="1ee0f-126">QuoteDetails</span></span> | <span data-ttu-id="1ee0f-127">Linhas de cotação de venda do CDS</span><span class="sxs-lookup"><span data-stu-id="1ee0f-127">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="1ee0f-128">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="1ee0f-128">Entity flow</span></span>

<span data-ttu-id="1ee0f-129">As cotações de vendas são criadas no Sales e sincronizadas ao Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-129">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="1ee0f-130">As cotações de vendas do Sales são sincronizadas somente se as seguintes condições forem atendidas:</span><span class="sxs-lookup"><span data-stu-id="1ee0f-130">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="1ee0f-131">Todos os produtos de cotação na cotação de vendas são mantidos externamente.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-131">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="1ee0f-132">Após você clicar em **Ativar cotação**, a cotação de venda ficará ativa.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-132">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="1ee0f-133">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="1ee0f-133">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="1ee0f-134">O campo **Tem Somente Produtos Mantidos Externamente** foi adicionado à entidade **Cotação** para rastrear consistentemente se a cotação de vendas consiste inteiramente em produtos mantidos externamente.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-134">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="1ee0f-135">Se uma cotação de venda mantiver somente produtos externamente, os produtos serão mantidos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-135">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="1ee0f-136">Este comportamento ajuda a garantir que você não tente sincronizar linhas da cotação de vendas que tenham produtos que são desconhecidos para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-136">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="1ee0f-137">Todos os produtos de cotação da cotação de venda são atualizados com as informações **Tem Somente Produtos Mantidos Externamente** do cabeçalho de cotação de venda.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-137">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="1ee0f-138">Essas informações se encontram no campo **A Cotação Tem Somente Produtos Mantidos Externamente** na entidade **QuoteDetails**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-138">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="1ee0f-139">Um desconto pode ser adicionado ao produto de cotação e será sincronizado para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-139">A discount can be added to the quote product and will be synchronized to Finance and Operations.</span></span> <span data-ttu-id="1ee0f-140">Os campos **Desconto**, **Encargos** e **Imposto** no cabeçalho são controlados por uma configuração no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-140">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Finance and Operations.</span></span> <span data-ttu-id="1ee0f-141">No momento, essa configuração não dá suporte ao mapeamento de integração.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-141">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="1ee0f-142">No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são mantidos e tratados no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-142">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in Finance and Operations.</span></span>

<span data-ttu-id="1ee0f-143">No Sales, a solução torna os seguintes campos somente para leitura, porque os valores não são sincronizados com o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="1ee0f-143">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="1ee0f-144">Campos somente leitura no cabeçalho de cotação de vendas: **% de Desconto**, **Desconto** e **Valor do Frete**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-144">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="1ee0f-145">Campos somente leitura em produtos de cotação: **Imposto**</span><span class="sxs-lookup"><span data-stu-id="1ee0f-145">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="1ee0f-146">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="1ee0f-146">Preconditions and mapping setup</span></span>

<span data-ttu-id="1ee0f-147">Antes de as cotações de venda serem sincronizadas, é importante atualizar as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-147">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="1ee0f-148">Configuração no Sales</span><span class="sxs-lookup"><span data-stu-id="1ee0f-148">Setup in Sales</span></span>

- <span data-ttu-id="1ee0f-149">Verifique se as permissões estão definidas para a equipe na qual o usuário da conexão configurada no Sales está atribuído.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-149">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="1ee0f-150">Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas a equipe não tem acesso admin.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-150">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="1ee0f-151">Se a equipe não tiver acesso de administrador quando você executar o projeto na Integração de dados, você receberá uma mensagem de erro indicando que a Equipe principal está ausente.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-151">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="1ee0f-152">Para configurar as permissões para a equipe, vá para **Configurações** &gt; **Segurança** &gt; **Equipes** e selecione a equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-152">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="1ee0f-153">Selecione **Gerenciar funções** e, em seguida, selecione a função que possui as permissões desejadas, como **Administrador do sistema**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-153">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="1ee0f-154">Vá para **Configurações** &gt; **Administração** &gt; **Configurações do sistema** &gt; **Vendas** e certifique-se de que as seguintes configurações sejam usadas:</span><span class="sxs-lookup"><span data-stu-id="1ee0f-154">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="1ee0f-155">A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-155">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="1ee0f-156">O campo **Método de cálculo de desconto** está definido como **Item de linha**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-156">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="1ee0f-157">Configuração no Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="1ee0f-157">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="1ee0f-158">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="1ee0f-158">QuoteHeader</span></span>

- <span data-ttu-id="1ee0f-159">Verifique se o mapeamento exigido existe para **Shipto\_country** para **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-159">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="1ee0f-160">No mapa de valores, você pode definir um valor padrão para ser usado se o valor for deixado em branco.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-160">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="1ee0f-161">Deixe apenas o lado esquerdo em branco e defina o lado direito para o país ou a região desejada.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-161">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="1ee0f-162">Assim, não é necessário digitar o país ou a região de ordens nacionais.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-162">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="1ee0f-163">O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados e um valor em branco é igual a um valor do **EUA**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-163">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="1ee0f-164">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="1ee0f-164">QuoteLine</span></span>

- <span data-ttu-id="1ee0f-165">Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-165">Make sure that the required value map exists for **SalesUnitSymbol** in Finance and Operations.</span></span>
- <span data-ttu-id="1ee0f-166">Verifique se as unidades necessários estão definidas no Sales.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-166">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="1ee0f-167">Um valor do modelo que tem um mapa de valores é definido para **oumid.name** como **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-167">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="1ee0f-168">Opcional: Você pode adicionar os seguintes mapeamentos para ajudar a garantir que as linhas de cotação de venda sejam importadas para o Finance and Operations, caso não haja informações padrão do cliente ou do produto:</span><span class="sxs-lookup"><span data-stu-id="1ee0f-168">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="1ee0f-169">**SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-169">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="1ee0f-170">Não há valor do modelo padrão para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-170">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="1ee0f-171">**WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-171">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="1ee0f-172">Não há valor do modelo padrão para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-172">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="1ee0f-173">Mapeamento de modelos no integrador de dados</span><span class="sxs-lookup"><span data-stu-id="1ee0f-173">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="1ee0f-174">Os campos **Desconto**, **Encargos** e **Imposto** são controlados por uma configuração complexa no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-174">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="1ee0f-175">No momento, essa configuração não dá suporte ao mapeamento de integração.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-175">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="1ee0f-176">No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são tratados pelo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-176">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="1ee0f-177">Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-177">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="1ee0f-178">Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-178">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="1ee0f-179">As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="1ee0f-179">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="1ee0f-180">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="1ee0f-180">QuoteHeader</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="1ee0f-182">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="1ee0f-182">QuoteLine</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="1ee0f-184">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1ee0f-184">Related topics</span></span>

[<span data-ttu-id="1ee0f-185">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="1ee0f-185">Prospect to cash</span></span>](prospect-to-cash.md)

