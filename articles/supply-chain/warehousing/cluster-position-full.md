---
title: Posição de cluster completa
description: Este tópico fornece informações sobre o recurso Posição de cluster completa. Este recurso oferece uma alternativa a uma aplicação mais rígida de regras de intervalo de trabalho quando a separação de cluster é usada, pois permite uma maior margem de erro nas restrições volumétricas de contêineres ou totes.
author: Mirzaab
manager: tfehr
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3610725815b35609ee98b69b367db2945bbf166a
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422543"
---
# <a name="cluster-position-full"></a>Posição de cluster completa

[!include [banner](../includes/banner.md)]

O recurso *Posição de cluster completa* oferece uma alternativa a uma aplicação mais rígida de regras de intervalo de trabalho quando a separação de cluster é usada, pois permite uma maior margem de erro nas restrições volumétricas de contêineres ou totes. Em um cenário comum, nem todos os itens de uma ordem de serviço cabem em um contêiner selecionado. Os trabalhadores de depósito que são a separação de cluster têm algumas opções neste cenário: eles devem alterar para um tamanho de contêiner maior ou trabalhar com seu supervisor para apresentar uma solução diferente.

Este recurso introduz a capacidade de executar o botão **Completo** em uma das unidades de trabalho em um cluster. Em versões anteriores, essa opção estava disponível apenas para a separação de ordem normal, não para a separação de cluster. No entanto, este recurso difere do botão **Completo** padrão, pois cancela o trabalho restante. Ele não sugere que o usuário adicione outro compartimento ao mesmo cluster e não cria um novo trabalho automaticamente.

## <a name="turn-on-the-cluster-position-full-feature"></a>Ativar o recurso Posição de cluster completa

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Posição de cluster completa*

## <a name="setup"></a>Configurar

Esta seção fornece diretrizes e um exemplo que mostra como configurar e usar o recurso *Posição de cluster completa*.

### <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para trabalhar com o [cenário de exemplo](#example-scenario) usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

Você também pode usar o cenário de exemplo como orientação para trabalhar com esse recurso em um sistema de produção. No entanto, nesse caso, você deve substituir seus valores pelas configurações descritas aqui.

### <a name="cluster-profiles"></a>Perfis de cluster

Você deve especificar se as IDs de cluster são geradas automaticamente, quantas posições são usadas, quando os clusters são divididos e como o trabalho de separação é sequenciado e verificado.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Perfis de cluster**.
1. No painel de lista, selecione o registro **Criar Cluster**.
1. Na FastTab **Geral**, verifique os valores a seguir:

    - **Gerar ID do cluster:** *Sim*
    - **Ativar posições:** *Sim*
    - **Número de posições:** *2*
    - **Nome da posição:** *Numérica*
    - **Dividir cluster em:** *Colocar*
    - **Tipo de verificação de classificação:** *Verificação da posição*

1. Na FastTab **Classificação de cluster**. A grade deve estar em branco (isto é, ela não deve conter linhas).

### <a name="work-templates"></a>Modelos do trabalho

Você deve definir como o trabalho de separação para a separação de cluster é criado.

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. Na parte superior da página, defina o campo **Tipo de ordem de serviço** como *Ordens de venda*.
1. Verifique se os seguintes modelos de trabalho dos dados de demonstração estão listados. Se eles não estiverem disponíveis, não será possível concluir o cenário.

    - Preparação de OV 61
    - Separação de cluster de OV 61

### <a name="location-directives"></a>Diretivas de localização

Você deve especificar de onde os itens são separados e onde eles são colocados.

1. Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No cabeçalho da lista, defina o campo **Tipo de ordem de serviço** como *Ordens de venda*.
1. Verifique se as seguintes diretivas de ordens de venda dos dados de demonstração estão listadas. Se eles não estiverem disponíveis, não será possível concluir o cenário.

    - Separação de cluster de 61
    - Ordem de separação de OV 61

### <a name="mobile-device-menu-items"></a>Itens de menu do dispositivo móvel

Você deve configurar um item de menu do dispositivo móvel para usar o trabalho existente que é direcionado pela separação de cluster. No item de menu do dispositivo móvel para separação de cluster, o parâmetro **Permitir divisão de trabalho** deve ser ativado e a classe de trabalho *Separação de OV* deve ser adicionada.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No painel de lista, selecione o registro **Criar Separação de Cluster**.
1. Selecione **Editar** no Painel de Ações.
1. Na FastTab **Geral**, defina os seguintes valores:

    - **Direcionado por:** *Separação de cluster*
    - **Gerar placa de licença:** *Sim*
    - **Permitir divisão de trabalho:** *Sim*
    - **ID do perfil do cluster:** *Criar Cluster*

    Aceite os valores padrão para todos os demais campos.

1. Na FastTab **Classes de trabalho**, adicione as duas linhas a seguir, conforme necessário:

    - Linha 1 (normalmente presente em dados de demonstração):

        - **ID da classe de trabalho:** *Vendas* 
        - **Tipo de ordem de serviço:** *Ordens de venda*

    - Linha 2 (provavelmente ausente em dados de demonstração):

        - **ID da classe de trabalho:** *Separação de OV*
        - **Tipo de ordem de serviço:** *Ordens de venda*

1. Vá para **Configuração de confirmação de trabalho** no Painel de Ações.
1. Selecione **Editar**.
1. Insira os seguintes valores na linha da grade.
    - **Tipo de trabalho** - *Separar*
    - **Confirmação do produto** - *Marque a caixa de seleção*

1. Selecione **Salvar** no Painel de Ações e feche a página.

## <a name="create-picking-work"></a>Criar trabalho de separação

Antes de iniciar a separação de cluster, você deve criar um trabalho de saída. O perfil de cluster criado anteriormente especifica duas posições de cluster. Portanto, pelo menos duas IDs de trabalho devem ser criadas para a separação de ordens de venda. Neste cenário, as transações ocorrerão no depósito *61* e usarão os itens *L0101* e *T0100*. Os dados de demonstração devem ter um estoque disponível suficiente desses itens. Verifique se você tem estoque suficiente para concluir as transações.

### <a name="create-sales-order-1"></a>Criar ordem de venda 1

1. Vá para **Vendas e Marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar a ordem de venda 1.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Conta de cliente:** *US-010*
    - **Depósito:** *61*

1. Selecione **OK**.
1. A nova ordem de venda é aberta. Na guia rápida **Linhas da ordem de venda**, adicione uma linha que tenha as seguintes configurações:

    - **Número de item:** *T0100*
    - **Quantidade:** *5*

1. Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Data de remessa confirmada** como a data de hoje.
1. Na FastTab **Linhas da ordem de venda**, adicione uma segunda linha que tenha as seguintes configurações:

    - **Número de item:** *L0101*
    - **Quantidade:** *20*

1. Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Data de remessa confirmada** como a data de hoje.
1. Para cada linha que você acabou de adicionar, siga estas etapas para reservar o estoque:

    1. Selecione a linha a ser reservada.
    2. Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.
    3. Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.
    4. Feche a página **Reserva**.

1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.

    Quando a liberação é concluída, você recebe mensagens informativas que mostram as IDs do ciclo e da carga que foram criadas.

### <a name="create-sales-order-2"></a>Criar ordem de venda 2

1. Vá para **Vendas e Marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar a ordem de venda 2.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Conta de cliente:** *US-011*
    - **Depósito:** *61*

1. Selecione **OK**.
1. A nova ordem de venda é aberta. Na guia rápida **Linhas da ordem de venda**, adicione uma linha que tenha as seguintes configurações:

    - **Número de item:** *L0101*
    - **Quantidade:** *20*

1. Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Data de remessa confirmada** como a data de hoje.
1. Na FastTab **Linhas da ordem de venda**, adicione uma segunda linha que tenha as seguintes configurações:

    - **Número de item:** *T0100*
    - **Quantidade:** *2*

1. Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Data de remessa confirmada** como a data de hoje.
1. Para cada linha que você acabou de adicionar, siga estas etapas para reservar o estoque:

    1. Selecione a linha a ser reservada.
    2. Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.
    3. Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.
    4. Feche a página **Reserva**.

1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.

    Quando a liberação é concluída, você recebe mensagens informativas que mostram as IDs do ciclo e da carga que foram criadas.

### <a name="get-work-ids-and-license-plate-numbers"></a>Obter IDs de trabalho e números das placas de licença

Duas IDs de trabalho devem ter sido criadas, cada uma com duas linhas de separação. Siga estas etapas para localizar as IDs de trabalho e as atribuições das placas de licença.

1. Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.
1. Na grade **Visão geral**, procure na coluna **Número da ordem** as duas ordens de venda recém-criadas. Para cada ordem de venda, anote a ID de trabalho correspondente.
1. Selecione a linha de cada ordem de venda para mostrar as informações relacionadas na grade **Linhas**. Anote o local de onde cada item será separado.
1. Vá para **Gerenciamento de estoque \> Consultas e relatórios \> Lista disponível**.
1. No Painel de Ações, selecione **Dimensões** para abrir a caixa de diálogo **Exibição de dimensão**.
1. Verifique se as caixas de seleção **Placa de licença**, **Depósito** e **Número do item** estão marcadas e, em seguida, selecione **OK**.
1. No painel **Filtro**, defina os seguintes filtros:

    - **Número do item** – **é um de** – *L0101* e *T100*
    - **Depósito** – **começa com** – *61*

1. Anote os valores da **Placa de licença** que são exibidos.

## <a name="example-scenario"></a><a name="example-scenario"></a>Cenário de exemplo

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a>Execução do fluxo do dispositivo móvel – Configuração de confirmação de trabalho para o produto

1. Entre no aplicativo do depósito como um usuário no depósito *61*.
1. Vá para **Saída \> Criar separação de cluster**.

    A página **TAREFA: Atribuir Trabalho ao Cluster** será exibida.

1. Insira a ID de trabalho da ordem de venda 1 para atribuí-la à posição de cluster 1.
1. Selecione **OK** (símbolo de marca de seleção).
1. Insira a ID de trabalho da ordem de venda 2 para atribuí-la à posição de cluster 2.
1. Selecione **OK** (símbolo de marca de seleção).

    A página **TAREFA: Criar Separação de Cluster: Separar** será exibida e mostrará *Item L0101 2 PL*.

Como o perfil do cluster definiu o número de posições como 2, o sistema automaticamente direciona você para a primeira separação consolidada: dois paletes (PL) do item *L0101*.

A qualquer momento durante as etapas a seguir, você pode selecionar a guia **Detalhes** para exibir informações adicionais sobre a tarefa, como o local de separação.

1. Defina o campo **ITEM** como *L0101*. Isso confirma o número do item, que é necessário para este item de menu (você configurou isso anteriormente selecionando **Configuração de confirmação de trabalho** na página **Item de menu do dispositivo móvel** quando criou esse item de menu).
1. Insira o número da placa de licença associado ao item no local que está sendo separado. Você separará dois paletes.
1. Defina o campo **LP** como *LP\_PICK\_01*.
1. Selecione **OK** (símbolo de marca de seleção).

    A página **TAREFA: Classificar: Criar Separação de Cluster** será exibida. Aqui, você classificará os dois paletes separados em uma posição de separação. Essa posição pode ser um tote ou contêiner usado para separar o estoque separado por ordem de venda.

1. Veja os detalhes mostrados para o item (*L0101*) e a quantidade (*20* ea) que serão classificados na posição 1 (para a ordem de venda 1).
1. Defina o campo **POSITION NA** como *1*.
1. Selecione **OK** (símbolo de marca de seleção).
1. Veja os detalhes mostrados para o item (*L0101*) e a quantidade (*20* ea) que serão classificados na posição 2 (para a ordem de venda 2).
1. Defina o campo **POSITION NA** como *2*.
1. Selecione **OK** (símbolo de marca de seleção).

    A página **TAREFA: Criar Separação de Cluster: Separar** será exibida e mostrará *Item T0100 7 ea*.

Neste cenário, a posição 1 não pode aceitar a quantidade total de itens que devem ser separados para atender à ordem de venda 1. Uma posição deve ser marcada como completa. Neste cenário, você fará uma separação parcial do segundo item. O segundo item será parcialmente separado para a posição 1 e um novo trabalho será criado para separar a quantidade restante a fim de atender à ordem.

1. Selecione o botão de menu (também chamado de hambúrguer ou botão de hambúrguer) e, em seguida, selecione **Posição completa**.
1. Identifique a posição completa e selecione *1*.
1. Selecione **OK** (símbolo de marca de seleção).
1. Insira a quantidade de separação que ainda pode ser separada na posição 1. O sistema pode determinar qual número de item está sendo separado.
1. Insira *2*.
1. Selecione **OK** (símbolo de marca de seleção).
1. Confirme o número do item para concluir a separação do item restante na posição 2.
1. Defina o campo **ITEM** como *T0100*.
1. Selecione **OK** (símbolo de marca de seleção).
1. Insira a placa de licença da qual o item está sendo separado, definindo o campo **LP** como *LPREPL04*.
1. Selecione **OK** (símbolo de marca de seleção).
1. Veja os detalhes mostrados para o item (*T0100*) e a quantidade (*2* ea) que serão classificados na posição 2 (para a ordem de venda 2).
1. Defina o campo **POSITION NA** como *2*.
1. Selecione **OK** (símbolo de marca de seleção).
1. Veja os detalhes mostrados para o item (*T0100*) e a quantidade (*2* ea) que serão classificados na posição 1 (para a ordem de venda 1).
1. Defina o campo **POSITION NA** como *1*.
1. Selecione **OK** (símbolo de marca de seleção).

    A página **TAREFA: Criar Separação de Cluster: Colocar** será exibida.

Neste cenário, a separação de cluster foi concluída e o usuário é direcionado para armazenar os itens separados da posição 1 e da posição 2 no local de preparo *STAGE01*.

1. Revise as informações na página. Ela mostra que uma quantidade total de *44* será colocada no local de preparo.
1. Selecione **OK** (símbolo de marca de seleção).

    Você recebe uma mensagem "Cluster Concluído".

Agora você pode usar o item de menu **Separação de Venda** para separar a quantidade restante. Em seguida, você pode usar o item de menu **Carregamento de venda** para mover os itens do local de preparo para a doca de carga.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]