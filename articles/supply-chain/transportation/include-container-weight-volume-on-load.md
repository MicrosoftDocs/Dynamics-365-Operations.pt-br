---
title: Incluir o peso e o volume do contêiner na carga
description: Este tópico descreve como configurar e aplicar a funcionalidade para incluir o peso e volume de contêineres em cargas.
author: Henrikan
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9196e9c4ce1a8aa629400b8bf379e7164a797b85
ms.sourcegitcommit: 0cc89dd42c1924ca0ec735c6566bc56b39cc5f7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2021
ms.locfileid: "6102629"
---
# <a name="include-container-weight-and-volume-on-load"></a>Incluir o peso e o volume do contêiner na carga

[!include [banner](../includes/banner.md)]

A funcionalidade para incluir o peso e volume de contêiner em uma carga fornece uma representação perfeita do peso e volume totais de contêineres e de itens que estejam prestes a serem carregados.

Uma carga contém uma ou várias remessas remessa de varejo, e essas remessas contêm itens distintos pertencentes a uma única ordem de venda a várias ordens de venda. Os itens são armazenados em um contêiner, e os contêineres são carregados uma carga. Os itens fora de um contêiner também podem fazer parte de uma carga. Com base nessas condições, o sistema calculará valores para peso e volume da carga, considerando o peso e volume de contêineres e de itens.

Se os valores calculados não são precisos, você pode ajustá-los inserindo valores reais do peso e volume na carga. Os valores do peso e volume são usados juntamente processos de gerenciamento de transporte. Por exemplo, os valores são usados na bancada do roteiro de taxa, que ajuda a definir e a taxa a roteiro de cargas, e também são usados para propostas de transporte e check-in do motorista.

## <a name="where-it-applies"></a>Aplica-se a

A funcionalidade para incluir o peso e volume de contêiner em uma carga aplica-se em processos gerenciamento de transporte, como bancada de roteiro de taxa, as propostas de transporte e check-in do motorista.

## <a name="how-it-is-set-up"></a>Como é configurada

O número de contêineres que devem ser considerados para uma carga ser calculada com base no peso e volume do contêiner e, em porcentagem de contêiner é usado.

-   Para definir o peso e volume de um contêiner, clique em **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Tipos de contêiner**.

-   Para definir a porcentagem de utilização de contêiner, clique em **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Grupos de contêiner**, e insira o valor no campo **Porcentagem de utilização do contêiner**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]