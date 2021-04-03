---
title: Criar atividades de transferência para lean manufacturing
description: Crie uma atividade de transferência para lean manufacturing.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityWizard, LeanWorkCellLookup, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e3c92c5fc9cdba7c77942fae5c32d625cc939f1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237909"
---
# <a name="create-transfer-activities-for-lean-manufacturing"></a>Criar atividades de transferência para lean manufacturing

[!include [banner](../../includes/banner.md)]

Crie uma atividade de transferência para lean manufacturing. 

Pré-requisitos: 

1. Um fluxo de produção e versão que não estão ativos devem ser criados.

2. É necessário criar os depósitos de origem e de destino e os locais. Opcionalmente, o reabastecimento ou a célula de trabalho reabastecida devem ser criados.


## <a name="find-the-production-flow-version"></a>Localizar a versão do fluxo de produção
1. Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.
2. Na lista, localize e selecione o PDV desejado.
    * Observe que o fluxo de produção deve ter uma versão em status de rascunho.  
3. Na lista, clique no link na linha selecionada.

## <a name="create-a-new-activity"></a>Criar uma atividade
1. Clique em Atividades.
    * Verifique se o fluxo de produção selecionado tem uma versão de rascunho e selecione-a.  
2. Clique em Criar uma atividade do plano.
3. Clique em Avançar.
4. No campo Nome, digite um valor.
5. No campo Tipo de atividade, selecione 'Transferência'.
6. No campo Quantidade processada, insira um número.
7. Clique em Avançar.

## <a name="select-the-work-cells"></a>Selecionar as células de trabalho
1. No campo Reabastecimento, clique no botão suspenso para abrir a pesquisa.
    * Para usar o local de saída da célula de trabalho como o local de origem na atividade de transferência, selecione uma célula de trabalho. O mesmo pode ser feito com a célula de trabalho reabastecida, que define o local de destino da atividade de transferência.  
2. Na lista, clique no link na linha selecionada.

## <a name="define-the-inventory-updates"></a>Definir as atualizações de estoque
1. No campo Tipo de produto, selecione uma opção.
    * Observe que uma transferência não altera o tipo de produto. Você pode transferir produtos finalizados ou semifinalizados (transferência entre duas atividades de um fluxo de produto e possivelmente um fluxo kanban).     Na transferência de produtos finalizados, você pode selecionar se deseja separar ou receber resultados em uma transação de estoque.  

## <a name="define-the-transfer-locations"></a>Definir os locais de transferência
1. Clique em Avançar.
2. No campo Depósito, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o registro desejado.
4. Na lista, clique no link na linha selecionada.
5. No campo Localização, clique no botão suspenso para abrir a pesquisa.
6. Na lista, clique no link na linha selecionada.
7. No campo Fretado por, selecione 'Expedidor'.
    * As opções incluem: Expedidor - a organização que opera o depósito de remessa, Destinatário - a organização que opera o depósito de recebimento, Transportadora - um fornecedor externo. Se a organização operacional for um fornecedor, a atividade de transferência precisará de um contrato de subcontratação.  
8. Clique em Avançar.

## <a name="define-the-activity-times"></a>Definir os períodos de atividade
1. Na lista, localize e selecione o PDV desejado.
    * A definição de um tempo de execução é necessária. O tempo de execução é usado para calcular custos e as horas de produtividade dos trabalhos kanban. Os tempos de execução não são usados para calcular a carga de capacidade e o consumo, que são calculados pelo ciclo de tempo, derivadas da tarefa de versão do fluxo de produção.  
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]