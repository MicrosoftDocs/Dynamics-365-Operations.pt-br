--- 
title: Criar uma regra kanban de retirada
description: "Este procedimento mostra a configuração necessária para criar uma regra kanban de saída para transferir o material em um ambiente de lean."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: c3172f5c932b94b2a9e442286eb61159286297fb
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-withdrawal-kanban-rule"></a>Criar uma regra kanban de retirada

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra a configuração necessária para criar uma regra kanban de saída para transferir o material em um ambiente de lean. A empresa de dados demo usada para criar este procedimento é USMF. Este procedimento destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam o reabastecimento de um material novo ou modificado.


## <a name="create-new-kanban-rule"></a>Criar regra kanban
1. Vá para Regras kanban.
2. Clique em Novo.
3. No campo Tipo, selecione "Retirada".
    * O tipo de retirada é usado para que as regras kanban transfiram o material ou as mercadorias.  
4. No campo Primeira atividade do plano, insira ou selecione um valor.
    * Selecione ReplenishSpeakerComponents.   Essa atividade é configurada para mover os componentes do depósito 11, do local 11 para o armazenamento 12, do local 12.  
5. No campo Produto, insira ou selecione um valor.
    * Selecione M0007.  
6. No campo Prazo de entrega, insira um número.
    * Por exemplo, 60.  
7. No campo Unidade de medida, insira ou selecione um valor.
    * Por exemplo, Minutos.  

## <a name="set-quantities-for-kanban"></a>Definir quantidades de kanban
1. Defina Quantidade padrão como '5'.
    * Esta é a quantidade que será transferida para cada kanban.  
2. No campo Quantidade kanban fixo, insira '2'.
    * Este é o valor de kanbans que deve ser ativado. Neste caso, 2 kanbans que transferem 5 de cada.  
3. No campo Valor mínimo de limite de alerta, insira '1'.
    * Usado para manter o controle do valor mínimo de kanbans completos que devem estar no destino. Por exemplo, ele é usado na visão geral da quantidade de kanbans.  
4. No campo Valor máximo de limite de alerta, insira '2'.
    * Usado para manter o controle do valor máximo de kanbans completos que devem estar no destino. Por exemplo, ele é usado na visão geral da quantidade de kanbans.  

## <a name="create-kanbans"></a>Criar kanbans
1. Clique em Salvar.
    * A regra kanban precisa ser salva antes de kanbans poderem ser criados.  
2. Clique em Adicionar.
    * Observe que, como não há kanbans ativos, o 'Número de novos kanbans' sugerido é 2, sendo igual à 'Quantidade de kanbans fixa'.  
3. Clique em Criar.
    * Isso criará dois kanbans.  
    * Note que 2 kanbans, para cada 5, foram criados para essa regra kanban de retirada.  Esta é a última etapa do procedimento.  

