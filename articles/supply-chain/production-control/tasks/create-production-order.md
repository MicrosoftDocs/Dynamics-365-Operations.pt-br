---
title: "Criar uma ordem de produção"
description: "Este procedimento mostra como criar uma ordem de produção."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 4db56f76c7f8ce0cccf85ab04024d9a1e88a8822
ms.contentlocale: pt-br
ms.lasthandoff: 02/06/2018

---
# <a name="create-a-production-order"></a>Criar uma ordem de produção

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar uma ordem de produção. A empresa de dados demo usada para criar este procedimento é USMF. Este é o primeiro procedimento fora de sete que explica o ciclo de vida da ordem de produção.


## <a name="create-a-production-order"></a>Criar uma ordem de produção
1. Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.
2. Clique em Nova ordem de produção.
3. No campo Número do item, digite 'D0001'.
4. No campo Entrega, insira uma data.
    * A data de entrega indica quando a ordem de produção deve terminar a fim de entregar à tempo. Esta data pode ser usada no processo de agendamento. Por exemplo, você pode programar o pedido de retrocessão para data de entrega.  
5. Defina a quantidade como '20'.
    * Observação: O campo número de BOM exibe automaticamente o número de qualquer BOM ativo para o item atual, mas você pode alterar a BOM para a ordem de produção ao selecionar uma BOM ativa na lista de versões da BOM aprovadas.    O campo número de Rota exibe automaticamente o número de qualquer Rota ativa para o item atual, mas você pode alterar a Rota para a ordem de produção ao selecionar uma Rota ativa na lista de versões da Rota aprovadas.  
6. Clique em Criar.

## <a name="validate-the-production-order"></a>Validar a ordem de produção
1. Na lista, clique no link na linha selecionada.
    * Clique no link para o número da ordem de produção que você acabou de criar. Isso abrirá a página de detalhes da ordem.  
2. Clique em Editar.
3. No campo Entrega, insira uma data.
    * Por exemplo, você pode alterar a data de entrega da ordem de produção.  
4. Clique em Salvar.
5. Feche a página.

## <a name="update-the-bom"></a>Atualizar BOM
1. No Painel de Ação, clique em Ordem de produção.
2. Clicar em BOM.
    * Abra a página BOM para validar os dados da BOM que foram copiados de dados padrão quando a ordem de produção foi criada. Nesse procedimento, você precisa atualizar a quantidade para uma BOM.  
3. Clique em Editar.
4. No campo Quantidade, insira um número.
    * Alterar a quantidade na linha de BOM tem previsão de custo de consumo de material para a ordem de produção.  
5. Clique em Salvar.
6. Feche a página.

## <a name="update-the-production-route"></a>Atualizar os roteiros de produção
1. No Painel de Ação, clique em Ordem de produção.
2. Clique em Rota.
    * Abra a página Rota para validar os dados da da rota de produção que foram copiados de dados padrão quando a ordem de produção foi criada. Nesse procedimento, você precisa atualizar a quantidade de uma das operações no roteiro de produção.  
3. Na lista, localize e selecione o PDV desejado.
4. Clique em Editar.
5. Em Processar quantidade. insira um número.
    * Alterar o tempo de processo afeta o consumo de roteiro custos previstos e da ordem de produção.  
6. Clique em Salvar.
7. Feche a página.

