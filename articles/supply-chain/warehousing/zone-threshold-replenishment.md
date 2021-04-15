---
title: Reabastecimento de limite de zona
description: O reabastecimento baseado em zona usa uma estratégia de reabastecimento mínimo/máximo (mín./máx.), mas ele avalia zonas de depósito inteiras e não apenas locais individuais. Portanto, os gerentes de depósito podem aprender mais rápido quando é necessário um estoque adicional em uma zona de separação.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d0a97ed7b01a32e9276433713448a672f83f7d02
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814359"
---
# <a name="zone-threshold-replenishment"></a>Reabastecimento de limite de zona

[!include [banner](../includes/banner.md)]

O reabastecimento baseado em zona usa uma estratégia de [reabastecimento](replenishment.md) mínimo/máximo (mín./máx.), mas ele avalia zonas de depósito inteiras e não apenas locais individuais. Portanto, os gerentes de depósito podem aprender mais rápido quando é necessário um estoque adicional em uma zona de separação.

A configuração desse recurso é semelhante à configuração de reabastecimento baseada em local. No entanto, ao configurar um modelo para reabastecimento mín./máx., você também pode especificar se o limite deve ser avaliado por local ou por zona. Se você configurar a avaliação baseada em zonas, deverá adicionar zonas específicas à consulta de seleção de zona.

Como o reabastecimento mín./máx. baseado em local, o reabastecimento mín./máx. baseado em zona segue a configuração de um limite de estoque mínimo que dispara a criação de trabalho de reabastecimento para os itens selecionados. Esse trabalho de reabastecimento aumentará o estoque até o limite máximo especificado para a zona.

> [!NOTE]
> Não há suporte aos processos de reabastecimento de zona para grades de produtos na versão atual.


Diferentemente do reabastecimento mín./máx. baseado em local, o reabastecimento mín./máx. baseado em zona não exige locais fixos para avaliar se os locais devem armazenar um item específico. Portanto, o reabastecimento baseado em zona permite que você use o reabastecimento mín./máx. mesmo que não tenha locais fixos para cada item ou grade de item no depósito. Quando uma quantidade na zona está abaixo do limite mínimo especificado, o trabalho de reabastecimento é criado. As diretivas de localização determinarão o local específico em que o estoque deverá ser inserido.

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a>Ativar o recurso Reabastecimento de limite de zona

Para que você possa usar o recurso *Reabastecimento de limite de zona*, ele deverá estar ativado no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso** *Reabastecimento de limite de zona*

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a>Configurar reabastecimento baseado em zona

Para configurar o reabastecimento baseado em zona, você deve configurar várias partes do sistema. Esta seção apresenta as várias configurações e fornece os valores de dados de demonstração que você poderá inserir se desejar trabalhar no cenário no final deste tópico.

### <a name="set-up-directive-codes"></a>Configurar códigos de diretiva

Os [códigos de diretiva](control-warehouse-location-directives.md) permitem que você seja mais específico ao definir o modelo de localização usado em um modelo de trabalho. Cada código estabelece um valor comum ao qual você pode se referir ao configurar cada tipo de modelo.

#### <a name="view-and-edit-directive-codes"></a>Exibir e editar códigos de diretiva

Para exibir ou editar códigos de diretiva, vá para **Gerenciamento de depósito \> Configuração \> Códigos de diretiva**.

#### <a name="prepare-demo-data-directive-codes"></a>Preparar códigos de diretiva de dados de demonstração

Este exemplo mostra como preparar um código de diretiva. Se pretende trabalhar no cenário no final deste tópico, use os valores de dados de demonstração fornecidos aqui. Caso contrário, use seus próprios valores.

1. Selecione a entidade legal **USMF** para trabalhar com os dados de demonstração.
1. Vá para **Gerenciamento de depósito \> Configuração \> Códigos de diretiva**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Código de diretiva:** _Reabastecimento de zona_
    - **Descrição de diretiva:** _Reabastecimento de zona_

1. Selecione **Salvar** para salvar o novo código.

### <a name="set-up-replenishment-templates"></a>Configurar modelos de reabastecimento

Os [modelos de reabastecimento mín./máx.](tasks/set-up-min-max-replenishment-process.md) são o principal mecanismo para manter níveis ideais em locais de separação. Nesses modelos, você deve configurar as regras que serão usadas para reabastecer o estoque no depósito. O reabastecimento para o qual os modelos podem ser usados inclui o reabastecimento baseado em zona.

#### <a name="view-and-edit-replenishment-templates"></a>Exibir e editar modelos de reabastecimento

Um modelo de reabastecimento é um conjunto de regras que controlam como e quando um local é reabastecido. Selecione um modelo para controlar quando e como o reabastecimento é feito. Para exibir ou editar modelos de reabastecimento, vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento**.

#### <a name="prepare-a-demo-data-replenishment-template"></a>Preparar um modelo de reabastecimento de dados de demonstração

Este exemplo mostra como preparar um modelo de reabastecimento. Se pretende trabalhar no cenário no final deste tópico, use os valores de dados de demonstração fornecidos aqui. Caso contrário, use seus próprios valores.

1. Selecione a entidade legal **USMF** para trabalhar com os dados de demonstração.
1. Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento**.
1. Selecione **Editar** para colocar a página no modo de edição.
1. No Painel de Ações, selecione **Novo** para adicionar uma linha à grade **Visão geral**.
1. Na nova linha, defina os valores a seguir. Aceite os valores padrão para todos os demais campos.

    - **Modelo de reabastecimento:** _Reabastecimento mín./máx. de zona_
    - **Descrição:** _Reabastecimento mín./máx. de zona_
    - **Tipo de reabastecimento:** _Mínimo ou máximo_

1. Selecione **Salvar**.
1. Enquanto a nova linha ainda estiver selecionada na grade **Visão geral**, selecione **Novo** acima da grade **Detalhes do Modelo de Reabastecimento** para adicionar uma linha associada ao modelo de reabastecimento *Reabastecimento mín./máx. de zona* que você acabou de criar.
1. Na nova linha, defina os seguintes valores:

    - **Número de sequência:** Insira _1_.
    - **Descrição:** Insira _Seleção de reabastecimento de zona_.
    - **Unidade de reabastecimento:** Selecione _ea_.
    - **Tipo de solicitação:** Deixe este campo em branco.
    - **Código de diretiva:** Este campo vincula o modelo de reabastecimento a uma diretiva de localização. Selecione o código de diretiva de dados de demonstração criado anteriormente (_Reabastecimento_).
    - **Modelo de trabalho:** Deixar este campo em branco.
    - **Quantidade mínima:** Este campo define a quantidade na qual o reabastecimento será disparado. Insira _50_.
    - **Quantidade máxima:** Este campo define a quantidade máxima de um item que pode estar presente em uma zona. O trabalho de reabastecimento gerado vai aumentar o estoque para essa quantidade. Insira _150_.
    - **Unidade:** Este campo define a unidade para os valores mínimo e máximo. Selecione _ea_.
    - **Incremento de demanda:** Selecione _Arredondar_.
    - **Reabastecer localizações fixas vazias:** Marque esta caixa de seleção.
    - **Reabastecer apenas localizações fixas:** Desmarque esta caixa de seleção.
    - **Modo de consulta de produto:** Selecione _Consulta de produto_.
    - **Escopo do limite de reabastecimento:** este campo define se o modelo deve ser avaliado por zona ou por localização específica. Selecione _Zona_.
    - **Depósito:** Selecione _61_.

1. Selecione **Selecionar produtos** acima da grade **Detalhes do Modelo de Reabastecimento**.
1. Na caixa de diálogo **Consulta do produto**, na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Tabela:** _Itens_
    - **Tabela derivada:** _Itens_
    - **Campo:** _Número do item_
    - **Critérios:** _A0001_

1. Selecione **OK** para salvar sua consulta e fechar a caixa de diálogo.
1. Selecione **Selecionar zonas para reabastecimento** acima da grade **Detalhes do Modelo de Reabastecimento**.
1. Na caixa de diálogo **Consulta de zona**, na guia **Intervalo**, adicione uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Tabela:** _Zona de depósito_
    - **Tabela derivada:** _Zona de depósito_
    - **Campo:** _ID da zona_
    - **Critérios:** _CHÃO_

1. Selecione **OK** para salvar sua consulta e fechar a caixa de diálogo.

### <a name="set-up-location-directives"></a>Configurar diretivas de localização

Diferente do reabastecimento mín./máx. baseado em local, o reabastecimento mín./máx. baseado em zona exige que você configure diretivas de local de seleção e diretivas de local de colocação, pois o sistema avalia a zona inteira e não apenas o local de separação do trabalho de saída.

#### <a name="view-and-edit-location-directives"></a>Exibir e editar diretivas de localização

Para exibir ou editar diretivas de localização, vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.

Para obter exemplos que mostram como usar as configurações para criar as diretivas de localização de separação e as diretivas de localização de colocação, consulte a próxima seção.

#### <a name="prepare-demo-data-location-directives"></a>Preparar diretivas de localização de dados de demonstração

Para preparar dados de demonstração de forma que possam ser usados no cenário no final deste tópico, você deve criar duas diretivas de localização: uma para separação e outra para colocação.

##### <a name="create-a-replenishment-pick-directive"></a>Criar uma diretiva de separação de reabastecimento

1. Selecione a entidade legal **USMF** para trabalhar com os dados de demonstração.
1. Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No painel esquerdo, defina o campo **Tipo de ordem de serviço** como _Reabastecimento_.
1. No Painel de Ações, selecione **Novo** para criar uma nova diretiva.
1. Defina os seguintes valores:

    - **Número de sequência:** aceite o valor padrão.
    - **Nome:** insira _Separação de zona_.
    - **Tipo de trabalho:** selecione _Separar_.
    - **Site:** selecione _6_.
    - **Depósito:** selecione _61_.
    - **Código de diretiva:** deixe este campo em branco.
    - **Várias SKUs:** defina esta opção como _Não_.

1. Selecione **Salvar** para criar uma diretiva com as configurações que você definiu até o momento.
1. Na FastTab **Linhas**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Número de sequência:** Insira _1_.
    - **Quantidade inicial:** insira _0_.
    - **Quantidade final:** insira _10000000_.
    - **Unidade:** Deixe este campo em branco.
    - **Localizar quantidade:** selecione _Nenhum_.
    - **Restringir por unidade:** marque ou desmarque esta caixa de seleção.
    - **Arredondar para unidade:** desmarque esta caixa de seleção.
    - **Localizar quantidade da embalagem:** desmarque esta caixa de seleção.
    - **Permitir divisão:** marque esta caixa de seleção.

1. Selecione **Salvar** para salvar a nova linha.
1. Embora a nova linha ainda esteja selecionada na grade **Linhas**, selecione **Nova** na FastTab **Ações de Diretiva de Localização** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Número de sequência:** Insira _1_.
    - **Nome:** insira _Separação em massa_.
    - **Uso de localização fixa:** selecione _Localizações fixas e não fixas_.
    - **Permitir estoque negativo:** desmarque esta caixa de seleção.
    - **Lote habilitado:** desmarque esta caixa de seleção.
    - **Estratégia:** selecione _Nenhum_.

1. Selecione **Salvar** para salvar a nova ação.
1. Com a nova ação ainda selecionada, selecione **Editar consulta** acima da grade **Ações de Diretiva de Localização**.
1. Uma caixa de diálogo de consulta é exibida, na qual você pode selecionar os locais a serem reabastecidos. Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Tabela:** _Localizações_
    - **Tabela derivada:** _Localizações_
    - **Campo:** _ID da zona_
    - **Critérios:** _MASSA_

1. Selecione **OK** para salvar sua consulta e fechar a caixa de diálogo.
1. Selecione **Salvar** para salvar sua diretiva de localização.

##### <a name="create-a-replenishment-put-directive"></a>Criar uma diretiva de colocação de reabastecimento

1. Na página **Diretivas de localização**, no painel esquerdo, verifique se o campo **Tipo de ordem de serviço** ainda está definido como _Reabastecimento_.
1. No Painel de Ações, selecione **Novo** para criar outra nova diretiva.
1. Defina os seguintes valores:

    - **Número de sequência:** aceite o valor padrão.
    - **Nome:** insira _Colocação de zona_.
    - **Tipo de ordem de serviço:** selecione _Colocar_.
    - **Site:** selecione _6_.
    - **Depósito:** selecione _61_.
    - **Código de diretiva:** selecione _Reabastecimento de zona_ para vincular esta diretiva de localização ao modelo de reabastecimento criado anteriormente, usando o código que você já criou.
    - **Várias SKUs:** defina esta opção como _Não_.

1. Selecione **Salvar** para criar uma diretiva com as configurações que você definiu até o momento.
1. Na FastTab **Linhas**, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Número de sequência:** Insira _1_.
    - **Quantidade inicial:** insira _0_.
    - **Quantidade final:** insira _10000000_.
    - **Unidade:** Deixe este campo em branco.
    - **Localizar quantidade:** selecione _Nenhum_.
    - **Restringir por unidade:** marque ou desmarque esta caixa de seleção.
    - **Arredondar para unidade:** desmarque esta caixa de seleção.
    - **Localizar quantidade da embalagem:** desmarque esta caixa de seleção.
    - **Permitir divisão:** marque esta caixa de seleção.

1. Selecione **Salvar** para salvar a nova linha.
1. Embora a nova linha ainda esteja selecionada na grade **Linhas**, selecione **Nova** na FastTab **Ações de Diretiva de Localização** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Número de sequência:** Insira _1_.
    - **Nome:** insira _Colocação de zona_.
    - **Uso de localização fixa:** selecione _Localizações fixas e não fixas_.
    - **Permitir estoque negativo:** desmarque esta caixa de seleção.
    - **Lote habilitado:** desmarque esta caixa de seleção.
    - **Estratégia:** selecione _Consolidar_.

1. Selecione **Salvar** para salvar a nova ação.
1. Com a nova ação ainda selecionada, selecione **Editar consulta** acima da grade **Ações de Diretiva de Localização**.
1. Uma caixa de diálogo de consulta é exibida, na qual você pode selecionar a zona a ser reabastecida. Essa zona deve ser a mesma zona especificada no modelo de reabastecimento. Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes valores:

    - **Tabela:** _Localizações_
    - **Tabela derivada:** _Localizações_
    - **Campo:** _ID da zona_
    - **Critérios:** _CHÃO_

1. Selecione **OK** para salvar sua consulta e fechar a caixa de diálogo.
1. Selecione **Salvar** para salvar sua diretiva de localização.

## <a name="scenario"></a>Cenário

Esta seção fornece um cenário de exemplo que mostra como trabalhar com o recurso.

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a>Preparar os dados de exemplo necessários para o cenário de exemplo

Antes de começar a trabalhar no cenário, você deve ativar os dados de exemplo e configurar o recurso conforme descrito nesta seção e na seção anterior deste tópico.

#### <a name="use-the-usmf-legal-entity"></a>Usar a entidade legal USMF

Para trabalhar no cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

#### <a name="prepare-additional-sample-data"></a>Preparar dados de exemplo adicionais

Depois de selecionar a entidade legal **USMF**, inclua os dados de exemplo adicionais necessários, conforme descrito na seção [Configurar reabastecimento baseado em zona](#setup) abordada antes neste tópico.

#### <a name="check-your-on-hand-inventory"></a>Verifique seu estoque disponível

Siga estas etapas para verificar se o sistema inclui estoque suficiente para dar suporte ao cenário de exemplo.

1. Verifique se há estoque disponível para o item *A0001* em dois locais diferentes na zona de separação (*CHÃO*) especificada no modelo de reabastecimento. No entanto, o estoque total deve ser menor que a quantidade mínima necessária (*50*) que é especificada no modelo de reabastecimento. Dessa forma, você pode simular como o cálculo ocorre para a zona inteira e não apenas para um único local. **Use qualquer um dos processos de depósito para ajustar o estoque, conforme necessário.**
1. Verifique se há estoque suficiente para o item *A0001* em um local de massa especificado na diretiva de localização de seleção de zona na qual o trabalho de reabastecimento deve separar os itens da ID de zona *MASSA*. O estoque total deve ser superior à quantidade máxima necessária (*150*) que é especificada no modelo de reabastecimento.
1. Opcional, mas recomendado: siga estas etapas para criar um diário de ajuste de estoque:

    1. Vá para **Gerenciamento de estoque \> Entradas de diário \> Itens \> Ajuste de estoque**.
    1. Selecione **Novo**.
    1. Na caixa de diálogo **Criar diário de estoque**, no campo **Depósito**, selecione *61*.
    1. Selecione **OK**.
    1. Na FastTab **Linhas do diário**, use o botão **Novo** para adicionar três linhas à grade e defina os valores a seguir. Ao concluir a configuração de cada linha, selecione **Salvar**.

        - **Linha 1:**

            - **Número de item:** *A0001*
            - **Local:** *6*
            - **Depósito:** *61*
            - **Localização:** *02A01R1S1B*
            - **Placa de licença:** selecione uma placa de licença existente na lista ou crie uma nova placa de licença.
            - **Quantidade:** *1000*

        - **Linha 2:**

            - **Número de item:** *A0001*
            - **Local:** *6*
            - **Depósito:** *61*
            - **Localização:** *07A01R2S1B*
            - **Placa de licença:** selecione uma placa de licença existente na lista ou crie uma nova placa de licença.
            - **Quantidade:** *15*

        - **Linha 3:**

            - **Número de item:** *A0001*
            - **Local:** *6*
            - **Depósito:** *61*
            - **Localização:** *07A01R1S1B*
            - **Placa de licença:** selecione uma placa de licença existente na lista ou crie uma nova placa de licença.
            - **Quantidade:** *10*

    1. No Painel de Ações, selecione **Validar**. Solucionar os erros encontrados antes de passar para a próxima etapa.
    1. No Painel de Ações, selecione **Lançar** para lançar o estoque no depósito.

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a>Cenário de exemplo: executar reabastecimento mín./máx. baseado em zona

Quando todos os dados de exemplo de pré-requisito estiverem ativos, você poderá disparar o reabastecimento seguindo essas etapas.

1. Vá para **Gerenciamento de depósito \> Reabastecimento \> Reabastecimentos**.
1. Na caixa de diálogo **Reabastecimento**, na FastTab **Registros a serem incluídos**, selecione **Filtrar**.
1. Na caixa de diálogo **Consulta**, na guia **Intervalo**, edite a linha da tabela padrão da seguinte maneira:

    - **Tabela:** selecione _Modelos de reabastecimento_.
    - **Tabela derivada:** selecione _Modelos de reabastecimento_.
    - **Campo:** selecione _Modelo de reabastecimento_.
    - **Critérios:** selecione _Reabastecimento mín./máx. de zona_. Esse modelo de reabastecimento é o modelo de reabastecimento criado durante a preparação dos dados de demonstração para esse cenário.

1. Selecione **OK** para salvar a consulta e voltar à caixa de diálogo **Reabastecimento**.
1. Selecione **OK** para executar o modelo de reabastecimento.

O trabalho de reabastecimento agora é criado para separar o estoque da zona *MASSA* e reabastecê-lo para a zona *CHÃO*.

## <a name="notes-and-tips"></a>Observações e dicas

Aqui estão algumas observações e dicas para trabalhar com o recurso:

- Para configurar o trabalho de reabastecimento que segue para a zona desejada, você pode vincular as linhas do modelo de reabastecimento e as diretivas de localização das seguintes maneiras:

    - Edite a consulta de cabeçalho da diretiva de localização e filtre as linhas do modelo de reabastecimento selecionado.
    - Use um código de diretiva na linha do modelo de reabastecimento e corresponda esse código com a diretiva de localização de colocação.

- Se você estiver usando locais dinâmicos, o trabalho de reabastecimento será criado para o primeiro local disponível ou para um local que já contenha estoque, se a ação diretiva de localização estiver configurada para usar a estratégia **Consolidar**.
- Se você estiver usando locais fixos e não zonas, deverá usar o [reabastecimento mín./máx. padrão](tasks/set-up-min-max-replenishment-process.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]