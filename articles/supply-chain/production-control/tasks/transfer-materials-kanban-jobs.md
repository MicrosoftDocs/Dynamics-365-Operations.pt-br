---
title: Transferir materiais com trabalhos kanban
description: Esse procedimento se concentra na execução de um trabalho kanban de retirada para transferir materiais.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11771bbedc9fe4bdfaaa074c449cd329ce1a1d8f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567982"
---
# <a name="transfer-materials-with-kanban-jobs"></a>Transferir materiais com trabalhos kanban

[!include [banner](../../includes/banner.md)]

Esse procedimento se concentra na execução de um trabalho kanban de retirada para transferir materiais. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é destinado ao trabalhador do depósito.


## <a name="display-transfer-jobs"></a>Exibir trabalhos de transferência
1. Acesse Controle de produção > Kanban > Quadro kanban para trabalhos de transferência.
2. Expandir ou recolher a seção Filtros.
    * Na seção Filtros, você pode especificar quais trabalhos você deseja visualizar filtrando por Fluxo de produção, Nome da atividade, Do depósito e localização, e Para o depósito e localização.  
3. No campo Do depósito, digite '11'.
4. No campo Para o local, digite '12'.

## <a name="start-a-transfer-job"></a>Iniciar um trabalho de transferência
1. Na lista, desmarque a linha selecionada - se houver alguma.
2. Na lista, selecione a linha 4.
    * Selecione o primeiro trabalho com o status Não planejado. Verifique se este é o único trabalho selecionado.  
3. Clique em Iniciar.
    * Observe que um ícone indica que o trabalho esta iniciado.  

## <a name="select-a-second-transfer-job-and-change-quantity"></a>Selecione um segundo trabalho de transferência e altere a quantidade
1. Na lista, localize e selecione o PDV desejado.
    * Você pode ter vários trabalhos selecionados, mas por enquanto selecione a linha 5.  
2. Na lista, localize e selecione o PDV desejado.
    * Verifique se o trabalho da etapa anterior é o único selecionado. Desmarque todos os outros trabalhos.  
3. Anote o valor do campo Quantidade do trabalho para referência futura
4. Defina Quantidade do trabalho para '30'.
    * Observe o aviso! Você não tem permissão para transferir 30. De acordo com a instalação da regra kanban, você só pode transferir a quantidade original.  
5. Use o valor anotado anteriormente no campo Quantidade do trabalho
    * Defina a Quantidade do trabalho para o valor anterior.  

## <a name="start-the-second-transfer-job"></a>Inicie o segundo trabalho de transferência
1. Clique em Iniciar.
    * Isso iniciará a transferência do trabalho da linha 5.  

## <a name="complete-both-transfer-jobs"></a>Conclua ambos os trabalhos de transferência
1. Na lista, selecione a linha 4.
    * Agora dois trabalhos de transferência são selecionados na linha 4 e na linha 5.  
2. Clique em Concluir.
    * Isso irá concluir a transferência de ambos os trabalhos.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]