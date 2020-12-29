---
title: Cancelar operação de ordem no PDV
description: Este tópico explica recursos disponíveis para aprimorar as páginas de cancelamento de ordens no PDV.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 42b11ff16757d633b868dfdf248341193a44378f
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665289"
---
# <a name="recall-order-operation-in-pos"></a><span data-ttu-id="37b48-103">Cancelar operação de ordem no PDV</span><span class="sxs-lookup"><span data-stu-id="37b48-103">Recall order operation in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="37b48-104">A operação **Cancelar ordem** no ponto de venda (PDV) do Commerce oferece recursos atualizados de pesquisa e filtragem de ordens e informações específicas da ordem.</span><span class="sxs-lookup"><span data-stu-id="37b48-104">The **Recall order** operation in the Commerce point of sale (POS) provides updated order search and filtering features and order-specific information.</span></span> <span data-ttu-id="37b48-105">Este recurso está disponível nas versões 10.0.15 e posterior do Commerce.</span><span class="sxs-lookup"><span data-stu-id="37b48-105">This feature is available in Commerce versions 10.0.15 and later.</span></span>

<span data-ttu-id="37b48-106">Para habilitar essa funcionalidade, ative a **Operação Cancelar ordem aprimorada no PDV** no espaço de trabalho **Gerenciamento de recursos** do Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="37b48-106">To enable this functionality, turn the **Improved Recall order operation in POS** feature on in **Feature management** workspace in Commerce headquarters.</span></span> <span data-ttu-id="37b48-107">Depois de habilitar o recurso, será recomendável atualizar os [layouts de tela](pos-screen-layouts.md) no PDV para aproveitar alguns dos recursos alterados.</span><span class="sxs-lookup"><span data-stu-id="37b48-107">After you enable the feature, consider updating your [screen layouts](pos-screen-layouts.md) in POS to take advantage of some of the changed  capabilities.</span></span>

<span data-ttu-id="37b48-108">A configuração do botão da operação **Cancelar ordem** permite que as organizações implantem a operação com uma exibição predefinida.</span><span class="sxs-lookup"><span data-stu-id="37b48-108">The configuration of the **Recall order** operation button allows organizations to deploy the operation with a pre-defined display.</span></span>

![Configuração da grade de botões](media/recallorderbuttongrid.png)

<span data-ttu-id="37b48-110">As opções de vídeo são as seguintes.</span><span class="sxs-lookup"><span data-stu-id="37b48-110">The display options are as follows.</span></span>
- <span data-ttu-id="37b48-111">**Nenhum** – essa opção implanta a operação sem nenhum vídeo específico.</span><span class="sxs-lookup"><span data-stu-id="37b48-111">**None** – This option deploys the operation with no specific display.</span></span> <span data-ttu-id="37b48-112">Quando um usuário abre a operação com essa configuração, ele será solicitado a procurar e encontrar ordens ou escolher um filtro de ordem predefinido.</span><span class="sxs-lookup"><span data-stu-id="37b48-112">When a user opens the operation with this configuration, they will be prompted to search and find orders or choose from a pre-defined order filter.</span></span>
- <span data-ttu-id="37b48-113">**Ordens a serem atendidas** – quando um usuário inicia a operação, uma consulta será executada automaticamente para pesquisar e exibir uma lista de ordens a serem atendidas pela loja.</span><span class="sxs-lookup"><span data-stu-id="37b48-113">**Orders to fulfill** – When a user launches the operation, a query will run automatically to search and display a list of orders that are to be fulfilled by the store.</span></span> <span data-ttu-id="37b48-114">Essas ordens são configuradas para remessa de armazenamento ou entrega em armazenamento, e as linhas dessas ordens ainda não foram retiradas nem empacotadas.</span><span class="sxs-lookup"><span data-stu-id="37b48-114">These orders are configured for in-store pickup or store shipment and the lines of these orders have not yet been picked or packed.</span></span>
- <span data-ttu-id="37b48-115">**Ordens a serem retiradas** – quando um usuário inicia a operação, uma consulta será executada automaticamente para pesquisar e exibir uma lista de ordens a serem configuradas para retira na loja atual do usuário.</span><span class="sxs-lookup"><span data-stu-id="37b48-115">**Orders to pick up** – When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for in-store pickup at the user's current store.</span></span>
- <span data-ttu-id="37b48-116">**Ordens a serem remetidas** – quando um usuário inicia a operação, uma consulta será executada automaticamente para pesquisar e exibir uma lista de ordens a serem configuradas para remessa da loja atual do usuário.</span><span class="sxs-lookup"><span data-stu-id="37b48-116">**Orders to ship** - When a user launches the operation, a query will run automatically to search and display a list of orders that are configured for shipment from the user's current store.</span></span>

<span data-ttu-id="37b48-117">Ao iniciar a operação **Cancelar ordem** no PDV, se o vídeo estiver configurado como **Nenhum**, um usuário poderá pesquisar e recuperar ordens de uma das seguintes maneiras.</span><span class="sxs-lookup"><span data-stu-id="37b48-117">When launching the **Recall order** operation from POS, if the display is configured to **None**, a user will be able to search and retrieve orders in one of the following ways.</span></span>
- <span data-ttu-id="37b48-118">Pesquisar códigos de barras da ordem.</span><span class="sxs-lookup"><span data-stu-id="37b48-118">Scan order barcodes.</span></span> <span data-ttu-id="37b48-119">Isso pesquisará os campos número da ordem, referência do canal e ID do recibo para conciliações.</span><span class="sxs-lookup"><span data-stu-id="37b48-119">This will search order number, channel reference, and receipt ID fields for matches.</span></span>
- <span data-ttu-id="37b48-120">Selecione o ícone de **Pesquisar ordens** ou **Pesquisar e filtrar** na AppBar para usar o mecanismo de filtragem para localizar ordens que atendam aos critérios do filtro.</span><span class="sxs-lookup"><span data-stu-id="37b48-120">Select **Search orders** or **Search and filter** icon on the AppBar to use the filtering mechanism to locate orders that meet the filter criteria.</span></span>
- <span data-ttu-id="37b48-121">Escolha em um filtro predefinido do menu suspenso **Mostrar Ordens** (ordens a serem atendidas, ordens a serem retiradas ou ordens a serem remetidas).</span><span class="sxs-lookup"><span data-stu-id="37b48-121">Choose from a pre-defined filter from the **Show Orders** drop-down menu (orders to fulfill, orders to pick up, or orders to ship).</span></span>

![RecallOrderMainMenu](media/recallordermain.png)

<span data-ttu-id="37b48-123">Depois que os critérios de pesquisa forem aplicados, o aplicativo exibirá uma lista de ordens de venda conciliadas.</span><span class="sxs-lookup"><span data-stu-id="37b48-123">After search criteria are applied, the application will display a list of matching sales orders.</span></span>

![RecallOrderDetail](media/orderrecalldetail.png)

<span data-ttu-id="37b48-125">Um usuário pode selecionar uma ordem na lista para exibir detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="37b48-125">A user can select an order on the list to view additional details.</span></span> <span data-ttu-id="37b48-126">O painel de informações, no lado direito da tela, exibe especificações sobre a ordem selecionada, incluindo detalhes da linha da ordem, detalhes de entrega e detalhes de preenchimento.</span><span class="sxs-lookup"><span data-stu-id="37b48-126">The information panel on the right side of the screen displays specifics on the selected order, including order line details, delivery details, and fulfillment details.</span></span>

<span data-ttu-id="37b48-127">Da AppBar, um usuário pode selecionar uma operação.</span><span class="sxs-lookup"><span data-stu-id="37b48-127">From the AppBar, a user can select an operation.</span></span> <span data-ttu-id="37b48-128">Dependendo do status da ordem, determinadas operações podem não estar habilitadas.</span><span class="sxs-lookup"><span data-stu-id="37b48-128">Depending on the status of the order, certain operations may not be enabled.</span></span>

- <span data-ttu-id="37b48-129">**Devolução** – executa uma devolução para uma ou mais faturas relacionadas à ordem do cliente selecionada.</span><span class="sxs-lookup"><span data-stu-id="37b48-129">**Return** – Executes a return for one or more invoices related to the selected customer order.</span></span>

- <span data-ttu-id="37b48-130">**Cancelar** – emita um cancelamento completo da ordem de venda selecionada.</span><span class="sxs-lookup"><span data-stu-id="37b48-130">**Cancel** – Issue a full cancellation of the selected sales order.</span></span>

- <span data-ttu-id="37b48-131">**Atender** – transfere o usuário para a página atendimento de ordem, que será filtrada previamente para a ordem selecionada.</span><span class="sxs-lookup"><span data-stu-id="37b48-131">**Fulfill** – Transfers the user to the order fulfillment page, which will be pre-filtered for the selected order.</span></span> <span data-ttu-id="37b48-132">Somente as linhas de ordem que estão abertas para preenchimento pela loja do usuário para a ordem selecionada serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="37b48-132">Only order lines that are open for fulfillment by the user's store for the selected order will be displayed.</span></span>

- <span data-ttu-id="37b48-133">**Editar** – permite que os usuários façam alterações na ordem de cliente selecionada.</span><span class="sxs-lookup"><span data-stu-id="37b48-133">**Edit** – Allows users to make changes to the selected customer order.</span></span>

- <span data-ttu-id="37b48-134">**Retirada** – lança o fluxo de retirada, que permite que o usuário escolha os produtos a serem retirados e cria a transação de venda de retirada.</span><span class="sxs-lookup"><span data-stu-id="37b48-134">**Pick up** – Launches the pickup flow, which allows the user to choose the products to be picked up and creates the pickup sales transaction.</span></span>
