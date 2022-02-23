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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2570479edac9bc8cc7aa998a8b69f54ffc10cd61
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646362"
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
