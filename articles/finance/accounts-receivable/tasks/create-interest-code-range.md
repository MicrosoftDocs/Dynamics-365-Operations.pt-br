---
title: Criar um código de juros com um intervalo
description: Os códigos de juros podem ser configurados para calcular os valores diferentes de juros com base em um intervalo de valores.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Interest, CustInterestRange
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d684eedd5b40ee9775ab779c243d05cdc6e01f58
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188846"
---
# <a name="create-an-interest-code-with-a-range"></a><span data-ttu-id="c5d94-103">Criar um código de juros com um intervalo</span><span class="sxs-lookup"><span data-stu-id="c5d94-103">Create an interest code with a range</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c5d94-104">Os códigos de juros podem ser configurados para calcular os valores diferentes de juros com base em um intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="c5d94-104">Interest codes can be set up to calculate different interest amounts based on a range of values.</span></span> <span data-ttu-id="c5d94-105">Este procedimento mostrará como adicionar um código de juros e adicionar um intervalo a ele.</span><span class="sxs-lookup"><span data-stu-id="c5d94-105">This procedure will show you how to add an interest code and add a range to it.</span></span>

1. <span data-ttu-id="c5d94-106">Vá para Crédito e cobranças > Juros > Configurar códigos de juros.</span><span class="sxs-lookup"><span data-stu-id="c5d94-106">Go to Credit and collections > Interest > Set up interest codes.</span></span>
2. <span data-ttu-id="c5d94-107">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c5d94-107">Click New.</span></span>
3. <span data-ttu-id="c5d94-108">No campo Código de juros, insira o nome do código de juros.</span><span class="sxs-lookup"><span data-stu-id="c5d94-108">In the Interest code field, enter the name of the interest code.</span></span>
4. <span data-ttu-id="c5d94-109">No campo Descrição, insira uma descrição para o código de juros.</span><span class="sxs-lookup"><span data-stu-id="c5d94-109">In the Description field, enter a description for the interest code.</span></span>
5. <span data-ttu-id="c5d94-110">Selecione Mês.</span><span class="sxs-lookup"><span data-stu-id="c5d94-110">Select Month.</span></span>
6. <span data-ttu-id="c5d94-111">Expandir a seção Ganhos.</span><span class="sxs-lookup"><span data-stu-id="c5d94-111">Expand the Earnings section.</span></span>
7. <span data-ttu-id="c5d94-112">Expanda a seção Ganhos pela moeda.</span><span class="sxs-lookup"><span data-stu-id="c5d94-112">Expand the Earnings by currency section.</span></span>
8. <span data-ttu-id="c5d94-113">No campo Conta de lançamento contábil, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="c5d94-113">In the Ledger posting account field, specify the desired values.</span></span>
9. <span data-ttu-id="c5d94-114">No campo Juros por intervalo, selecione 'Meses'.</span><span class="sxs-lookup"><span data-stu-id="c5d94-114">In the Interest by range field, select 'Months'.</span></span>
10. <span data-ttu-id="c5d94-115">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c5d94-115">Click Add.</span></span>
11. <span data-ttu-id="c5d94-116">No campo Descrição, insira uma descrição para esta moeda e intervalo.</span><span class="sxs-lookup"><span data-stu-id="c5d94-116">In the Description field, enter a description for this currency and range.</span></span>
12. <span data-ttu-id="c5d94-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c5d94-117">Click Save.</span></span>
13. <span data-ttu-id="c5d94-118">Clique em Intervalos.</span><span class="sxs-lookup"><span data-stu-id="c5d94-118">Click Ranges.</span></span>
14. <span data-ttu-id="c5d94-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c5d94-119">Click New.</span></span>
15. <span data-ttu-id="c5d94-120">Insira o valor De como 0 e insira a porcentagem de juros para o mês que será usado para calcular os juros.</span><span class="sxs-lookup"><span data-stu-id="c5d94-120">Enter the From value as 0 and then enter the interest percent per month that will be used to calculate the interest.</span></span> <span data-ttu-id="c5d94-121">Para nosso exemplo, será 1,5.</span><span class="sxs-lookup"><span data-stu-id="c5d94-121">For our example, it is 1.5.</span></span>
16. <span data-ttu-id="c5d94-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c5d94-122">Click New.</span></span>
17. <span data-ttu-id="c5d94-123">Insira o próximo valor De como 4, que é o primeiro mês que você estará calculando um novo valor de juros.</span><span class="sxs-lookup"><span data-stu-id="c5d94-123">Enter the next From value as 4, which is the first month that you will be calculating a new interest amount.</span></span>
18. <span data-ttu-id="c5d94-124">Insira a porcentagem de juros por mês que será usada para calcular os juros a partir do mês 4.</span><span class="sxs-lookup"><span data-stu-id="c5d94-124">Enter the interest percent per month that will be used to calculate the interest starting in month 4.</span></span> <span data-ttu-id="c5d94-125">Para este exemplo, será 2,0.</span><span class="sxs-lookup"><span data-stu-id="c5d94-125">For this example, it is 2.0.</span></span>
19. <span data-ttu-id="c5d94-126">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c5d94-126">Click New.</span></span>
20. <span data-ttu-id="c5d94-127">Insira o próximo valor De como 7, que é o próximo mês que você estará calculando um novo valor de juros.</span><span class="sxs-lookup"><span data-stu-id="c5d94-127">Enter the next From value as 7, which is the next month that you will be calculating a new interest amount.</span></span>
21. <span data-ttu-id="c5d94-128">Insira a porcentagem de juros por mês que será usada para calcular os juros a partir do mês 7.</span><span class="sxs-lookup"><span data-stu-id="c5d94-128">Enter the interest percent per month that will be used to calculate the interest starting in month 7.</span></span> <span data-ttu-id="c5d94-129">Para este exemplo, será 2,5.</span><span class="sxs-lookup"><span data-stu-id="c5d94-129">For this example, it is 2.5.</span></span>
22. <span data-ttu-id="c5d94-130">Clique em Fechar para finalizar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c5d94-130">Click Close to complete the setup.</span></span>
