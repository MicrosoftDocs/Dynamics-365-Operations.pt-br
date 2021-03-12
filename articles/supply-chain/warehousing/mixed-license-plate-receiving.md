---
title: Recebimento de placa de licença mista
description: Este tópico descreve como usar o recebimento de placa de licença mista para registrar e criar trabalho para vários itens com um dispositivo móvel.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c4dcafa5d997bce21d37d02f87fbf604568c24e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965620"
---
# <a name="mixed-license-plate-receiving"></a><span data-ttu-id="959ed-103">Recebimento de placa de licença mista</span><span class="sxs-lookup"><span data-stu-id="959ed-103">Mixed license plate receiving</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="959ed-104">O recebimento de placa de licença mista permite criar uma placa de licença que consiste em vários itens antes de você registrar e criar trabalho de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="959ed-104">Mixed license plate receiving allows you to build a license plate consisting of multiple items before you register and create put-away work.</span></span> 

<span data-ttu-id="959ed-105">Uma placa de licença que consiste em vários itens não precisa ser dividida na doca de recebimento para que você registre cada item.</span><span class="sxs-lookup"><span data-stu-id="959ed-105">A license plate that consists of multiple items does not have to be split at the receiving dock for you to register each item.</span></span> 

<span data-ttu-id="959ed-106">Ao usar um fluxo relacionado ao item para identificar as linhas do documento de origem, você pode procurar códigos de barras no controle de item.</span><span class="sxs-lookup"><span data-stu-id="959ed-106">When using an item-related flow to identify the source document lines, you can scan bar codes on the item control.</span></span> <span data-ttu-id="959ed-107">Se o código de barras tiver uma quantidade e uma UOM (unidade de medida) configuradas nele, o item e a quantidade serão adicionados automaticamente à placa de licença mista, e você será redirecionado à tela para verificar outro item.</span><span class="sxs-lookup"><span data-stu-id="959ed-107">If the bar code has a quantity and a unit of measure (UOM) configured on it, the item and quantity will automatically be added to the mixed license plate, and you will be returned to the screen to scan another item.</span></span> <span data-ttu-id="959ed-108">Isso permite a você verificar rapidamente todos os itens sem a necessidade de uma confirmação a cada etapa.</span><span class="sxs-lookup"><span data-stu-id="959ed-108">This allows you to quickly scan all the items without having to make a confirmation at each step.</span></span> 

<span data-ttu-id="959ed-109">No fluxo para o recebimento de placa de licença mista, você pode exibir a lista de itens que já foram verificados pela placa de licença e, assim, alterar ou corrigir a quantidade de um item.</span><span class="sxs-lookup"><span data-stu-id="959ed-109">In the flow for mixed license plate receiving, you can display the list of items that are already scanned to the license plate and from here you can modify or correct the quantity of an item.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="959ed-110">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="959ed-110">Where it applies</span></span>

<span data-ttu-id="959ed-111">O recebimento de placa de licença mista é um dispositivo móvel de recebimento de fluxo para registrar e criar trabalho para várias linhas/itens ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="959ed-111">Mixed license plate receiving is a mobile device receiving flow to register and create work for multiple lines/items at the same time.</span></span> <span data-ttu-id="959ed-112">Isso é útil caso você receba placas de licença de entrada com diversos itens.</span><span class="sxs-lookup"><span data-stu-id="959ed-112">This is useful if you receive inbound license plates with multiple items.</span></span> 

## <a name="how-to-set-up-mixed-license-plate-receiving"></a><span data-ttu-id="959ed-113">Como configurar o recebimento de placa de licença mista</span><span class="sxs-lookup"><span data-stu-id="959ed-113">How to set up mixed license plate receiving</span></span>
<span data-ttu-id="959ed-114">O recebimento de placa de licença mista é configurado como um item de menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="959ed-114">Mixed license plate receiving is set up as a mobile device menu item.</span></span>

<span data-ttu-id="959ed-115">Você precisa criar um novo item de menu com o modo de trabalho que não usa o trabalho existente, e sim um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="959ed-115">You need to create a new menu item with mode work that does not use existing work and use one of the following methods:</span></span>

- <span data-ttu-id="959ed-116">Recebimento de placa de licença mista</span><span class="sxs-lookup"><span data-stu-id="959ed-116">Mixed license plate receiving</span></span>
- <span data-ttu-id="959ed-117">Recebimento e armazenamento de placa de licença mista</span><span class="sxs-lookup"><span data-stu-id="959ed-117">Mixed license plate receiving and put away</span></span>

<span data-ttu-id="959ed-118">As opções para identificar as linhas do documento de origem são: item da ordem de compra, linha da ordem de compra, ordem de devolução, item da ordem de transferência e linha da ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="959ed-118">The options to identify the source document lines are purchase order item, purchase order line, return order, transfer order item, and transfer order line.</span></span> <span data-ttu-id="959ed-119">Essas opções podem alterar a ordem de recebimento em uma única placa de licença.</span><span class="sxs-lookup"><span data-stu-id="959ed-119">These options can change the receiving order on a single license plate.</span></span> <span data-ttu-id="959ed-120">A última opção é por item de carga.</span><span class="sxs-lookup"><span data-stu-id="959ed-120">The last option is by load item.</span></span> <span data-ttu-id="959ed-121">Você pode adicionar vários itens a uma placa de licença, mas não pode alternar entre várias cargas.</span><span class="sxs-lookup"><span data-stu-id="959ed-121">You can add multiple items to a license plate, but you cannot switch between multiple loads.</span></span>
