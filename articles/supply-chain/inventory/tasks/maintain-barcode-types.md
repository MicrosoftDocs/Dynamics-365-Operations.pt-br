--- 
title: "Manter tipos de código de barras"
description: "Este procedimento mostra como configurar a definição de um novo código de barras que pode ser usado como parte do relatório da lista de separação."
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: a0d7092228f078f528ec1cb9ac56d7034c44bccf
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="maintain-barcode-types"></a><span data-ttu-id="0f8a6-103">Manter tipos de código de barras</span><span class="sxs-lookup"><span data-stu-id="0f8a6-103">Maintain barcode types</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0f8a6-104">Este procedimento mostra como configurar a definição de um novo código de barras que pode ser usado como parte do relatório da lista de separação.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-104">This procedure shows you how to set up a new barcode definition which can then be used as part of the picking list report.</span></span> <span data-ttu-id="0f8a6-105">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-105">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="0f8a6-106">Se você estiver usando USMF você pode usar os valores de exemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-106">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="0f8a6-107">Essas tarefas normalmente seriam realizadas por um gerente do depósito.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-107">These tasks would typically be carried out by a warehouse manager.</span></span>

1. <span data-ttu-id="0f8a6-108">Vá para Códigos de barras.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-108">Go to Bar codes.</span></span>
2. <span data-ttu-id="0f8a6-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-109">Click New.</span></span>
3. <span data-ttu-id="0f8a6-110">No campo Configuração de código de barras, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-110">In the Barcode setup field, type a value.</span></span>
4. <span data-ttu-id="0f8a6-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0f8a6-112">No campo Tipo de código de barras, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-112">In the Bar code type field, select an option.</span></span>
    * <span data-ttu-id="0f8a6-113">Se você estiver usando USMF, você pode selecionar 'Código 39'.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-113">If you're using USMF, you can select 'Code 39'.</span></span>  
6. <span data-ttu-id="0f8a6-114">No campo Tamanho, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-114">In the Size field, enter a number.</span></span>
7. <span data-ttu-id="0f8a6-115">No campo Comprimento máximo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-115">In the Maximum length field, enter a number.</span></span>
8. <span data-ttu-id="0f8a6-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-116">Click Save.</span></span>
9. <span data-ttu-id="0f8a6-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-117">Close the page.</span></span>
10. <span data-ttu-id="0f8a6-118">Vá para Parâmetros de gerenciamento de estoque e depósito.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-118">Go to Inventory and warehouse management parameters.</span></span>
11. <span data-ttu-id="0f8a6-119">No campo Configuração de código de barras, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-119">In the Barcode setup field, enter or select a value.</span></span>
    * <span data-ttu-id="0f8a6-120">Selecione a configuração de código de barras que você criou antes, mas esteja ciente de que o formato do código de barras deve corresponder ao formato do identificador exclusivo para o tipo de registro usado no processo.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-120">Select the barcode setup that you created before, but be aware that the bar code format must match the format of the unique identifier for the record type used in the process.</span></span> <span data-ttu-id="0f8a6-121">Por exemplo, para roteiros de separação, o formato do código de barras deve corresponder ao formato da referência do roteiro de separação, que normalmente é uma sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-121">For example, for picking routes, the bar code format should match the format of the picking route reference, which is typically a number sequence.</span></span>  
12. <span data-ttu-id="0f8a6-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-122">Click Save.</span></span>
13. <span data-ttu-id="0f8a6-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f8a6-123">Close the page.</span></span>


