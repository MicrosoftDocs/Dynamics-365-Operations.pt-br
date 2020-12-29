---
title: Slots de depósito
description: Este tópico fornece informações sobre slots de depósito. Os slots de depósito permitem consolidar a demanda por item e unidade de medida de ordens com um status de Encomendado, Reservado ou Liberado. Eles ajudam os gerentes de depósito a planejar de forma inteligente os locais de separação antes de liberar as ordens para o depósito e criar um trabalho de separação.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 31b86837735ca16610a1d304eab611b12a6aceeb
ms.sourcegitcommit: be4b9d557511bbb43e71a93f2c3b23b5f1a4669d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/24/2020
ms.locfileid: "4627740"
---
# <a name="warehouse-slotting"></a>Slots de depósito

[!include [banner](../includes/banner.md)]

Vários recursos de slots de depósito estão disponíveis para ajudar os gerentes de depósito a planejar os locais de separação de forma inteligente antes de liberar as ordens para o depósito e criar um trabalho de separação.

O *Recurso Slots de depósito* permite consolidar a demanda por item e unidade de medida de ordens com um status de *Encomendado*, *Reservado* ou *Liberado*. A demanda gerada pode ser aplicada a locais que serão usados para separação, com base na quantidade, unidade, dimensões físicas, locais fixos e muito mais. Depois que o plano de slots for estabelecido, o trabalho de reabastecimento poderá ser criado para agregar o valor apropriado de estoque a cada local.

O recurso *Slots de depósito para ordens de transferência* permite que os gerentes de depósito reabasteçam os locais de separação, com base na demanda de ordens de transferência que ainda não foram liberadas para o depósito. Isso garante que os locais de separação incluirão todos os itens necessários para as ordens de transferência após serem liberados para o depósito. Esse recurso requer que você também ative o recurso *Slots de depósito*.

O recurso *Aprimoramentos de alocação de slots de depósito* adiciona uma opção para as linhas de modelo que são usadas pelo recurso *Slots de depósito*. A opção permite que o sistema considere o estoque disponível existente em um local de destino. Portanto, menos reabastecimentos podem ser gerados para alocação. O recurso *Aprimoramentos de alocação de slots de depósito* requer que você também ative o recurso *Slots de depósito*. Opcionalmente, ele pode ser usado juntamente com o recurso *Slots de depósito para ordens de transferência*.

## <a name="turn-on-the-warehouse-slotting-features"></a>Ativar os recursos de slots de depósito

Antes de usar esses recursos, eles devem ser ativados em seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status desses recursos e ativá-los, se necessário. Ative os seguintes recursos conforme necessário:

- Recurso de slots de depósito
- Slots de depósito para ordens de transferência

    > [!IMPORTANT]
    > O recurso *Slots de depósito* deve ser ativado antes desse recurso.

- Aprimoramentos de alocação de slots de depósito

    > [!IMPORTANT]
    > O recurso *Slots de depósito* deve ser ativado antes desse recurso.

## <a name="set-up-warehouse-slotting"></a>Configurar slots de depósito

Para usar slots de depósito, é necessário configurar os elementos a seguir no seu sistema:

- Camadas de unidade de medida em slots
- Códigos de diretiva
- Modelos de slots
- Diretivas de localização

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a>Criar níveis de unidade de medida para slots

Os níveis de unidade de medida permitem que várias unidades de medida sejam agrupadas para fins de slots. Por exemplo, se vários tamanhos de caixas são separados na mesma área de separação de caixa, um nível pode ser criado para todos os tamanhos. **Uma linha deve ser criada para cada unidade de medida que deve fazer parte do nível.**

1. Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Slots de níveis da unidade de medida**.
1. Selecione **Novo**.
1. No cabeçalho, defina os seguintes valores:

    - **Nível da unidade de medida:** *EaBoxPl*
    - **Descrição:** *Cada palete de caixa*

1. Selecione **Salvar**.
1. Na FastTab **Unidades de medida**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Unidade:** *Caixa*
    - **Descrição:** deixe este campo em branco. Ele será preenchido automaticamente quando você salvar as alterações.
    - **Classe de unidade:** *Quantidade*

1. Selecione **Novo** para adicionar uma segunda linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Unidade:** *ea*
    - **Descrição:** deixe este campo em branco. Ele será preenchido automaticamente quando você salvar as alterações.
    - **Classe de unidade:** *Quantidade*

1. Selecione **Novo** para adicionar uma terceira linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Unidade:** *PL*
    - **Descrição:** deixe este campo em branco. Ele será preenchido automaticamente quando você salvar as alterações.
    - **Classe de unidade:** *Quantidade*

1. Selecione **Salvar** para salvar o nível.

### <a name="create-a-directive-code-for-slotting"></a>Criar um código de diretiva para slots

Você deve selecionar o código de diretiva que deve ser associado a um modelo.

1. Vá para **Gerenciamento de depósito \> Configuração \> Códigos de diretiva**.
1. No Painel de Ações, selecione **Novo**.
1. No campo **Código de diretiva**, insira *Slots*.
1. No campo **Descrição de diretiva**, insira *Slots*.

### <a name="set-up-slotting-templates"></a>Configurar modelos de slots

Cada modelo de slots controla como o estoque é atribuído a locais para um depósito específico. Cada modelo deve incluir uma linha para cada especificação de slots. Use os procedimentos desta seção para configurar os modelos de slots.

1. Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de slots**.
1. Selecione **Novo** para criar um modelo.

Em seguida, você deve configurar o cabeçalho do modelo, as especificações de slots e as diretivas de localização, conforme explicado nas subseções a seguir. A configuração para alocação para ordens de transferência é semelhante à configuração para alocação para ordens de venda, mas o campo **Ordens de transferência** é definido como *Ordens de transferência* em vez de *Ordem de venda*.

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a>Configurar o cabeçalho para um modelo de slots de ordem de venda

1. No cabeçalho do modelo, defina os seguintes valores:

    - **Modelos de slots:** _61_
    - **Descrição:** _61_
    - **Tipo de demanda:** *Ordem de venda*

        > [!NOTE]
        > Atualmente, *Ordens de venda* e *Ordens de transferência* são os únicos tipos de demanda compatíveis. Você pode selecionar *Ordens de transferência* somente se o recurso *Slots de depósito para ordens de transferência* estiver ativado.

    - **Estratégia de demanda:** _Encomendada_

        Os seguintes valores estão disponíveis neste campo:

        - **Encomendado** – a quantidade encomendada completa na ordem de venda deve ser considerada demanda.
        - **Reservado** – somente as quantidades de linha de ordem de venda que são reservadas (físicas e encomendadas) devem ser consideradas demandas.
        - **Liberado** – A quantidade liberada deve ser considerada demanda.

    - **Depósito:** _61_
    - **Permitir que a demanda de onda use quantidades não reservadas:** _Sim_

Você também pode especificar uma consulta para restringir o escopo da demanda avaliada.

#### <a name="set-up-slotting-specifications-for-each-template"></a>Configure especificações de slots para cada modelo

Para cada modelo de ordem de venda criado, siga estas etapas para adicionar uma linha a cada especificação de slots.

1. Na FastTab **Detalhes do modelo de slots**, selecione **Novo** para criar uma linha de modelo.
1. Na nova linha, defina os valores a seguir:

    - **Sequência:** _1_
    - **Descrição:** _Local fixo_
    - **Quantidade mínima:** _1_

        Este campo define a quantidade mínima de demanda necessária para a linha.

    - **Quantidade máxima:** _1000000_

        Este campo define a quantidade máxima de demanda que é válida para a linha.

    - **Unidade:** Deixe este campo em branco.

        Este campo define a unidade de medida à qual as quantidades mínima e máxima se referem.

    - **Nível da Unidade de Medida:** _EaBoxPl_

        Este campo define as unidades de medida de demanda que são válidas para a linha. (Para obter mais informações, consulte a seção [Configurar níveis de unidade de medida para slots](#unit-tiers) anteriormente neste tópico.)

    - **Atribuir critérios de slot:** _Considerar quantidade_

        Os seguintes valores estão disponíveis neste campo:

        - **Supor vazio** – este sistema deve supor que todos os locais na área de separação estão vazios e não devem verificar esses locais para estoque.
        - **Considerar qtd** – o sistema deve verificar os locais na área de separação do estoque e deve manter locais que não estão vazios.
        - **Considerar disponível** – O sistema deve verificar se algum local de destino contém quantidades não reservadas para o item na linha de demanda. Se a quantidade for grande o suficiente para satisfazer pelo menos uma unidade da linha de demanda, o registro do plano de slots gerado é reduzido pela quantidade disponível. Por exemplo, se a demanda for de 10 casos e um caso estiver disponível, a demanda localizada será de 9 casos. Se a demanda for de 10 casos e cada um estiver disponível, a demanda localizada será de 10 casos. Esse valor está disponível apenas quando o recurso *Aprimoramentos de alocação de slots de depósito* está ativado.

    - **Código de diretiva:** _Slots_

        Este campo define a diretiva de localização que é usada para encontrar o local de separação do trabalho de reabastecimento.

    - **Local de excesso:** deixe este campo em branco.

        Este campo define o local em que o estoque é colocado, caso um local não possa ser encontrado para a quantidade quando a linha é processada.

    - **Permitir pausa:** _Sim_

        Quando esta opção for definida como *Sim*, se uma demanda não puder ser encaixada, o trabalho de movimento será criado para retirar o estoque dos locais onde há estoque, mas onde nada foi encaixado. O modelo será reexecutado. Desta vez, ele ignora o estoque nos locais. Essa funcionalidade funciona melhor quando o campo **Atribuir critérios de slot** é definido como _Considerar qtd_.

    - **Uso de local fixo:** _Somente localizações fixas do produto_

        Os seguintes valores estão disponíveis neste campo:

        - **Locais fixos e não fixos** – o sistema não deve se limitar a usar apenas locais fixos.
        - **Apenas locais fixos do produto** – o sistema deve ter slots apenas para locais fixos do produto.
        - **Apenas locais fixos da grade de produto** – o sistema deve ter slots apenas para locais fixos da grade de produto.

> [!NOTE]
> Se o modelo de slots contiver pelo menos uma linha em que o campo **Atribuir critérios de slot** for definido como *Considerar disponível*, não serão mais permitidas pausas nas linhas do modelo.

1. Selecione **Salvar**.
1. Selecione **Novo** para criar uma segunda linha de modelo.
1. Na nova linha, defina os valores a seguir:

    - **Sequência:** _2_
    - **Descrição:** _Outro_
    - **Qtd. mínima:** _1_
    - **Qtd. máxima:** _1000000_
    - **Unidade:** Deixe este campo em branco.
    - **Nível da unidade de medida:** _EaBoxPl_
    - **Atribuir critérios de slot:** _Considerar quantidade_
    - **Código de diretiva:** _Slots_
    - **Local de excesso:** deixe este campo em branco.
    - **Permitir pausa:** _Sim_
    - **Usar locais fixos:** _Locais fixos e não fixos_

    Na consulta da segunda linha, você agora especificará os critérios usados para determinar os locais nos quais a demanda da linha pode ser encaixada.

1. Selecione a linha em que o campo **Sequência** está definido como *2*.
1. Selecione **Editar consulta**.
1. Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Tabela:** *Localizações*
    - **Tabela derivada:** *Locais*
    - **Campo:** *ID de perfil da localização*
    - **Critérios:** *Separar-06* (selecione o sinal de adição duplo \[**++**\] no campo para expandir a lista e selecione *Separar-06* - *Site de Separação 6*).

1. Selecione **OK**.

#### <a name="set-up-location-directives"></a>Configurar diretivas de localização

Pelo menos uma diretiva de localização deve ser configurada para dar suporte a seleções de slots. Use os procedimentos desta seção para configurar uma nova *diretiva de local de reabastecimento* para separações de slots.

1. Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No painel esquerdo, no campo **Tipo de ordem de serviço**, selecione *Reabastecimento*.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho da nova diretiva de localização, no campo **Nome**, insira *Seleção de slots 61*.
1. No campo **Número de sequência**, aceite o valor padrão.

##### <a name="configure-the-location-directives-fasttab"></a>Configurar a FastTab Diretivas de localização

1. Na FastTab **Diretivas de localização**, defina os valores a seguir. Aceite os valores padrão para todos os demais campos.

    - **Tipo de trabalho:** _Separar_
    - **Local:** _6_
    - **Depósito:** _61_
    - **Código de diretiva:** _Slots_

1. Selecione **Salvar** para disponibilizar a FastTab **Linhas**.

##### <a name="configure-the-lines-fasttab"></a>Configurar a FastTab Linhas

1. Na FastTab **Linhas**, selecione **Novo** para criar uma linha.
1. Na nova linha, defina os valores a seguir.

    - **Quantidade inicial:** _0_
    - **Quantidade final:** _1000000_

1. Aceite os valores padrão para os campos restantes.
1. Selecione **Salvar** para disponibilizar a FastTab **Ações de Diretiva de Localização**.

##### <a name="configure-the-location-directive-actions-fasttab"></a>Configurar a FastTab Ações de Diretiva

1. Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** para criar uma linha.
1. Na nova linha, defina os valores a seguir. Aceite os valores padrão para todos os demais campos.

    - **Número de sequência:** aceite o valor padrão.
    - **Nome:** _Massa_
    - **Estratégia:** _Nenhuma_

1. Aceite os valores padrão para os campos restantes.
1. Selecione **Salvar** para disponibilizar o botão **Editar consulta**.

##### <a name="edit-the-query"></a>Editar a consulta

1. Na FastTab **Ações de Diretiva de Localização**, selecione **Editar consulta**.
1. Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Tabela:** *Localizações*
    - **Tabela derivada:** *Localizações*
    - **Campo:** *ID da zona*
    - **Critérios:** *Massa* (selecione o sinal de adição duplo \[**++**\] no campo para expandir a lista e selecione *Massa*.)

1. Selecione **OK**.

## <a name="scenario"></a>Cenário

### <a name="set-up-the-scenario"></a>Configurar o cenário

Para esse cenário, use os dados de exemplo internos e crie os registros descritos nesta seção.

#### <a name="use-the-usmf-sample-data"></a>Usar os dados de exemplo USMF

Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

#### <a name="create-demand"></a>Criar demanda

Siga as etapas a seguir para criar a solicitação à qual você aplicará slots.

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar uma ordem de venda.
1. Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione _US-007_.
1. No campo **Depósito**, selecione _61_.
1. Selecione **OK**.
1. A nova ordem de venda é aberta. Ela inclui uma linha vazia na FastTab **Linhas da ordem de venda**. Nessa linha, defina os seguintes valores:

    - **Item:** _L0101_
    - **Quantidade:** _20_

1. Selecione **Adicionar linha** para adicionar uma nova linha e defina os seguintes valores:

    - **Item:** _T0100_
    - **Quantidade:** _8_

1. Selecione **Salvar**.
1. Selecione **Novo** para criar uma segunda ordem de venda.
1. Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione _US-008_.
1. No campo **Depósito**, selecione _61_.
1. A nova ordem de venda é aberta. Ela inclui uma linha vazia na FastTab **Linhas da ordem de venda**. Nessa linha, defina os seguintes valores:

    - **Item:** _T0100_
    - **Quantidade:** _1_

1. Selecione **Salvar**.

### <a name="walk-through-a-typical-slotting-scenario"></a>Examine um cenário típico de slots

Depois que todos os elementos de pré-requisito estiverem em uso, conforme descrito na seção anterior, você estará pronto para testar o recurso, executando cada exercício desta seção.

#### <a name="generate-demand"></a>Gerar demanda

1. Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de slots** e selecione o modelo de slots que você criou antes.
1. No Painel de Ações, selecione **Gerar demanda**. Este comando avalia toda a demanda que está no sistema e corresponde à consulta do modelo de slots. A demanda total em todas as ordens é consolidada em uma linha por quantidade/unidade de medida. Uma mensagem informativa é exibida quando o processo é concluído.

#### <a name="slotting-demand"></a>Demanda de slots

A *demanda de slots* mostra os resultados da geração de demanda, com base na configuração do modelo de slots.

- No Painel de Ações, selecione **Demanda de slots** para exibir os resultados do comando **Gerar demanda**. As linhas na demanda de slots podem ser editadas. Você pode excluir uma linha, adicionar uma nova linha ou editar detalhes da linha.

> [!NOTE]
> Você pode editar manualmente a demanda ou pode importá-la de um sistema externo usando o gerenciamento de dados. Seja qual for a demanda de slots, ela será usada na próxima etapa, independentemente da origem.

#### <a name="locate-demand"></a>Localizar demanda

Depois que a demanda for gerada, utilize o comando **Localizar demanda** para gerar o *plano de slots*.

- No Painel de Ações, selecione **Localizar demanda**. O processo de slots é executado. Uma mensagem informativa é exibida quando o processo é concluído.

#### <a name="slotting-plan"></a>Plano de slots

O plano de slots mostra o local ao qual cada item/quantidade foi atribuído, se o estouro foi usado, se o trabalho de pausa foi criado e a linha de modelo que foi usada. *Qualquer demanda que não possa ser encaixada será realçada em vermelho.*

- No Painel de Ações, selecione **Plano de slots** para exibir os resultados.

> [!NOTE]
> - Os processos **Gerar demanda**, **Localizar demanda** e **Executar reabastecimento** agora são executados em uma área restrita. (Esses processos estão disponíveis no Painel de Ações na página **Modelos de slots**.)
> - Os processos **Gerar demanda**, **Localizar demanda** e **Executar reabastecimento** têm um bloqueio para garantir que não possam ser acionados ao mesmo tempo. Caso contrário, os dados usados podem ser excluídos.
> - Os processos **Gerar demanda** e **Localizar demanda** mostram um aviso se a execução não gerou registros ou se faltam informações nos registros.
> - Quando você seleciona **Plano de slots**, a página não tem os botões **Novo**, **Editar** ou **Excluir** no Painel de Ações, porque não é possível editar a fonte de dados.
> - Quando você seleciona **Executar reabastecimento**, o sistema valida o modelo de slot e os processos selecionados.

#### <a name="create-replenishment"></a>Criar reabastecimento

Após a criação do plano de slots, você deverá criar um *trabalho de reabastecimento*, com base no plano.

- No Painel de Ações, selecione **Executar reabastecimento**. Uma mensagem informativa é exibida quando o processo é concluído. Esta mensagem indica o número de cabeçalhos que foram criados para a ID de criação do trabalho.

As diretivas de localização que serão usadas são identificadas com base no código de diretiva especificado em cada linha de modelo.

## <a name="tips"></a>Dicas

### <a name="set-up-automatic-slotting"></a>Configurar slots automáticos

Quando todos os elementos necessários estiverem ativos, você poderá configurar slots para execução automática seguindo essas etapas.

1. Vá para **Gerenciamento de depósito \> Reabastecimento \> Executar slots**.
1. Especifique as etapas de slots a serem executadas. Selecione uma ou mais das seguintes etapas de slots:

    - Gerar demanda
    - Localizar demanda
    - Criar trabalho de reabastecimento

    > [!NOTE]
    > As etapas de slots são progressivas. Se desejar selecionar *Localizar demanda*, primeiro selecione *Gerar demanda*.

1. Especifique o modelo de slots a ser usado.
1. Defina que a recorrência seja executada automaticamente, se desejar.

Para os exercícios no cenário, **não** configure slots automáticos.
