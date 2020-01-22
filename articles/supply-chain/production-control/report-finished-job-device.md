---
title: Relatar como concluído para um local controlado por placa de licença no Dispositivo de ficha de trabalho
description: Este tópico descreve o processo para concluir produtos acabados em uma ordem de produção para estoque quando uma placa de licença controla o local.
author: johanhoffmann
manager: AnnBe
ms.date: 01/06/2020
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
ms.openlocfilehash: 63073035941cd2ef343c65364536fe76a9b71430
ms.sourcegitcommit: af36eb17b36092a3101bbfc96486b25036676558
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2020
ms.locfileid: "2935113"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="fbd06-103">Relatar como concluído para um local controlado por placa de licença no Dispositivo de ficha de trabalho</span><span class="sxs-lookup"><span data-stu-id="fbd06-103">Report as finished to a license plate controlled location from the Job card device</span></span> 

<span data-ttu-id="fbd06-104">O processo chamado Relatar como concluído finaliza os produtos acabados em uma ordem de produção para o estoque.</span><span class="sxs-lookup"><span data-stu-id="fbd06-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="fbd06-105">Se o produto acabado for habilitado para os processos avançados de depósito, o produto será relatado como concluído para um local chamado de local de saída de produção.</span><span class="sxs-lookup"><span data-stu-id="fbd06-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="fbd06-106">Para obter informações sobre como configurar o local de saída de produção, consulte [Local de saída de produção](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span><span class="sxs-lookup"><span data-stu-id="fbd06-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="fbd06-107">Se o local de saída de produção for controlado por placa de licença, será necessário fornecer uma placa de licença ao relatar como concluído.</span><span class="sxs-lookup"><span data-stu-id="fbd06-107">If the production output location is license plate controlled, then a license plate must be provided when reporting as finished.</span></span> <span data-ttu-id="fbd06-108">O campo **Placa de licença** fica visível no prompt **Relatar progresso** na página **Dispositivo de ficha de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fbd06-108">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="fbd06-109">O campo só fica visível no aviso **Progresso do relatório** quando o relatório na última operação da ordem de produção e o item da ordem de produção estiver habilitado para processos de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="fbd06-109">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order and the item for the production order is enabled for the warehouse management processes.</span></span> 

<span data-ttu-id="fbd06-110">Há duas opções para fornecer a placa de licença</span><span class="sxs-lookup"><span data-stu-id="fbd06-110">There are two options for providing the license plate</span></span>
- <span data-ttu-id="fbd06-111">O usuário está selecionando uma placa de licença existente no campo placa de licença.</span><span class="sxs-lookup"><span data-stu-id="fbd06-111">The user is selecting an existing license plate in the license plate field.</span></span>
- <span data-ttu-id="fbd06-112">A placa de licença é gerada automaticamente a partir de uma sequência numérica e por padrão para o campo da placa de licença.</span><span class="sxs-lookup"><span data-stu-id="fbd06-112">The license plate is automatically generated from a number sequence and defaulted to the license plate field.</span></span>

<span data-ttu-id="fbd06-113">A opção para que a placa de licença seja gerada automaticamente é configurada selecionando a opção **Gerar placa de licença** na página **Configurar cartão de trabalho para dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="fbd06-113">The option to have the license plate generated automatically is configured by selecting the option **Generate license plate** on the **Configure job card for devices** page.</span></span>
