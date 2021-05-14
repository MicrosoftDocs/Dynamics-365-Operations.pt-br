---
title: Os campos de peso nas linhas de carga não correspondem aos campos de peso na carga
description: Os campos de peso nas linhas de carga não correspondem aos campos de peso na carga
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924342"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a><span data-ttu-id="33d82-103">Os campos de peso nas linhas de carga não correspondem aos campos de peso na carga</span><span class="sxs-lookup"><span data-stu-id="33d82-103">The weight fields on load lines don't match the weight fields on the load</span></span>

<span data-ttu-id="33d82-104">Códigos de erro: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span><span class="sxs-lookup"><span data-stu-id="33d82-104">Error codes: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span></span>

## <a name="symptoms"></a><span data-ttu-id="33d82-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="33d82-105">Symptoms</span></span>

<span data-ttu-id="33d82-106">O sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="33d82-106">The system shows the following error message:</span></span>

> <span data-ttu-id="33d82-107">Os campos de peso nas linhas de carga não correspondem aos campos de peso na carga %1.</span><span class="sxs-lookup"><span data-stu-id="33d82-107">The weight fields on load lines do not match the weight fields on load %1.</span></span> <span data-ttu-id="33d82-108">Execute a Verificação de consistência do peso da carga do depósito para recalcular os campos de peso.</span><span class="sxs-lookup"><span data-stu-id="33d82-108">Run the Warehouse load weight consistency check to recalculate the weight fields.</span></span>

## <a name="cause"></a><span data-ttu-id="33d82-109">Causa</span><span class="sxs-lookup"><span data-stu-id="33d82-109">Cause</span></span>

<span data-ttu-id="33d82-110">Os campos **Peso líquido** e **Peso da tara** estão definidos como *0* (zero) na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="33d82-110">The **Net weight** and **Tara weight** fields are set to *0* (zero) on the load line.</span></span> <span data-ttu-id="33d82-111">No entanto, os campos de peso não estão definidos como *0* para as medições de peso no produto.</span><span class="sxs-lookup"><span data-stu-id="33d82-111">However, the weight fields aren't set to *0* for the weight measurements on the product.</span></span> <span data-ttu-id="33d82-112">Quando os campos de peso não são definidos na linha de carga, qualquer correção da quantidade na linha de carga pode causar um cálculo de peso incorreto na carga.</span><span class="sxs-lookup"><span data-stu-id="33d82-112">When weight fields aren't set on the load line, any corrections of the quantity on the load line might cause incorrect weight calculation on the load.</span></span> <span data-ttu-id="33d82-113">Esse problema pode ocorrer se os pesos no produto tiverem sido alterados desde que a linha de carga foi criada.</span><span class="sxs-lookup"><span data-stu-id="33d82-113">This issue might occur if the weights on the product have been changed since the load line was created.</span></span>

## <a name="resolution"></a><span data-ttu-id="33d82-114">Resolução</span><span class="sxs-lookup"><span data-stu-id="33d82-114">Resolution</span></span>

<span data-ttu-id="33d82-115">Por padrão, quando uma linha de carga é criada, os campos de peso do produto são inseridos nela.</span><span class="sxs-lookup"><span data-stu-id="33d82-115">By default, when a load line is created, the weight fields from the product are entered on it.</span></span> <span data-ttu-id="33d82-116">Se o peso for zero, você poderá recalculá-lo usando a funcionalidade *Verificação de consistência do peso da carga do depósito*.</span><span class="sxs-lookup"><span data-stu-id="33d82-116">If the weight is zero, you can recalculate it by using the *Warehouse load weight consistency check* functionality.</span></span>

1. <span data-ttu-id="33d82-117">Vá para **Administração do sistema \> Tarefas periódicas \> Banco de dados \> Verificação de consistência**.</span><span class="sxs-lookup"><span data-stu-id="33d82-117">Go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="33d82-118">Na caixa de diálogo **Verificação de consistência**, defina o campo **Módulo** como *Gerenciamento de depósito*.</span><span class="sxs-lookup"><span data-stu-id="33d82-118">In the **Consistency check** dialog box, set the **Module** field to *Warehouse management*.</span></span>
1. <span data-ttu-id="33d82-119">Defina o campo **Verificar/Corrigir** como *Corrigir erro*.</span><span class="sxs-lookup"><span data-stu-id="33d82-119">Set the **Check/Fix** field to *Fix error*.</span></span>
1. <span data-ttu-id="33d82-120">Na lista de caixas de seleção, marque a caixa de seleção **Verificação de consistência do peso da carga do depósito** e verifique se somente a linha dessa caixa de seleção está realçada.</span><span class="sxs-lookup"><span data-stu-id="33d82-120">In the checkbox list, select the **Warehouse load weight consistency check** checkbox, and make sure that only the row for this checkbox is highlighted.</span></span>
1. <span data-ttu-id="33d82-121">Na parte superior da lista de caixas de seleção, selecione o botão de reticências (**...**) e, em seguida, selecione **Caixa de diálogo** no menu.</span><span class="sxs-lookup"><span data-stu-id="33d82-121">At the top of the checkbox list, select the ellipsis button (**...**), and then select **Dialog** on the menu.</span></span>
1. <span data-ttu-id="33d82-122">Na caixa de diálogo **Verificação de consistência do peso da carga do depósito**, defina os campos a seguir para especificar os critérios de execução da verificação de consistência:</span><span class="sxs-lookup"><span data-stu-id="33d82-122">In the **Warehouse load weight consistency check** dialog box, set the following fields to specify the criteria that the consistency check should run for:</span></span>

    - <span data-ttu-id="33d82-123">**ID de carga:** especifique uma ID de carga.</span><span class="sxs-lookup"><span data-stu-id="33d82-123">**Load ID:** Specify a load ID.</span></span> <span data-ttu-id="33d82-124">Deixe este campo em branco para verificar todas as IDs de carga.</span><span class="sxs-lookup"><span data-stu-id="33d82-124">Leave this blank to check all load IDs.</span></span>
    - <span data-ttu-id="33d82-125">**Número de item:** especifique um número de item.</span><span class="sxs-lookup"><span data-stu-id="33d82-125">**Item number:** Specify an item number.</span></span> <span data-ttu-id="33d82-126">Deixe este campo em branco para verificar todos os itens.</span><span class="sxs-lookup"><span data-stu-id="33d82-126">Leave this blank to check all items.</span></span>
    - <span data-ttu-id="33d82-127">**Sempre recalcular o peso nas cargas:** defina esta opção como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="33d82-127">**Always recalculate weight on loads:** Set this option to *Yes*.</span></span>
    - <span data-ttu-id="33d82-128">**Permitir substituição de peso nas linhas de carga:** defina esta opção como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="33d82-128">**Allow overwrite of weight on load lines:** Set this option to *Yes*.</span></span>

1. <span data-ttu-id="33d82-129">Selecione **OK** para fechar a caixa de diálogo **Verificação de consistência do peso da carga do depósito**.</span><span class="sxs-lookup"><span data-stu-id="33d82-129">Select **OK** to close the **Warehouse load weight consistency check** dialog box.</span></span>
1. <span data-ttu-id="33d82-130">Selecione o botão de reticências e, em seguida, selecione **Executar** no menu.</span><span class="sxs-lookup"><span data-stu-id="33d82-130">Select the ellipsis button, and then select **Execute** on the menu.</span></span>

<span data-ttu-id="33d82-131">O peso é recalculado com base nos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="33d82-131">The weight is recalculated based on the criteria that you specified.</span></span> <span data-ttu-id="33d82-132">Selecione o link **Detalhes da mensagem** para exibir o resultado da verificação de consistência.</span><span class="sxs-lookup"><span data-stu-id="33d82-132">Select the **Message details** link to view the result of the consistency check.</span></span>
