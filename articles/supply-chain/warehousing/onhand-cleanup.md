---
title: Trabalho de limpeza de entradas disponíveis do gerenciamento de depósito
description: Este artigo descreve o trabalho de limpeza de entradas disponíveis, que ajuda a melhorar o desempenho do sistema identificando e excluindo registros relacionados, mas não necessários.
author: perlynne
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: a82a3b26f2bf7cb546383da047d18c2997569ca5
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065109"
---
# <a name="warehouse-management-on-hand-entries-cleanup-job"></a>Trabalho de limpeza de entradas disponíveis do gerenciamento de depósito

[!include [banner](../includes/banner.md)]

O desempenho das consultas que são usadas para calcular o estoque disponível é afetado pelo número de registros nas tabelas envolvidas. Uma forma de ajudar a melhorar o desempenho é reduzir o número de registros que o banco de dados deve considerar.

Este artigo descreve o trabalho de limpeza de entradas disponíveis, que exclui registros desnecessários nas tabelas `InventSum` e `WHSInventReserve`. Essas tabelas armazenam informações disponíveis para itens habilitados para processamento de gerenciamento de depósito. (Esses itens são mencionados como itens de WMS). A exclusão desses registros pode melhorar significativamente o desempenho dos cálculos disponíveis.

## <a name="what-the-cleanup-job-does"></a>O que o trabalho de limpeza faz

O trabalho de limpeza de entradas disponíveis exclui quaisquer registros nas tabelas `WHSInventReserve` e `InventSum` em que todos os valores de campo sejam *0* (zero). Esses registros podem ser excluídos porque não contribuem para as informações disponíveis. O trabalho exclui somente os registros que estão abaixo do nível de **Localização**.

Se o estoque físico negativo for permitido, talvez o trabalho de limpeza não consiga excluir todas as entradas relevantes. O motivo dessa limitação é que o trabalho deve permitir um cenário especial no qual uma placa de licença tem vários números de série, e um desses números de série se tornou negativo. Por exemplo, o sistema tiver zero disponível no nível da placa de licença quando uma placa de licença tiver mais de 1 pcs de número de série 1 e -1 pcs de número de série 2. Para esse cenário especial, o trabalho faz uma exclusão em primeiro nível, em que ele tenta excluir primeiro dos níveis inferiores.

## <a name="schedule-and-configure-the-cleanup-job"></a>Agendar e configurar o trabalho de limpeza

O trabalho de limpeza de entradas disponíveis está disponível em **Gerenciamento de estoque \> Tarefas periódicas \> Limpeza \> Limpeza de entradas disponíveis no gerenciamento de depósito**. Use as configurações de trabalho padrão para controlar o escopo e a agenda para a execução do trabalho. Adicionalmente, as configurações a seguir são fornecidas:

- **Excluir se não for atualizado para este número de dias** – insira o número mínimo de dias que o trabalho deve aguardar antes de excluir uma entrada disponível que tenha caído para quantidade zero. Use esta configuração para ajudar a reduzir o risco de excluir entradas disponíveis que ainda estão sendo usadas. Se você deseja que a limpeza ocorra o mais rápido possível, digite *0* (zero) ou deixe o campo em branco.
- **Tempo de execução máximo (horas)** – insira o tempo de execução máximo do trabalho de limpeza, em horas. Se o trabalho não for concluído antes desse tempo, ele salvará o trabalho concluído até o momento e, em seguida, será fechado. Esse recurso é especialmente relevante para implementações com alto uso de estoque. Nesses casos, você deverá agendar o trabalho a ser executado às vezes quando a carga do sistema for a mais clara possível. Se você deseja que o trabalho em lotes continue a ser executado até que seja concluído, insira *0* (zero) ou deixe o campo em branco. Essa configuração só estará disponível se o recurso relacionado tiver sido [ativado no sistema](#max-execution-time).

Embora seja possível executar o trabalho durante o horário comercial normal, recomendamos que ele seja executado fora do horário de trabalho. Dessa forma, você ajudará a evitar conflitos que poderão ocorrer se um usuário estiver trabalhando com um registro que também está sendo limpo.

Se o trabalho tentar excluir um registro de um item enquanto esse registro estiver sendo usado por outro usuário, ocorrerá um erro de deadlock para o trabalho de limpeza ou o usuário.

Quando o trabalho é executado, ele tem um tamanho de confirmação de 100. Em outras palavras, ele tentará confirmar uma vez para cada 100 exclusões. No entanto, como algumas exclusões são baseadas em conjunto, pode haver situações em que mais de 100 registros possam ser excluídos na mesma transação. Portanto, as escalonamentos de bloqueio ainda podem ocorrer.

## <a name="possible-user-impact"></a>Possível impacto do usuário

Os usuários poderão ser afetados se o trabalho de limpeza de entradas disponíveis excluir todos os registros de um determinado nível (como o nível da placa de licença). Nesse caso, a funcionalidade para ver que o estoque estava disponível anteriormente em uma placa de licença talvez não funcione conforme o esperado, pois as entradas disponíveis relevantes não estão mais disponíveis. Isso pode, por exemplo, ser visto nas seguintes situações:

- Na **Lista disponível**, quando o usuário desmarca a condição **Quantidade \<\> 0** ou seleciona a condição **Transações fechadas** nas configurações de **Exibição de dimensões**.
- Em um relatório de **Estoque físico por dimensão do estoque** de períodos anteriores, quando o usuário define o parâmetro **A partir da data**.

No entanto, a melhoria de desempenho que o trabalho de limpeza fornece deve compensar essas pequenas perdas de funcionalidade.

## <a name="make-the-maximum-execution-time-setting-available"></a><a name="max-execution-time"></a>Disponibilizar a configuração de tempo de execução máximo

A configuração de **Tempo de execução máximo** só estará disponível quando o recurso *Tempo de execução máximo para o trabalho de limpeza de entradas disponíveis no gerenciamento de depósito* estiver ativado. A partir da versão 10.0.25 do Supply Chain Management, este recurso está ativado por padrão. Os administradores podem ativar ou desativar essa funcionalidade procurando o recurso *Tempo de execução máximo para o trabalho de limpeza de entradas disponíveis no gerenciamento de depósito* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]