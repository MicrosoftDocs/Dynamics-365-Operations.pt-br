---
title: Clusters de armazenamento
description: Os clusters de armazenamento oferecem uma forma de separar várias chapas de licença ao mesmo tempo e, depois, levá-las para armazenamento em locais diferentes. Elas podem ser muito úteis para empresas de varejo, nas quais as chapas de licença normalmente não são paletes completos de estoque.
author: Mirzaab
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 559ca80976955d6328cb4d6b2020d5662460cef9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863640"
---
# <a name="putaway-clusters"></a>Clusters de armazenamento

[!include [banner](../includes/banner.md)]

Os clusters de armazenamento oferecem uma forma de separar várias chapas de licença ao mesmo tempo e, depois, levá-las para armazenamento em locais diferentes. Esse processo geralmente é conhecido como *entrega programada*. Os clusters de armazenamento podem ser muito úteis para empresas de varejo, nas quais as chapas de licença normalmente não são paletes completos de estoque. 

## <a name="turn-the-cluster-putaway-feature-on-or-off"></a>Ativar ou desativar o recurso de cluster de armazenamento

Para usar a funcionalidade descrita neste artigo, o recurso *Armazenamento de cluster* deve estar ativado para o sistema. A partir do Supply Chain Management 10.0.25, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.25, os administradores poderão habilitar ou desabilitar essa funcionalidade pesquisando o recurso *Armazenamento de cluster* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="setup-for-the-example-scenario"></a>Configuração do cenário de exemplo

### <a name="cluster-profiles"></a>Perfis de cluster

O perfil de cluster de armazenamento determina para onde um item irá, com base na localização atribuída ao item no momento do recebimento. Se forem necessários diferentes clusters, clusters de armazenamento diferentes deverão ser criados, um para cada item de menu de dispositivo móvel.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Perfis de cluster**.
1. No Painel de Ações, selecione **Novo**.
1. Na exibição do **Cabeçalho**, defina os seguintes valores:

    - **ID do perfil de cluster de armazenamento:** *Cluster de armazenamento*
    - **Nome da ID do perfil de cluster de armazenamento:** *Cluster de armazenamento*
    - **Tipo de cluster:** *Armazenamento*
    - **Número de sequência:** aceite o valor padrão.

1. Selecione **Salvar** para disponibilizar os campos necessários na Guia rápida **Geral**.
1. Na FastTab **Geral**, defina os seguintes valores:

    - **Tempo de atribuição do cluster:** *No recebimento*

        Este campo define se o cluster de armazenamento deve ser atribuído imediatamente quando o estoque é recebido ou se deve ser classificado posteriormente.

    - **Regra de atribuição de cluster:** *Manual*

        Esse campo define se a atribuição do cluster deve ser determinada automaticamente pelo sistema ou manualmente pelo usuário.

    - **Código de diretiva:** deixe este campo em branco.
    - **Localização do cluster de armazenamento:** *Recebimento*

        Os valores a seguir estão disponíveis:

        - **Recebimento** – Um local encontrado imediatamente durante o recebimento.
        - **Cluster fechado** – Um local encontrado quando o cluster é fechado.
        - **Direcionado pelo usuário** – Um local é encontrado quando a placa de licença é separada do cluster para armazenamento. Nesse caso, nenhuma localização é especificada quando o trabalho de armazenamento é criado. Durante o armazenamento, o usuário deve verificar a placa de licença ou a ID de trabalho para iniciar a etapa put. O sistema encontra o local de put novamente e informa ao usuário onde colocar a quantidade separada.

    - **Cluster de armazenamento por usuário:** *Não*

        Este campo define se cada cluster deve ser exclusivo por usuário quando os clusters são atribuídos automaticamente. Ele está disponível somente quando o campo **Regra de atribuição de cluster** está definido como *Automático*.

    - **Restrição de unidade:** Deixe este campo em branco.

        Este campo define a unidade que deve ser recebida para o perfil ser válido. Se estiver em branco, todas as unidades serão válidas.

    - **Quebra de unidade de trabalho:** *Individual*

        Este campo define se todo o estoque deve ser consolidado (usando a ID do cluster e a placa de licença) em uma chapa de licença quando um cluster é fechado e se deve ser retirado como uma única placa de licença ou separadamente nas placas de licença recebidas. Este campo não estará disponível quando o campo **Localizar cluster de armazenamento** estiver definido como *Recebido*.

    - **O cluster persiste como placa de licença pai:** *Não*

        Se esta opção estiver definida como *Sim*, quando a etapa put for concluída, a ID do cluster se tornará uma placa de licença pai e todos os itens na ID do cluster serão vinculados à placa da licença pai.

1. Na Guia rápida **Classificação de cluster**, você pode definir critérios de classificação de armazenamento. Selecione **Novo** na barra de ferramentas para adicionar uma linha e defina os seguintes valores:

    - **Número de sequência:** aceite o valor padrão.
    - **Nome do campo:** *WMSLocationId*

        Este campo define o campo que essa linha deve usar como um critério de classificação.

    - **Classificação:** *Crescente*

        Este campo define se a classificação deve ser feita em ordem crescente ou decrescente.

1. Na Guia rápida **Modelo de trabalho do cluster**, selecione **Novo** na barra de ferramentas para adicionar uma linha e defina os seguintes valores:

    - **Tipo de ordem de trabalho:** *Ordens de compra*
    - **Modelo de trabalho:** *Direto de OC 61*

1. No Painel de ações, selecione **Salvar** e, em seguida, **Editar consulta**.
1. Na caixa de diálogo **Cluster de armazenamento**, na guia **Intervalo**, selecione **Adicionar** para adicionar uma segunda linha à consulta. Em seguida, atualize as linhas da consulta conforme mostrado na tabela a seguir.

    | Tabela | Tabela derivada | Campo | Critérios |
    |---|---|---|---|
    | Trabalho | Trabalho | Depósito | *61* |
    | Trabalho | Trabalho | ID do Trabalho | Deixe esse campo em branco. |

1. Selecione **OK** para salvar a consulta e fechar a caixa de diálogo.
1. No Painel de ações, selecione **Salvar**, e feche a página.

> [!IMPORTANT]
> Os campos no perfil de cluster que aparecem esmaecidos quando **Gerar ID do cluster** está definido como *Sim* não estão disponíveis e não são considerados quando esse recurso é usado.

### <a name="mobile-device-menu-items"></a>Itens de menu do dispositivo móvel

Dois novos itens de menu de dispositivo móvel estão disponíveis para esse recurso. O item de menu **Receber e classificar cluster** é usado para classificar o estoque recebido em um cluster de armazenamento no recebimento. O item de menu **Cluster de armazenamento** é usado para colocar o cluster fora depois de atribuído.

#### <a name="receive-and-sort-cluster"></a>Receber e classificar cluster

Criar um novo item de menu de dispositivo móvel para receber estoque e classificar em um cluster. Este item de menu criará trabalho de entrada depois que o estoque for recebido, o que indica que o item de menu a receber será usado para os clusters de putaway.

> [!NOTE]
> O item de menu **Receber e classificar cluster** pode ser usado com os seguintes itens de menu de recebimento:
>
> - Recebimento da linha da ordem de compra
> - Recebimento do item da ordem de compra
> - Recebimento do item de carga

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ações, selecione **Novo**.
1. Na exibição do **Cabeçalho**, defina os seguintes valores:

    - **Nome do item de menu:** *Receber e classificar cluster*
    - **Título:** *Receber e classificar cluster*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Não*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Processo de criação de trabalho:** *Recebimento de item da ordem de compra*
    - **Gerar placa de licença:** *Sim*
    - **Atribuir cluster de armazenamento:** *Sim*

        > [!NOTE]
        > A opção **Atribuir cluster de armazenamento** está disponível apenas para a atividade *Processo de criação de trabalho* em uma etapa para recebimento.

    Aceite os valores padrão para os campos restantes.

1. No Painel de ações, selecione **Salvar**.

#### <a name="cluster-putaway"></a>Armazenamento de cluster

Crie um novo item de menu de dispositivo móvel para colocar o cluster fora depois que ele tiver sido atribuído.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ações, selecione **Novo**.
1. Na exibição do **Cabeçalho**, defina os seguintes valores:

    - **Nome do item de menu:** *Cluster de armazenamento*
    - **Título:** *Cluster de armazenamento*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Sim*

1. Na FastTab **Geral**, defina o campo **Direcionado por** como *Cluster de armazenamento*. Aceite os valores padrão para os campos restantes.
1. Na Guia rápida **Classes de trabalho**, configure a classe de trabalho válida para este item de menu de dispositivo móvel:

    - **ID da classe de trabalho:** *Compra*
    - **Tipo de ordem de trabalho:** *Ordens de compra*

1. No Painel de ações, selecione **Salvar**.

### <a name="mobile-device-menu"></a>Menu de dispositivos móveis

Adicione os itens de menu que acabou de criar ao menu de entrada do aplicativo móvel.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. No Painel de Ações, selecione **Editar**.
1. Na lista de menus, selecione **Entrada**.
1. Na lista **Menus e Itens de Menu Disponíveis**, localize e selecione **Receber e classificar cluster**.
1. Selecione o botão de seta para a direita a fim de mover o item de menu selecionado para a lista **Estrutura de Menu**.
1. Use o botão seta para cima ou seta para baixo para mover o item de menu para a posição desejada no menu.
1. No Painel de ações, selecione **Salvar**.
1. Repita as etapas 4 a 7 para adicionar os itens de menu restantes:

    - Atribuir cluster
    - Armazenamento de cluster

## <a name="example-scenario"></a>Cenário de exemplo

Esse cenário simula o processamento de cluster de armazenamento.

### <a name="create-a-purchase-order"></a>Criar uma ordem de compra

1. Acesse **Contas a pagar \> Ordens de compra \> Todas as ordens de compra**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de compra**, defina os seguintes valores:

    - **Conta do fornecedor:** *1001*
    - **Depósito:** *61*

1. Selecione **OK**.

    A página **Todas as ordens de compra** é exibida.

1. Na página **Todas as ordens de compra**, na Guia rápida **Linhas da ordem de compra**, use o botão **Adicionar linha** para adicionar as seguintes linhas:

    - Linha de ordem de compra 1:

        - **Número de item:** *A0001*
        - **Quantidade:** *10*

    - Linha de ordem de compra 2:

        - **Número de item:** *A0002*
        - **Quantidade:** *20*

    - Linha de ordem de compra 3:

        - **Número de item:** *M9215*
        - **Quantidade:** *30*

1. No Painel de ações, selecione **Salvar**.
1. Anote o número da ordem de compra.

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a>Receber estoque e armazená-lo longe do dispositivo móvel

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a>Receber e classificar o estoque em um cluster

1. Entre no aplicativo móvel de Gerenciamento de depósito como um usuário definido para o depósito *61*.
1. No menu principal, selecione **Entrada**.
1. No menu **Entrada**, selecione **Receber e classificar cluster**.
1. No campo **Ponum**, insira o número da ordem de compra.
1. Selecione o botão **OK** (o botão de marca de seleção).
1. Selecione o campo **Item**, insira o número de item *A0001* e selecione **OK**.
1. Selecione o campo **Qtd**, insira *10* usando o teclado numérico e, em seguida, selecione o botão de marca de seleção.
1. Na página de tarefas **Qtd**, selecione **OK** (o botão marca de seleção) para confirmar a quantidade inserida.
1. Na página de tarefas **Item**, selecione **OK** para confirmar que o item *A0001* foi inserido.
1. Selecione o campo **ID do cluster** e insira um valor para atribuir uma ID para o cluster que está sendo criado.

    A ID inserida aqui será usada quando os dois itens restantes da ordem de compra forem recebidos.

1. Selecione **OK**.

    A página de tarefa **Ponum** será exibida e mostrará uma mensagem "Trabalho concluído".

    O item *A0001* foi recebido no local *RECV* e atribuído à ID do cluster que você inseriu na etapa 10.

1. Repita as etapas 4 a 11 para receber os dois itens restantes da ordem de compra e atribuí-los à ID do cluster:

    - Uma quantidade de *20* para o item *A0002*
    - Uma quantidade de *30* para o item *M9215*

#### <a name="close-the-cluster"></a>Fechar o cluster

Antes que os itens no cluster possam ser descartados, o cluster deve ser fechado.

1. No Supply Chain Management, Acesse **Gerenciamento de depósito \> Trabalho \> Saída \> Clusters de trabalho**.
1. Na página **Clusters de trabalho**, na seção **Cluster de trabalho**, pesquise o campo **ID do cluster** para a ID do cluster inserida anteriormente.
1. Se o cluster não for exibido, talvez ele já tenha sido fechado. Para determinar se o cluster foi fechado, marque a caixa de seleção **Mostrar trabalho fechado** e procure a ID do cluster inserida anteriormente. E então, siga uma destas etapas:

    - Se o cluster tiver sido fechado, pule as etapas restantes deste procedimento e Acesse o próximo procedimento, [Armazenar o cluster](#put-the-cluster-away).
    - Se o cluster não tiver sido fechado, siga as etapas restantes deste procedimento para fechar o cluster manualmente. Em seguida, Acesse o procedimento a seguir.

1. Na seção **Cluster de trabalho**, selecione a ID de cluster inserida anteriormente.
1. No Painel de Ação, selecione **Fechar cluster**.

    Depois que o cluster for fechado, ele não será mais exibido na seção **Cluster de trabalho** (a menos que a caixa de seleção **Mostrar trabalho fechado** esteja marcada).

#### <a name="put-the-cluster-away"></a>Armazenar o cluster

1. Entre no aplicativo móvel de Gerenciamento de depósito como um usuário definido para o depósito *61*.
1. No menu principal, selecione **Entrada**.
1. No menu **Entrada**, selecione **Cluster de armazenamento**.
1. Selecione **ID do cluster** e digite a ID do cluster que você inseriu anteriormente para o cluster fechado.
1. Selecione **OK**.

    A página **Cluster de armazenamento: Pegar** é exibida. Ele mostra a ID do cluster, o local de separação, os itens (o valor *Múltiplo* será mostrado) e a quantidade total no cluster que deve ser separada.

1. Selecione **OK**.

    A página **Cluster de armazenamento: Colocar** é exibida. As instruções **Put** identificam a ID do cluster, o local de remessa, os itens, a quantidade total e as IDs da placa de licença para os itens que foram recebidos no cluster.

    Você tem as opções padrão para substituir ou passar nesta etapa.

    ![Cluster de armazenamento: inserir página.](media/Cluster_putaway-Put.png "Cluster de armazenamento: Página put")

1. Selecione **OK** para confirmar o armazenamento do cluster.

    Uma mensagem "Cluster Concluído" é exibida.

## <a name="notes-and-tips"></a>Observações e dicas

Nos casos em que a ID do cluster se torna a placa de licença pai de um palete aninhado, a posição de put é automaticamente fornecida quando a ID do cluster é verificada. Nenhuma placa de licença adicional deverá ser verificada, mesmo se a geração da placa de licenças estiver definida como manual.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]