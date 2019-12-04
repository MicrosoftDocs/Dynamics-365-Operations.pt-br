---
title: Configurar decisões condicionais em um fluxo de trabalho
description: Use os procedimentos a seguir para configurar as propriedades da decisão condicional.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 278773a5ad8be35f9b6dcd1ec0d0a35e32222bb1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176507"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a><span data-ttu-id="6364d-103">Configurar decisões condicionais em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="6364d-103">Configure conditional decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6364d-104">Use os procedimentos a seguir para configurar as propriedades da decisão condicional.</span><span class="sxs-lookup"><span data-stu-id="6364d-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="6364d-105">Uma decisão condicional é um ponto em que um fluxo de trabalho se divide em duas ramificações.</span><span class="sxs-lookup"><span data-stu-id="6364d-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="6364d-106">Para configurar uma decisão condicional, no editor de fluxo de trabalho, clique com o botão direito do mouse na decisão condicional e, em seguida, em **Propriedades** para abrir o formulário**Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6364d-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="6364d-107">Nomeie uma decisão</span><span class="sxs-lookup"><span data-stu-id="6364d-107">Name a decision</span></span>

<span data-ttu-id="6364d-108">Siga estas etapas para inserir um nome para a decisão condicional.</span><span class="sxs-lookup"><span data-stu-id="6364d-108">Follow these steps to enter a name for a conditional decision.</span></span>

1. <span data-ttu-id="6364d-109">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="6364d-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="6364d-110">No campo **Nome**, insira um nome exclusivo para a decisão condicional.</span><span class="sxs-lookup"><span data-stu-id="6364d-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="6364d-111">Definir condições</span><span class="sxs-lookup"><span data-stu-id="6364d-111">Set conditions</span></span>

<span data-ttu-id="6364d-112">O sistema determina qual ramificação é usada para avaliar o documento enviado para determinar se ele atende às condições específicas.</span><span class="sxs-lookup"><span data-stu-id="6364d-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>

1. <span data-ttu-id="6364d-113">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="6364d-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="6364d-114">Clique em **Adicionar condição**.</span><span class="sxs-lookup"><span data-stu-id="6364d-114">Click **Add condition**.</span></span>
3. <span data-ttu-id="6364d-115">Insira uma condição.</span><span class="sxs-lookup"><span data-stu-id="6364d-115">Enter a condition.</span></span>
4. <span data-ttu-id="6364d-116">Insira condições adicionais, se forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="6364d-116">Enter additional conditions, if they are required.</span></span>
5. <span data-ttu-id="6364d-117">Para verificar se as condições inseridas foram configuradas corretamente, execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="6364d-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="6364d-118">Clique em **Teste** para abrir o formulário **Condição de fluxo de trabalho de teste**.</span><span class="sxs-lookup"><span data-stu-id="6364d-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="6364d-119">Selecione um registro na área **Validar condição** do formulário.</span><span class="sxs-lookup"><span data-stu-id="6364d-119">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="6364d-120">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="6364d-120">Click **Test**.</span></span> <span data-ttu-id="6364d-121">O sistema avaliará o registro para determinar se ele atende às condições definidas.</span><span class="sxs-lookup"><span data-stu-id="6364d-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="6364d-122">Clique em **OK** ou em **Cancelar** para retornar ao formulário **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="6364d-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>