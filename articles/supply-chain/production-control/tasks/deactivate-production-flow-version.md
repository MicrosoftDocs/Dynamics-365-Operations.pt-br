--- 
title: "Desativar uma versão de fluxo de produção"
description: "Quando uma versão ativa de fluxo de produção não é mais necessária, ela pode ser desativada."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4a7eee6617e12d59a3d06207f5f6b58c93e28240
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="deactivate-a-production-flow-version"></a>Desativar uma versão de fluxo de produção

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


