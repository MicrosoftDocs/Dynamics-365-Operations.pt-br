---
title: Confirmação de produto para a separação do cluster
description: Este tópico descreve como você configura a verificação do item com a separação do cluster.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 530129ba6877c68475217d3a035775e25930cd07
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808861"
---
# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="71dfe-103">Confirmação de produto para a separação do cluster</span><span class="sxs-lookup"><span data-stu-id="71dfe-103">Product confirmation for cluster picking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71dfe-104">A separação do cluster permite que você escolha itens para várias ordens simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="71dfe-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="71dfe-105">Quando a separação do cluster é aplicada, confirmação do item é importante para verificar os itens adicionados aos clusters.</span><span class="sxs-lookup"><span data-stu-id="71dfe-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="71dfe-106">Você pode verificar os itens na separação do cluster durante o processo de separação do cluster.</span><span class="sxs-lookup"><span data-stu-id="71dfe-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="71dfe-107">Aplica-se a</span><span class="sxs-lookup"><span data-stu-id="71dfe-107">Where it applies</span></span>

<span data-ttu-id="71dfe-108">A verificação do item da separação do cluster funciona da mesma maneira que quando você verifica itens em processos de separação não cluster.</span><span class="sxs-lookup"><span data-stu-id="71dfe-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="71dfe-109">A configuração é baseada na configuração de código de barras de produto.</span><span class="sxs-lookup"><span data-stu-id="71dfe-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="71dfe-110">Configurar verificação do item com separação de cluster</span><span class="sxs-lookup"><span data-stu-id="71dfe-110">Set up item verification with cluster picking</span></span>

1. <span data-ttu-id="71dfe-111">No item de menu do dispositivo móvel, abra o formulário de configuração para a confirmação de trabalho: **Gerenciamento de depósito** > **Gerenciamento de depósito** > **Configuração** > **Dispositivo móvel** > **Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="71dfe-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
1. <span data-ttu-id="71dfe-112">Do item de menu de dispositivo móvel, abra a **Configuração de confirmação de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="71dfe-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

|        <span data-ttu-id="71dfe-113">Opção</span><span class="sxs-lookup"><span data-stu-id="71dfe-113">Option</span></span>        |                                    <span data-ttu-id="71dfe-114">descrição</span><span class="sxs-lookup"><span data-stu-id="71dfe-114">Description</span></span>                                    |
|----------------------|-----------------------------------------------------------------------------------|
| <span data-ttu-id="71dfe-115">Confirmação do produto</span><span class="sxs-lookup"><span data-stu-id="71dfe-115">Product confirmation</span></span> | <span data-ttu-id="71dfe-116">Permite a você verificar cada peça de estoque do dispositivo móvel quando examinado.</span><span class="sxs-lookup"><span data-stu-id="71dfe-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]