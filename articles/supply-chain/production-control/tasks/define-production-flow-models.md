--- 
title: "Definir modelos de fluxo de produção"
description: "Os modelos de fluxo de produção descrevem como capacidade das células de trabalho de lean manufacturing é calculada e atualizada."
author: cvocph
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
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 3da0b5c4fc50136a98017e37b65afea9f8ec7b38
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="define-production-flow-models"></a>Definir modelos de fluxo de produção

[!include[task guide banner](../../includes/task-guide-banner.md)]

Os modelos de fluxo de produção descrevem como capacidade das células de trabalho de lean manufacturing é calculada e atualizada. Entretanto, a definição de um modelo de fluxo de produção é um pré-requisito da definição das células de trabalho. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="define-a-production-flow-model"></a>Defina um modelo de fluxo de produção. 
1. Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Modelos do fluxo de produção
2. Clique em Novo.
3. No campo Modelo de fluxo de produção, digite uma ID para o modelo de fluxo de produção.
4. No campo Tipo de modelo, selecione uma opção.
    * Há dois tipos de modelo: Tipo de produtividade e Tipo de horas. Para o Tipo de produtividade, a capacidade das células de trabalho que usam este modelo de fluxo de produção será expressa e calculadas em quantidades de produto. Para o Tipo de horas, a capacidade das células de trabalho que usam este modelo de fluxo de produção será expressa e calculadas em horas. Observe que essa propriedade não pode ser alterada para um modelo de fluxo de produção existente. Depois que uma célula de trabalho tiver reservas de capacidade, o tipo de modelo do fluxo de produção não pode ser alterado.  
5. Informe o número de dias no Ciclo de EPE.
    * O intervalo descreve o período em que cada parte produzida pelo fluxo de produção ou uma célula de trabalho será gerada pelo menos uma vez. Quanto mais curto for o ciclo de EPE, mais flexível será o processo de produção. Se o ciclo de EPE = 0, todas as demandas poderão ser geradas no mesmo dia. O ciclo de EPE é usado para agendar trabalhos do processo de lean manufacturing. Ao agendar um trabalho em uma célula de trabalho com o ciclo de EPE = 5, o processo de agendamento procurará a capacidade na célula de trabalho na Data de vencimento - ciclo de EPE (5 dias antes da data de vencimento) para garantir que o produto pode ser gerados naquele ciclo. O prazo de entrega de estoque de um produto geralmente é igual ou superior ao ciclo de EPE do processo de produção relacionado.  
6. No campo Tipo de período de planejamento, selecione uma opção.
    * Depois que uma célula de trabalho tiver reservas de capacidade, o tipo de período de agendamento não poderá ser alterado. Você só pode selecionar modelos de fluxo de produção com o mesmo tipo de período para a célula de trabalho específica.  
7. No campo Limite de tempo de planejamento, insira um número.
    * O limite de tempo de planejamento descreve o número de dias que as reservas de capacidade podem ser feitas para as células de trabalho relacionadas. No limite de tempo de Planejamento, insira o número de dias.   Os trabalhos de processo kanban fora deste período não são planejados com planejamento automático. O limite de tempo de planejamento normalmente é duas vezes o prazo de entrega médio de estoque dos produtos gerados em um fluxo de produção ou em uma célula de trabalho. O Ciclo de EPE não deve ser maior do que a metade do limite de tempo de planejamento.     
8. No campo Reação de escassez de capacidade, selecione uma opção.
    * As opções incluem: Adiar - adia a demanda completa do evento de agendamento no próximo dia disponível de produção, com a produtividade disponível. Cancelar - finaliza o planejamento automático para o evento de agendamento e deixa os trabalhos relacionados sem planejamento.   Adicionar ao dia solicitado - planeja os trabalhos solicitados para o período solicitado. Isso sobrecarrega a célula para esse dia e requer que o planejador revise e faça uma interação manual.   Distribuir entre períodos disponíveis - distribui os diferentes trabalhos do evento de agendamento em todos os dias disponíveis de produção, começando pelo primeiro dia disponível. A quantidade mínima de distribuição é a quantidade de trabalhos kanban. A distribuição atribui a quantidade mínima de planejamento (quantidade de kanbans) a cada dia com produtividade suficiente disponível.  


