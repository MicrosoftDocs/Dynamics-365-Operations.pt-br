---
title: Monitorar a execução de um planejamento mestre
description: Este artigo explica como o planejador de produção pode ver se a execução de um planejamento mestre está em andamento.
author: t-benebo
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da04ef95f2f7e411ecea3fadf7ff31b3502d3d99
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860744"
---
# <a name="monitor-a-master-planning-run"></a>Monitorar a execução de um planejamento mestre

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a>Use um gráfico de Gantt para visualizar o andamento do planejamento mestre

Na página **Exibir andamento de planejamento mestre**, você pode exibir detalhes de execuções históricas do planejamento mestre como um gráfico de Gantt. Esta funcionalidade pode ajudar a entender o tempo decorrido nas várias fases de planejamento mestre. Para um trabalho de planejamento ativo atual, a página **Exibir andamento de planejamento mestre** pode ser usada para controlar o andamento e exibir o tempo estimado restante.

### <a name="turn-the-master-plan-progress-visualization-feature-on-or-off"></a>Ativar ou desativar o recurso Visualização do andamento do plano mestre

A partir da versão 10.0.21 do Supply Chain Management, este recurso está ativado por padrão. A partir do Supply Chain Management 10.0.25, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.25, os administradores poderão habilitar ou desabilitar essa funcionalidade pesquisando o recurso *Visualização do andamento do plano mestre* no espaço de trabalho [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="use-the-master-plan-progress-visualization-feature"></a>Usar o recurso Visualização do andamento do plano mestre

A página **Exibir andamento de planejamento mestre** pode exibir trabalhos de planejamento históricos e trabalhos de planejamento ativos. 

Para exibir trabalhos históricos de planejamento, há duas opções. 

1. Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres** e, depois, no Painel de Ação, selecione **Histórico**. Com o trabalho desejado selecionado, selecione **Consultas** e depois selecione **Exibir andamento**
1. Acesse **Planejamento mestre \> Espaços de trabalho \> Planejamento mestre**, no bloco Planejamento mestre, clique em **Histórico**. Com o trabalho desejado selecionado, selecione **Consultas** e depois selecione **Exibir andamento**

Para exibir trabalhos de planejamento ativos, há duas opções. 
1. Acesse **Planejamento mestre \> Espaços de trabalho \> Planejamento mestre**, no Painel de Ação, selecione **Processo de planejamento inacabado**. Com o trabalho desejado selecionado, selecione **Consultas** e depois selecione **Exibir andamento**.
1. Acesse **Planejamento mestre \> Espaços de trabalho \> Planejamento mestre**, no bloco Planejamento mestre, clique em **Exibir andamento**. Com o trabalho desejado selecionado, selecione **Consultas** e depois selecione **Exibir andamento**

Observe que você só poderá exibir os trabalhos ativos quando um trabalho de planejamento estiver em processamento.

### <a name="analyze-a-master-planning-job"></a>Analisar um trabalho de planejamento mestre

No gráfico de Gantt, é possível expandir cada um dos processos de planejamento para exibir detalhes adicionais sobre o tempo gasto:

- Inicializando
- Excluindo e inserindo dados
- Planejamento de cobertura
- Atrasos
- Mensagens de ação
- Finalização
- Confirmação automática

O gráfico de Gantt é uma ferramenta útil se desejar exibir o impacto do uso de mensagens de ação.

#### <a name="navigation-in-the-gantt-chart"></a>Navegação no gráfico de Gantt

- Para expandir o grupo selecionado e mostrar os detalhes, selecione o sinal de adição (**+**) no modo de exibição de árvore.
- Para recolher o grupo selecionado, selecione o sinal de subtração (**–**) no modo de exibição de árvore.
- Você pode usar o teclado para a navegação. Use as teclas **Seta para cima** e **Seta para baixo** para mover-se entre linhas. Use as teclas **Seta para a direita** e **Seta para a esquerda** para expandir e recolher grupos.
- Para abrir ou fechar todos os níveis no gráfico de Gantt, **Expandir tudo** ou **Recolher tudo**.
- Para exibir o tempo de processamento relacionado, passe o mouse sobre uma tarefa. (As tarefas estão no nível mais baixo no gráfico Gantt).

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a>Exibir uma execução do planejamento mestre adicional para comparar trabalhos

Ao selecionar um trabalho de planejamento mestre no campo **Mostrar execução de planejamento mestre adicional**, você poderá exibir uma exibição de planejamento mestre adicional no gráfico de Gantt e comparar os dois trabalhos.

#### <a name="bom-level-display"></a>Exibição do nível de BOM

Os níveis de lista de materiais (BOM) são mostrados de forma diferente para planejamento de cobertura, atrasos, ações e confirmação.

- **Planejamento de cobertura** – os níveis de BOM são mostrados conforme esperado. Eles são calculados de cima para baixo.

    **Exemplo:** nível 0, 1, 2 de BOM

- **Atrasos** – os níveis de BOM são mostrados como os níveis de BOM de planejamento de cobertura multiplicados por –1. (Ou seja, eles têm um sinal negativo).

    **Exemplo:** nível –2, –1, 0 de BOM

- **Mensagem de ação** – os níveis de BOM são mostrados conforme esperado. Eles são calculados de cima para baixo.

    **Exemplo:** nível 0, 1, 2 de BOM

- **Confirmação automática** – os níveis de BOM são mostrados como 999 menos o nível de BOM de planejamento de cobertura.

    **Exemplo:** nível 999, 998, 997 de BOM

A tabela a seguir resume o comportamento.

| Nível de BOM que é mostrado | Item final | Subcomponente | Matéria-prima |
|---|---|---|---|
| Planejamento de cobertura | 0 | 1 | 2 |
| Atrasos | 0 | –1 | –2 |
| Mensagem de ação | 0 | 1 | 2 |
| Confirmação automática | 999 | 998 | 997 |

#### <a name="visualize-progress"></a>Visualizar progresso

Se você exibir um trabalho de planejamento mestre que esteja em execução, o andamento será mostrado por meio de cores no gráfico de Gantt. As cores a seguir se aplicam ao tema azul. Para outros temas de cor, as cores serão diferentes.

- **Azul escuro** – tarefas de planejamento concluídas.
- **Laranja** – a tarefa que está em andamento.
- **Azul claro** – a estimativa para as tarefas restantes.

A cor é mostrada somente no nível mais baixo no gráfico de Gantt. Selecione **Expandir tudo** para exibir todas as tarefas no trabalho de planejamento mestre. A estimativa de tarefas restantes se baseia em trabalhos históricos de planejamento mestre.

## <a name="run-master-planning-and-track-processing-time"></a>Executar o planejamento mestre e controlar o tempo de processamento

1. No painel padrão, selecione **Planejamento mestre**.
1. No campo **Plano**, insira ou selecione um valor.
1. Selecione **Executar**.
1. Defina a opção **Controlar tempo de processamento** como **Sim**.
1. No campo **Número de threads**, insira um número.
1. Na Guia Rápida **Registros a incluir**, selecione **Filtro**.
1. Na grade, selecione a linha em que o campo **Campo** é definido como **Número do item**.
1. No campo **Critérios**, insira um valor.
1. Selecione **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]