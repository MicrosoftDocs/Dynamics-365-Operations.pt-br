---
title: Colocar no mural - colocar na loja
description: Este artigo fornece informações sobre a funcionalidade Colocar no mural - colocar na loja. Essa funcionalidade permite trabalhar com cenários onde você deve consolidar um produto em uma área de preparo do pacote com base em critérios configuráveis. Ela ajuda a diminuir o tempo de separação porque permite separar em uma única placa de licença de destino e pode usar mais posições de colocação do que a separação de cluster.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: af6dcb6d822ab14b0b4b881ca32626ea6eae4c28
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334496"
---
# <a name="put-to-wall---put-to-store"></a>Colocar no mural - colocar na loja

[!include [banner](../includes/banner.md)]

A funcionalidade *Colocar no mural - colocar na loja* permite trabalhar com cenários onde você deve consolidar um produto em uma área de preparo do pacote com base em critérios configuráveis. Como essa funcionalidade permite separar em uma única placa de licença de destino e pode usar mais posições de colocação do que a separação de cluster, as empresas que enviam para lojas ou processam itens pequenos se beneficiarão com a redução do tempo de separação.

O fluxo de trabalho dessa funcionalidade direciona o produto separado para uma localização de classificação para distribuição em vários tipos de contêineres. Geralmente, cada localização de classificação inclui várias posições de classificação. Cada posição de classificação é atribuída de acordo com os critérios definidos pelo processo empresarial. Os critérios típicos são destino final, remessa ou carga. Depois que um produto chega, ele é distribuído para cada posição de classificação com base na quantidade associada à ordem, ao destino, à remessa ou à carga. Quando um contêiner está cheio ou completo, ele passa para um local de preparo ou um local de remessa para processamento extra, dependendo do processo empresarial.

Essa funcionalidade de depósito também é conhecida por outros nomes, como put-to-light e break opens.

## <a name="turn-on-the-outbound-sorting-feature"></a>Ativar o recurso Classificação de saída

Para que você possa usar a funcionalidade *Colocar no mural - colocar na loja*, o recurso *Classificação de saída* deve estar ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *classificação de saída*

O recurso *Classificação de saída* pode ser usado junto com o recurso *Código da etapa da onda em toda a organização* se estiver ativado. Você também deve ativar esse recurso se for usar códigos predefinidos configurados nos códigos da etapa da onda. No espaço de trabalho **Gerenciamento de recursos**, este recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Código da etapa da onda em toda a organização*

## <a name="setup"></a>Instalação

Para esta demonstração, são usados os dados da Contoso e o depósito *62* como padrão. Alguns acréscimos observados posteriormente também são usados.

### <a name="location-type"></a>Tipo de localização

1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Tipos de localização**.
1. No Painel de Ação, selecione **Novo** para criar um tipo de localização para classificação.
1. Defina os seguintes valores:

    - **Tipo de localização:** *CLASSIFICAR*
    - **Descrição:** *Classificar*

1. Selecione **Salvar**.

### <a name="warehouse-management-parameters"></a>Parâmetros de gerenciamento de depósito

1. Acesse **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na guia **Geral**, na FastTab **Tipos de localização**, no campo **Tipo de localização de classificação**, insira *CLASSIFICAR*.
1. Selecione **Salvar**.

### <a name="location-profile"></a>Perfil de localização

1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.
1. No Painel de Ação, selecione **Novo** para criar um perfil de localização para a localização de classificação.
1. No cabeçalho, defina os seguintes valores:

    - **ID do perfil de localização:** *Classificar*
    - **Nome:** *Classificar*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Formato de localização:** *EMBALAR*
    - **Tipo de localização:** *CLASSIFICAR*
    - **Usar rastreamento da placa de licença:** *Sim*
    - **Permitir itens mistos:** *Sim*
    - **Permitir status de estoque mistos:** *Sim*

1. Selecione **Salvar**.

### <a name="locations"></a>Localizações

1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**.
1. Desmarque a caixa de seleção **Gerar dígitos de verificação para localização**.
1. No Painel de Ação, selecione **Novo** e, depois, defina os seguintes valores:

    - **Depósito:** *62*
    - **Localização:** *Classificar*
    - **ID do perfil de localização:** *Classificar*

1. Selecione **Salvar**.

### <a name="packing-profiles"></a>Perfis de embalagem

1. Acesse **Gerenciamento de depósito \> Configuração \> Embalagem \> Perfis de embalagem**.
1. No Painel de Ação, selecione **Novo** e, depois, defina os seguintes valores:

    - **ID do perfil de embalagem:** *Classificar*
    - **Descrição:** *Classificar*
    - **Diretiva de embalagem de contêiner:** deixe este campo em branco.
    - **Modo de ID do Contêiner:** *Automático*
    - **Tipo de contêiner:** *PALETE 48X48*
    - **Criar automaticamente contêiner no fechamento do contêiner:** deixe este campo em branco.

1. Selecione **Salvar**.

### <a name="wave-step-codes"></a>Códigos da etapa da onda

Se você ativou o recurso *Código da etapa da onda em toda a organização*, configure o código a seguir.

1. Acesse **Gerenciamento de depósito \> Configuração \> Ondas \> Códigos da etapa da onda**.
1. No Painel de Ação, selecione **Novo** e, depois, defina os seguintes valores:

    - **Código da etapa da onda:** *Classificar*
    - **Descrição da etapa da onda:** *Classificar*
    - **Tipo de etapa de onda:** *Modelo de classificação*

1. Selecione **Salvar**.

### <a name="outbound-sorting-template"></a>Modelo de classificação de saída

O modelo de classificação controla se as posições de classificação são criadas, quais critérios são usados e outros atributos do processo de classificação.

1. Acesse **Gerenciamento de depósito \> Configuração \> Embalagem \> Modelo de classificação de saída**.
1. No Painel de Ação, selecione **Novo** para criar um modelo de classificação.
1. No cabeçalho do novo modelo, defina os seguintes valores:

    - **ID do modelo de classificação de saída:** *Classificação de Onda*
    - **Descrição:** *Classificação de onda*
    - **Tipo de modelo de classificação:** *Demanda da onda*

        Este campo define o processo para o qual o modelo de classificação é usado. Os valores a seguir estão disponíveis:

        - **Demanda da onda** – O modelo de classificação é usado para o processo *Colocar no mural*. Este tipo de modelo é usado para ignorar a estação de embalagem e processar o estoque diretamente da onda. Você só poderá usá-lo se o método do processo de onda **classificação** estiver incluído no modelo da onda.
        - **Contêiner** – O modelo de classificação é usado para o processo *Criação do palete após embalagem*. Este tipo de modelo é usado para processar os contêineres que estão fechados na estação de embalagem e que devem ser classificados em paletes.

    - **Depósito:** *62*
    - **Localização:** *Classificar*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Verificação de classificação:** *Verificação da posição*

        Este campo define a verificação necessária durante a classificação. Os valores a seguir estão disponíveis:

        - Nemhum(a)
        - Verificação da placa de licença
        - Verificação da posição

    - **Criar trabalho no fechamento da posição:** *Sim*

        Se esta opção for definida como *Sim*, quando a posição for fechada, será criado um trabalho para mover o estoque para a localização da remessa final. Se ela for definida como *Não*, o estoque será separado imediatamente para a ordem quando a posição for fechada.

    - **Atribuição da posição:** *Manual*

        Este campo define o tipo de atribuição de posição. Os valores a seguir estão disponíveis:

        - **Manual** – O usuário sempre deve indicar a posição para classificar o estoque.
        - **Automática** – O sistema guiará o estoque automaticamente para uma posição sempre que possível, com base nas divisões do modelo de classificação.

    - **Atribuir critérios de posição de classificação:** *Usar apenas a posição vazia*

        Este campo controla se o estoque já presente nas posições de classificação é considerado quando uma posição é atribuída para a demanda. Os valores a seguir estão disponíveis:

        - **Usar apenas a posição vazia** – As posições que já têm estoque associado serão levadas em consideração
        - **Assumir posição vazia** – Qualquer estoque que já esteja na posição será ignorado durante a atribuição. Todas as posições disponíveis serão usadas.

    - **Código da etapa da onda:** *Classificar*

        Se o recurso *Código da etapa da onda em toda a organização* estiver ativado, o código da etapa da onda *Classificar* também deverá ser configurado em códigos da etapa da onda.

    - **Posição de classificação de fechamento automático:** *Sim*

        Se essa opção for definida como *Sim*, a posição de classificação será fechada automaticamente quando todo o trabalho recebido na posição for concluído.

    - **Número de posições de classificação:** *3*

        Este campo define o número máximo de posições de classificação que o sistema irá criar.

    - **Prefixo da posição de classificação:** *SP-*

        Este campo define o prefixo que o sistema atribui antes do número da posição.

    - **Posição de classificação com embalagem automática:** *Sim*

        Se esta opção for definida como *Sim*, o estoque na posição de classificação será embalado em um contêiner quando a posição for fechada.

    - **ID do perfil de embalagem:** *Classificar*

        O campo define o perfil de embalagem que será usado quando a posição de classificação for embalada em um contêiner.

1. No Painel de Ação, selecione **Editar consulta** para especificar os critérios usados para esse modelo de classificação.
1. Na caixa de diálogo de consulta, na guia **Classificação**, selecione **Novo** para adicionar uma linha e defina os seguintes valores:

    - **Tabela:** *Detalhes da carga*
    - **Tabela derivada:** *Detalhes da carga*
    - **Campo:** *ID da Remessa*
    - **Direção da pesquisa:** *Crescente*

1. Selecione **OK**.
1. Você poderá receber a seguinte mensagem: "O agrupamento será redefinido, continuar?" Selecione **Sim**.

    O botão **Divisões do modelo de classificação de saída** no Painel de Ação ficará disponível.

1. No Painel de Ação, selecione **Divisões do modelo de classificação de saída**.
1. Selecione a caixa de diálogo **Agrupar por campo** para agrupar por ID da remessa.

    Esta configuração criará uma posição de classificação por remessa que é um contêiner na onda.

1. Selecione **OK**.

### <a name="wave-process-methods"></a>Métodos de processo de onda

1. Acesse **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.
1. No Painel de Ação, selecione **Regenerar métodos**.

    O método de **classificação** é adicionado à lista de métodos disponíveis e o tipo de modelo de onda *Remessa* é selecionado para ele.

### <a name="wave-templates"></a>Modelos de onda

Edite o modelo de onda usado para classificação de demanda da onda.

1. Acesse **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.
1. No campo **Tipo de modelo de onda**, selecione *Remessa*.
1. Selecione o modelo **Padrão de remessa 62** existente.
1. No Painel de Ações, selecione **Editar**.
1. Na FastTab **Geral**, faça as seguintes alterações:

    - Defina a opção **Processar onda na liberação para o depósito** como *Não*.
    - Defina a opção **Atribuir às ondas abertas** como *Sim*.

1. Na FastTab **Métodos**, configure o método de **classificação**:

    1. Na grade **Métodos Restantes**, selecione **classificação**.
    2. Selecione o botão de seta para a direita para mover **classificação** para a grade **Métodos Selecionados**.
    3. Na grade **Métodos Selecionados**, selecione **classificação**.
    4. Defina o campo **Código da etapa da onda** como *Classificar*.

1. Selecione **Salvar**.

### <a name="mobile-device-menu-items"></a>Itens de menu do dispositivo móvel

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho, defina os seguintes valores:

    - **Nome do item de menu:** *Classificar*
    - **Título:** *Classificar*
    - **Modo:** *Indireto*
    - **Usar trabalho existente:** *Não*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Código de atividade:** *Classificação de saída*
    - **Usar guia de processo:** *Sim* (valor padrão)
    - **ID do modelo de classificação de saída:** *Classificação de Onda*

1. Selecione **Salvar**.

### <a name="mobile-device-menu"></a>Menu de dispositivos móveis

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. Na lista de menus, selecione **Saída**.
1. No Painel de Ações, selecione **Editar**.
1. Na grade **Menus e Itens de Menu Disponíveis**, localize e selecione o item de menu **Classificar** que você acabou de criar.
1. Selecione o botão de seta para a direita para mover **Classificar** para a grade **Estrutura de Menu**. Dessa forma, você adiciona o item de menu ao menu **Saída**.
1. Selecione **Salvar**.

### <a name="location-directives"></a>Diretivas de localização

Você deve criar diretivas de localização para orientar o trabalho criado depois que a classificação for concluída.

1. Acesse **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No campo **Tipo de ordem de trabalho**, selecione *Separação do estoque classificado*.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho, defina os seguintes valores:

    - **Sequência:** *1*
    - **Nome:** *Colocar em Baydoor*

1. Na FastTab **Diretivas de localização**, defina os seguintes valores:

    - **Tipo de trabalho:** *Colocar*
    - **Local:** *6*
    - **Depósito:** *62*
    - **Código de diretiva:** deixe este campo em branco.
    - **Várias SKUs:** *Não*

1. Selecione **Salvar** para disponibilizar a FastTab **Linhas**.
1. Na FastTab **Linhas**, selecione **Novo** e defina os valores a seguir. Aceite os valores padrão para todos os demais campos.

    - **Número de sequência:** *1*
    - **Quantidade inicial:** *0*
    - **Quantidade final:** *1000000*

1. Selecione **Salvar** para disponibilizar a FastTab **Ações de Diretiva de Localização**.
1. Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** e defina os valores a seguir. Aceite os valores padrão para todos os demais campos.

    - **Número de sequência:** *1*
    - **Nome:** *Porta da baía*

1. Selecione **Salvar** para disponibilizar o botão **Editar consulta** na FastTab **Ações de Diretiva de Localização**.
1. Na FastTab **Ações de Diretiva de Localização**, selecione **Editar consulta**.
1. Na caixa de diálogo de consulta, na guia **Intervalo**, localize a linha na qual o campo **Campo** está definido como *Local*. Defina o campo **Critérios** dessa linha como *Baydoor*.
1. Selecione **OK** para confirmar a edição.

### <a name="work-classes"></a>Classes de trabalho

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.
1. No Painel de Ações, selecione **Novo**.
1. No cabeçalho, defina os seguintes valores:

    - **ID da classe de trabalho:** *Classificação*
    - **Descrição:** *Classificação*
    - **Tipo de ordem de serviço:** *Separação do estoque classificado*

1. Selecione **Salvar**.

### <a name="work-templates"></a>Modelos do trabalho

1. Acesse **Gerenciamento de depósito \> Trabalho \> Modelos de trabalho**.
1. No campo **Tipo de ordem de trabalho**, selecione *Ordens de compra*.
1. Na grade, selecione o modelo de trabalho **62 Separar para embalar**.
1. No Painel de Ação, selecione **Quebras de cabeçalho de trabalho**.
1. No Painel de Ações, selecione **Editar**.
1. Na linha em que o campo **Nome do campo** está definido como *ID da Remessa*, desmarque a caixa de seleção **Agrupar por este campo**.
1. Selecione **Salvar** e feche a caixa de diálogo **Quebras de cabeçalho de trabalho**.
1. No campo **Tipo de ordem de trabalho**, selecione *Separação do estoque classificado*.
1. Selecione **Novo** para criar um modelo de trabalho.
1. Na seção **Visão geral**, defina os valores a seguir. Aceite os valores padrão para todos os demais campos.

    - **Modelo de trabalho:** *Separação classificada*
    - **Descrição do modelo de trabalho:** *Separação classificada*

1. Selecione **Salvar** para disponibilizar a seção **Detalhes do Modelo de Trabalho**.
1. Na seção **Detalhes do Modelo de Trabalho**, você criará duas linhas. Selecione **Novo** e defina os seguintes valores para a linha 1:

    - **Tipo de trabalho:** *Separar*
    - **Obrigatório:** selecionado (= *Sim*)
    - **ID da classe de trabalho:** *Classificação*

1. Selecione **Novo** novamente e defina os seguintes valores para a linha 2:

    - **Tipo de trabalho:** *Colocar*
    - **Obrigatório:** selecionado (= *Sim*)
    - **ID da classe de trabalho:** *Classificação*

1. Selecione **Salvar**.

## <a name="example-scenario"></a>Cenário de exemplo

Este cenário simula uma situação em que o depósito armazena itens pequenos em locais e deve embalá-los em caixas antes de eles serem remetidos e na qual a funcionalidade de estação de embalagem não é adequada. Os trabalhadores separam ordens de vários clientes e diferentes endereços ao mesmo tempo para aumentar a velocidade de separação. Depois de concluída a separação, os trabalhadores chegam à localização de classificação, onde os itens separados podem ser classificados na caixa correta com base em critérios exigidos. Neste exemplo, a ID de remessa será usada para determinar a caixa correta, pois cada remessa tem um endereço diferente. Depois que todos os itens da carga são embalados e classificados por remessa, as caixas serão movidas para a área de preparação e carregadas em um caminhão.

Antes de iniciar o cenário, verifique se toda a funcionalidade de depósito padrão está configurada corretamente para seu depósito. O depósito *62* padrão da Contoso é usado para essa finalidade. As configurações padrão não foram alteradas, além do que está descrito na configuração.

### <a name="create-demand"></a>Criar demanda

Para que a funcionalidade possa ser demonstrada, você deve criar alguma demanda. Para este cenário, você criará três ordens de venda para três clientes diferentes a fim de simular endereços de entrega diferentes. Dessa forma, você criará três remessas separadas.

Antes de criar as ordens de venda e remessas, certifique-se de que os locais de separação têm estoque suficiente para todos os itens nas ordens. Examine as configuração de diretiva de localização para confirmar os locais de separação que são usados para separação de ordens de venda. Se precisar ajustar o estoque, você poderá criar movimentações manuais, usar o reabastecimento ou utilizar qualquer outro fluxo. Em seguida, reserve o estoque.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar uma ordem de venda para a ordem 1.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Cliente:** *US-001*
    - **Depósito:** *62*

1. Selecione **OK**.
1. Uma nova linha é adicionada à FastTab **Linhas da ordem de venda**. Defina os seguintes valores:

    - **Número de item:** *A0001*
    - **Quantidade:** *5*

1. Selecione **Adicionar linha** para adicionar uma segunda linha e defina os seguintes valores:

    - **Número de item:** *A0002*
    - **Quantidade:** *10*

1. Repita as seguintes etapas para cada linha de venda na ordem a fim de reservar estoque para ela:

    1. Na FastTab **Linhas da ordem de venda**, no menu **Estoque**, selecione **Reserva**.
    1. Na página **Reserva**, selecione **Reservar lote** e feche a página.
    1. Selecione **Salvar**.

1. Selecione **Novo** para criar uma ordem de venda para a ordem 2.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Cliente:** *US-004*
    - **Depósito:** *62*

1. Selecione **OK**.
1. Uma nova linha é adicionada à FastTab **Linhas da ordem de venda**. Defina os seguintes valores:

    - **Número de item:** *A0001*
    - **Quantidade:** *7*

1. Selecione **Adicionar linha** para adicionar uma segunda linha e defina os seguintes valores:

    - **Número de item:** *A0002*
    - **Quantidade:** *3*

1. Repita as seguintes etapas para cada linha de venda na ordem a fim de reservar estoque para ela:

    1. Na FastTab **Linhas da ordem de venda**, no menu **Estoque**, selecione **Reserva**.
    1. Na página **Reserva**, selecione **Reservar lote** e feche a página.
    1. Selecione **Salvar**.

1. Selecione **Novo** para criar uma ordem de venda para a ordem 3.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Cliente:** *US-007*
    - **Depósito:** *62*

1. Selecione **OK**.
1. Uma nova linha é adicionada à FastTab **Linhas da ordem de venda**. Defina os seguintes valores:

    - **Número de item:** *A0001*
    - **Quantidade:** *8*

1. Siga estas etapas para reservar o estoque para a linha de venda:

    1. Na FastTab **Linhas da ordem de venda**, no menu **Estoque**, selecione **Reserva**.
    1. Na página **Reserva**, selecione **Reservar lote** e feche a página.
    1. Selecione **Salvar**.

Execute o procedimento a seguir para liberar cada ordem de venda para o depósito. Serão criadas três remessas diferentes. Em seguida, você adicionará todas as três remessas a uma nova onda.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Na grade, selecione a primeira ordem de venda que você criou.
1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.

    Você recebe uma mensagem informativa que mostra a ID da onda e a ID da remessa que foram criadas.

1. Repita as etapas anteriores para liberar as ordens de venda 2 e 3 para o depósito. Observe que a mensagem informativa recebida indica que uma remessa foi adicionada ao onda que foi criada quando você liberou a ordem de venda 1.
1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Selecione a ID da onda que foi criada na liberação das ordens de venda para abrir a página **Ondas**. Essa página mostra os detalhes da onda. A FastTab **Linhas da onda** mostra as remessas criadas.

    Agora, você deve criar um trabalho para trazer itens dos locais de separação para a localização de classificação.

1. No Painel de Ação, selecione **Processo**.

    Durante o processamento da onda, o método de classificação usará o modelo de classificação para atribuir o estoque a posições de classificação. Quando o processamento da onda for concluído, você receberá uma mensagem informativa indicando que a onda foi lançada e o trabalho foi criado.

1. No Painel de Ação, na guia **Onda**, no grupo **Informações relacionadas**, selecione **Trabalho** para ver o trabalho que foi criado. Anote a ID do trabalho.
1. Acesse **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Atribuições de posição de classificação de saída**.
1. Na coluna esquerda, você pode ver a posição de classificação de saída criada para cada remessa.
1. Na FastTab **Classificar critérios de posição**, você pode ver a ID da remessa dessa posição.

Uma ID de trabalho foi criada para trazer estoque dos locais de separação para a localização de classificação. Para concluir o trabalho, você precisará da ID de trabalho criada durante o processamento da onda.

### <a name="sales-order-picking-to-the-sorting-location"></a>Separação da ordem de venda para a localização de classificação

1. Entre no aplicativo móvel como um trabalhador do depósito *62*.
1. No menu principal, selecione **Saída**.
1. No menu **Saída**, selecione **Separação de Venda**.
1. Selecione o campo **ID** e insira a ID de trabalho do processamento da onda.
1. Confirme a entrada.

    Em seguida, você deverá inserir uma placa de licença de destino (LP). Observe que a linha 1 da ordem de venda 1 é o que deve ser separado e adicionado à placa de licença de destino. O número do item, a quantidade, a descrição do item e o local de separação são mostrados.

1. No campo **LP de destino**, insira um número de placa de licença.

    Você separará todas as linhas criadas da onda processada para a mesma placa de licença de destino.

1. Confirme a entrada.

    Agora, o aplicativo móvel apresenta uma série de páginas **Separar** que levam à localização de separação e também ao item e à quantidade que devem ser separados. Depois que o item separado for adicionado à placa de licença, você confirmará o trabalho de separação. A última página será o trabalho de colocar os itens separados na localização de classificação.

1. Confirme o primeiro trabalho de separação.
1. O próximo trabalho de separação é mostrado. Confirme a separação.
1. Continue confirmando o trabalho de separação restante.
1. A última etapa é concluir o trabalho de colocação. Confirme o armazenamento para a localização de classificação.

    Você receberá uma mensagem "Trabalho concluído".

1. Saia de **Separação de Venda** no aplicativo móvel.

### <a name="sortingput-to-wall"></a>Classificação/colocar no mural

Agora que todo o estoque foi colocado na localização de classificação, ele deve ser classificado para a posição de classificação correta.

1. Entre no aplicativo móvel.
1. No menu principal, selecione **Saída**.
1. No menu **Saída**, selecione **Classificar** para começar a classificar os itens.
1. No campo **LP/CON**, insira a placa de licença de destino do trabalho da ordem de venda separada.
1. Confirme a entrada.
1. Insira o número do item a ser classificado primeiro.
1. O sistema determina a primeira posição de classificação que deve ser mostrada. Confirme a posição de classificação.
1. Você deverá atribuir uma placa de licença à posição de classificação. Selecione o campo **LP**, insira um número de placa de licença e confirme a entrada.

    Como a posição de classificação está relacionada à ID da remessa, você classificará os itens separados em uma chapa de licença que seja específica da remessa e da ordem de venda de saída.

    A próxima página mostra a ID do item, a quantidade, a ID da posição de classificação e as IDs da placa de licença "de" (separação) e "para" (classificação). As informações nessa página o orientam a classificar o item e as quantidades especificados da placa de licença de separação na placa de licença de classificação.

1. Confirme a posição de classificação.
1. Classifique os itens na primeira posição de classificação. Quando você terminar, o sistema o levará à próxima posição de classificação.
1. Repita o processo para todas as linhas separadas da ordem de trabalho. Você também deve usar esse processo quando houver várias linhas de separação com o mesmo número de itens.

    À medida que você repetir esse processo para todos os itens, o sistema avaliará os critérios do próximo item verificado (linha de trabalho) e determinará em qual posição de classificação ele deve ser colocado. Você é direcionado automaticamente para colocar o item na posição de classificação correta. Dependendo da configuração de confirmação, você também deverá confirmar essa ação inserindo o número da posição ou a ID da placa de licença.

    > [!NOTE]
    > Se a classificação automática estiver ativada, a substituição manual não estará disponível.

1. Quando terminar, no Microsoft Dynamics 365 Supply Chain Management, abra a página **Atribuições de posição de classificação de saída** para analisar o status das posições.

    - Se as posições forem fechadas automaticamente, selecione **Mostrar fechado** para mostrar as posições fechadas.
    - As transações de posição de classificação são mostradas. O item e a quantidade processados por meio da posição são exibidos.

    Ao configurar o modelo de classificação de saída, você define a opção **Posição de classificação de fechamento automático** como *Sim*. Portanto, a posição é fechada automaticamente depois que o último estoque previsto é colocado nela. As posições de classificação têm o status **Fechado**, e foi criado um trabalho para mover o estoque classificado para o local *Baydoor*.

1. Conclua o trabalho de separação do estoque classificado para mover o estoque para o local da remessa. Quando o estoque estiver pronto, confirme-o para a remessa.

> [!NOTE]
> Para que o trabalho de separação de estoque classificado seja processado corretamente, um item de menu do dispositivo móvel que tem uma ID de classe de trabalho na qual o campo **Tipo de ordem de trabalho** está definido como *Separação do estoque classificado* deve ser usado para o processo de movimentação e carga.

### <a name="manually-close-a-position-optional"></a>Fechar uma posição manualmente (opcional)

Se as posições de classificação tiverem que ser fechadas manualmente, a opção **Posição de classificação de fechamento automático** do modelo de classificação de saída deverá ser definida como *Não* e o fechamento deverá ser feito antes que o estoque possa ser movido para a área da porta da baía. As posições podem ser fechadas de várias maneiras:

- Por meio do aplicativo móvel de Gerenciamento de depósito:

    - O usuário pode examinar um dos itens que já estão na posição e selecionar **Fechar** para fechar a posição.
    - Se o usuário examinar um contêiner que já foi classificado, será exibida uma mensagem de erro. No entanto, o usuário ainda poderá continuar para fechar a posição.

- Na página **Atribuições de posição de classificação de saída** do Microsoft Dynamics 365 Supply Chain Management:

    - O usuário pode selecionar o registro da posição de classificação de saída e selecionar **Fechar posição** no Painel de Ação.

## <a name="tips"></a>Dicas

- Os itens não podem ser movidos entre posições depois de terem sido atribuídos a uma. O sistema avalia a quantidade de cada item que deve ir para uma posição específica.
- O modelo de classificação pode ser configurados para criar contêineres automaticamente quando posições forem fechadas. Essa abordagem criará a estrutura de ID de contêiner padrão com base no perfil de embalagem especificado.

> [!IMPORTANT]
> Depois que o trabalho de movimentação tiver sido criado com base na localização de classificação, você não deverá cancelá-lo. Caso contrário, a posição e os contêineres nela serão excluídos do sistema e ficarão indisponíveis para processamento adicional. O estoque também será removido.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]