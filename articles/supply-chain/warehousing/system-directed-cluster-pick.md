---
title: Separação de cluster direcionada pelo sistema
description: Este tópico fornece uma visão geral da separação de cluster direcionada pelo sistema no Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkCluster, WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: dca006ca00e7ff5aa3681daac713f1e93187cd9c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239175"
---
# <a name="system-directed-cluster-picking"></a>Separação de cluster direcionada pelo sistema

[!include [banner](../includes/banner.md)]

A separação de clusters é um processo de separação de peças que permite separar itens para várias ordens ao mesmo tempo, agrupando-os em clusters de separação. Em seguida, você terá que visitar o local de separação apenas uma vez. Normalmente, essa funcionalidade é usada com pequenas ou menores quantidades de separação de ordens que são menores que as quantidades do caso.

Quando a separação de clusters direcionados pelo sistema é configurada, você pode separar os cabeçalhos de trabalho em cluster, com base em um cluster gerado pelo sistema. As ordens de separações de cluster do sistema até o número de posições especificado no perfil do cluster. Portanto, é possível separar várias ordens ao mesmo tempo, sem a necessidade de criar um cluster manualmente.

A separação de cluster direcionada pelo sistema oferece uma alternativa para criação de cluster manual, no qual um perfil de cluster é usado para criar um cluster. Várias linhas relacionadas à configuração devem ser definidas no perfil de cluster antes de serem usadas:

- **Número de posições** corresponde ao número de ordens que serão colocadas em um cluster. Portanto, ele corresponde ao número de totes.
- **Dividir cluster** determina quando o cluster deve ser dividido.
- **Gerar ID de cluster** controla se o ID de cluster será gerado pelo sistema ou informado pelo usuário.
- **Classificar tipo de verificação** determina se a verificação de posição é necessária.

Um novo item de menu de dispositivo móvel é usado para a separação de cluster direcionada pelo sistema. A **ID do perfil do cluster** deve ser especificado para a opção **Direcionada por** selecionada. Além disso, as consultas de sequência de trabalho direcionada pelo sistema podem agrupar ordens com base em critérios específicos da empresa. Portanto, você pode otimizar ainda mais a atribuição de ordens de trabalho especificando critérios de classificação personalizados usando as consultas de sequência de trabalho direcionadas pelo sistema.

Quando a separação de clusters direcionados pelo sistema estiver habilitada, os trabalhadores de depósito são apresentados com um cluster em que as ordens de separação foram atribuídas a posições de cluster. Portanto, os trabalhadores podem começar a separar um item para várias ordens de trabalho visitando o local de separação apenas uma vez. O processo de separação para a separação de clusters direcionados pelo sistema é o mesmo que o processo de separação de clusters direcionada pelo usuário.

## <a name="enable-the-system-directed-cluster-picking-feature"></a>Habilitar o recurso de separação de cluster direcionado pelo sistema

Antes de poder usar esse recurso, ele deverá estar habilitado no seu sistema. Os administradores podem usar a página [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Aqui o recurso está listado como:

- **Módulo** - gerenciamento de Depósito
- **Nome do recurso** - separação de cluster direcionado pelo sistema

Esse recurso também requer a habilitação de um recurso dependente. O recurso dependente é:

- **Módulo** - gerenciamento de Depósito
- **Nome do recurso** - sequenciamento de trabalho direcionado pelo sistema em toda a organização

## <a name="set-up-system-directed-cluster-picking"></a>Configurar separação de cluster direcionada pelo sistema

### <a name="create-cluster-profiles"></a>Criar perfis de cluster

Os perfis de cluster controlam como o sistema cria cada cluster. Se forem necessários diferentes clusters, um perfil de cluster diferente deverá ser criado para cada item de menu de dispositivo móvel.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Perfis de cluster**.
2. Selecione **Novo**.
3. No campo **ID do perfil de cluster**, informe **2 Posições**.
4. No campo **Nome**, digite **2 Posições**.
5. Na Guia Rápida **Geral**, insira as seguintes informações:

    - **Gerar ID do cluster** - selecione **Sim**. Esta opção determina se a ID do cluster será criada automaticamente pelo sistema ou se o usuário a criará no início da separação. 
    - **Ativar posições** - selecione **Sim**. Esta opção determina se os nomes de posição são gerados automaticamente com base na configuração do nome da posição. Se esta opção for definida como **Não**, será usada a ID da placa de licença para a posição.
    - **Número de posições** - selecione **2**. Este campo determina o número máximo de posições que o cluster pode ter (ou seja, o número máximo de caixas, totes, etc.).
    - **Nome da posição** - selecione **Numérico**, para que as posições sejam nomeadas usando números contínuos. Se você selecionar **Alfabética**, as posições serão nomeadas em ordem alfabética.
    - **Dividir cluster em** - selecione **Colocar**. Este campo determina quando o cluster é dividido. 
    - **Classificar tipo de verificação** - selecione **Verificação da posição**. Este campo determina se a etapa posição de colocação é verificada.
        
6. Na Guia Rápida **Classificação de cluster**, é possível definir critérios de classificação, criando uma nova linha e inserindo estas informações:

    - **Sequência numérica** - selecione **1**. Esse campo determina a sequência pela qual o sistema classifica. Um valor é inserido automaticamente, mas você pode alterá-lo, se necessário.
    - **Nome do campo** - insira **WMSLocationId**. Este campo determina o campo que a linha usa para critérios de classificação.
    - **Classificação** - selecione **Crescente**. Este campo define se a classificação é feita em ordem crescente ou decrescente.

### <a name="create-a-mobile-device-menu-item"></a>Criar um item de menu de dispositivo móvel

Para criar um novo item de menu de dispositivo móvel para a separação de cluster dirigida pelo sistema e vincular a ID do perfil de cluster ao item de menu do dispositivo móvel, siga estas etapas.

1. Vá para **Gerenciamento de depósito > Configuração > Dispositivo móvel > Itens de menu de dispositivo móvel**.
1. Selecione **Novo**.
1. Na seção de cabeçalho, insira as seguintes informações:
    - **Nome do item de menu** - Cluster SD
    - **Título** - Cluster SD
    - **Modo** - Trabalho
    - **Usar trabalho existente** - sim

1. Na Guia Rápida **Geral**, insira as seguintes informações:
    - **Direcionado por** - separação de cluster direcionada pelo sistema
    - **Gerar placa de licença** - sim
    - **ID do perfil do cluster** - posição 2

1. Na Guia Rápida **Classes de trabalho**, configure a classe de trabalho válida para este item de menu do dispositivo móvel definindo os seguintes campos:
    - **ID da classe de trabalho** - Venda
    - **Tipo de ordem de trabalho** - Ordens de venda

1. No Painel de Ações **Itens de menu do dispositivo móvel**, selecione **Consultas de sequência de trabalho direcionada do sistema** e siga estas etapas para especificar uma nova consulta de sequência de trabalho direcionada pelo sistema:
    - Selecione **Novo** no Painel de Ações.
    - **Número de sequência** - 1
    - **Descrição** - prioridade do trabalho – ID do trabalho

1. No Painel de Ações, selecione **Editar consulta**
1. Selecione a guia **Classificação**
1. Selecione **Adicionar** para adicionar uma nova linha e, em seguida, insira o seguinte:
    - **Tabela** - Trabalho
    - **Tabela derivada** - Trabalho
    - **Campo** - Prioridade de trabalho
    - **Direção da pesquisa** - crescente
1. Selecione **Adicionar** para adicionar uma segunda linha e, em seguida, insira o seguinte:
    - **Tabela** - Trabalho
    - **Tabela derivada** - Trabalho
    - **Campo** - ID do Trabalho
    - **Direção da pesquisa** - crescente

1. O sistema agora classificará as IDs de trabalho no cluster, primeiro por prioridade de trabalho e, em seguida, por ID de trabalho.

### <a name="set-up-a-mobile-device-menu"></a>Configura um menu de dispositivo móvel

1. Vá para **Gerenciamento de depósito > Configuração > Dispositivo móvel > Menu de dispositivo móvel**.
1. Adicione o item de menu **Cluster SD** que você acabou de criar a um menu Dispositivo móvel.
1. Selecione o menu **Saída**.
1. Selecione **Editar** no Painel de Ações.
1. Role até encontrar **Cluster SD**.
1. Selecione **Cluster SD**, a seta que aponta para a lista **Estrutura de Menu** será habilitada.
1. Selecione o botão de **seta** para mover o item de menu **Cluster SD** para a estrutura de menu **Saída**.
1. Selecione **Cluster SD** na lista **Estrutura de Menu** e, em seguida, selecione as setas **PARA CIMA** e **PARA BAIXO** para mover o item de menu para a posição desejada no menu do dispositivo móvel.

## <a name="scenario"></a>Cenário

### <a name="create-picking-work"></a>Criar trabalho de separação

Antes de configurar a separação de cluster direcionada pelo sistema, você deverá criar trabalho de saída qualificado. O perfil de cluster criado anteriormente especifica duas posições de cluster. Portanto, você deve criar pelo menos duas IDs de trabalho. Neste cenário, você criará duas ordens de venda, reservar estoque, liberar as ordens de venda para o depósito e então processar manualmente a onda.

1. Vá para **Vendas e Marketing > Ordens de venda > Todas as ordens de venda**.
1. Selecione **Nova** no Painel de Ações para criar a primeira ordem de venda.
    - O menu **Criar ordem de venda** será aberto, insira as seguintes informações:
        - Na Guia Rápida **Cliente**, insira **Conta do cliente** - **US-004**.
        - Na Guia Rápida **Geral**, insira **Depósito** - **62**.
        - Selecione **OK** para fechar o menu e criar a ordem de venda.
    - Na Guia Rápida **Linhas da ordem de venda**, selecione **Adicionar linha** se uma nova linha não for adicionada automaticamente e insira o seguinte:
        - **Número do item** - A0001
        - **Quantidade** - 1
        - Selecione **Adicionar linha** para adicionar uma segunda linha.
        - **Número do item** - A0002
        - **Quantidade** - 3
    - Reserve o estoque para as duas linhas que você acabou de criar.
        - Selecione **Linha 1**.
        - No Painel de Ações **Linhas da ordem de venda**, selecione **Estoque** e então selecione **Reserva** na lista.
        - No formulário **Reserva**, selecione **Reservar lote** para reservar o estoque.
        - Feche o formulário **Reserva** quando a reserva estiver concluída.
        - Repita essas etapas para reservar o estoque para a **Linha 2**.
1. Selecione **Nova** no Painel de Ações para criar a segunda ordem de venda
    - O menu **Criar ordem de venda** será aberto, insira as seguintes informações:
        - Na Guia Rápida **Cliente**, insira **Conta do cliente** - **US-005**.
        - Na Guia Rápida **Geral**, insira **Depósito** - **62**.
        - Selecione **OK** para fechar o menu e criar a ordem de venda
    - Na Guia Rápida **Linhas da ordem de venda**, selecione **Adicionar linha** se uma nova linha não for adicionada automaticamente e insira as seguintes informações:
        - **Número do item** - A0001
        - **Quantidade** - 4
        - Selecione **Adicionar linha** para adicionar uma segunda linha.
        - **Número do item** - A0002
        - **Quantidade** - 2
    - Reserve o estoque para ambas as linhas que você acabou de criar.
        - Selecione **Linha 1**.
        - No Painel de Ações **Linhas da ordem de venda**, selecione **Estoque** e então selecione **Reserva** na lista.
        - No formulário **Reserva**, selecione **Reservar lote** para reservar o estoque.
        - Feche o formulário **Reserva** quando a reserva estiver concluída.
        - Repita essas etapas para reservar o estoque para a **Linha 2**.
    - Feche a ordem de venda e volte para a página de listagem **Todas as ordens de venda**.
1. Localize as duas ordens de venda que acabou de criar (talvez seja necessário atualizar a página). Na tabela, selecione as duas ordens de venda usando a marca de seleção da seção.
    - No Painel de Ações **Todas as ordens de venda**, selecione a guia **Depósito**.
    - No grupo **Ações** , selecione **Liberar para o depósito** para liberar as duas ordens de venda para o depósito.
1. Quando o processo de liberação para depósito for concluído, será exibida uma mensagem informativa.
    - As remessas serão criadas para cada ordem de venda.
    - Uma onda será criada e ambas as remessas serão atribuídas à onda. Anote a **ID da Onda**.
1. Vá para **Gerenciamento de depósito > Ondas de saída > Ondas de remessa > Todas as ondas**.
    - Na lista **Todas as ondas**, localize e selecione a **ID da Onda** criada na etapa anterior.
    - No Painel de Ações, selecione a guia **Onda**.
    - No grupo **Ondas**, selecione **Processo** para processar a onda e criar **Trabalho**.
    - As mensagens informativas serão geradas quando o processamento tiver sido concluído, indicando que o trabalho foi criado e que a onda foi lançada.
1. **Opcional**: vá para **Gerenciamento de depósito > Trabalho > Detalhes do trabalho** para exibir o trabalho criado. Duas IDs de trabalho diferentes serão criadas. Cada ID de trabalho tem duas linhas de separação.

### <a name="run-the-mobile-device-flow"></a>Execute o fluxo do dispositivo móvel

1. Entre no dispositivo móvel para um usuário no depósito **62**.
1. No **Menu Principal**, selecione **Saída**.
1. No menu **Saída**, selecione **Cluster SD** para iniciar a separação.
    - Um cluster é criado e as duas IDs de trabalho criadas anteriormente são anexadas. Se você tiver criado mais de duas IDs de trabalho, somente as duas primeiras serão adicionadas ao cluster. Observe que as IDs de trabalho são adicionadas ao cluster na ordem crescente, conforme especificado na configuração de consulta.

    > [!NOTE]
    > O novo cluster será criado automaticamente somente se IDs de trabalho adicionais forem criadas anteriormente. Caso contrário, a seguinte mensagem será exibida: "não é possível encontrar um trabalho suficiente para o cluster".

    - Depois que você selecionar o menu, a primeira tela de seleção será exibida. O sistema agrega todas as linhas de separação correspondentes das duas IDs de trabalho e o orienta a visitar o local de separação uma vez, de forma que você possa atender a ambas as ordens usando uma separação. Esse processo é feito da mesma forma que o processo de separação de clusters direcionada pelo usuário.

1. Confirme o local e o item da primeira separação selecionando **OK**.
    - A quantidade de separação será o total do item exibido nas ordens de venda no cluster.
1. Insira o nome da posição (Numérica ou Alfabética) para confirmar que a quantidade separada do item para a posição foi colocada na posição correta.
1. Repita esse processo até que todas as quantidades de item tenham sido separadas e colocadas na posição correta.
1. A última etapa no dispositivo móvel é **colocar** o cluster na localização final. Selecione **OK**
    - Quando a operação put é confirmada, o cluster é fechado e dividido, com base no valor definido para o campo **Dividir cluster em** no perfil de cluster. As IDs de trabalho também são fechadas.
1. Uma mensagem de "Cluster concluído" é exibida no dispositivo móvel.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]