---
title: Agendar ordens de serviço
description: Este tópico explica como agendar ordens de serviço no Gerenciamento de Ativo.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a594bacb1fcf53ae4a278dbb26f1de174e22288c
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275593"
---
# <a name="schedule-work-orders"></a>Agendar ordens de serviço

[!include [banner](../../includes/banner.md)]

 

Este tópico explica como agendar ordens de serviço no Gerenciamento de Ativo. 

O número necessário de horas para uma ordem de serviço é definido pela soma das horas previstas menos as horas lançadas. Se mais tempo for necessário, a previsão deve ser ajustada de acordo. Em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**, você pode exibir ou editar previsões em uma ordem de serviço selecionando ordem de serviço e clicando em **Previsão** na guia **Ordem de serviço**. Quando ordens de serviço foram criadas e estimadas, a próxima etapa para concluir ordens de serviço é alocar os funcionários de manutenção necessários e ferramentas.

Somente ordens de serviço com um estado de ciclo de vida da ordem de serviço que permite agendamento podem ser agendadas. Permitir agendamento é configurado na Guia Rápida **Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Estados de ciclo de vida** > **Geral** > **Permitir agendamento**.

1. Clique em **Gerenciamento de ativo** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço**.

2. Selecione as ordens de serviço que deseja agendar na lista. Por exemplo, você pode classificar a lista por **Estado do ciclo de vida atual**.

3. Na guia **Geral**, clique em **Agenda**.

4. Na caixa de diálogo **Agendar ordens de serviço**, você pode adicionar seleções com relação a data de início esperada e nível de serviço, se necessário. Se o processo de agendamento respeitar as limitações de capacidade em relação aos recursos já agendados em outros trabalhos, verifique se os botões de alternância **Ativo**, **Ferramenta** e **Trabalhador** estão definidos como "Sim".

    [!NOTE]
    Se você definir o **Ativo**, **Ferramenta** e os botões de alternância **Trabalhador** como "Não", reservas existentes serão ignoradas. No Log de Informações, uma lista de agendamentos de ordem de serviço sobrepostas será exibida, e você pode clicar nas mensagens para abrir uma ordem de serviço e reagendar, se necessário.

5. Para ver informações detalhadas sobre o processo de agendamento, selecione "Sim" no botão de alternância **Detalhado**. Isso significa que informações detalhadas sobre as pontuações calculadas nas ordens de serviço e funcionários de manutenção serão exibidas no Log de Informações.

6. Clique em **OK** para iniciar o processo de agendamento.

7. Quando o planejamento é concluído, um Log de informações mostra o número de ordens de serviço programadas, e também informações mais detalhadas se o botão de alternância **Detalhamento** foi definido como "Sim".

>[!NOTE]
>As ordens de serviço são agendadas em um ciclo por ordem de serviço, não por trabalho de ordem de serviço. Você também pode abrir a caixa de diálogo **Agendar ordens de serviço** diretamente em **Gerenciamento de ativos** > **Periódico** > **Ordens de serviço** > **Agendar ordens de serviço**. Faça suas seleções e clique em **OK** para iniciar o planejamento de trabalho. É possível configurar o agendamento de ordem de serviço em lotes na caixa de diálogo **Agendar ordens de serviço** > na Guia Rápida **Executar em segundo plano**.

*Exemplo:* na figura abaixo, a fórmula inserida no campo **Início esperado** gera o agendamento de ordem de serviço para todas as ordens de serviço com data de início esperada uma semana a partir de agora e posteriormente. Essa fórmula pode ser útil quando você executa a ordem de serviço sempre, mas deseja se certificar que as ordens de serviço agendadas para os próximos 5-6 dias não sejam reagendadas.

![Figura 1](media/03-work-order-scheduling.png)

O tipo de ordem de serviço relacionado a ordens de serviço pode configurar o plano para um funcionário de manutenção (botão de alternância**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Tipos de ordem de serviço** > **Um funcionário de manutenção** definido como "Sim"). Isso significa que se o tipo de ordem de serviço é usado em uma ordem de serviço, o botão de alternância **Um funcionário de manutenção** é definido automaticamente como "Sim" automaticamente na página de detalhes **Todas as ordens de serviço** > **Cabeçalho** > exibir Guia Rápida **Agendar**. Durante o planejamento de ordem de serviço, todos os trabalhos de ordem de serviço criados na ordem de serviço serão agendados subsequentemente ao mesmo funcionário de manutenção. Se necessário, você pode editar a seleção no botão de alternância **Um funcionário de manutenção** em **Todas as ordens de serviço** para permitir o agendamento de vários trabalhadores ou de um trabalhador nos trabalhos da ordem de serviço.

O processo de planejamento no Gerenciamento de Ativos inclui vários fatores no cálculo do agendamento:

- O cálculo de pontuações para ordens de trabalho e funcionários de manutenção. As pontuações de ordens de serviço e funcionários de manutenção são definidas nos **Parâmetros de gerenciamento de ativos**. 
- Verificar a existência de competências correspondentes, o que significa habilidades e certificados, necessários para realizar o trabalho. As habilidades e certificados são configurados nos funcionários de manutenção no módulo **Recursos Humanos** (**Recursos Humanos** > **Trabalhadores** > **Trabalhadores** > selecione o trabalhador na lista > na guia **Trabalhador** > na seção **Competências** > nos botões **Habilidades** e **Certificados**). Além disso, as habilidades e certificados podem ser adicionados nos tipos de trabalho de manutenção e comércios de trabalho de manutenção. Leia mais sobre competências e tipos de trabalho de manutenção em [Categorias do tipo de trabalho e tipos de trabalho de manutenção, grades do tipo de trabalho de manutenção, comércios de trabalho de manutenção e listas de verificação de manutenção](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).  

## <a name="scores-used-in-work-order-scheduling"></a>Contagens usadas no planejamento da ordem de serviço

Calcular pontuações de um trabalho de ordem de serviço baseado em data de início esperada e nível de serviço da ordem de serviço.

Cálculo da **Data inicial**: para cada data futura calculada a partir da data de início esperada, a pontuação de data de início é subtraída e multiplicada pela pontuação, que é de "10" nos exemplos abaixo.

Cálculo de **Gravidade**: pontuação de gravidade multiplicada pela gravidade na ordem de serviço.

Cálculo de **Nível de serviço**: A pontuação do nível de serviço é dividida pelo nível de serviço na ordem de serviço.

Nos exemplos abaixo, a contagem de gravidade é de "2" e as pontuações de nível de serviço são "5" e "100".

**Exemplo 1:**

| ID da ordem de serviço | Data de início esperada | Severidade da ordem de serviço | Nível de serviço da ordem de serviço | Cálculo               | Pontuação      |
|---------------|---------------------|------------------------|--------------------------|---------------------------|------------|
| WO-00010816   | Amanhã            | 2                      | 20              | (-1 \* 10) + (2 \* 2) + 5 / 20     | \- 5.75    |
| WO-00010817   | Dois dias a partir de hoje   | 2                      | 20              | (-2 \* 10) + (2 \* 2) + 5 / 20     | \- 15.75   |
| WO-00010818   | Dois dias a partir de hoje   | 3                      | 5               | (-2 \* 10) + (2 \* 3) + 5 / 5      | \- 13      |

As ordens de serviço serão agendadas na ordem a seguir: WO-000108**16**, WO-000108**18**, WO-000108**17**.

**Exemplo 2:**

| ID da ordem de serviço | Data de início esperada | Severidade da ordem de serviço | Nível de serviço da ordem de serviço | Cálculo                 | Pontuação    |
|---------------|---------------------|------------------------|---------------------|----------------------------------|----------|
| WO-00010816   | Amanhã            | 2                      | 20                  | (-1 \* 10) + (2 \* 2) + 100 / 20 | \- 1     |
| WO-00010817   | Dois dias a partir de hoje   | 2                      | 20                  | (-2 \* 10) + (2 \* 2) + 100 / 20 | \- 11    |
| WO-00010818   | Dois dias a partir de hoje   | 3                      | 5                   | (-2 \* 10) + (2 \* 3) + 100 / 5  | 6        |

Se a pontuação de nível de serviço é aumentada para '100' em vez de '5', a ordem de agendamento será: WO-000108**18**, WO-000108**16**, WO-000108**17**.

As pontuações de classificação relacionadas para calcular quais funcionários de trabalho devem trabalhar nas ordens de serviço são todas definidas como números, que são adicionadas para cada cálculo de ordem de manutenção durante agendamento da ordem de serviço. O funcionário de manutenção com a pontuação mais alta é selecionada na ordem de trabalho. Aqui está uma descrição resumida das pontuações de funcionário de manutenção:

| Pontuação do funcionário de manutenção| Descrição |
|---|---|
| Trabalhador responsável | Se o trabalhador de manutenção for selecionado como funcionário responsável na ordem de serviço, a pontuação é adicionada. |
| Grupo de funcionários de manutenção responsável | Se o funcionário de manutenção for parte do grupo de funcionário de manutenção responsável na ordem de serviço, a pontuação é adicionada. |
| Funcionário de manutenção preferencial         | Se o trabalhador for selecionado como funcionário de manutenção preferido no ativo, a pontuação será adicionada. |
| Grupo de funcionários de manutenção preferencial   | Se o trabalhador for parte do grupo de funcionário de manutenção preferido no ativo, a pontuação será adicionada.  |
| Local  | Se sua empresa usar locais funcionais, os funcionários de manutenção receberão a pontuação total se estiverem no local funcional relacionado ao ativo. Se o local funcional do ativo tiver um local parente, os funcionários de manutenção naquele local funcional obterão 1/2 da pontuação. Se esse local também tiver um responsável, os funcionários de manutenção desse local obterão 1/3 da pontuação. Se esse local também tiver um responsável, os funcionários de manutenção desse local obterão 1/4 da pontuação e assim por diante. Se sua empresa usar o local do ativo, o que não recomendamos, o local, a área e a zona serão usados para calcular pontuações do local. Os trabalhadores receberão a pontuação total se estiverem no local, na área e na zona relacionados ao ativo. Se o local do trabalhador corresponder apenas ao local e à área, a pontuação de classificação para o funcionário de manutenção será 2/3 da pontuação total. Se o local do funcionário de manutenção corresponder apenas ao local, a pontuação de classificação para o funcionário de manutenção será 1/3 da pontuação total. |
| Data inicial do trabalhador  | Para cada data em que a data inicial programada é posterior à data de início esperada, a contagem será subtraída.  |

>[!NOTE]
>Se uma pontuação for definida como “0", a contagem não será calculada. Isso é útil, por exemplo, se você não deseja incluir o trabalhador responsável na programação.

## <a name="competencies-used-in-work-order-scheduling"></a>Competências usadas no planejamento de trabalho

As habilidades e requisitos de certificado podem ser configurados em tipos de trabalho de manutenção (**Gerenciamento de ativos** > **Configuração** > **Trabalhos** > **Tipos de trabalho de manutenção**) e em comércios de trabalho de manutenção (**Gerenciamento de ativos** > **Configuração** > **Trabalhos** > **Comércio de trabalho de manutenção**). 

Tipos de trabalho de manutenção e comércios de trabalho de manutenção são selecionados em trabalhos de ordem de serviço. Se habilidades ou certificados foram selecionados em um tipo de trabalho de manutenção ou comércio de trabalho de manutenção, e se o tipo de trabalho de manutenção ou comércio de trabalho de manutenção é usado em um trabalho de ordem de serviço, apenas funcionários de manutenção com habilidades e certificados que combinam são agendados para trabalhar na ordem de serviço.

<a name="gantt"></a>

## <a name="work-with-scheduled-work-orders-using-a-gantt-chart"></a>Trabalhar com ordens de serviço agendadas usando um gráfico de Gantt

O gráfico de Gantt **Gráfico de Gantt das ordens de serviço agendadas** fornece uma interface gráfica na qual é possível visualizar e reagendar suas ordens de serviço.

Para visualizar e trabalhar com o gráfico de Gantt:

1. Acesse **Gerenciamento de ativos > Ordens de serviço > Gráfico de Gantt das ordens de serviço agendadas**.

1. Use as listas suspensas e os campos na seção **Configurações** para configurar qual local funcional, intervalo de tempo e escala de tempo a serem exibidos no gráfico de Gantt.

1. Selecione **Aplicar**.

    - O gráfico de Gantt é atualizado para mostrar as ordens de serviço agendadas que correspondem às suas configurações. Cada ordem de serviço é representada por um retângulo azul.
    - Para reagendar uma ordem de serviço exibida, selecione e arraste-a para a nova data e hora apropriadas.

1. Se você fez alguma alteração, selecione **Salvar** no painel de ações para salvá-las.
