---
title: Escolher o lote mais antigo em um dispositivo móvel
description: Este artigo descreve como configurar e aplicar as opções para escolher o lote mais antigo de um dispositivo móvel.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad1f2cfd029d71784d5efcc169178a791f0ae077
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885628"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a>Escolher o lote mais antigo em um dispositivo móvel

[!include [banner](../includes/banner.md)]

Você pode acessar a configuração **Escolher lote mais antigo** em um menu de dispositivo móvel, o que permite a você forçar os trabalhadores do depósito ou orientá-los a escolher o lote mais antigo do local atual.  

## <a name="where-it-applies"></a>Aplica-se a
Escolher lote mais antigo é configurado em itens de menu de dispositivo móvel e afeta a separação de lote dos itens abaixo.

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a>Como definir a configuração para Escolher lote mais antigo 
Para itens definidos de modo a usar o trabalho existente, **Escolher lote mais antigo** pode ser definido como **Nenhum**, **Avisar**, ou **Forçar** do menu do dispositivo móvel.

**Nenhum**: Os trabalhadores não receberão nenhuma mensagem e poderão escolher qualquer lote no local.

**Avisar** e **Forçar**: Uma lista de lote(s) com a data de vencimento mais antiga será exibida acima do controle de lote quando o trabalhador selecionar um lote. Se a localização for controlada por placa de licença, uma lista de placas de licença com o lote mais antigo será exibida acima do controle de placa de licença. 
-   **Avisar**: Se um trabalhador escolher uma placa de licença ou um lote que não esteja na lista exibida, o controle será cancelado e um aviso de que há um lote mais antigo a selecionar será exibido. Para poder continuar o trabalho, o trabalhador pode selecionar novamente a mesma placa de licença ou lote.  
-   **Forçar**: os trabalhadores continuarão a receber a mensagem informando que há um lote mais antigo a escolher.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]