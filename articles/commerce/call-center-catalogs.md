---
title: Catálogos do call center
description: Este tópico descreve a funcionalidade específica de call center para catálogos no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e4d2b1f4b7fb9394f54674f9622c8a8edd435311
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021578"
---
# <a name="call-center-catalogs"></a><span data-ttu-id="f3451-103">Catálogos do call center</span><span class="sxs-lookup"><span data-stu-id="f3451-103">Call center catalogs</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f3451-104">Este tópico descreve a funcionalidade específica de call center vinculada a recursos de catálogo no Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f3451-104">This topic describes the call center–specific functionality linked to the catalog capabilities in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f3451-105">Os recursos de catálogo disponíveis no Commerce podem ser usados para várias finalidades.</span><span class="sxs-lookup"><span data-stu-id="f3451-105">The catalog features found in Commerce can be used for multiple purposes.</span></span> <span data-ttu-id="f3451-106">Os recursos de catálogo foram inicialmente criados para dar suporte a integrações de comércio eletrônico de terceiros.</span><span class="sxs-lookup"><span data-stu-id="f3451-106">Initially the catalog features were created to support third party e-Commerce integrations.</span></span> <span data-ttu-id="f3451-107">O catálogo permitiu às empresas a criação de um agrupamento de produtos e atributos que podem ser publicados externamente para o consumo por uma solução de comércio eletrônico de terceiros.</span><span class="sxs-lookup"><span data-stu-id="f3451-107">Catalog setup allowed companies to create a grouping of products and attributes that could be published externally for consumption by a third party e-Commerce solution.</span></span>

<span data-ttu-id="f3451-108">Quando o suporte do canal de call center foi adicionado, o conceito de catálogo se expandiu para adicionar mais funcionalidades de suporte e gerenciamento de recursos relacionadas aos catálogos tradicionais de marketing direto ao consumidor.</span><span class="sxs-lookup"><span data-stu-id="f3451-108">When call center channel support was added, the catalog concept was expanded to add additional capabilities for supporting and managing features related to traditional direct-to-consumer marketing catalogs.</span></span> <span data-ttu-id="f3451-109">Uma empresa direta ao consumidor frequentemente produzirá catálogos impressos, enviados por email a um ou mais segmentos de clientes.</span><span class="sxs-lookup"><span data-stu-id="f3451-109">A direct-to-consumer company will often produce printed catalogs, which are then mailed to one or more segments of customers.</span></span> <span data-ttu-id="f3451-110">Esses catálogos normalmente têm promoções ou ofertas específicas que somente serão liquidadas se o cliente fornecer um código de identificação do catálogo no momento da criação da ordem.</span><span class="sxs-lookup"><span data-stu-id="f3451-110">These catalogs will typically have specific promotions or offers that will only be honored if the customer provides a catalog identification code at the time of order creation.</span></span>

<span data-ttu-id="f3451-111">As empresas de marketing direto ao consumidor são muito focadas no rastreamento de resposta para esses catálogos para garantir que os custos para produzir e enviar e-mail para eles sejam justificados.</span><span class="sxs-lookup"><span data-stu-id="f3451-111">Direct-to-consumer marketing companies are very focused on tracking the response to these catalogs to ensure that the costs to produce and mail them are justified.</span></span> <span data-ttu-id="f3451-112">Para rastrear a resposta, um código é impresso na parte de trás do catálogo e esse código é solicitado e aplicado quando o destinatário do catálogo ligar para fazer um pedido por telefone (ou agora o código pode ser inserido quando o cliente fizer um pedido online).</span><span class="sxs-lookup"><span data-stu-id="f3451-112">To track the response, a code is traditionally printed on the back of the catalog and this code is then requested and applied when the catalog recipient calls to place an order by phone (or now more traditionally the code may be entered when the customer places an order online).</span></span> <span data-ttu-id="f3451-113">Embora existam diferentes termos do setor usados para identificar esse código de rastreamento de catálogo (incluindo código de tecla, código promocional, código de catálogo, código-fonte), no Commerce nos referimos ao código como a **ID do código-fonte**.</span><span class="sxs-lookup"><span data-stu-id="f3451-113">While there are different industry terms that have been used to identify this catalog tracking code (including key code, promo code, catalog code, source code), we refer to the code in Commerce as the **Source code ID**.</span></span>

## <a name="basic-catalog-setup"></a><span data-ttu-id="f3451-114">Configuração básica do catálogo</span><span class="sxs-lookup"><span data-stu-id="f3451-114">Basic catalog setup</span></span>

<span data-ttu-id="f3451-115">Vá para **Varejo e Comércio** \> **Catálogos e classificações** \> **Todos os catálogos** para configurar seu catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-115">Go to **Retail and Commerce** \> **Catalogs and assortments** \> **All catalogs** to configure your catalog.</span></span>

<span data-ttu-id="f3451-116">Ao criar um novo catálogo, primeiro você deve vincular o catálogo a um ou mais canais.</span><span class="sxs-lookup"><span data-stu-id="f3451-116">When you create a new catalog, you must first link the catalog to one or more channels.</span></span> <span data-ttu-id="f3451-117">Isso é feito na FastTab **Canais de comércio** do formulário **Configuração de catálogo**.</span><span class="sxs-lookup"><span data-stu-id="f3451-117">This is done in the **Commerce channels** fast tab on the **Catalog setup** form.</span></span> <span data-ttu-id="f3451-118">Clique em **Adicionar** e selecione um ou mais canais.</span><span class="sxs-lookup"><span data-stu-id="f3451-118">Click **Add** and select one or more channels.</span></span> <span data-ttu-id="f3451-119">Somente os itens vinculados ao canal selecionado [sortimentos](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments) podem ser usados ao criar o catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-119">Only items linked to your selected channel [assortments](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments) can be used when creating the catalog.</span></span>

<span data-ttu-id="f3451-120">Para adicionar produtos a um catálogo, uma hierarquia de navegação será escolhida.</span><span class="sxs-lookup"><span data-stu-id="f3451-120">To add products to a catalog, a navigation hierarchy must be chosen.</span></span> <span data-ttu-id="f3451-121">A hierarquia de navegação suportará a estrutura da categoria do catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-121">The navigation hierarchy will support the category structure for the catalog.</span></span> <span data-ttu-id="f3451-122">Você deve selecionar de uma das hierarquias de navegação vinculadas aos canais selecionados na FastTab **Canais de comércio** da página **Catálogo**.</span><span class="sxs-lookup"><span data-stu-id="f3451-122">You must pick from one of the navigation hierarchies linked to the channels selected on the **Commerce channels** FastTab of the **Catalog** page.</span></span> <span data-ttu-id="f3451-123">Se um canal de navegação não foi vinculado a um canal anteriormente, vá para **Varejo e Comércio** \> **Configuração de canal** \> **Categorias de canal e atributos de produtos** para vincular uma hierarquia de navegação padrão a cada um de seus canais.</span><span class="sxs-lookup"><span data-stu-id="f3451-123">If a navigation channel was not linked to a channel previously, go to **Retail and Commerce** \> **Channel setup** \> **Channel categories and product attributes** to link a navigation hierarchy default to each of your channels.</span></span>

<span data-ttu-id="f3451-124">Na guia de menu **Catálogos**, na página **Configuração de catálogo**, clique em **Adicionar produtos** para configurar os produtos para adicionar ao catálogo, ou selecione um nó na hierarquia de navegação (selecionar um nó alterará a apresentação da tela e permitirá que você adicionar produtos diretamente a uma categoria no catálogo).</span><span class="sxs-lookup"><span data-stu-id="f3451-124">On the **Catalogs** menu tab, on the **Catalog setup** page, click **Add products** to configure the products to add to the catalog, or select a node in the navigation hierarchy (selecting a node will change the screen presentation and allow you to add products directly to a category within the catalog).</span></span>

<span data-ttu-id="f3451-125">Clique no nó superior da hierarquia do catálogo para retornar à exibição do cabeçalho do catálogo principal.</span><span class="sxs-lookup"><span data-stu-id="f3451-125">Click the top node of the catalog hierarchy to return to the main catalog header view.</span></span> <span data-ttu-id="f3451-126">Configure datas efetivas e de vencimento, conforme necessário na guia rápida **Geral** .</span><span class="sxs-lookup"><span data-stu-id="f3451-126">Configure effective and expiration dates as necessary on the **General** FastTab.</span></span>

<span data-ttu-id="f3451-127">Antes do catálogo ficar disponível para uso, ele deve ser publicado.</span><span class="sxs-lookup"><span data-stu-id="f3451-127">Before the catalog is available to use, it must be published.</span></span> <span data-ttu-id="f3451-128">Clique em **Validar catálogo** no menu **Catálogos** para processar a validação.</span><span class="sxs-lookup"><span data-stu-id="f3451-128">Click **Validate catalog** on the **Catalogs** menu to process a validation.</span></span> <span data-ttu-id="f3451-129">Esta ação é necessária e validará se a configuração necessário é precisa.</span><span class="sxs-lookup"><span data-stu-id="f3451-129">This is required action and will validate that the required setup is accurate.</span></span> <span data-ttu-id="f3451-130">Clique em **Exibir resultados** para ver os detalhes da validação.</span><span class="sxs-lookup"><span data-stu-id="f3451-130">Click **View results** to see the details of the validation.</span></span> <span data-ttu-id="f3451-131">Se forem encontrados erros, você deverá corrigir os dados e executar a validação novamente até que ela seja aprovada.</span><span class="sxs-lookup"><span data-stu-id="f3451-131">If errors are found, you must correct the data and run validation again until the validation has passed.</span></span>

<span data-ttu-id="f3451-132">Depois que a validação for confirmada, clique em **Fluxo de trabalho** no menu para iniciar o fluxo de trabalho de aprovação.</span><span class="sxs-lookup"><span data-stu-id="f3451-132">After validation is confirmed, click **Workflow** on the menu to start the approval workflow.</span></span> <span data-ttu-id="f3451-133">Clique em **Enviar** no menu **Fluxo de Trabalho** para executar o processo.</span><span class="sxs-lookup"><span data-stu-id="f3451-133">Click **Submit** on the **Workflow** menu to execute the process.</span></span> <span data-ttu-id="f3451-134">Configure as etapas e os usuários autorizados para o fluxo de trabalho em **Varejo e Comércio** \> **Configuração da sede** \> **Fluxos de trabalho de comércio**.</span><span class="sxs-lookup"><span data-stu-id="f3451-134">Configure the steps and authorized users for the workflow from **Retail and Commerce** \> **Headquarters setup** \> **Commerce workflows**.</span></span> <span data-ttu-id="f3451-135">O fluxo de trabalho definirá as etapas necessárias para obter o catálogo com um status **Aprovado** .</span><span class="sxs-lookup"><span data-stu-id="f3451-135">The workflow will define the steps needed to get the catalog into an **Approved** status.</span></span> <span data-ttu-id="f3451-136">Quando o catálogo estiver com um status **Aprovado** , clique na opção **Publicar** no menu **Catálogos** para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="f3451-136">When the catalog is in an **Approved** status, you can click the **Publish** option on the **Catalogs** menu to complete the process.</span></span> <span data-ttu-id="f3451-137">Depois do catálogo estiver em um status **Publicado** , ele poderá ser usado na entrada de ordem do call center e nos processo de envio do catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-137">After the catalog is in a **Published** status, it can be used in call center order entry and send catalog processes.</span></span>

## <a name="use-catalogs-to-drive-sales-order-pricing-and-promotions"></a><span data-ttu-id="f3451-138">Use catálogos para impulsionar preços e promoções de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="f3451-138">Use catalogs to drive sales order pricing and promotions</span></span>

<span data-ttu-id="f3451-139">Um motivo essencial para definir um catálogo a ser usado em um call center é poder configurar preços e promoções específicos desse catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-139">A core reason for defining a catalog to use with a call center is to be able to configure specific prices and promotions for that catalog.</span></span> <span data-ttu-id="f3451-140">Os clientes que fizerem pedidos a partir deste catálogo receberão esses preços e promoções na entrada de ordem do call center, se o **ID do código-fonte** for aplicado ao cabeçalho ou linhas da ordem.</span><span class="sxs-lookup"><span data-stu-id="f3451-140">Customers ordering from this catalog will receive these prices and promotions in call center order entry if the catalog's **Source code ID** is applied to the order header or lines.</span></span>

<span data-ttu-id="f3451-141">Para configurar preços específicos do catálogo, selecione a opção **Grupos de preços** da guia **Catálogo** para vincular um ou mais grupos de preços ao catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-141">To configure catalog specific prices, select the **Price groups** option from the **Catalogs** tab to link one or more price groups to the catalog.</span></span> <span data-ttu-id="f3451-142">Todos os contratos comerciais, diários de ajuste de preço e descontos avançados (limite, quantidade, compra combinada) que forem vinculados ao mesmo grupo de preços serão aplicados quando os clientes fizerem pedidos usando este catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-142">All trade agreements, price adjustment journals, and advanced discounts (threshold, quantity, mix and match) that have been linked to the same price group will be applied when customers order from this catalog.</span></span>

<span data-ttu-id="f3451-143">Na guia rápida **Códigos-fonte**, clique em **Adicionar** para adicionar um ou mais identificadores de **ID de código-fonte** neste catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-143">On the **Source codes** FastTab, click **Add** to add one or more **Source code ID** identifiers to this catalog.</span></span> <span data-ttu-id="f3451-144">Esse é o código que será aplicado durante a entrada da ordem do call center ao cabeçalho da ordem de venda (e linhas).</span><span class="sxs-lookup"><span data-stu-id="f3451-144">This is the code that will be applied during call center order entry to the sales order header (and lines).</span></span> <span data-ttu-id="f3451-145">Este código é usado para vincular a ordem de venda ao catálogo e, finalmente aos grupos de preços e a quaisquer preços especiais e promoções que foram configurados.</span><span class="sxs-lookup"><span data-stu-id="f3451-145">This code is used to link the sales order to the catalog and ultimately to the price groups and any special prices and promotions that have been configured.</span></span>

## <a name="use-the-source-id-to-track-costs-and-response-rates"></a><span data-ttu-id="f3451-146">Use a ID de origem para rastrear custos e taxas de resposta</span><span class="sxs-lookup"><span data-stu-id="f3451-146">Use the source ID to track costs and response rates</span></span>

<span data-ttu-id="f3451-147">Ao definir a **ID do código-fonte**, você pode, como opção, vincular esta ID a uma **ID do mercado de destino**.</span><span class="sxs-lookup"><span data-stu-id="f3451-147">When defining the **Source code ID**, you can optionally link this ID to a **Target market ID**.</span></span> <span data-ttu-id="f3451-148">A **ID do mercado de destino** pode ser definida em **Varejo e Comércio** \> **Clientes** \> **Mercado de destino**.</span><span class="sxs-lookup"><span data-stu-id="f3451-148">The **Target market ID** can be defined in **Retail and Commerce** \> **Customers** \> **Target market**.</span></span> <span data-ttu-id="f3451-149">O mercado de destino é uma lista de clientes e/ou clientes potenciais que pertencem a um segmento definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f3451-149">The target market is a list of customers and/or prospects that belong to a user-defined segment.</span></span> <span data-ttu-id="f3451-150">Vincular os dados do cliente ou do cliente potencial à ID do código-fonte permite a melhor visibilidade dos destinatários do catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-150">Linking the customer or prospect data to the source code ID allows for better visibility into the recipients of the catalog.</span></span> <span data-ttu-id="f3451-151">Se um cliente estiver vinculado a um mercado de destino e esse mercado de destino estiver vinculado à ID do código-fonte/catálogo ativos, os usuários do call center também poderão ver quais catálogos um cliente recebeu, selecionando a opção de menu **Códigos-fonte** na guia do menu **Clientes** na página **Atendimento ao cliente**.</span><span class="sxs-lookup"><span data-stu-id="f3451-151">If a customer is linked to a target market and that target market is linked to an active source code ID/catalog, call center users will be able to see what catalogs a customer has received by selecting the **Source codes** menu option on the **Customers** menu tab on the **Customer service** page.</span></span> <span data-ttu-id="f3451-152">Durante a entrada de ordem, os usuários do call center também podem ver os catálogos específicos enviados ao cliente na lista suspensa **Origem** no cabeçalho da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f3451-152">During order entry, call center users can also see the specific catalogs a customer was sent in the **Source** drop-down list on the sales order header.</span></span> <span data-ttu-id="f3451-153">Alterar o filtro de **Todos** para **Destinado** permitirá que o usuário veja os catálogos ativos específicos enviados ao cliente.</span><span class="sxs-lookup"><span data-stu-id="f3451-153">Changing the filter from **All** to **Targeted** will allow the user to see the specific active catalogs the customer was sent.</span></span> <span data-ttu-id="f3451-154">Isso é útil em situações em que o cliente pode ter esquecido seu catálogo ou não consegue localizar ou ler o código de catálogo quando está chamando para criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f3451-154">This is helpful in situations where the customer may have forgotten their catalog or can't locate or read the catalog code when they are calling in to create a sales order.</span></span>

<span data-ttu-id="f3451-155">É possível vincular várias IDs do código-fonte um catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-155">It's possible to link multiple source code IDs to a catalog.</span></span> <span data-ttu-id="f3451-156">Geralmente, isso é necessário quando uma empresa quer rastrear a taxa de resposta por segmentos diferentes.</span><span class="sxs-lookup"><span data-stu-id="f3451-156">This is often needed when a company wants to track the response rate by different segments.</span></span> <span data-ttu-id="f3451-157">A empresa fornecerá um código de catálogo exclusivo para diferentes segmentos de clientes, o que permitirá rastrear a taxa de resposta até o nível do segmento, dentro de um determinado evento de catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-157">The company will give a unique catalog code to different customer segments, which allows for tracking the response rate, down to the segment level, within a particular catalog event.</span></span>

<span data-ttu-id="f3451-158">Selecionar um registro específico de **ID de código-fonte** e clicar na opção **Detalhes** na guia rápida **Códigos-fonte** fornecerá campos adicionais nos quais projeções de venda, custos com correspondência e datas da correspondência podem ser capturados.</span><span class="sxs-lookup"><span data-stu-id="f3451-158">Selecting a particular **Source code ID** record and clicking the **Details** option on the **Source codes** FastTab will provide additional fields where sales projections, mailing costs, and mailing dates can be captured.</span></span> <span data-ttu-id="f3451-159">Esses dados são úteis para uma análise detalhada da eficácia do catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-159">This data is helpful for doing detailed analysis on the effectiveness of the catalog.</span></span> <span data-ttu-id="f3451-160">Os usuários podem retornar a esta página ao longo do tempo e usar os botões **Análise de código-fonte** e **Comparar promoções** para acionar relatórios analíticos com base nos dados de vendas atuais e comparar custos e orçamento com os valores reais.</span><span class="sxs-lookup"><span data-stu-id="f3451-160">Users can return to this page over time and use the **Source code analysis** and **Compare promotions** buttons to trigger analytical reports based on current sales data and compare costs and budget to actuals.</span></span>

## <a name="configure-catalog-specific-order-and-item-scripts"></a><span data-ttu-id="f3451-161">Configurar scripts de itens e ordens específicas de catálogo</span><span class="sxs-lookup"><span data-stu-id="f3451-161">Configure catalog-specific order and item scripts</span></span>

<span data-ttu-id="f3451-162">Quando um usuário do call center estiver criando uma ordem de venda, eles podem usar scripts na tela.</span><span class="sxs-lookup"><span data-stu-id="f3451-162">When a call center user is creating a sales order, they can use on-screen scripts.</span></span> <span data-ttu-id="f3451-163">Esses scripts baseados em texto podem fornecer informações adicionais que o usuário deve informar ao cliente, ou podem ser notas/lembretes internos que o usuário do call center deve analisar e atuar, enquanto cria a ordem do cliente.</span><span class="sxs-lookup"><span data-stu-id="f3451-163">These text-based scripts may provide additional information that the user should say to the customer, or it may be internal notes/reminders that the call center user should review and react to as they are creating the sales order.</span></span>

<span data-ttu-id="f3451-164">Geralmente, é bom ter diferentes conjuntos de scripts para diferentes catálogos.</span><span class="sxs-lookup"><span data-stu-id="f3451-164">It is often helpful to have different sets of scripts for different catalogs.</span></span> <span data-ttu-id="f3451-165">Na guia rápida **Scripts**, os scripts pré-definidos podem ser vinculados a um catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-165">On the **Scripts** FastTab, pre-defined scripts can be linked to a catalog.</span></span> <span data-ttu-id="f3451-166">Use o campo **Tempo** para determinar se o script aparecerá no início da ordem (assim que a ID do código-fonte for inserida no cabeçalho da ordem) ou no final da ordem (no formulário de resumo da ordem do cliente).</span><span class="sxs-lookup"><span data-stu-id="f3451-166">Use the **Timing** field to determine if the script will appear at the beginning of the order (as soon as the source code ID is entered on the order header), or at the end of the order (in the sales order summary form).</span></span>

<span data-ttu-id="f3451-167">Ao selecionar um nó na hierarquia do catálogo e ao trabalhar com dados na guia rápida **Produtos**, os usuários também podem vincular scripts que são específicos para catálogos ou itens que usam a ação **Scripts**.</span><span class="sxs-lookup"><span data-stu-id="f3451-167">When selecting a node in the catalog's hierarchy and working with the data on the **Products** FastTab, users can also link scripts that are specific to catalogs or items using the **Scripts** action.</span></span>

## <a name="configure-catalog-specific-up-sell-and-cross-sell-items"></a><span data-ttu-id="f3451-168">Configurar itens de venda cruzada e venda específicos do catálogo</span><span class="sxs-lookup"><span data-stu-id="f3451-168">Configure catalog-specific up-sell and cross-sell items</span></span>

<span data-ttu-id="f3451-169">A vinculação de sugestões de venda/venda cruzada a um item pode ser feita a partir da configuração de produtos, mas em alguns casos, uma empresa pode promover itens especiais de venda/venda cruzada a clientes que solicitam um produto específico de um catálogo específico</span><span class="sxs-lookup"><span data-stu-id="f3451-169">Linking up-sell/cross-sell suggestions to an item can be done from the products setup, but in some cases, a company may want to promote special up-sell/cross-sell items to customers ordering a specific product from a specific catalog.</span></span> <span data-ttu-id="f3451-170">Na guia rápida **Produtos**, selecione um item e clique em **Itens de venda adicional/venda cruzada** para configurar produtos para venda ou venda cruzada a clientes que compram o item selecionado do catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-170">On the **Products** FastTab, select an item and click **Up-sell/cross-sell items** to configure products to be up or cross-sold to customers who purchase the selected item from the catalog.</span></span> <span data-ttu-id="f3451-171">Durante a entrada de ordem do call center, os itens de venda/venda cruzada específicos do catálogo serão exibidos na tela, em vez de produtos padrão de venda/venda cruzada que podem ter sido configurados para esse item por meio da configuração usual do produto.</span><span class="sxs-lookup"><span data-stu-id="f3451-171">During call center order entry, catalog specific up-sell/cross-sell items will appear on the screen instead of standard up-sell/cross-sell products that may have been configured for that item through the usual product configuration.</span></span>

<span data-ttu-id="f3451-172">Os itens de venda/venda cruzada também podem aproveitar os recursos de script para mostrar mensagens específicas que um usuário verá quando o item de venda/venda cruzada for exibido durante a entrada da ordem.</span><span class="sxs-lookup"><span data-stu-id="f3451-172">Up-sell/cross-sell items can also take advantage of the script features to show specific messages that a user will see when the up-sell/cross-sell item is displayed during order entry.</span></span> <span data-ttu-id="f3451-173">Os scripts vinculados a produtos de venda/venda cruzada configurados especificamente para um produto de catálogo só aparecerão quando o código-fonte desse catálogo for aplicado na entrada de ordem do call center.</span><span class="sxs-lookup"><span data-stu-id="f3451-173">Scripts tied to up-sell/cross-sell products configured specifically for a catalog product will only appear when that catalog's source code is applied in call center order entry.</span></span>

## <a name="catalog-page-analysis"></a><span data-ttu-id="f3451-174">Análise da página do catálogo</span><span class="sxs-lookup"><span data-stu-id="f3451-174">Catalog page analysis</span></span>

<span data-ttu-id="f3451-175">Na guia **Catálogos**, as opções estão disponíveis para configurar as **Páginas do catálogo**.</span><span class="sxs-lookup"><span data-stu-id="f3451-175">On the **Catalogs** tab, options are available to configure **Catalog pages**.</span></span> <span data-ttu-id="f3451-176">Esse recurso permite definir as páginas específicas e os tipos de páginas para o tipo de catálogo impresso e seus custos associados.</span><span class="sxs-lookup"><span data-stu-id="f3451-176">This feature allows you to define specific pages and page types for the printed catalog and their associated costs.</span></span>

<span data-ttu-id="f3451-177">Ao configurar os produtos no catálogo, use a ação **Layout de página de produto** para definir as páginas específicas, a porcentagem da página e a posição dos detalhes da página para o item.</span><span class="sxs-lookup"><span data-stu-id="f3451-177">When configuring the products in the catalog, use the **Product page layout** action to define the specific pages, percentage of page, and position of page details for the item.</span></span> <span data-ttu-id="f3451-178">A configuração desses dados permitirá que os usuários obtenham vantagem do **Relatório de análise de área de catálogo**.</span><span class="sxs-lookup"><span data-stu-id="f3451-178">Configuring this data will allow users to take advantage of the **Catalog area analysis report**.</span></span> <span data-ttu-id="f3451-179">Para encontrar este relatório, navegue até **Varejo e Comércio** \> **Relatórios de call center** \> **Relatório de análise de área de catálogo**.</span><span class="sxs-lookup"><span data-stu-id="f3451-179">This report is found by navigating to **Retail and Commerce** \> **Call center reports** \> **Catalog area analysis** report.</span></span> <span data-ttu-id="f3451-180">Este relatório analisa as vendas feitas em relação ao catálogo (ordens de vendas nas quais o código de origem do catálogo estava vinculado ao cabeçalho ou à linha da ordem) e sua porcentagem de página e custos associados para fornecer um relatório de marketing direto tradicional**Análise de polegada quadrada**.</span><span class="sxs-lookup"><span data-stu-id="f3451-180">This report analyzes sales placed against the catalog (sales orders where the source ID for the catalog was tied to the order header or line) and their associated percent of page and costs to give a traditional direct marketing **Square inch analysis** report.</span></span>

## <a name="catalog-requests"></a><span data-ttu-id="f3451-181">Solicitações de catálogo</span><span class="sxs-lookup"><span data-stu-id="f3451-181">Catalog requests</span></span>

<span data-ttu-id="f3451-182">Como os catálogos são configurados e publicados no Commerce, é possível utilizar o recurso **Enviar catálogo**.</span><span class="sxs-lookup"><span data-stu-id="f3451-182">As catalogs are configured and published in Commerce, the **Send catalog** feature can be utilized.</span></span> <span data-ttu-id="f3451-183">Esse recurso ficará disponível nas páginas **Pesquisa de cliente** e **Atendimento ao cliente**.</span><span class="sxs-lookup"><span data-stu-id="f3451-183">This feature is available on the **Customer search** and **Customer service** pages.</span></span> <span data-ttu-id="f3451-184">Depois de selecionar um registro de cliente através da **Pesquisa de cliente** ou enquanto exibe uma conta de clientes selecionados do **Atendimento ao cliente**, os usuários podem selecionar a opção **Enviar catálogo** que abrirá uma caixa de diálogo permitindo que o usuário escolha entre uma lista de catálogos publicados e ativos.</span><span class="sxs-lookup"><span data-stu-id="f3451-184">After selecting a customer record through **Customer search** or while viewing a selected customers account from **Customer service**, users may select the **Send catalog** option which will open a dialog box allowing the user to choose from a list of any published and active catalogs.</span></span> <span data-ttu-id="f3451-185">Um usuário pode selecionar um catálogo e uma quantidade e um ID de código-fonte específico para enviar.</span><span class="sxs-lookup"><span data-stu-id="f3451-185">A user can select a catalog and a quantity, and a particular source code ID to send.</span></span> <span data-ttu-id="f3451-186">Quando eles clicam no botão **Enviar**, uma solicitação é armazenada, que pode ser gerenciada imprimindo o relatório **Solicitações de catálogo**.</span><span class="sxs-lookup"><span data-stu-id="f3451-186">When they click the **Send** button, a request is stored which can then be managed by printing the **Catalog requests** report.</span></span> <span data-ttu-id="f3451-187">Para encontrar este relatório, navegue até **Varejo e Comércio** \> **Relatórios de call center** \> **Relatório de solicitações de catálogo**.</span><span class="sxs-lookup"><span data-stu-id="f3451-187">This report is found by navigating to **Retail and Commerce** \> **Call center reports** \> **Catalog requests report**.</span></span> <span data-ttu-id="f3451-188">Ele lista todas as solicitações de catálogo, incluindo o nome do cliente e os detalhes do endereço do cliente que solicitou o catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-188">It lists all the catalog requests, including the customer name and address details of the customer who requested the catalog.</span></span> <span data-ttu-id="f3451-189">Esse relatório pode ser usado internamente ou os dados podem ser transmitidos para um terceiro que suporta processos externos para enviar fisicamente o catálogo ao cliente.</span><span class="sxs-lookup"><span data-stu-id="f3451-189">This report can be used internally or the data can be transmitted to a third party supporting external processes for physically sending the catalog to the customer.</span></span>

## <a name="additional-features"></a><span data-ttu-id="f3451-190">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f3451-190">Additional features</span></span>

<span data-ttu-id="f3451-191">Na guia **Catálogos**, as opções para configurar uma **Agenda de pagamento** e **Produtos liberados** também estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f3451-191">On the **Catalogs** tab, options for configuring a **Payment schedule** and **Free products** are also available.</span></span> <span data-ttu-id="f3451-192">Se o ID do código-fonte vinculado ao catálogo for aplicado durante a entrada de ordem do call center, o cliente será elegível para os produtos gratuitos ou o uso das agendas de pagamento do catálogo específico, conforme definido.</span><span class="sxs-lookup"><span data-stu-id="f3451-192">If the source code ID linked to the catalog is applied during call center order entry, the customer will be eligible for the free products or use of the specific catalog payment schedules as defined.</span></span> <span data-ttu-id="f3451-193">Se for necessário limitar o cliente para poder selecionar apenas as programações de pagamento vinculadas ao seu catálogo e nem todas as programações de pagamento ativas no sistema, a caixa de seleção **Permitir apenas planos de catálogo** pode ser selecionada para um ou mais das IDs do código-fonte definidos para aplicar essas restrições.</span><span class="sxs-lookup"><span data-stu-id="f3451-193">If it's necessary to limit the customer to only being able to select from payment schedules linked to their catalog and not all active payment schedules in the system, the **Only allow catalog plans** check box can be selected for one or more of the source code IDs defined to enforce that limitation.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="f3451-194">Notas adicionais</span><span class="sxs-lookup"><span data-stu-id="f3451-194">Additional notes</span></span>

<span data-ttu-id="f3451-195">Atualmente, quando uma ID de código-fonte é aplicada a uma ordem de venda no call center, ela é usada para impulsionar preços, promoções, scripts e vendas/vendas cruzadas específicas do catálogo.</span><span class="sxs-lookup"><span data-stu-id="f3451-195">Currently, when a source code ID is applied to a sales order in call center, it is used to drive prices, promotions, scripts and up-sell/cross-sell's that are catalog specific.</span></span> <span data-ttu-id="f3451-196">O sistema não proibirá nem impedirá que um produto que não esteja no catálogo seja solicitado na ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f3451-196">The system will not prohibit or prevent a product that is not in the catalog from being ordered on the sales order.</span></span> <span data-ttu-id="f3451-197">Se for pedido um item que não faz parte do catálogo, primeiro o sistema usará o **Grupo de preços** definido no canal de call center (**Varejo e Comércio** \> **Canais** \> **Call centers** \> **Todos os call centers**) para o preço de item ou promoções.</span><span class="sxs-lookup"><span data-stu-id="f3451-197">If an item is ordered that is not part of the catalog, the system will first use the **Price group** that is defined on the call center channel (**Retail and Commerce** \> **Channels** \> **Call centers** \> **All call centers**) for item price or promotions.</span></span> <span data-ttu-id="f3451-198">Se nenhum preço de canal específico for encontrado, o preço de venda base do item será usado.</span><span class="sxs-lookup"><span data-stu-id="f3451-198">If no specific channel price is found, the base selling price of the item will be used.</span></span>