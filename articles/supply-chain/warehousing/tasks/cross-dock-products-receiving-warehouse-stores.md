---
title: Produtos de distribuição integrada de recebimento de depósitos para armazenamento
description: Este procedimento orienta nas etapas para criar e processar uma distribuição integrada dos produtos do local de recebimento de uma ordem de compra para uma ou várias lojas.
author: ShylaThompson
manager: tfehr
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f17585359d93030d7830eb60ce07af7c48f5d49f
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979566"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a><span data-ttu-id="b731a-103">Produtos de distribuição integrada de recebimento de depósitos para armazenamento</span><span class="sxs-lookup"><span data-stu-id="b731a-103">Cross-dock products from receiving warehouse to stores</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b731a-104">Este procedimento orienta nas etapas para criar e processar uma distribuição integrada dos produtos do local de recebimento de uma ordem de compra para uma ou várias lojas.</span><span class="sxs-lookup"><span data-stu-id="b731a-104">This procedure walks through the steps to create and process a Cross-dock to distribute products from the receiving location of a purchase order to one or many stores.</span></span> <span data-ttu-id="b731a-105">O usuário pode definir várias configurações e fazer com que o sistema sugira como distribuir os produtos ou inserir manualmente onde os produtos serão distribuídos e a quantidade distribuída em cada loja.</span><span class="sxs-lookup"><span data-stu-id="b731a-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="b731a-106">O procedimento não inclui a instalação de dados que possam ser usados na distribuição integrada, como regras de reabastecimento, hierarquias das organizações e pesos das lojas.</span><span class="sxs-lookup"><span data-stu-id="b731a-106">The procedure doesn't include setup of data that can be used in the Cross-dock, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="b731a-107">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="b731a-107">The procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="b731a-108">Ir para Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="b731a-108">Go to All purchase orders.</span></span>
2. <span data-ttu-id="b731a-109">Selecione uma ordem de compra na lista e clique no link para abrir a ordem.</span><span class="sxs-lookup"><span data-stu-id="b731a-109">Select a purchase order in the list and click the link to open the order.</span></span>
3. <span data-ttu-id="b731a-110">No Painel de Ação, clique em Varejo e Comércio.</span><span class="sxs-lookup"><span data-stu-id="b731a-110">On the Action Pane, click Retail and Commerce.</span></span>
4. <span data-ttu-id="b731a-111">Clique em Distribuição integrada.</span><span class="sxs-lookup"><span data-stu-id="b731a-111">Click Cross docking.</span></span>
5. <span data-ttu-id="b731a-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="b731a-112">Click Edit.</span></span>
    * <span data-ttu-id="b731a-113">A categoria pode ser usada para filtrar os itens na seção Linhas.</span><span class="sxs-lookup"><span data-stu-id="b731a-113">The category can be used to filter the items in the Lines section.</span></span>  
6. <span data-ttu-id="b731a-114">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b731a-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="b731a-115">No campo Quantidade de distribuição integrada, digite um valor para especificar a quantidade do produto selecionado sendo comprado que deve ser distribuída.</span><span class="sxs-lookup"><span data-stu-id="b731a-115">In the Cross docking quantity field, type a value to specify how much of the quantity being purchased of the selected product should be distributed.</span></span>
8. <span data-ttu-id="b731a-116">No campo Quantidade de distribuição integrada adicional, insira um valor para especificar as quantidades de distribuição para os produtos disponíveis que estão sendo comprados.</span><span class="sxs-lookup"><span data-stu-id="b731a-116">In the Additional cross docking quantity field, enter a value to specify the quantities to distribute for the available products being purchased</span></span>
9. <span data-ttu-id="b731a-117">No campo Distribuição, insira 'Peso da localização'.</span><span class="sxs-lookup"><span data-stu-id="b731a-117">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="b731a-118">Você pode selecionar os outros tipos para usar regras diferentes para a distribuição.</span><span class="sxs-lookup"><span data-stu-id="b731a-118">You can select the other types to use different rules for the distribution.</span></span>  
10. <span data-ttu-id="b731a-119">No campo Hierarquia de reabastecimento, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b731a-119">In the Replenishment hierarchy field, select a value.</span></span>
11. <span data-ttu-id="b731a-120">Selecione Sim no campo Respeitar classificações.</span><span class="sxs-lookup"><span data-stu-id="b731a-120">Select Yes in the Respect assortments field.</span></span>
12. <span data-ttu-id="b731a-121">Clique em Calcular quantidades.</span><span class="sxs-lookup"><span data-stu-id="b731a-121">Click Calculate quantities.</span></span>
13. <span data-ttu-id="b731a-122">Clique em Criar ordem.</span><span class="sxs-lookup"><span data-stu-id="b731a-122">Click Create order.</span></span>
14. <span data-ttu-id="b731a-123">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="b731a-123">Click Yes.</span></span>
15. <span data-ttu-id="b731a-124">Na lista, localize e selecione um depósito que tenha recebido produtos.</span><span class="sxs-lookup"><span data-stu-id="b731a-124">In the list, find and select a warehouse that received products</span></span>
16. <span data-ttu-id="b731a-125">Clicar em Ordem para exibir as ordens criadas para o depósito selecionado</span><span class="sxs-lookup"><span data-stu-id="b731a-125">Click Order to view the orders that got created for the selected warehouse</span></span>

