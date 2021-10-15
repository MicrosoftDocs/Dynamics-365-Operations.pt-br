---
title: Alterar pool de trabalho no trabalho
description: Este tópico explica como você pode usar o botão Alterar pool de trabalho para itens de trabalho a fim de alterar o pool de trabalho do trabalho existente.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 066655b58d4676bafb6e8ed8d80a95636c047444
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566014"
---
# <a name="change-work-pool-on-work"></a>Alterar pool de trabalho no trabalho

[!include [banner](../includes/banner.md)]

É possível usar pools de trabalho para organizar o trabalho em grupos. Por exemplo, é possível criar um pool de trabalho para classificar o trabalho que ocorre em uma localização específica do depósito.

O recurso *Alterar pool de trabalho no trabalho* adiciona um botão **Alterar pool de trabalho** ao Painel de Ação para itens de trabalho. Portanto, os gerentes de depósito podem alterar facilmente o pool de trabalho do trabalho existente. Este recurso permite aos gerentes reagir rapidamente a alterações no chão de fábrica do depósito e ajuda a melhorar sua capacidade de adaptação a situações mutáveis e a necessidade de transferir trabalho para outro pool de trabalho.

## <a name="turn-on-the-change-work-pool-on-work-feature"></a>Ativar o recurso Alterar pool de trabalho no trabalho

Antes de começar a configurar ou usar este recurso, você deve verificar se ele está disponível no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Alterar pool de trabalho no trabalho*

## <a name="set-up-the-change-work-pool-on-work-feature"></a>Configurar o recurso Alterar pool de trabalho no trabalho

Para usar este recurso, você deve ter alguns pools de trabalho configurados. Você também pode configurar seus modelos de trabalho para que eles atribuam um pool automaticamente. Se você quiser trabalhar no cenário de exemplo apresentado mais adiante neste tópico, configure o sistema conforme descrito nesta seção.

### <a name="set-up-work-pools"></a>Configurar pools de trabalho

Os pools de trabalho permitem organizar itens de trabalho por tipo. Para trabalhar com o recurso *Alterar pool de trabalho no trabalho*, você deve ter pelo menos dois pools de trabalho disponíveis. Para exibir e adicionar pools de trabalho, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Pools de trabalho**.
1. Se você estiver trabalhando com dados de demonstração da empresa **USMF** e for trabalhar no cenário de exemplo posteriormente neste tópico, adicione dois pools de trabalho com as seguintes configurações:

    - Pool de trabalho 1:

        - **ID do pool de trabalho:** *Webshop*
        - **Descrição:** *Web Shop*

    - Pool de trabalho 2:

        - **ID do pool de trabalho:** *CallCenter*
        - **Descrição:** *Call Center*

1. No Painel de ações, selecione **Salvar**.

### <a name="set-up-work-templates"></a>Configurar modelos de trabalho

Para cada um dos modelos de trabalho, você pode definir um pool de trabalho padrão, conforme necessário. Para cada modelo relevante, você atribui um pool de trabalho na coluna **ID do pool de trabalho**. Nesse caso, todos os itens de trabalho gerados por meio de um determinado modelo herdam automaticamente o pool de trabalho atribuído. Se você estiver trabalhando com os dados de demonstração da empresa **USMF** e for trabalhar no cenário de exemplo posteriormente neste tópico, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. No Painel de Ação, selecione **Editar** para colocar a página no modo de edição.
1. Edite o modelo definindo os seguintes valores:

    - **Modelo de trabalho:** *62 Separar para embalar*
    - **ID do pool de trabalho:** *Webshop*

1. Selecione **Salvar**.

## <a name="example-scenario"></a>Cenário de exemplo

Este cenário mostra como alterar o fluxo de processamento de um item de trabalho existente alterando seu pool de trabalho. Ele usa dados de demonstração da empresa **USMF** e as configurações que foram sugeridas anteriormente neste tópico.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Criar uma ordem de venda e liberá-la para o depósito

1. Confirme se há estoque disponível suficiente para os itens *A0001* e *A0002* no depósito *62*. Acesse **Gerenciamento de estoque \> Consultas e relatórios \> Lista disponível** e edite os filtros, conforme mostrado aqui:

    - O valor de **Depósito** começa com *62*.
    - O valor de **Número do item** é *A001* ou *A002*.

    Os dados de demonstração devem ter uma quantidade de 10 cada.

    Em seguida, você deve criar uma ordem de venda.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Conta de cliente:** *US-007*
    - **Depósito:** *62*

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Ele deve incluir uma nova linha vazia na grade da FastTab **Linhas de ordem de venda**. Nessa linha, defina os seguintes valores:

    - **Número de item:** *A0001*
    - **Quantidade:** *2*

1. No menu **Estoque** acima da grade, selecione **Reserva**.
1. Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.
1. Feche a página.
1. Na FastTab **Linhas da ordem de venda**, selecione **Adicionar linha** para adicionar outra linha à sua ordem de venda. Nessa linha, defina os seguintes valores:

    - **Número de item:** *A0002*
    - **Quantidade:** *2*

1. No menu **Estoque** acima da grade, selecione **Reserva**.
1. Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.
1. Feche a página.
1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.
1. Você recebe mensagens informativas que mostram a ID da onda e a ID da remessa que foram criadas com base na liberação. Anote a ID da onda.

### <a name="review-the-outbound-wave"></a>Revisar a onda de saída

1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Na grade, procure a ID da onda que foi criada com base na liberação da ordem de venda.
1. Selecione a ID da onda para exibir os detalhes.
1. Na FastTab **Linhas da onda**, verifique se uma ID de remessa é mostrada para a ordem de venda.

    > [!TIP]
    > Se a opção **Processar onda na liberação para o depósito** estiver definida como *Não* na configuração do modelo de onda de remessa, você deverá processar manualmente a onda selecionando **Processar** na guia **Onda** no Painel de Ação para criar um trabalho.

1. Verifique se a onda foi processada. Esse processamento cria o trabalho necessário.

### <a name="view-work-details-and-change-the-work-pool"></a>Exibir detalhes do trabalho e alterar o pool de trabalho

Você pode usar a página **Detalhes do trabalho** para exibir o trabalho criado e gerenciar o pool de trabalho.

1. Acesse **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.
1. Selecione a linha para o trabalho que acabou de criar. A coluna **Número da ordem** mostrará o número da ordem de venda.

    O campo **ID do pool de trabalho** será definido como a ID do pool de trabalho que foi configurado no modelo de trabalho.

    > [!TIP]
    > Se você não vir o campo **ID do pool de trabalho**, adicione a coluna à grade e atualize a página.

1. Para alterar o pool de trabalho associado à ID de trabalho, no Painel de Ação, na guia **Trabalho**, selecione **Alterar ID do pool de trabalho**.
1. Na caixa de diálogo **Alterar pool de trabalho**, na FastTab **Parâmetros**, no campo **ID do pool de trabalho**, selecione *CallCenter*.
1. Selecione **OK** para aplicar a alteração.
1. Observe que o valor do campo **ID do pool de trabalho** foi alterado para *CallCenter*.

> [!IMPORTANT]
> Quando a caixa de diálogo **Alterar pool de trabalho** for exibida, o campo **ID do pool de trabalho** poderá estar em branco por padrão. Se o campo estiver em branco quando você selecionar **OK** para aplicar as alterações, o pool de trabalho será completamente removido do trabalho.
>
> Além de alternar pools de trabalho, você pode usar esse procedimento para adicionar um pool de trabalho a qualquer item de trabalho que não tenha um ou para remover um pool de trabalho de qualquer item de trabalho que tenha um.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]