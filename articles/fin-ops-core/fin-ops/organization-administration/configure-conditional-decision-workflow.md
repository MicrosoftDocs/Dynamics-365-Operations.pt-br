---
title: Configurar decisões condicionais em um fluxo de trabalho
description: Use os procedimentos a seguir para configurar as propriedades da decisão condicional.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a593d4e188f47b73967f0c5468f7d7c3e9f64dc8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567451"
---
# <a name="configure-conditional-decisions-in-a-workflow"></a><span data-ttu-id="9aec1-103">Configurar decisões condicionais em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="9aec1-103">Configure conditional decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9aec1-104">Use os procedimentos a seguir para configurar as propriedades da decisão condicional.</span><span class="sxs-lookup"><span data-stu-id="9aec1-104">Use the following procedure to configure the properties of a conditional decision.</span></span>

<span data-ttu-id="9aec1-105">Uma decisão condicional é um ponto em que um fluxo de trabalho se divide em duas ramificações.</span><span class="sxs-lookup"><span data-stu-id="9aec1-105">A conditional decision is a point at which a workflow divides into two branches.</span></span> <span data-ttu-id="9aec1-106">Para configurar uma decisão condicional, no editor de fluxo de trabalho, clique com o botão direito do mouse na decisão condicional e, em seguida, em **Propriedades** para abrir o formulário **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9aec1-106">To configure a conditional decision, in the workflow editor, right-click the conditional decision, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-a-decision"></a><span data-ttu-id="9aec1-107">Nomeie uma decisão</span><span class="sxs-lookup"><span data-stu-id="9aec1-107">Name a decision</span></span>

<span data-ttu-id="9aec1-108">Siga estas etapas para inserir um nome para a decisão condicional.</span><span class="sxs-lookup"><span data-stu-id="9aec1-108">Follow these steps to enter a name for a conditional decision.</span></span>

1. <span data-ttu-id="9aec1-109">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="9aec1-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="9aec1-110">No campo **Nome**, insira um nome exclusivo para a decisão condicional.</span><span class="sxs-lookup"><span data-stu-id="9aec1-110">In the **Name** field, enter a unique name for the conditional decision.</span></span>

## <a name="set-conditions"></a><span data-ttu-id="9aec1-111">Definir condições</span><span class="sxs-lookup"><span data-stu-id="9aec1-111">Set conditions</span></span>

<span data-ttu-id="9aec1-112">O sistema determina qual ramificação é usada para avaliar o documento enviado para determinar se ele atende às condições específicas.</span><span class="sxs-lookup"><span data-stu-id="9aec1-112">The system determines which branch is used by evaluating the submitted document to determine whether it meets specific conditions.</span></span>

1. <span data-ttu-id="9aec1-113">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="9aec1-113">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="9aec1-114">Clique em **Adicionar condição**.</span><span class="sxs-lookup"><span data-stu-id="9aec1-114">Click **Add condition**.</span></span>
3. <span data-ttu-id="9aec1-115">Insira uma condição.</span><span class="sxs-lookup"><span data-stu-id="9aec1-115">Enter a condition.</span></span>
4. <span data-ttu-id="9aec1-116">Insira condições adicionais, se forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="9aec1-116">Enter additional conditions, if they are required.</span></span>
5. <span data-ttu-id="9aec1-117">Para verificar se as condições inseridas foram configuradas corretamente, execute as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="9aec1-117">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="9aec1-118">Clique em **Teste** para abrir o formulário **Condição de fluxo de trabalho de teste**.</span><span class="sxs-lookup"><span data-stu-id="9aec1-118">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="9aec1-119">Selecione um registro na área **Validar condição** do formulário.</span><span class="sxs-lookup"><span data-stu-id="9aec1-119">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="9aec1-120">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="9aec1-120">Click **Test**.</span></span> <span data-ttu-id="9aec1-121">O sistema avaliará o registro para determinar se ele atende às condições definidas.</span><span class="sxs-lookup"><span data-stu-id="9aec1-121">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="9aec1-122">Clique em **OK** ou em **Cancelar** para retornar ao formulário **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9aec1-122">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]