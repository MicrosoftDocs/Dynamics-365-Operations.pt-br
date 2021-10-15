---
title: Transporte em contêineres
description: Este tópico descreve como automatizar o transporte de cargas em contêineres. O transporte em contêineres automatizado cria contêineres e o trabalho de separação para remessas quando um ciclo é processado.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSContainerType, WHSContainerGroup, WHSContainerizationTable, WHSContainerizationBreak, WHSCreateContainerBreak, WHSContainerStructure, WHSContainerTable, WHSContainerizatonHistory, WHSContainerPackingPolicyChange, WHSManifestShipmentContainers, WHSAllowedContainerTypeGroup, WHSPostMethod, WHSContainerCreateDialog, WHSContainerCloseDiag, WHSContainer
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9293beba6a251a670b918fecbb2315a5e94660b9
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572256"
---
# <a name="containerization"></a>Transporte em contêineres

[!include [banner](../includes/banner.md)]

Este tópico descreve como automatizar o transporte de cargas em contêineres. O transporte em contêineres automatizado cria contêineres e o trabalho de separação para remessas quando um ciclo é processado.

Para configurar o transporte em contêineres, você deverá criar o seguinte:

- **Tipo de contêiner** – define as características físicas dos contêineres. Use tipos do contêineres para embalar os itens de estoque em um tipo e tamanho de embalagem específico, como compartimentos ou paletes.
- **Grupos de contêineres** – crie grupos de tipos de contêiner que sejam semelhantes. Por exemplo, um grupo de contêineres pode incluir os tipos de contêineres que têm dimensões semelhantes. Um grupo de contêineres especifica a sequência na qual os contêineres são embalados, e a porcentagem de preenchimento de cada contêiner.
- **Modelo de criação de contêiner** – crie modelos que definem regras para o transporte em contêineres. Por exemplo, regras para misturar o estoque e outras estratégias de embalagem.
- **Modelos de ciclo** – configure um ou mais modelos de ciclo para criar o trabalho de separação para transporte em contêineres.

## <a name="create-wave-templates-for-containerization"></a>Criar modelos de ciclo para transporte em contêineres

Você deve configurar um ou mais modelos de ciclo de remessa para transporte em contêineres. Os modelos de ciclo incluem os critérios que determinam o seguinte:

- Como processar ciclos. Isso pode ser manual ou automático.
- Como criar o trabalho de separação. Isso é determinado pelos métodos de ciclo. O modelo de ciclo deve incluir o método de **transporte em contêineres** .
- Como corresponder itens ou linhas de alocação com um ciclo.

Para obter mais informações, consulte [Modelos de ciclo](wave-templates.md).

## <a name="create-container-types"></a>Criar tipos de contêiner

Use tipos de contêiner para criar as descrições de contêineres, incluindo valores máximo de dimensões físicas de tamanho e capacidade de peso. Quando um ciclo de transporte em contêineres for processado, os contêineres serão criados com base nas informações do tipo de contêiner.

Para configurar um tipo de contêiner, siga estas etapas:

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Tipo de contêiner**.
1. Selecione **Novo** para criar um novo tipo de contêiner.
1. Insira um identificador exclusivo (ID) e uma descrição para o tipo de contêiner.
1. No campo **Peso da tara**, insira o peso real ou previsto do contêiner.
1. No campo **Peso máximo**, insira o peso máximo que o contêiner pode ter.
1. Nos campos **Volume máximo do transporte em contêineres**, **Tamanho máximo do transporte em contêineres**, **Largura máxima do transporte em contêineres** e **Altura máxima do transporte em contêineres**, especifique as dimensões físicas do contêiner.

    > [!NOTE]
    > Os valores do tamanho e largura são permutáveis. Isso significa que você pode girar itens lateralmente, ou no eixo x, se necessário. Por exemplo, se o tamanho for 2 metros, e a largura for 1 metro, você pode alterar o tamanho para 1 metro e a largura para 2 metros. Observe que isso não se aplica à dimensão de altura. Não é possível alterar o valor da altura para girar um item verticalmente.

1. Selecione valores de atributo personalizado para o contêiner nos campos de atributos. Os atributos são valores personalizados usados para filtrar ou classificar itens com base em um valor que, de outra forma, não estará disponível. Por exemplo, se quiser embalar os itens para um cliente específico, você poderá criar um atributo para o nome do cliente. Você cria esses atributos na página **Atributos do contêiner**.

## <a name="create-container-groups"></a>Criar grupos de contêineres

Você pode configurar grupos lógicos de tipos de contêiner. Para cada grupo, você pode especificar a sequência na qual deverá embalar os contêineres e a porcentagem dos contêineres a ser preenchida. As dimensões de tamanho do item determinam se ele caberá em um contêiner. O contêiner que é o mais próximo às dimensões de tamanho do item será usado. Se você tiver vários tipos de contêiner em um grupo, recomendamos que você organize a sequência pelo tamanho, de forma o contêiner maior é o primeiro, número 1 na sequência, e o contêiner menor é o último.

Para configurar um grupo de contêineres, siga estas etapas:

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Grupos de contêineres**.
1. Selecione **Novo** para criar um grupo de contêineres.
1. Insira uma ID exclusiva e uma descrição para o grupo de contêineres.
1. Na Guia Rápida **Detalhes**, selecione **Novo** para adicionar um tipo de contêiner ao grupo.
1. No campo **Tipo de contêiner**, selecione um tipo de contêiner.
1. Selecione **Mover para cima** ou **Mover para baixo** para especificar a sequência na qual os tipos de contêiner são embalados.

## <a name="create-container-build-templates"></a>Criar modelos de criação de contêiner

Você pode configurar regras para o processo de transporte em contêineres, como regras de combinação de estoque e outras estratégias de embalagem. Por exemplo, você pode configurar uma regra de modo que os trabalhadores não possam embalar as linhas de alocação que representem ordens de venda de clientes diferentes no mesmo contêiner.

Para configurar um modelo de criação de contêiner, siga estas etapas:

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Contêineres** \> **Modelo de criação de contêiner**.
1. Crie um novo modelo de criação de contêiner.
1. Nos campos **Nome do transporte em contêineres** e **Número de sequência**, insira o nome do modelo de transporte em contêineres e a ordem que corresponde às linhas de alocação.

    > [!NOTE]
    > O sistema aplicará o primeiro modelo no qual a linha de alocação atenda aos critérios de consulta. Portanto, coloque o modelo com os critérios mais específicos na parte superior da lista. Quanto mais amplos os critérios, maior a probabilidade de uma linha de alocação atender aos critérios. Isso pode resultar em linhas atribuídas ao contêiner incorreto. Se necessário, você poderá selecionar **Mover para cima** ou **Mover para baixo** para alterar a sequência de modelos.

1. No campo **ID do grupo de contêineres**, selecione o grupo de contêineres do qual os contêineres serão criados.
1. No campo **Tipos de consulta base**, selecione o tipo de consulta que determinará o que embalar e no que basear a consulta do filtro. As opções a seguir estão disponíveis:

      - **Linha de alocação de vendas** – linhas de alocação de embalagem criadas para as ordens de venda.
      - **Linha de alocação de transferência** – linhas de alocação de embalagem criadas para as ordens de transferência.
      - **Contêiner** – embale um contêiner que já tenha sido criado pelo processo de transporte em contêiner. Por exemplo, isso é usado para aninhar contêineres.

        > [!NOTE]
        > Para usar contêineres aninhados, você deverá tornar o método de transporte em contêineres repetível. Para obter mais informações, consulte [Modelos de ciclo](wave-templates.md).

1. Na Guia Rápida **Geral**, no campo **Código de etapa do ciclo**, insira o identificador exclusivo do método do processo de ciclo que vincula o modelo de criação de contêiner às etapas em um modelo de ciclo.
1. Marque a caixa de seleção **Permitir separações divididas** para permitir que os trabalhadores embalem itens de uma ordem de trabalho em contêineres separados. Isso requer que a quantidade total seja ajustada ao contêiner. A maior unidade de medida na linha de alocação sempre será usada.
1. No campo **Embalar por unidade**, selecione a unidade de medida que representará o contêiner. Por exemplo, você pode indicar que uma caixa é um contêiner. Se você embalar por unidade de medida, também não poderá especificar um grupo de contêineres porque a unidade de medida é o contêiner.
1. No campo **Estratégia de embalagem de contêiner**, selecione a estratégia de embalagem a ser usada. As opções a seguir estão disponíveis:

    > [!NOTE]
    > A estratégia se aplica somente às linhas de alocação de venda e linhas de alocação de transferência.

      - **Embalar em todos os contêineres abertos** – o sistema avalia se a linha de alocação caberá em qualquer contêiner que for criada durante o ciclo de transporte em contêiner.
      - **Embalar somente no contêiner atual** – o sistema avalia somente se a linha de alocação caberá no contêiner recentemente criado.

    Para obter mais informações e exemplos que mostrem como trabalhar com estratégias de embalagem de contêineres, consulte [Estratégias de embalagem de contêineres](container-packing-strategy-overview.md).

1. Para configurar regras para linhas de alocação de embalagem em contêineres, selecione **Divisões da Lógica de Combinação**. Por exemplo, você pode criar uma regra que permitirá que os funcionários embalem linhas de alocação para dois itens diferentes no mesmo contêiner. Para definir uma regra de combinação, siga estas etapas:

    1. Na página **Divisões da Lógica de Combinação**, selecione **Nova**.
    1. No campo **Tabela**, selecione a tabela que contém o campo a ser usado como critério para a divisão da lógica de combinação.
    1. No campo **Seleção de Campo**, selecione o campo para usar como critério para a divisão da lógica de combinação.
    1. Repita essas etapas até adicionar todos os critérios para a divisão da lógica de combinação.

    > [!NOTE]
    > Se você usar a lógica de combinação, recomendamos que você classifique pelos mesmos campos nos critérios de consulta de pesquisa. Isso reduzirá o número de contêineres criados.
