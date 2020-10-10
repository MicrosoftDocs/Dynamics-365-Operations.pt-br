---
title: Liberar uma ordem de produção
description: Este procedimento mostra como liberar uma ordem de produção.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: beef850e7e58fb58db545c0be5990b52619070d3
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826565"
---
# <a name="release-a-production-order"></a>Liberar uma ordem de produção

[!include [banner](../../includes/banner.md)]

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

