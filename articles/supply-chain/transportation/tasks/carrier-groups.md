---
title: Grupos de operadoras
description: Este tópico descreve como configurar dados para grupos de operadoras.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 10a30d8fae52a25b7d65b5a9cc991677df33a2a7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574872"
---
# <a name="carrier-groups"></a>Grupos de operadoras

[!include [banner](../../includes/banner.md)]

Um grupo de operadoras é um conjunto de operadoras de remessa e serviços de operadoras. Cada grupo de operadoras especifica a sequência preferencial para as operadoras de remessa e os serviços de operadoras que pertencem a elas.

Quando existem várias operadoras e serviços de operadoras para o mesmo segmento de roteiro, você pode especificar um grupo de operadoras em vez de uma operadora de remessa e um serviço de operadora específicos no plano de roteiro ou no guia de roteiro.

## <a name="create-a-carrier-group"></a>Criar um grupo de operadoras

1. Acesse **Gerenciamento de transporte &gt; Configurar &gt; Operadoras &gt; Grupo de operadoras**.
1. Selecione **Novo**.
1. No campo **Grupo de operadoras**, insira um identificador exclusivo (ID) para o grupo.
1. No campo **Nome**, insira um nome descritivo para o grupo.
1. Na FastTab **Detalhes**, adicione uma linha e selecione uma operadora de remessa e um serviço de operadora para ela. Repita essa etapa até adicionar todas as operadoras necessárias para o grupo.
1. Feche a página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]