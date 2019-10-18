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
ms.openlocfilehash: 35ad27a6b8a52bfd086fbe4fc57b1681ff88fd5b
ms.sourcegitcommit: 58db26b7edf02e7c33aaaf1c934e3263aa74b01f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/11/2019
ms.locfileid: "1995133"
---
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Relatar como concluído para um local controlado por placa de licença no Dispositivo de ficha de trabalho 

O processo chamado Relatar como concluído finaliza os produtos acabados em uma ordem de produção para o estoque. Se o produto acabado for habilitado para os processos avançados de depósito, o produto será relatado como concluído para um local chamado de local de saída de produção. Para obter informações sobre como configurar o local de saída de produção, consulte [Local de saída de produção](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

Você deve selecionar um número da placa de licença existente para concluir essa tarefa. Se o local de saída de produção for configurado para ser rastreado pela placa de licença, o número da placa de licença deverá ser incluído ao relatar o local de saída de produção como concluído. O campo **Placa de licença** fica visível no prompt **Relatar progresso** na página **Dispositivo de ficha de trabalho**. O campo ficará visível apenas no prompt **Relatar progresso** durante o relato da última operação da ordem de produção. O campo será exibido somente se o item para a ordem de produção for habilitado para os processos de gerenciamento de depósito. 
