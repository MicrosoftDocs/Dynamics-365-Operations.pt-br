---
title: Desativar uma versão de fluxo de produção
description: Quando uma versão ativa de fluxo de produção não é mais necessária, ela pode ser desativada.
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
ms.openlocfilehash: e47cb950ce488d8b6170f829e1fedc664b921a1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811549"
---
# <a name="deactivate-a-production-flow-version"></a>Desativar uma versão de fluxo de produção

[!include [banner](../../includes/banner.md)]

Quando uma versão ativa de fluxo de produção não é mais necessária, ela pode ser desativada. Você deverá usar esta opção somente se todas as regras kanban e todas as atividades terminaram e não serão ativadas novamente. Observe que a data de vencimento de todas as regras kanban relacionadas a essa versão de fluxo de produção será atualizada com a data e hora atuais. 

Para modificar uma versão ativa de fluxo de produção, considere definir uma data de vencimento para a versão ativa e criar uma nova versão. Isto permitirá que você continue com suas operações de produção enquanto prepara a nova versão e as regras kanban relacionadas. 

Para expirar uma versão ativa de fluxo de produção, é necessário definir uma data de vencimento. Nesse sentido, a desativação funciona mais como uma exceção do que uma regra. 

Para este procedimento, é necessário um fluxo de produção com uma versão que possa ser desativada. Não tente isso em um ambiente de produção a menos que você tenha plena certeza de que a versão está completamente obsoleta.


## <a name="deactivate-a-production-flow-version"></a>Desativar uma versão de fluxo de produção
1. Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Na lista, localize e selecione o PDV desejado.
5. Clique em Desativar.
    * Não continue se não estiver totalmente certo de que esta versão do fluxo de produção esteja obsoleta. Clicar em OK expirará todas as regras kanban ativas e interromperá instantaneamente todas as atividades de produção e de reabastecimento desta versão de fluxo de produção.  
6. Clique em OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]