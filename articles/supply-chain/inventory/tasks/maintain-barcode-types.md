---
title: Manter tipos de código de barras
description: Este procedimento mostra como configurar a definição de um novo código de barras que pode ser usado como parte do relatório da lista de separação.
author: perlynne
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 979726a1d094146b546bbc6d31963367de2c59f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422442"
---
# <a name="maintain-barcode-types"></a><span data-ttu-id="787e2-103">Manter tipos de código de barras</span><span class="sxs-lookup"><span data-stu-id="787e2-103">Maintain barcode types</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="787e2-104">Este procedimento mostra como configurar a definição de um novo código de barras que pode ser usado como parte do relatório da lista de separação.</span><span class="sxs-lookup"><span data-stu-id="787e2-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="787e2-105">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="787e2-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="787e2-106">Se você estiver usando USMF você pode usar os valores de exemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="787e2-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="787e2-107">Essas tarefas normalmente seriam realizadas por um gerente do depósito.</span><span class="sxs-lookup"><span data-stu-id="787e2-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="787e2-108">Vá para Códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="787e2-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="787e2-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="787e2-109">Click New.</span></span>
3. <span data-ttu-id="787e2-110">No campo Configuração de código de barras, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="787e2-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="787e2-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="787e2-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="787e2-112">No campo Tipo de código de barras, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="787e2-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="787e2-113">Se você estiver usando USMF, você pode selecionar 'Código 39'.</span><span class="sxs-lookup"><span data-stu-id="787e2-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="787e2-114">No campo Tamanho, insira um número.</span><span class="sxs-lookup"><span data-stu-id="787e2-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="787e2-115">No campo Comprimento máximo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="787e2-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="787e2-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="787e2-116">Click Save.</span></span>
9. <span data-ttu-id="787e2-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="787e2-117">Close the page.</span></span>
10. <span data-ttu-id="787e2-118">Vá para Parâmetros de gerenciamento de estoque e depósito.</span><span class="sxs-lookup"><span data-stu-id="787e2-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="787e2-119">No campo Configuração de código de barras, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="787e2-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="787e2-120">Selecione a configuração de código de barras que você criou antes, mas esteja ciente de que o formato do código de barras deve corresponder ao formato do identificador exclusivo para o tipo de registro usado no processo.</span><span class="sxs-lookup"><span data-stu-id="787e2-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="787e2-121">Por exemplo, para roteiros de separação, o formato do código de barras deve corresponder ao formato da referência do roteiro de separação, que normalmente é uma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="787e2-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="787e2-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="787e2-122">Click Save.</span></span>
13. <span data-ttu-id="787e2-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="787e2-123">Close the page.</span></span>

