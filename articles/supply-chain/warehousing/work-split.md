---
title: Divisão do trabalho
description: Este tópico fornece informações sobre a funcionalidade de divisão do trabalho. Essa funcionalidade permite dividir grandes ordens de serviço em várias ordens de serviço menores que você pode atribuir a vários funcionários do depósito. Dessa forma, o mesmo trabalho pode ser separado simultaneamente por vários funcionários do depósito.
author: mirzaab
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: e3f14dd25a60f8d185f0e58a0612a322c5175ab2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579871"
---
# <a name="work-split"></a>Divisão do trabalho

[!include [banner](../includes/banner.md)]

A funcionalidade de divisão do trabalho permite dividir grandes IDs de trabalho (ou seja, ordens de serviço que têm várias linhas) em várias IDs de trabalho menores que você pode atribuir a vários funcionários do depósito. Dessa forma, o mesmo número de criação de trabalho pode ser selecionado simultaneamente por vários funcionários do depósito.

> [!IMPORTANT]
> Você pode dividir apenas as ordens de serviço que têm um status de *Aberto* ou *Em andamento*.

## <a name="turn-on-the-work-split-functionality"></a>Ativar a funcionalidade de divisão do trabalho

Antes de usar a funcionalidade de divisão do trabalho, você deve ativar o recurso e seu recurso de pré-requisito em seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status dos recursos e ativá-los se necessário.

Primeiro, ative o recurso de pré-requisito *Bloqueio de trabalho em toda a organização* se ainda não estiver ativado. No espaço de trabalho **Gerenciamento de recursos**, este recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Bloqueio de trabalho em toda a organização*

> [!NOTE]
> Quando esse recurso é ativado, uma atualização de dados é aplicada automaticamente depois que o recurso é ativado em todas as entidades legais.

Em seguida, ative o recurso *Divisão do trabalho*, que está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Divisão do trabalho*

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a>Aprimoramentos dos detalhes de trabalho e todas as páginas de trabalho

O recurso *Divisão do trabalho* adiciona os dois botões a seguir à guia **Trabalho** no Painel de ações das páginas **Detalhes do trabalho** e **Todos os trabalhos**:

- **Divisão do trabalho** – Divida a ID de trabalho atual em várias IDs menores do trabalho que podem ser processadas por funcionários separados.
- **Cancelar sessão de divisão do trabalho** – Cancele a sessão de divisão do trabalho e disponibilize o trabalho para processamento.

![Botões Divisão do trabalho e Cancelar sessão de divisão do trabalho.](media/Work_split_buttons.png "Botões Divisão do trabalho e Cancelar sessão de divisão do trabalho")

> [!IMPORTANT]
> O botão **Divisão do trabalho** não estará disponível se qualquer uma das seguintes condições for atendida:
>
> - O status do trabalho é diferente de *Aberto* ou *Em andamento*.
> - Uma ID de contêiner está associada à ID de trabalho. (Um contêiner não pode ser sistematicamente dividido, porque requer ações físicas.)
> - O trabalho está associado a um cluster.
> - O tipo de ordem de serviço é diferente de um dos seguintes tipos:
>
>    - Ordens de Venda
>    - Separação de matéria-prima
>    - Transferir saída
>
> - O trabalho está sendo dividido por outro usuário. Se você tentar abrir a página de divisão de um trabalho que já está sendo dividido por outro usuário, receberá a seguinte mensagem de erro: "O trabalho com ID \#\#\#\# está sendo dividido no momento. Tente novamente em alguns minutos. Se continuar a receber esta mensagem, entre em contato com um supervisor."

Um novo motivo de bloqueio do trabalho, *Divisão do trabalho*, indica quando a ID de trabalho está em processo de divisão. É mostrado na página **Divisão do trabalho** e no aplicativo móvel Gerenciamento de Depósito se um usuário tentar executar o trabalho. Quando motivos de bloqueio são usados, o nome do campo **Ciclo bloqueado** da ID de trabalho é alterado para **Bloqueado**.

## <a name="initiate-a-work-split"></a>Iniciar uma divisão de trabalho

O recurso adiciona uma nova página **Divisão do trabalho** que permite aos usuários dividir as linhas de trabalho a partir da ID de trabalho. Quando a página é aberta pela primeira vez, mostra as linhas que têm um status de trabalho de *Aberto* e que estão disponíveis para serem divididas. No Painel de ações, selecione **Divisão do trabalho** para processar o trabalho selecionado.

Para dividir o trabalho, siga as etapas a seguir.

1. Abra uma das seguintes páginas de trabalho:

    - **Detalhes do trabalho** (**Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**)
    - **Todos os trabalhos** (**Gerenciamento de depósito \> Trabalho \> Todos os trabalhos**)

1. Na grade, selecione uma ID de trabalho a ser dividida. O campo **Tipo de ordem de serviço** deve ser definido com um dos seguintes valores:

    - Ordens de Venda
    - Separação de matéria-prima
    - Transferir saída

1. No Painel de Ação, na guia **Trabalho**, no grupo **Trabalho**, selecione **Divisão do trabalho**.

    A página **Divisão do trabalho** aparece e mostra as linhas de trabalho que estão abertas e disponíveis para serem divididas. Por padrão, apenas as linhas de trabalho disponíveis são mostradas. Para exibir todas as linhas da ID de trabalho (por exemplo, linhas que têm um tipo de trabalho de *Colocar*), marque a caixa de seleção **Mostrar todas as linhas** acima da grade.

    A seguinte mensagem é mostrada: "Os usuários não podem processar linhas de trabalho até que você termine a divisão e feche esta página."

    O campo **Motivo de bloqueio de trabalho** do trabalho atual será definido como *Divisão do trabalho* e o trabalho será bloqueado.

    ![Motivo do bloqueio.](media/Blocking_reason.png "Motivo do bloqueio")

1. Selecione as linhas a serem removidas da ID de trabalho atual e adicionadas a uma nova ID de trabalho. Os seguintes eventos ocorrem:

    - Quando você divide o trabalho, as linhas selecionadas da ID de trabalho original são canceladas e, depois, copiadas em uma nova ID de trabalho.
    - A estrutura do modelo de trabalho existente e a localização da opção Colocar (e também futuros pares de retirada/ colocação) são preservados. Os valores para os seguintes campos de ID de trabalho são copiados do trabalho original para o novo trabalho:

        - ID da Carga
        - ID da Remessa
        - Tipo de ordem de serviço
        - Número da ordem
        - Site
        - Depósito
        - Prioridade de trabalho
        - ID do pool de trabalho
        - ID da Onda
        - Número de criação do trabalho

    - Os seguintes campos não são copiados para a nova ID de trabalho:

        - **ID de trabalho** – Uma nova ID de trabalho é gerada a partir da sequência numérica apropriada.
        - **Status do trabalho** – Este campo está definido como *Aberto*.
        - **Bloqueado por** – Este campo é inicialmente definido como em branco.
        - **ID da placa de licença de destino** – Este campo é deixado em branco.
        - **Data e hora de criação** – Este campo é definido para a data e hora atuais.
        - **Ciclo bloqueado/congelado** – Este campo é recalculado para a ID do trabalho original e a nova ID do trabalho.

1. No Painel de Ação, selecione **Divisão do trabalho**.

Enquanto o trabalho está sendo dividido, a seguinte mensagem é exibida: "Operação de processamento - Divisão do trabalho". Enquanto essa mensagem estiver visível, você pode cancelar a operação selecionando **Cancelar** na caixa de mensagem.

Se a caixa de seleção **Mostrar todas as linhas** estiver desmarcada, a linha que foi dividida e cancelada não aparecerá mais na grade. Se a caixa de seleção estiver selecionada, você verá que o valor do campo **Status do trabalho** dessa linha foi alterado para *Cancelado*.

A seguinte notificação é mostrada para indicar que a nova ID de trabalho foi criada: "O trabalho \#\#\#\# foi criado pela divisão do trabalho original \#\#\#\#."

Outras linhas de trabalho da ID de trabalho original (como *Colocar* linhas) serão ajustadas conforme necessário para refletir as linhas de trabalho que foram canceladas. Por exemplo, se a ID do trabalho original tem uma linha *Colocar* para uma quantidade de 15 e as linhas *Separar* com uma quantidade total de 10 foram canceladas, a nova quantidade *Colocar* na ID de trabalho original agora será são 5.

O novo trabalho não será atribuído imediatamente a nenhum usuário. Contudo, você pode atribuí-lo a um usuário agora, conforme necessário, usando a funcionalidade padrão da página **Detalhes do trabalho**.

> [!IMPORTANT]
> É possível dividir apenas IDs de trabalho que contenham duas ou mais linhas de trabalho disponíveis. Se você selecionar **Divisão do trabalho** quando houver apenas uma linha de trabalho, receberá a seguinte mensagem de erro: "Pelo menos uma linha de trabalho deve permanecer no trabalho inicial." Nesse caso, nenhuma divisão ocorrerá.

## <a name="finish-a-work-split"></a>Concluir uma divisão de trabalho

Para terminar o trabalho de divisão, o motivo de bloqueio *Divisão do trabalho* deve ser removido. Existem duas maneiras de concluir esta etapa:

- O usuário que está dividindo o trabalho fecha a página **Divisão do trabalho** selecionando o botão **Fechar** (**X**) no canto superior direito. Quando a página for fechada, o motivo de bloqueio *Divisão do trabalho* será removido. O estado *Bloqueado* do trabalho será recalculado e, se não houver motivos de bloqueio restantes, ele será desbloqueado.
- Qualquer usuário abre a ID de trabalho e seleciona o botão **Cancelar sessão de divisão do trabalho** no Painel de ações. O motivo de bloqueio *Divisão do trabalho* será removido e o estado *Bloqueado* desse trabalho será recalculado, assim como quando a página **Divisão do trabalho** for fechada.

Após a remoção do motivo de bloqueio *Divisão do trabalho*, o trabalho pode ser executado no dispositivo móvel, desde que o estado **Bloqueado** seja definido como *Não* na ID de trabalho.

## <a name="user-blocking-on-the-warehouse-management-mobile-app"></a>Bloqueio de usuário no aplicativo móvel Gerenciamento de Depósito

Se você tentar usar o aplicativo móvel Gerenciamento de Depósito para executar o trabalho de separação em uma ID de trabalho que está sendo dividida, receberá a seguinte mensagem de erro: "O trabalho com a ID \#\#\#\# está sendo dividido no momento." Se você receber essa mensagem, selecione **Cancelar**. É possível continuar a processar outro trabalho.

## <a name="other-blocked-operations"></a>Outras operações bloqueadas

Qualquer operação que modifique linhas de trabalho, transações de estoque de trabalho ou links de reabastecimento relacionados ao trabalho que está sendo dividido falhará e a seguinte mensagem de erro será exibida: "O trabalho com ID \#\#\#\# está sendo dividido."


[!INCLUDE[footer-include](../../includes/footer-banner.md)]