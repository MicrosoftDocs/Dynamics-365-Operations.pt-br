---
title: Definir pontos de premiação de fidelidade
description: Este procedimento orienta na definição de pontos de recompensa de fidelidade.
author: scott-tucker
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7f3b19513bb25d1976d2e4d0e235c347c38ccb4
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798456"
---
# <a name="define-loyalty-reward-points"></a><span data-ttu-id="babb5-103">Definir pontos de premiação de fidelidade</span><span class="sxs-lookup"><span data-stu-id="babb5-103">Define loyalty reward points</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="babb5-104">Este procedimento orienta na definição de pontos de recompensa de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="babb5-104">This procedure walks through defining loyalty reward points.</span></span> <span data-ttu-id="babb5-105">Você deve definir pontos de recompensa de fidelidade antes de configurar um programa de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="babb5-105">You should set up loyalty reward points before you set up a loyalty program.</span></span> <span data-ttu-id="babb5-106">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="babb5-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="babb5-107">Vá para Varejo e Comércio > Clientes > Fidelidade > Pontos de premiação de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="babb5-107">Go to Retail and Commerce > Customers > Loyalty > Loyalty reward points.</span></span>
2. <span data-ttu-id="babb5-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="babb5-108">Click New.</span></span>
3. <span data-ttu-id="babb5-109">No campo ID do ponto de recompensa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="babb5-109">In the Reward point ID field, type a value.</span></span>
4. <span data-ttu-id="babb5-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="babb5-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="babb5-111">No campo Tipo de ponto de recompensa, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="babb5-111">In the Reward point type field, select an option.</span></span>
    * <span data-ttu-id="babb5-112">Selecione Quantidade se deseja que os pontos de recompensa sejam arredondados para o número inteiro mais próximo.</span><span class="sxs-lookup"><span data-stu-id="babb5-112">Select Quantity if you want the reward points to be rounded to the nearest integer.</span></span> <span data-ttu-id="babb5-113">Selecione Valor se deseja que os pontos de recompensa sejam arredondados de acordo com as regras de arredondamento de moeda.</span><span class="sxs-lookup"><span data-stu-id="babb5-113">Select Amount if you want the reward points to be rounded according to currency rounding rules.</span></span> <span data-ttu-id="babb5-114">Se você selecionar Quantidade, ignore a próxima etapa deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="babb5-114">If you select Quantity, skip the next step of this procedure..</span></span>  
6. <span data-ttu-id="babb5-115">No campo Moeda, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="babb5-115">In the Currency field, type a value.</span></span>
    * <span data-ttu-id="babb5-116">Para pontos de recompensa de Tipo de valor, todos os pontos emitidos serão na moeda selecionada.</span><span class="sxs-lookup"><span data-stu-id="babb5-116">For Amount type reward points, all points issued will have the selected currency.</span></span> <span data-ttu-id="babb5-117">Para pontos de recompensa de Tipo de quantidade, esse campo não é aplicável, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="babb5-117">For Quantity type reward points, this field doesn't apply—skip this step.</span></span>  
7. <span data-ttu-id="babb5-118">Marque ou desmarque a caixa de seleção Resgatável.</span><span class="sxs-lookup"><span data-stu-id="babb5-118">Check or uncheck the Redeemable checkbox.</span></span>
8. <span data-ttu-id="babb5-119">No campo Classificação de resgate, insira um número.</span><span class="sxs-lookup"><span data-stu-id="babb5-119">In the Redeem ranking field, enter a number.</span></span>
    * <span data-ttu-id="babb5-120">A Classificação de resgate será usada quando dois ou mais pontos resgatáveis de recompensa possam ser usados para pagar por produtos.</span><span class="sxs-lookup"><span data-stu-id="babb5-120">Redeem ranking is used when two or more redeemable reward points can be used to pay for products.</span></span> <span data-ttu-id="babb5-121">Se os dois pontos de recompensa tiverem a mesma classificação de resgate, o que necessitar do número mais baixo de pontos será usado.</span><span class="sxs-lookup"><span data-stu-id="babb5-121">If the two reward points have the same redeem ranking, then the one that needs to lower number of points will be used.</span></span>  
9. <span data-ttu-id="babb5-122">No campo Valor do período de validade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="babb5-122">In the Expiration time value field, enter a number.</span></span>
    * <span data-ttu-id="babb5-123">Os pontos de recompensa expirarão no número especificado de dias, meses ou anos depois que forem emitidos.</span><span class="sxs-lookup"><span data-stu-id="babb5-123">The reward points will expire the specified number of days, months, or years after when the points are issued.</span></span> <span data-ttu-id="babb5-124">Um valor de "0" significa que os pontos de recompensa de fidelidade nunca expirarão.</span><span class="sxs-lookup"><span data-stu-id="babb5-124">A value of '0' means the loyalty reward points will never expire.</span></span>  
10. <span data-ttu-id="babb5-125">No campo Unidade do período de validade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="babb5-125">In the Expiration time unit field, select an option.</span></span>
11. <span data-ttu-id="babb5-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="babb5-126">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]