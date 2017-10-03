--- 
title: "Liberar uma ordem de produção"
description: "Este procedimento mostra como liberar uma ordem de produção."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 6497921db5632fe69ae596bddd6889c6d3125c38
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="release-a-production-order"></a>Liberar uma ordem de produção

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como liberar uma ordem de produção. A empresa de dados demo usada para criar este procedimento é USMF. Este é o quarto procedimento de sete que explica o ciclo de vida da ordem de produção.

1. Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.
    * Na grade, selecione uma ordem de produção que tem o status Agendado.  
2. No Painel de Ação, clique em Ordem de produção.
3. Clique em Liberar.
    * Nesta página, você pode confirmar a versão do intervalo selecionado de ordens de produção. Clique em Selecionar se deseja adicionar ordens.  
    * A etapa de liberação indica quando a ordem de produção é liberada para o chão de fábrica de produção de modo que os operadores de chão de fábrica possam informar o progresso no trabalho de produção. Os documentos de produção que contêm informações relevantes sobre o processamento do trabalho podem ser emitidos. O trabalho de depósito para a separação de matéria-prima é gerado para os itens configurados para o processo de depósito.  
4. Clique na guia Geral.
    * Selecione os relatórios de produção que devem ser impressos. O relatório de ficha de trabalho imprime uma página para cada trabalho programado e requer a ordem de produção a ser planejada no nível do profissional. O relatório contém informações sobre as horas inicial e final programadas, a quantidade a gerar e o recurso que processa os trabalhos. O relatório de roteiro de trabalho coleta as mesmas informações na mesma página, mas não imprime uma página para cada trabalho. O relatório de cartão de roteiro mostra apenas as operações, mas não os trabalhos. Consequentemente, este relatório não requer o plano de trabalho, mas pode ser usado quando as ordens de produção são planejadas no nível da operação.  
5. Clique na caixa de seleção Imprimir cartão de roteiro.
6. Clique em OK.
7. Feche a página.


