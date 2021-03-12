---
title: Criar atividades de processo para lean manufacturing
description: Crie uma atividade de processo para lean manufacturing.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup, PlanActivityDetails, KanbanJobPickingListPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bd505446456791b26850d676722b6676b50dca4b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4981197"
---
# <a name="create-process-activities-for-lean-manufacturing"></a>Criar atividades de processo para lean manufacturing

[!include [banner](../../includes/banner.md)]

Crie uma atividade de processo para lean manufacturing. 

Pré-requisitos: 

1. Um fluxo de produção e versão que não estão ativos devem ser criados.

2. Uma célula de trabalho deve ser criada.


## <a name="find-the-production-flow-version"></a>Localizar a versão do fluxo de produção
1. Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.

## <a name="create-a-new-activity"></a>Criar uma atividade
1. Clique em Atividades.
    * Verifique se o fluxo de produção selecionado tem uma versão de rascunho e selecione-a.  
2. Clique em Criar uma atividade do plano.
3. Clique em Avançar.
4. No campo Nome, digite um valor.
5. No campo Nome, digite um valor.
    * Vale notar que o nome deve ser exclusivo para um determinado fluxo de produção para todas as versões.  
6. No campo Quantidade processada, insira um número.
    * Independentemente da quantidade de trabalho a ser processada, essa é a quantidade mínima por trabalho para cálculo do custo de mão de obra. Se as quantidades de trabalho divergirem dessa quantidade, uma variação de custo de mão de obra será criada.  
7. Clique em Avançar.

## <a name="select-the-work-cell"></a>Selecionar a célula de trabalho
1. No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.
2. Na lista, clique no link na linha selecionada.

## <a name="define-the-inventory-updates"></a>Definir as atualizações de estoque
1. Selecione ou desmarque a caixa de seleção Atualizar recebimento disponível.
    * Em caso de Atualizar disponibilidade = Não, você pode definir a atividade para receber um produto semifinalizado (a atividade não chega ao próximo nível de BOM).    Você também pode optar por consumir produtos semifinalizados.  

## <a name="define-the-picking-activities"></a>Definir as atividades de separação
1. Clique em Avançar.
2. Na lista, marque a linha selecionada.
    * Uma atividade de separação padrão é criada para o local de entrada da célula de trabalho selecionada.  
3. Clique em Adicionar.
    * Você pode criar atividades de separação adicionais para produtos específicos, que não são preparados na atividade de entrada da célula de trabalho.  
4. Na lista, localize e selecione o PDV desejado.
5. No campo Número de item, digite um valor.
6. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
    * Com essa definição, todos os materiais consumidos na atividade são separados no depósito e local de entrada padrão, com exceção do item que é definido na segunda atividade de separação. Esse item será separado em um depósito e local diferentes.  
7. Na lista, localize e selecione o PDV desejado.
8. Na lista, clique no link na linha selecionada.
9. Selecione ou desmarque a caixa de seleção Registrar sucata.
10. Clique em Avançar.

## <a name="define-the-activity-times"></a>Definir os períodos de atividade
1. Na lista, localize e selecione o PDV desejado.
    * A definição de um tempo de execução é necessária. O tempo de execução é usado para calcular custos e as horas de produtividade dos trabalhos kanban. Os tempos de execução não são usados para calcular a capacidade máxima e o consumo, que são calculados pelo tempo de ciclo, derivados da tarefa de versão do fluxo de produção.  
2. No campo Hora, insira um número.
3. No campo Unidade, digite um valor.
4. Selecione a unidade Hora.
5. No campo Por quantidade, insira um número.
6. Na lista, localize e selecione o PDV desejado.
    * Tempos de espera são opcionais.  
7. No campo Hora, insira um número.
8. No campo Unidade, digite um valor.
9. Selecione a unidade Hora.
10. No campo Por quantidade, insira um número.
11. Clique em Avançar.
12. Clique em Finish (Concluir).
13. Feche a página.

