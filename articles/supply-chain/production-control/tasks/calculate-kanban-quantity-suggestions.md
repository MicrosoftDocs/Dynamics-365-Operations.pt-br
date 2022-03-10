---
title: Calcular sugestões de quantidade de kanbans
description: Este procedimento foca na otimização das quantidades e tamanho kanban para uma regra kanban específica através do uso do cálculo da quantidade kanban.
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18d2a8dd2a8c132873744ba890ca6b1eb1fd34b6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570121"
---
# <a name="calculate-kanban-quantity-suggestions"></a>Calcular sugestões de quantidade de kanbans

[!include [banner](../../includes/banner.md)]

Este procedimento foca na otimização das quantidades e tamanho kanban para uma regra kanban específica através do uso do cálculo da quantidade kanban. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é destinado ao gerente de fluxo de valor. A conclusão do procedimento Adicionar uma nova política de cálculo da quantidade kanban à uma regra kanban é um pré-requisito.


## <a name="create-a-kanban-quantity-calculation"></a>Crie um cálculo da quantidade kanban
1. Acesse Controle de produção > Tarefas periódicas > Cálculo da quantidade de kanbans > Calcular quantidade kanban.
2. Clique em Novo.
3. No campo Nome, digite 'Spearker2016'.
4. No campo Nome, clique no botão suspenso para abrir a pesquisa.
    * Selecione a política que você criou durante o procedimento Adicionar uma nova política de cálculo de quantidade kanban à uma regra kanban. Por exemplo, Speaker2016.  
5. Na lista, clique no link na linha selecionada.
6. No campo Regra ativa a partir da data, defina a data e a hora para '2012-12-17T08:00:00'.
    * Essa data serve como base para determinar quais regras fixas kanban estão incluídas no cálculo da quantidade kanban.  
7. No campo Data de início do período de demanda cumprida, defina a data e a hora para '2012-11-17T09:00:00'.
    * A data a partir da qual transações de demanda passadas são incluídas no cálculo da quantidade kanban.  
8. No campo Data de término do período de demanda cumprida, defina a data e a hora para '2012-12-17T07:59:59'.
    * A data até a qual as transações de demanda passadas são incluídas no cálculo da quantidade kanban.  
9. No campo Data de início do período de demanda, defina a data e a hora para '2012-12-17T08:00:00'.
    * A data a partir da qual as transações de demanda atuais são incluídas no cálculo da quantidade kanban.  
10. No campo Data de término do período de demanda, defina a data e a hora para '2013-01-16T07:59:59'.
    * A data até a qual as transações de demanda atuais são incluídas no cálculo da quantidade kanban.  

## <a name="generate-kanban-quantity-proposal"></a>Gere a proposta da quantidade kanban
1. Clique em Salvar.
2. Clique em Gerar.
    * Isso gera uma linha de proposta da quantidade kanban para a regra kanban 000020.  

## <a name="run-kanban-quantity-calculation"></a>Execute o cálculo da quantidade kanban
1. Clique em Calcular.
    * Isso calcula a proposta da quantidade kanban.  
2. Clique em OK.
3. Na lista, marque a linha selecionada.
    * Observe que a quantidade kanban sugerida é 2.  

## <a name="change-product-quantity-and-calculate-again"></a>Altere a quantidade do produto e calcule novamente
1. Defina Quantidade de produto para '5'.
2. Clique em Calcular.
3. Clique em OK.
    * Observe que com uma quantidade kanban de 5, a sugestão é alterada para uma quantidade kanban de 4.  
    * Isso é causado pelo fato de que com uma quantidade menor de produto, são necessários mais kanbans para atender a demanda.  

## <a name="update-kanban-rule"></a>Atualize a regra kanban
1. No campo Data efetiva da regra, insira uma data e hora.
    * Defina 'Regra ativa a partir da data' para uma data futura. Por exemplo, hoje + um ano.  
2. Clique em Atualizar.
3. Clique em OK.
4. Feche a página.

## <a name="validate-change-on-kanban-rule"></a>Valide a alteração na regra kanban
1. Acesse Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.
2. Na lista, clique no link na linha selecionada.
    * Selecione a regra kanban que foi criada na subtarefa anterior. Esta deve ser a primeira regra kanban na lista classificada por número.  
3. Ative a expansão da seção Detalhes.
    * Observe a data efetiva, o que significa que esta regra não estará ativada até essa data.  
4. Ative a expansão da seção Quantidades.
    * Observe que esta é a quantidade padrão que você inseriu no cálculo da quantidade kanban.  
    * Observe que esta é a quantidade kanban fixa de 4 do cálculo da quantidade kanban.  
5. Clique na guia Painel de Lista.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]