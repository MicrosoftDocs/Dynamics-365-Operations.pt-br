---
title: Relatar como concluído para um local controlado por placa de licença no Dispositivo de ficha de trabalho
description: Este tópico descreve o processo para concluir produtos acabados em uma ordem de produção para estoque quando uma placa de licença controla o local.
author: johanhoffmann
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: cb809e596fd6bf3030bcee460838798435512b95
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572120"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="9739e-103">Relatar como concluído para um local controlado por placa de licença no Dispositivo de ficha de trabalho</span><span class="sxs-lookup"><span data-stu-id="9739e-103">Report as finished to a license plate controlled location from the Job card device</span></span> 

<span data-ttu-id="9739e-104">O processo chamado Relatar como concluído finaliza os produtos acabados em uma ordem de produção para o estoque.</span><span class="sxs-lookup"><span data-stu-id="9739e-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="9739e-105">Se o produto acabado for habilitado para os processos avançados de depósito, o produto será relatado como concluído para um local chamado de local de saída de produção.</span><span class="sxs-lookup"><span data-stu-id="9739e-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="9739e-106">Para obter informações sobre como configurar o local de saída de produção, consulte [Local de saída de produção](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="9739e-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="9739e-107">Você deve selecionar um número da placa de licença existente para concluir essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="9739e-107">You must select an existing license plate number to complete this task.</span></span> <span data-ttu-id="9739e-108">Se o local de saída de produção for configurado para ser rastreado pela placa de licença, o número da placa de licença deverá ser incluído ao relatar o local de saída de produção como concluído.</span><span class="sxs-lookup"><span data-stu-id="9739e-108">If the production output location is set up to be tracked by license plate, then a license plate number must be included when reporting the production output location as finished.</span></span> <span data-ttu-id="9739e-109">O campo **Placa de licença** fica visível no prompt **Relatar progresso** na página **Dispositivo de ficha de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="9739e-109">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="9739e-110">O campo ficará visível apenas no prompt **Relatar progresso** durante o relato da última operação da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="9739e-110">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order.</span></span> <span data-ttu-id="9739e-111">O campo será exibido somente se o item para a ordem de produção for habilitado para os processos de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="9739e-111">The field is only shown if the item for the production order is enabled for the warehouse management processes.</span></span> 
