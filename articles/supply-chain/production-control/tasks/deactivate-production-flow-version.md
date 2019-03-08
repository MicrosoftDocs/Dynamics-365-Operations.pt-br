---
title: Desativar uma versão de fluxo de produção
description: Quando uma versão ativa de fluxo de produção não é mais necessária, ela pode ser desativada.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 091cafd02bd568323e586373fc8b0f983afee343
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "340743"
---
# <a name="deactivate-a-production-flow-version"></a>Desativar uma versão de fluxo de produção

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

