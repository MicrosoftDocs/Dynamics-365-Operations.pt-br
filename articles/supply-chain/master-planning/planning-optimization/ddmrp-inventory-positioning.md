---
title: Posicionamento de estoque
description: Este artigo fornece informações sobre o posicionamento estratégico de estoque, que envolve a identificação de pontos de separação na sua cadeia de fornecedores, na qual você pode criar um estoque disponível para ajudar a reduzir os prazos de entrega e absorver choques da sua cadeia de fornecedores.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ReqGroup, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 847108575cbf7207282db00d731363c8cfad883a
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689529"
---
# <a name="inventory-positioning"></a>Posicionamento de estoque

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

O posicionamento estratégico de estoque envolve a identificação de pontos de separação na sua cadeia de fornecedores, nos quais é possível criar o estoque disponível. Essa abordagem é usada principalmente para ajudar a reduzir os prazos de entrega e absorver choques da sua cadeia de fornecedores. Ela permite atenuar o "efeito chicote", pois a variabilidade da demanda não é transmitida completamente na cadeia de fornecedores. (O *efeito chicote* refere-se à forma como as flutuações pequenas na demanda, no nível de varejo, podem causar flutuações cada vez maiores na demanda nos níveis de atacado, distribuidor, fabricante e fornecedor de material bruto.)

O posicionamento do estoque é a primeira etapa do DDMRP (Planejamento de Recursos Materiais Orientado por Demanda).

## <a name="inventory-positioning-for-manufacturing"></a>Posicionamento de estoque para fabricação

Esta seção fornece um exemplo que mostra como tomar decisões de posicionamento de estoque se você fabrica travesseiros comuns. O travesseiro tem uma BOM (lista de materiais) de vários níveis, como mostrado na ilustração a seguir.

![Exemplo de BOM (lista de materiais) de vários níveis para um travesseiro.](media/ddmrp-bom-example.png "Exemplo de BOM (lista de materiais) de vários níveis para um travesseiro")

### <a name="choose-your-decoupling-points"></a>Escolha os pontos de separação

Ao escolher onde colocar os pontos de separação, considere todos os seguintes aspectos de cada item da BOM como critérios:

- Variabilidade externa
- Aproveitamento e flexibilidade de estoque
- Proteção de operação crítica
- Tempo de tolerância do cliente
- Horizonte de visibilidade da ordem de venda
- Prazo de entrega potencial do mercado

No exemplo de travesseiros, você pode colocar seu primeiro ponto de separação nos *tarugos de espuma* pelos seguintes motivos:

- É difícil prover os materiais usados para fazer os tarugos de espuma, e a disponibilidade é volátil. Portanto, o critério de *variabilidade externa* é atendido.
- Os tarugos de espuma podem ser cortados em vários formatos e tamanhos diferentes de modo a criar aplicações de espuma para outros produtos que você fabrica, além do travesseiro. Portanto, o critério *aproveitamento e flexibilidade de estoque* é atendido.

Em seguida, você pode colocar seu próximo ponto de separação no *kit de malha*, que é a malha de travesseiro pré-cortada. Você pode escolher esse ponto porque tem apenas uma máquina de corte de malha. Portanto, o critério de *proteção de operação crítica* é atendido.

Por fim, você pode colocar seu último ponto de separação no item de travesseiro finalizado. Esse ponto pode ser escolhido porque você tem um *tempo de tolerância do cliente* muito baixo em vendas e porque o *horizonte de visibilidade da ordem de venda* é razoavelmente curto. Portanto, é conveniente garantir que você tenha o estoque disponível para atender às ordens de entrada. Também é possível definir um preço mais alto mantendo o prazo de entrega curto, que é a isso que se refere o critério *prazo de entrega potencial do mercado*.

Com base nessa análise, a ilustração a seguir mostra como será a BOM de travesseiros. Os símbolos de estoque amarelos realçam os pontos de separação.

![Exemplo de BOM com pontos de separação destacados.](media/ddmrp-bom-decoupling-example.png "Exemplo de BOM com pontos de separação destacados")

### <a name="calculate-your-decoupled-lead-time"></a>Calcular prazo de entrega separado

Esta seção mostra como calcular os novos prazos de entrega depois de introduzidos os pontos de separação.

Na ilustração a seguir para o exemplo de travesseiros iniciado na seção anterior, os prazos de entrega são mostrados nas caixas cinzas no canto superior esquerdo de cada componente da BOM. As caixas que têm um contorno vermelho indicam itens que direcionam o prazo de entrega cumulativo (a soma dos tempos de entrega mais longos em cada nível da BOM). Esse prazo de entrega é de 21 dias quando você começa do zero.

![Exemplo de BOM com prazos de entrega.](media/ddmrp-bom-lead-times-example.png "Exemplo de BOM com prazos de entrega")

No entanto, se você aplicar os pontos de separação anteriormente escolhidos, os itens separados sempre estarão em estoque. Portanto, eles terão um prazo de entrega igual a 0 (zero). O novo prazo de entrega para o travesseiro agora é de apenas cinco dias: dois dias para comprar o thread e três dias para produzir o travesseiro. Esse prazo de entrega é conhecido como o *prazo de entrega separado*.

![Exemplo de prazo de entrega separado.](media/ddmrp-bom-decoupled-lead-time-example.png "Exemplo de prazo de entrega separado")

## <a name="strategic-inventory-positioning-in-a-retail-model"></a>Posicionamento estratégico de estoque em um modelo de varejo

Como os varejistas estocam somente os produtos finalizados, as BOMs não são um problema. No entanto, os varejistas ainda podem usar o DDMRP definindo o posicionamento estratégico de estoque e os níveis de buffer com base nos locais de armazenamento na rede de distribuição.

A ilustração a seguir mostra um exemplo de uma empresa com um centro de distribuição em Seattle e lojas em Boston, Atlanta e Portland.

![Pontos de separação com base na localização em um modelo de varejo.](media/ddmrp-retail-decoupl-points-example.png "Pontos de separação com base na localização em um modelo de varejo")

Você pode decidir que o tempo de transferência para mover uma manta entre o centro de distribuição e as lojas violam o *tempo de tolerância do cliente*, pois os clientes esperam que a manta esteja no estoque quando eles visitam a loja. Nesse caso, você configurará um ponto de separação para o item manta em cada uma das três lojas. Cada loja terá níveis de buffer diferentes, com base nos prazos de entrega, padrões de demanda e assim por diante.

## <a name="implement-inventory-positioning-in-dynamics-365-supply-chain-management"></a>Implementar o posicionamento de estoque no Dynamics 365 Supply Chain Management

Esta seção descreve como implementar sua estratégia de posicionamento de estoque no Microsoft Dynamics 365 Supply Chain Management.

### <a name="set-up-item-coverage-groups-that-create-decoupling-points"></a>Configurar grupos de cobertura de item que criam pontos de separação

Os itens tornam-se os pontos de separação quando pertencem a um grupo de cobertura configurado com um valor de **Código de cobertura** do *Ponto de separação*. Portanto, a primeira etapa do processo de configuração do DDMRP é decidir quais grupos de cobertura devem ser implementados para a sua estratégia de DDMRP e, depois, criá-los seguindo essas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Cobertura \> Grupos de cobertura**.
1. No Painel de Ações, selecione **Novo** para criar um grupo de cobertura.
1. Insira informações que identificam o grupo de cobertura e selecione o calendário a ser usado.
1. Na guia **Geral**, defina o campo **Código de cobertura** como *Ponto de separação*. Essa configuração fará com que todos os itens que pertencem a esse grupo de cobertura sejam tratados como pontos de separação para DDMRP. Ela também habilita todas as configurações de DDMRP para esse grupo, conforme descrito posteriormente neste procedimento.
1. Na guia **Outros**, na seção **Parâmetros do DDMRP**, defina os seguintes campos:

    - **Fator de prazo de entrega** – especifique um fator (como um valor decimal entre 0 e 1) para controlar o impacto que o prazo de entrega deve ter quando os níveis de estoque mínimo e máximo são calculados para itens nesse grupo de cobertura. Em geral, quanto maior o prazo de entrega de um item, menor deverá ser o fator de prazo de entrega. Um fator de prazo de entrega menor produz níveis de estoque mínimo e máximo e, portanto, gera ordens menores e mais frequentes. A metodologia de DDMRP recomenda um valor entre 0,20 e 0,40 para itens que têm longos prazos de entrega, entre 0,41 e 0,60 para itens que têm prazos de entrega médios, e entre 0,61 e 1,0 para itens com tempos de entrega curtos. Para obter mais informações, consulte [Perfil e níveis de buffer](ddmrp-buffer-profile-and-levels.md).
    - **Fator de variabilidade** – especifique um fator (como um valor decimal entre 0 e 1) para controlar o impacto que a demanda variável deve ter quando o nível de estoque mínimo é calculado para itens nesse grupo de cobertura. Em geral, quanto mais variável uma demanda de item for, maior deverá ser o fator de variabilidade. Um fator de variabilidade maior produz um nível de estoque mínimo mais alto. A metodologia de DDMRP recomenda um valor entre 0,00 e 0,40 para itens que têm variabilidade baixa, entre 0,41 e 0,60 para itens com variabilidade média, e entre 0,61 e 1,0 para itens com variabilidade alta. Para obter mais informações, consulte [Perfil e níveis de buffer](ddmrp-buffer-profile-and-levels.md).
    - **Período mínimo, máximo e de ponto de reabastecimento** – especifique com que frequência calcular os valores de buffer (*Diário* ou *Semanal*).

1. Na guia **Outros**, na seção **Uso diário médio**, defina os seguintes campos:

    - **Uso diário médio baseado em** – selecione em quais períodos de tempo o cálculo do ADU (uso diário médio) deve se basear. Selecione um dos seguintes valores:

        - *Passado* – olhe apenas o uso passado para o número de dias especificado no campo **Período passado (dias)**. O ADU é calculado como a demanda total de um item durante o período de cálculo (em unidades de estoque) dividido pelo número de dias do período de cálculo.
        - *Futuro* – observe somente o uso futuro projetado (incluindo previsões) para o número de dias especificados no campo **Período posterior (dias)**. O ADU é calculado como a demanda total de um item durante o período de cálculo (em unidades de estoque) dividido pelo número de dias do período de cálculo. 
        - *Combinado* – observe o uso passado e futuro. As configurações para o campo **Período passado (dias)**, o campo **Período futuro (dias)** e as opções de combinação são todas aplicadas. 

            *ADU combinado* = (\[*Ponderação passada* × *ADU passado*\] + \[*Ponderação futura* × *ADU futuro*\]) ÷ (*Ponderação passada* + *Ponderação futura*)

    - **Período passado (dias)** – insira o número de dias passados (até e incluindo hoje) que o sistema deve considerar ao calcular o ADU de itens nesse grupo de cobertura. Essa configuração se aplica somente quando o campo **Uso diário médio baseado em** é definido como *Passado* ou *Combinado*.
    - **Período futuro (dias)** – insira o número de dias futuros (de hoje até o dia especificado) que o sistema deve considerar ao calcular o ADU de itens nesse grupo de cobertura. Essa configuração se aplica somente quando o campo **Uso diário médio baseado em** é definido como *Futuro* ou *Combinado*.
    - **Peso relativo do período passado para uso médio misto de uso diário** – insira o peso (como uma porcentagem) a ser aplicado ao período passado quando o ADU combinado é calculado. Essa configuração se aplica somente quando o campo **Uso diário médio baseado em** é definido como *Combinado*.
    - **Peso relativo do período futuro para uso médio misto de uso diário** – insira o peso (como uma porcentagem) a ser aplicado ao período futuro quando o ADU combinado é calculado. Essa configuração se aplica somente quando o campo **Uso diário médio baseado em** é definido como *Combinado*.

1. Para todos os outros campos e guias, insira as configurações detalhadas usadas para calcular os requisitos para os itens vinculados a esse grupo de cobertura.

### <a name="set-an-item-as-a-decoupling-point"></a>Definir um item como um ponto de separação

Para definir um item como um ponto de separação, siga estas etapas.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Localize e selecione um item liberado que você deseja configurar para DDMRP.
1. No Painel de Ações, na guia **Plano**, selecione **Cobertura do item**.
1. Na página **Cobertura do item**, vários registros de cobertura de item já podem estar listados, cada um deles se aplica a uma combinação diferente de dimensões de produto e de armazenamento. Você pode selecionar um registro de cobertura de item existente que se aplique às dimensões nas quais deseja criar um ponto de separação. Como alternativa, é possível selecionar **Novo** no Painel de Ações para criar um novo registro de cobertura de item.
1. Configure o registro de cobertura de item como de costume. No mínimo, você deve especificar o site e o depósito onde o ponto de separação será aplicado.
1. Com o registro apropriado ainda selecionado, selecione a guia **Geral**.
1. Marque a caixa de seleção **Usar configurações específicas**.
1. Defina o campo **Grupo de cobertura** para um grupo de cobertura configurado para criar pontos de separação (conforme descrito na seção anterior).
1. O item agora está configurado como um ponto de separação. Geralmente, ao usar DDMRP, você também define as configurações que afetam os tamanhos de buffer e a quantidade de reabastecimento. No entanto, é possível concluir essa configuração posteriormente. Para obter mais informações sobre as configurações, consulte [Configurar buffers para um item do ponto de separação](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

> [!NOTE]
> Para planejar itens que não sejam pontos de separação, siga as mesmas etapas de quando o MRP (planejamento de requisitos de material padrão) é usado.
