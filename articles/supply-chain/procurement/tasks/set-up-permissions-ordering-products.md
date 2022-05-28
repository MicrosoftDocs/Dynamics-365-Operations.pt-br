---
title: Configurar permissões para solicitar produtos em nome de qualquer outra pessoa
description: Este tópico explica como conceder a trabalhadores a permissão para preparar requisições da compra em nome de outros trabalhadores.
author: GalynaFedorova
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1313ca01686e55d802716adf335e77ffeb1ece34
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679293"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>Configurar permissões para solicitar produtos em nome de qualquer outra pessoa

[!include [banner](../../includes/banner.md)]

Este tópico explica como conceder a trabalhadores a permissão para preparar requisições da compra em nome de outros trabalhadores. Ou seja, um "preparador" de requisição de compra pode criar uma requisição para outro "solicitante". O procedimento também mostra como conceder permissões a um trabalhador para pedir itens e serviços em diferentes entidades legais ou unidades operacionais. Geralmente, essas tarefas são realizadas por um gerente de compras. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>Conceda permissões para inserir requisições de compra em nome de outro trabalhador
1. No Painel de navegação, Acesse **Módulos > Compras e fornecimento > Configuração > Políticas > Permissões de requisição de compra**. Certifique-se de que o campo **Exibição atual** está ajustado **Pelo preparador**. A lista no painel à esquerda mostra as pessoas que podem receber a permissão para preparar requisições em nome de outras pessoas.  
2. Selecione a pessoa para conceder a permissão (o preparador).
3. Selecione **Adicionar**.
4. Encontre e selecione a pessoa para adicionar como um solicitador.
    - O solicitante é a pessoa com a qual o preparador pode criar requisições em seu nome.  
    - No campo **Autorização**, selecione **Específico** se o preparador puder criar requisições da compra em nome do trabalhador selecionado. Selecione **Relatório** se o preparador também puder criar requisições da compra em nome de todos os trabalhadores que reportam a esse trabalhador.  
5. No campo **Efetivo**, insira uma data.
6. No campo **Vencimento**, insira uma data.

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>Veja os preparadores que têm a permissão para criar requisições de compra para um trabalhador selecionado
1. No campo **Exibição atual**, selecione **Pelo solicitador**. Esta exibição exibe uma lista de preparadores que receberam permissão para criar requisições de compra em node de um trabalhador selecionado.  
2. Use o filtro rápido para encontrar o trabalhador que você apenas adicionou como o solicitador.
3. Selecione o solicitante. A lista do preparador mostra as pessoas que têm a permissão para pedir artigos em nome do solicitador que é selecionado no painel à esquerda.  Você pode adicionar preparadores adicionais aqui. Esta exibição também permite que a permissão do solicitante crie requisições em entidades legais e unidades operacionais que não são a pessoa da entidade legal primária ou unidade operacional.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]