---
title: Transmissão automática de notas fiscais eletrônicas (Brasil)
description: Use o procedimento a seguir para configurar parâmetros de email para enviar automaticamente uma Nota Fiscal eletrônica (NF-e) a um fornecedor ou um cliente após sua aprovação ou cancelamento, ou se você gerar uma carta de correção.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Brazil
ms.search.industry: Manufacturing;Distribution;Service industries
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3647d7afd883737e452db7fcea2cc99572ee8f3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183869"
---
# <a name="automatic-transmission-of-nf-e-fiscal-documents-brazil"></a><span data-ttu-id="2173b-103">Transmissão automática de notas fiscais eletrônicas (Brasil)</span><span class="sxs-lookup"><span data-stu-id="2173b-103">Automatic transmission of NF-e fiscal documents (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2173b-104">Use o procedimento a seguir para configurar parâmetros de email para enviar automaticamente uma Nota Fiscal eletrônica (NF-e) a um fornecedor ou um cliente após sua aprovação ou cancelamento, ou se você gerar uma carta de correção.</span><span class="sxs-lookup"><span data-stu-id="2173b-104">Use the following procedure to set up email parameters to automatically send a Nota Fiscal eletrônica (NF-e) to a vendor or customer after the NF-e is approved or canceled, or if you generate a correction letter.</span></span> <span data-ttu-id="2173b-105">Você pode configurar um grupo de lotes e modelos de e-mail para uma NF-e.</span><span class="sxs-lookup"><span data-stu-id="2173b-105">You can set up a batch group and email templates for an NF-e.</span></span> <span data-ttu-id="2173b-106">Você deve criar modelos de e-mail separados para uma NF-e aprovada, uma NF-e cancelada e uma carta de correção.</span><span class="sxs-lookup"><span data-stu-id="2173b-106">You must create separate email templates for an approved NF-e, a canceled NF-e, and a correction letter.</span></span> <span data-ttu-id="2173b-107">Então será possível criar um processo em lote para enviar a NF-e por email.</span><span class="sxs-lookup"><span data-stu-id="2173b-107">You can then create a batch process to send the NF-e by email.</span></span> <span data-ttu-id="2173b-108">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="2173b-108">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="2173b-109">Vá para Administração do sistema > Configuração > Grupo de lotes.</span><span class="sxs-lookup"><span data-stu-id="2173b-109">Go to System administration > Setup > Batch group.</span></span>
2. <span data-ttu-id="2173b-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2173b-110">Click New.</span></span>
3. <span data-ttu-id="2173b-111">No campo Grupo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="2173b-112">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2173b-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2173b-113">Click Save.</span></span>
6. <span data-ttu-id="2173b-114">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2173b-114">Close the page.</span></span>
7. <span data-ttu-id="2173b-115">Vá para Administração do sistema > Tarefas periódicas > Processamento de email > Lote.</span><span class="sxs-lookup"><span data-stu-id="2173b-115">Go to System administration > Periodic tasks > Email processing > Batch.</span></span>
8. <span data-ttu-id="2173b-116">Expanda a seção Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2173b-116">Expand the Run in the background section.</span></span>
9. <span data-ttu-id="2173b-117">Selecione Sim no campo Processamento de lote.</span><span class="sxs-lookup"><span data-stu-id="2173b-117">Select Yes in the Batch processing field.</span></span>
10. <span data-ttu-id="2173b-118">No campo Grupo de lotes, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-118">In the Batch group field, enter or select a value.</span></span>
11. <span data-ttu-id="2173b-119">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="2173b-119">Click Recurrence.</span></span>
12. <span data-ttu-id="2173b-120">Selecione a opção Nenhuma data de término.</span><span class="sxs-lookup"><span data-stu-id="2173b-120">Select the No end date option.</span></span>
13. <span data-ttu-id="2173b-121">No campo Contagem, insira um número.</span><span class="sxs-lookup"><span data-stu-id="2173b-121">In the Count field, enter a number.</span></span>
14. <span data-ttu-id="2173b-122">No campo Fuso horário, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="2173b-122">In the Time zone field, select an option.</span></span>
15. <span data-ttu-id="2173b-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2173b-123">Click OK.</span></span>
16. <span data-ttu-id="2173b-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2173b-124">Click OK.</span></span>
17. <span data-ttu-id="2173b-125">Vá para Administração da organização > Configuração > Modelos de email.</span><span class="sxs-lookup"><span data-stu-id="2173b-125">Go to Organization administration > Setup > Email templates.</span></span>
18. <span data-ttu-id="2173b-126">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="2173b-126">Click New.</span></span>
19. <span data-ttu-id="2173b-127">No campo ID do email, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-127">In the Email ID field, type a value.</span></span>
20. <span data-ttu-id="2173b-128">No campo Email do remetente, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-128">In the Sender email field, type a value.</span></span>
21. <span data-ttu-id="2173b-129">No campo Nome do remetente, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-129">In the Sender name field, type a value.</span></span>
22. <span data-ttu-id="2173b-130">No campo Código do idioma padrão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-130">In the Default language code field, enter or select a value.</span></span>
23. <span data-ttu-id="2173b-131">No campo Linhas ou cabeçalho, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="2173b-131">In the Lines or header field, select an option.</span></span>
24. <span data-ttu-id="2173b-132">No campo Grupo de lotes, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-132">In the Batch group field, enter or select a value.</span></span>
25. <span data-ttu-id="2173b-133">No campo Descrição de email, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-133">In the Email description field, type a value.</span></span>
26. <span data-ttu-id="2173b-134">No campo Linhas ou cabeçalho, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="2173b-134">In the Lines or header field, select an option.</span></span>
27. <span data-ttu-id="2173b-135">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2173b-135">Click Save.</span></span>
28. <span data-ttu-id="2173b-136">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="2173b-136">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="2173b-137">No campo Assunto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-137">In the Subject field, type a value.</span></span>
30. <span data-ttu-id="2173b-138">No campo Idioma, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-138">In the Language field, enter or select a value.</span></span>
31. <span data-ttu-id="2173b-139">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="2173b-139">Click Edit.</span></span>
32. <span data-ttu-id="2173b-140">No campo WritableContent, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-140">In the WritableContent field, type a value.</span></span>
33. <span data-ttu-id="2173b-141">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2173b-141">Click OK.</span></span>
34. <span data-ttu-id="2173b-142">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2173b-142">Click Save.</span></span>
35. <span data-ttu-id="2173b-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2173b-143">Close the page.</span></span>
36. <span data-ttu-id="2173b-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2173b-144">Close the page.</span></span>
37. <span data-ttu-id="2173b-145">Vá para Administração da organização > Organizações > Estabelecimentos fiscais > Estabelecimentos fiscais.</span><span class="sxs-lookup"><span data-stu-id="2173b-145">Go to Organization administration > Organizations > Fiscal establishments > Fiscal establishments.</span></span>
38. <span data-ttu-id="2173b-146">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="2173b-146">Use the Quick Filter to find records.</span></span> <span data-ttu-id="2173b-147">Por exemplo, filtre no campo ID do estabelecimento fiscal com um valor de "Matriz".</span><span class="sxs-lookup"><span data-stu-id="2173b-147">For example, filter on the Fiscal establishment ID field with a value of 'Matriz'.</span></span>
39. <span data-ttu-id="2173b-148">Expanda a seção NF-e e NFC-e federal.</span><span class="sxs-lookup"><span data-stu-id="2173b-148">Expand the NF-e and NFC-e federal section.</span></span>
40. <span data-ttu-id="2173b-149">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="2173b-149">Click Edit.</span></span>
41. <span data-ttu-id="2173b-150">No campo NF-e aprovada, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2173b-150">In the Approved NF-e field, enter or select a value.</span></span>
42. <span data-ttu-id="2173b-151">Selecione Sim no campo Anexar DANFE em PDF ao email.</span><span class="sxs-lookup"><span data-stu-id="2173b-151">Select Yes in the Attach the DANFE as PDF file to  email field.</span></span>
43. <span data-ttu-id="2173b-152">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="2173b-152">Click Save.</span></span>
44. <span data-ttu-id="2173b-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2173b-153">Close the page.</span></span>
