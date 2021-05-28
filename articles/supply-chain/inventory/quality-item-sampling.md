---
title: Amostragem de item de gerenciamento de qualidade
description: Este tópico descreve como configurar a amostragem de item.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae8bfd329ca0d7c30adcd93a759ee6bea7b76278
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022219"
---
# <a name="quality-management-item-sampling"></a><span data-ttu-id="ce169-103">Amostragem de item de gerenciamento de qualidade</span><span class="sxs-lookup"><span data-stu-id="ce169-103">Quality management item sampling</span></span>

<span data-ttu-id="ce169-104">A amostragem de item é usada como parte de uma associação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="ce169-104">Item sampling is used as part of a quality association.</span></span> <span data-ttu-id="ce169-105">Ela define a quantidade de estoque físico atual que deve ser inspecionada.</span><span class="sxs-lookup"><span data-stu-id="ce169-105">It defines the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="ce169-106">A amostragem pode se basear em quantidades fixas, em uma porcentagem ou em uma placa de licença completa.</span><span class="sxs-lookup"><span data-stu-id="ce169-106">Sampling can be based on fixed quantities, a percentage, or a full license plate.</span></span>

## <a name="set-up-item-sampling"></a><span data-ttu-id="ce169-107">Configurar amostragem de item</span><span class="sxs-lookup"><span data-stu-id="ce169-107">Set up item sampling</span></span>

<span data-ttu-id="ce169-108">Siga estas etapas para configurar a amostragem de item.</span><span class="sxs-lookup"><span data-stu-id="ce169-108">Follow these steps to set up item sampling.</span></span>

1. <span data-ttu-id="ce169-109">Vá para **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Amostragem de item**.</span><span class="sxs-lookup"><span data-stu-id="ce169-109">Go to **Inventory management \> Setup \> Quality control \> Item sampling**.</span></span>
1. <span data-ttu-id="ce169-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ce169-110">Select **New**.</span></span>
1. <span data-ttu-id="ce169-111">No campo **Amostragem de item**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="ce169-111">In the **Item sampling** field, enter a value.</span></span>
1. <span data-ttu-id="ce169-112">No campo **Descrição**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="ce169-112">In the **Description** field, enter a value.</span></span>
1. <span data-ttu-id="ce169-113">No campo **Valor**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ce169-113">In the **Value** field, enter a number.</span></span> <span data-ttu-id="ce169-114">Esse valor é relacionado ao valor de especificação de quantidade selecionado no campo adjacente.</span><span class="sxs-lookup"><span data-stu-id="ce169-114">This value is related to the quantity specification value that is selected in the adjacent field.</span></span>
1. <span data-ttu-id="ce169-115">Na seção **Processar**, marque a caixa de seleção **Bloqueio total** para a quantidade de linhas da ordem ou do lote inteiro ser bloqueada se um teste falhar.</span><span class="sxs-lookup"><span data-stu-id="ce169-115">In the **Process** section, select the **Full blocking** check box if the whole lot or order line quantity should be blocked if a test is failed.</span></span> <span data-ttu-id="ce169-116">Se essa caixa de seleção estiver desmarcada, somente os itens na ordem de qualidade serão bloqueados se um teste falhar.</span><span class="sxs-lookup"><span data-stu-id="ce169-116">If this check box is cleared, only the items in the quality order will be blocked if a test is failed.</span></span>
1. <span data-ttu-id="ce169-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ce169-117">Select **Save**.</span></span>
1. <span data-ttu-id="ce169-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ce169-118">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="ce169-119">*Gestão de qualidade para processos de depósito* fornece recursos adicionais de amostragem de itens.</span><span class="sxs-lookup"><span data-stu-id="ce169-119">The *Quality management for warehouse processes* feature provides additional item sampling capabilities.</span></span> <span data-ttu-id="ce169-120">Ele adiciona o conceito de *escopo de amostragem de item* e permite definir uma placa de licença completa como especificação de quantidade.</span><span class="sxs-lookup"><span data-stu-id="ce169-120">It adds the concept of *item sampling scope* and lets you define a full license plate as the quantity specification.</span></span> <span data-ttu-id="ce169-121">Se você ativou esse recurso, consulte [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="ce169-121">If you've turned on this feature, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
