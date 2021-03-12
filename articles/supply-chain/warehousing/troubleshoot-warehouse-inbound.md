---
title: Resolver problemas de operações de depósito de entrada
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com operações de depósito de entrada no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 71f590ec01b757de298bd2692fdbdb0324843376
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970230"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="55f30-103">Resolver problemas de operações de depósito de entrada</span><span class="sxs-lookup"><span data-stu-id="55f30-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="55f30-104">Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com operações de depósito de entrada no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="55f30-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="55f30-105">Recebo a seguinte mensagem de erro: "A ordem de qualidade %1 foi gerada.</span><span class="sxs-lookup"><span data-stu-id="55f30-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="55f30-106">Não foi possível localizar o perfil do cluster. Verifique a sua configuração."</span><span class="sxs-lookup"><span data-stu-id="55f30-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="55f30-107">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="55f30-107">Issue description</span></span>

<span data-ttu-id="55f30-108">Essa mensagem de erro está relacionada a um processo de recebimento em que o gerenciamento de qualidade (QMS) está ativado.</span><span class="sxs-lookup"><span data-stu-id="55f30-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="55f30-109">Dependendo das configurações de seu ambiente, detalhes adicionais sobre a transação que está gerando a mensagem de erro podem ajudar a corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="55f30-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="55f30-110">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="55f30-110">Issue resolution</span></span>

<span data-ttu-id="55f30-111">Primeiro, revise a configuração de [separação de cluster](set-up-cluster-picking.md) e certifique-se de que seus perfis de cluster estejam configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="55f30-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="55f30-112">Você não pode usar um item de menu de dispositivo móvel para seleção de cluster, a menos que os perfis de cluster sejam configurados.</span><span class="sxs-lookup"><span data-stu-id="55f30-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="55f30-113">Dependendo do seu ambiente, você também pode ter que revisar outras configurações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="55f30-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="55f30-114">O recebimento de placas de licença mistas não funciona para nenhum código de disposição, exceto Crédito.</span><span class="sxs-lookup"><span data-stu-id="55f30-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="55f30-115">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="55f30-115">Issue description</span></span>

<span data-ttu-id="55f30-116">Quando o campo **Ação** para um código de disposição é definido como *Crédito* ou *Sucata*, você pode usar somente o item de menu [Recebimento de placa de licença mista](mixed-license-plate-receiving.md) para processar itens devolvidos.</span><span class="sxs-lookup"><span data-stu-id="55f30-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="55f30-117">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="55f30-117">Issue resolution</span></span>

<span data-ttu-id="55f30-118">A Microsoft avaliou esse problema e determinou que é uma limitação de recurso.</span><span class="sxs-lookup"><span data-stu-id="55f30-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="55f30-119">Atualmente, somente [códigos de disposição](../service-management/set-up-disposition-codes.md) em que o campo **Ação** é definido como *Crédito* ou *Sucata* são compatíveis para recebimento de placa de licença mista.</span><span class="sxs-lookup"><span data-stu-id="55f30-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="55f30-120">Quando executo a tarefa periódica Atualizar recebimentos de produtos, as ordens de compra não confirmadas são confirmadas.</span><span class="sxs-lookup"><span data-stu-id="55f30-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="55f30-121">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="55f30-121">Issue description</span></span>

<span data-ttu-id="55f30-122">Depois de executar a tarefa periódica *Atualizar recebimentos de produtos*, o sistema confirma automaticamente as ordens de compra não confirmadas com status de transação de estoque *Registrado*.</span><span class="sxs-lookup"><span data-stu-id="55f30-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="55f30-123">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="55f30-123">Issue resolution</span></span>

<span data-ttu-id="55f30-124">Um novo recurso de processamento de cargas de entrada, *Recebimento a mais de quantidade de carga*, corrige esse problema.</span><span class="sxs-lookup"><span data-stu-id="55f30-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="55f30-125">Para ativar esse recurso, vá para [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative os seguintes recursos (na ordem em que estão listados):</span><span class="sxs-lookup"><span data-stu-id="55f30-125">To turn on this feature, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="55f30-126">Associar transações de estoque da ordem de compra com carga</span><span class="sxs-lookup"><span data-stu-id="55f30-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="55f30-127">Recebimento a mais de quantidade de carga</span><span class="sxs-lookup"><span data-stu-id="55f30-127">Over receipt of load quantities</span></span>

<span data-ttu-id="55f30-128">Para obter mais informações, consulte [Lançar quantidades de produtos registrados nas ordens de compra](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="55f30-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>
