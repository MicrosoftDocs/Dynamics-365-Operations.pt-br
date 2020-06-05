---
title: Confirmação de produto para a separação do cluster
description: Este tópico descreve como você configura a verificação do item com a separação do cluster.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 272c3a13b68e2b862faf20cc269ca790322b61de
ms.sourcegitcommit: 89022f39502b19c24c0997ae3a01a64b93280f42
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367282"
---
# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="5273f-103">Confirmação de produto para a separação do cluster</span><span class="sxs-lookup"><span data-stu-id="5273f-103">Product confirmation for cluster picking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5273f-104">A separação do cluster permite que você escolha itens para várias ordens simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="5273f-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="5273f-105">Quando a separação do cluster é aplicada, confirmação do item é importante para verificar os itens adicionados aos clusters.</span><span class="sxs-lookup"><span data-stu-id="5273f-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="5273f-106">Você pode verificar os itens na separação do cluster durante o processo de separação do cluster.</span><span class="sxs-lookup"><span data-stu-id="5273f-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="5273f-107">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="5273f-107">Where it applies</span></span>

<span data-ttu-id="5273f-108">A verificação do item da separação do cluster funciona da mesma maneira que quando você verifica itens em processos de separação não cluster.</span><span class="sxs-lookup"><span data-stu-id="5273f-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="5273f-109">A configuração é baseada na configuração de código de barras de produto.</span><span class="sxs-lookup"><span data-stu-id="5273f-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="5273f-110">Configurar verificação do item com separação de cluster</span><span class="sxs-lookup"><span data-stu-id="5273f-110">Set up item verification with cluster picking</span></span>

1. <span data-ttu-id="5273f-111">No item de menu do dispositivo móvel, abra o formulário de configuração para a confirmação de trabalho: **Gerenciamento de depósito** > **Gerenciamento de depósito** > **Configuração** > **Dispositivo móvel** > **Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="5273f-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
1. <span data-ttu-id="5273f-112">Do item de menu de dispositivo móvel, abra a **Configuração de confirmação de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="5273f-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

|        <span data-ttu-id="5273f-113">Opção</span><span class="sxs-lookup"><span data-stu-id="5273f-113">Option</span></span>        |                                    <span data-ttu-id="5273f-114">descrição</span><span class="sxs-lookup"><span data-stu-id="5273f-114">Description</span></span>                                    |
|----------------------|-----------------------------------------------------------------------------------|
| <span data-ttu-id="5273f-115">Confirmação do produto</span><span class="sxs-lookup"><span data-stu-id="5273f-115">Product confirmation</span></span> | <span data-ttu-id="5273f-116">Permite a você verificar cada peça de estoque do dispositivo móvel quando examinado.</span><span class="sxs-lookup"><span data-stu-id="5273f-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span> |
