---
title: Agendar limpeza de dados de histórico de vendas
description: Este tópico descreve como você pode ajudar a melhorar o desempenho do sistema ao agendar a tarefa periódica de limpeza do histórico de atualizações de vendas para ser executada em intervalos regulares.
author: myvakalo
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6c6c1e08d45f2a7d1e1267010b286111bad01a6c
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570348"
---
# <a name="schedule-sales-history-data-cleanup"></a>Agendar limpeza de dados de histórico de vendas

[!include [banner](../includes/banner.md)]

Como parte de sua operação padrão, o Microsoft Dynamics 365 Supply Chain Management gera e armazena dados de atualização de histórico de vendas em uma base contínua. Com o tempo, um grande número de dados desatualizados do histórico de vendas pode se acumular no sistema. Esses dados acumulados podem causar problemas funcionais e de desempenho quando os documentos relacionados a ordens de venda são lançados. (Esses documentos incluem confirmações de ordem de venda, guias de remessa de venda, listas de separação de vendas e faturas). Portanto, você deve configurar e programar a tarefa periódica de *limpeza do histórico de atualização de vendas* para ser executada em intervalos regulares. Esta tarefa removerá todos os dados de atualização do histórico de vendas que não são mais necessários.

Se você usar a tarefa periódica de *limpeza do histórico de atualização de vendas*, é recomendável habilitar o recurso de *Melhorias no desempenho de limpeza do histórico de vendas*, o que torna a execução da tarefa mais eficiente. (No entanto, você também pode executar a tarefa sem habilitar esse recurso.)

## <a name="turn-on-the-sales-history-cleanup-features"></a>Ativar os recursos de limpeza do histórico de vendas

Para configurar e usar a tarefa periódica de *limpeza do histórico de atualizações de vendas* junto com todos os recursos descritos neste tópico, você deve habilitar os recursos *Melhorias no desempenho de limpeza do histórico de vendas* e *Limpar histórico de atualizações de vendas com base na idade* no gerenciamento de recursos, conforme descrito nas subseções a seguir.

### <a name="sales-history-cleanup-performance-improvements"></a>Melhorias no desempenho de limpeza do histórico de vendas

O trabalho em lote periódico **Limpeza do histórico de vendas** pode demorar muito se for executada com pouca frequência em ambientes com um alto volume de atualizações de vendas. Nessas situações, o recurso *Aperfeiçoamentos de desempenho da limpeza de vendas* pode ajudar a reduzir a duração da execução e melhorar a confiabilidade.

O recurso melhora o trabalho de limpeza atual das seguintes maneiras:

- Ele divide a limpeza em lotes (você pode alterar o tamanho do lote por meio das personalizações).
- Ela será executada por um máximo de 2 horas (você pode alterar a duração por meio das personalizações).
- Sempre que possível, a limpeza utiliza os recursos do banco de dados para minimizar o bloqueio e evitar a junção de tabelas transacionais durante a limpeza.

Depois de habilitar o recurso, o trabalho em lotes **Limpeza do histórico de atualizações de vendas** (**Vendas e marketing \> Tarefas periódicas de \> Limpeza \> Limpeza do histórico de atualizações de vendas**) será executado como de costume, mas com melhor desempenho e por um máximo de 2 horas. Isso significa que talvez seja necessário executar várias vezes para limpar todos os dados de um período de retenção específico.

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Vendas e marketing*
- **Nome do recurso:** *melhorias no desempenho de limpeza do histórico de vendas*

### <a name="clean-up-sales-update-history-based-on-age"></a>Limpar histórico de atualizações de vendas com base na idade

O recurso *Limpar histórico de atualizações de vendas com base na idade* permite especificar a idade máxima dos registros a serem mantidos durante a execução da tarefa *Limpeza do histórico de atualização de vendas*. Os registros mais antigos serão excluídos. Esse recurso é útil quando você configura a tarefa para ser executada periodicamente porque a idade é sempre calculada em relação à data em que a tarefa é executada. Se não usar esse recurso, você só pode definir uma data específica para que os registros mais antigos sejam mantidos.

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Vendas e marketing*
- **Nome do recurso:** *Limpar histórico de atualizações de vendas com base na idade*

## <a name="set-up-and-schedule-the-sales-history-cleanup-periodic-task"></a>Configurar e agendar a tarefa periódica de limpeza do histórico de vendas

Para configurar e agendar a tarefa periódica de *limpeza do histórico de vendas*, siga estas etapas.

1. Analise suas necessidades comerciais para determinar quantos dias de dados de lançamento da ordem de venda histórica devem ser mantidos. Geralmente, recomendamos que você execute a tarefa de limpeza a cada três meses e, no máximo, a cada seis meses.
1. Acesse **Vendas e marketing \> Tarefas periódicas \> Limpeza \> Limpeza do histórico de atualização de vendas**.
1. Na caixa de diálogo **Limpar histórico de atualização de vendas**, na FastTab **Parâmetros**, defina os seguintes campos:

    - **Limpeza**: selecione um dos valores a seguir para especificar o tipo de registro a ser limpo:

        - **Executado**: exclui somente os registros que foram totalmente processados. Como você provavelmente não terá mais nenhum uso para esses registros, essa opção será a mais segura.
        - **Executados e errados**: exclua os registros e registros totalmente processados em que ocorreu um erro. Essa opção é a mais usada. Talvez seja interessante inspecionar e até corrigir registros errôneos, em vez de limpá-los automaticamente. No entanto, muitas empresas optam por limpar esses registros muito tempo depois de cerca de um mês, pois eles provavelmente não são mais relevantes nesse período.
        - **Todos**: exclua registros executados, errados e em espera. Os registros em espera são válidos, mas ainda não foram totalmente processados. Na maioria dos casos, você provavelmente não deseja que eles sejam excluídos automaticamente. No entanto, em algumas situações, você pode optar por excluí-las automaticamente depois que um determinado período de tempo tiver passado.

    - **Reter registros com base na idade**: especifique se deseja limpar registros com base na idade no dia em que a tarefa é executada ou excluir registros que foram criados antes de uma data fixa. Se você estiver agendando a limpeza como uma tarefa recorrente, deverá definir esta opção como *Sim*, porque a idade é sempre calculada em relação à data em que a tarefa é executada.

        - Defina essa opção como *Sim* para habilitar o campo **Idade máxima**. Use este campo para especificar a duração máxima dos registros e manter sempre que a tarefa for executada. O campo **Criado até** será ignorado.
        - Defina essa opção como *Não* para habilitar o campo **Criado até**. Use este campo para especificar a data de criação mais antiga dos registros para manter quando a tarefa é executada. O campo **Idade máxima** é ignorado.

    - **Criado até**: essa configuração se aplica somente quando a opção **Reter registros com base na idade** está definida como *Não*. Especifique a data de criação mais antiga dos registros para manter quando a tarefa é executada. Os registros que foram criados antes dessa data serão excluídos.
    - **Idade máxima**: essa configuração se aplica somente quando a opção **Reter registros com base na idade** está definida como *Sim*. Especifique a idade máxima dos registros (em dias) e manter sempre que a tarefa for executada. Os registros mais antigos serão excluídos.

1. Na Guia Rápida **Executar no plano de fundo**, especifique como, quando e com que frequência a tarefa é executada. Use essas configurações para implementar a agenda determinada na etapa 1. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em lote](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Selecione **OK** para aplicar suas configurações e fechar a caixa de diálogo.
