---
title: Configurar permissões para solicitar produtos em nome de qualquer outra pessoa
description: Este procedimento mostra como conceder a trabalhadores a permissão para preparar requisições da compra em nome de outros trabalhadores.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: eea1577972879cc24a2295a0c5a8d7d3de5f4520
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837965"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>Configurar permissões para solicitar produtos em nome de qualquer outra pessoa

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como conceder a trabalhadores a permissão para preparar requisições da compra em nome de outros trabalhadores. Ou seja, um "preparador" de requisição de compra pode criar uma requisição para outro "solicitante". O procedimento também mostra como conceder permissões a um trabalhador para pedir itens e serviços em diferentes entidades legais ou unidades operacionais. Geralmente, essas tarefas são realizadas por um gerente de compras. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>Conceda permissões para inserir requisições de compra em nome de outro trabalhador
1. Vá para Compras > Configuração > Políticas > Permissões de requisição de compra.
    * Certifique-se de que o campo da exibição atual está ajustado pelo preparador.  A lista no painel à esquerda mostra as pessoas que podem receber a permissão para preparar requisições em nome de outras pessoas.  
2. Selecione a pessoa para conceder a permissão (o preparador).
3. Clique em Adicionar.
4. Encontre e selecione a pessoa para adicionar como um solicitador.
    * O solicitante é a pessoa com a qual o preparador pode criar requisições em seu nome.  
    * No campo Autorização, selecione Específico se o preparador puder criar requisições da compra em nome do trabalhador selecionado. Selecione Relatório se o preparador também puder criar requisições da compra em nome de todos os trabalhadores que reportam a esse trabalhador.  
5. No campo Efetivo, insira uma data.
6. No campo Vencimento, insira uma data.

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>Veja os preparadores que têm a permissão para criar requisições de compra para um trabalhador selecionado
1. No campo Exibição atual, selecione “Pelo solicitador”.
    * Esta exibição exibe uma lista de preparadores que receberam permissão para criar requisições de compra em node de um trabalhador selecionado.  
2. Use o filtro rápido para encontrar o trabalhador que você apenas adicionou como o solicitador.
3. Selecione o solicitante.
    * A lista do preparador mostra as pessoas que têm a permissão para pedir artigos em nome do solicitador que é selecionado no painel à esquerda.   Você pode adicionar preparadores adicionais aqui.   Esta exibição também permite que a permissão do solicitante crie requisições em entidades legais e unidades operacionais que não são a pessoa da entidade legal primária ou unidade operacional.  

