---
title: Problemas de processamento ocorrem após a instalação de uma carga de trabalho de depósito de unidade
description: Este tópico descreve problemas que podem ocorrer logo após a instalação de uma carga de trabalho de depósito de unidade de escala e dá conselhos para corrigi-las.
author: perlynne
ms.date: 1/13/2022
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningWorkbench, WHSOutboundLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-01-13
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f589ffed61b695f471989ab1dd693f30cd5d5262
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071615"
---
# <a name="processing-issues-occur-after-a-scale-unit-warehouse-workload-is-installed"></a>Problemas de processamento ocorrem após a instalação de uma carga de trabalho de depósito de unidade

Este tópico descreve problemas que podem ocorrer logo após a instalação de uma carga de trabalho de depósito de unidade de escala e dá conselhos para corrigi-las.

## <a name="issue-1-error-after-a-load-is-released-from-a-load-planning-workbench"></a>Problema 1: erro depois que um carregamento é liberado de uma bancada de planejamento de carga

### <a name="symptoms-of-issue-1"></a>Sintomas do problema 1

Ao lançar um carregamento a partir da página **Bancada do planejamento de carga** ou da página **Workbench de planejamento de carga de entrada**, você receberá uma mensagem de erro com o seguinte formulário:

> Foi detectada uma exceção ao lançar a carga %1. Não foi possível liberar a carga.
> 
> UPDATE WHSSHIPMENTTABLE SET ...
> 
> Não é possível editar um registro nas Remessas (WHSShipmentTable). ID da Remessa: ...

Aqui está um exemplo real que inclui dados de exemplo:

> Foi detectada uma exceção ao lançar a carga USMF-000033, não foi possível liberar a carga.
sessão 5133 (Admin)
>
> UPDATE WHSSHIPMENTTABLE SET ORDERNUM=?,RECVERSION=?,MODIFIEDDATETIME=?,MODIFIEDBY=? WHERE ((RECID=?) AND (RECVERSION=?))  
> [Microsoft][Driver ODBC 17 para SQL Server][SQL Server]Unidade de Escala @@ tentativa de atualizar os registros da Unidade de Escala @A.  
> Servidor de Objetos Azure:
>
> Não é possível editar um registro nas Remessas (WHSShipmentTable). ID da Remessa: USMF-000031, USMF-000033. Erro no banco de dados SQL.

### <a name="cause-of-issue-1"></a>Causa do problema 1

Esse problema pode ocorrer se a seguinte combinação de condições existir quando você instalar a carga de trabalho de depósito da unidade de escala:

- O sistema inclui um carregamento não liberado em que várias linhas são associadas a ordens diferentes e algumas linhas de carregamento não estão associadas a uma remessa.
- O sistema está configurado para usar a consolidação de remessa.

Em uma implantação de topologia híbrida distribuída, cada registro de carga e remessa é marcado como pertencente a uma unidade de escala específica ou a um Hub. Ao liberar um carregamento da página **Bancada do planejamento de carga**, o sistema altera a propriedade atribuída. No entanto, devido às condições listadas anteriormente, o sistema talvez não consiga resolver a propriedade dos dados. Portanto, ele não libera a carga para o depósito.

### <a name="resolution-of-issue-1"></a>Resolução de problema 1

Divida a carga em duas pequenas cargas antes de liberá-la para o depósito.

## <a name="issue-2-error-while-a-wave-is-processed-on-a-scale-unit"></a>Saída 2: erro enquanto um ciclo é processado em uma unidade de escala

### <a name="symptoms-of-issue-2"></a>Sintomas do problema 2

Quando você está processando um ciclo em uma unidade de escala, uma mensagem de erro é exibida com o seguinte formulário:

> Não é possível modificar a linha de carregamento com RecId = %1, ID de carregamento = %2 já que ela ainda pertence ao Hub empresarial. Verifique se o carregamento de saída correspondente foi liberado para uma unidade de escala e, dessa forma, linhas de ordem de depósito criadas.

Aqui está um exemplo real que inclui dados de exemplo:

> Log de informações para executar o ciclo de trabalho USMF-000000012 (9223377668365210)  
> Log de informações para executar o ciclo de tarefas USMF-000000012 (9223377668370462)  
> Não é possível modificar a linha de carregamento com RecId = 68719478242, ID de carga = USMF-000034 já que ela ainda pertence ao Hub empresarial. Verifique se o carregamento de saída correspondente foi liberado para uma unidade de escala e, dessa forma, linhas de ordem de depósito criadas.

### <a name="cause-of-issue-2"></a>Causa do problema 2

Em uma implantação de topologia híbrida distribuída, a propriedade de dados de carga e remessa é atribuída a uma unidade de escala específica ou a um Hub. Como parte do processamento do ciclo, espera-se que a propriedade dos dados seja atribuída a uma unidade de escala.

Quando você instala uma carga de trabalho de depósito de unidade de escala, se uma remessa aberta for associada a um carregamento e um ciclo, o sistema não pode controlar a propriedade dos dados. Portanto, o processamento do ciclo falha na unidade de escala.

### <a name="resolution-of-issue-2"></a>Resolução de problema 2

Libere a carga para o depósito do hub.

## <a name="troubleshoot-issues-by-viewing-a-records-ownership-and-destination"></a>Solucionar problemas exibindo a propriedade e o destino de um registro

Em uma implantação de topologia híbrida distribuída, muitos tipos de registros são marcados como pertencente a uma unidade de escala específica ou a um hub. Depois de alternar para uma topologia híbrida distribuída e/ou configurar uma nova carga de trabalho de depósito de unidade de escala, o sistema atribui a propriedade a cada registro relevante. Esse processo pode, às vezes, causar erros ou produzir resultados inesperados. Portanto, as informações sobre a propriedade de um registro e o destino da transferência podem ajudá-lo a solucionar problemas que ocorrerem depois que você fizer esses tipos de alterações.

Siga estas etapas para exibir a propriedade e o destino da transferência de um registro.

1. Abra o registro relevante.
1. No Painel de Ação, na guia **Opções**, no grupo **Informações sobre registro**, selecione **Mostrar todos os campos**.
1. A página exibida mostra valores para todos os campos disponíveis para o registro selecionado. Revise os campos a seguir:

    - **SYSSCALEUNITID** – este campo mostra o proprietário atual do registro.
    - **SYSTARGETSCALEUNITID** – este campo mostra a ID da unidade de escala do hub ou da unidade organizacional para a qual o registro será transferido quando o proprietário atual tiver concluído o trabalho com ele. O valor deste campo é usado pelos trabalhos em lote que gerenciam esse tipo de processo. Embora esse campo não esteja diretamente relacionado à propriedade, a propriedade pode ser alterada quando o registro é transferido. Em alguns casos, este campo ficará em branco.
