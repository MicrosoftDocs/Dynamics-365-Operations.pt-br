---
title: Configurar eventos de vida futuros
description: Este artigo descreve como agendar eventos futuros da vida no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2cb3ca03e0d9d7e5423a405f1eb0372e1c19588d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227975"
---
# <a name="configure-future-life-events"></a>Configurar eventos de vida futuros

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

Você pode agendar eventos de vida futuros no Dynamics 365 Human Resources.

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Eventos de vida futuros**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | Data do evento de vida | O sistema processa todos os eventos durante o período de inscrição que ocorrem até a data atual. |
   | Evento de vida registrado | Data e hora em que o evento de vida é registrado. |
   | Tipo de log | Mostra se a ação é uma das seguintes:</br></br>- **Atualização** – uma alteração em um registro existente que está rastreando eventos de vida</br></br>- **Inserção** – a criação de um registro de evento de vida |
   | ID do tipo de evento de vida | O identificador exclusivo do tipo de evento de vida. |
   | Tipo de evento de vida | Um catalisador para atualizar a inscrição em benefícios de um funcionário. Para mais detalhes, consulte a seção "Gatilhos de eventos da vida". |
   | Status | Se o evento de vida foi processado ou não. |
   | Linha | O número da linha do evento de vida futuro. |

4. Selecione **Salvar**. 

Você pode excluir eventos da vida futuros. Se um evento da vida futura processada for excluído, o registro futuro também será excluído. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
