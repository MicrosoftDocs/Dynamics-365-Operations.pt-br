---
title: Ordens de cliente híbrido
description: Um ordem de cliente híbrido é uma única ordem que contém os produtos que podem ser retirados da loja pelo cliente, além produtos a serem retirados ou enviados posteriormente.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1c2105aa99e0489d7643d076e84123eec628679e
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021680"
---
# <a name="hybrid-customer-orders"></a><span data-ttu-id="71a27-103">Ordens de cliente híbrido</span><span class="sxs-lookup"><span data-stu-id="71a27-103">Hybrid customer orders</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="71a27-104">Um ordem de cliente híbrido é uma única ordem que contém os produtos que podem ser retirados da loja pelo cliente, além produtos a serem retirados ou enviados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="71a27-104">A hybrid customer order is a single order, which contains products that can be carried out of the store by the customer, as well as products that will be picked up or shipped later.</span></span>

<span data-ttu-id="71a27-105">No Commerce, você pode optar por executar todos os produtos ou os produtos selecionados para uma ordem do cliente.</span><span class="sxs-lookup"><span data-stu-id="71a27-105">In Commerce, you can select either carry out all products or carry out selected products for a customer order.</span></span> <span data-ttu-id="71a27-106">As linhas do produto que estão marcadas como executadas são faturadas automaticamente depois que a ordem é criada, o mesmo ocorre, para uma ordem que deve ser separada depois que a ordem é criada.</span><span class="sxs-lookup"><span data-stu-id="71a27-106">The product lines that are marked as carry out are automatically invoiced after the order is created, similarly this is the same for an order that is to be picked-up after the order is created.</span></span> <span data-ttu-id="71a27-107">O valor devido em ordens híbridas é determinado pela adição da porcentagem de depósito nas linhas de produtos de separação e de remessa com o valor total das linhas da execução.</span><span class="sxs-lookup"><span data-stu-id="71a27-107">The amount due on hybrid orders is determined by adding the deposit percentage on pick and ship product lines with the full amount of the carry out lines.</span></span> <span data-ttu-id="71a27-108">Para ordens híbridas, o sistema alterna entre o modo da ordem de cliente e o modo cash and carry, como segue:</span><span class="sxs-lookup"><span data-stu-id="71a27-108">For hybrid orders, the system switches between customer order mode and cash and carry mode as follows:</span></span>

- <span data-ttu-id="71a27-109">Se todos os produtos no carrinho forem definidos como **Realizar entrega**, a ordem será manipulada como uma transação Cash and Carry.</span><span class="sxs-lookup"><span data-stu-id="71a27-109">If all products in the cart are set to **Carry out delivery**, the order will be handled as a Cash and Carry transaction.</span></span>
- <span data-ttu-id="71a27-110">Se algumas ou todas as linhas forem definidas como **Separação** ou **entrega**, a ordem será tratada como transação de ordem do Cliente.</span><span class="sxs-lookup"><span data-stu-id="71a27-110">If any or all lines in the cart are set to either **Pick** or **ship delivery**, the order will be handled as a Customer order transaction.</span></span>

<span data-ttu-id="71a27-111">Se uma linha do carrinho for selecionada e a opção **Separação selecionada**, **Envio selecionado** ou **Execução selecionada** for selecionada, somente a linha específica do carrinho é definida com esse método de entrega.</span><span class="sxs-lookup"><span data-stu-id="71a27-111">If a cart line is selected and **Pick selected**, **Ship selected**, or **Carry out selected** is selected, only the specific cart line is set with that delivery method.</span></span> <span data-ttu-id="71a27-112">Nesse caso, o fluxo downstream da operação continua normalmente.</span><span class="sxs-lookup"><span data-stu-id="71a27-112">In that case, the downstream flow of the operation continues as usual.</span></span> <span data-ttu-id="71a27-113">Porém, se a opção **Separação selecionada**, **Envio selecionado** ou **Execução selecionada** for escolhida, será aberta uma nova página que listará todas as linhas do carrinho.</span><span class="sxs-lookup"><span data-stu-id="71a27-113">However, if **Pick selected**, **Ship selected**, or **Carry out selected** is selected without a cart line being selected, a new page opens that lists all the cart lines.</span></span> <span data-ttu-id="71a27-114">Nessa tela, você pode selecionar várias linhas imediatamente para definir o método de entrega.</span><span class="sxs-lookup"><span data-stu-id="71a27-114">On that screen, you can select multiple lines at once for setting the delivery method.</span></span> <span data-ttu-id="71a27-115">Quando você usar esse método para selecionar linhas qualquer método anterior de entrega que for atribuído à linha será substituído.</span><span class="sxs-lookup"><span data-stu-id="71a27-115">When you use that method for selecting lines, any previous delivery method that has been assigned to the line will be overridden.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="71a27-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="71a27-116">Additional resources</span></span>

[<span data-ttu-id="71a27-117">Ordens de cliente no Modern POS (MPOS)</span><span class="sxs-lookup"><span data-stu-id="71a27-117">Customer orders in Modern POS (MPOS)</span></span>](customer-orders-overview.md)