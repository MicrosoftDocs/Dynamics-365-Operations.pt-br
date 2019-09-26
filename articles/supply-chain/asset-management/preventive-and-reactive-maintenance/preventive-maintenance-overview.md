---
title: Visão geral da manutenção preventiva
description: Este tópico explica a manutenção preventiva no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3b43c795426f40cb43962976824c44a7702d91b7
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875493"
---
# <a name="preventive-maintenance-overview"></a>Visão geral da manutenção preventiva

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Este tópico explica a manutenção preventiva no Gerenciamento de Ativos. A manutenção preventiva é uma disciplina envolvendo trabalhos de manutenção planejados, por exemplo, serviço periódico, calibração e inspeções. No **Gerenciamento de Ativos**, você pode criar planos de manutenção e configurá-los em ativos e locais funcionais. Você também pode configurar rounds de manutenção em locais funcionais. Planos de manutenção em ativos ficam ativados independentemente de onde o ativo é instalado. Os planos de manutenção e rounds de manutenção em local funcional ficam ativados para os ativos instalados no local. Em vez de configurar planos de manutenção em ativos ou configurar rounds de manutenção em locais funcionais, você pode criar rounds de manutenção que incluem vários ativos nos quais é necessário executar tipos relacionados de trabalhos de manutenção na mesma rotina de trabalho. Os rounds de manutenção criados a partir de ativos, em vez de criados em locais funcionais, indicam que você pode selecionar vários ativos para um round de manutenção, que não são instalados no mesmo local funcional.

Os planos de manutenção são usados para a manutenção preventiva e reativa em ativos individuais. Os rounds de manutenção são usados para a manutenção preventiva em um grupo ou conjunto de ativos. Os planos de manutenção e os rounds de manutenção são usados para gerar propostas de ordem de serviço. As propostas de ordem de serviço são salvas como linhas do agendamento de manutenção, que podem ser reunidas e convertidas em ordens de serviço.

A figura abaixo fornece uma visão geral do fluxo de trabalho, desde a criação de planos de manutenção e rounds de manutenção até a criação de ordens de serviço para ativos, com base nesses planos e rounds de manutenção.

![Figura 1](media/01-preventive-maintenance.png)
