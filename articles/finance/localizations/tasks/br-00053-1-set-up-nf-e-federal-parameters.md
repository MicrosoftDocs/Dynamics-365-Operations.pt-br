---
title: Configurar parâmetros federais de NF-e (Brasil)
description: É possível configurar serviços de Web da Nota Fiscal eletrônica (NF-e), códigos de rejeição e esquemas para gerar uma NF-e.
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
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d05077433bcdbc0ee0754169da40a38c200f9450
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183871"
---
# <a name="set-up-nf-e-federal-parameters-brazil"></a><span data-ttu-id="71d00-103">Configurar parâmetros federais de NF-e (Brasil)</span><span class="sxs-lookup"><span data-stu-id="71d00-103">Set up NF-e federal parameters (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="71d00-104">É possível configurar serviços de Web da Nota Fiscal eletrônica (NF-e), códigos de rejeição e esquemas para gerar uma NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-104">You can set up Nota Fiscal eletrônica (NF-e) web services, rejection codes, and schemas to generate an NF-e.</span></span> <span data-ttu-id="71d00-105">Após gerar uma NF-e, mensagens XML são geradas e enviadas para a Secretaria da Fazenda (SEFAZ).</span><span class="sxs-lookup"><span data-stu-id="71d00-105">After you generate an NF-e, XML messages are generated and submitted to the Secretaria da Fazenda (SEFAZ).</span></span> <span data-ttu-id="71d00-106">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="71d00-106">This task uses the BRMF demo company.</span></span>



1. <span data-ttu-id="71d00-107">Vá para Administração da organização > Organizações > Notas fiscais eletrônicas > Parâmetros federais de NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-107">Go to Organization administration > Organizations > Electronic fiscal documents > NF-e federal parameters.</span></span>
2. <span data-ttu-id="71d00-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-108">Click New.</span></span>
    * <span data-ttu-id="71d00-109">Uma autoridade de imposto deve ser criada por estado.</span><span class="sxs-lookup"><span data-stu-id="71d00-109">One tax authority must be created per state.</span></span>  
3. <span data-ttu-id="71d00-110">No campo Autoridade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-110">In the Authority field, type a value.</span></span>
4. <span data-ttu-id="71d00-111">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="71d00-112">Marque a caixa de seleção Ignorar acentos.</span><span class="sxs-lookup"><span data-stu-id="71d00-112">Select the Ignore accents check box.</span></span>
6. <span data-ttu-id="71d00-113">Marque a caixa de seleção Cancelar como Evento.</span><span class="sxs-lookup"><span data-stu-id="71d00-113">Select the Cancel as Event check box.</span></span>
    * <span data-ttu-id="71d00-114">Essa opção está de acordo com o cancelamento da NF-e em eventos, em veze de um arquivo de cancelamento XML específico.</span><span class="sxs-lookup"><span data-stu-id="71d00-114">This option complies with the cancellation of NF-e through events instead of a specific XML cancellation file.</span></span>  
7. <span data-ttu-id="71d00-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="71d00-115">Click Save.</span></span>
8. <span data-ttu-id="71d00-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-116">Click New.</span></span>
9. <span data-ttu-id="71d00-117">No campo Ambiente, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-117">In the Environment field, select an option.</span></span>
10. <span data-ttu-id="71d00-118">Selecione o serviço da Web para autorização de NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-118">Select the web service for NF-e authorization.</span></span>
11. <span data-ttu-id="71d00-119">No campo Versão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-119">In the Version field, type a value.</span></span>
12. <span data-ttu-id="71d00-120">No campo Endereço na Internet, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-120">In the Internet address field, type a value.</span></span>
13. <span data-ttu-id="71d00-121">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-121">Click New.</span></span>
14. <span data-ttu-id="71d00-122">No campo Ambiente, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-122">In the Environment field, select an option.</span></span>
15. <span data-ttu-id="71d00-123">Selecione o serviço da Web para descarte de NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-123">Select the web service for NF-e discard.</span></span>
16. <span data-ttu-id="71d00-124">No campo Versão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-124">In the Version field, type a value.</span></span>
17. <span data-ttu-id="71d00-125">No campo Endereço na Internet, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-125">In the Internet address field, type a value.</span></span>
18. <span data-ttu-id="71d00-126">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-126">Click New.</span></span>
19. <span data-ttu-id="71d00-127">No campo Ambiente, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-127">In the Environment field, select an option.</span></span>
20. <span data-ttu-id="71d00-128">Selecione o serviço da Web para Consultas de NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-128">Select the web service for NF-e inquiries.</span></span>
21. <span data-ttu-id="71d00-129">No campo Versão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-129">In the Version field, type a value.</span></span>
22. <span data-ttu-id="71d00-130">No campo Endereço na Internet, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-130">In the Internet address field, type a value.</span></span>
23. <span data-ttu-id="71d00-131">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-131">Click New.</span></span>
24. <span data-ttu-id="71d00-132">No campo Ambiente, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-132">In the Environment field, select an option.</span></span>
25. <span data-ttu-id="71d00-133">Selecione o serviço da Web para devoluções de NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-133">Select the web service for NF-e authorization returns.</span></span>
26. <span data-ttu-id="71d00-134">No campo Versão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-134">In the Version field, type a value.</span></span>
27. <span data-ttu-id="71d00-135">No campo Endereço na Internet, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-135">In the Internet address field, type a value.</span></span>
28. <span data-ttu-id="71d00-136">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-136">Click New.</span></span>
29. <span data-ttu-id="71d00-137">No campo Ambiente, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-137">In the Environment field, select an option.</span></span>
30. <span data-ttu-id="71d00-138">Selecione o serviço da Web para eventos de NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-138">Select the web service for NF-e events.</span></span>
31. <span data-ttu-id="71d00-139">No campo Versão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-139">In the Version field, type a value.</span></span>
32. <span data-ttu-id="71d00-140">No campo Endereço na Internet, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-140">In the Internet address field, type a value.</span></span>
33. <span data-ttu-id="71d00-141">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-141">Click New.</span></span>
34. <span data-ttu-id="71d00-142">No campo Ambiente, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-142">In the Environment field, select an option.</span></span>
35. <span data-ttu-id="71d00-143">Selecione o serviço da Web para consultas de status de serviço de NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-143">Select the web service for NF-e service status inquiries.</span></span>
36. <span data-ttu-id="71d00-144">No campo Versão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-144">In the Version field, type a value.</span></span>
37. <span data-ttu-id="71d00-145">No campo Endereço na Internet, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-145">In the Internet address field, type a value.</span></span>
38. <span data-ttu-id="71d00-146">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="71d00-146">Click Save.</span></span>
39. <span data-ttu-id="71d00-147">Clique na guia Códigos de rejeição.</span><span class="sxs-lookup"><span data-stu-id="71d00-147">Click the Rejection codes tab.</span></span>
40. <span data-ttu-id="71d00-148">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-148">Click New.</span></span>
    * <span data-ttu-id="71d00-149">Insira os códigos de rejeição listados no guia oficial da NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-149">Enter the rejection codes that are listed in the official NF-e guide.</span></span>  
41. <span data-ttu-id="71d00-150">No campo código de rejeição de NF-e, insira o código de rejeição do guia oficial de NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-150">In the NF-e rejection code field, enter the rejection code from the official NF-e guide.</span></span>
42. <span data-ttu-id="71d00-151">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-151">In the Description field, type a value.</span></span>
43. <span data-ttu-id="71d00-152">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="71d00-152">In the list, mark the selected row.</span></span>
44. <span data-ttu-id="71d00-153">No campo Tipo de mensagem, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-153">In the Message type field, select an option.</span></span>
45. <span data-ttu-id="71d00-154">No campo Status do documento fiscal, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-154">In the Fiscal document status field, select an option.</span></span>
    * <span data-ttu-id="71d00-155">Insira o status de nota fiscal que deve ser definido quando o código de rejeição for inserido.</span><span class="sxs-lookup"><span data-stu-id="71d00-155">Enter the fiscal document status that must be set when the rejection code is entered.</span></span>  
46. <span data-ttu-id="71d00-156">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="71d00-156">Click Save.</span></span>
47. <span data-ttu-id="71d00-157">Clique na guia Esquemas.</span><span class="sxs-lookup"><span data-stu-id="71d00-157">Click the Schemas tab.</span></span>
48. <span data-ttu-id="71d00-158">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-158">Click New.</span></span>
    * <span data-ttu-id="71d00-159">Quando aplicável, insira o caminho de arquivo XSD que será usado para validar o XML da NF-e.</span><span class="sxs-lookup"><span data-stu-id="71d00-159">When applicable, enter the path of the XSD file that will be used to validate the NF-e XML.</span></span>  
49. <span data-ttu-id="71d00-160">No campo A versão do recurso de NF-e, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-160">In the The version of the NF-e feature field, select an option.</span></span>
50. <span data-ttu-id="71d00-161">No campo Esquema, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-161">In the Schema field, type a value.</span></span>
51. <span data-ttu-id="71d00-162">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-162">Click New.</span></span>
52. <span data-ttu-id="71d00-163">No campo Tipo de esquema, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-163">In the Schema type field, select an option.</span></span>
53. <span data-ttu-id="71d00-164">No campo A versão do recurso de NF-e, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-164">In the The version of the NF-e feature field, select an option.</span></span>
54. <span data-ttu-id="71d00-165">No campo Esquema, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-165">In the Schema field, type a value.</span></span>
55. <span data-ttu-id="71d00-166">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-166">Click New.</span></span>
56. <span data-ttu-id="71d00-167">No campo Tipo de esquema, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-167">In the Schema type field, select an option.</span></span>
57. <span data-ttu-id="71d00-168">No campo A versão do recurso de NF-e, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-168">In the The version of the NF-e feature field, select an option.</span></span>
58. <span data-ttu-id="71d00-169">No campo Esquema, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-169">In the Schema field, type a value.</span></span>
59. <span data-ttu-id="71d00-170">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="71d00-170">Click New.</span></span>
60. <span data-ttu-id="71d00-171">No campo Tipo de esquema, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-171">In the Schema type field, select an option.</span></span>
61. <span data-ttu-id="71d00-172">No campo A versão do recurso de NF-e, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="71d00-172">In the The version of the NF-e feature field, select an option.</span></span>
62. <span data-ttu-id="71d00-173">No campo Esquema, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="71d00-173">In the Schema field, type a value.</span></span>
63. <span data-ttu-id="71d00-174">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="71d00-174">Click Save.</span></span>
64. <span data-ttu-id="71d00-175">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="71d00-175">Close the page.</span></span>
65. <span data-ttu-id="71d00-176">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="71d00-176">Click Save.</span></span>

