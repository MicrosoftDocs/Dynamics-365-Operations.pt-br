---
title: Grupos de operadoras
description: Este tópico descreve como configurar dados para grupos de operadoras.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 95517153dda06cecf8e57b1f9b080aa07966c111
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247253"
---
# <a name="carrier-groups"></a>Grupos de operadoras

Um grupo de operadoras é um conjunto de operadoras de remessa e serviços de operadoras. Cada grupo de operadoras especifica a sequência preferencial para as operadoras de remessa e os serviços de operadoras que pertencem a elas.

Quando existem várias operadoras e serviços de operadoras para o mesmo segmento de roteiro, você pode especificar um grupo de operadoras em vez de uma operadora de remessa e um serviço de operadora específicos no plano de roteiro ou no guia de roteiro.

## <a name="create-a-carrier-group"></a>Criar um grupo de operadoras

1. Vá para **Gerenciamento de transporte &gt; Configurar &gt; Operadoras &gt; Grupo de operadoras**.
1. Selecione **Novo**.
1. No campo **Grupo de operadoras**, insira um identificador exclusivo (ID) para o grupo.
1. No campo **Nome**, insira um nome descritivo para o grupo.
1. Na FastTab **Detalhes**, adicione uma linha e selecione uma operadora de remessa e um serviço de operadora para ela. Repita essa etapa até adicionar todas as operadoras necessárias para o grupo.
1. Feche a página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]