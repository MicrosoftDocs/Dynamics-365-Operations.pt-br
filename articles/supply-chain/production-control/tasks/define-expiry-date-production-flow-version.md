---
title: Definir uma data de vencimento de uma versão de fluxo de produção
description: Para encerrar a validade e o processamento de uma versão de fluxo de produção em uma data planejada ou para planejar a substituição de uma versão ativa por uma nova, é necessário definir uma data de vencimento na versão.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a595ca4ff9f6753631303b656d56735320a22a69
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975076"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a>Definir uma data de vencimento de uma versão de fluxo de produção

[!include [banner](../../includes/banner.md)]

Para encerrar a validade e o processamento de uma versão de fluxo de produção em uma data planejada ou para planejar a substituição de uma versão ativa por uma nova, é necessário definir uma data de vencimento na versão. Não é necessário desativar a versão.


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a>Definir uma data de vencimento para encerrar uma versão de fluxo de produção
1. Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione qualquer fluxo de produção que tenha uma versão já definida.  
3. Na lista, clique no link na linha selecionada.
4. Clique em Editar.
5. Na lista, marque a linha selecionada.
6. No campo Data de vencimento, insira uma data e hora.
    * Para a data de vencimento, uma nova versão não iniciará nem será ativada. Também não será possível criar ou iniciar trabalhos para esse fluxo de produção. Ainda será possível concluir trabalhos iniciados após a data de vencimento.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]