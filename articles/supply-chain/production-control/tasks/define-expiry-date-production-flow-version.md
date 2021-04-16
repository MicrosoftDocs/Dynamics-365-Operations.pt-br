---
title: Definir uma data de vencimento de uma versão de fluxo de produção
description: Para encerrar a validade e o processamento de uma versão de fluxo de produção em uma data planejada ou para planejar a substituição de uma versão ativa por uma nova, é necessário definir uma data de vencimento na versão.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 97d652fbf647b62359efe27d4d740f6e38b70b59
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828793"
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