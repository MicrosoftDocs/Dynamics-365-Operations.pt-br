---
title: Localizar grades de produtos obsoletos
description: Este procedimento mostra como localizar produtos ou grades de produtos liberados obsoletos e como associar um estado do ciclo de vida do produto aos produtos obsoletos.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aea9c785ce57bf498007d3127edbd270b1c31a52
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203471"
---
# <a name="find-obsolete-product-variants"></a>Localizar grades de produtos obsoletos 

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como localizar produtos ou grades de produtos liberados obsoletos e como associar um estado do ciclo de vida do produto aos produtos obsoletos. Pré-requisito: você precisa definir pelo menos um estado do ciclo de vida do produto que esteja inativo para planejar para poder executar este guia de tarefas.


## <a name="run-a-simulation"></a>Executar uma simulação
1. Vá para Gerenciamento de informações sobre produtos > Tarefas periódicas > Alterar o estado do ciclo de vida para produtos obsoletos.
2. No campo Novo estado do ciclo de vida do produto, insira ou selecione um valor.
3. Selecione Sim no campo Executar simulação sem atualizar dados de produto.
4. No campo Excluir produtos criados neste número de dias, digite um número.
5. No campo Excluir produtos usados em transações (em número de dias), digite um número.
6. Expanda os Registros para incluir a seção.
7. Clique em Filtro.
8. Na lista, marque a linha selecionada.
9. No campo Critérios, digite um valor.
10. Clique em OK.
11. Clique em OK.

> [!NOTE]
> É recomendável executar a simulação em lote se você espera pesquisar um grande número de produtos. Além disso, garanta que a simulação não seja executada durante o horário de trabalho mais ativo da empresa.  

## <a name="review-the-simulation-results"></a>Examinar os resultados da simulação
1. Vá para Gerenciamento de informações sobre produtos > Consultas e relatórios > Histórico de manutenção do estado do ciclo de vida do produto.
   
> [!NOTE]
> Nesta página, você pode examinar os resultados da simulação e avaliar quantos produtos e grades de produtos serão associados a um novo estado do ciclo de vida do produto ao executar a atualização sem simulação.  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a>Executar a atualização do Estado do ciclo de vida do produto para produtos obsoletos
1. Feche a página.
2. Vá para Gerenciamento de informações sobre produtos > Tarefas periódicas > Alterar o estado do ciclo de vida para produtos obsoletos.
3. Expanda os Registros para incluir a seção.

> [!NOTE]
> Observe que a última seleção foi salva.  

4. Selecione Não no campo Executar simulação sem atualizar dados de produto.
5. Expanda a seção Executar em segundo plano.

> [!NOTE]
> Dependendo da quantidade de produtos e de grades de produtos afetados, considere executar este trabalho em lote. Não execute um trabalho de atualização grande durante o horário de trabalho mais ativo da empresa.  

6. Clique em OK.
7. Vá para Gerenciamento de informações sobre produtos > Consultas e relatórios > Histórico de manutenção do estado do ciclo de vida do produto.

> [!NOTE]
> Examinar os produtos e as grades de produtos liberados alterados.  

8. Na lista, localize e selecione o PDV desejado.

