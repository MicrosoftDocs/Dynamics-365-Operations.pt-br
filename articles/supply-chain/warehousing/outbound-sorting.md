---
title: Classificação de saída
description: Este tópico contém informações sobre classificação de saída. Esta funcionalidade facilita a manipulação de pequenos contêineres e ajuda os trabalhadores do depósito a planejar e organizar melhor a capacidade dos paletes no caminhão.
author: Mirzaab
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 3c576209a86f776ac424f7fb9f2b606bea774a67
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828385"
---
# <a name="outbound-sorting"></a>Classificação de saída

[!include [banner](../includes/banner.md)]

Esta funcionalidade facilita a manipulação de pequenos contêineres e ajuda os trabalhadores do depósito a planejar e organizar melhor a capacidade dos paletes no caminhão. Quando você usa a classificação de saída, pode classificar os contêineres embalados no palete correto depois que eles tiverem estado em uma estação de embalagem. Você também pode criar uma hierarquia de embalagem.

Esta funcionalidade permite criar paletes de contêineres que são embalados por meio da funcionalidade de embalagem. O contêiner não é enviado para o local da remessa final porque está no fluxo de embalagem original. Em vez disso, os funcionários podem fechar o contêiner e movê-lo para um local do tipo classificação. Eles podem então classificar os contêineres em posições, e cada uma tem uma placa de licença (LP). Depois que os contêineres forem classificados, poderá ser criado um trabalho para enviar a LP inteira à doca de remessa final ou aos locais de espera com base nas diretivas de localização ou nas suas necessidades. Além disso, a ação de fechamento da posição de classificação pode mover o estoque imediatamente para o local de remessa final e separá-lo para a ordem.

## <a name="turn-on-the-outbound-sorting-feature"></a>Ativar o recurso Classificação de saída

Para que você possa usar o recurso, ele deve estar ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *classificação de saída*

## <a name="setup"></a>Instalação

Para este cenário, você deve usar dados de demonstração **USMF** padrão e o depósito *62*. Você também deve concluir a configuração descrita nas subseções a seguir.

### <a name="set-up-a-wave-template"></a>Configurar um modelo de onda

Esta configuração processa a onda automaticamente e cria um trabalho quando uma linha é liberada para o depósito.

1. Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
1. Na lista de modelos, selecione **Depósito 62**.
1. Na FastTab **Geral**, verifique se a opção **Processar onda na liberação para o depósito** está definida como *Sim*.

### <a name="set-up-a-worker"></a>Configurar um trabalhador

A estação de embalagem é considerada um local. Os trabalhadores do depósito que se conectam na estação de embalagem veem e trabalham somente em remessas e contêineres planejados nessa localização de embalagem específica. Um usuário que entra no Microsoft Dynamics 365 deve estar configurado como trabalhador no Gerenciamento de depósito. Se o nome do usuário não está na lista de usuários de trabalho, use o procedimento a seguir para adicioná-lo.

> [!NOTE]
> Essas etapas supõem que o usuário já existe no sistema e que foi associado a um funcionário ou trabalhador no módulo **Recursos Humanos**.

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalhador**.
1. Selecione **Novo**.
1. No campo **Trabalhador**, selecione o usuário de destino na lista de funcionários.
1. Escolha **Selecionar**.
1. No Painel de ações, selecione **Salvar**.
1. Na FastTab **Usuários**, selecione **Novo** para criar uma conta de dispositivo móvel e defina os seguintes valores para ela:

    - **ID do Usuário:** insira uma ID exclusiva.
    - **Nome de usuário:** insira um nome para a ID.
    - **Depósito padrão:** *62*
    - **Nome do menu:** *Principal*

1. No Painel de ações, selecione **Salvar**.
1. A caixa de diálogo **Definir senha** é exibida e nela você pode criar uma senha simples que o usuário pode usar para entrar no aplicativo móvel. Defina os seguintes valores:

    - **Senha:** insira uma senha simples.
    - **Confirmar senha:** insira a mesma senha novamente.

1. Selecione **Definir senha**.

    Uma notificação na Central de Ações informa que a senha foi definida para o usuário que você criou.

### <a name="create-a-location-type"></a>Criar um tipo de localização

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Tipos de localização**.
1. No Painel de Ação, selecione **Novo** para criar um tipo de localização e defina os seguintes valores:

    - **Tipo de localização:** *CLASSIFICAR*
    - **Descrição:** *Classificar*

1. No Painel de ações, selecione **Salvar**.

### <a name="set-up-warehouse-management-parameters"></a>Configurar parâmetros de Gerenciamento de depósito

1. Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na guia **Geral**, na FastTab **Tipos de localização**, defina o campo **Tipo de localização de classificação** como *CLASSIFICAR*.
1. No Painel de ações, selecione **Salvar**.

### <a name="set-up-a-location-profile"></a>Configurar um perfil de localização

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho, defina os seguintes valores:

    - **ID do perfil de localização:** *Classificação*
    - **Nome:** *Classificação*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Formato de localização:** *ASRB* (Corredor-Rack-Prateleira-Compartimento)
    - **Tipo de localização:** *CLASSIFICAR*
    - **Usar rastreamento da placa de licença:** *Sim*
    - **Permitir itens mistos:** *Sim* (Quando você define esta opção como *Sim*, a opção **Permitir lotes de estoque mistos** é definida automaticamente como *Sim* e não pode ser alterada de modo independente.)

1. Selecione **Salvar**.

### <a name="set-up-a-location"></a>Configurar uma localização

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**.
1. No cabeçalho, desmarque a caixa de seleção **Gerar dígitos de verificação para localização**.
1. No Painel de Ação, selecione **Novo** para criar uma localização e defina os seguintes valores:

    - **Depósito:** *62*
    - **Localização:** *SORT*
    - **ID do perfil de localização:** *CLASSIFICAÇÃO*

1. Selecione **Salvar**.

### <a name="set-up-an-outbound-sorting-template"></a>Configurar um modelo de classificação de saída

O modelo de classificação de saída determina se o trabalho é criado fora da localização de classificação e se a classificação é feita manual ou automaticamente.

Para este cenário, você criará um modelo de classificação de saída para criar paletes após a estação de embalagem.

1. Vá para **Gerenciamento de Depósito \> Configuração \> Embalagem \> Modelo de classificação de saída**.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho do novo modelo, defina os seguintes valores:

    - **ID do modelo de classificação de saída:** *Trabalho Automático*
    - **Descrição:** *Criação de Trabalho Automático*
    - **Tipo de modelo de classificação de saída:** *Contêiner*
    - **Depósito:** *62*
    - **Localização:** *SORT*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Verificação de classificação:** *Verificação da posição*
    - **Criar trabalho no fechamento da posição:** *Sim*

        Se esta opção for definida como *Sim*, quando a posição for fechada, será criado um trabalho para mover o estoque para a localização da remessa final. Se ela for definida como *Não*, o estoque será separado imediatamente para a ordem quando a posição for fechada.

    - **Atribuição da posição:** *Automática*

        Se este campo for definido como *Manual*, o usuário sempre deverá indicar a posição para classificar o estoque. Se ele for definido como *Automática*, o sistema guiará o estoque automaticamente para uma posição sempre que possível, com base nas divisões do modelo de classificação.

1. Selecione **Salvar** para tornar o botão **Editar consulta** disponível no Painel de Ação.
1. No Painel de Ações, selecione **Editar Consulta**.
1. No editor de consultas, na guia **Classificação**, adicione uma linha com os seguintes valores:

    - **Tabela:** *Remessas*
    - **Tabela derivada:** *Remessas*
    - **Campo:** *Serviço da operadora*

        Quando selecionar esse valor, você poderá receber a seguinte mensagem: "O campo Serviço da transportadora não é um campo de índice. Deseja adicionar classificação a ele?" Selecione **Sim**.

    - **Direção da pesquisa:** *Crescente*

1. Selecione **OK**.
1. Você poderá receber a seguinte mensagem: "O agrupamento será redefinido, continuar?" Selecione **Sim**.

    O botão **Divisões do modelo de classificação de saída** no Painel de Ação ficará disponível.

1. No Painel de Ação, selecione **Divisões do modelo de classificação de saída**.
1. Na caixa de diálogo **Critérios de classificação de saída**, defina os seguintes valores:

    - **Nome da tabela de referência:** *Remessas*
    - **Nome do campo de referência:** *Serviço da transportadora*
    - **Agrupar por campo:** marque essa caixa de seleção para agrupar as remessas por serviço da transportadora.

1. Selecione **OK** para salvar suas configurações e fechar a caixa de diálogo.

### <a name="set-up-container-packing-policies"></a>Configurar políticas de embalagem de contêiner

1. Vá para **Gerenciamento de depósito \> Configuração \> Contêineres \> Políticas de embalagem de contêiner**.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho da nova política, defina os seguintes valores:

    - **Política de embalagem de contêiner:** *Classificar*
    - **Descrição:** *Classificar*

1. Na FastTab **Visão geral**, defina os seguintes valores:

    - **Depósito:** *62*
    - **Local padrão para classificação:** *CLASSIFICAR*
    - **Unidade de peso:** *kg*
    - **Política de fechamento de contêiner:** *Liberação automática*
    - **Política de liberação de contêiner:** *Atribuir contêiner a posição de classificação de saída*

1. Selecione **Salvar**.

### <a name="set-up-packing-profiles"></a>Configurar perfis de embalagem

Crie um novo perfil de embalagem que será usado junto com a funcionalidade de classificação.

1. Vá para **Gerenciamento de depósito \> Configuração \> Embalagem \> Perfis de embalagem**.
1. No Painel de Ação, selecione **Novo** para criar uma linha e defina os seguintes valores:

    - **ID do perfil de embalagem:** *Classificar*
    - **Descrição:** *Classificar*
    - **Política de embalagem de contêiner:** *Classificar*
    - **Modo de ID do Contêiner:** *Automático*
    - **Tipo de contêiner:** *Caixa-Grande*
    - **Criar automaticamente contêiner no fechamento do contêiner:** desmarcada (= *Não*)

1. Selecione **Salvar**.

### <a name="set-up-work-classes"></a>Configurar classes de trabalho

Configure uma classe de trabalho que será usada junto com a classificação.

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.
1. No Painel de Ação, selecione **Novo** para criar uma classe de trabalho e defina os seguintes valores:

    - **ID da classe de trabalho:** *Classificar*
    - **Descrição:** *Classificar*
    - **Tipo de ordem de serviço:** *Separação do estoque classificado*

1. Selecione **Salvar**.

### <a name="set-up-mobile-device-menu-items"></a>Configurar itens de menu de dispositivo móvel

#### <a name="set-up-a-new-pallet-menu-item"></a>Configurar um item de menu de novo palete

Crie um item de menu de dispositivo móvel para criar paletes durante a classificação.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho, defina os seguintes valores:

    - **Nome do item de menu:** *Criação do palete*
    - **Título:** *Criação do palete*
    - **Modo:** *Indireto*
    - **Usar trabalho existente:** *Não*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Código de atividade:** *Classificação de saída*

        Quando esse campo é definido como *Classificação de saída*, é exibido o campo **ID do modelo de classificação de saída**.

    - **Usar guia de processo:** *Sim*

        Quando o campo **Código de atividade** está definido como *Classificação de saída*, esta opção é definida automaticamente como *Sim*.

    - **ID do modelo de classificação de saída:** *Trabalho Automático*

1. Selecione **Salvar**.

#### <a name="set-up-a-new-loading-menu-item"></a>Configurar um item de menu de nova carga

Em seguida, crie um item de menu que permita aos usuários mover os itens de estoque classificados para a localização de remessa.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho, defina os seguintes valores:

    - **Nome do item de menu:** *Carregar da Classificação*
    - **Título:** *Carregar da Classificação*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Sim*

1. Na FastTab **Geral**, defina o campo **Direcionado por** como *Dirigido pelo usuário*.
1. Na FastTab **Classes de trabalho**, selecione **Novo** e defina os seguintes valores:

    - **ID da classe de trabalho:** *CLASSIFICAR*
    - **Tipo de ordem de serviço:** *Separação do estoque classificado*

1. Selecione **Salvar**.

### <a name="set-up-the-mobile-device-menu"></a>Configura o menu de dispositivo móvel

Agora, você deve adicionar os novos itens de menu ao menu do dispositivo móvel.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. Selecione o menu **Saída**.
1. No Painel de Ações, selecione **Editar**.
1. Na coluna **Menus e itens de menu disponíveis**, localize e selecione **Criação do palete**.
1. Selecione o botão de seta para a direita para mover **Criação do palete** para a coluna **Estrutura de menu**.
1. Use os botões de seta para cima e seta para baixo para colocar o item de menu **Criação do palete** na posição desejada no menu do dispositivo móvel.
1. Selecione **Salvar**.
1. Repita este procedimento para adicionar o item de menu **Carregar da Classificação** ao menu **Saída**.

### <a name="set-up-location-directives"></a>Configurar diretivas de localização

As *diretivas de localização* são regras que ajudam a identificar localizações de separação e armazenamento para o movimento do estoque. Agora, você deve criar uma regra para gerenciar o trabalho de classificação.

#### <a name="set-up-a-single-sku-directive"></a>Configurar uma diretiva de SKU única

1. Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No painel esquerdo, altere o valor do campo **Tipo de ordem de serviço** para *Separação do estoque classificado*.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho, defina os seguintes valores:

    - **Sequência:** *1*
    - **Nome:** *Porta da baía*

1. Na FastTab **Diretivas de localização**, defina os seguintes valores:

    - **Tipo de trabalho:** *Colocar*
    - **Local:** *6*
    - **Depósito:** *62*
    - **Várias SKUs:** *Não*

1. Selecione **Salvar** para disponibilizar a barra de tarefas na FastTab **Linhas**.
1. Na FastTab **Linhas**, selecione **Novo** e defina os valores a seguir na nova linha. Aceite os valores padrão para todos os demais campos.

    - **Sequência:** *1*
    - **De:** *0*
    - **Até:** *1.000.000*

1. Selecione **Salvar** para disponibilizar a barra de ferramentas na FastTab **Ações de Diretiva de Localização**.
1. Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** e defina os valores a seguir na nova linha. Aceite os valores padrão para todos os demais campos.

    - **Sequência:** *1*
    - **Nome:** *Porta da baía*

1. Selecione **Salvar**.
1. Na FastTab **Ações de Diretiva de Localização**, selecione **Editar consulta**.
1. Na guia **Intervalo** do editor de consultas, localize a linha na qual o campo **Campo** está definido como *Local*. Defina o campo **Critérios** dessa linha como *Baydoor*.
1. Selecione **OK** para salvar as configurações e fechar o editor de consultas.

#### <a name="set-up-a-multiple-sku-directive"></a>Configurar uma diretiva de várias SKUs

1. Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No painel esquerdo, altere o valor do campo **Tipo de ordem de serviço** para *Separação do estoque classificado*.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho, defina os seguintes valores:

    - **Sequência:** *2*
    - **Nome:** *Baydoor Multi*

1. Na FastTab **Diretivas de localização**, defina os seguintes valores:

    - **Tipo de trabalho:** *Colocar*
    - **Local:** *6*
    - **Depósito:** *62*
    - **Várias SKUs:** *Sim*

1. Selecione **Salvar** para disponibilizar a barra de tarefas na FastTab **Linhas**.
1. Na FastTab **Linhas**, selecione **Novo** e defina os valores a seguir na nova linha. Aceite os valores padrão para todos os demais campos.

    - **Sequência:** *1*
    - **De:** *0*
    - **Até:** *1.000.000*

1. Selecione **Salvar** para disponibilizar a barra de ferramentas na FastTab **Ações de Diretiva de Localização**.
1. Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** e defina os valores a seguir na nova linha. Aceite os valores padrão para todos os demais campos.

    - **Sequência:** *1*
    - **Nome:** *Baydoor Multi*

1. Selecione **Salvar**.
1. Na FastTab **Ações de Diretiva de Localização**, selecione **Editar consulta**.
1. Na guia **Intervalo** do editor de consultas, localize a linha na qual o campo **Campo** está definido como *Local*. Defina o campo **Critérios** dessa linha como *Baydoor*.
1. Selecione **OK** para salvar as configurações e fechar o editor de consultas.

### <a name="set-up-work-templates"></a>Configurar modelos de trabalho

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. Altere o valor do campo **Tipo de ordem de serviço** para *Separação do estoque classificado*.
1. No Painel de Ação, selecione **Novo** para criar um modelo de trabalho.
1. Na guia **Visão geral**, defina os seguintes valores:

    - **Sequência:** *1*
    - **Modelo de trabalho:** *Classificar*
    - **Descrição do modelo de trabalho:** *Classificar*

1. Selecione **Salvar** para disponibilizar a FastTab **Detalhes do Modelo de Trabalho**.
1. Na FastTab **Detalhes do modelo de trabalho**, selecione **Novo** para adicionar uma linha e defina os seguintes valores:

    - **Tipo de trabalho:** *Separar*
    - **ID da classe de trabalho:** *CLASSIFICAR*

1. Selecione **Novo** novamente para adicionar uma segunda linha e defina os seguintes valores para ela:

    - **Tipo de trabalho:** *Colocar*
    - **ID da classe de trabalho:** *CLASSIFICAR*

1. Selecione **Salvar**.

## <a name="scenario"></a>Cenário

Este cenário simula uma situação em que os contêineres embalados devem ser classificados automaticamente em diferentes posições (paletes) após a estação de embalagem, dependendo do serviço de transportadora. Depois que todos os itens da carga forem embalados e classificados por endereço, os paletes serão movidos para a porta da baía.

### <a name="create-sales-orders-and-picking-work"></a>Criar ordens de venda e trabalho de separação

#### <a name="create-sales-order-1"></a>Criar ordem de venda 1

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Conta de cliente:** *US-005*
    - **Depósito:** *62*

1. Selecione **OK** para fechar a caixa de diálogo.

    A nova ordem de venda é aberta.

1. Alterne para a exibição do **Cabeçalho**.
1. Na guia **Remessa**, na seção **Transporte**, defina os seguintes valores:

    - **Transportadora:** *Carga aérea*
    - **Serviço da transportadora:** *Aéreo*

1. Alterne para a exibição **Linhas**.
1. Se uma nova linha vazia não for adicionada automaticamente à grade na FastTab **Linhas de ordem de venda**, selecione **Adicionar linha**.
1. Na nova linha de ordem, defina os seguintes valores:

    - **Número de item:** *A0001*
    - **Quantidade:** *2*

1. Com a nova linha de ordem ainda selecionada na FastTab **Linhas de ordem de venda**, no menu **Estoque** acima da grade, selecione **Reserva**.
1. Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.
1. Feche a página **Reserva** para retornar à ordem de venda.
1. No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.
1. Você recebe uma mensagem informativa que mostra a remessa e a onda dessa ordem. Anote os números da ID da onda e da ID da remessa.

#### <a name="sales-order-2"></a>Ordem de venda 2

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Conta de cliente:** *US-006*
    - **Depósito:** *62*

1. Selecione **OK** para fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Ele deve incluir uma nova linha vazia na grade da FastTab **Linhas de ordem de venda**. Defina os seguintes valores na linha de ordem:

    - **Item:** *A0001*
    - **Quantidade:** *1*

1. Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Modo de entrega** como *Flowe-STD*.
1. Na FastTab **Linhas de ordem de venda**, selecione **Adicionar linha** e defina os seguintes valores na segunda linha da ordem:

    - **Item:** *A0002*
    - **Quantidade:** *1*

1. Na FastTab **Detalhes da linha**, na guia **Entrega**, mude o valor do campo **Modo de entrega** para *Air C - Via Aérea*.
1. Na FastTab **Linhas de ordem de venda**, selecione a primeira linha da ordem. Depois, no menu **Estoque** acima da grade, selecione **Reserva**.
1. Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.
1. Feche a página **Reserva** para retornar à ordem de venda.
1. Na FastTab **Linhas de ordem de venda**, selecione a segunda linha da ordem. Depois, no menu **Estoque** acima da grade, selecione **Reserva**.
1. Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.
1. Feche a página **Reserva** para retornar à ordem de venda.
1. No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.
1. Você recebe uma mensagem informativa que mostra a remessa e a onda dessa ordem. Observe que são criados dois números de ID de onda e dois números de ID de remessa, um para cada modo de entrega das linhas da ordem de venda.

#### <a name="get-the-work-ids-from-the-work-details"></a>Obter as IDs de trabalho nos detalhes do trabalho

1. Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.
1. A página mostra as IDs de trabalho que foram criadas com base nas ordens de venda. Use as IDs de onda e as IDs de remessa das ordens de venda que você criou para encontrar a ID de trabalho de cada onda e remessa. Anote essas IDs de trabalho, pois elas serão necessárias nas próximas etapas. Observe que duas IDs de trabalho foram criadas para a segunda ordem de venda. Se forem separados itens diferentes de locais diferentes, serão geradas IDs de trabalho separadas.

### <a name="pick-items-for-the-sales-orders"></a>Separar itens para as ordens de venda

Conclua o trabalho criado usando o dispositivo móvel para mover os itens à estação de embalagem.

1. No dispositivo móvel, entre no depósito *62* usando a ID de usuário criada para este cenário (ou a ID de usuário de um usuário de dados de demonstração existente).
1. No menu principal, selecione **Saída**.
1. No menu **Saída**, selecione **Separação de Venda**.
1. No campo **ID**, insira a ID de trabalho criada para a ordem de venda 1.
1. Selecione **OK**.
1. Na página **Ordens de venda - Separar**, insira uma LP de destino criada para a ordem de venda 1. Observe que são exibidos o local de separação (*bulk-001*), o item (*A0001*) e a quantidade (*2 pacotes*).
1. Selecione **OK**.
1. Examine as informações na página **Ordens de venda - Colocar**. O campo **Loc** deve indicar que os itens separados vão para o local de *Embalagem*.
1. Selecione **OK**.

    Na página **Digitalizar uma ID de trabalho/ID de placa de licença**, você receberá a mensagem "Trabalho Concluído", que indica que a ID de trabalho da ordem de venda 1 foi preenchida.

    Agora, você vai separar a ordem de venda 2.

1. No campo **ID**, insira a ID de trabalho criada para a ordem de venda 2, onde a linha 1 tem o item *A0001*.
1. Selecione **OK**.
1. Na página **Ordens de venda - Separar**, insira uma LP de destino. Observe que são exibidos o local de separação (*bulk-001*), o item (*A0001*) e a quantidade (*1 pacotes*).
1. Selecione **OK**.
1. Examine as informações na página **Ordens de venda - Colocar**. O campo **Loc** deve indicar que os itens separados vão para o local de *Embalagem*.
1. Selecione **OK**.

    Na página **Digitalizar uma ID de trabalho/ID de placa de licença**, você receberá a mensagem "Trabalho Concluído". Esta mensagem indica que a ID de trabalho da linha 1 da ordem de venda 2 foi preenchida.

1. No campo **ID**, insira a ID de trabalho criada para a ordem de venda 2, onde a linha 2 tem o item *A0002*.
1. Selecione **OK**.
1. Na página **Ordens de venda - Separar**, insira uma LP de destino. Observe que são exibidos o local de separação (*bulk-002*), o item (*A0001*) e a quantidade (*1 pacotes*).
1. Selecione **OK**.
1. Examine as informações na página **Ordens de venda - Colocar**. O campo **Loc** deve indicar que os itens separados vão para o local de *Embalagem*.
1. Selecione **OK**.

    Na página **Digitalizar uma ID de trabalho/ID de placa de licença**, você receberá a mensagem "Trabalho Concluído". Esta mensagem indica que a ID de trabalho da linha 2 da ordem de venda 2 foi preenchida.

### <a name="pack-sales-orders-into-containers"></a>Embalar ordens de venda em contêineres

#### <a name="pack-sales-order-1-into-containers"></a>Embalar a ordem de venda 1 em contêineres

1. Vá para **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Embalar**.

    É exibida a caixa de diálogo **Selecionar estação de embalagem**. Por padrão, o campo **Trabalhador** deve ser definido com o nome do trabalhador configurado anteriormente.

1. Defina os valores a seguir para exibir e trabalhar em remessas e contêineres planejados no local de embalagem específico:

    - **Local:** *6*
    - **Depósito:** *62*
    - **Local:** *Embalar*
    - **ID do perfil de embalagem:** *Classificar*

1. Selecione **OK** para fechar a caixa de diálogo.
1. Na página **Embalar**, no campo **Placa de licença ou remessa**, insira a LP de destino da ordem de venda 1. Depois, selecione a tecla **Tab** ou **Enter** no teclado para sair do campo.
1. No Painel de Ação, selecione **Novo contêiner**.
1. Aceite todas as configurações padrão e selecione **OK**. Anote a ID do contêiner.
1. Na FastTab **Embalagem de item**, defina os seguintes valores:

    - **Quantidade:** *1*
    - **Identificador:** Item *A0001*

1. No Painel de Ação, selecione **Fechar contêiner**.
1. Na caixa de diálogo **Fechar contêiner**, selecione **Obter peso do sistema** para o sistema atualizar o campo **Peso bruto**.
1. Selecione **OK**. O contêiner muda para o local *CLASSIFICAR* e está pronto para classificação.
1. Crie um segundo contêiner para adicionar o segundo item da LP da ordem de venda 1 a um novo contêiner.
1. No Painel de Ação, selecione **Novo contêiner**.
1. Aceite todas as configurações padrão e selecione **OK**. Anote a ID do contêiner.
1. Na FastTab **Embalagem de item**, defina os seguintes valores:

    - **Quantidade:** *1*
    - **Identificador:** Item *A0001*

1. No Painel de Ação, selecione **Fechar contêiner**.
1. Na caixa de diálogo **Fechar contêiner**, selecione **Obter peso do sistema** para o sistema atualizar o campo **Peso bruto**.
1. Selecione **OK**. O contêiner muda para o local *CLASSIFICAR* e está pronto para classificação.

#### <a name="pack-sales-order-2-into-containers"></a>Embalar a ordem de venda 2 em contêineres

1. Na página **Embalar**, no campo **Placa de licença ou remessa**, insira a LP de destino da linha 1 da ordem de venda 2. Depois, selecione a tecla **Tab** ou **Enter** no teclado para sair do campo.
1. No Painel de Ação, selecione **Novo contêiner**.
1. Aceite todas as configurações padrão e selecione **OK**. Anote a ID do contêiner.
1. Na FastTab **Embalagem de item**, defina os seguintes valores:

    - **Quantidade:** *1*
    - **Identificador:** Item *A0001*

1. No Painel de Ação, selecione **Fechar contêiner**.
1. Na caixa de diálogo **Fechar contêiner**, selecione **Obter peso do sistema** para o sistema atualizar o campo **Peso bruto**.
1. Selecione **OK**. O contêiner muda para o local *CLASSIFICAR* e está pronto para classificação.
1. No campo **Placa de licença ou remessa**, insira a LP de destino da linha 2 da ordem de venda 2. Depois, selecione a tecla **Tab** ou **Enter** no teclado para sair do campo.
1. No Painel de Ação, selecione **Novo contêiner**.
1. Aceite todas as configurações padrão e selecione **OK**. Anote a ID do contêiner.
1. Na FastTab **Embalagem de item**, defina os seguintes valores:

    - **Quantidade:** *1*
    - **Campo identificador:** Item *A0002*

1. No Painel de Ação, selecione **Fechar contêiner**.
1. Na caixa de diálogo **Fechar contêiner**, selecione **Obter peso do sistema** para o sistema atualizar o campo **Peso bruto**.
1. Selecione **OK**. O contêiner muda para o local *CLASSIFICAR* e está pronto para classificação.

Para ver os detalhes do contêiner, vá para **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Contêineres** e procure as IDs de contêiner criadas durante a embalagem.

### <a name="sort-the-containers"></a>Classificar os contêineres

> [!IMPORTANT]
> Ao acessar o item de menu **Criação do palete** no aplicativo móvel para fazer a classificação de saída, você verá um botão **Completo**. *Não use o botão **Completo** para classificar ou fechar a posição.*
>
> O botão **Completo** é fornecido por padrão e não pode ser desabilitado nem removido da página. Ele não é usado para o recurso *Classificação de saída*.

#### <a name="sort-the-first-container"></a>Classificar o primeiro contêiner

1. No dispositivo móvel, entre no depósito *62* usando a ID de usuário criada para este cenário (ou a ID de usuário de um usuário de dados de demonstração existente).
1. No menu principal, selecione **Saída**.
1. No menu **Saída**, selecione **Criação do palete**.
1. No campo **LP/Con**, insira a primeira ID de contêiner associada à ordem de venda 1.
1. Selecione **OK**.
1. Como não existem posições de classificação no momento, você deve especificar uma. No campo **ID da posição de classificação**, insira *SP01*.
1. Como no momento não há nenhuma LP associada à posição de classificação *SP01*, você deve especificar uma. No campo **LP**, insira *PLP01*.
1. Selecione **OK**.
1. Como a validação da posição de classificação está ativada, você deve inserir a ID da posição de classificação novamente. No campo **ID da Posição de Classificação**, insira *SP01*.
1. Selecione **OK**.

    Você receberá uma mensagem "Trabalho concluído".

> [!TIP]
> Para exibir a posição de classificação e a LP nela, vá para **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Atribuições de posição de classificação de saída**.
>
> A página **Atribuições de posição de classificação de saída** mostra todas as posições de classificação que estão ativas. O campo **Classificar transações de posição** mostra a LP associada a cada posição de classificação e os contêineres que estão na posição de classificação. Observe que no momento existe uma posição de classificação e que a FastTab **Classificar critérios de posição** mostra um critério de **Remessa – Serviço da transportadora – Via Aérea**.

#### <a name="sort-the-remaining-containers"></a>Classificar os contêineres restantes

1. No dispositivo móvel, entre no depósito *62* usando a ID de usuário criada para este cenário (ou a ID de usuário de um usuário de dados de demonstração existente).
1. No menu principal, selecione **Saída**.
1. No menu **Saída**, selecione **Criação do palete**.
1. No campo **LP/Con**, insira a segunda ID de contêiner associada à ordem de venda 1.
1. Selecione **OK**. Como o modelo de classificação está configurado para classificar automaticamente e já existe uma posição de classificação com critérios correspondentes, você será direcionado automaticamente para a posição de classificação correta.
1. Selecione **OK**.
1. Confirme a ID da posição da classificação para indicar que o estoque está no local correto. No campo **ID da Posição de Classificação**, insira *SP01*.
1. Selecione **OK**.

    O trabalho foi concluído no segundo contêiner da ordem de venda 1. Agora, você classificará os contêineres restantes da ordem de venda 2.

1. No campo **LP/Con**, insira a ID de contêiner do contêiner da ordem de venda 2 que contém o item *A0001*. Como o serviço da transportadora é diferente, você deverá inserir uma nova posição de classificação e atribuir uma LP a ela. Use a posição de classificação *SP02* e a LP *PLP02*.
1. Selecione **OK**.
1. Confirme a posição de classificação inserindo *SP02* no campo **ID da Posição de Classificação**.
1. Selecione **OK**.

    O trabalho foi concluído no contêiner.

1. No campo **LP/Con**, insira a ID de contêiner do contêiner restante da ordem de venda 2 que contém o item *A0002*. Como o serviço de transportadora é o mesmo que o da ordem de venda 1, o sistema mostra a posição de classificação existente que tem os critérios correspondentes.
1. Selecione **OK**.
1. Confirme a posição de classificação inserindo *SP01* no campo **ID da Posição de Classificação**.
1. Selecione **OK**.

    O trabalho foi concluído no contêiner.

### <a name="close-the-outbound-sorting-positions"></a>Fechar as posições de classificação de saída

Quando todo o estoque for classificado, a posição deverá ser fechada para que o trabalho possa ser criado. O trabalho de separação do estoque classificado será criado para levar o estoque para a porta da baía.

#### <a name="close-a-position-from-the-mobile-device"></a>Fechar uma posição no dispositivo móvel

1. No dispositivo móvel, entre no depósito *62* usando a ID de usuário criada para este cenário (ou a ID de usuário de um usuário de dados de demonstração existente).
1. No menu principal, selecione **Saída**.
1. No menu **Saída**, selecione **Criação do palete**.
1. No campo **LP/Con**, insira uma ID de contêiner classificada para a posição de classificação *SP01*.
1. Selecione **OK**.
1. Você receberá a seguinte mensagem: "O contêiner já está classificado para a posição SP01. Fechar esta posição?" Selecione **Fechar**.

    O trabalho foi concluído.

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a>Fechar uma posição nas atribuições de posição de classificação de saída

1. Vá para **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Atribuições de posição de classificação de saída**.
1. Na coluna esquerda, selecione **SP02**. Essa linha da posição de classificação de saída é a que você fechará.
1. No Painel de Ação, selecione **Fechar posição**. O registro da posição de classificação é fechado e não é mais exibido.

    > [!TIP]
    > Para mostrar todos os registros de posição fechados, marque a caixa de seleção **Mostrar fechado**.

### <a name="sorted-inventory-picking"></a>Separação de estoque classificado

Você deve concluir o trabalho de separação do estoque classificado. Quando ele for concluído, o estoque será separado para a ordem de venda. Nesse ponto, todos os demais processos de depósito se aplicam.

1. No dispositivo móvel, entre no depósito *62* usando a ID de usuário criada para este cenário (ou a ID de usuário de um usuário de dados de demonstração existente).
1. No menu principal, selecione **Saída**.
1. No menu **Saída**, selecione **Carregar da Classificação**.
1. Insira a ID da LP de destino da primeira posição de classificação, *SP01*. Defina o campo **ID** como *PLP01*.
1. Selecione **OK**.
1. A página **Separação do estoque classificado: Separar** mostra o trabalho de separação que deve ser feito. Separe do local *CLASSIFICAR* e da LP de destino *PLP01*, que tem vários itens e uma quantidade de *3*.
1. Selecione **OK**.
1. A página **Separação do estoque classificado: Colocar** mostra o trabalho de colocação que deve ser feito. Coloque no local *Baydoor* e na LP de destino *PLP01*, que tem vários itens e uma quantidade de *3*.
1. Selecione **OK**.

    O trabalho foi concluído.

1. Insira a ID da placa de licença de destino da segunda posição de classificação, *SP02*. Defina o campo **ID** como *PLP02*.
1. Selecione **OK**.
1. A página **Separação do estoque classificado: Separar** mostra o trabalho de separação que deve ser feito. Separe do local *CLASSIFICAR* e da LP de destino *PLP02*, que tem vários itens e uma quantidade de *1*.
1. Selecione **OK**.
1. A página **Separação do estoque classificado: Colocar** mostra o trabalho de colocação que deve ser feito. Coloque no local *Baydoor* e na LP de destino *PLP02*, que tem vários itens e uma quantidade de *1*.
1. Selecione **OK**.

    O trabalho foi concluído.

Desse ponto para a frente, todos os demais processos de depósito se aplicam.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]