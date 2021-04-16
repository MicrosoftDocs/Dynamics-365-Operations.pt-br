---
title: Verificar a qualidade de mercadorias
description: Este tópico explica como processar uma ordem de qualidade.
author: perlynne
ms.date: 08/01/2019
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
ms.openlocfilehash: 47e7156e5c57d5f983564cc966b4108f1180ff8d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5825906"
---
# <a name="inspect-the-quality-of-goods"></a><span data-ttu-id="9f73d-103">Verificar a qualidade de mercadorias</span><span class="sxs-lookup"><span data-stu-id="9f73d-103">Inspect the quality of goods</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9f73d-104">Este tópico explica como processar uma ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f73d-104">This topic explains how to process a quality order.</span></span> <span data-ttu-id="9f73d-105">Você pode executar este guia na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="9f73d-105">You can run this guide in demo data company USMF.</span></span> <span data-ttu-id="9f73d-106">Antes de iniciar este procedimento de exemplo, você precisa confirmar a ordem de compra "000016" e lançar um recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="9f73d-106">Before you start this example procedure, you need to confirm purchase order "000016" and post a product receipt.</span></span> <span data-ttu-id="9f73d-107">Isso criará automaticamente uma ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f73d-107">This will automatically create a quality order.</span></span> <span data-ttu-id="9f73d-108">As inspeções de qualidade são realizadas tipicamente por um vendedor de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9f73d-108">Quality inspections are typically carried out by a quality clerk.</span></span>


## <a name="select-a-quality-order"></a><span data-ttu-id="9f73d-109">Selecione uma ordem de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f73d-109">Select a quality order</span></span>
1. <span data-ttu-id="9f73d-110">No painel de navegação, vá para **Módulos > Gerenciamento de estoque > Tarefas periódicas > Gerenciamento de qualidade > Ordens de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="9f73d-110">In the navigation pane, go to **Modules > Inventory management > Periodic tasks > Quality management > Quality orders**.</span></span>
2. <span data-ttu-id="9f73d-111">Selecione a ordem de qualidade que foi criada antes do início deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="9f73d-111">Select the quality order that was created before you started this procedure.</span></span>  

## <a name="record-test-results"></a><span data-ttu-id="9f73d-112">Registrar resultados do teste</span><span class="sxs-lookup"><span data-stu-id="9f73d-112">Record test results</span></span>
1. <span data-ttu-id="9f73d-113">Selecione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="9f73d-113">Select **Results**.</span></span>
2. <span data-ttu-id="9f73d-114">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9f73d-114">Select **Edit**.</span></span>
3. <span data-ttu-id="9f73d-115">No campo **Quantidade do resultado**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="9f73d-115">In the **Result quantity** field, enter a number.</span></span>
4. <span data-ttu-id="9f73d-116">No campo **Resultado**, selecione o registro desejado no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="9f73d-116">In the **Outcome** field, select the desired record in the drop-down menu.</span></span>  
- <span data-ttu-id="9f73d-117">Neste exemplo o resultado é baseado em um resultado predefinido.</span><span class="sxs-lookup"><span data-stu-id="9f73d-117">In this example the result is based on a pre-defined outcome.</span></span> <span data-ttu-id="9f73d-118">Normalmente você registraria um resultado de teste mais específico por exemplo, um tamanho ou outra dimensão.</span><span class="sxs-lookup"><span data-stu-id="9f73d-118">Normally you would record a more specific test result, for example a size or other dimension.</span></span>  
5. <span data-ttu-id="9f73d-119">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9f73d-119">Select **Save**.</span></span>
6. <span data-ttu-id="9f73d-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f73d-120">Close the page.</span></span>

## <a name="validate-the-quality-order"></a><span data-ttu-id="9f73d-121">Validar a ordem de qualidade</span><span class="sxs-lookup"><span data-stu-id="9f73d-121">Validate the quality order</span></span>
1. <span data-ttu-id="9f73d-122">Selecione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="9f73d-122">Select **Validate**.</span></span>
2. <span data-ttu-id="9f73d-123">No campo **Validado por**, selecione o usuário que executa a inspeção do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="9f73d-123">In the **Validated by** field, select the user performing the inspection from the drop-down menu.</span></span>  
3. <span data-ttu-id="9f73d-124">Clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="9f73d-124">Click **Select**.</span></span>
4. <span data-ttu-id="9f73d-125">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f73d-125">Select **OK**.</span></span>
5. <span data-ttu-id="9f73d-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f73d-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]