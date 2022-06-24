---
title: Processamento adiado de movimento de estoque manual
description: Este artigo descreve como usar o processamento adiado do movimento de estoque manual no Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 04/27/2021
ms.topic: article
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-27
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5e5d0a93a4c628d4867161d082b0f0e177ddb95c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863727"
---
# <a name="deferred-processing-of-manual-inventory-movement"></a>Processamento adiado de movimento de estoque manual

[!include [banner](../includes/banner.md)]

Este artigo descreve como usar o processamento adiado do movimento de estoque manual no Microsoft Dynamics 365 Supply Chain Management.

O processamento adiado permite que trabalhadores de depósito continuem a fazer outros trabalhos enquanto uma operação colocada é processada em segundo plano. O processamento adiado é útil quando o servidor pode ter aumentos ocasionais ou não planejados no tempo de processamento e o tempo de processamento maior pode afetar a produtividade do trabalhador. O tipo de trabalho *movimento de estoque* foi agora adicionado ao conjunto de tipos de trabalho que esse recurso suporta.

O processamento em segundo plano é obtido usando o [recurso Processar eventos de aplicativo de depósito](warehouse-app-events.md).

## <a name="turn-on-this-feature-for-your-system"></a>Ative este recurso para o seu sistema

Para disponibilizar esse recurso, ative os recursos a seguir no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md): Você deve ativá-los nesta ordem:

1. *Bloqueio de trabalho em toda a organização*<br>(Desde a versão 10.0.21 do Supply Chain Management, este recurso é obrigatório, portanto, é ativado por padrão e não pode ser desativado novamente.)
1. *Processar eventos do aplicativo de depósito*<br>(A partir do Supply Chain Management versão 10.0.25, este recurso está ativado por padrão.)
1. *Operações put diferidas*
1. *Processamento adiado da operação de movimentação de estoque manual*<br>(Desde a versão 10.0.25 do Supply Chain Management, este recurso é obrigatório, portanto, é ativado por padrão e não pode ser desativado novamente.)

## <a name="configure-the-work-processing-policies"></a>Configure políticas de processamento de trabalho

Para usar o processamento adiado, você deve configurar e utilizar uma política de processamento de trabalho. Para o processamento colocado adiado, o [recurso Processamento adiado de trabalho de depósito](deferred-put.md) oferece suporte aos seguintes tipos de trabalho: *Ordem de venda*, *Emissão de ordem de transferência* e *Reabastecimento*. O recurso *Processamento adiado de operação de movimento de estoque manual* adiciona um novo tipo de trabalho: *Movimento de estoque*.

Para configurar uma política de processamento de trabalho, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Políticas de processamento de trabalho**.
1. Selecione uma política existente na lista ou crie uma nova política, selecionando **Novo** no Painel de Ações. O cabeçalho de cada política tem os seguintes campos:

    - **Nome da política de processamento de trabalhos** - o nome da política de processamento de trabalhos.
    - **Descrição:** - uma descrição da política de processamento de trabalho.

1. Na FastTab **Regras de processamento**, configure a coleção de regras que a política aplicará. Use os botões da barra de ferramentas para adicionar e remover regras, conforme necessário. Em cada regra, defina os seguintes campos:

    - **Tipo de ordem de trabalho** - selecione o tipo de trabalho ao qual a diretiva se aplica.
    - **Operação** – Selecione a operação que a política costuma processar. Se você selecionou *Movimento de estoque* no campo **Tipo de ordem de trabalho**, não precisará definir este campo porque as operações separar e colocar são processadas como um único evento.
    - **Método de processamento de trabalho** – Selecione o método usado para processar a linha de trabalho. Se você selecionar *Imediato*, o comportamento será parecido com o de quando nenhuma política de processamento de trabalho é usada para processar a linha. Se você selecionar *Adiado*, o sistema aplicará o processamento adiado que usa a estrutura de lotes.
    - **Limite de processamento adiado** – se você definir este campo como *0* (zero), não haverá nenhum limite. Neste caso, o método de processamento *Adiado* é usado, se possível. Se o cálculo de limite específico estiver abaixo do limite, o método *Imediato* será usado. Caso contrário, o método *Adiado* será usado, se possível. Para vendas e trabalho relacionado a transferências, o limite é calculado como o número de linhas de carga da origem associadas que estão sendo processados para o trabalho. Para trabalhos de reabastecimento, o limite será calculado como o número de linhas de trabalho que estão sendo reabastecidas pelo trabalho. Por exemplo, ao definir um limite de *5* para venda, você garante que trabalhos menores com menos de cinco linhas de carga de origem inicial não usarão o processamento adiado, mas trabalhos maiores o usarão. O limite terá efeito somente se o campo **Método de processamento de trabalho** for definido como *Adiado*.
    - **Grupo de lotes de processamento adiado** – especifique o grupo de lotes usado para processamento. Se você selecionou *Movimento de estoque* no campo **Tipo de ordem de trabalho**, não precisará definir este campo porque o grupo de lotes está selecionado na caixa de diálogo **Processar eventos do aplicativo de depósito**.

## <a name="assign-the-work-creation-policy"></a>Atribuir a política de criação de trabalho

Para obter detalhes sobre como atribuir uma política de criação de trabalho, consulte [Processamento adiado de trabalho de depósito](deferred-put.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurar um trabalho em lotes para processar eventos de aplicativo de depósito

Para usar o processo *Processamento adiado de operação de movimento de estoque manual*, configure um trabalho em lotes agendado.

1. Acesse **Gerenciamento de depósito \> Tarefas periódicas \> Processar remessas de saída**.
1. Na caixa de diálogo **Processar eventos do aplicativo de depósito**, na FastTab **Executar em segundo plano**, defina a opção **Processamento em lotes** como *Sim*.
1. Selecione **Recorrência** e configure um plano de execução que atenda aos requisitos de sua empresa.
1. Selecione **OK** em cada caixa de diálogo.

## <a name="inquire-about-the-warehouse-app-events"></a>Consulte sobre eventos do aplicativo de depósito

Você pode exibir a fila de eventos e as mensagens de eventos geradas pelo aplicativo de depósito indo para **Gerenciamento de depósito \> Consultas e relatórios \> Logs do dispositivo móvel \> Eventos do aplicativo de depósito**.

As mensagens de evento *Movimento de estoque* terão o status de *Enfileirado* quando forem criadas pela primeira vez. Este status indica que o trabalho em lotes **Processar eventos do aplicativo de depósito** irá coletá-las e processá-las. Quando o status for atualizado para *Concluído*, todos os eventos relacionados serão excluídos da fila.

Todos os eventos *Movimento de estoque* serão acumulados em uma coleção por tipo de evento e depósito.

O trabalho em lotes processará os eventos do aplicativo de depósito de acordo com a recorrência configurada na caixa de diálogo **Processar eventos de aplicativo de depósito**. Portanto, até que uma mensagem seja processada, você pode encontrar a ID do depósito verificando o campo **Identificador**.

Os detalhes da mensagem contêm os detalhes da movimentação (por exemplo, os locais "de" e "para").

Para obter mais informações, consulte [Processamento de eventos do aplicativo de depósito](warehouse-app-events.md).

## <a name="configure-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Configure o menu de dispositivo móvel para ignorar a política de processamento adiado

Para obter detalhes sobre como configurar o menu de dispositivo móvel para ignorar a política de processamento adiado, consulte [Processamento adiado de trabalho de depósito](deferred-put.md).

## <a name="impact-on-closed-work-dates"></a>Impacto em datas de trabalho fechado

Para obter detalhes sobre o impacto nas datas de trabalho fechadas, consulte [processamento adiado de trabalho de depósito](deferred-put.md).

## <a name="additional-resources"></a>Recursos adicionais

- [Processamento adiado de trabalho de depósito](deferred-put.md)
- [Processamento de eventos do aplicativo de depósito](warehouse-app-events.md)
- [Configurar dispositivos móveis para trabalho de depósito](configure-mobile-devices-warehouse.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
