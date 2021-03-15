---
title: Processamento adiado de trabalho de depósito
description: Este tópico descreve a funcionalidade que disponibiliza o processamento adiado de operações colocadas do trabalho de depósito no Dynamics 365 Supply Chain Management.
author: josaw1
manager: tfehr
ms.date: 11/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-6-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c85dd895e18805da2d1daf5f90f64db82bdc0116
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973776"
---
# <a name="deferred-processing-of-warehouse-work"></a>Processamento adiado de trabalho de depósito

[!include [banner](../includes/banner.md)]

Este tópico descreve a funcionalidade que disponibiliza o processamento adiado de operações colocadas do trabalho de depósito no Dynamics 365 Supply Chain Management.

A funcionalidade de processamento adiado permite que trabalhadores de depósito continuem a fazer outros trabalhos enquanto a operação colocada é processada em segundo plano. O processamento adiado é útil quando várias linhas de trabalho devem ser processadas e o trabalhador pode deixar esse trabalho ser processado de forma assíncrona. Também é útil quando o servidor pode ter aumentos ad hoc ou não planejados no tempo de processamento e o tempo de processamento maior pode afetar a produtividade do usuário.

O processamento em segundo plano é obtido usando a estrutura SysOperation. Para obter mais informações, consulte [Visão geral da estrutura SysOperation](https://docs.microsoft.com/dynamicsax-2012/developer/sysoperation-framework-overview).

## <a name="configuring-the-work-processing-policies"></a>Como configurar políticas de processamento de trabalhos

Para usar o processamento adiada, você deve configurar e utilizar uma política de processamento de trabalhos.

Políticas são configuradas na página **Políticas de processamento de trabalhos**. A tabela a seguir descreve os campos nessa página.

| Campo                           | Descrição |
|---------------------------------|-------------|
| Nome da política de processamento de trabalhos     | O nome da política de processamento de trabalho. |
| Tipo de ordem de serviço                 | O tipo de ordem de serviço ao qual a política se aplica. |
| Operação                       | A operação que é processada usando a política. |
| Método de processamento de trabalho          | O método que é usado para processar a linha de trabalho. Se o método for definido como **Imediato**, o comportamento será parecido com o de quando nenhuma política de processamento de trabalho é usada para processar a linha. Se o método for definido como **Adiado**, o processamento adiado que utiliza a estrutura de lotes será usado. |
| Limite de processamento adiado   | Um valor **0** (zero) indica que não há limite. Nesse caso, o processamento adiado será usado se puder ser usado. Se o cálculo de limite específico estiver abaixo do limite, o método imediato será usado. Caso contrário, o método adiado será usado se puder ser usado. Para vendas e trabalho relacionado a transferências, o limite é calculado como o número de linhas de carga da origem associadas que estão sendo processados para o trabalho. Para trabalhos de reabastecimento, o limite será calculado como o número de linhas de trabalho que estão sendo reabastecidas pelo trabalho. Por exemplo, ao definir um limite de **5** para venda, os trabalhos menores com menos de cinco linhas de carga de origem inicial não usarão o processamento adiado, mas trabalhos maiores o usarão. O limite terá um efeito apenas se o método de processamento do trabalho estiver definido como **Adiado**. |
| Grupo de lote de processamento adiado |O grupo de lotes usado para processamento. |

Para o processamento de inserção adiada, os seguintes tipos de ordem de serviço são suportados: ordem de venda, emissão de ordem de transferência e reabastecimento.

## <a name="assigning-the-work-creation-policy"></a>Atribuição da política de criação de trabalho

A política de criação do trabalho pode ser atribuída nos parâmetros de gerenciamento de depósito. Ela também pode ser atribuída em nível de depósitos individuais. Se a política for atribuída a um depósito, ela será aplicada apenas ao trabalho criado para esse depósito. Se nenhuma política for atribuída em nível de depósito, a política dos parâmetros de gerenciamento de depósito será aplicada.

## <a name="viewing-the-deferred-put-processing-tasks"></a>Exibição das tarefas de processamento colocado adiado

Você pode exibir tarefas de processamento colocado adiado na página **Tarefas de processamento colocado adiado**.

Por padrão, as tarefas **Concluídas** são mostradas.

| Campo            | Descrição |
|------------------|-------------|
| Status           | O status da tarefa. |
| Status do trabalho em lotes | O status do trabalho em lote relacionado. Se o trabalho em lote foi processado, o histórico de lotes conterá o log e as informações do trabalho em lotes. |

Veja aqui uma explicação dos possíveis status:

- **Espera** – O trabalho em lotes relacionado está aguardando o processamento no servidor de lote.
- **Com falha** – O processamento falhou. A tarefa pode ser reprocessada usando a ação **Processo adiado colocado**, ou pode ser cancelada usando a ação **Cancelamento adiado colocado**.
- **Concluído** – O trabalho foi concluído.

## <a name="impact-on-closed-work-dates"></a>Impacto em datas de trabalho fechado

Quando o processamento colocado adiado for usado, a data de trabalho fechado será definida como a data/hora criada das de tarefas de processamento colocado adiado. A data de trabalho fechado é usada como a melhor previsão quando a operação colocada é concluída.

## <a name="reprocessing-a-failed-task"></a>Reprocessamento de uma tarefa com falha

Para reprocessar uma tarefa com falha, selecione na página e selecione **Processo adiado colocado**. Reprocessar corresponde a uma situação em que o usuário conclui o armazenamento a partir do dispositivo móvel como se estivesse definido para processamento imediato.

## <a name="canceling-failed-tasks"></a>Cancelamento de tarefas com falha

Apenas as tarefas com falha podem ser canceladas. Quando você cancela uma tarefa, pode atribuí-la a um novo usuário. Como alternativa, a tarefa pode permanecer atribuída ao usuário que processou o trabalho. O cancelamento corresponde a uma situação em que o trabalho é retornado ao dispositivo móvel como se a última etapa de separação tivesse recém-concluída e o trabalho precisasse ser armazenado. Entretanto, o usuário poderá determinar que o trabalho seja "diferentes", pois terá apenas uma etapa de armazenamento. O local corresponderá ao local em que o primeiro usuário que processou o trabalho teve como um local colocado final.

Quando uma tarefa é cancelada, o trabalho não é mais bloqueado pelo motivo de bloqueio de processamento colocado adiado. Ele pode ser reprocessado usando o dispositivo móvel.

O registro da tarefa é excluído quando a tarefa é cancelada.

## <a name="configuring-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Configuração do menu de dispositivo móvel para ignorar a política de processamento diferida

Você pode configurar o item de menu de dispositivo móvel de forma que a política de processamento diferida não seja usada. O trabalho é processado da mesma forma quando nenhuma política de processamento diferido é usada. Esta funcionalidade permite que um supervisor utilize um item de menu específico em que colocado adiado não é usado. Para configurá-lo, defina o campo **Política de processamento colocado adiado** como **Substituir configurações e processo colocado de forma síncrona**. 

## <a name="restrictions-when-the-deferred-put-processing-isnt-applied"></a>Restrições quando o processamento colocado adiado não se aplica

Há vários cenários onde o processamento colocado adiado não se aplica, embora a política esteja configurada. Eis alguns exemplos:

- A conclusão do trabalho manual é usada.
- O trabalho é concluído usando a conclusão automática.
- Modelos de auditoria são usados.


## <a name="monitoring-the-deferred-processing-tasks-from-the-outbound-work-monitoring-workspace"></a>Monitoramento do processamento adiado de tarefas do espaço de trabalho Monitoramento do trabalho de saída

O espaço de trabalho **Monitoramento do trabalho de saída** apresenta dois blocos que ajudam a monitorar tarefas de processamento colocado adiado:

- **Falha em tarefas de processando colocado adiado** – Este bloco mostra o número de tarefas com falhas. Se houver tarefas com falhas, o gerente de depósito deverá reprocessá-las ou cancelá-las, pois elas não serão reprocessadas automaticamente.
- **Aguardando processamento de tarefas colocadas adiadas** – Este bloco mostra o número de tarefas que ficaram com o status **Aguardando** por mais de 10 minutos. Se o bloco mostrar um número, ele indicará que um problema ocorreu durante o processamento em lotes. Você pode processar manualmente as tarefas **Aguardando**. Se o trabalho em lotes para uma tarefa for processado mais tarde, ele falhará, pois já foi processado. Não haverá impacto.

## <a name="deleting-completed-tasks"></a>Excluindo tarefas concluídas

Você pode excluir tarefas de processamento colocado adiado que foram concluídas, selecionando-as e excluindo-as na página.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]