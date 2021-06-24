---
title: Alterar modo de entrega no PDV
description: Este tópico descreve como configurar e usar o modo de alteração da operação de entrega no PDV.
author: hhainesms
ms.date: 03/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-20
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: fd69d82536047c06e94ba4a7e860ef54680619a4
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193122"
---
# <a name="change-mode-of-delivery-in-pos"></a><span data-ttu-id="24e3a-103">Alterar modo de entrega no PDV</span><span class="sxs-lookup"><span data-stu-id="24e3a-103">Change mode of delivery in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="24e3a-104">Este tópico descreve como configurar e usar a funcionalidade "Alterar modo de entrega" no ambiente de ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="24e3a-104">This topic describes how to set up and use the "change mode of delivery" functionality in your point of sale (POS) environment.</span></span> 

<span data-ttu-id="24e3a-105">Nas versões 10.0.10 e posteriores do Dynamics 365 Commerce, a operação **Alterar modo de entrega** (647) está disponível para ser adicionado aos layouts de tela de PDV.</span><span class="sxs-lookup"><span data-stu-id="24e3a-105">In Dynamics 365 Commerce versions 10.0.10 and later, the **Change mode of delivery** operation (647) is available to add to your POS screen layouts.</span></span>

<span data-ttu-id="24e3a-106">O modo de alteração do recurso de entrega fornece a opção de alterar o modo de entrega de uma ou mais linhas de venda configuradas pela remessa na transação do PDV.</span><span class="sxs-lookup"><span data-stu-id="24e3a-106">The change mode of delivery feature provides you with the option to change the mode of delivery for one or more shipment-configured sales lines on the POS transaction.</span></span> <span data-ttu-id="24e3a-107">Em versões anteriores do Commerce, você precisava passar por todos os fluxos de configuração **Remeter tudo** ou **Remeter selecionados**, se quiser alterar o modo de entrega em uma linha existente que foi configurada para remessa.</span><span class="sxs-lookup"><span data-stu-id="24e3a-107">In previous versions of Commerce, you had to go through the full **Ship all** or **Ship selected** configuration flows if you wanted to change the mode of delivery on an existing line that was configured for shipment.</span></span> <span data-ttu-id="24e3a-108">Esse processo foi demorado e poderia resultar em alterações acidentais na origem da entrega ou nas datas de entrega da linha.</span><span class="sxs-lookup"><span data-stu-id="24e3a-108">This process was time consuming and could result in accidental changes to the delivery origin or delivery dates for the line.</span></span> <span data-ttu-id="24e3a-109">A nova funcionalidade fornece um método alternativo para a atualização eficiente do modo de entrega nessas linhas de venda.</span><span class="sxs-lookup"><span data-stu-id="24e3a-109">The new functionality provides an alternative method for efficiently updating the mode of delivery on these sales lines.</span></span>

<span data-ttu-id="24e3a-110">Para obter mais informações sobre como adicionar uma operação a um botão na grade de botões PDV, consulte [Layouts de tela para o ponto de venda](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="24e3a-110">For more information about how to add an operation to a button on your POS button grid, see [Screen layouts for the point of sale](pos-screen-layouts.md).</span></span>

<span data-ttu-id="24e3a-111">Depois que esse recurso é configurado no PDV, quando você seleciona **Alterar modo de entrega**, será apresentado uma página de listagem que permite escolher as linhas da transação para as quais você deseja alterar o modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="24e3a-111">After this feature is configured in POS, when you select **Change mode of delivery**, you will be presented with a list page that allows you to choose the lines of the transaction that you want to change the mode of delivery for.</span></span> <span data-ttu-id="24e3a-112">Você pode escolher algumas ou todas as linhas ou sair sem fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="24e3a-112">You can choose some or all of the lines, or exit without making any changes.</span></span> <span data-ttu-id="24e3a-113">As linhas de venda que foram previamente configuradas para remessa são as únicas linhas da lista que podem ser alteradas.</span><span class="sxs-lookup"><span data-stu-id="24e3a-113">The sales lines that were previously configured for shipment are the only lines in the list that you can change.</span></span> <span data-ttu-id="24e3a-114">Se desejar alterar uma linha designada para retirada ou postergado para remessa, você deve usar as operações **Remeter tudo** ou **Remeter selecionados**.</span><span class="sxs-lookup"><span data-stu-id="24e3a-114">If you want to change a line designated for pickup or carryout to ship, you must use the **Ship all** or **Ship selected** operations.</span></span> <span data-ttu-id="24e3a-115">Por outro lado, se desejar alterar uma linha designada como remessa para uma retirada ou postergar, você deverá usar as operações **Separar todos**, **Separar selecionados**, **Executar todos** ou **Executar selecionado**.</span><span class="sxs-lookup"><span data-stu-id="24e3a-115">Conversely, if you want to change a line designated as a shipment to a pickup or carryout, you must use the  **Pickup all**, **Pickup selected**, **Carryout all**, or **Carryout selected** operations.</span></span>

<span data-ttu-id="24e3a-116">Depois de selecionar as linhas que deseja alterar, clique em **Alterar modo de entrega** para ser solicitado a selecionar as opções do modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="24e3a-116">After you select the lines that you want to change, click **Change mode of delivery** to be prompted to select the delivery mode options.</span></span> <span data-ttu-id="24e3a-117">Se você selecionou várias linhas para alterar, o PDV só exibirá os modos de entrega que foram configurados como permitidos para todos os produtos selecionados.</span><span class="sxs-lookup"><span data-stu-id="24e3a-117">If you selected multiple lines to change, POS will only display modes of delivery that have been configured as allowable for all of the selected products.</span></span> <span data-ttu-id="24e3a-118">Os modos de entrega podem ser configurados para dar suporte a produtos e endereços de entrega específicos.</span><span class="sxs-lookup"><span data-stu-id="24e3a-118">Modes of delivery can be configured to support specific products and delivery addresses.</span></span> <span data-ttu-id="24e3a-119">Se houver um modo de entrega aceitável para uma combinação de produtos e endereços, mas não for aceitável para outra combinação de produtos e endereços selecionados, o modo de entrega não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="24e3a-119">If there is a mode of delivery that is acceptable for one product and address combination but is not acceptable for another selected product and address combination, the mode of delivery is not available.</span></span> <span data-ttu-id="24e3a-120">Talvez seja necessário selecionar as linhas uma a uma e alterar o modo de entrega para cada linha separadamente se você desejar selecionar um modo de entrega para um produto que não tenha suporte por outro produto.</span><span class="sxs-lookup"><span data-stu-id="24e3a-120">You may need to select lines one by one and change the mode of delivery for each line separately if you want to select a mode of delivery for one product that is not supported by another product.</span></span>  

<span data-ttu-id="24e3a-121">Depois de selecionar o novo modo de entrega, a página de transação é exibida.</span><span class="sxs-lookup"><span data-stu-id="24e3a-121">After you select the new mode of delivery, the transaction page is displayed.</span></span> <span data-ttu-id="24e3a-122">Para revisar as seleções do novo modo de entrega, selecione a guia **Entrega** na lista de transações.</span><span class="sxs-lookup"><span data-stu-id="24e3a-122">To review your new delivery mode selections, select the **Delivery** tab on the transaction list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="24e3a-123">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="24e3a-123">Additional resources</span></span>

[<span data-ttu-id="24e3a-124">Criar ordens de call center</span><span class="sxs-lookup"><span data-stu-id="24e3a-124">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="24e3a-125">Personalizar emails transacionais por modo de entrega</span><span class="sxs-lookup"><span data-stu-id="24e3a-125">Customize transactional emails by mode of delivery</span></span>](customize-email-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]