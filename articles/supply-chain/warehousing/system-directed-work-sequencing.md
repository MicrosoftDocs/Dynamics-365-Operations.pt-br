---
title: Sequenciamento do trabalho direcionado pelo sistema
description: Este tópico fornece informações sobre o sequenciamento de trabalho direcionado pelo sistema. Essa funcionalidade permite classificar e filtrar as ordens de serviço que o sistema apresenta a usuários para execução. Ela é útil em cenários que exigem critérios adicionais para direcionar o processo de separação de depósito.
author: Mirzaab
manager: tfehr
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 86d396b069a354b8fa7e15793372a8293273d238
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017014"
---
# <a name="system-directed-work-sequencing"></a>Sequenciamento do trabalho direcionado pelo sistema

[!include [banner](../includes/banner.md)]

O sequenciamento direcionado pelo sistema permite classificar e filtrar as ordens de serviço que o sistema apresenta a usuários para execução. Ela é útil em cenários que exigem critérios adicionais (como o tempo de remessa, a zona de separação, o perfil de local ou uma combinação de vários critérios) para direcionar o processo de separação de depósito.

Essa funcionalidade estende a funcionalidade atual de separação direcionada pelo sistema, adicionando uma ordem de consulta direcionada pelo sistema, na qual os usuários podem configurar uma sequência e uma ou mais consultas que avaliarão todas as ordens de serviço criadas. Somente as ordens de serviço que atendem aos critérios especificados na configuração do item de menu do dispositivo móvel serão capturadas e apresentadas.

Portanto, essa funcionalidade permite maior otimização de processos de separação de depósito, já que identifica as ordens de serviço que correspondem aos critérios especificados, atribuindo-as ao item de menu de dispositivo móvel correto e apresentando-as a um trabalhador, com base em um conjunto de habilidades específico, um equipamento de separação ou outro requisito.

> [!NOTE]
> Se forem necessários critérios diferentes, vários itens de menu de dispositivo móvel deverão ser usados.

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a>Ative o recurso de sequenciamento de trabalho direcionado pelo sistema em toda a organização

Para que você possa usar o sequenciamento de trabalho direcionado pelo sistema, o recurso deve estar ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *sequenciamento de trabalho direcionado pelo sistema em toda a organização*

## <a name="setup"></a>Instalação

### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

Para trabalhar com o cenário usando os valores apresentados neste tópico, você deve trabalhar em um sistema em que os dados de demonstração padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF**. O cenário usa o depósito *51* dos dados de demonstração.

> [!IMPORTANT]
> Antes de liberar as ordens para o depósito, verifique se os locais de separação têm estoque suficiente para todos os itens nas ordens.
>
> Os dados USMF padrão devem oferecer suporte a esse cenário. Se não estiver usando dados de demonstração, revise a configuração **Diretiva de localização** para saber quais locais de separação são usados para separação da ordem de venda. Se precisar ajustar o estoque, você poderá criar movimentações manuais, usar o reabastecimento ou utilizar qualquer outro fluxo.

### <a name="set-up-a-mobile-device-menu-item"></a>Configurar um item de menu de dispositivo móvel

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Na lista de itens de menu de dispositivo móvel, selecione **Separação de Vendas – Sistema**. O item de menu necessário já deve existir. 
1. Confirme as seguintes configurações:

    - Na FastTab **Geral** , o campo **Direcionado por** deve ser definido como *Dirigido pelo sistema*.
    - A FastTab **Classes de trabalho** deve mostrar as seguintes configurações.

        | ID da classe de trabalho | Tipo de ordem de serviço |
        |---|---|
        | Sales | Ordens de Venda |
        | Separação de OV | Ordens de Venda |

1. No Painel de Ações, selecione **Consultas de sequência de trabalho direcionadas pelo sistema**.
1. Selecione **Editar**.
1. Exclua a linha existente e confirme a ação selecionando **Sim**.
1. No Painel de Ações, selecione **Novo** para criar uma linha.
1. Na nova linha, defina os valores a seguir:

    - **Número de sequência:** *1*
    - **Campo de descrição:** *Quantidade de trabalho inferior a 20 e decrescente*

1. Selecione **Salvar**.
1. No Painel de Ações, selecione **Editar Consulta**.
1. Na guia **Junções** , expanda a hierarquia de junções para mostrar a tabela **Linhas de trabalho**.
1. Selecione a junção de tabela **Linhas de trabalho**.
1. Selecione **Adicionar junção de tabela**.
1. Na lista exibida, localize e selecione a linha que tem as seguintes configurações:

    - **Modo de junção:** *n:1*
    - **Relação:** *Locais (local)*

1. Escolha **Selecionar**.

    Os locais são adicionados à junção da tabela.

1. Na guia **Classificação** , selecione **Adicionar** para adicionar uma linha.
1. Na nova linha, defina os valores a seguir:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *Quantidade de trabalho* (na caixa de mensagem que aparecer, selecione **Sim** para adicionar classificação a este campo.)
    - **Direção da pesquisa:** *Decrescente*

1. Selecione a guia **Intervalo**.

    Se somente critérios de trabalho específicos devem ser incluídos no sequenciamento, você pode especificá-los na guia **Intervalo**. Neste exemplo, você deseja incluir somente o trabalho em que a quantidade é inferior a 20 ea (a menor unidade de medida).

    Observe que algumas linhas já foram incluídas. Essas linhas não devem ser removidas.

1. Selecione **Adicionar** para adicionar uma linha.
1. Na nova linha, defina os valores a seguir:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *Quantidade de trabalho de estoque*
    - **Critérios:** *\<20* (menos de 20)

1. Selecione **Adicionar** para adicionar outra linha.
1. Na nova linha, defina os valores a seguir:

    - **Tabela:** *Linhas de trabalho*
    - **Tabela derivada:** *Linhas de trabalho*
    - **Campo:** *Tipo de trabalho*
    - **Critérios:** *Separação*

1. Selecione **Adicionar** para adicionar outra linha.
1. Na nova linha, defina os valores a seguir:

    - **Tabela:** *Localizações*
    - **Tabela derivada:** *Locais*
    - **Campo:** *ID de perfil da localização*
    - **Critérios:** *!ESTÁGIO*

        > [!IMPORTANT]
        > Inclua o ponto de exclamação ( *!* ) antes de *ESTÁGIO*.

1. Selecione **OK** para salvar e fechar a consulta.
1. Selecione **Salvar**.
1. Feche a página para retornar à página **Itens de menu do dispositivo móvel**.

> [!NOTE]
> Essa configuração define os critérios que serão usados para alimentar o trabalho elegível para o item de menu do dispositivo móvel. Se você adicionar mais linhas de critérios à consulta, o sistema usará primeiro a linha de consulta com o menor número de sequência. Em outras palavras, todo o trabalho elegível para a sequência número 1 será apresentado primeiro ao usuário e, em seguida, todo o trabalho para a sequência número 2. Portanto, se um intervalo e classificação específicos precisam ser usados juntos, eles devem ser especificados na mesma consulta de sequência de trabalho direcionada pelo sistema.
>
> Esta configuração capturará trabalhos que tenham pelo menos uma linha em que a quantidade seja inferior a 20 ea. Portanto, se o trabalho tiver uma linha em que a quantidade seja exatamente 20 ea ou mais de 20 ea, ela será válida, desde que também tenha pelo menos uma linha em que a quantidade seja inferior a 20 ea.

### <a name="location-directives"></a>Diretivas de localização

Se você estiver usando dados padrão da Contoso, a consulta para a ação diretiva de localização não exigirá alterações. No entanto, para verificar se as diretivas de localização capturarão os itens nas ordens de venda quando você aplicar o recurso em um ambiente que não seja da Contoso, crie uma nova diretiva de localização. Para verificar as configurações no ambiente de demonstração, siga estas etapas.

1. Vá para **Gerenciamento de depósito** \> **Configuração** \> **Diretivas de localização**.
1. No campo **Tipo de ordem de trabalho** , selecione *Ordens de compra*.
1. Selecione a diretiva de localização chamada *Separação 51*.
1. Na guia **Ações de Diretiva de Localização** , selecione a linha para a ação **Separação**.
1. Selecione **Editar consulta** acima da grade.
1. Analise a consulta **Intervalo**.

    1. Localize a linha em que o campo **Campo** está definido como *Local*.
    2. Verifique se o campo **Critérios** está em branco (isto é, se não há restrições).

## <a name="scenario"></a>Cenário

### <a name="create-sales-order-picking-work"></a>Criar trabalho de separação de ordem de venda

Antes da execução da separação direcionada pelo sistema, deve ser criado um trabalho de saída. Para esse cenário, você criará quatro ordens de venda com base nas consultas de sequência de trabalho direcionadas pelo sistema.

Você reservará quantidades de estoque para cada ordem de venda. Portanto, o estoque reservado não pode ser retirado do depósito para outras ordens, a menos que a reserva do estoque, ou parte dela, seja cancelada.

Você liberará cada ordem de venda para o depósito a fim de criar o trabalho de saída.

#### <a name="sales-order-1"></a>Ordem de venda 1

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo** para criar a ordem de venda 1.
1. Na caixa de diálogo **Criar ordem de venda** , defina os seguintes valores:

    - Na seção **Cliente** , defina o campo **Conta do cliente** como *US-004*.
    - Na seção **Geral** , defina o campo **Depósito** como *51*.

1. Selecione **OK** para fechar a caixa de diálogo. Anote o número da ordem de venda.
1. Adicione uma linha à nova ordem de venda e defina os seguintes valores:

    - **Número de item:** *M9200*
    - **Quantidade:** *20*

1. No menu **Estoque** acima da grade, selecione **Reserva**.
1. Na página **Reserva** , selecione **Reservar lote** para reservar o estoque.
1. Feche a página **Reserva**.
1. No Painel de Ações, na guia **Depósito** , selecione **Liberar para depósito** para criar trabalho para o depósito.

    Você recebe mensagens informativas que mostram a ID da onda e as IDs de remessa que foram criadas para a ordem de venda.

#### <a name="sales-order-2"></a>Ordem de venda 2

1. No Painel de Ações, selecione **Novo** para criar a ordem de venda 2.
1. Na caixa de diálogo **Criar ordem de venda** , defina os seguintes valores:

    - **Conta de cliente:** *US-007*
    - **Depósito:** *51*

1. Selecione **OK** para fechar a caixa de diálogo. Anote o número da ordem de venda.
1. Adicione uma linha à nova ordem de venda e defina os seguintes valores:

    - **Número de item:** *M9200*
    - **Quantidade:** *5*

1. Selecione **Adicionar linha** para adicionar uma segunda linha e defina os seguintes valores:

    - **Número de item:** *M9201*
    - **Quantidade:** *1*

1. Reservar estoque para ambas as linhas.
1. Libere a ordem para o depósito.

#### <a name="sales-order-3"></a>Ordem de venda 3

1. No Painel de Ações, selecione **Novo** para criar a ordem de venda 3.
1. Na caixa de diálogo **Criar ordem de venda** , defina os seguintes valores:

    - **Conta de cliente:** *US-009*
    - **Depósito:** *51*

1. Selecione **OK** para fechar a caixa de diálogo. Anote o número da ordem de venda.
1. Adicione uma linha à nova ordem de venda e defina os seguintes valores:

    - **Número de item:** *M9200*
    - **Quantidade:** *7*

1. Selecione **Adicionar linha** para adicionar uma segunda linha e defina os seguintes valores:

    - **Número de item:** *M9202*
    - **Quantidade:** *8*

1. Reservar estoque para ambas as linhas.
1. Libere a ordem para o depósito.

#### <a name="sales-order-4"></a>Ordem de venda 4

1. No Painel de Ações, selecione **Novo** para criar a ordem de venda 4.
1. Na caixa de diálogo **Criar ordem de venda** , defina os seguintes valores:

    - **Conta de cliente:** *US-010*
    - **Depósito:** *51*

1. Selecione **OK** para fechar a caixa de diálogo. Anote o número da ordem de venda.
1. Adicione uma linha à nova ordem de venda e defina os seguintes valores:

    - **Número de item:** *M9200*
    - **Quantidade:** *25*

1. Selecione **Adicionar linha** para adicionar uma segunda linha e defina os seguintes valores:

    - **Número de item:** *M9202*
    - **Quantidade:** *10*

1. Reservar estoque para ambas as linhas.
1. Libere a ordem para o depósito.

### <a name="get-work-ids-for-the-work-that-was-created"></a>Obter IDs de trabalho para o trabalho que foi criado

1. Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.
1. Filtre o campo **Depósito** para que somente o trabalho do depósito *51* seja exibido.
1. Quatro IDs de trabalho devem ter sido criadas. Anote a ID de trabalho de cada ordem de venda.

    | ID da Ordem de venda | ID do Trabalho | Quantidade de trabalho |
    |---|---|---|
    | Ordem de venda 1 | ID de trabalho 1 | 20 ea |
    | Ordem de venda 2 | ID de trabalho 2 | 6 ea (soma das duas linhas) |
    | Ordem de venda 3 | ID de trabalho 3 | 15 ea (soma das duas linhas) |
    | Ordem de venda 4 | ID de trabalho 4 | 35 ea (soma das duas linhas) |

Antes de executar o fluxo no dispositivo móvel, verifique se somente o trabalho recém-criado está com o status *Aberto* para o depósito *51* e o tipo de ordem de trabalho de *Ordem de venda*. Caso contrário, os resultados do teste podem variar, pois a separação direta do sistema incluirá todo o trabalho elegível.

1. Vá para **Gerenciamento de depósito \> Trabalho \> Saída \> Trabalho de venda aberto**.
1. Na grade **Trabalho de venda aberto** , filtre o campo **Depósito** para que somente o trabalho do depósito *51* seja exibido.
1. Confirme se aparecem apenas as quatro IDs de trabalho criadas anteriormente.
1. Feche a página **Trabalho**.

### <a name="mobile-device-flow-execution"></a>Execução do fluxo do dispositivo móvel

Com base na configuração, o sistema alimentará o trabalho do usuário que é classificado da quantidade da linha de trabalho superior à inferior. A quantidade em cada linha será inferior a 20 ea.

Lembre-se de que esta configuração capturará trabalhos com pelo menos uma linha em que a quantidade seja inferior a 20 ea. Portanto, se o trabalho tiver outra linha em que a quantidade seja exatamente 20 ea ou superior a 20 ea, ela também será válida.

#### <a name="mobile-app"></a>Aplicativo móvel

1. Entre no aplicativo do depósito como um usuário no depósito *51*.
1. Vá para **Saída \> Separação de Venda - Sistema**.

    A etapa de separação para a ID de trabalho *4* é apresentada. Essa ID de trabalho é apresentada primeiro por causa da configuração da ordem de consulta direcionada pelo sistema, na qual você especificou que o trabalho deve ser sequenciado com base na quantidade de linha de trabalho decrescente.

1. Conclua a separação necessária e coloque-a para fechar a ID de trabalho.

    Em seguida, a ID de trabalho *3* é apresentada. Uma das linhas de trabalho é a próxima na sequência, com base na quantidade da linha de trabalho.

1. Conclua a separação e coloque-a para fechar a ID de trabalho.

    Em seguida, a ID de trabalho *2* é apresentada. A linha de separação deste trabalho é a próxima na sequência.

1. Conclua a separação e coloque-a para fechar a ID de trabalho.

    Nenhum trabalho adicional deve ser apresentado a você. A ID de trabalho *1* não está qualificada para este item de menu de dispositivo móvel, pois a consulta especifica que os cabeçalhos de trabalho serão considerados somente se a quantidade nas linhas de trabalho for inferior a 20 ea.

## <a name="tips"></a>Dicas

As consultas de sequência de trabalho direcionadas pelo sistema são *inclusivas*. É importante lembrar desse fato para algumas configurações. Por exemplo, você deseja que um item de menu específico processe apenas o trabalho em que a unidade de trabalho seja *ea* e especifica essa restrição na guia **Intervalo** da consulta. Nesse caso, todos os trabalhos em que pelo menos uma linha de trabalho tenha a unidade de trabalho definida como *ea* serão alimentados para o trabalhador. Portanto, esse trabalho também podem incluir trabalho em que as linhas de trabalho tenham uma unidade de trabalho diferente de *ea* (como *caixa* ou *palete* ). A consulta excluirá o trabalho apenas quando nenhuma linha de trabalho tiver a unidade de trabalho definida como *ea*.

Portanto, no exemplo desse cenário, a ID de trabalho *4* também foi capturada pela consulta. Quando ela foi criada, duas linhas foram adicionadas: uma para 25 ea e outra para 10 ea. O trabalho ainda foi apresentado ao usuário porque pelo menos uma linha de trabalho tem uma quantidade inferior a 20 ea.

Dependendo do cenário, você pode evitar esse comportamento usando pausas de trabalho.
