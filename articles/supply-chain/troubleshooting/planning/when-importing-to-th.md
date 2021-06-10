---
title: Você será solicitado a salvar as configurações de cobertura do item, embora não tenha feito alterações
description: Você será solicitado a salvar as configurações de cobertura do item, embora não tenha feito alterações.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dfa974740420433af1e1b37630b22509510c91b
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049452"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a><span data-ttu-id="cb265-103">Você será solicitado a salvar as configurações de cobertura do item, embora não tenha feito alterações</span><span class="sxs-lookup"><span data-stu-id="cb265-103">You're prompted to save item coverage settings even though you made no changes</span></span>

<span data-ttu-id="cb265-104">Número da base de dados de conhecimento: 4615588</span><span class="sxs-lookup"><span data-stu-id="cb265-104">KB number: 4615588</span></span>

## <a name="symptoms"></a><span data-ttu-id="cb265-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="cb265-105">Symptoms</span></span>

<span data-ttu-id="cb265-106">Em alguns cenários, você pode receber a seguinte mensagem ao abrir a página **Cobertura de item** depois de importar itens por meio da entidade *Cobertura de item V2*:</span><span class="sxs-lookup"><span data-stu-id="cb265-106">In some scenarios, you might receive the following message when you open the **Item coverage** page after you import items through the *Item coverage V2* entity:</span></span>

> <span data-ttu-id="cb265-107">Deseja salvar suas alterações antes de fechar?</span><span class="sxs-lookup"><span data-stu-id="cb265-107">Do you want to save your changes before closing?</span></span>

<span data-ttu-id="cb265-108">Você recebe esta mensagem, embora não tenha feito nenhuma alteração.</span><span class="sxs-lookup"><span data-stu-id="cb265-108">You receive this message even though you haven't made any changes.</span></span>

## <a name="resolution"></a><span data-ttu-id="cb265-109">Resolução</span><span class="sxs-lookup"><span data-stu-id="cb265-109">Resolution</span></span>

<span data-ttu-id="cb265-110">A página **Cobertura de item** inclui uma lógica padrão complexa que pode fazer com que a mensagem seja mostrada depois que mudanças diretas foram feitas recentemente no banco de dados, como por meio de importação de entidade.</span><span class="sxs-lookup"><span data-stu-id="cb265-110">The **Item coverage** page includes complex defaulting logic that might cause the message to be shown after direct changes have recently been made in the database, such as through entity import.</span></span> <span data-ttu-id="cb265-111">Por exemplo, o campo de entidade `AREGENERALSETTINGSOVERRIDDEN` é definido como *Não*, mas você importa um arquivo que fornece valores novos ou modificados para campos como `PRODUCTCOVERAGEGROUPID` e/ou `VENDORACCOUNTNUMBER`.</span><span class="sxs-lookup"><span data-stu-id="cb265-111">For example, the `AREGENERALSETTINGSOVERRIDDEN` entity field is set to *No*, but you import a file that provides new or modified values for fields such as `PRODUCTCOVERAGEGROUPID` and/or `VENDORACCOUNTNUMBER`.</span></span> <span data-ttu-id="cb265-112">Nesse caso, como o campo `AREGENERALSETTINGSOVERRIDDEN` está definido como *Não*, os valores são automaticamente apagados dos campos quando você abre a página **Cobertura de item** pela primeira vez após a importação.</span><span class="sxs-lookup"><span data-stu-id="cb265-112">In this case, because the `AREGENERALSETTINGSOVERRIDDEN` field is set to *No*, the values are automatically cleared from the fields when you open the **Item coverage** page for the first time after the import.</span></span> <span data-ttu-id="cb265-113">Se você salvar as alterações conforme as solicitações da caixa de mensagem, elas serão armazenadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cb265-113">If you save the changes as the message box prompts, they are stored in the database.</span></span> <span data-ttu-id="cb265-114">Caso contrário, você receberá a mesma mensagem na próxima vez que abrir a página.</span><span class="sxs-lookup"><span data-stu-id="cb265-114">Otherwise, you will receive the same message the next time that you open the page.</span></span>

<span data-ttu-id="cb265-115">Para evitar esse comportamento, mas também incluir valores para campos como `PRODUCTCOVERAGEGROUPID` por meio da importação de entidade, defina `AREGENERALSETTINGSOVERRIDDEN` como *Sim* ao importar.</span><span class="sxs-lookup"><span data-stu-id="cb265-115">To prevent this behavior but also include values for fields such as `PRODUCTCOVERAGEGROUPID` through entity import, set `AREGENERALSETTINGSOVERRIDDEN` to *Yes* when you import.</span></span>
