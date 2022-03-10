---
title: Desativar uma versão de fluxo de produção
description: Quando uma versão ativa de fluxo de produção não é mais necessária, ela pode ser desativada.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1691dc644e2e191a9e74980784d6dcf741dcd598
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576751"
---
# <a name="deactivate-a-production-flow-version"></a>Desativar uma versão de fluxo de produção

[!include [banner](../../includes/banner.md)]

Quando uma versão ativa de fluxo de produção não é mais necessária, ela pode ser desativada. Você deverá usar esta opção somente se todas as regras kanban e todas as atividades terminaram e não serão ativadas novamente. Observe que a data de vencimento de todas as regras kanban relacionadas a essa versão de fluxo de produção será atualizada com a data e hora atuais. 

Para modificar uma versão ativa de fluxo de produção, considere definir uma data de vencimento para a versão ativa e criar uma nova versão. Isto permitirá que você continue com suas operações de produção enquanto prepara a nova versão e as regras kanban relacionadas. 

Para expirar uma versão ativa de fluxo de produção, é necessário definir uma data de vencimento. Nesse sentido, a desativação funciona mais como uma exceção do que uma regra. 

Para este procedimento, é necessário um fluxo de produção com uma versão que possa ser desativada. Não tente isso em um ambiente de produção a menos que você tenha plena certeza de que a versão está completamente obsoleta.


## <a name="deactivate-a-production-flow-version"></a>Desativar uma versão de fluxo de produção
1. Acesse Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Na lista, localize e selecione o PDV desejado.
5. Clique em Desativar.
    * Não continue se não estiver totalmente certo de que esta versão do fluxo de produção esteja obsoleta. Clicar em OK expirará todas as regras kanban ativas e interromperá instantaneamente todas as atividades de produção e de reabastecimento desta versão de fluxo de produção.  
6. Clique em OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]