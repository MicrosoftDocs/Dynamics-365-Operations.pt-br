---
title: Posicionamento da placa de licença de localização
description: O posicionamento da placa de licença de localização permite ver onde há uma placa de licença em uma localização com vários paletes, como um que usa um rack de paletes com profundidade dupla.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 7b0ebfb965e5a8f1bfe1857a9642d998dac2faf3
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017107"
---
# <a name="location-license-plate-positioning"></a>Posicionamento da placa de licença de localização

[!include [banner](../includes/banner.md)]

O posicionamento da placa de licença de localização permite ver onde há uma placa de licença em uma localização com vários paletes, como um que usa um rack de paletes com profundidade dupla.

O recurso adiciona um número de sequência a cada placa de licença colocada em um local de armazenamento. Esse número de sequência é usado para ordenar as placas de licença no local de armazenamento. Por isso, o recurso oferece suporte de modo inteligente a cenários em que os clientes usam um sistema de rack de gravidade e devem saber qual placa de licença está virada para a frente, para fins de separação.

Este tópico apresenta um cenário que mostra como configurar e usar o recurso.

## <a name="turn-on-the-location-license-plate-positioning-feature"></a>Ativar o recurso de posicionamento da placa de licença de localização

Para que você possa usar o posicionamento da placa de licença de localização, o recurso deve estar ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Posicionamento da placa de licença de localização*

## <a name="example-scenario"></a>Cenário de exemplo

### <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para trabalhar nesse cenário usando os valores aqui sugeridos, você deve trabalhar em um sistema no qual os dados de exemplo estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de iniciar.

### <a name="set-up-the-feature-for-this-scenario"></a>Configurar o recurso para o cenário

Execute os procedimentos a seguir para configurar o recurso *Posicionamento da placa de licença de localização* para o cenário apresentado neste tópico.

#### <a name="location-profiles"></a>Perfis de localização

O recurso deve estar ativado no perfil de localização de cada localização onde ele será usado.

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.
1. Na lista de perfis de localização no painel esquerdo, selecione **MASSA-06**.
1. Na FastTab **Geral** , duas novas opções foram adicionadas pelo recurso. Defina os seguintes valores:

    - **Habilitar posição da placa de licença:** *Sim*

        Quando a opção for definida como *Sim* , a posição será mantida para as placas de licença no local.

    - **Exibir posição da LP do dispositivo móvel:** *Sim*

        Quando a opção for definida como *Sim* , a posição da placa de licença será mostrada para os usuários do dispositivo móvel durante o ajuste e a contagem. Você só poderá alterar a configuração da opção quando o recurso estiver ativado.

1. Selecione **Salvar**.

#### <a name="location-directives"></a>Diretivas de localização

1. Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No painel esquerdo, verifique se o campo **Tipo de ordem de trabalho** está definido como *Ordens de venda*.
1. Na lista de diretivas de localização, selecione **Ordem de separação de OV 61**.
1. No Painel de Ações, selecione **Editar**.
1. Na FastTab **Linhas** , selecione a linha que tem um valor **Número de sequência** de *2*.
1. Na FastTab **Ações de Diretiva de Localização** , selecione a linha que tem um valor **Nome** de *Separar para menos que palete* (deve ser a única linha) e mude o valor **Número de sequência** para *2*.
1. Selecione **Novo** acima da grade para adicionar uma linha para uma nova ação de diretiva de localização.
1. Na nova linha, defina os valores a seguir:

    - **Número de sequência:** *1*
    - **Nome:** *Posição de separação 1*

1. Com a nova linha ainda selecionada, selecione **Editar consulta** acima da grade.
1. No editor de consultas, selecione a guia **Junções**.
1. Expanda junção de tabela **Localizações** para mostrar a junção na tabela **Dimensões de estoque**.
1. Expanda a junção de tabela **Dimensões de estoque** para mostrar a junção na tabela **Estoque disponível**.
1. Selecione **Dimensões de estoque** e, depois, **Adicionar tabela de junção**.
1. Na lista de tabelas exibida, na coluna **Relação** , selecione **Placa de licença (Placa de licença)**. Depois, clique em **Selecionar** para adicionar **Placa de licença** à junção de tabela **Dimensões de estoque**.
1. Com **Placa de licença** ainda selecionada, selecione **Adicionar junção de tabela**.
1. Na lista de tabelas exibida, na coluna **Relação** , selecione **Posicionamento da placa de licença de localização (Placa de licença)**. Depois, clique em **Selecionar** para adicionar **Posicionamento da placa de licença de localização** à junção de tabela **Dimensões de estoque**.

    ![Junções de tabela](media/LpTableJoin.png "Junções de tabela")

1. Selecione **OK** para confirmar as tabelas associadas atualizadas e fechar o editor de consultas.
1. Na FastTab **Ações de Diretiva de Localização** , selecione **Editar consulta** novamente para reabrir o editor de consultas.
1. Na guia **Intervalo** , selecione **Adicionar** para adicionar uma linha à grade.
1. Na nova linha, defina os valores a seguir:

    - **Tabela:** *Posicionamento da placa de licença de localização*
    - **Tabela derivada:** *Posicionamento da placa de licença de localização*
    - **Campo:** *Posição da LP*
    - **Critérios:** *1*

    ![Novo intervalo](media/LpPositionCriteria.png "Novo intervalo")

1. Selecione **OK** para confirmar as alterações e fechar o editor de consultas.

### <a name="set-up-sample-data-for-this-scenario"></a>Configurar dados de exemplo para o cenário

Para este cenário, o usuário deve entrar no aplicativo móvel de depósito usando um trabalhador configurado para o depósito *61* para executar o trabalho. O usuário também deve concluir as transações.

Como o recurso *Posicionamento da placa de licença de localização* adiciona um novo identificador para as posições de placa de licença em uma localização, primeiro você deve criar alguns dados para dar suporte ao cenário.

#### <a name="spot-count-the-first-location"></a>Contagem pontual da primeira localização

1. Abra o aplicativo móvel de depósito e entre no depósito *61*.
1. Vá para **Estoque \> Contagem Pontual**.
1. Na página **Contagem Pontual** , defina o campo **Localização** como *01A01R1S1B*.
1. Selecione **OK**.

    A página mostra a localização que você inseriu. Ela também mostra a seguinte mensagem: "Localização concluída, adicionar nova LP ou item?"

1. Selecione **Atualizar** para adicionar uma contagem na localização.
1. Na página **Contagem Cíclica: Adicionar um Novo LP ou Item** , selecione o campo **Item** e insira o valor *A0001*.
1. Selecione **OK**.
1. Na página **Contagem Cíclica: Adicionar um Novo LP ou Item** , selecione o campo **LP** e insira o valor *LP1001* (ou qualquer outro número de placa de licença de sua escolha).

    A página **Contagem Cíclica: Adicionar um Novo LP ou Item** mostra **Posição 1 da Placa de Licença**.

1. Selecione **OK**.

    Agora, você deve especificar a quantidade do item contada na placa de licença.

1. Defina o campo **Qtd.** como *10*.
1. Selecione **OK**.

    A página mostra a localização que você inseriu. Ela também mostra a seguinte mensagem: "Localização concluída, adicionar nova LP ou item?"

1. Selecione **Atualizar** para adicionar outra contagem na localização.
1. Na página **Contagem Cíclica: Adicionar um Novo LP ou Item** , selecione o campo **Item** e insira o valor *A0002*.
1. Selecione **OK**.
1. Na página **Contagem Cíclica: Adicionar um Novo LP ou Item** , selecione o campo **LP** e insira o valor *LP1002* (ou qualquer outro número de placa de licença de sua escolha, desde que seja diferente do número da placa de licença especificado anteriormente).
1. Mude a posição da placa de licença definindo o campo **Posição da LP** como *2*.
1. Selecione **OK**.
1. Especifique a quantidade do item contada na placa de licença definindo o campo **Qtd.** como *10*.
1. Selecione **OK**.

    A página mostra a localização que você inseriu. Ela também mostra a seguinte mensagem: "Localização concluída, adicionar nova LP ou item?"

1. Selecione **OK**.

Agora o trabalho está concluído.

#### <a name="spot-count-the-second-location"></a>Contagem pontual da segunda localização

1. Na página **Contagem Pontual** , defina o campo **Localização** como *01A01R1S2B*.
1. Selecione **OK**.

    A página mostra a localização que você inseriu. Ela também mostra a seguinte mensagem: "Localização concluída, adicionar nova LP ou item?"

1. Selecione **Atualizar** para adicionar uma contagem na localização.
1. Na página **Contagem Cíclica: Adicionar um Novo LP ou Item** , selecione o campo **Item** e insira o valor *A0002*.
1. Selecione **OK**.
1. Na página **Contagem Cíclica: Adicionar um Novo LP ou Item** , selecione o campo **LP** e insira o valor *LP1003* (ou qualquer outro número de placa de licença de sua escolha, desde que seja diferente dos dois números de placa de licença especificados no procedimento anterior).

    A página **Contagem Cíclica: Adicionar um Novo LP ou Item** mostra **Posição 1 da Placa de Licença**.

1. Selecione **OK**.
1. Especifique a quantidade do item contada na placa de licença definindo o campo **Qtd.** como *10*.
1. Selecione **OK**.

    A página mostra a localização que você inseriu. Ela também mostra a seguinte mensagem: "Localização concluída, adicionar nova LP ou item?"

1. Selecione **OK**.

Agora o trabalho está concluído.

#### <a name="work-details"></a>Detalhes do trabalho

> [!NOTE]
> As contagens pontuais do aplicativo móvel criam um trabalho de contagem cíclica no Microsoft Dynamics 365. O trabalho exige que as contagens sejam aceitas antes de serem lançadas no estoque.

1. Entre no Dynamics 365 Supply Chain Management.
1. Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.
1. Na guia **Visão geral** , procure as linhas com os seguintes valores:

    - **Tipo de ordem de trabalho:** *Contagem cíclica*
    - **Depósito:** *61*
    - **Status do trabalho:** *Revisão pendente*

    Duas IDs de trabalho devem ter sido criadas para essas linhas. As contagens para essas duas IDs de trabalho devem ser aceitas.

1. Na grade, selecione a primeira ID de trabalho para o tipo de ordem de trabalho *Contagem Cíclica*.
1. No Painel de Ação, na guia **Trabalho** , no grupo **Trabalho** , selecione **Contagem cíclica**.

    Duas linhas são mostradas, uma para cada item e placa de licença. Os valores nos campos **Quantidade contada** , **Localização** , **Placa de licença** e **Item** devem coincidir com as entradas de contagem criadas no dispositivo móvel. Se algum desses campos não estiver visível, selecione **Exibir dimensões** no Painel de Ação para adicioná-los à grade.

1. Selecione as duas linhas.
1. No Painel de Ação, selecione **Aceitar contagem**.
1. Você receberá uma mensagem "Lançamento - Diário". Selecione **Detalhes da mensagem** para exibir o número de diário lançado.
1. Feche os detalhes da mensagem.
1. Atualize a página **Trabalho**.

    A primeira ID de trabalho foi fechada e não é mais mostrada.

    > [!TIP]
    > Para ver o trabalho fechado, marque a caixa de seleção **Mostrar fechado** acima da grade.

    Agora você aceitará o trabalho referente à placa de licença na localização *01A01R1S2B*.

1. Na guia **Visão geral** , selecione a segunda ID de trabalho para o tipo de ordem de trabalho *Contagem Cíclica*.
1. No Painel de Ação, na guia **Trabalho** , no grupo **Trabalho** , selecione **Contagem cíclica**.

    É mostrada uma linha relativa ao item e à placa de licença. Os valores nos campos **Quantidade contada** , **Localização** , **Placa de licença** e **Item** devem coincidir com as entradas de contagem criadas no dispositivo móvel.

1. Selecione a linha.
1. No Painel de Ação, selecione **Aceitar contagem**.
1. Você receberá uma mensagem "Lançamento - Diário". Selecione **Detalhes da mensagem** para exibir o número de diário lançado.
1. Feche os detalhes da mensagem.
1. Atualize a página **Trabalho**.

    A segunda ID de trabalho foi fechada e não é mais mostrada.

    > [!TIP]
    > Para ver o trabalho fechado, marque a caixa de seleção **Mostrar fechado** acima da grade.

#### <a name="on-hand-by-location"></a>Disponibilidade por localização

1. Vá para **Gerenciamento de depósito \> Consultas e relatórios \> Disponível por local**.
1. Defina os seguintes valores:

    - **Local:** *6*
    - **Depósito:** *61*
    - **Atualizar entre localizações:** *Sim*

1. Observe que a localização *01A01R1S1B* tem duas placas de licença:

    - **A0001** , na qual o campo **Posição da LP** está definido como *1*
    - **A0002** , na qual o campo **Posição da LP** está definido como *2*

1. Observe que a localização *01A01R1S2B* tem uma placa de licença:

    - **A0002** , na qual o campo **Posição da LP** está definido como *1*

### <a name="sales-order-scenario"></a>Cenário de ordem de venda

Agora que o recurso *Posicionamento da placa de licença de localização* foi configurado e o estoque foi preparado, você deve criar uma ordem de venda para gerar um trabalho de separação que orientará o trabalhador do depósito a separar o item *A0002* da localização de estoque em que a ID do palete está na posição *1*.

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda** , defina os seguintes valores:

    - **Conta de cliente:** *US-004*
    - **Depósito:** *61*

1. Selecione **OK**.
1. Uma nova linha é adicionada à grade na FastTab **Linhas de ordem de venda**. Nessa nova linha, defina os seguintes valores:

    - **Número de item:** *A0002*
    - **Quantidade:** *1*

1. No menu **Estoque** acima da grade, selecione **Reserva**.
1. na página **Reserva** , no Painel de Ação, selecione **Reservar lote** para reservar estoque para a linha da ordem.
1. Feche a página **Reserva**.
1. No Painel de Ação, na guia **Depósito** , no grupo **Ações** , selecione **Liberar para o depósito**.

    Você receberá uma mensagem informativa que indica a ID da onda e a ID de remessa criadas para a ordem.

1. Na FastTab **Linhas de ordem de venda** , no menu **Depósito** acima da grade, selecione **Detalhes do trabalho**.
1. A página **Trabalho** é exibida e mostra o trabalho que foi criado para a linha de venda. Anote a ID de trabalho mostrada.

### <a name="sales-picking-scenario"></a>Cenário de separação de venda

1. Abra o aplicativo móvel e entre no depósito *61*.
1. Vá para **Saída \> Separação de venda**.
1. Na página **Digitalizar uma ID de trabalho/ID de placa de licença** , selecione o campo **ID** e insira a ID de trabalho na linha de venda.
1. Observe que o trabalho de separação leva você a selecionar o item *A0002* da localização *01A01R1S2B*. Você recebe essa instrução porque o item *A0002* está em uma placa de licença na posição *1* dessa localização.

    ![Localização da posição 1](media/LocationLicensePlatePositioning.png "Localização da posição 1")

1. Insira a ID da placa de licença que você criou para a localização e siga os prompts para separar a ordem de venda.
