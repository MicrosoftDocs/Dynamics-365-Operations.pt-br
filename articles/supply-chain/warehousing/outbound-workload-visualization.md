---
title: Visualização da carga de trabalho de saída
description: Este tópico fornece informações sobre a visualização de carga de trabalho de saída. Essa funcionalidade permite que os gerentes e supervisores de depósito criem gráficos de carga de trabalho personalizados que podem ser usados para monitorar o andamento do trabalho atual e a quantidade restante dele. Os gerentes de depósito podem criar várias exibições e configurar a atualização automática, conforme necessário.
author: Mirzaab
manager: tfehr
ms.date: 08/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-08-28
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: cbfb395c9103ff31979bfd57333f689e38915652
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645419"
---
# <a name="outbound-workload-visualization"></a>Visualização da carga de trabalho de saída

[!include [banner](../includes/banner.md)]

Recursos de configuração avançados acessíveis por meio da página **Visualização de carga de trabalho de saída** permitem que os gerentes e supervisores de depósito criem gráficos de carga de trabalho personalizados que podem ser usados para monitorar o andamento do trabalho atual e a quantidade restante dele. Os gerentes de depósito podem criar várias exibições e configurar a atualização automática, conforme necessário. As visualizações de cargas de trabalho de saída são adequadas para exibição em páginas de desempenho de depósito.

Essa funcionalidade pode ser usada para acompanhar o andamento do trabalho de separação. O recurso está integrado ao gerenciamento de mão de obra e, se este estiver configurado, as visualizações de cargas de trabalho de saída poderão mostrar um cálculo do número de horas restantes para o trabalho de separação exibido (filtrado).

## <a name="turn-on-the-outbound-workload-visualization-feature"></a>Ativar o recurso Visualização de carga de trabalho de saída

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações do [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Visualização de carga de trabalho de saída*

## <a name="set-up-outbound-workload-visualizations"></a>Configurar visualizações de cargas de trabalho de saída

Para configurar suas visualizações, crie uma coleção de filtros (exibições) e projete cada filtro para que ele mostre um tipo diferente de análise. Use a página **Configurar filtros** para projetar os filtros.

Para configurar uma visualização de carga de trabalho de saída, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Relatórios de monitoramento de depósito \> Visualização de carga de trabalho de saída**.

    A página **Visualização de carga de trabalho de saída** será exibida. Depois que você criar alguns filtros, essa página mostrará sua visualização. Você pode criar quantos filtros desejar. Todos os filtros criados por você são salvos na sua conta de usuário, para que possa usá-los posteriormente. Em outras palavras, cada usuário terá seu próprio conjunto de filtros que criou. Esses filtros não serão compartilhados com outros usuários.

1. Na página **Visualização de carga de trabalho de saída**, no Painel de Ações, na guia **Filtros**, selecione **Configurar filtros**.
1. Na página **Configurar filtros**, no Painel de Ações, selecione **Novo** para adicionar um filtro e, em seguida, defina os seguintes campos para ele:

    - **Tabela de grupos do eixo X** – Selecione a tabela que contém o campo que deve ser usado para agrupar os valores do eixo X.
    - **Campo de grupos do eixo X** – Dentre os campos da tabela que você selecionou no campo **Tabela de grupos do eixo X**, selecione aquele que deve ser usado para agrupar os valores do eixo X.
    - **Tabela de valores do eixo X** – Selecione a tabela que contém o campo que deve ser usado para analisar mais profundamente os grupos.
    - **Campo de valores do eixo X** – Dentre os campos da tabela que você selecionou no campo **Tabela de valores do eixo X**, selecione aquele que fornece os valores que devem ser analisados para cada grupo.
    - **Atualização automática** – Selecione se a visualização deve ser atualizada automaticamente.
    - **Intervalo de atualização (minutos)** – Insira o número de minutos entre as atualizações automáticas.
    - **Nível de exibição** – Selecione se o gráfico deve mostrar linhas abertas ou contagens de cabeçalho abertas.
    - **Tipo de separação** – Se você definir o campo **Nível de exibição** como _Linhas abertas_, selecione se a contagem de linhas de trabalho abertas no gráfico deve incluir separações iniciais, separações preparadas ou ambas.
    - **Site** – Selecione o site para o qual carregar o gráfico.
    - **Depósito** – Selecione o depósito para o qual carregar o gráfico.
    - **Dias a incluir** – Insira o número de dias no passado para o qual o gráfico deve ser gerado.
    - **Tipo de ordem de serviço** – Selecione os tipos de ordem de serviço de saída a serem filtrados.

    ![Página Configurar filtros](media/work-viz-filters-1.png "Página Configurar filtros")

1. Feche a página **Configurar filtros** para retornar à página **Visualizações de cargas de trabalho de saída**.

    A página **Visualizações de cargas de trabalho de saída** agora mostra dados baseados nas suas novas configurações de filtro. O novo filtro já está disponível e está selecionado no campo **Filtro**. Os seguintes campos estão disponíveis na parte superior do gráfico:

    - **Filtro** – Este campo inclui todos os filtros que você criou até agora. Selecione um filtro para exibir seus dados no gráfico.
    - **Última atualização** – Este campo mostra a data e a hora da última atualização das informações do gráfico.
    - **Tempo estimado/real** – Se os padrões de mão de obra estiverem configurados no sistema, defina esta opção como *Sim* para mostrar os tempos de separação estimados acumulados na parte superior de cada coluna no gráfico. Se você não estiver usando padrões de mão de obra, essa opção não estará disponível.

    ![Visualização de exemplo](media/work-viz-chart.png "Visualização de exemplo")

1. Selecione qualquer barra no gráfico para exibir os detalhes da linha de trabalho associada.

    ![Detalhes da linha de trabalho](media/work-viz-work-details.png "Detalhes da linha de trabalho")

## <a name="example-outbound-workload-visualization-for-zones"></a>Exemplo: Visualização de carga de trabalho de saída para zonas

Para este exemplo, você deseja configurar uma visualização que mostre linhas de trabalho para cada zona e o status de cada linha de trabalho (_Aberta_, _Fechada_ ou _Cancelada_). Nesse caso, você pode configurar um filtro que tenha as seguintes configurações:

- **Nome do filtro** – Insira um nome para o filtro (como _Zona vs. Status do trabalho_).
- **Descrição** – Insira uma breve descrição para o filtro (como _Zona vs. Status do trabalho_).
- **Tabela de grupos do eixo X** – Selecione _Locais_.
- **Grupo do eixo X** – Selecione _ID da zona_.
- **Tabela de valores do eixo X** – Selecione _Trabalho_, pois você deseja exibir trabalhos por zona.
- **Campo de valores do eixo X** – Selecione _Status do trabalho_, pois você deseja exibir o status do trabalho.
- **Atualização automática** – Selecione se a visualização deve ser atualizada automaticamente.
- **Tipo de separação** – Selecione _Separações iniciais e separações preparadas_, pois você deseja incluir as separações iniciais e as separações dos locais de preparo. Em outras palavras, você essencialmente deseja incluir todas as suas linhas de trabalho de separação.
- **Nível de exibição** – Selecione _Linhas abertas_, pois você deseja exibir as informações por linha, não por cabeçalho de trabalho.

A ilustração a seguir mostra um exemplo do gráfico resultante.

![Visualização Zona vs. Status do trabalho](media/work-viz-chart.png "Visualização Zona vs. Status do trabalho")

Este gráfico mostra duas zonas chamadas **FLOOR** e **BULK**, além de uma zona chamada **Em branco**. A zona **Em branco** representa todas as linhas de trabalho que não são membros de nenhuma zona. O gráfico sempre mostra todos os dados filtrados não relacionados como **Em branco**, para fornecer o máximo de visibilidade possível. Na zona **FLOOR**, o gráfico mostra três linhas fechadas e quatro linhas abertas. Na zona **BULK**, o gráfico mostra quatro linhas fechadas, uma linha aberta e 24 linhas canceladas. Por fim, o gráfico mostra oito linhas fechadas que não fazem parte de nenhuma zona e, portanto, são listadas como **Em branco**.
