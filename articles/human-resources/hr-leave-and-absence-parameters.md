---
title: Configurar parâmetros de licença e ausência
description: Definir parâmetros de recursos humanos para licença e ausência no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2acb8502ebcab122a0a1ff21e9f5e23931026327
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008073"
---
# <a name="configure-leave-and-absence-parameters"></a><span data-ttu-id="0904e-103">Configurar parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="0904e-103">Configure leave and absence parameters</span></span>

<span data-ttu-id="0904e-104">Antes de configurar os planos de licença e ausência no Dynamics 365 Human Resources, convém verificar as configurações de todos os parâmetros de recursos humanos relacionados, incluindo:</span><span class="sxs-lookup"><span data-stu-id="0904e-104">Before you set up leave and absence plans in Dynamics 365 Human Resources, it's a good idea to verify the settings for all related human resources parameters, including:</span></span>

- <span data-ttu-id="0904e-105">Sequência numérica para solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="0904e-105">Number sequence for leave requests</span></span>
- <span data-ttu-id="0904e-106">Lei de família de licença e médica (FMLA)</span><span class="sxs-lookup"><span data-stu-id="0904e-106">Family Medical and Leave Act (FMLA) settings</span></span>
- <span data-ttu-id="0904e-107">Configurações de auto-atendimento para funcionário para solicitações de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="0904e-107">Employee self service settings for leave and absence requests</span></span>
- <span data-ttu-id="0904e-108">Parâmetros de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="0904e-108">Leave and absence parameters</span></span>

## <a name="view-and-change-human-resources-parameters"></a><span data-ttu-id="0904e-109">Exibir e alterar parâmetros de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="0904e-109">View and change human resources parameters</span></span>

1. <span data-ttu-id="0904e-110">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="0904e-110">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="0904e-111">Em **Configuração**, selecione **Parâmetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="0904e-111">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="0904e-112">Na guia **Sequências numéricas**, verifique o **Código de sequência numérica** para **ID de solicitação de licença** e faça as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="0904e-112">On the **Number sequences** tab, verify the **Number sequence code** for **Leave request ID** and change as necessary.</span></span> <span data-ttu-id="0904e-113">Esta configuração determina a sequência usada para atribuir automaticamente IDs a solicitações de licença.</span><span class="sxs-lookup"><span data-stu-id="0904e-113">This setting determines the sequence used for automatically assigning IDs to leave requests.</span></span>

4. <span data-ttu-id="0904e-114">Na guia **FMLA**, verifique as configurações de FMLA e altere conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0904e-114">On the **FMLA** tab, verify the FMLA settings and change as necessary.</span></span>

5. <span data-ttu-id="0904e-115">Na guia **Autoatendimento para funcionários**, indique se os gerentes podem inserir solicitações de licença e ausência em nome de seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="0904e-115">On the **Employee self service** tab, indicate whether managers can enter leave and absence requests on behalf of their employees.</span></span>

6. <span data-ttu-id="0904e-116">Na guia **Licença e ausência**, verifique as configurações e altere conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0904e-116">On the **Leave and absence** tab, verify the settings and change as necessary.</span></span>

7. <span data-ttu-id="0904e-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0904e-117">Select **Save**.</span></span>

## <a name="configure-calendar-parameters"></a><span data-ttu-id="0904e-118">Configure parâmetros de calendário.</span><span class="sxs-lookup"><span data-stu-id="0904e-118">Configure calendar parameters</span></span>

<span data-ttu-id="0904e-119">Se você tiver habilitado o recurso de visualização do calendário de licenças e ausências, será necessário configurar parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="0904e-119">If you have enabled the Leave and absence calendar preview feature, you need to configure additional parameters.</span></span> 

[!include [banner](includes/preview-feature-leave-absence.md)]

> [!NOTE]
> <span data-ttu-id="0904e-120">Para a versão de visualização em 3 de fevereiro de 2020, somente **Solicitações de licença pendentes** estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="0904e-120">For the preview release on February 3, 2020, only **Pending leave requests** are enabled.</span></span>

1. <span data-ttu-id="0904e-121">Na página **Licença e ausência**, selecione a guia **Links**.</span><span class="sxs-lookup"><span data-stu-id="0904e-121">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="0904e-122">Em **Configuração**, selecione **Parâmetros de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="0904e-122">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="0904e-123">Na guia **Calendário**, altere as configurações de calendário, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0904e-123">On the **Calendar** tab, change calendar settings as necessary.</span></span>

4. <span data-ttu-id="0904e-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0904e-124">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0904e-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="0904e-125">See also</span></span>

- [<span data-ttu-id="0904e-126">Visão geral de licença e ausência</span><span class="sxs-lookup"><span data-stu-id="0904e-126">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
