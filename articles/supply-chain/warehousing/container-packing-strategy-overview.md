---
title: Estratégias de embalagem de contêineres
description: Este tópico descreve as diferenças entre as estratégias de embalagem de contêineres e fornece exemplos.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: article
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f481f6ca047ee0285fe0e81d8fa96665e9d27cee
ms.sourcegitcommit: 8e846b52763f90d2232ec7d427839f4722570bce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6292752"
---
# <a name="container-packing-strategies"></a>Estratégias de embalagem de contêineres

Uma *estratégia de embalagem de contêineres* é uma estratégia que você pode usar para definir alocações de itens entre contêineres. Este tópico explica as diferenças entre as estratégias *Embalar em todos os contêineres abertos* e *Embalar somente no contêiner atual*.

- **Embalar em todos os contêineres abertos** – O sistema deve verificar todos os contêineres abertos que já foram criados durante o ciclo de transporte em contêiner, para garantir que o item caberá em um deles. Durante a embalagem, o sistema verifica cada item para determinar se ele caberá em algum dos contêineres criados anteriormente. Se o item não couber em um contêiner existente, o sistema cria um novo contêiner e continua até terminar de embalar todo o pedido.

    Por exemplo, *n* itens encomendados requerem conteinerização. Na pior das hipóteses, toda vez que o sistema processa um item que não cabe em nenhum contêiner existente, ele fará um total de (\[(*n* – 1) × (*n* + 1)\] ÷ 2) verificações para avaliar se o item cabe nos contêineres existentes.

- **Embalar somente no contêiner atual** – O sistema deve verificar somente o contêiner criado por último para garantir que o item não se encaixará nele. Durante a embalagem, o sistema verifica cada item para determinar se ele caberá no contêiner criado por último. Se o item não couber nesse contêiner, o sistema cria um novo contêiner e continua até terminar de embalar todo o pedido.

    Por exemplo, *n* itens encomendados requerem conteinerização. Na pior das hipóteses, o sistema fará um total de (*n* – 1) verificações para avaliar se o item cabe nos contêineres.

## <a name="example-of-the-flow-for-container-packing-strategies"></a>Exemplo do fluxo para estratégias de embalagem de contêineres

Você deverá configurar os seguintes itens para transporte em contêiner.

| Item  | Dimensões físicas (largura × profundidade × altura) | Peso |
|---|---|---|
| Cabo HDMI de 6" | 1 × 1 × 1 | 1 |
| Cabo HDMI de 12" | 2 × 1 × 1 | 1 |
| Cabo HDMI de 18" | 3 × 1 × 1 | 2 |

Você também deverá configurar a seguinte caixa que será usada para embalagem.

| Contêiner | Dimensões físicas (comprimento x largura × altura) | Peso | Volume |
|---|---|---|---|
| Caixa Média | 6 × 3 × 2 | 10 | 100 |

Por fim, você deve configurar um pedido que tenha os seguintes produtos e quantidades.

| Linha da ordem de venda | Quantidade |
|---|---|
| Cabo HDMI de 12" | 9 |
| Cabo HDMI de 18" | 8 |
| Cabo HDMI de 6" | 13 |

A tabela a seguir resume como funciona a conteinerização quando você usa a estratégia *Embalar em todos os contêineres abertos* e quando usa a estratégia *Embalar somente no contêiner atual*.

| Embalar todos os contêineres abertos | Embalar no recipiente atual |
|---|---|
| <p>Cabo HDMI de 12":</p><ol><li>Criar um novo contêiner, CONT0001.</li><li>Coloque 9 ea no contêiner CONT0001.</li></ol> | <p>Cabo HDMI de 12":</p><ol><li>Criar um novo contêiner, CONT0001.</li><li>Coloque 9 ea no contêiner CONT0001.</li></ol> |
| <p>Cabo HDMI de 18":</p><ol><li>Verifique se o item cabe no contêiner CONT0001.</li><li>Criar um novo contêiner, CONT0002.</li><li>Coloque 5 ea no contêiner CONT0002.</li><li>Criar um novo contêiner, CONT0003.</li><li>Coloque 3 ea no contêiner CONT0003.</li></ol> | <p>Cabo HDMI de 18":</p><ol><li>Verifique se o item cabe no contêiner CONT0001.</li><li>Criar um novo contêiner, CONT0002.</li><li>Coloque 5 ea no contêiner CONT0002.</li><li>Criar um novo contêiner, CONT0003.</li><li>Coloque 3 ea no contêiner CONT0003.</li></ol> |
| <p>Cabo HDMI de 6":</p><ol><li>Verifique se o item cabe no contêiner CONT0001.</li><li>Coloque 1 ea no contêiner CONT0001.</li><li>Verifique se o item cabe no contêiner CONT0002.</li><li>Verifique se o item cabe no contêiner CONT0003.</li><li>Coloque 4 ea no contêiner CONT0003.</li><li>Criar um novo contêiner, CONT0004.</li><li>Coloque 8 ea no contêiner CONT0004.</li></ol> | <p>Cabo HDMI de 6":</p><ol><li>Verifique se o item cabe no contêiner CONT0003.</li><li>Coloque 4 ea no contêiner CONT0003.</li><li>Criar um novo contêiner, CONT0004.</li><li>Coloque 9 ea no contêiner CONT0004.</li></ol> |

## <a name="example-scenario-pack-single-orders-per-container"></a>Cenário do exemplo: Embalar pedidos únicos por contêiner

Esta seção apresenta um cenário onde o sistema é configurado para consolidar vários pedidos em uma única remessa. Portanto, a conteinerização será feita com base na ordem de vendas para garantir que cada pedido que contenha vários produtos seja embalado em seu próprio contêiner.

Essa funcionalidade permite lidar com cenários onde você deve embalar apenas um pedido de venda em cada contêiner, para que o centro de distribuição possa realizar distribuição integrada com contêineres cheios entre lojas de varejo. Além dos cenários de varejo (pedido por loja de varejo e envio para um centro de distribuição integrada), essa técnica também é comumente usada em cadeias de suprimentos enxutas (ordem de vendas por linha de produção just-in-time).

Este cenário mostra como você pode diminuir o número de contêineres que são avaliados durante a embalagem usando a estratégia *Embalar somente no contêiner atual*.

### <a name="prerequisites"></a>Pré-requisitos

#### <a name="turn-on-the-consolidate-shipments-feature-in-your-system"></a>Ativar o recurso Consolidar remessas no seu sistema

Este cenário utiliza o recurso *Consolidar remessas*. Se esse recurso ainda não estiver disponível no seu sistema, você deve ativá-lo usando o [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

#### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

O cenário deste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management. Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.

### <a name="inspect-or-create-container-types"></a>Inspecionar ou criar tipos de contêineres

Para inspecionar seus tipos de contêineres ou criar novos tipos de contêineres, se necessário, siga estas etapas.

1. Vá para **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Tipos de contêiner**.
1. Certifique-se de que cada um destes tipos de contêiner esteja disponível em seus dados de demonstração. Edite ou crie tipos de contêineres conforme necessário.

    - Tipo de contêiner 1:

        - **Código do tipo de contêiner:** *Box-Large*
        - **Descrição:** *Caixa Grande*
        - **Peso líquido máximo:** *100*
        - **Volume:** *400*
        - **Comprimento:** *4*
        - **Largura:** *10*
        - **Altura:** *10*

    - Tipo de contêiner 2:

        - **Código do tipo de contêiner:** *Box-Medium*
        - **Descrição:** *Caixa Média*
        - **Peso líquido máximo:** *50*
        - **Volume:** *200*
        - **Comprimento:** *2*
        - **Largura:** *10*
        - **Altura:** *10*

    - Tipo de contêiner 3:

        - **Código do tipo de contêiner:** *Box-Small*
        - **Descrição:** *Caixa Pequena*
        - **Peso líquido máximo:** *20*
        - **Volume:** *100*
        - **Comprimento:** *1*
        - **Largura:** *10*
        - **Altura:** *10*

### <a name="inspect-or-create-container-groups"></a>Inspecionar ou criar grupos de contêineres

Para inspecionar seus grupos de contêineres ou criar novos grupos de contêineres, se necessário, siga estas etapas.

1. Vá para **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Grupos de contêineres**.
1. Certifique-se de que o seguinte grupo de contêiner esteja disponível em seus dados de demonstração. Se ele não estiver disponível, selecione **Novo** para criá-lo.

    - **ID do grupo de contêineres:** *Caixas*
    - **Descrição:** *Tamanhos de caixa*

1. Na FastTab **Detalhes** do grupo de contêineres *Caixas*, certifique-se de que as seguintes linhas existam. Se não existirem, selecione **Novo** para adicioná-las.

    - Linha 1:

        - **Número de sequência:** *1*
        - **Tipo de contêiner:** *Caixa-Grande*
        - **Porcentagem de utilização do contêiner:** *100*

    - Linha 2:

        - **Número de sequência:** *2*
        - **Tipo de contêiner:** *Caixa Média*
        - **Porcentagem de utilização do contêiner:** *100*

    - Linha 3:

        - **Número de sequência:** *3*
        - **Tipo de contêiner:** *Caixa Pequena*
        - **Porcentagem de utilização do contêiner:** *100*

### <a name="create-a-new-container-build-template"></a>Crie um novo modelo de criação de contêiner

Para criar um novo modelo de criação de contêiner, siga estas etapas.

1. Vá para **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Modelo de criação de contêiner**.
1. Selecione **Novo** para criar um modelo de criação de contêiner que tenha as seguintes configurações:

    - **Número de sequência:** *1*
    - **ID do modelo do contêiner:** *Caixa*
    - **ID do grupo de contêineres:** *Caixas*
    - **Tipos de consulta base:** *Linha de alocação de vendas*
    - **Código da etapa do ciclo:** *234*
    - **Permitir separações divididas:** *Sim*
    - **Estratégia de embalagem de contêineres:** *Embalar somente no contêiner atual*
    - **Embalar por unidade diretiva:** *Não*

1. Enquanto a linha do novo modelo ainda estiver selecionado, selecione **Editar consulta** no Painel de Ações.
1. Uma caixa de diálogo do editor de consultas padrão é exibida. Na guia **Classificação**, selecionar **Adicionar** para adicionar uma linha com as seguintes configurações:

    - **Tabela:** *Transações de trabalho temporário*
    - **Tabela derivada:** *Transações de trabalho temporário*
    - **Campo:** *Número da ordem*
    - **Direção da pesquisa:** *Crescente*

    > [!IMPORTANT]
    > Para evitar percorrer todos os outros contêineres abertos e acelerar o processo verificando um contêiner de cada vez, use a estratégia *Embalar somente no contêiner atual* além de classificar por número de pedido. Essa combinação funcionará como uma pausa de trabalho em um modelo de trabalho.

1. Selecione **OK** para fechar a caixa de diálogo do editor de consultas.
1. Enquanto a linha do novo modelo ainda estiver selecionado, selecione **Restrições de combinação de contêiner** no Painel de Ações.

    Agora você adicionará uma restrição que coloca itens de uma única ordem em um único contêiner. Os itens de qualquer outra ordem serão colocados em um contêiner separado.

1. Selecione **Novo** para criar uma restrição de combinação que tenha as seguintes configurações:

    - **Tabela:** *Ordens de venda*
    - **Seleção de campo:** *SalesId* (O campo aparecerá como *Ordem de vendas* na grade.)

1. Selecione **OK** para adicionar a restrição.
1. Feche a página.

### <a name="set-up-a-wave-template-for-containerization"></a>Configurar um modelo de ciclo para transporte em contêineres

Para configurar um modelo de ciclo, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
1. No painel de lista, defina o campo **Tipo de modelo de onda** como *Remessa*.
1. Selecione o modelo **63 Conteinerização** na lista.
1. No Painel de Ações, selecione **Editar**.
1. Na FastTab **Métodos**, na coluna **Métodos selecionados**, localize a seguinte linha:

    - **Nome do método:** *conteinerização*
    - **Nome:** *Conteinerização*

1. Defina o campo **Código da etapa da onda** para a linha como *234*.

### <a name="set-up-a-work-template"></a>Configurar um modelo de trabalho

Para configurar um modelo de trabalho, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. Defina o campo **Tipo de ordem de serviço** como *Ordens de venda*.
1. Na grade **Visão geral**, localize e selecione o modelo de trabalho que deve ser usado para embalar ordens únicas por contêiner. Para esse cenário, selecione o modelo **63 Separar para contêiner**.
1. No Painel de Ações, selecione **Editar consulta**.
1. Uma caixa de diálogo do editor de consultas padrão é exibida. Na guia **Classificação**, adicione as seguintes linhas:

    - Linha 1:

        - **Tabela:** *Transações de trabalho temporário*
        - **Tabela derivada:** *Transações de trabalho temporário*
        - **Campo:** *ID da Remessa*
        - **Direção da pesquisa:** *Crescente*

    - Linha 2:

        - **Tabela:** *Transações de trabalho temporário*
        - **Tabela derivada:** *Transações de trabalho temporário*
        - **Campo:** *Número da ordem*
        - **Direção da pesquisa:** *Crescente*

    - Linha 3:

        - **Tabela:** *Transações de trabalho temporário*
        - **Tabela derivada:** *Transações de trabalho temporário*
        - **Campo:** *ID do contêiner*
        - **Direção da pesquisa:** *Crescente*

1. Selecione **OK** para fechar a caixa de diálogo do editor de consultas.
1. Você receberá a seguinte mensagem: "O agrupamento será redefinido. Deseja continuar?" Selecione **Sim** para continuar.
1. Enquanto o modelo **63 Separar para contêiner** ainda estiver selecionado, selecione **Quebras de cabeçalho de trabalho** no Painel de Ações.

    Agora você aplicará configurações para interromper o trabalho para que cada contêiner na ordem esteja vinculado a uma ordem de serviço.

1. Marque a caixa de seleção **Agrupar por este campo** para cada linha na página **Quebras de cabeçalho de trabalho** (**ID da remessa**, **Número do pedido** e **ID do contêiner**).
1. Feche a página.

### <a name="set-up-shipment-consolidation-policies"></a>Configurar políticas de consolidação da remessa

Para configurar uma política de consolidação de remessa, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Liberar para depósito \> Políticas de consolidação de remessa**.
1. No painel de lista, defina o campo **Tipo de política** como *Ordens de venda*.
1. Selecione a política **Padrão** na lista.
1. No Painel de Ações, selecione **Editar**.
1. Na Guia Rápida **Campos de consolidação**, na lista **Campos selecionados**, selecione a linha na qual o campo **Nome do campo** está definido como *Número da ordem*.
1. Selecione o botão **Remover** ![Seta para a esquerda](media/backward-button.png) para mover o campo para a lista **Campos restantes**.
1. No Painel de ações, selecione **Salvar**.

### <a name="set-up-physical-dimensions-for-the-product"></a>Configurar dimensões físicas para o produto

Para configurar dimensões físicas para os produtos que serão utilizados nesse cenário, siga essas etapas.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione o produto no qual o campo **Número do item** esteja definido como *A0001*.
1. No Painel de Ação, na guia **Gerenciar estoque**, no grupo **Depósito**, selecione **Dimensões físicas**.
1. Na página **Dimensões físicas**, você deve ver a seguinte linha na grade:

    - **Unidade:** *pcs*
    - **Peso bruto:** *3,00*
    - **Largura:** *2,00*
    - **Profundidade:** *2,00*
    - **Altura:** *4,00*
    - **Volume:** *16,00*

1. Feche a página.
1. Selecione o produto no qual o campo **Número do item** esteja definido como *A0002*.
1. No Painel de Ação, na guia **Gerenciar estoque**, no grupo **Depósito**, selecione **Dimensões físicas**.
1. Na página **Dimensões físicas**, você deve ver a seguinte linha na grade:

    - **Unidade:** *pcs*
    - **Peso bruto:** *4,00*
    - **Largura:** *3,00*
    - **Profundidade:** *1,00*
    - **Altura:** *3,00*
    - **Volume:** *9,00*

### <a name="create-sales-order-1"></a>Criar ordem de venda 1

Para criar uma ordem de venda, siga estas etapas.

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Uma caixa de diálogo para criar uma nova ordem de venda aparece. Defina os seguintes valores:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *63*

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Na FastTab **Linhas da ordem de venda**, adicione as seguintes linhas de venda:

    - Linha 1:

        - **Número de item:** *A0001*
        - **Quantidade:** *2*

    - Linha 2:

        - **Número de item:** *A0002*
        - **Quantidade:** *2*

1. Selecione a primeira linha e selecione **Inventário \> Reserva**.
1. Na página **Reserva**, selecione **Reservar lote**. Depois feche a página.
1. Repita os dois passos anteriores para a segunda linha.
1. Feche a página.

### <a name="create-sales-order-2"></a>Criar ordem de venda 2

Siga estas etapas para criar uma segunda ordem de venda.

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Uma caixa de diálogo para criar uma nova ordem de venda aparece. Defina os seguintes valores:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *63*

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Na FastTab **Linhas da ordem de venda**, adicione as seguintes linhas de venda:

    - Linha 1:

        - **Número de item:** *A0001*
        - **Quantidade:** *4*

    - Linha 2:

        - **Número de item:** *A0002*
        - **Quantidade:** *4*

1. Selecione a primeira linha e selecione **Inventário \> Reserva**.
1. Na página **Reserva**, selecione **Reservar lote**. Depois feche a página.
1. Repita os dois passos anteriores para a segunda linha.
1. Feche a página.

### <a name="create-the-load"></a>Criar a carga

Para criar uma carga para cada ordem que você criou para esse cenário e, em seguida, liberá-lo para o depósito, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Cargas \> Bancada de planejamento de carga**.
1. Na guia **Linhas de venda**, localize e selecione todas as linhas da ordem de venda nas ordens criadas para esse cenário.
1. No Painel de Ação, na guia **Oferta e demanda** , no grupo **Adicionar** , selecione **Para nova carga**. As linhas de ordem selecionadas são adicionadas a uma nova carga.
1. Na caixa de diálogo **Atribuição de modelo de carga**, no campo **ID do modelo de carga**, selecione um modelo de carga, como *Contêiner de 40"*.
1. Selecione **OK** para fechar a caixa de diálogo.
1. Na seção **Cargas**, localize e selecione a carga que você acabou de criar.
1. Selecione **Liberação \> Liberação para depósito**.
1. Na caixa de diálogo **Liberar para depósito**, selecione **OK** para liberar a carga selecionada para o depósito.

### <a name="verify-the-shipments-and-containers"></a>Verificar as remessas e os contêineres

O procedimento a seguir permite verificar as remessas que foram criadas. Use-o para revisar a ordem que você criou para este cenário e ter certeza de que você obteve os resultados esperados.

1. Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.
1. Encontre e selecione a remessa que foi criada para a carga que você acabou de liberar.
1. No painel de ações, na guia **Transporte**, selecione **Exibir contêineres**.
1. Confirme que os itens das ordens de venda foram conteinerizados em dois contêineres diferentes.

## <a name="additional-resources"></a>Recursos adicionais

- [Transporte em contêineres](wave-containerization.md)
