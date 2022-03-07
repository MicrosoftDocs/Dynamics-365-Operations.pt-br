---
title: Agrupamento de modelos de onda
description: O agrupamento de modelos de onda permite que o sistema use configurações de modelo de onda para determinar, com base em critérios definidos por você, como ele deve dividir linhas liberadas e atribuí-las a ondas novas ou existentes. Esse recurso pode ser útil em depósitos nos quais as ondas são criadas com base em critérios específicos, mas em que os gerentes preferem criar ondas de forma automática e não manual.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: b265c0d5cb43e151386fe90e3a3dea414ec0aca6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579895"
---
# <a name="wave-template-grouping"></a>Agrupamento de modelos de onda

[!include [banner](../includes/banner.md)]

O agrupamento de modelos de onda permite que o sistema use configurações de [modelo de onda](tasks/configure-wave-processing.md) para determinar, com base em critérios definidos por você, como ele deve dividir linhas liberadas e atribuí-las a ondas novas ou existentes. Esse recurso pode ser útil em depósitos nos quais as ondas são criadas com base em critérios específicos, mas em que os gerentes preferem criar ondas de forma automática e não manual. Ele permite que o sistema adicione cada remessa recém-liberada à primeira onda encontrada com valores de campo de agrupamento correspondente. Se não houver correspondência, o sistema criará uma nova onda para a nova remessa.

> [!IMPORTANT]
> O agrupamento de modelos de onda não tem suporte para os tipos de trabalho *separação de matéria-prima de produção* ou *separação de Kanban*. Isso ocorre porque o agrupamento de onda se baseia em remessas e esses tipos de trabalho não usam remessas.

## <a name="turn-on-the-wave-template-grouping-feature"></a>Ativar o recurso Agrupamento de modelos de onda

Para você usar o recurso *Agrupamento de modelos de onda*, ele deve estar ativado no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Agrupamento de modelos de onda*

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a>Definir um modelo de onda para usar o agrupamento de modelos de onda

Para disponibilizar o agrupamento de modelos de onda, siga estas etapas para configurar o [modelo de onda](tasks/configure-wave-processing.md).

1. Acesse **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
1. No painel esquerdo, selecione o modelo de onda a ser configurado. Se você estiver se preparando para trabalhar no cenário mais adiante neste tópico usando dados de demonstração, selecione o modelo **Padrão de remessa 62**.
1. Selecione **Editar** para colocar a página no modo de edição.
1. Na FastTab **Geral**, defina os seguintes valores:

    - **Automatizar criação da onda:** *Sim*
    - **Atribuir a ondas abertas:** *Sim*
    - **Processar onda na liberação para o depósito** *Não*

1. No Painel de Ações, selecione **Editar consulta** para abrir a caixa de diálogo de consulta.
1. Na caixa de diálogo de consulta, na guia **Classificação**, analise os critérios de classificação e verifique se há uma regra que inclua o campo que você deseja usar para agrupar suas ondas.

    Se você estiver se preparando para trabalhar no cenário usando dados de demonstração, adicione uma linha com os seguintes valores:

    - **Tabela:** *Remessas*
    - **Tabela derivada:** *Remessas*
    - **Campo:** *Serviço da operadora*

        > [!NOTE]
        > Depois de selecionar este valor, você receberá a seguinte mensagem: "O serviço da operadora de campo não é um campo de índice. Deseja adicionar classificação a ele?" Selecione **Sim** para adicionar classificação.

    - **Direção da pesquisa:** *Crescente*

1. Selecione **OK** para salvar as alterações e fechar a caixa de diálogo de consulta.
1. No Painel de Ações, selecione **Agrupamento de modelos de onda**.
1. Na página **Agrupamento de modelos de onda**, marque a caixa de seleção **Agrupar por** para cada linha que você deseja usar para agrupar linhas de ordem em ondas, conforme necessário. Se você estiver se preparando para trabalhar no cenário usando dados de demonstração, marque a caixa de seleção **Agrupar por** para a linha *Serviço da operadora*.
1. Selecione **Salvar**.
1. Feche a página **Agrupamento de modelos de onda**.
1. Selecione **Salvar** para salvar o seu modelo.

## <a name="scenario"></a>Cenário

Esta seção fornece um script saber o que esse recurso faz e como trabalhar com ele.

### <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

Você também pode usar este cenário como orientação para usar o recurso ao trabalhar em um sistema de produção. No entanto, nesse caso, você deve substituir seus próprios valores e talvez não tenha alguns tipos de registros necessários fornecidos pelos dados de demonstração padrão.

### <a name="scenario-wave-template-grouping"></a>Cenário: agrupamento de modelos de onda

Este cenário mostra como usar o agrupamento de modelos de onda para criar automaticamente várias ondas, com base em critérios de agrupamento definidos em um modelo de onda. Neste cenário, o modelo de onda é configurado no sistema para criar uma onda por serviço de operadora.

Antes de começar, prepare o modelo de onda, conforme descrito na seção [Definir um modelo de onda para usar o agrupamento de modelos de onda](#set-up-template) anteriormente neste tópico. Se você estiver trabalhando com dados de demonstração para esse cenário, utilize os valores de dados de demonstração sugeridos no procedimento. Essa configuração agrupará suas ondas de acordo com o serviço da operadora definido para cada ordem de venda.

#### <a name="create-sales-order-1"></a>Criar ordem de venda 1

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar uma ordem de venda.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - Na FastTab **Cliente**, defina o campo **Conta do cliente** como *US-004*.
    - Na FastTab **Geral**, defina o campo **Depósito**, como *62*.

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo **Criar ordem de venda**.
1. A nova ordem de venda é aberta na exibição **Linhas**. Anote o número da ordem de venda.
1. Alterne para a exibição do **Cabeçalho**.
1. Na guia **Remessa**, na seção **Transporte**, defina os seguintes valores:

    - **Transportadora:** *Carga aérea*
    - **Serviço da transportadora:** *Aéreo*

1. Alterne novamente para a exibição **Linhas**.
1. Na seção **Linhas da ordem de venda**, selecione **Adicionar linha** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Número de item:** *A0002*
    - **Quantidade:** *2*

1. Selecione a nova linha da ordem e, no menu **Estoque**, acima da grade, selecione **Reserva**.
1. Na página **Reserva**, no Painel de Ações, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.
1. Feche a página **Reserva** para retornar à ordem de venda.
1. No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.
1. Você recebe uma mensagem informativa que mostra a remessa e a onda dessa ordem. Anote o número da ID da onda e os números de ID da remessa.

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a>Exibir a onda que foi criada com base na ordem de venda 1

1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Selecione a ID da onda que foi criada com base na ordem de venda.
1. Selecione o link da ID da onda para abrir a página detalhes da onda.
1. Observe que a remessa foi adicionada à FastTab **Linhas da onda**.

#### <a name="create-sales-order-2"></a>Criar ordem de venda 2

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar uma ordem de venda.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - Na FastTab **Cliente**, defina o campo **Conta do cliente** como *US-005*.
    - Na FastTab **Geral**, defina o campo **Depósito**, como *62*.

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo **Criar ordem de venda**.
1. A nova ordem de venda é aberta na exibição **Linhas**. Anote o número da ordem de venda.
1. Alterne para a exibição do **Cabeçalho**.
1. Na guia **Remessa**, na seção **Transporte**, defina os seguintes valores:

    - **Transportadora:** *Movimento de flores*
    - **Serviço da operadora:** *Padrão*

1. Alterne novamente para a exibição **Linhas**.
1. Na seção **Linhas da ordem de venda**, selecione **Adicionar linha** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Número de item:** *A0001*
    - **Quantidade:** *1*

1. Selecione a nova linha da ordem e, no menu **Estoque**, acima da grade, selecione **Reserva**.
1. Na página **Reserva**, no Painel de Ações, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.
1. Feche a página **Reserva** para retornar à ordem de venda.
1. No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.
1. Você recebe uma mensagem informativa que mostra a remessa e a onda dessa ordem. Anote o número da ID da onda e os números de ID da remessa. Observe que a ID da onda difere da ID da onda da primeira ordem de venda.

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a>Exibir a onda que foi criada com base na ordem de venda 2

1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Selecione a ID da onda que foi criada com base na segunda ordem de venda.
1. Selecione o link da ID da onda para abrir a página detalhes da onda.
1. Observe que a remessa foi adicionada à FastTab **Linhas da onda**.

Uma nova onda foi criada para essa remessa, pois ela usa um serviço de operadora diferente da primeira ordem de venda.

#### <a name="create-sales-order-3"></a>Criar ordem de venda 3

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar uma ordem de venda.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - Na FastTab **Cliente**, defina o campo **Conta do cliente** como *US-006*.
    - Na FastTab **Geral**, defina o campo **Depósito**, como *62*.

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo **Criar ordem de venda**.
1. A nova ordem de venda é aberta na exibição **Linhas**. Anote o número da ordem de venda.
1. Alterne para a exibição do **Cabeçalho**.
1. Na guia **Remessa**, na seção **Transporte**, defina os seguintes valores:

    - **Transportadora:** *Carga Aérea*
    - **Serviço da transportadora:** *Aéreo*

1. Alterne novamente para a exibição **Linhas**.
1. Na seção **Linhas da ordem de venda**, selecione **Adicionar linha** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Número de item:** *A0001*
    - **Quantidade:** *1*

1. Selecione a nova linha da ordem e, no menu **Estoque**, acima da grade, selecione **Reserva**.
1. Na página **Reserva**, no Painel de Ações, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.
1. Feche a página **Reserva** para retornar à ordem de venda.
1. No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.
1. Você recebe uma mensagem informativa que mostra a remessa e a onda dessa ordem. Anote o número da ID da onda e os números de ID da remessa. A remessa foi atribuída à onda existente com base na primeira ordem de venda.

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a>Exibir a onda para as ordens de venda 1 e 3

1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Selecione a ID da onda que foi criada com base na terceira ordem de venda.
1. Selecione o link da ID da onda para abrir a página detalhes da onda.
1. Observe que a remessa foi adicionada à FastTab **Linhas da onda**, junto com a remessa da primeira ordem de venda.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]