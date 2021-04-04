---
title: Configurar o compartilhamento de dados financeiros entre empresas
description: Este procedimento mostra como configurar, habilitar, validar e resolver conflitos para compartilhar dados entre empresas.
author: aprilolson
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportRnr, DMFExecutionHistoryWorkspace, DMFExecutionHistorySummary, DMFExecutionHistoryEntities,  SysDataSharingConfiguration, SysDataSharingDiscrepencies
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 167f43224591462a4db42d041487ff8f66b02cd9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561065"
---
# <a name="configure-financial-cross-company-data-sharing"></a><span data-ttu-id="02003-103">Configurar o compartilhamento de dados financeiros entre empresas</span><span class="sxs-lookup"><span data-stu-id="02003-103">Configure financial cross-company data sharing</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="02003-104">Este procedimento mostra como configurar, habilitar, validar e resolver conflitos para compartilhar dados entre empresas.</span><span class="sxs-lookup"><span data-stu-id="02003-104">This procedure shows how to configure, enable, validate, and resolve conflicts when sharing data between companies.</span></span> <span data-ttu-id="02003-105">A empresa usa USMF e as datas financeiras que compartilham o modelo.</span><span class="sxs-lookup"><span data-stu-id="02003-105">It uses the USMF company and the Financial data sharing template.</span></span>

<span data-ttu-id="02003-106">Este guia de tarefas requer a plataforma 7.1 do Dynamics AX ou posterior.</span><span class="sxs-lookup"><span data-stu-id="02003-106">This task guide requires Dynamics AX platform 7.1 or later.</span></span>

1. <span data-ttu-id="02003-107">Vá para **Painel de navegação > Módulos > Administração do sistema > Espaços de trabalho > Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="02003-107">Go to **Navigation pane > Modules > System administration > Workspaces > Data management**.</span></span>
2. <span data-ttu-id="02003-108">Clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="02003-108">Click **Import**.</span></span>
3. <span data-ttu-id="02003-109">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="02003-109">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="02003-110">No campo **Formato de dados de origem**, selecione o tipo 'Pacote'.</span><span class="sxs-lookup"><span data-stu-id="02003-110">In the **Source data format** field, select the 'Package' type.</span></span> <span data-ttu-id="02003-111">Clique em **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="02003-111">Click **Upload**.</span></span> <span data-ttu-id="02003-112">Vá para o local do Arquivo do pacote de modelo de compartilhamento de dados financeiros e selecione este arquivo.</span><span class="sxs-lookup"><span data-stu-id="02003-112">Navigate to the location of the Financial data sharing template package file and select that file.</span></span>
5. <span data-ttu-id="02003-113">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02003-113">Click **Save**.</span></span>
6. <span data-ttu-id="02003-114">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="02003-114">In the list, mark the selected row.</span></span> <span data-ttu-id="02003-115">Selecione os dados que compartilham a diretiva que acabou de ser criada.</span><span class="sxs-lookup"><span data-stu-id="02003-115">Select the data sharing policy that was just created.</span></span>  
7. <span data-ttu-id="02003-116">Clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="02003-116">Click **Import**.</span></span>
8. <span data-ttu-id="02003-117">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="02003-117">Click **Close**.</span></span>
9. <span data-ttu-id="02003-118">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="02003-118">Refresh the page.</span></span>
10. <span data-ttu-id="02003-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="02003-119">Close the page.</span></span>
11. <span data-ttu-id="02003-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="02003-120">Close the page.</span></span>
12. <span data-ttu-id="02003-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="02003-121">Close the page.</span></span>
13. <span data-ttu-id="02003-122">Vá para **Painel de navegação > Módulos > Administração do sistema > Configuração > Configurar o compartilhamento de dados entre empresas**.</span><span class="sxs-lookup"><span data-stu-id="02003-122">Go to **Navigation pane > Modules > System administration > Setup > Configure cross-company data sharing**.</span></span>
14. <span data-ttu-id="02003-123">Na lista, localize e selecione **Dias de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="02003-123">In the list, find and select **Payment days**.</span></span>
15. <span data-ttu-id="02003-124">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="02003-124">Click **Add**.</span></span>
16. <span data-ttu-id="02003-125">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="02003-125">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="02003-126">No campo **Empresa**, digite 'USSI'.</span><span class="sxs-lookup"><span data-stu-id="02003-126">In the **Company** field, type 'USSI'.</span></span>
18. <span data-ttu-id="02003-127">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="02003-127">Click **Add**.</span></span>
19. <span data-ttu-id="02003-128">No campo **Empresa**, digite 'USMF'.</span><span class="sxs-lookup"><span data-stu-id="02003-128">In the **Company** field, type 'USMF'.</span></span>
20. <span data-ttu-id="02003-129">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02003-129">Click **Save**.</span></span>
21. <span data-ttu-id="02003-130">Clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="02003-130">Click **Enable**.</span></span>
22. <span data-ttu-id="02003-131">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="02003-131">Click **Yes**.</span></span>
23. <span data-ttu-id="02003-132">Clique em **Localizar problemas de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="02003-132">Click **Find sharing issues**.</span></span>
24. <span data-ttu-id="02003-133">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="02003-133">Click **Yes**.</span></span>
25. <span data-ttu-id="02003-134">Clique em **Atualizar valor do campo**.</span><span class="sxs-lookup"><span data-stu-id="02003-134">Click **Update field value**.</span></span>
26. <span data-ttu-id="02003-135">Clique em **Usar valor da empresa 1**.</span><span class="sxs-lookup"><span data-stu-id="02003-135">Click **Use value from company 1**.</span></span>
27. <span data-ttu-id="02003-136">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="02003-136">Refresh the page.</span></span>
28. <span data-ttu-id="02003-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="02003-137">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]