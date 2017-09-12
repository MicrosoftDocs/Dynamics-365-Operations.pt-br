--- 
title: Configurar texto de origem da nota fiscal (Brasil)
description: "Você pode anexar textos de nota fiscal à ordem de venda, ordem de compra ou fatura de texto livre."
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2e040ebe28874f0eefc248bcba8a498781e7f30f
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-fiscal-document-source-text-brazil"></a><span data-ttu-id="d4a62-103">Configurar texto de origem da nota fiscal (Brasil)</span><span class="sxs-lookup"><span data-stu-id="d4a62-103">Set up fiscal document source text (Brazil)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4a62-104">Você pode anexar textos de nota fiscal à ordem de venda, ordem de compra ou fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="d4a62-104">You can attach fiscal document texts to a sales order, purchase order, or free text invoice.</span></span> <span data-ttu-id="d4a62-105">Os textos de nota fiscal anexados à ordem de venda, ordem de compra ou fatura de texto livre são impressos na nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d4a62-105">The fiscal document texts that are attached to the sales order, purchase order, or free text invoice are printed on the fiscal document.</span></span> <span data-ttu-id="d4a62-106">Os textos de nota fiscal fornecem informações adicionais sobre os impostos e as leis que são aplicados à nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d4a62-106">The fiscal document texts provide additional information about the taxes and laws that are applied to the fiscal document.</span></span> <span data-ttu-id="d4a62-107">Também é possível incluir os espaços reservados no texto de origem da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d4a62-107">You can also include placeholders in the fiscal document source text.</span></span> <span data-ttu-id="d4a62-108">Os espaços reservados serão substituídos pelo texto predefinido quando você lança o documento fiscal ao qual o texto da nota fiscal está anexado.</span><span class="sxs-lookup"><span data-stu-id="d4a62-108">The placeholders are replaced by predefined text when you post the fiscal document that the fiscal document text is attached to.</span></span> <span data-ttu-id="d4a62-109">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="d4a62-109">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="d4a62-110">Vá para Administração da organização > Gerenciamento de documentos > Tipos de documento.</span><span class="sxs-lookup"><span data-stu-id="d4a62-110">Go to Organization administration > Document management > Document types.</span></span>
2. <span data-ttu-id="d4a62-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d4a62-111">Click New.</span></span>
3. <span data-ttu-id="d4a62-112">No campo Tipo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d4a62-112">In the Type field, type a value.</span></span>
4. <span data-ttu-id="d4a62-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d4a62-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d4a62-114">Selecione Nota simples.</span><span class="sxs-lookup"><span data-stu-id="d4a62-114">Select Simple note.</span></span>
6. <span data-ttu-id="d4a62-115">Selecione Banco de Dados.</span><span class="sxs-lookup"><span data-stu-id="d4a62-115">Select Database.</span></span>
7. <span data-ttu-id="d4a62-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d4a62-116">Click Save.</span></span>
8. <span data-ttu-id="d4a62-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d4a62-117">Close the page.</span></span>
9. <span data-ttu-id="d4a62-118">Vá para Administração da organização > Configuração > Parâmetros brasileiros.</span><span class="sxs-lookup"><span data-stu-id="d4a62-118">Go to Organization administration > Setup > Brazilian parameters.</span></span>
10. <span data-ttu-id="d4a62-119">Clique na guia Nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d4a62-119">Click the Fiscal document tab.</span></span>
11. <span data-ttu-id="d4a62-120">No campo Tipo de documento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d4a62-120">In the Document type field, enter or select a value.</span></span>
12. <span data-ttu-id="d4a62-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d4a62-121">Click Save.</span></span>
13. <span data-ttu-id="d4a62-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d4a62-122">Close the page.</span></span>
14. <span data-ttu-id="d4a62-123">Vá para Administração da organização > Configuração > Textos de origem da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d4a62-123">Go to Organization administration > Setup > Fiscal document source texts.</span></span>
15. <span data-ttu-id="d4a62-124">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d4a62-124">Click New.</span></span>
16. <span data-ttu-id="d4a62-125">No campo Texto da nota fiscal, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d4a62-125">In the Fiscal document text field, type a value.</span></span>
17. <span data-ttu-id="d4a62-126">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d4a62-126">In the Description field, type a value.</span></span>
18. <span data-ttu-id="d4a62-127">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d4a62-127">In the Text field, type a value.</span></span>
19. <span data-ttu-id="d4a62-128">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d4a62-128">Click Save.</span></span>
20. <span data-ttu-id="d4a62-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d4a62-129">Close the page.</span></span>


