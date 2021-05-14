---
title: Verificar a qualidade de mercadorias
description: Este tópico descreve como processar ordens de qualidade.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec67e7864db12178c0f3cfe8b93d510a46e8a0d4
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956125"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="fd9ad-103">Verificar a qualidade de mercadorias</span><span class="sxs-lookup"><span data-stu-id="fd9ad-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fd9ad-104">Este tópico descreve como processar ordens de qualidade.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-104">This topic describes how to process quality orders.</span></span> <span data-ttu-id="fd9ad-105">As inspeções de qualidade costumam ser realizadas por um vendedor de qualidade.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-105">Quality inspections are typically done by a quality clerk.</span></span>

<span data-ttu-id="fd9ad-106">Se os dados de demonstração padrão forem instalados, você poderá usá-los para concluir os procedimentos deste tópico.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-106">If the standard demo data is installed, you can use it to complete the procedures in this topic.</span></span> <span data-ttu-id="fd9ad-107">Para usar os dados de demonstração, selecione a entidade legal *USMF* antes de começar.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-107">To use the demo data, select the *USMF* legal entity before you begin.</span></span> <span data-ttu-id="fd9ad-108">Você deve confirmar a ordem de compra *000016* e lançar um recebimento de produto.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-108">You must then confirm purchase order *000016* and post a product receipt.</span></span> <span data-ttu-id="fd9ad-109">Uma ordem de qualidade é gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-109">A quality order is automatically generated.</span></span>

## <a name="step-1-select-a-quality-order"></a><span data-ttu-id="fd9ad-110">Etapa 1: Selecione uma ordem de qualidade</span><span class="sxs-lookup"><span data-stu-id="fd9ad-110">Step 1: Select a quality order</span></span>

<span data-ttu-id="fd9ad-111">Para selecionar uma ordem de qualidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-111">To select a quality order, follow these steps.</span></span>

1. <span data-ttu-id="fd9ad-112">Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="fd9ad-113">Selecione a ordem de qualidade que foi gerada antes do início deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-113">Select the quality order that was generated before you started this procedure.</span></span>

## <a name="step-2-record-test-results"></a><span data-ttu-id="fd9ad-114">Etapa 2: Registrar resultados do teste</span><span class="sxs-lookup"><span data-stu-id="fd9ad-114">Step 2: Record test results</span></span>

<span data-ttu-id="fd9ad-115">Para registrar resultados do teste, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-115">To record test results, follow these steps.</span></span>

1. <span data-ttu-id="fd9ad-116">Selecione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-116">Select **Results**.</span></span>
1. <span data-ttu-id="fd9ad-117">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-117">Select **Edit**.</span></span>
1. <span data-ttu-id="fd9ad-118">No campo **Quantidade do resultado**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-118">In the **Result quantity** field, enter a number.</span></span>
1. <span data-ttu-id="fd9ad-119">No campo **Resultado**, selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-119">In the **Outcome** field, select the desired record.</span></span> <span data-ttu-id="fd9ad-120">Neste exemplo, o resultado é baseado em um resultado predefinido.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-120">In this example, the result is based on a predefined outcome.</span></span> <span data-ttu-id="fd9ad-121">Em geral, você registrará um resultado de teste mais específico, como um tamanho ou outra dimensão.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-121">Usually, you will record a more specific test result, such as a size or other dimension.</span></span>
1. <span data-ttu-id="fd9ad-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-122">Select **Save**.</span></span>
1. <span data-ttu-id="fd9ad-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-123">Close the page.</span></span>

## <a name="step-3-validate-the-quality-order"></a><span data-ttu-id="fd9ad-124">Etapa 3: Validar a ordem de qualidade</span><span class="sxs-lookup"><span data-stu-id="fd9ad-124">Step 3: Validate the quality order</span></span>

<span data-ttu-id="fd9ad-125">Para validar a ordem de qualidade, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-125">To validate the quality order, follow these steps.</span></span>

1. <span data-ttu-id="fd9ad-126">Selecione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-126">Select **Validate**.</span></span>
1. <span data-ttu-id="fd9ad-127">No campo **Validado por**, selecione o usuário que está fazendo a inspeção.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-127">In the **Validated by** field, select the user who is doing the inspection.</span></span>
1. <span data-ttu-id="fd9ad-128">Escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-128">Select **Select**.</span></span>
1. <span data-ttu-id="fd9ad-129">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-129">Select **OK**.</span></span>
1. <span data-ttu-id="fd9ad-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fd9ad-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
