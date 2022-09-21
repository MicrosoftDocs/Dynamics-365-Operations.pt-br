---
title: Perfil e níveis de buffer
description: Este artigo fornece informações sobre perfis e níveis de buffer, que determinam os níveis de estoque mínimo e máximo que devem ser mantidos para cada ponto de separação.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 57ee6206da926d0dbf62f562197538bfcdd41148
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428135"
---
# <a name="buffer-profile-and-levels"></a>Perfil e níveis de buffer

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Depois de identificar os pontos de separação (itens principais que você manterá estrategicamente no estoque), você deve decidir quanto estoque (buffer) será mantido em cada um deles. Essa é a segunda etapa do DDMRP (Planejamento de Recursos Materiais Orientado por Demanda).

## <a name="buffer-levels-and-zones"></a>Níveis e zonas de buffer

No DDMRP, cada buffer de estoque é definido usando três valores: a quantidade mínima, a quantidade máxima e o ponto de reabastecimento. Esses valores estabelecem três zonas de diferença, que são identificadas pelos seguintes códigos de cor:

- **Zona vermelha** – a área abaixo da quantidade mínima. A quantidade mínima também é conhecida como "acima do vermelho", e a sua estratégia de planejamento deve ser projetada para garantir que os níveis de estoque estejam sempre acima desse ponto.
- **Zona amarela** – a área entre a quantidade mínima e o ponto de reabastecimento. O ponto de reabastecimento também é conhecido como "acima do amarelo". Quando esse ponto for atingido, o sistema deverá reabastecer.
- **Zona verde** – a área entre o ponto de reabastecimento e a quantidade máxima. A quantidade máxima também é chamada de "acima do verde". Esse ponto é o nível máximo para o qual o estoque será reabastecido.

A ilustração a seguir mostra as três zonas coloridas e como elas se relacionam à quantidade mínima, à quantidade máxima e ao ponto de reabastecimento.

![Níveis e zonas de buffer do DDMRP](media/ddmrp-buffer-levels.png "Níveis e zonas de buffer do DDMRP")

## <a name="calculating-the-buffer-zones"></a>Calculando as zonas de buffer

Esta seção explica como a altura de cada zona de buffer é calculada.

Em geral, a região amarela é calculada primeiro. Essa zona representa a quantidade que você consome a partir do momento em que faz a solicitação até o momento em que o pedido chega. Em outras palavras, é o consumo esperado durante o prazo de entrega de reabastecimento. É calculado usando a seguinte equação:

- **Zona amarela** = *ADU (Uso Diário Médio)* × *Prazo de entrega separado*

O *prazo de entrega separado* representa o tempo necessário para produzir ou receber um item se os pontos de separação estiverem sempre no estoque. Normalmente, é muito menor do que o *prazo de entrega cumulativo* que é tradicionalmente usado no planejamento mestre. As configurações de buffer corretas são a chave para garantir que os pontos de separação sempre estejam no estoque, mas não em excesso.

A zona vermelha é calculada usando as seguintes equações:

- **Base vermelha** = *ADU* × *Prazo de entrega separado* × *Fator de prazo de entrega*
- **Segurança vermelha** = *Base vermelha* × *Fator de variabilidade*
- **Zona vermelha** = *Base vermelha* + *Segurança vermelha*

A zona verde é calculada como resultado máximo das três equações a seguir:

- *Quantidade mínima de ordens*
- *ADU* × *Ciclo da ordem*
- *ADU* × *Prazo de entrega separado* × *Fator de prazo de entrega*

## <a name="calculating-average-daily-usage"></a>Calculando o uso diário médio

O sistema usa uma das três abordagens para calcular o valor que você consome por dia:

- **Uso médio diário (passado)** – essa abordagem se baseia no consumo passado real.
- **Uso médio diário (futuro)** – essa abordagem se baseia no consumo futuro previsto.
- **Uso médio diário (combinado)** – essa abordagem se baseia em uma mistura ponderada de consumo passado e previsto.

### <a name="average-daily-usage-past"></a>Uso diário médio (passado)

O ADU passado é calculado como uma média adicionando as quantidades usadas por dia para um número especificado de dias anteriores e, em seguida, dividindo o total pelo número de dias. A ilustração a seguir mostra como essa abordagem funciona quando o cálculo é de três dias no passado.

![Gráfico de uso diário médio (passado).](media/ddmrp-adu-past.png "Gráfico de uso diário médio (passado)")

Na ilustração anterior, se hoje é a manhã de 11 de junho, o ADU dos três dias anteriores (8, 9 e 10 de junho) é 21.

- **ADU (passado)** = (29 + 11 + 23) ÷ 3 = 21

As transações a seguir são levadas em consideração para o cálculo de uso diário médio (passado):

- Transações que diminuem a quantidade do item (na tabela `inventtrans` em que a quantidade é menor do que zero)
- Transações com um status *Na ordem*, *Encomendado reservado*, *Físico reservado*, *Separado*, *Deduzido* ou *Vendido*
- Transações com data no período anterior escolhido (o uso médio diário após o período)
- Transações que não sejam trabalho de depósito, quarentena, cotações de venda ou instruções (`WHSWork`, `WHSQuarantine`, `SalesQuotation` ou `Statement`)
- Transações que não sejam de transferência de diários que estão na mesma dimensão de cobertura

### <a name="average-daily-usage-forward"></a>Uso diário médio (futuro)

Para um novo produto, talvez você não tenha nenhum dado de uso passado. Nesse caso, você pode usar o ADU projetado para o futuro (por exemplo, com base na demanda prevista). A ilustração a seguir mostra como essa abordagem funciona quando o cálculo é de três dias no futuro (incluindo hoje).

![Gráfico de uso diário médio (futuro).](media/ddmrp-adu-forward.png "Gráfico de uso diário médio (futuro)")

Na ilustração anterior, se hoje é a manhã de 11 de junho, o ADU dos três próximos dias (11, 12 e 13 de junho) é 21,66.

- **ADU (futuro)** = (18 + 18 + 29) ÷ 3 = 21,66

As transações a seguir são levadas em consideração para o cálculo de uso diário médio (posterior):

- Transações de previsão para o item em que a previsão está selecionada no planejamento mestre
- Transações com data no período posterior escolhido (o período posterior de uso médio diário)

### <a name="average-daily-usage-blended"></a>Uso diário médio (combinado)

O ADU combinado mescla o uso médio passado e o uso médio futuro, conforme mostrado na ilustração a seguir.

![Gráfico do uso diário médio (combinado).](media/ddmrp-adu-blended.png "Gráfico de uso diário médio (combinado)")

Na ilustração anterior, se hoje é a manhã de 11 de junho, o ADU combinado dos três dias anteriores e próximos (8 a 13 de junho) é 21,33.

- **ADU combinado** = (*ADU passado* + *ADU futuro*) ÷ 2<br>= (21 + 21,66) ÷ 2<br>= 21,33

## <a name="buffer-calculation-factors"></a>Fatores de cálculo de buffer

Para cada item, você pode definir dois fatores para ajustar quão grandes as zonas vermelha e verde podem ser. Dessa forma, você pode compensar o prazo de entrega previsto e a variabilidade da demanda.

![Fatores de variabilidade e prazo de entrega.](media/ddmrp-zone-factors.png "Fatores de variabilidade e prazo de entrega")

O primeiro fator é o *fator de prazo de entrega*. O valor é um valor decimal de 0 a 1. Quanto maior o prazo de entrega, menor o valor deve ser. O Instituto Orientado por Demanda recomenda os seguintes intervalos:

- **Prazo de entrega longo:** 0,20 – 0,40
- **Prazo de entrega médio:** 0,41 – 0,60
- **Prazo de entrega curto:** 0,61 – 1,00

O segundo fator é o *fator de variabilidade*. O valor é um valor decimal de 0 a 1. Quanto maior a variabilidade de demanda, menor o valor deve ser. O Instituto Orientado por Demanda recomenda os seguintes intervalos:

- **Variabilidade baixa:** 0,20 – 0,40
- **Variabilidade média:** 0,41 – 0,60
- **Variabilidade alta:** 0,61 – 1,00

## <a name="buffer-calculation-examples"></a>Exemplos de cálculo de buffer

Este exemplo continua o exemplo de produção de travesseiros fornecido no [Posicionamento de estoque](ddmrp-inventory-positioning.md). Nesse exemplo, você selecionou os pontos de separação que reduzem o prazo de entrega de 21 dias para cinco dias, conforme mostrado na ilustração a seguir.

![Exemplo de prazo de entrega separado.](media/ddmrp-bom-decoupled-lead-time-example.png "Exemplo de prazo de entrega separado")

Para esse exemplo, suponha que o ADU foi calculado como 23 peças e, como mostra a ilustração anterior, o prazo de entrega separado é de cinco dias. Usando esses valores, é possível calcular a zona amarela usando a seguinte equação:

- **Zona amarela** = *ADU* × *Prazo de entrega separado* = 115

![Exemplo de cálculo da zona amarela.](media/ddmrp-example-calc-yellow.png "Exemplo de cálculo da zona amarela")

O cálculo da zona vermelha é semelhante ao cálculo da zona amarela, mas é preenchido para variabilidade e prazo de entrega. Para esse exemplo, suponha que você observou um prazo de entrega médio (fator = 0,50) e variabilidade de demanda alta (fator = 0,8). Usando esses valores com os componentes da equação da zona amarela, você pode calcular a zona vermelha usando as equações a seguir:

- **Base vermelha** = *ADU* × *Prazo de entrega separado* × *Fator de prazo de entrega* = 57,5
- **Segurança vermelha** = *Base vermelha* × *Fator de variabilidade* = 46
- **Zona vermelha** = *Base vermelha* + *Segurança vermelha* = 103,5

O sistema arredondará a zona vermelha para 104 peças (ea), pois as peças são contadas em números inteiros.

![Exemplo de cálculo da zona vermelha.](media/ddmrp-example-calc-red.png "Exemplo de cálculo da zona vermelha")

O cálculo da zona verde também inclui os componentes da equação da zona amarela, mas permite um tamanho mínimo da ordem, ciclo da ordem e fator de prazo de entrega. Nesse exemplo, suponha que não haja um ciclo de ordem (portanto, você não tem restrições de tempo sobre a frequência com que faz encomendas) e a quantidade mínima da ordem é de 10 peças. A zona verde é então calculada como resultado máximo das três equações a seguir:

- *Quantidade mínima da ordem* = 10
- *ADU* × *Ciclo da ordem* = 0
- *ADU* × *Prazo de entrega separado* × *Fator de prazo de entrega* = 57,5

O sistema arredondará a zona verde para 58 peças (ea), pois as peças são contadas em números inteiros.

![Exemplo de cálculo da zona verde.](media/ddmrp-example-calc-green.png "Exemplo de cálculo da zona verde")

A ilustração a seguir resume os resultados do cálculo dessa zona usando o gráfico de funil que geralmente é usado em DDMRP.

![Resumo dos resultados do cálculo da zona.](media/ddmrp-example-calc-summary.png "Resumo dos resultados do cálculo da zona")

## <a name="dynamic-adjustments"></a><a name="dynamic-adjustments"></a>Ajustes dinâmicos

Os ajustes dinâmicos permitem aplicar um *fator de ajuste de demanda* durante períodos de alta ou baixa demanda. Esse fator multiplica o ADU em todos os cálculos para o período selecionado. As zonas de buffer, por sua vez, são modificadas. Geralmente, você aplicará esse fator depois de gerar os valores iniciais do buffer, de forma que possa ajustá-los ao longo do tempo e em resposta a condições variáveis. Essa é a terceira etapa do DDMRP.

Por exemplo, pode haver mais demanda por travesseiros em agosto, quando as pessoas saem de férias. Portanto, espera-se que as vendas sejam mais altas. Nesse caso, você pode alterar o valor do **Fator de ajuste de demanda** do produto para *1,5* em todas as semanas de agosto.

Dessa forma, é possível calcular os valores do buffer ao longo do tempo e ajustá-los com base não só nas informações contidas no sistema. Em uma implementação completa do DDMRP, você calculará os novos valores de buffer todos os dias por meio de um trabalho em lote e aceitará automaticamente os valores. Em seguida, você executará o planejamento como um trabalho em lote e revisará as ordens planejadas todos os dias para reabastecer os buffers.

## <a name="implement-buffers-in-supply-chain-management"></a>Implementar buffers no Supply Chain Management

Esta seção descreve como implementar sua estratégia de zona de buffer no Microsoft Dynamics 365 Supply Chain Management. Ela pressupõe que você já fez as análises e os cálculos que são descritos na primeira metade deste artigo.

### <a name="set-up-buffers-for-a-decoupling-point-item"></a><a name="set-up-buffers"></a>Configurar buffers para um item de ponto de separação

Siga estas etapas para configurar valores de buffer para um ponto de separação.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione um item liberado que seja configurado como um ponto de separação. (Para obter mais informações, consulte [Posicionamento de estoque](ddmrp-inventory-positioning.md).)
1. No Painel de Ações, na guia **Plano**, selecione **Cobertura do item**.
1. Na página **Cobertura do item**, selecione um registro de cobertura de item que crie um ponto de separação. (Esse registro mostrará o nome de um grupo de cobertura configurado para criar pontos de separação.)
1. Selecione a guia **Geral**.
1. Se desejar que o sistema recalcule valores de buffer todos os dias ou toda semana, com base nas configurações de histórico de vendas, previsões e grupo de cobertura, siga estas etapas:

    1. Defina a opção **Valores de buffer ao longo do tempo** para *Sim*.
    1. Uma caixa de mensagem o notifica que as configurações manuais do buffer (**Mínimo**, **Ponto de reabastecimento** e **Máximo**) serão redefinidas se você continuar. Selecione **Sim** para manter a nova configuração.

    Alternativamente, se você preferir calcular ou inserir suas configurações de buffer apenas uma vez, siga estas etapas:

    1. Defina a opção **Valores de buffer ao longo do tempo** para *Não*.
    1. Defina os campos **Mínimo**, **Ponto de reabastecimento** e **Máximo** para os valores de buffer calculados para o item, conforme descrito anteriormente neste artigo.

1. Defina os campos a seguir para concluir a configuração dos cálculos de DDMRP para o item:

    - **Ciclo da ordem** – especifique o número de dias que devem transcorrer entre as ordens de compra do item. Defina o valor para *0* (zero) se não houver restrições de ordem. Esse campo afeta o buffer de quantidade máxima, conforme discutido anteriormente neste artigo.
    - **Uso diário médio** – você pode, opcionalmente, inserir um ADU estimado para o item. Este campo é meramente informativo. Normalmente, o valor é calculado automaticamente como parte dos cálculos de buffer.
    - **Limite de pico da ordem** – especifique o número mínimo de vendas diárias do item que é qualificado como um pico de venda (alta demanda incomum). O sistema usa esse campo para aumentar a quantidade de reabastecimento das ordens planejadas em períodos de alta demanda. Para obter mais informações, consulte [Planejamento orientado por demanda](ddmrp-planning.md).

### <a name="calculate-or-enter-decoupled-lead-times"></a><a name="calc-lead-time"></a>Calcular ou inserir prazos de entrega separados

Para os itens que você escolhe permitir que o sistema [calcule as zonas de buffer automaticamente](#set-up-buffers), siga estas etapas para calcular ou inserir os prazos de entrega separados de um item do ponto de separação.

1. Abra a página **Cobertura do item** para o item do ponto de separação. (Para obter mais informações, consulte [Configurar buffers para um item do ponto de separação](#set-up-buffers).)
1. Selecione um registro de cobertura de item que crie um ponto de separação.
1. Selecione a guia **Valores de buffer**.
1. Se nenhum período de tempo for mostrado na grade, no Painel de Ações, na guia **Valores de buffer**, selecione **Adicionar períodos de tempo**. O sistema preenche a grade com as linhas de cada período de tempo diário ou semanal, dependendo de como o campo **Período mínimo, máximo e de ponto de reabastecimento** para o [grupo de cobertura](ddmrp-inventory-positioning.md) está definido: *Diário* ou *Semanal*. O sistema adicionará linhas suficientes para atingir o limite de tempo especificado para o grupo de cobertura atribuído ao item.
1. Selecione o período de tempo em que deseja calcular o prazo de entrega separado. (Normalmente, esse período de tempo é o período que inclui a data de hoje.)
1. No Painel de Ações, na guia **Valores de buffer**, selecione **Calcular prazo de entrega separado**.
1. Na caixa de diálogo **Calcular prazo de entrega separado**, defina os seguintes campos:

    - **BOM** – selecione a bom (lista de materiais) na qual você deseja executar o cálculo.
    - **Data** – selecione a data na qual você deseja executar o cálculo. O conjunto de BOMs disponíveis será filtrado para que apenas as BOMs ativas para a data selecionada sejam mostradas.
    - **Quantidade** – informe a quantidade para a qual deseja executar o cálculo. O conjunto de BOMs disponíveis será filtrado para que apenas as BOMs que se aplicam à quantidade especificada sejam mostradas.

1. Selecione **OK** para executar o cálculo e fechar a caixa de diálogo **Calcular prazo de entrega separado**. A coluna **Prazo de entrega separado** para o período de tempo selecionado agora mostra o valor calculado.

### <a name="calculate-or-enter-average-daily-usage"></a><a name="calc-adu"></a>Calcular ou inserir uso médio diário

Para os itens que você escolhe permitir que o sistema [calcule as zonas de buffer automaticamente](#set-up-buffers), siga estas etapas para calcular ou inserir o ADU de um item do ponto de separação.

1. Abra a página **Cobertura do item** para o item do ponto de separação. (Para obter mais informações, consulte [Configurar buffers para um item do ponto de separação](#set-up-buffers).)
1. Selecione um registro de cobertura de item que crie um ponto de separação.
1. Selecione a guia **Valores de buffer**.
1. Se nenhum período de tempo for mostrado na grade, no Painel de Ações, na guia **Valores de buffer**, selecione **Adicionar períodos de tempo**. O sistema preenche a grade com as linhas de cada período de tempo diário ou semanal, dependendo de como o campo **Período mínimo, máximo e de ponto de reabastecimento** para o [grupo de cobertura](ddmrp-inventory-positioning.md) está definido: *Diário* ou *Semanal*. Além disso, os valores padrão para os campos **Fator de prazo de entrega** e **Fator de variabilidade** são retirados do grupo de cobertura. Você pode editar esses valores para cada linha, conforme necessário.
1. Selecione um período de tempo em que deseja calcular o ADU.
1. No Painel de Ações, na guia **Valores de buffer**, selecione **Calcular uso diário médio**. O sistema tenta coletar os dados necessários para o cálculo do ADU, conforme definido para o [grupo de cobertura](ddmrp-inventory-positioning.md).
1. Siga uma destas etapas:

    - Se os dados necessários estiverem disponíveis, os resultados do cálculo serão adicionados à coluna **Uso diário médio**. Nesse caso, nenhuma ação é necessária.
    - Se os dados necessários não estiverem disponíveis, nenhum valor será adicionado automaticamente. Nesse caso, insira manualmente os valores estimados para cada linha em que você está planejando calcular os valores de buffer.

### <a name="calculate-and-apply-buffer-values"></a>Calcular e aplicar valores de buffer

Para os itens que você escolhe permitir que o sistema [calcule as zonas de buffer automaticamente](#set-up-buffers), é possível disparar manualmente o cálculo dos valores do buffer seguindo essas etapas.

1. Para o item do ponto de separação relevante, [configure o cálculo do buffer](#set-up-buffers), [calcule ou insira os prazos de entrega separados](#calc-lead-time) e [calcule ou insira o uso diário médio](#calc-adu) para todos os períodos de tempo relevantes, conforme descrito anteriormente neste artigo.
1. Abra a página **Cobertura do item** para o item do ponto de separação.
1. Selecione a guia **Valores de buffer**, que já deve mostrar uma lista de períodos de tempo.
1. Selecione o período de tempo em que deseja calcular os valores de buffer. (Normalmente, esse período de tempo será o período que inclui hoje.) A linha selecionada já deve ter valores diferentes de zero nas colunas **Uso diário médio** e **Prazo de entrega separado**.
1. Edite o campo **Fator de ajuste de demanda** para uma ou mais linhas, conforme necessário. O sistema aplicará esse fator ao valor de **Uso diário médio** em todos os cálculos de buffer nos quais esse valor é usado. Esse fator permite que você faça ajustes para como a demanda flutua por data (por exemplo, para feriados ou itens sazonais).
1. No Painel de Ações, na guia **Valores de buffer**, selecione **Calcular quantidades mínima, máxima e de ponto de reabastecimento**. O sistema calcula e preenche as colunas **Mínimo calculado**, **Ponto de reabastecimento calculado** e **Máximo calculado** na grade da página **Cobertura do item**.
1. Quando terminar de revisar os valores calculados, você deverá aplicá-los. Caso contrário, eles não terão nenhum efeito. Quando você aplica um cálculo para uma ou mais linhas, os valores dos campos **Mínimo calculado**, **Reabastecimento calculado** e **Máximo calculado** são copiados para as colunas **Mínimo**, **Ponto de reabastecimento** e **Máximo**, respectivamente. No Painel de Ações, na guia **Valores de buffer**, no grupo **Executar ação**, selecione um dos seguintes botões:

    - **Aceitar todos os cálculos** – aplique todos os valores calculados na grade.
    - **Aceitar cálculos para as linhas selecionadas** – aplique valores calculados somente para as linhas selecionadas.
    - **Descartar todos os cálculos** – descarta todos os valores calculados para quantidades mínimas, quantidades máximas e pontos de reabastecimento na grade.
    - **Descartar cálculos das linhas selecionadas** – descarta todos os valores calculados para quantidades mínimas, quantidades máximas e pontos de reabastecimento das linhas selecionadas.

### <a name="schedule-automatic-buffer-value-calculations"></a>Agendar cálculos automáticos do valor do buffer

Depois de configurar completamente as definições de DDMRP e confirmar que elas funcionam como esperado, você provavelmente desejará configurar um trabalho em lote para recalcular periodicamente o ADU e os valores de buffer relacionados, conforme necessário, com base nos dados de consumo reais e/ou previsões atualizadas. Esse procedimento se aplica somente a itens para os quais você escolhe permitir que o sistema [calcule automaticamente suas zonas de buffer](#set-up-buffers).

Siga estas etapas para agendar os cálculos automáticos do valor do buffer.

1. Vá para **Planejamento mestre \> Planejamento mestre \> DDMRP \> Calcular valores de buffer**.
1. Na caixa de diálogo **Calcular valores de buffer**, defina os seguintes campos:

    - **Calcular uso diário médio** – defina esta opção como *Sim* para recalcular o ADU de itens do ponto de separação toda vez que o trabalho for executado. Defina-a como *Não* para ignorar esse cálculo. Em geral, você deve definir essa opção como *Sim*.
    - **Calcular prazo de entrega separado** – defina essa opção como *Sim* para recalcular os prazos de entrega separados toda vez que o trabalho for executado. Defina-a como *Não* para ignorar esse cálculo. Em geral, você deve definir essa opção como *Sim*.
    - **Calcular valores de buffer** – defina essa opção como *Sim* para recalcular os valores de buffer sempre que o trabalho for executado. Defina-a como *Não* para ignorar esse cálculo. Em geral, você deve definir essa opção como *Sim*.
    - **Aceitar cálculos para mínimo, máximo e ponto de reabastecimento** – defina essa opção como *Sim* para aprovar e aplicar automaticamente os valores de buffer recalculados toda vez que o trabalho for executado. Defina-a como *Não* para que os valores recalculados não sejam aplicados. Nesse caso, os valores recalculados não entrarão em vigor, a menos que alguém os aplique manualmente da página **Cobertura de item** de cada produto. Em geral, você deve definir essa opção como *Sim*.
    - **Plano mestre** – selecione um plano mestre que inclua os itens que serão afetados pelo cálculo. O cálculo se aplicará a todos os itens no filtro de plano, que será ainda mais limitado pelas configurações de **Filtro** nessa caixa de diálogo.

1. Para limitar o conjunto de registros em que esse trabalho em lote deve ser executado, na FastTab **Registros a serem incluídos**, selecione **Filtro** para abrir a caixa de diálogo **Consulta**. Essa caixa de diálogo funciona do mesmo jeito que para outros tipos de [trabalho em segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Na FastTab **Executar em segundo plano**, especifique como, quando e com que frequência os cálculos selecionados devem ser feitos para os itens selecionados. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Selecione **OK** para adicionar o novo trabalho a uma fila de lote para execução.

### <a name="review-and-recalculate-decoupled-lead-times-for-all-items"></a>Revisar e recalcular os prazos de entrega separados para todos os itens

Siga estas etapas para revisar e recalcular todos os prazos de entrega separados que estão disponíveis na sua entidade legal (empresa).

1. Vá para **Planejamento mestre \> Planejamento mestre \> DDMRP \> Prazo de entrega separado**.
1. Na página **Prazo de entrega separado**, procure e filtre a lista, conforme necessário, para encontrar as informações que você está procurando. Para exibir ainda mais informações de um item, selecione seu link na coluna **Número do Item**.
1. Se desejar recalcular o prazo de entrega separado para qualquer item, selecione o item e, em seguida, selecione **Calcular prazo de entrega separado** no Painel de Ações. A caixa de diálogo **Calcular prazo de entrega separado** é exibida. Essa caixa de diálogo funciona do mesmo jeito quando você [calcula prazos de entrega separados](#calc-lead-time) para o mesmo item na página **Cobertura do item**.
