---
title: Contratos de nível de serviço
description: Em um contrato de nível de serviço, o cliente concorda com um tempo de resposta mínimo com base em quando a empresa de serviços registra o problema até que ele seja resolvido.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServicelevelagreement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cffe3a7766502dd5d888a7a99a32150967911301
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562617"
---
# <a name="service-level-agreements"></a>Contratos de nível de serviço        

[!include [banner](../includes/banner.md)]


Um contrato de nível de serviço (SLA) é um contrato entre uma empresa de serviços e um cliente de serviços. Em um SLA, o cliente concorda com um tempo de resposta mínimo que vai do momento em que a empresa de serviços registra o problema até o momento em que o problema é resolvido.

Um SLA garante que um nível padrão de serviço seja oferecido aos clientes e também deixa transparente para uma empresa de serviços quando um serviço deve ser concluído.

Pode-se criar qualquer número de SLAs para oferecer aos clientes de serviços níveis diferentes de serviço.

## <a name="create-a-service-level-agreement"></a>Criar um contrato de nível de serviço

1.  Clique em **Gerenciamento de serviços** \> **Configuração** \> **Contratos de serviço** \> **Contratos de nível de serviço**.

2.  Digite um nome para esse contrato de nível de serviço no campo **Contrato de nível de serviço**.

3.  Digite o tempo que deseja reservar a conclusão das chamadas de serviço anexadas ao contrato de nível de serviço. Selecione um calendário se você deseja basear o contrato de nível de serviço em um calendário específico.

## <a name="apply-a-service-level-agreement"></a>Aplicar um contrato de nível de serviço

O SLA é aplicado diretamente a um contrato de serviço.

As ordens de serviço criadas manualmente e anexadas a um contrato de serviço com um SLA são medidas contra esse SLA.

As ordens de serviço criadas automaticamente não são associadas a um SLA.

## <a name="apply-the-service-level-agreement-to-the-service-agreement"></a>Aplicar o contrato de nível de serviço ao contrato de serviço

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**. Selecione o contrato de serviço para o qual você deseja aplicar um SLA, e clique em **Editar** no **Painel de Ação**.

2.  No campo **Contrato de nível de serviço**, selecione o SLA que deseja atribuir.

## <a name="apply-the-service-level-agreement-to-the-service-agreement-group"></a>Aplicar o contrato de nível de serviço ao grupo de contratos de serviço

1.  Clique em **Gerenciamento de serviços** \> **Configuração** \> **Contratos de serviço** \> **Grupos de contratos de serviço**.

2.  No campo **Contrato de nível de serviço**, selecione o SLA que deseja atribuir.

## <a name="track-time-on-a-service-order-against-an-sla"></a>Rastrear tempo em uma ordem de serviço contra um SLA

Quando você cria uma nova ordem de serviço para um contrato de serviço com um SLA for atribuído, o intervalo de tempo para a entrega de serviço é iniciado, e o sistema rastreie o tempo de entrega. Além disso, você pode definir estas opções:

  - Você pode iniciar e parar o registro do tempo na ordem de serviço para registrar o tempo total gasto nas ordens de serviço.

  - Você pode monitorar a conformidade com o intervalo de tempo definido no contrato de nível de serviço.

  - Você pode definir códigos de motivo que devem ser definidos se o intervalo de tempo do contrato de nível de serviço for ultrapassado.

## <a name="see-also"></a>Consulte também

[Exibir a conformidade com contratos de nível de serviço](view-compliance-with-service-level-agreements.md)

  


