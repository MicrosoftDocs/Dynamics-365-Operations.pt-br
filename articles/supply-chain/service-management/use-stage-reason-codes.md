---
title: Usar códigos de motivo da fase
description: Os códigos de motivo são usados para indicar por que um contrato de nível de serviço (SLA) foi cancelado ou por que uma ordem de serviço excedeu o limite de tempo definido no SLA.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 74594871e9eeed86ae2914d1e5a08c0af28ab643
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422337"
---
# <a name="use-stage-reason-codes"></a>Usar códigos de motivo da fase 

[!include [banner](../includes/banner.md)]


Os códigos de motivo são usados para indicar por que um contrato de nível de serviço (SLA) foi cancelado ou por que uma ordem de serviço excedeu o limite de tempo definido no SLA.

Você também pode especificar que um código de motivo será necessário quando um SLA for cancelado, ou quando o limite de tempo exceder o tempo especificado no SLA para a ordem de serviço.

Se você especificou que um código de motivo será necessário, deverá inserir um código de motivo nas seguintes situações:

  - Quando uma ordem de serviço for movida para um estágio no qual o registro de tempo em relação ao SLA da ordem é interrompido.

  - Quando a ordem de serviço for aprovada.

  - Quando o registro de tempo for interrompido manualmente.

## <a name="set-up-reason-codes"></a>Configurar códigos de motivo

1.  Clique em **Gerenciamento de serviços** \> **Configuração** \> **Ordens de serviço** \> **Códigos de motivo da fase**.

2.  No formulário **Códigos de motivos da fase**, clique em **Novo** para criar um novo código de motivo.

3.  No campo **Código de motivo da fase**, insira um código de motivo de estágio exclusivo.

4.  No campo **Descrição**, insira uma descrição do código de motivo de estágio.

5.  Feche o formulário para salvar suas alterações.

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a>Exigir códigos de motivo quando um contrato de nível de serviço é cancelado

1.  Clique em **Gerenciamento de serviços** \> **Configuração** \> **Parâmetros de gerenciamento de serviços**.

2.  No formulário **Parâmetros de gerenciamento de serviço**, clique no link **Geral**, e marque a caixa de seleção **Código de motivo para cancelamento**.

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a>Exigir códigos de motivo quando a ordem de serviço exceder o limite de tempo definido pelo contrato de nível de serviço

1.  Clique em **Gerenciamento de serviços** \> **Configuração** \> **Parâmetros de gerenciamento de serviços**.

2.  No formulário **Parâmetros de gerenciamento de serviço**, clique no link **Geral**, e marque a caixa de seleção **Código de motivo sobre tempo excedente**.

## <a name="see-also"></a>Consulte também

[Iniciar e parar a folha de ponto em uma ordem de serviço](start-and-stop-time-recording-on-a-service-order.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]