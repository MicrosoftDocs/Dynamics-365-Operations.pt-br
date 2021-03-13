---
title: Visão geral de desenvolvimento
description: Este guia de desenvolvedor fornece uma referência de campos de API e personalizados. Ele também fornece informações sobre a integração com outros aplicativos.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 517febd7967350956a28dfd9d11e4042456c7da0
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115381"
---
# <a name="development-overview"></a><span data-ttu-id="a011b-104">Visão geral de desenvolvimento</span><span class="sxs-lookup"><span data-stu-id="a011b-104">Development overview</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a011b-105">Este guia de desenvolvedor fornece uma referência de campos de API e personalizados.</span><span class="sxs-lookup"><span data-stu-id="a011b-105">This Developer Guide provides an API and custom fields reference.</span></span> <span data-ttu-id="a011b-106">Ele também fornece informações sobre a integração com outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a011b-106">It also provides information on integrating with other apps.</span></span>

- [<span data-ttu-id="a011b-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="a011b-107">Overview</span></span>](hr-developer-overview.md)

- [<span data-ttu-id="a011b-108">Estender com o Power Apps e o Power Automate</span><span class="sxs-lookup"><span data-stu-id="a011b-108">Extend with Power Apps and Power Automate</span></span>](hr-developer-power-apps.md)

- [<span data-ttu-id="a011b-109">Entidades do Human Resources no Dataverse</span><span class="sxs-lookup"><span data-stu-id="a011b-109">Human Resources entities in Dataverse</span></span>](hr-developer-entities.md)

- [<span data-ttu-id="a011b-110">Campos personalizados</span><span class="sxs-lookup"><span data-stu-id="a011b-110">Custom fields</span></span>](hr-developer-custom-fields.md)

- <span data-ttu-id="a011b-111">Configurar integração de dados</span><span class="sxs-lookup"><span data-stu-id="a011b-111">Set up data integration</span></span>
  - [<span data-ttu-id="a011b-112">Escolha uma tecnologia de integração de dados</span><span class="sxs-lookup"><span data-stu-id="a011b-112">Choose a data integration technology</span></span>](hr-admin-integration-choose-technology.md)
  - [<span data-ttu-id="a011b-113">Configurar integração do Dataverse</span><span class="sxs-lookup"><span data-stu-id="a011b-113">Configure Dataverse integration</span></span>](hr-admin-integration-common-data-service.md)
  - [<span data-ttu-id="a011b-114">Configurar a integração com o Finance</span><span class="sxs-lookup"><span data-stu-id="a011b-114">Configure integration with Finance</span></span>](hr-admin-integration-finance.md)
  - [<span data-ttu-id="a011b-115">Configurar a integração com o Dayforce</span><span class="sxs-lookup"><span data-stu-id="a011b-115">Configure integration with Dayforce</span></span>](hr-admin-integration-dayforce.md)
  - [<span data-ttu-id="a011b-116">Criar um aplicativo de exportação de dados recorrente</span><span class="sxs-lookup"><span data-stu-id="a011b-116">Create a recurring data export app</span></span>](hr-admin-integration-recurring-data-export.md)
  - <span data-ttu-id="a011b-117">Integrar com o Office</span><span class="sxs-lookup"><span data-stu-id="a011b-117">Integrate with Office</span></span>
    - [<span data-ttu-id="a011b-118">Tutorial de integração do Office</span><span class="sxs-lookup"><span data-stu-id="a011b-118">Office integration tutorial</span></span>](../dev-itpro/office-integration/office-integration-tutorial.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="a011b-119">Atualizar dados da entidade no Excel</span><span class="sxs-lookup"><span data-stu-id="a011b-119">Update entity data in Excel</span></span>](../dev-itpro/office-integration/use-excel-add-in.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="a011b-120">Criar experiências de Abrir no Excel</span><span class="sxs-lookup"><span data-stu-id="a011b-120">Create Open in Excel experiences</span></span>](../dev-itpro/office-integration/office-integration-edit-excel.md?toc=/dynamics365/unified-operations/talent/toc.json)
    - [<span data-ttu-id="a011b-121">Solucionar problemas de integração do Office</span><span class="sxs-lookup"><span data-stu-id="a011b-121">Troubleshoot Office integration</span></span>](../dev-itpro/office-integration/office-integration-troubleshooting.md?toc=/dynamics365/unified-operations/talent/toc.json)

- <span data-ttu-id="a011b-122">Referência da API da Entidade</span><span class="sxs-lookup"><span data-stu-id="a011b-122">Entity API reference</span></span>
  - [<span data-ttu-id="a011b-123">Autenticação</span><span class="sxs-lookup"><span data-stu-id="a011b-123">Authentication</span></span>](hr-developer-api-authentication.md)
  - <span data-ttu-id="a011b-124">Entidades</span><span class="sxs-lookup"><span data-stu-id="a011b-124">Entities</span></span>
    - [<span data-ttu-id="a011b-125">MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="a011b-125">MyLeaveRequests</span></span>](hr-developer-api-myleaverequests-overview.md)
    - [<span data-ttu-id="a011b-126">Enviar uma solicitação de licença para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="a011b-126">Submit a leave request to workflow</span></span>](hr-developer-api-myleaverequests-submit.md)

## <a name="see-also"></a><span data-ttu-id="a011b-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a011b-127">See also</span></span>

- [<span data-ttu-id="a011b-128">Novidades ou alterações em Human Resources</span><span class="sxs-lookup"><span data-stu-id="a011b-128">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)
- [<span data-ttu-id="a011b-129">Guia do administrador</span><span class="sxs-lookup"><span data-stu-id="a011b-129">Administrator Guide</span></span>](hr-admin-overview.md)
- [<span data-ttu-id="a011b-130">Guia do usuário</span><span class="sxs-lookup"><span data-stu-id="a011b-130">User Guide</span></span>](hr-hrpro-overview.md)
