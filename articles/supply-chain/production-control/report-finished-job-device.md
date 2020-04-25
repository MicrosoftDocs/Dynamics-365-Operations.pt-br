---
title: Relatar como concluído para um local controlado por placa de licença no Dispositivo de ficha de trabalho
description: Este tópico descreve o processo para concluir produtos acabados em uma ordem de produção para estoque quando uma placa de licença controla o local.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: f5863202facc83afb91b380ba5666334783ccbcf
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211160"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a>Relatar como concluído para um local controlado por placa de licença no Dispositivo de ficha de trabalho 

O processo chamado Relatar como concluído finaliza os produtos acabados em uma ordem de produção para o estoque. Se o produto acabado for habilitado para os processos avançados de depósito, o produto será relatado como concluído para um local chamado de local de saída de produção. Para obter informações sobre como configurar o local de saída de produção, consulte [Local de saída de produção](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).

Se o local de saída de produção for controlado por placa de licença, será necessário fornecer uma placa de licença ao relatar como concluído. O campo **Placa de licença** fica visível no prompt **Relatar progresso** na página **Dispositivo de ficha de trabalho**. O campo só fica visível no aviso **Progresso do relatório** quando o relatório na última operação da ordem de produção e o item da ordem de produção estiver habilitado para processos de gerenciamento de depósito. 

Há duas opções para fornecer a placa de licença
- O usuário está selecionando uma placa de licença existente no campo placa de licença.
- A placa de licença é gerada automaticamente a partir de uma sequência numérica e por padrão para o campo da placa de licença.

A opção para que a placa de licença seja gerada automaticamente é configurada selecionando a opção **Gerar placa de licença** na página **Configurar cartão de trabalho para dispositivos**.
