---
title: "Sincronizar cabeçalhos e linhas de cotação de venda diretamente do Sales para o Finance and Operations"
description: "O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de cotação de venda diretamente do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: ChristianRytt
manager: AnnBe
ms.date: 11/14/2017
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
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 8a75c6dd91020ab3e676e2bb40d5c822731e244f
ms.contentlocale: pt-br
ms.lasthandoff: 11/14/2017

---

# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-finance-and-operations"></a><span data-ttu-id="28822-103">Sincronizar cabeçalhos e linhas de cotação de venda diretamente do Sales para o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="28822-103">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="28822-104">O tópico discute os modelos e as tarefas subjacentes que são usados para sincronizar cabeçalhos e linhas de cotação de venda diretamente do Microsoft Dynamics 365 for Sales com o Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="28822-104">The topic discusses the templates and underlying tasks that are used to synchronize sales quotation headers and lines directly from Microsoft Dynamics 365 for Sales to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.</span></span>

> [!NOTE]
> <span data-ttu-id="28822-105">Antes de usar a solução Prospect to cash, você deve familiarizar-se com a [Integração de dados do Dynamics 365](/common-data-service/entity-reference/dynamics-365-integration).</span><span class="sxs-lookup"><span data-stu-id="28822-105">Before you can use the Prospect to cash solution, you should be familiar with [Dynamics 365 Data integration](/common-data-service/entity-reference/dynamics-365-integration).</span></span>

## <a name="template-and-tasks"></a><span data-ttu-id="28822-106">Modelo e tarefas</span><span class="sxs-lookup"><span data-stu-id="28822-106">Template and tasks</span></span>

<span data-ttu-id="28822-107">O seguinte modelo e as tarefas subjacentes são usados para sincronizar cabeçalhos e linhas de cotação de venda diretamente do Sales para o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="28822-107">The following template and underlying tasks are used to synchronize sales quotation headers and lines directly from Sales to Finance and Operations:</span></span>

- <span data-ttu-id="28822-108">**Nome do modelo na Integração de dados:** cotações de venda (Sales para Fin and Ops) – Direto</span><span class="sxs-lookup"><span data-stu-id="28822-108">**Name of the template in Data integration:** Sales Quotes (Sales to Fin and Ops) - Direct</span></span>
- <span data-ttu-id="28822-109">**Nomes das tarefas no projeto de Integração de dados:**</span><span class="sxs-lookup"><span data-stu-id="28822-109">**Names of the tasks in the Data integration project:**</span></span>

    - <span data-ttu-id="28822-110">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="28822-110">QuoteHeader</span></span>
    - <span data-ttu-id="28822-111">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="28822-111">QuoteLine</span></span>

<span data-ttu-id="28822-112">As seguintes tarefas de sincronização são obrigatórias para que a sincronização de cabeçalhos e linhas de cotação de venda possa ocorrer:</span><span class="sxs-lookup"><span data-stu-id="28822-112">The following synchronization tasks are required before synchronization of sales quotation headers and lines can occur:</span></span>

- <span data-ttu-id="28822-113">Produtos (Fin and Ops para Sales) – Direto</span><span class="sxs-lookup"><span data-stu-id="28822-113">Products (Fin and Ops to Sales) - Direct</span></span>
- <span data-ttu-id="28822-114">Contas (Sales para Fin and Ops) - Direto (se usado)</span><span class="sxs-lookup"><span data-stu-id="28822-114">Accounts (Sales to Fin and Ops) - Direct (if used)</span></span>
- <span data-ttu-id="28822-115">Contatos para Clientes (Sales para Fin and Ops) – Direto (se usados)</span><span class="sxs-lookup"><span data-stu-id="28822-115">Contacts to Customers (Sales to Fin and Ops) - Direct (if used)</span></span>

## <a name="entity-set"></a><span data-ttu-id="28822-116">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="28822-116">Entity set</span></span>

| <span data-ttu-id="28822-117">Vendas</span><span class="sxs-lookup"><span data-stu-id="28822-117">Sales</span></span>        | <span data-ttu-id="28822-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="28822-118">Finance and Operations</span></span>     |
|--------------|----------------------------|
| <span data-ttu-id="28822-119">Cotações</span><span class="sxs-lookup"><span data-stu-id="28822-119">Quotes</span></span>       | <span data-ttu-id="28822-120">Cabeçalho de cotação de venda CDS</span><span class="sxs-lookup"><span data-stu-id="28822-120">CDS sales quotation header</span></span> |
| <span data-ttu-id="28822-121">QuoteDetails</span><span class="sxs-lookup"><span data-stu-id="28822-121">QuoteDetails</span></span> | <span data-ttu-id="28822-122">Linhas de cotação de venda do CDS</span><span class="sxs-lookup"><span data-stu-id="28822-122">CDS sales quotation lines</span></span>  |

## <a name="entity-flow"></a><span data-ttu-id="28822-123">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="28822-123">Entity flow</span></span>

<span data-ttu-id="28822-124">As cotações de vendas são criadas no Sales e sincronizadas ao Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-124">Sales quotations are created in Sales and synchronized to Finance and Operations.</span></span>

<span data-ttu-id="28822-125">As cotações de vendas do Sales são sincronizadas somente se as seguintes condições forem atendidas:</span><span class="sxs-lookup"><span data-stu-id="28822-125">Sales quotations from Sales are synchronized only if the following conditions are met:</span></span>

- <span data-ttu-id="28822-126">Todos os produtos de cotação na cotação de vendas são mantidos externamente.</span><span class="sxs-lookup"><span data-stu-id="28822-126">All quote products on the sales quotation are externally maintained.</span></span>
- <span data-ttu-id="28822-127">Após você clicar em **Ativar cotação**, a cotação de venda ficará ativa.</span><span class="sxs-lookup"><span data-stu-id="28822-127">After you click **Activate quote**, the sales quotation is active.</span></span>

## <a name="prospect-to-cash-solution-for-sales"></a><span data-ttu-id="28822-128">Solução Prospect to cash para o Sales</span><span class="sxs-lookup"><span data-stu-id="28822-128">Prospect to cash solution for Sales</span></span>

<span data-ttu-id="28822-129">O campo **Tem Somente Produtos Mantidos Externamente** foi adicionado à entidade **Cotação** para rastrear consistentemente se a cotação de vendas consiste inteiramente em produtos mantidos externamente.</span><span class="sxs-lookup"><span data-stu-id="28822-129">The **Has Externally Maintained Products Only** field has been added to the **Quote** entity to consistently track whether the sales quotation consists entirely of externally maintained products.</span></span> <span data-ttu-id="28822-130">Se uma cotação de venda mantiver somente produtos externamente, os produtos serão mantidos no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-130">If a sales quotation has only externally maintained products, the products are maintained in Finance and Operations.</span></span> <span data-ttu-id="28822-131">Este comportamento ajuda a garantir que você não tente sincronizar linhas da cotação de vendas que tenham produtos que são desconhecidos para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-131">This behavior helps guarantee that you don't try to synchronize sales quotation lines that have products that are unknown to Finance and Operations.</span></span>

<span data-ttu-id="28822-132">Todos os produtos de cotação da cotação de venda são atualizados com as informações **Tem Somente Produtos Mantidos Externamente** do cabeçalho de cotação de venda.</span><span class="sxs-lookup"><span data-stu-id="28822-132">All quote products on the sales quotation are updated with the **Has Externally Maintained Products Only** information from the sales quotation header.</span></span> <span data-ttu-id="28822-133">Essas informações se encontram no campo **A Cotação Tem Somente Produtos Mantidos Externamente** na entidade **QuoteDetails**.</span><span class="sxs-lookup"><span data-stu-id="28822-133">This information is found in the **Quote Has Externally Maintained Products Only** field on the **QuoteDetails** entity.</span></span>

<span data-ttu-id="28822-134">Um desconto pode ser adicionado ao produto de cotação e será sincronizado para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-134">A discount can be added to the quote product and will be synchronized to Finance and Operations.</span></span> <span data-ttu-id="28822-135">Os campos **Desconto**, **Encargos** e **Imposto** no cabeçalho são controlados por uma configuração no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-135">The **Discount**, **Charges**, and **Tax** fields on the header are controlled by a setup in Finance and Operations.</span></span> <span data-ttu-id="28822-136">No momento, essa configuração não dá suporte ao mapeamento de integração.</span><span class="sxs-lookup"><span data-stu-id="28822-136">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="28822-137">No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são mantidos e tratados no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-137">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are maintained and handled in Finance and Operations.</span></span>

<span data-ttu-id="28822-138">No Sales, a solução torna os seguintes campos somente para leitura, porque os valores não são sincronizados com o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="28822-138">In Sales, the solution makes the following fields read-only, because the values aren't synchronized to Finance and Operations:</span></span>

- <span data-ttu-id="28822-139">Campos somente leitura no cabeçalho de cotação de vendas: **% de Desconto**, **Desconto** e **Valor do Frete**</span><span class="sxs-lookup"><span data-stu-id="28822-139">Read-only fields on the sales quotation header: **Discount %**, **Discount**, and **Freight Amount**</span></span>
- <span data-ttu-id="28822-140">Campos somente leitura em produtos de cotação: **Imposto**</span><span class="sxs-lookup"><span data-stu-id="28822-140">Read-only fields on quote products: **Tax**</span></span>

## <a name="preconditions-and-mapping-setup"></a><span data-ttu-id="28822-141">Precondições e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="28822-141">Preconditions and mapping setup</span></span>

<span data-ttu-id="28822-142">Antes de as cotações de venda serem sincronizadas, é importante atualizar as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="28822-142">Before sales quotations are synchronized, it's important that you update the following settings.</span></span>

### <a name="setup-in-sales"></a><span data-ttu-id="28822-143">Configuração no Sales</span><span class="sxs-lookup"><span data-stu-id="28822-143">Setup in Sales</span></span>

- <span data-ttu-id="28822-144">Verifique se as permissões estão definidas para a equipe na qual o usuário da conexão configurada no Sales está atribuído.</span><span class="sxs-lookup"><span data-stu-id="28822-144">Make sure that permissions are set up for the team that the user from your connection set in Sales is assigned to.</span></span> <span data-ttu-id="28822-145">Se estiver usando os dados de demonstração, geralmente o usuário tem acesso admin, mas a equipe não tem acesso admin.</span><span class="sxs-lookup"><span data-stu-id="28822-145">If you're using demo data, the user usually has admin access, but the team doesn't have admin access.</span></span> <span data-ttu-id="28822-146">Se a equipe não tiver acesso de administrador quando você executar o projeto na Integração de dados, você receberá uma mensagem de erro indicando que a Equipe principal está ausente.</span><span class="sxs-lookup"><span data-stu-id="28822-146">If the team doesn't have admin access when you run the project from Data integration, you will receive an error message that states that the Principal team is missing.</span></span>

    <span data-ttu-id="28822-147">Para configurar as permissões para a equipe, vá para **Configurações** &gt; **Segurança** &gt; **Equipes** e selecione a equipe relevante.</span><span class="sxs-lookup"><span data-stu-id="28822-147">To set up permissions for the team, go to **Settings** &gt; **Security** &gt; **Teams**, and select the relevant team.</span></span> <span data-ttu-id="28822-148">Selecione **Gerenciar funções** e, em seguida, selecione a função que possui as permissões desejadas, como **Administrador do sistema**.</span><span class="sxs-lookup"><span data-stu-id="28822-148">Select **Manage Roles**, and then select a role that has the desired permissions, such as **System Administrator**.</span></span>

- <span data-ttu-id="28822-149">Vá para **Configurações** &gt; **Administração** &gt; **Configurações do sistema** &gt; **Vendas** e certifique-se de que as seguintes configurações sejam usadas:</span><span class="sxs-lookup"><span data-stu-id="28822-149">Go to **Settings** &gt; **Administration** &gt; **System settings** &gt; **Sales**, and make sure that the following settings are used:</span></span>

    - <span data-ttu-id="28822-150">A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="28822-150">The **Use system prizing calculation system** option is set to **Yes**.</span></span>
    - <span data-ttu-id="28822-151">O campo **Método de cálculo de desconto** está definido como **Item de linha**.</span><span class="sxs-lookup"><span data-stu-id="28822-151">The **Discount calculation method** field is set to **Line item**.</span></span>

### <a name="setup-in-the-data-integration-project"></a><span data-ttu-id="28822-152">Configuração no Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="28822-152">Setup in the Data integration project</span></span>

#### <a name="quoteheader"></a><span data-ttu-id="28822-153">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="28822-153">QuoteHeader</span></span>

- <span data-ttu-id="28822-154">Verifique se o mapeamento exigido existe para **Shipto\_country** para **DeliveryAddressCountryRegionISOCode**.</span><span class="sxs-lookup"><span data-stu-id="28822-154">Make sure that the required mapping exists for **Shipto\_country** to **DeliveryAddressCountryRegionISOCode**.</span></span> <span data-ttu-id="28822-155">No mapa de valores, você pode definir um valor padrão para ser usado se o valor for deixado em branco.</span><span class="sxs-lookup"><span data-stu-id="28822-155">In the value map, you can define a default value that is used if the value is left blank.</span></span> <span data-ttu-id="28822-156">Deixe apenas o lado esquerdo em branco e defina o lado direito para o país ou a região desejada.</span><span class="sxs-lookup"><span data-stu-id="28822-156">Just leave the left side blank, and set the right side to the desired country or region.</span></span> <span data-ttu-id="28822-157">Assim, não é necessário digitar o país ou a região de ordens nacionais.</span><span class="sxs-lookup"><span data-stu-id="28822-157">In this way, you don't have to type the country or region for national orders.</span></span>

    <span data-ttu-id="28822-158">O valor do modelo é um mapa de valores em que vários países ou regiões são mapeados e um valor em branco é igual a um valor do **EUA**.</span><span class="sxs-lookup"><span data-stu-id="28822-158">The template value is a value map where several countries or regions are mapped, and where a blank value equals a value of **US**.</span></span>

#### <a name="quoteline"></a><span data-ttu-id="28822-159">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="28822-159">QuoteLine</span></span>

- <span data-ttu-id="28822-160">Verifique se existe o mapa de valores necessário para **SalesUnitSymbol** no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-160">Make sure that the required value map exists for **SalesUnitSymbol** in Finance and Operations.</span></span>
- <span data-ttu-id="28822-161">Verifique se as unidades necessários estão definidas no Sales.</span><span class="sxs-lookup"><span data-stu-id="28822-161">Make sure that the required units are defined in Sales.</span></span>

    <span data-ttu-id="28822-162">Um valor do modelo que tem um mapa de valores é definido para **oumid.name** como **SalesUnitSymbol**.</span><span class="sxs-lookup"><span data-stu-id="28822-162">A template value that has a value map is defined for **oumid.name** to **SalesUnitSymbol**.</span></span>

- <span data-ttu-id="28822-163">Opcional: Você pode adicionar os seguintes mapeamentos para ajudar a garantir que as linhas de cotação de venda sejam importadas para o Finance and Operations, caso não haja informações padrão do cliente ou do produto:</span><span class="sxs-lookup"><span data-stu-id="28822-163">Optional: You can add the following mappings to help guarantee that sales quotation lines are imported into Finance and Operations if there is no default information from either the customer or the product:</span></span>

    - <span data-ttu-id="28822-164">**SiteId** – Um site é necessário para gerar cotações e linhas da ordem de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-164">**SiteId** – A site is required in order to generate quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="28822-165">Não há valor do modelo padrão para **SiteId**.</span><span class="sxs-lookup"><span data-stu-id="28822-165">There is no default template value for **SiteId**.</span></span>
    - <span data-ttu-id="28822-166">**WarehouseId** – Um depósito é necessário para processar cotações e linhas da ordem de venda no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-166">**WarehouseId** – A warehouse is required in order to process quotations and sales order lines in Finance and Operations.</span></span> <span data-ttu-id="28822-167">Não há valor do modelo padrão para **WarehouseId**.</span><span class="sxs-lookup"><span data-stu-id="28822-167">There is no default template value for **WarehouseId**.</span></span>

## <a name="template-mapping-in-data-integrator"></a><span data-ttu-id="28822-168">Mapeamento de modelos no integrador de dados</span><span class="sxs-lookup"><span data-stu-id="28822-168">Template mapping in data integrator</span></span>

> [!NOTE]
> - <span data-ttu-id="28822-169">Os campos **Desconto**, **Encargos** e **Imposto** são controlados por uma configuração complexa no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-169">The **Discount**, **Charges**, and **Tax** fields are controlled by a complex setup in Finance and Operations.</span></span> <span data-ttu-id="28822-170">No momento, essa configuração não dá suporte ao mapeamento de integração.</span><span class="sxs-lookup"><span data-stu-id="28822-170">Currently, this setup doesn't support integration mapping.</span></span> <span data-ttu-id="28822-171">No design atual, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são tratados pelo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="28822-171">In the current design, the **Price**, **Discount**, **Charge**, and **Tax** fields are handled by Finance and Operations.</span></span>
> - <span data-ttu-id="28822-172">Os campos **Termos de pagamento**, **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="28822-172">The **Payment terms**, **Freight terms**, **Delivery terms**, **Shipping method**, and **Delivery mode** fields aren't part of the default mappings.</span></span> <span data-ttu-id="28822-173">Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="28822-173">To map these fields, you must set up a value mapping that is specific to the data in the organizations that the entity is synchronized between.</span></span>

<span data-ttu-id="28822-174">As seguintes ilustrações mostram um exemplo de um mapeamento de modelos no integrador de dados.</span><span class="sxs-lookup"><span data-stu-id="28822-174">The following illustrations show an example of a template mapping in data integrator.</span></span>

### <a name="quoteheader"></a><span data-ttu-id="28822-175">QuoteHeader</span><span class="sxs-lookup"><span data-stu-id="28822-175">QuoteHeader</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a><span data-ttu-id="28822-177">QuoteLine</span><span class="sxs-lookup"><span data-stu-id="28822-177">QuoteLine</span></span>

![Mapeamento de modelos no integrador de dados](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a><span data-ttu-id="28822-179">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="28822-179">Related topics</span></span>

[<span data-ttu-id="28822-180">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="28822-180">Prospect to cash</span></span>](prospect-to-cash.md)


