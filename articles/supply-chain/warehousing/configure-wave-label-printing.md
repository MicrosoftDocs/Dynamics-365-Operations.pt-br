---
title: Configurar e usar a impressão de etiquetas de onda
description: Este tópico descreve a impressão de etiquetas de onda e explica como configurá-la.
author: GarmMSFT
manager: PJacobse
ms.date: 05/01/2020
ms.topic: configure-wave-label-printing
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSDocumentRouting, WHSWaveTableListPage, WHSPostMethod, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelType, WHSWaveLabelTemplateGroup, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: PJacobse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 1f51ed9f05caede3d4f320ddb6b705e67df9aa1f
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016945"
---
# <a name="set-up-and-use-wave-label-printing"></a>Configurar e usar a impressão de etiquetas de onda

[!include [banner](../includes/banner.md)]

A impressão de etiquetas de onda oferece uma abordagem alternativa para a impressão de etiquetas introduzindo um novo método de etapa da onda que permite criar e imprimir etiquetas diretamente do modelo de onda durante a execução de ondas. Portanto, as etiquetas estarão disponíveis antes que os trabalhadores executem a ordem de serviço em um dispositivo móvel. Os trabalhadores poderão então anexar as etiquetas necessárias durante a separação, em vez de após a separação.

A impressão de etiquetas de onda usa a Linguagem de Programação Zebra (ZPL) para criar layouts de etiqueta. Um layout de etiqueta é dividido em três seções (cabeçalho, corpo e rodapé) para permitir etiquetas que tenham estrutura repetitiva. Os modelos de etiqueta de onda informam ao sistema qual layout de etiqueta deve ser usado. Os usuários podem especificar a impressora a ser usada. Eles também podem imprimir etiquetas em várias impressoras ao mesmo tempo, conforme necessário. A página **Histórico de etiquetas de onda** mostra um registro de todas as etiquetas que foram criadas usando esta configuração.

Você pode imprimir e agrupar etiquetas com base em cabeçalhos de trabalho, imprimir etiquetas de intervalo por cabeçalho de trabalho e imprimir etiquetas de conteúdo de contêiner, etiquetas de caso e outras etiquetas semelhantes.

> [!NOTE]
> Essa funcionalidade não substitui a funcionalidade de impressão de etiquetas existente que é baseada no roteamento de documentos.

A impressão de etiquetas de onda oferece os seguintes aprimoramentos:

- Imprimir etiquetas de acordo com o número de caixas em uma única linha de trabalho, sem o transporte em contêineres. (A "caixa" é uma unidade designada em linhas do grupo de sequências de unidade.)
- Imprimir várias sequências de etiquetas diferentes (por exemplo, etiquetas de caixa e de palete).
- Incluir enumeração de etiquetas (por exemplo, 1/124, 2/124, ... 124/124) e definir o intervalo de enumeração (por exemplo, linha de trabalho, linha de carga ou remessa).
- Criar e imprimir uma ID de conhecimento de embarque nas etiquetas antes que o conhecimento de embarque seja gerado.
- Criar um código série do contêiner de remessa (SSCC) exclusivo para cada caixa e incluí-lo em cada etiqueta.
- Criar sequências numéricas em conformidade com o GS1 para IDs de conhecimento de embarque e SSCCs.
- Reimprimir etiquetas de dispositivos móveis e do cliente avançado.
- Anular etiquetas (por exemplo, em cenários de separação insuficiente) e reimprimi-las.
- Limpar o histórico de etiquetas de onda.
- Os aprimoramentos nos layouts de roteamento de documentos são compartilhados entre layouts de roteamento de documentos e layouts de etiqueta de onda. (Para obter mais informações, consulte [Layout de roteamento de documentos para placas de licença](../warehousing/document-routing-layout-for-license-plates.md).)

Esses aprimoramentos tornam mais eficiente a etiquetagem de caixas antes da paletização. Eles são especialmente benéficos para empresas que enviam para grandes varejistas que automaticamente confirmam os recebimentos de ordens digitalizando cada caixa de forma separada.

> [!NOTE]
> Você pode implementar os cenários de configuração descritos neste tópico separadamente ou em combinação, dependendo dos seus requisitos comerciais. Você pode criar vários modelos de etiqueta de onda que funcionam em sequência (conforme ilustrado no cenário 3). Por exemplo, você pode usar o cenário 1 para imprimir etiquetas de caixa e o cenário 2 para imprimir etiquetas de palete (se os paletes no estoque variarem em tamanho e composição).

## <a name="turn-on-the-wave-label-printing-feature"></a>Ativar o recurso Impressão de etiquetas de onda

Para que você possa usar o recurso *Impressão de etiquetas de onda* , ele deve estar ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Impressão de etiquetas de onda*

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a>Cenário 1: Impressão de etiquetas de onda na qual uma única etiqueta de onda é gerada

Este cenário mostra como uma empresa pode imprimir etiquetas de remessa para um grande varejista que automaticamente confirma os recebimentos de ordens digitalizando cada caixa de forma separada.

Ele mostra o fluxo de ponta a ponta.

### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

Para seguir este cenário, você deve ter dados de demonstração instalados e deve selecionar a entidade legal **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Verificar se o método de etiqueta de onda está disponível

Pode ser necessário regenerar os métodos de processo de onda para tornar o método de impressão de etiquetas de onda disponível.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.
1. Confirme se **waveLabelPrinting** está na lista. Se não estiver, selecione **Regenerar métodos** no Painel de Ação para adicioná-lo.

### <a name="configure-a-wave-template"></a>Configurar um modelo de onda

Os modelos de onda permitem vincular instâncias específicas de métodos de onda a um modelo de etiqueta de onda correspondente.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
1. Selecione um modelo, como **Padrão de Remessa 62**.
1. Na FastTab **Métodos** , mova o método **Impressão de etiquetas de onda** para a coluna **Métodos selecionados**.
1. Na coluna **Métodos selecionados** , selecione o método **Impressão de etiquetas de onda** e defina seu campo **Código da etapa da onda** como *PrintLabel*. Para obter mais informações sobre códigos da etapa da onda, consulte [Códigos da etapa da onda](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Criar um layout de etiqueta de onda

O layout de etiqueta controla quais informações são impressas na etiqueta e como são apresentadas. Aqui, insira o código ZPL enviado à impressora.

1. Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Layouts de etiqueta de onda**.
1. Crie um registro com as seguintes configurações:

    - **ID do layout da etiqueta:** *Caixa*
    - **Descrição:** *Caixa (SSCC)*

1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ação, selecione **Configurações da linha da etiqueta da onda**.

    A página **Configurações da linha da etiqueta da onda** será exibida. Aqui, você pode configurar a parte dinâmica da etiqueta.

1. Adicione uma linha com as seguintes configurações:

    - **ID da linha:** *WaveLabel*
    - **Nome da tabela de linhas:** *WHSWaveLabel*
    - **Posição inicial da linha:** *0*

        Este campo define a posição vertical na qual a linha será iniciada na etiqueta.

    - **Altura da linha:** *0*

        Este campo define a altura de cada linha (em pontos), de acordo com o padrão ZPL. A altura da linha é positiva para etiquetas horizontais e negativa para etiquetas verticais. Como há apenas uma linha neste exemplo, você pode definir o valor como *0* (zero).

    - **Linhas por página:** *1*

        Este campo define o número de linhas que podem ser impressas em cada etiqueta.

        > [!NOTE]
        > Esta configuração fará com que uma etiqueta ZPL separada seja impressa para cada registro na tabela de etiquetas de onda.

1. Feche a página.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consultas, na guia **Intervalo** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *Tipo de trabalho*
    - **Critérios:** *Separação*

    Esta consulta garante que somente as linhas de trabalho de separação serão impressas na etiqueta, não as linhas de trabalho de colocação.

1. Se você quiser imprimir a ID do conhecimento de embarque, na guia **Junções** , selecione a tabela **Linhas de trabalho** e junte a tabela **Remessas** a ela.
1. Feche a caixa de diálogo do editor de consultas.
1. A FastTab **Layout do texto da impressora** tem três seções nas quais é possível escrever código da impressora: **Seção do cabeçalho** , **Seção do corpo** e **Seção do rodapé**. Na **Seção do cabeçalho** , no campo **Cabeçalho da etiqueta** , insira o código para o cabeçalho obrigatório. Por exemplo, se você estiver usando impressoras Zebra, poderá usar o código a seguir.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. Na **Seção do corpo** , no campo **Corpo da etiqueta** , insira o código ZPL para o corpo obrigatório. Veja aqui um exemplo.

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. Na **Seção do corpo** , no campo **Rodapé da etiqueta** , insira o código ZPL para o rodapé obrigatório. Veja aqui um exemplo.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Esta configuração imprimirá uma cópia de cada etiqueta. Se você precisar de mais cópias (por exemplo, uma cópia para cada lado do palete), defina o valor **n** para a seção **\^PQn** no rodapé como o número de cópias necessário. Por exemplo, para imprimir quatro cópias de cada etiqueta, especifique **\^PQ4**.

Sua etiqueta agora está pronta para uso.

### <a name="create-a-wave-label-type"></a>Criar um tipo de etiqueta de onda

Os tipos de etiqueta de onda são usados para vincular modelos de etiqueta de onda a uma unidade em linhas de grupo de sequências de unidade.

1. Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Tipos de etiqueta de onda**.
1. Adicione um tipo de etiqueta de onda com as seguintes configurações:

    - **Tipo de etiqueta:** *Caixa*
    - **Descrição:** *Caixa*

### <a name="set-up-unit-sequence-groups"></a>Configurar grupos de sequências de unidade

Em seguida, configure o grupo de sequências de unidade para o tipo de etiqueta de onda.

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Grupos de sequências de unidade**.
1. Selecione o grupo **Ea Caixa PL**.
1. Para a linha **Caixa** , defina o campo **Tipo de nível de onda** como *Caixa*.

### <a name="create-a-wave-label-template"></a>Criar um modelo de etiqueta de onda

Em seguida, crie o modelo de etiqueta de onda para o tipo de etiqueta de onda.

1. Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Modelos de etiqueta de onda**.
1. Adicione um modelo de nível de onda e defina os seguintes valores no cabeçalho:

    - **Nome do modelo de etiqueta:** *Etiquetas de caixa*
    - **Descrição:** *Etiquetas de caixa*
    - **Código da etapa da onda:** *PrintLabel*
    - **Depósito:** *62*

1. Na FastTab **Geral** , defina o campo **Tipo de etiqueta de onda** como *Caixa*.
1. Na FastTab **Detalhes do modelo de etiqueta de onda** , adicione uma nova linha com as seguintes configurações:

    - **ID do layout da etiqueta:** *Caixa*
    - **Nome da impressora:** Selecione uma impressora ZPL apropriada.
    - **Executar consulta:** *Sim* (esta configuração é opcional, mas recomendável para um desempenho ideal.)

1. No Painel de ações, selecione **Salvar**.
1. Opcional: se estiver configurando um design de etiqueta específico do cliente, você deve criar uma consulta para localizar a conta do cliente. Na FastTab **Detalhes do modelo de etiqueta de onda** , selecione **Editar consulta**. Em seguida, na caixa de diálogo do editor de consultas, na guia **Intervalo** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Remessas*
    - **Tabela derivada:** *Remessas*
    - **Campo:** *Número da conta*
    - **Critérios:** Insira o número da conta do cliente relevante.

    Quando terminar, selecione **OK** para fechar a caixa de diálogo do editor de consultas.

1. No Painel de Ação, selecione **Editar consulta** para abrir a caixa de diálogo do editor de consultas para todo o modelo de etiqueta.
1. Na caixa de diálogo do editor de consultas, na guia **Classificação** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *ID da linha de carga de referência (ID do Registro)*
    - **Direção da pesquisa:** *Crescente*

1. Selecione **OK** para fechar a caixa de diálogo do editor de consultas.
1. Uma caixa de mensagem solicitará que você confirme a operação de redefinição do agrupamento. Selecione **Sim** para continuar.
1. No Painel de Ação, selecione **Grupo de modelos de etiqueta de onda**.
1. Na caixa de diálogo **Grupo de modelos de etiqueta de onda** , selecione a linha na qual o campo **Nome do campo de referência** está definido como *ID da linha de carga de referência* e, em seguida, marque a caixa de seleção **ID de criação da etiqueta** para essa linha.

    > [!NOTE]
    > Essa configuração criará uma sequência de etiquetas ("Caixa 1 de X") por linha de carga ao longo da onda, independentemente da configuração do agrupamento de trabalho. Essa sequência de etiquetas pode ser impressa no layout de etiqueta.

### <a name="configure-number-sequence-extensions"></a>Configurar extensões de sequência numérica

As extensões de sequência numérica controlam a conformidade com o GS1 de sequências numéricas específicas. Esta configuração é opcional para o cenário atual. Para obter mais informações e instruções de configuração, consulte [Configurar extensões de sequência numérica](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Criar uma ordem de venda e liberá-la para o depósito

1. Vá para **Vendas e marketing \> Ordem de venda \> Todas as ordens de venda**.
1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *62*

1. Adicione duas linhas da ordem de venda com as seguintes configurações:

    - Linha 1 da ordem de venda:

        - **Número de item:** *A0001*
        - **Quantidade:** *9024*
        - **Unidade:** *ea* (9024 ea = 376 Caixa = 47 PL)

    - Linha 2 da ordem de venda:

        - **Número de item:** *A0002*
        - **Quantidade:** *9016*
        - **Unidade:** *ea* (9016 ea = 322 Caixa = 46 PL)

    > [!NOTE]
    > Os itens e as quantidades fornecidos aqui são apenas exemplos. Eles devem usar o grupo de sequências de unidade definido anteriormente, conversões de unidade apropriadas de *ea* para *Caixa* para *PL* devem ser definidas para eles, e eles devem ter estoque no depósito *62*. Para obter mais informações, consulte [Políticas de unidade de medida e estoque](unit-measure-stocking-policies.md).

1. Selecione a linha 1 da ordem de venda. Em seguida, na seção **Linha da ordem de venda** , no menu **Estoque** , selecione **Reservas**.
1. Na página **Reserva** , no Painel de Ação, selecione **Reservar lote** e, em seguida, feche a página.
1. Repita as etapas 4 e 5 para a linha 2 da ordem de venda.
1. No Painel de Ações, na guia **Depósito** , selecione **Liberar para o depósito**.

    Os seguintes eventos ocorrem:

    - O sistema processa a remessa criada usando o modelo que inclui a etapa de impressão de etiquetas. O layout da etiqueta será usado para definir o formato da etiqueta, e o resultado será uma etiqueta impressa na impressora selecionada no modelo de etiqueta.
    - Etiquetas de onda são geradas e impressas. O número de etiquetas será igual ao número de caixas (neste exemplo, 376 etiquetas Caixa para a linha 1 e 322 etiquetas Caixa para a linha 2).
    - Uma nova ID de conhecimento de embarque é gerada para as remessas. Se você configurou as extensões de sequência numérica, as IDs de etiqueta de onda seguirão o formato numérico de **SSCC-18**. 

Você pode exibir e reimprimir etiquetas de onda nas páginas a seguir. No Painel de Ações de cada página, na guia **Remessas** , no grupo **Informações relacionadas** , selecione **Etiquetas de onda**.

- Todas as remessas \> Detalhes da remessa
- Todas as cargas \> Detalhes da carga
- Todas as ondas
- Etiquetas de onda
- Histórico da etiqueta de onda

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a>Cenário 2: Impressão de etiquetas de onda para transporte em contêineres (sem registros de etiqueta de onda)

Este cenário permite imprimir etiquetas de onda ao usar o transporte em contêineres para dividir itens automaticamente em caixas e, portanto, não requer um registro de etiqueta de onda. Nesse caso, a ID do contêiner atua como um espaço reservado para o SSCC.

Estas são as principais diferenças entre este cenário e o cenário 1:

- **Modelos de etiqueta de onda:** você não selecionará um tipo de etiqueta de onda no modelo de etiqueta de onda e não precisará de um agrupamento de criações de etiquetas. Caso contrário, você configurará o modelo de etiqueta de onda e se vinculará ao modelo de onda da mesma forma que é descrita no cenário 1. Você deve deixar o tipo de etiqueta de onda em branco para evitar que etiquetas de onda sejam geradas.
- **Layouts de etiqueta de onda:** você definirá as configurações de linha do layout de etiqueta de onda para linhas de trabalho em vez de registros de etiqueta de onda. Você deve definir a configuração de linha para o layout de etiqueta usando a tabela **WHSWorkLine** em vez da tabela **WHSWaveLabel**. A configuração **Linhas por página** controla o número de linhas que a seção do corpo terá. 

Essa configuração também é adequada para cenários comerciais nos quais vários itens diferentes são embalados em uma caixa etiquetada ou em um palete, e esse processo de embalagem pode ser definido pela criação do trabalho (por exemplo, trabalho agrupado por remessa).

Ele mostra o fluxo de ponta a ponta.

### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

Para seguir este cenário, você deve ter dados de demonstração instalados e deve selecionar a entidade legal **USMF**.

### <a name="make-sure-that-the-wave-label-method-is-available"></a>Verificar se o método de etiqueta de onda está disponível

Pode ser necessário regenerar os métodos de processo de onda para tornar o método de impressão de etiquetas de onda disponível.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.
1. Confirme se **waveLabelPrinting** está na lista. Se não estiver, selecione **Regenerar métodos** no Painel de Ação para adicioná-lo.

### <a name="set-up-a-wave-template"></a>Configurar um modelo de onda

Os modelos de onda permitem vincular instâncias específicas de métodos de onda a um modelo de etiqueta de onda correspondente.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
1. Selecione um modelo, como **Transporte em Contêineres 63**.
1. Na FastTab **Métodos** , mova o método **Impressão de etiquetas de onda** para a coluna **Métodos selecionados**.
1. Na coluna **Métodos selecionados** , selecione o método **Impressão de etiquetas de onda** e defina seu campo **Código da etapa da onda** como *PrintLabel*. Para obter mais informações sobre códigos da etapa da onda, consulte [Códigos da etapa da onda](wave-step-codes.md).

### <a name="create-a-wave-label-layout"></a>Criar um layout de etiqueta de onda

1. Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Layouts de etiqueta de onda**.
1. Crie um registro com as seguintes configurações:

    - **ID do layout da etiqueta:** *Caixa*
    - **Descrição:** *Caixa (SSCC)*

1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ação, selecione **Configurações da linha da etiqueta da onda**.

    A página **Configurações da linha da etiqueta da onda** será exibida. Aqui, você pode configurar a parte dinâmica da etiqueta.

1. Adicione uma linha com as seguintes configurações:

    - **ID da linha:** *WorkLine*
    - **Nome da tabela de linhas:** *WHSWorkLine*
    - **Posição inicial da linha:** *500*

        Este campo define a posição vertical na qual a linha será iniciada na etiqueta.

    - **Altura da linha:** *-50*

        Este campo define a altura de cada linha. A altura da linha é positiva para etiquetas horizontais e negativa para etiquetas verticais.

    - **Linhas por página:** *5*

        Este campo define o número de linhas que podem ser impressas em cada etiqueta.

        > [!NOTE]
        > Esta configuração imprimirá várias etiquetas ZPL por trabalho, em que cada página pode conter até cinco linhas de trabalho. Por exemplo, se uma etiqueta for impressa para um contêiner que tem 12 linhas, três etiquetas serão impressas. Se quiser imprimir uma etiqueta separada para cada linha de separação, defina este valor como *1*.

1. Feche a página.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consultas, na guia **Intervalo** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *Tipo de trabalho*
    - **Critérios:** *Separação*

1. Se você quiser imprimir a ID do conhecimento de embarque, na guia **Junções** , selecione a tabela **Linhas de trabalho** e junte a tabela **Remessas** a ela.
1. Feche a caixa de diálogo do editor de consultas.
1. A FastTab **Layout do texto da impressora** tem três seções nas quais é possível escrever código da impressora: **Seção do cabeçalho** , **Seção do corpo** e **Seção do rodapé**. Na **Seção do cabeçalho** , no campo **Cabeçalho da etiqueta** , insira o código para o cabeçalho obrigatório. Por exemplo, se você estiver usando impressoras Zebra, poderá usar o código a seguir.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. Na **Seção do corpo** , no campo **Corpo da etiqueta** , insira o código ZPL para o corpo obrigatório. Veja aqui um exemplo.

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. Na **Seção do corpo** , no campo **Rodapé da etiqueta** , insira o código ZPL para o rodapé obrigatório. Veja aqui um exemplo.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Esta configuração imprimirá uma cópia de cada etiqueta. Se você precisar de mais cópias (por exemplo, uma cópia para cada lado do palete), defina o valor **n** para a seção **\^PQn** no rodapé como o número de cópias necessário. Por exemplo, para imprimir quatro cópias de cada etiqueta, especifique **\^PQ4**.

Sua etiqueta agora está pronta para uso.

### <a name="create-a-wave-label-template"></a>Criar um modelo de etiqueta de onda

1. Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Modelos de etiqueta de onda**.
1. Adicione um modelo de nível de onda e defina os seguintes valores no cabeçalho:

    - **Nome do modelo de etiqueta:** *Etiquetas de contêiner*
    - **Descrição:** *Etiquetas de contêiner*
    - **Código da etapa da onda:** *PrintLabel*
    - **Depósito:** *63*

1. Na FastTab **Detalhes do modelo de etiqueta de onda** , adicione uma linha com as seguintes configurações:

    - **ID do layout da etiqueta:** *Contêiner*
    - **Nome da impressora:** Selecione uma impressora ZPL apropriada.
    - **Executar consulta:** *Sim* (esta configuração é opcional, mas recomendável para um desempenho ideal.)

1. No Painel de ações, selecione **Salvar**.
1. Opcional: se estiver configurando um design de etiqueta específico do cliente, você deve criar uma consulta para localizar a conta do cliente. Na FastTab **Detalhes do modelo de etiqueta de onda** , selecione **Editar consulta**. Em seguida, na caixa de diálogo do editor de consultas, na guia **Intervalo** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Remessas*
    - **Tabela derivada:** *Remessas*
    - **Campo:** *Número da conta*
    - **Critérios:** Insira o número da conta do cliente relevante.

    Quando terminar, selecione **OK** para fechar a caixa de diálogo do editor de consultas.

### <a name="configure-number-sequence-extensions"></a>Configurar extensões de sequência numérica

As extensões de sequência numérica controlam a conformidade com o GS1 de sequências numéricas específicas. Esta configuração é opcional para o cenário atual. Para obter mais informações e instruções de configuração, consulte [Configurar extensões de sequência numérica](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Criar uma ordem de venda e liberá-la para o depósito

1. Vá para **Vendas e marketing \> Ordem de venda \> Todas as ordens de venda**.
1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *63*

1. Adicione cinco linhas da ordem de venda:

    - Linha 1 da ordem de venda:

        - **Número de item:** *A0001*
        - **Quantidade:** *10*

    - Linha 2 da ordem de venda:

        - **Número de item:** *A0002*
        - **Quantidade:** *20*

    - Linha 3 da ordem de venda:

        - **Número de item:** *L0006*
        - **Quantidade:** *20*

    - Linha 4 da ordem de venda:

        - **Número de item:** *L0100*
        - **Quantidade:** *40*

    - Linha 5 da ordem de venda:

        - **Número de item:** *L0101*
        - **Quantidade:** *50*

    > [!NOTE]
    > Os itens e as quantidades fornecidos aqui são apenas exemplos. Eles devem ter estoque no depósito especificado.

1. Selecione a linha 1 da ordem de venda. Em seguida, na seção **Linha da ordem de venda** , no menu **Estoque** , selecione **Reservas**.
1. Na página **Reserva** , no Painel de Ação, selecione **Reservar lote** e, em seguida, feche a página.
1. Repita as etapas 4 e 5 para cada linha da ordem de venda adicional.
1. No Painel de Ações, na guia **Depósito** , selecione **Liberar para o depósito**.

    Os seguintes eventos ocorrem:

    - O sistema processa a remessa criada usando o modelo que inclui a etapa de impressão de etiquetas. O layout da etiqueta será usado para definir o formato da etiqueta, e o resultado final será uma etiqueta com cinco linhas impressa na impressora selecionada no modelo de etiqueta.
    - Uma nova ID de conhecimento de embarque é gerada para as remessas. Se você configurou as extensões de sequência numérica, as IDs de etiqueta de onda seguirão o formato numérico de **SSCC-18**. 

Você pode reimprimir essas etiquetas de onda indo para **Gerenciamento de depósito \> Consultas e relatórios \> Histórico de etiquetas de onda**.

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a>Cenário 3: Impressão de etiquetas de onda para etiquetas de várias camadas

Este cenário mostra como usar a funcionalidade de impressão de etiquetas de onda quando os processos de depósito exigem várias camadas de etiquetas de remessa. Por exemplo, pode ser necessário imprimir etiquetas separadas para caixas e paletes e uma etiqueta de intervalo para uma remessa inteira. As etiquetas de intervalo são um tipo separado de etiqueta que pode ser usado como divisor entre rolos e contêineres, como etiquetas para a ID de remessa e um código de barras, de forma que as etiquetas possam ser classificadas facilmente após serem impressas.

A principal diferença entre a configuração deste cenário e a configuração do cenário 1, além do fato de as etiquetas de intervalo estarem habilitadas, é que vários tipos de etiqueta de onda devem ser associados a modelos de etiqueta de onda e linhas de grupo de sequências de unidade. Para realizar essa configuração, defina os seguintes elementos para este cenário:

- **Métodos de processamento de ondas:** você vai marcar o método de etiqueta de onda como "repetível", adicioná-lo duas (ou mais) vezes ao modelo de onda e definir códigos de etapa de onda diferentes.
- **Modelos de etiqueta de onda:** você configurará os modelos de etiqueta de onda e os vinculará ao modelo de onda. Cada modelo de etiqueta de onda tem seu próprio tipo de etiqueta de onda.
- **Layouts de etiqueta de onda:** você criará vários layouts de etiqueta de onda. Haverá um layout de etiqueta separado para cada "camada" de etiquetas e também haverá um layout de etiqueta de intervalo.

Ele mostra o fluxo de ponta a ponta.

### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

Para seguir este cenário, você deve ter dados de demonstração instalados e deve selecionar a entidade legal **USMF**.

### <a name="set-up-a-wave-process-method"></a>Configurar um método de processo de onda

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.
1. Confirme se **waveLabelPrinting** está na lista. Se não estiver, selecione **Regenerar métodos** no Painel de Ação para adicioná-lo.
1. Para o método **waveLabelPrinting** , marque a caixa de seleção **Tornar o método repetível**.

### <a name="set-up-a-wave-template"></a>Configurar um modelo de onda

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
2. Selecione um modelo, como **Padrão de Remessa 62**.
3. Na FastTab **Métodos** , mova o método **Impressão de etiquetas de onda** para a coluna **Métodos selecionados**.
4. Na coluna **Métodos selecionados** , atribua um valor de **Código da etapa da onda** , como *Caixa* , ao método **Impressão de etiquetas de onda**. Para obter mais informações sobre códigos da etapa da onda, consulte [Códigos da etapa da onda](wave-step-codes.md).
5. Mova o método **Impressão de etiquetas de onda** para a coluna **Métodos selecionados** novamente.
6. Na coluna **Métodos selecionados** , atribua um valor diferente de **Código da etapa da onda** , como *Palete* , ao segundo método **Impressão de etiquetas de onda**. Para obter mais informações sobre códigos da etapa da onda, consulte [Códigos da etapa da onda](wave-step-codes.md).

### <a name="create-three-wave-label-layouts"></a>Criar três layouts de etiqueta de onda

1. Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Layouts de etiqueta de onda**.
1. Crie um registro com as seguintes configurações:

    - **ID do layout da etiqueta:** *Caixa*
    - **Descrição:** *Caixa (SSCC)*

1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ação, selecione **Configurações da linha da etiqueta da onda**.

    A página **Configurações da linha da etiqueta da onda** será exibida. Aqui, você pode configurar a parte dinâmica da etiqueta.

1. Adicione uma linha com as seguintes configurações:

    - **ID da linha:** *WaveLabel*
    - **Nome da tabela de linhas:** *WHSWaveLabel*
    - **Posição inicial da linha:** *0*

        Este campo define a posição vertical na qual a linha será iniciada na etiqueta.

    - **Altura da linha:** *0*

        Este campo define a altura de cada linha (em pontos), de acordo com o padrão ZPL. A altura da linha é positiva para etiquetas horizontais e negativa para etiquetas verticais. Como há apenas uma linha neste exemplo, você pode definir o valor como *0* (zero).

    - **Linhas por página:** *1*

        Este campo define o número de linhas que podem ser impressas em cada etiqueta.

        > [!NOTE]
        > Esta configuração fará com que uma etiqueta ZPL separada seja impressa para cada registro na tabela de etiquetas de onda.

1. Feche a página.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consultas, na guia **Intervalo** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *Tipo de trabalho*
    - **Critérios:** *Separação*

    Esta consulta garante que somente as linhas de trabalho de separação serão impressas na etiqueta, não as linhas de trabalho de colocação.

1. Se você quiser imprimir a ID do conhecimento de embarque, na guia **Junções** , selecione a tabela **Linhas de trabalho** e junte a tabela **Remessas** a ela. 
1. Feche a caixa de diálogo do editor de consultas.
1. A FastTab **Layout do texto da impressora** tem três seções nas quais é possível escrever código da impressora: **Seção do cabeçalho** , **Seção do corpo** e **Seção do rodapé**. Na **Seção do cabeçalho** , no campo **Cabeçalho da etiqueta** , insira o código para o cabeçalho obrigatório. Por exemplo, se você estiver usando impressoras Zebra, poderá usar o código a seguir.


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. Na **Seção do corpo** , no campo **Corpo da etiqueta** , insira o código ZPL para o corpo obrigatório. Veja aqui um exemplo.

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. Na **Seção do corpo** , no campo **Rodapé da etiqueta** , insira o código ZPL para o rodapé obrigatório. Veja aqui um exemplo.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Esta configuração imprimirá uma cópia de cada etiqueta. Se você precisar de mais cópias (por exemplo, uma cópia para cada lado do palete), defina o valor **n** para a seção **\^PQn** no rodapé como o número de cópias necessário. Por exemplo, para imprimir quatro cópias de cada etiqueta, especifique **\^PQ4**.

1. A primeira etiqueta agora está pronta para uso.
1. Crie um segundo registro de layout com as seguintes configurações:

    - **ID do layout da etiqueta:** *Palete*
    - **Descrição:** *Palete*

1. No Painel de ações, selecione **Salvar**.
1. No Painel de Ação, selecione **Configurações da linha da etiqueta da onda**.

    A página **Configurações da linha da etiqueta da onda** será exibida. Aqui, você pode configurar a parte dinâmica da etiqueta.

1. Adicione uma linha com as seguintes configurações:

    - **ID da linha:** *WaveLabel*
    - **Nome da tabela de linhas:** *WHSWaveLabel*
    - **Posição inicial da linha:** *0*

        Este campo define a posição vertical na qual a linha será iniciada na etiqueta.

    - **Altura da linha:** *0*

        Este campo define a altura de cada linha (em pontos), de acordo com o padrão ZPL. A altura da linha é positiva para etiquetas horizontais e negativa para etiquetas verticais. Como há apenas uma linha neste exemplo, você pode definir o valor como *0* (zero).

    - **Linhas por página:** *1*

        Este campo define o número de linhas que podem ser impressas em cada etiqueta.

        > [!NOTE]
        > Esta configuração faz com que uma etiqueta ZPL separada seja impressa para cada registro na tabela de etiquetas de onda.

1. Feche a página.
1. No Painel de Ações, selecione **Editar consulta**.
1. Na caixa de diálogo do editor de consultas, na guia **Intervalo** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *Tipo de trabalho*
    - **Critérios:** *Separação*

    Esta consulta garante que somente as linhas de trabalho de separação serão impressas na etiqueta, não as linhas de trabalho de colocação.

1. Se você quiser imprimir a ID do conhecimento de embarque, na guia **Junções** , selecione a tabela **Linhas de trabalho** e junte a tabela **Remessas** a ela.
1. Feche a caixa de diálogo do editor de consultas.
1. A FastTab **Layout do texto da impressora** tem três seções nas quais é possível escrever código da impressora: **Seção do cabeçalho** , **Seção do corpo** e **Seção do rodapé**. Na **Seção do cabeçalho** , no campo **Cabeçalho da etiqueta** , insira o código para o cabeçalho obrigatório. Por exemplo, se você estiver usando impressoras Zebra, poderá usar o código a seguir.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. Na **Seção do corpo** , no campo **Corpo da etiqueta** , insira o código ZPL para o corpo obrigatório. Veja aqui um exemplo.

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. Na **Seção do corpo** , no campo **Rodapé da etiqueta** , insira o código ZPL para o rodapé obrigatório. Veja aqui um exemplo.

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > Esta configuração imprimirá uma cópia de cada etiqueta. Se você precisar de mais cópias (por exemplo, uma cópia para cada lado do palete), defina o valor **n** para a seção **\^PQn** no rodapé como o número de cópias necessário. Por exemplo, para imprimir quatro cópias de cada etiqueta, especifique **\^PQ4**.

1. A segunda etiqueta agora está pronta para uso.
1. Crie um terceiro registro de layout com as seguintes configurações:

    - **ID do layout da etiqueta:** *Intervalo*
    - **Descrição:** *Etiqueta de intervalo*

1. No Painel de ações, selecione **Salvar**.
1. A FastTab **Layout do texto da impressora** tem três seções nas quais é possível escrever código da impressora: **Seção do cabeçalho** , **Seção do corpo** e **Seção do rodapé**. Na **Seção do cabeçalho** , no campo **Cabeçalho da etiqueta** , insira o código ZPL para o cabeçalho obrigatório. Veja aqui um exemplo.

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. Desta vez, o corpo não é obrigatório. Portanto, basta inserir o texto obrigatório na **Seção de rodapé**. Veja aqui um exemplo.

    ```plaintext
    ^XZ
    ```

    A terceira etiqueta agora está pronta para uso.

    > [!NOTE]
    > Essa terceira etiqueta é uma etiqueta de intervalo que será usada como um divisor entre os rolos de etiquetas.

### <a name="create-two-wave-label-types"></a>Criar dois tipos de etiqueta de onda

1. Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Tipos de etiqueta de onda**.
1. Crie um registro com as seguintes configurações:

    - **Tipo de etiqueta:** *Caixa*
    - **Descrição:** *Caixa*

1. Crie um segundo registro com as seguintes configurações:

    - **Tipo de etiqueta:** *Palete*
    - **Descrição:** *Palete*

### <a name="set-up-unit-sequence-groups"></a>Configurar grupos de sequências de unidade

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Grupos de sequências de unidade**.
1. Selecione ou crie um grupo **Ea Caixa PL**.
1. Para a linha **Caixa** , defina o campo **Tipo de nível de onda** como *Caixa*.
1. Para a linha **PL** , defina o campo **Tipo de nível de onda** como *Palete*.

### <a name="create-wave-label-templates"></a>Criar modelos de etiqueta de onda

1. Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Modelos de etiqueta de onda**.
1. Crie um modelo de etiqueta com as seguintes configurações:

    - **Nome do modelo de etiqueta:** *Etiquetas de caixa*
    - **Descrição:** *Etiquetas de caixa*
    - **Código da etapa da onda:** *Caixa*
    - **Depósito:** *62*

1. Na FastTab **Geral** , no campo **Tipo de etiqueta de onda** , selecione um valor, como *Caixa*.
1. Na FastTab **Detalhes do modelo de etiqueta de onda** , adicione uma linha com as seguintes configurações:

    - **ID do layout da etiqueta:** *Caixa*
    - **Nome da impressora:** Selecione uma impressora ZPL apropriada.
    - **Executar consulta:** *Sim* (esta configuração é opcional, mas recomendável para um desempenho ideal.)

1. No Painel de ações, selecione **Salvar**.
1. Opcional: se estiver configurando um design de etiqueta específico do cliente, você deve criar uma consulta para localizar a conta do cliente. Na FastTab **Detalhes do modelo de etiqueta de onda** , selecione **Editar consulta**. Em seguida, na caixa de diálogo do editor de consultas, na guia **Intervalo** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Remessas*
    - **Tabela derivada:** *Remessas*
    - **Campo:** *Número da conta*
    - **Critérios:** Insira o número da conta do cliente relevante.

    Quando terminar, selecione **OK** para fechar a caixa de diálogo do editor de consultas.

1. No Painel de Ação, selecione **Editar consulta** para abrir a caixa de diálogo do editor de consultas para todo o modelo de etiqueta.
1. Na caixa de diálogo do editor de consultas, na guia **Classificação** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *ID da linha de carga de referência (ID do Registro)*
    - **Direção da pesquisa:** *Crescente*

1. Adicione uma segunda linha com as seguintes configurações:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *ID da Remessa*
    - **Direção da pesquisa:** *Crescente*

1. Selecione **OK** para fechar a caixa de diálogo do editor de consultas.
1. Uma caixa de mensagem solicitará que você confirme a operação de redefinição do agrupamento. Selecione **Sim** para continuar.
1. No Painel de Ação, selecione **Grupo de modelos de etiqueta de onda**.
1. Na caixa de diálogo **Grupo de modelos de etiqueta de onda** , para a linha na qual o campo **Nome do campo de referência** está definido como *ID da Remessa* , defina os seguintes valores:

    - **Imprimir etiqueta de intervalo:** Marque esta caixa de seleção.
    - **ID do layout da etiqueta:** Selecione uma etiqueta de intervalo. (Por exemplo, selecione o layout da etiqueta *Intervalo* criado anteriormente neste cenário.)
    - **Nome da impressora:** Selecione a impressora para a etiqueta de intervalo. (Normalmente, para dividir os rolos de etiquetas, você deve selecionar a mesma impressora selecionada na FastTab **Detalhes do modelo de etiqueta de onda**. No entanto, outros cenários são possíveis.)

1. Para a linha na qual o campo **Nome do campo de referência** está definido como *ID da linha de carga de referência* , marque a caixa de seleção **ID de criação da etiqueta**.

    > [!NOTE]
    > Essa configuração criará uma sequência de etiquetas ("Caixa 1 de X") por linha de carga ao longo da onda, independentemente da configuração do agrupamento de trabalho. Essa sequência de etiquetas pode ser impressa em um layout de etiqueta. Além disso, etiquetas de remessas diferentes serão separadas pela etiqueta de intervalo selecionada.

1. Selecione **OK** para fechar a caixa de diálogo **Grupo de modelos de etiqueta de onda**.
1. Crie um segundo modelo de etiqueta com as seguintes configurações:

    - **Nome do modelo de etiqueta:** *Etiquetas de palete*
    - **Descrição:** *Etiquetas de palete*
    - **Código da etapa da onda:** *Palete*
    - **Depósito:** *62*

1. Na FastTab **Geral** , no campo **Tipo de etiqueta de onda** , selecione um valor, como *Palete*.
1. Na FastTab **Detalhes do modelo de etiqueta de onda** , adicione uma linha com as seguintes configurações:

    - **ID do layout da etiqueta:** *Palete*
    - **Nome da impressora:** Selecione uma impressora ZPL apropriada.
    - **Executar consulta:** *Sim* (esta configuração é opcional, mas recomendável para um desempenho ideal.)

1. No Painel de ações, selecione **Salvar**.
1. Opcional: se estiver configurando um design de etiqueta específico do cliente, você deve criar uma consulta para localizar a conta do cliente. Na FastTab **Detalhes do modelo de etiqueta de onda** , selecione **Editar consulta**. Em seguida, na caixa de diálogo do editor de consultas, na guia **Intervalo** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Remessas*
    - **Tabela derivada:** *Remessas*
    - **Campo:** *Número da conta*
    - **Critérios:** Insira o número da conta do cliente relevante.

    Quando terminar, selecione **OK** para fechar a caixa de diálogo do editor de consultas. 

1. No Painel de Ação, selecione **Editar consulta** para abrir a caixa de diálogo do editor de consultas para todo o modelo de etiqueta.
1. Na caixa de diálogo do editor de consultas, na guia **Classificação** , adicione uma linha com as seguintes configurações:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *ID da linha de carga de referência (ID do Registro)*
    - **Direção da pesquisa:** *Crescente*

1. Adicione uma segunda linha com as seguintes configurações:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *ID da Remessa*
    - **Direção da pesquisa:** *Crescente*

1. Selecione **OK** para fechar a caixa de diálogo do editor de consultas.
1. Uma caixa de mensagem solicitará que você confirme a operação de redefinição do agrupamento. Selecione **Sim** para continuar.
1. No Painel de Ação, selecione **Grupo de modelos de etiqueta de onda**.
1. Na caixa de diálogo **Grupo de modelos de etiqueta de onda** , para a linha na qual o campo **Nome do campo de referência** está definido como *ID da Remessa* , defina os seguintes valores:

    - **Imprimir etiqueta de intervalo:** Marque esta caixa de seleção.
    - **ID do layout da etiqueta:** Selecione uma etiqueta de intervalo. (Por exemplo, selecione o layout da etiqueta *Intervalo* criado anteriormente neste cenário.)
    - **Nome da impressora:** Selecione a impressora para a etiqueta de intervalo. (Normalmente, para dividir os rolos de etiquetas, você deve selecionar a mesma impressora selecionada na FastTab **Detalhes do modelo de etiqueta de onda**. No entanto, outros cenários são possíveis.)

1. Para a linha na qual o campo **Nome do campo de referência** está definido como *ID da linha de carga de referência* , marque a caixa de seleção **ID de criação da etiqueta**.

    > [!NOTE]
    > Essa configuração criará uma sequência de etiquetas ("Caixa 1 de X") por linha de carga ao longo da onda, independentemente da configuração do agrupamento de trabalho. Essa sequência de etiquetas pode ser impressa em um layout de etiqueta. Além disso, etiquetas de remessas diferentes serão separadas pela etiqueta de intervalo selecionada.

### <a name="configure-number-sequence-extensions"></a>Configurar extensões de sequência numérica

As extensões de sequência numérica controlam a conformidade com o GS1 de sequências numéricas específicas. Esta configuração é opcional para o cenário atual. Para obter mais informações e instruções de configuração, consulte [Configurar extensões de sequência numérica](../warehousing/configure-number-sequence-extensions.md).

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Criar uma ordem de venda e liberá-la para o depósito

1. Vá para **Vendas e marketing \> Ordem de venda \> Todas as ordens de venda**.
1. Crie uma ordem de venda com as seguintes configurações:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *62*

1. Adicione duas linhas da ordem de venda:

    - Linha 1 da ordem de venda:

        - **Número de item:** *A0001*
        - **Quantidade:** *9024*
        - **Unidade:** *ea* (9024 ea = 376 Caixa = 47 PL)

    - Linha 2 da ordem de venda:

        - **Número de item:** *A0002*
        - **Quantidade:** *9016*
        - **Unidade:** *ea* (9016 ea = 322 Caixa = 46 PL)

    > [!NOTE]
    > Os itens e as quantidades fornecidos aqui são apenas exemplos. Eles devem usar o grupo de sequências de unidade definido anteriormente, conversões de unidade apropriadas de *ea* para *Caixa* para *PL* devem ser definidas para eles, e eles devem ter estoque no depósito *62*. Para obter mais informações, consulte [Políticas de unidade de medida e estoque](unit-measure-stocking-policies.md).

1. Selecione a linha 1 da ordem de venda. Em seguida, na seção **Linha da ordem de venda** , no menu **Estoque** , selecione **Reservas**.
1. Na página **Reserva** , no Painel de Ação, selecione **Reservar lote** e, em seguida, feche a página.
1. Repita as etapas 4 e 5 para a linha 2 da ordem de venda.
1. No Painel de Ações, na guia **Depósito** , selecione **Liberar para o depósito**.

    Os seguintes eventos ocorrem: 

    - O sistema processa a remessa criada usando o modelo que inclui a etapa de impressão de etiquetas. O layout da etiqueta será usado para definir o formato da etiqueta, e o resultado será uma etiqueta impressa na impressora selecionada no modelo de etiqueta.
    - Etiquetas de onda são geradas e impressas. O número de etiquetas será igual ao número de caixas (neste exemplo, 376 etiquetas Caixa para a linha 1, 322 etiquetas Caixa para a linha 2, 47 etiquetas PL para a linha 1, 47 etiquetas PL para a linha 2 e duas etiquetas de intervalo com a ID de remessa).
    - Uma nova ID de conhecimento de embarque é gerada para as remessas. Se você configurou as extensões de sequência numérica, as IDs de etiqueta de onda seguirão o formato numérico de **SSCC-18**. 

Você pode exibir e reimprimir etiquetas de onda nas páginas a seguir:

- Todas as remessas \> Detalhes da remessa
- Todas as cargas \> Detalhes da carga
- Todas as ondas
- Etiquetas de onda
- Histórico da etiqueta de onda

Para a maioria dessas páginas, você pode encontrar a função relevante selecionando **Etiquetas de onda** no grupo **Informações relacionadas** na guia **Remessas** do Painel de Ação.
