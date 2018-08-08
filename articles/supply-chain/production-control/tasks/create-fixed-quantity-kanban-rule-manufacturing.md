--- 
title: "Criar uma regra kanban de quantidade fixa para fabricação"
description: "Este procedimento tem como foco a configuração necessária para criar uma regra kanban de fabricação fixa para ativação de atividades de transformação, em uma célula de trabalho, em um ambiente de lean manufacturing."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8020a37bf0c725fc260574cfe87861aeb017519e
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a>Criar uma regra kanban de quantidade fixa para fabricação

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento tem como foco a configuração necessária para criar uma regra kanban de fabricação fixa para ativação de atividades de transformação, em uma célula de trabalho, em um ambiente de lean manufacturing. A empresa de dados demo usada para criar este procedimento é USMF. Este procedimento destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado.


## <a name="create-new-kanban-rule"></a>Criar regra kanban
1. Vá para Regras kanban.
2. Clique em Novo.
    * Observe que o tipo padrão é fabricação e a estratégia de reabastecimento é fixa. Você não precisa alterar esses parâmetros.  
3. No campo Primeira atividade do plano, insira ou selecione um valor.
    * Esta é a atividade que será realizada para kanbans criados com base nesta regra kanban.  Selecione 'SpeakerTestAndPackaging'.  
4. Expanda a seção Detalhes.
5. No campo Produto, insira ou selecione um valor.
    * Selecione L0050.  
6. No campo Unidade de medida, insira ou selecione um valor.
    * Selecione minutos.  
7. No campo Prazo de entrega, insira um número.
    * Digite 5.  

## <a name="set-quantities"></a>Definir quantidades
1. Expanda a seção Quantidades.
2. Defina Quantidade padrão como '10'.
    * Esta é a quantidade que será transferida para cada kanban.  
3. Marque a caixa de seleção Variação de quantidade de produto.
    * Com ela, os kanbans selecionados podem ser concluídos com uma variação da quantidade padrão.  Para permitir que os kanbans sejam concluídos com a quantidade de 8 a 12, defina ambas as variações como 2.  
4. Defina Variação abaixo como '2'.
    * Isso permitirá a conclusão até 10 - 2 = 8  
5. Defina Variação acima como '2'.
    * Isso permitirá a conclusão até 10 + 2 = 12  
6. No campo Quantidade de kanbans fixa, insira um número.
    * Este é o valor de kanbans que deve ser ativado. Neste caso, 5 kanbans que processam 10 de cada.  
7. No campo Valor mínimo de limite de alerta, insira '2'.
    * Usado para manter o controle do valor mínimo de kanbans completos que devem estar no destino. Por exemplo, ele é usado na visão geral da quantidade de kanbans.  
8. No campo Valor máximo de limite de alerta, insira '4'.
    * Usado para manter o controle do valor máximo de kanbans completos que devem estar no destino. Por exemplo, ele é usado na visão geral da quantidade de kanbans.  
9. No campo Quantidade de planejamento automático, insira '1'.
    * A liquidação dele até 1 significa que cada kanban será planejado automaticamente.   Se inseríssemos 3, os kanbans não seriam planejados até 3 kanbans vazios estarem prontos para planejamento. Isso é útil para agrupar trabalho e evitar excesso de configuração.  

## <a name="create-kanbans"></a>Criar Kanbans
1. Expanda a seção kanbans.
2. Clique em Salvar.
    * A regra kanban precisa ser salva antes de kanbans poderem ser criados.  
3. Clique em Adicionar.
    * Observe que não há kanbans ativos, por isso, o 'Número de novos kanbans' sugerido é 5. É o mesmo número da 'Quantidade fixa de kanbans'.  
4. Clique em Criar.
    * Isso criará 5 kanbans.  
    * Note que 5 kanbans, para cada 10, foram criados para essa regra kanban de fabricação. Esta é a última etapa do procedimento.  


