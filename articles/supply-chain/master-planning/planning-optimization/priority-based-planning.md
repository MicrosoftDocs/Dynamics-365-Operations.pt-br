---
title: Planejamento baseado em prioridade
description: Este artigo descreve o recurso de planejamento baseado em prioridade do Microsoft Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 4997ba123f105f683daaa6b29fe8c5ee72cb47cb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873801"
---
# <a name="priority-based-planning"></a>Planejamento baseado em prioridade

[!include [banner](../../includes/banner.md)]

Este artigo descreve o recurso de planejamento baseado em prioridade do Microsoft Dynamics 365 Supply Chain Management. O recurso adiciona o suporte para planejamento orientado por demanda, que é uma etapa do planejamento de requisitos de material (DDMRP) por demanda. O planejamento baseado em prioridade permite que a Otimização do Planejamento gere ordens planejadas que são controladas por prioridades de planejamento em vez de datas de requisito.

O planejamento baseado em prioridade permite priorizar as ordens de reabastecimento para garantir que a demanda urgente seja priorizada em relação à demanda menos importante. Por exemplo, uma ordem de reabastecimento de estoque será priorizada em uma ordem de reabastecimento de reabastecimento padrão. O sistema pode dividir automaticamente ordens maiores em ordens menores separadas em que as linhas da ordem são agrupadas por prioridade. Em seguida, ele pode processar todas as ordens de alta prioridade primeiro.

Para obter uma visão geral rápida deste recurso, consulte o seguinte vídeo: [Suporte à otimização de planejamento para planejamento baseado em prioridade no Dynamics 365 Supply Chain Management](https://youtu.be/GmMHzFETTQc).

## <a name="turn-on-priority-based-planning-in-your-system"></a>Ativar o planejamento baseado em prioridade no seu sistema

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Planejamento mestre*
- **Nome do recurso:** *Suporte ao MRP baseado em prioridade para a Otimização de Planejamento*

## <a name="where-and-how-planning-priorities-are-assigned"></a>Onde e como as prioridades de planejamento são atribuídas

As informações de *Prioridade de planejamento* sobre fornecimento e demanda são a base do planejamento baseado em prioridade. A prioridade de planejamento define a importância de uma linha de fornecimento ou de uma demanda. A Otimização de Planejamento a utiliza quando o campo **Código de cobertura** está definido como *Prioridade*.

A prioridade de planejamento geralmente é um número entre 0 (zero) e 100, em que 0 representa a maior importância. Ela é exibida e definido no campo **Prioridade de planejamento**. Este campo pode ser encontrado nas seguintes páginas: **Linhas de previsão de demanda**, **Detalhes da ordem de venda**, **Detalhes da ordem de compra**, **Detalhes da ordem de transferência** e **Detalhes da ordem planejada**.

Quando o campo **Código de cobertura** para o item ou grupo de cobertura relevante é definido como *Prioridade*, a Otimização de Planejamento equilibra o suprimento com a demanda usando uma abordagem orientada por demanda, pois ela calcula a prioridade de planejamento e, para cada produto liberado, considera os valores definidos para os campos **Mínimo**, **Ponto de reabastecimento** e **Máximo** na página **Cobertura de item**.

> [!NOTE]
> O valor *Prioridade* está disponível para o campo **Código de cobertura** somente quando a Otimização do Planejamento está habilitada.

Os *modelos de prioridade de planejamento* relacionados controlam a prioridade de planejamento e dividem ordens planejadas por intervalo de prioridade. Eles também permitem definir valores de prioridade de planejamento padrão para cada tipo de fornecimento ou demanda, e definir o método de cálculo de prioridade.

## <a name="types-of-priority-calculation-methods"></a>Tipos de métodos de cálculo de prioridade

Cada modelo de prioridade de planejamento tem uma configuração de **Método de cálculo de prioridade** que controla como o planejamento mestre aplica a prioridade a ordens planejadas. Os valores disponíveis são *Porcentagem da quantidade máxima de estoque* e *Intervalos de prioridade*. Os *intervalos de prioridade* representam uma versão mais avançada do método *Porcentagem da quantidade máxima de estoque*.

### <a name="percent-of-maximum-inventory-quantity"></a>Porcentagem da quantidade máxima de estoque

No método de cálculo *Porcentagem da quantidade máxima de estoque*, o cálculo da prioridade de fornecimento encontra o *estoque total disponível* atual (fluxo líquido) como uma porcentagem do valor da **Quantidade máxima de estoque** definido para um item. Uma única ordem planejada é criada por item e fornecedor (a menos que a quantidade de ordem máxima seja usada para forçar uma divisão). A prioridade de planejamento da ordem é calculada como uma porcentagem do máximo.

Esta é a fórmula usada:

*Porcentagem máxima* = (*posição de fluxo líquido* × 100) ÷ *Valor de quantidade máxima de estoque da cobertura do item*

Nessa fórmula, a *Posição de fluxo líquido* é calculada da seguinte maneira:

*Posição de fluxo líquido* = *Disponível* + *Sob encomenda* – *Demanda qualificada*

- *Sob encomenda* é o fornecimento esperado.
- A *demanda qualificada* representa os requisitos líquidos com a data do requisito no limite de tempo de planejamento.

Durante a execução do planejamento mestre, novas ordens planejadas são criadas quando a posição do fluxo líquido é menor que a quantidade do ponto de reabastecimento de um item. A quantidade da ordem planejada é a diferença entre o valor da **Quantidade máxima de estoque** definido no nível do item e a posição do fluxo líquido. A prioridade da ordem planejada é calculada como uma porcentagem de *posição de fluxo líquido* do valor da **Quantidade máxima de estoque**.

> [!NOTE]
> A prioridade calculada não poderá ser negativa, mesmo se a demanda exceder o total de fornecimento. Se a demanda exceder o total de fornecimento, a prioridade calculada será definida como 0 (zero).

### <a name="priority-ranges"></a>Intervalos de prioridade

O método de cálculo de *Intervalos de prioridade* é mais avançado do que o método *Percentual da quantidade máxima de estoque* e é configurado no nível do modelo de prioridade de planejamento. Várias ordens de fornecimento planejadas podem ser criadas para atender à demanda por item. As prioridades do fornecimento planejado seguem os valores definidos na grade **Intervalos de prioridades de planejamento** na página **Modelos de prioridade de planejamento**.

As seguintes regras adicionais entram em vigor quando o campo **Método de cálculo de prioridade** é definido como *Intervalos de prioridade*:

- Se a opção **Considerar prioridade de demanda** para o modelo de prioridade planejada for definida como *Sim*, a prioridade definida em cada linha de demanda limitará o bucket de intervalo de prioridade. A prioridade de qualquer nova ordem planejada para fornecimento não será menor do que a prioridade da demanda. O valor superior do intervalo é considerado um limite para o qual o valor de prioridade da demanda é comparado. Se a prioridade da demanda estiver exatamente no meio entre os valores de limite superior de dois intervalos, o intervalo com a prioridade mais alta (ou seja, o menor valor de prioridade) será selecionado.
- Se o campo **Criação de ordem planejada** para o modelo de prioridade planejada estiver definido como *Fornecimento único com a prioridade mais importante*, somente um fornecimento será criado para atender até o máximo. A prioridade será definida como a prioridade do primeiro intervalo que disparará uma fonte.
- Se não houver estoque disponível, fornecimento e demanda, a linha na grade **Intervalos de prioridade de planejamento** onde o campo **Quantidade inicial** é definido como *Zero* será usada.
- Se não houver demanda, mas nenhum estoque disponível ou fornecimento esperado, a linha na grade **Intervalos de prioridade de planejamento** onde o campo **Quantidade inicial** é definido como *Zero ou menos* será usada.
- Quando o intervalo do qual a demanda faz parte for avaliado, a definição da opção **Considerar prioridade de demanda** ainda terá efeito.

## <a name="differences-between-traditional-timeline-calculations-and-priority-based-planning"></a>Diferenças entre cálculos tradicionais de linha de tempo e planejamento baseado em prioridade

O planejamento baseado em prioridade é diferente dos cálculos de linha de tempo tradicionais das seguintes maneiras:

- Todos os processadores de planejamento prévio regulares ainda estão em vigor. Esses pré-processadores incluem a vinculação de ordens planejadas aprovadas em relação à demanda de vendas, o mapeamento de requisição de compra e a lógica de reserva. Somente a demanda que é atendida por esses processadores é processada.
- Durante a vinculação, todo o fornecimento é considerado, independentemente da prioridade. Esse fornecimento inclui estoque disponível, fornecimento liberado e a parte não vinculada de ordens planejadas aprovadas.
- Nenhuma demanda de "dias negativos" pode ser vinculada ao fornecimento durante o tempo de cobertura.
- Quando o fornecimento é vinculado à demanda, o fornecimento com a maior prioridade (ou seja, o menor valor de prioridade) é usado primeiro. O fornecimento disponível é considerado um valor de prioridade 0 (zero). Portanto, ele será consumido como a primeira fonte.
- As novas linhas de fornecimento planejadas serão criadas de acordo com as regras normais para o tamanho mínimo da ordem, o tamanho máximo da ordem, o múltiplo da quantidade e assim por diante.

## <a name="planning-priority-models"></a>Modelos de prioridade de planejamento

Os *modelos de prioridade de planejamento* são atribuídos a grupos de cobertura e controlam a prioridade de planejamento para ordens planejadas. Eles definem a lógica que determina como o valor de prioridade de planejamento é calculado para cada ordem planejada e como a prioridade é atribuída a ordens planejadas, linhas de fornecimento e linhas de demanda.

Para trabalhar com os modelos de prioridade de planejamento, acesse **Planejamento mestre \> Configuração \> Modelos de prioridade de planejamento**. Como foi discutido anteriormente, uma das configurações mais importantes de um modelo é o valor do **Método de cálculo de prioridade**. Esta configuração controla o método de cálculo usado quando o planejamento mestre atribui um valor de prioridade a ordens planejadas.

> [!NOTE]
> Os modelos de prioridade de planejamento são aplicados na organização inteira, em todas as entidades legais.

### <a name="coverage-group"></a>Grupo de cobertura

Configure um novo grupo de cobertura que você pretende usar para planejamento baseado em prioridade, conforme descrito em [Definir regras de cobertura para itens](../tasks/define-coverage-rules-items.md). Depois de criar o grupo de cobertura, defina os seguintes campos adicionais:

- **Código de cobertura** – selecione *Prioridade* se o grupo de cobertura usar o planejamento baseado em prioridade.
- **Modelo de prioridade de planejamento** – selecione um modelo de prioridade de planejamento para a organização inteira.

### <a name="item-coverage"></a>Cobertura do item

Defina as configurações de cobertura de item, conforme descrito em [Configurações de cobertura](../coverage-settings.md). Por padrão, o valor de **Código de cobertura** selecionado para o grupo de cobertura é copiado para as configurações de cobertura de item. No entanto, você pode substituir o valor padrão conforme desejado. Em alguns casos, o campo **Código de cobertura** de um registro de cobertura de item é definido como *Planejamento*, mas nenhum modelo de prioridade de planejamento é definido para o grupo de cobertura relacionado. Nesses casos, qualquer modelo em que o campo **Método de cálculo de prioridade** seja definido como *Porcentagem da quantidade máxima de estoque* e o campo **Criação de ordem planejada** seja definido como *Fornecimento único com a prioridade mais importante*, será aplicado por padrão.

Defina o campo **Código de cobertura** como *Prioridade* para disponibilizar o campo **Ponto de reabastecimento** nas configurações de cobertura de item. Neste campo, insira a quantidade de pontos de reabastecimento que o sistema deve usar ao determinar quando criar ordens planejadas com um valor de **Código de cobertura** de *Prioridade*.

A quantidade de pontos de reabastecimento geralmente é calculada como a demanda durante o prazo de entrega mais um valor mínimo (estoque de segurança). Ela deve ser um valor entre os valores **Mínimo** e **Máximo**.

Por exemplo, você pode definir os campos da seguinte maneira:

- **Mínimo:** *10*
- **Ponto de reabastecimento:** *45*
- **Máximo:** *60*

Para este exemplo, a quantidade de pontos de reabastecimento se baseia em um prazo de entrega de sete dias e um uso médio diário de 5. Portanto, a demanda durante o prazo de entrega é 35. O valor mínimo de 10 (estoque de segurança) é adicionado para obter um ponto de reabastecimento de 45. Quando esta configuração for usada, o fornecimento será sugerido quando o nível disponível projetado for inferior a 45. A prioridade da ordem será baseada na configuração da prioridade de planejamento.

### <a name="manage-planning-priority-models"></a>Gerenciar modelos de prioridade de planejamento

Para trabalhar com os modelos de prioridade de planejamento, siga estas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Modelos de prioridade de planejamento**.
1. Selecione um modelo existente no painel de lista ou selecione **Novo** no Painel de Ações para criar um novo modelo.
1. No cabeçalho do registro, defina os seguintes campos:

    - **Nome** – insira um nome do modelo. O nome deve ser exclusivo entre todas as entidades legais da organização.
    - **Descrição** – insira uma descrição do modelo.
    - **Método de cálculo de prioridade** – selecione um dos seguintes valores:

        - *Intervalos de prioridade* – quando você seleciona este valor, a grade **Intervalos de prioridade de planejamento** é disponibilizada. Nela, você deve estabelecer vários intervalos de prioridade para definir o valor de prioridade de planejamento.
        - *Porcentagem da quantidade máxima de estoque* – calcule o valor da prioridade de planejamento como uma porcentagem, com base no nível de estoque projetado sobre a quantidade de estoque máxima.

    - **Criação de ordens planejadas** – este campo é disponibilizado quando o campo **Método de cálculo de prioridade** é definido como *Intervalos de prioridade*. Selecione um dos seguintes valores:

        - *Fornecimento único com prioridade mais importante* – não divida ordens planejadas com base no intervalo de prioridades. A prioridade de planejamento para uma ordem planejada se baseia no intervalo de prioridade mais importante (ou seja, o menor valor de prioridade de planejamento).
        - *Dividir de acordo com intervalos de prioridade* – divida a demanda em várias ordens planejadas, com base nos intervalos de prioridade de planejamento. A prioridade de planejamento para ordens planejadas individuais é definida pela prioridade de planejamento do intervalo de prioridades de planejamento relacionado.

    - **Considerar prioridade de demanda** – defina esta opção como *Sim* para limitar a prioridade de uma nova ordem planejada criada para fornecimento. (A prioridade não será inferior à prioridade da demanda relacionada). Se você definir esta opção como *Não*, a prioridade da ordem de demanda não será considerada quando a prioridade da ordem de suprimento for calculada.

1. Se você definir o campo **Método de cálculo de prioridade** como *Intervalos de prioridades*, use os botões **Adicionar** e **Remover** na barra de ferramentas da FastTab **Intervalos de prioridade de planejamento** para adicionar ou remover linhas de intervalo de prioridade conforme necessário. Se houver várias linhas e você inserir uma nova linha, a prioridade de planejamento será definida automaticamente como a média da linha selecionada e a linha acima dela. Para cada linha, defina os seguintes campos:

    - **Prioridade de planejamento** – Insira um valor entre 0,00 e 100,00. Esse valor representa a prioridade de planejamento usada para a linha. O menor valor de prioridade representa a maior prioridade. Um valor padrão é atribuído, mas você pode alterá-lo, conforme necessário. O mesmo valor de **Prioridade de planejamento** não pode ser usado para mais de um intervalo de prioridades de planejamento no mesmo modelo de prioridade de planejamento.
    - **Descrição** – insira uma descrição do intervalo de prioridades de planejamento (por exemplo, o *Ponto de reabastecimento como Máximo*).
    - **Quantidade inicial** – o limite inferior do intervalo de prioridades de planejamento. Esse valor é somente leitura e é baseado nos valores **Quantidade final** e **Porcentagem até quantidade** para o intervalo de prioridades de planejamento anterior.
    - **Quantidade final** – selecione o campo da cobertura do item que deve ser usado para definir o limite superior do intervalo. Os seguintes valores têm suporte e influenciarão o valor de **Quantidade inicial** do próximo intervalo:

        - *Zero* – esse valor representa um intervalo de negativo a zero (*Zero ou menos* até *Zero*). Para linhas em que esse valor é selecionado, o campo **Porcentagem até quantidade** é somente leitura e é sempre definido como *100* por cento.
        - *Quantidade mínima de estoque* – esse valor representa o valor **Mínimo** de um item na página **Cobertura de item**. Para as linhas em que esse valor é selecionado, o campo **Porcentagem até quantidade** é editável e usado para definir o valor **Quantidade inicial** do próximo intervalo (por exemplo, como *80% da quantidade mínima de estoque*).
        - *Ponto de reabastecimento* – esse valor representa o valor **Ponto de reabastecimento** de um item na página **Cobertura de item**. Para as linhas em que esse valor é selecionado, o campo **Porcentagem até quantidade** é editável e usado para definir o valor **Quantidade inicial** do próximo intervalo (por exemplo, como *80% do Ponto de reabastecimento*).
        - *Quantidade máxima de estoque* – esse valor representa o valor **Máximo** de um item na página **Cobertura de item**. Para as linhas em que esse valor é selecionado, o campo **Porcentagem até quantidade** é editável e usado para definir **Quantidade inicial** do próximo intervalo (por exemplo, como *80% da quantidade mínima de estoque*).
        - *Infinito* – esse valor representa um nível superior infinito do intervalo (*Infinito ou menos* até *Infinito*). Para linhas em que esse valor é selecionado, o campo **Porcentagem até quantidade** é somente leitura e é sempre definido como *100* por cento.

    - **Porcentagem até quantidade** – Insira um valor percentual usado para calcular o limite superior do intervalo de prioridades de planejamento, com base no valor selecionado no campo **Quantidade final**. Por exemplo, se o campo **Quantidade final** for definido como *Quantidade mínima de estoque* e o campo **Porcentagem até quantidade** for definido como *50*, o limite superior será de 50% da quantidade mínima de estoque da cobertura de item relacionada.

1. Na FastTab **Padrões de prioridade de planejamento**, defina os campos conforme necessário para definir as prioridades de planejamento padrão para cada tipo de ordem ou de linha de demanda (ordens de venda, ordem de compra, ordem de transferência ou previsão de demanda). Somente valores positivos podem ser inseridos.

## <a name="view-and-maintain-planning-priority"></a>Exibir e manter a prioridade de planejamento

A prioridade de planejamento é mostrada e definida no campo **Prioridade de planejamento**. Este campo pode ser encontrado nas páginas listadas na tabela a seguir. A prioridade é definida como um número entre 0 (zero) e 100, em que 0 representa a maior importância.

| Página | Localização do campo | Origem do valor |
|---|---|---|
| LInhas de previsão de demanda | <p>Guia **Item**</p><p>(Selecione uma linha na seção superior e, depois, a guia **Item**.)</p> | Valor padrão ou valor que é definido manualmente |
| Detalhes da Ordem de Venda | <p>Guia **Entrega** na FastTab **Detalhes da linha**</p><p>(Selecione uma linha na FastTab **Linhas da ordem de venda** e, depois, na FastTab **Detalhes da linha**, selecione a guia **Entrega**.)</p> | Valor padrão, valor da intercompanhia ou valor que é definido manualmente |
| Detalhes da ordem de compra | <p>Guia **Entrega** na FastTab **Detalhes da linha**</p><p>(Selecione uma linha na FastTab **Linhas da ordem de compra** e, depois, na FastTab **Detalhes da linha**, selecione a guia **Entrega**.)</p> | Valor definido durante a confirmação das ordens planejadas, valor da intercompanhia ou valor definido manualmente |
| Detalhes da ordem de transferência | <p>Guia **Entrega** na FastTab **Detalhes da linha**</p><p>(Selecione uma linha na FastTab **Linhas da ordem de transferência** e, depois, na FastTab **Detalhes da linha**, selecione a guia **Entrega**.)</p> | Valor definido durante a confirmação das ordens planejadas ou valor definido manualmente |
| Detalhes da Ordem Planejada | FastTab **Geral** | Valor calculado durante o planejamento mestre ou o valor que é definido manualmente |

### <a name="intercompany-trade"></a>Comércio intercompanhia

O valor **Prioridade de planejamento** nas linhas de fornecimento e de demanda intercompanhia é compartilhado entre as entidades vinculadas. A modificação em ambos os lados será refletida na linha da ordem vinculada.

Veja alguns exemplos:

- Um usuário altera a prioridade de planejamento de uma linha da ordem de venda intercompanhia de 20 para 30. Essa alteração é refletida na linha da ordem de compra intercompanhia vinculada.
- Um usuário altera a prioridade de planejamento de uma linha da ordem de compra intercompanhia de 40 para 50. Essa alteração é refletida na linha da ordem de venda intercompanhia vinculada.
