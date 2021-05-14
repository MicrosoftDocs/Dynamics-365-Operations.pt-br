---
title: Resolver problemas de operações de depósito de entrada
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com operações de depósito de entrada no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 6f6d689c596b4ec924cb50ec3bea8ce907e6dc6b
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920978"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="41201-103">Resolver problemas de operações de depósito de entrada</span><span class="sxs-lookup"><span data-stu-id="41201-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="41201-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com operações de depósito de entrada no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="41201-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="41201-105">Recebo a seguinte mensagem de erro: "A ordem de qualidade %1 foi gerada.</span><span class="sxs-lookup"><span data-stu-id="41201-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="41201-106">Não foi possível localizar o perfil do cluster. Verifique a sua configuração."</span><span class="sxs-lookup"><span data-stu-id="41201-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="41201-107">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="41201-107">Issue description</span></span>

<span data-ttu-id="41201-108">Essa mensagem de erro está relacionada a um processo de recebimento em que o gerenciamento de qualidade (QMS) está ativado.</span><span class="sxs-lookup"><span data-stu-id="41201-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="41201-109">Dependendo das configurações de seu ambiente, detalhes adicionais sobre a transação que está gerando a mensagem de erro podem ajudar a corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="41201-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="41201-110">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="41201-110">Issue resolution</span></span>

<span data-ttu-id="41201-111">Primeiro, revise a configuração de [separação de cluster](set-up-cluster-picking.md) e certifique-se de que seus perfis de cluster estejam configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="41201-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="41201-112">Você não pode usar um item de menu de dispositivo móvel para seleção de cluster, a menos que os perfis de cluster sejam configurados.</span><span class="sxs-lookup"><span data-stu-id="41201-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="41201-113">Dependendo do seu ambiente, você também pode ter que revisar outras configurações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="41201-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="41201-114">O recebimento de placas de licença mistas não funciona para nenhum código de disposição, exceto Crédito.</span><span class="sxs-lookup"><span data-stu-id="41201-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="41201-115">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="41201-115">Issue description</span></span>

<span data-ttu-id="41201-116">Quando o campo **Ação** para um código de disposição é definido como *Crédito* ou *Sucata*, você pode usar somente o item de menu [Recebimento de placa de licença mista](mixed-license-plate-receiving.md) para processar itens devolvidos.</span><span class="sxs-lookup"><span data-stu-id="41201-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="41201-117">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="41201-117">Issue resolution</span></span>

<span data-ttu-id="41201-118">A Microsoft avaliou esse problema e determinou que é uma limitação de recurso.</span><span class="sxs-lookup"><span data-stu-id="41201-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="41201-119">Atualmente, somente [códigos de disposição](../service-management/set-up-disposition-codes.md) em que o campo **Ação** é definido como *Crédito* ou *Sucata* são compatíveis para recebimento de placa de licença mista.</span><span class="sxs-lookup"><span data-stu-id="41201-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="41201-120">Quando executo a tarefa periódica Atualizar recebimentos de produtos, as ordens de compra não confirmadas são confirmadas.</span><span class="sxs-lookup"><span data-stu-id="41201-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="41201-121">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="41201-121">Issue description</span></span>

<span data-ttu-id="41201-122">Depois de executar a tarefa periódica *Atualizar recebimentos de produtos*, o sistema confirma automaticamente as ordens de compra não confirmadas com status de transação de estoque *Registrado*.</span><span class="sxs-lookup"><span data-stu-id="41201-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="41201-123">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="41201-123">Issue resolution</span></span>

<span data-ttu-id="41201-124">Um novo recurso de processamento de cargas de entrada, *Recebimento a mais de quantidade de carga*, corrige esse problema.</span><span class="sxs-lookup"><span data-stu-id="41201-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="41201-125">Para ativar esse recurso, acesse o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative os seguintes recursos (na ordem em que estão listados):</span><span class="sxs-lookup"><span data-stu-id="41201-125">To turn on this feature, go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="41201-126">Associar transações de estoque da ordem de compra com carga</span><span class="sxs-lookup"><span data-stu-id="41201-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="41201-127">Recebimento a mais de quantidade de carga</span><span class="sxs-lookup"><span data-stu-id="41201-127">Over receipt of load quantities</span></span>

<span data-ttu-id="41201-128">Para obter mais informações, consulte [Lançar quantidades de produtos registrados nas ordens de compra](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="41201-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a><span data-ttu-id="41201-129">Ao registrar as ordens de entrada, recebo a seguinte mensagem de erro: "A quantidade não é válida".</span><span class="sxs-lookup"><span data-stu-id="41201-129">When I register inbound orders, I receive the following error message: "The quantity is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="41201-130">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="41201-130">Issue description</span></span>

<span data-ttu-id="41201-131">Se o campo **Política de agrupamento de placas de licença** estiver definido como *Definido pelo usuário* para um item de menu de dispositivo móvel usado para registrar ordens de entrada, você receberá uma mensagem de erro ("A quantidade não é válida") e não poderá concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="41201-131">If the **License plate grouping policy** field is set to *User defined* for a mobile device menu item that is used to register inbound orders, you receive an error message ("The quantity is not valid"), and you can't complete the registration.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="41201-132">Causa do problema</span><span class="sxs-lookup"><span data-stu-id="41201-132">Issue cause</span></span>

<span data-ttu-id="41201-133">Quando *Definido pelo usuário* é usado como uma política de agrupamento de placas de licença, o sistema divide o estoque de entrada em chapas de licença separadas, conforme indicado pelo grupo de sequências de unidades.</span><span class="sxs-lookup"><span data-stu-id="41201-133">When *User defined* is used as a license plate grouping policy, the system splits the incoming inventory into separate license plates, as indicated by the unit sequence group.</span></span> <span data-ttu-id="41201-134">Se os números do lote ou de série forem usados para rastrear o item que está sendo recebido, as quantidades de cada número do lote ou de série deverão ser especificadas por placa de licença registrada.</span><span class="sxs-lookup"><span data-stu-id="41201-134">If batch or serial numbers are used to track the item that is being received, the quantities of each batch or serial must be specified per license plate that is registered.</span></span> <span data-ttu-id="41201-135">Se a quantidade especificada para uma placa de licença exceder a quantidade que ainda deve ser recebida para as dimensões atuais, você receberá a mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="41201-135">If the quantity that is specified for a license plate exceeds the quantity that must still be received for the current dimensions, you receive the error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="41201-136">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="41201-136">Issue resolution</span></span>

<span data-ttu-id="41201-137">Ao registrar um item usando um item de menu de dispositivo móvel no qual o campo **Política de agrupamento de chapas de licença** está definido como *Definido pelo usuário*, o sistema poderá exigir que você confirme ou insira números de placas de licença, números do lote ou números de série.</span><span class="sxs-lookup"><span data-stu-id="41201-137">When you register an item by using a mobile device menu item where the **License plate grouping policy** field is set to *User defined*, the system might require that you confirm or enter license plate numbers, batch numbers, or serial numbers.</span></span>

<span data-ttu-id="41201-138">Na página de confirmação da placa de licença, o sistema mostrará a quantidade alocada para a placa de licença atual.</span><span class="sxs-lookup"><span data-stu-id="41201-138">On the license plate confirmation page, the system will show the quantity that is allocated for the current license plate.</span></span> <span data-ttu-id="41201-139">Nas páginas de confirmação do número de série ou do lote, o sistema mostrará a quantidade que ainda deve ser recebida na placa de licença atual.</span><span class="sxs-lookup"><span data-stu-id="41201-139">On the batch or serial confirmation pages, the system will show the quantity that must still be received on the current license plate.</span></span> <span data-ttu-id="41201-140">Ele também incluirá um campo no qual é possível inserir a quantidade a ser registrada para essa combinação de placa de licença e número do lote ou de série.</span><span class="sxs-lookup"><span data-stu-id="41201-140">It will also include a field where you can enter the quantity to register for that combination of license plate and batch or serial number.</span></span> <span data-ttu-id="41201-141">Nesse caso, verifique se a quantidade que está sendo registrada para a placa de licença não excede a quantidade que ainda deverá ser recebida.</span><span class="sxs-lookup"><span data-stu-id="41201-141">In this case, make sure that the quantity that is being registered for the license plate doesn't exceed the quantity that must still be received.</span></span>

<span data-ttu-id="41201-142">Como alternativa, se muitas placas de licença estiverem sendo geradas no registro de ordem de entrada, o valor do campo **Política de agrupamento da chapa de licença** poderá ser alterado para *Agrupamento de placas de licença*, um novo grupo de sequências de unidades poderá ser atribuído ao item, ou a opção **Agrupamento de placas de licença** para o grupo de sequências de unidades poderá ser desativada.</span><span class="sxs-lookup"><span data-stu-id="41201-142">Alternatively, if too many license plates are being generated on inbound order registration, the value of the **License plate grouping policy** field can be changed to *License plate grouping*, a new unit sequence group can be assigned to the item, or the **License plate grouping** option for the unit sequence group can be inactivated.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
