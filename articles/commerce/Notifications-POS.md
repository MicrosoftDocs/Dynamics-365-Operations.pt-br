---
title: Mostrar notificações de ordem no ponto de venda (PDV)
description: Este tópico descreve como habilitar notificações de ordem no ponto de venda e a estrutura de notificação.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5ea902b5d65f806fc88e688d10bdad9ae75611ef
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585073"
---
# <a name="show-order-notifications-in-the-point-of-sale-pos"></a>Mostrar notificações de ordem no ponto de venda (PDV)

[!include [banner](includes/banner.md)]

Os associados da loja podem receber várias tarefas na loja, como atendimento de ordens ou execução de contagens de estoque ou recebimento de estoque. O cliente do ponto de venda (PDV) fornece um único aplicativo no qual os associados podem ser notificados dessas tarefas. A estrutura de notificação no PDV ajuda, permitindo que os varejistas configurem notificações baseadas em funções. Começando no Dynamics 365 Retail com a atualização do aplicativo 5, essas notificações podem ser configuradas somente para operações de PDV.

O sistema pode mostrar notificações para a operação *atendimento da ordem* e começando nas notificações da versão 10.0.18 do Commerce também podem ser mostradas para a operação *Cancelar ordem*. No entanto, como a estrutura é criada para ser extensível, os desenvolvedores poderão [gravar um manipulador de notificação](dev-itpro/extend-pos-notification.md) para qualquer operação e mostrar as notificações para essa operação no PDV.

## <a name="enable-notifications-for-order-fulfillment-or-recall-order-operations"></a>Habilitar notificações para operações de atendimento da ordem ou para cancelar a ordem

Para habilitar notificações para as operações de atendimento da ordem ou para cancelar a ordem, consulte as seguintes etapas:

1. Vá para **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> PDV \> Operações**.
1. Procure a operação **Atendimento da ordem** ou **Cancelar ordem** e selecione **Habilitar notificações** para que a operação especifique que a estrutura de notificação deve detectar o manipulador para essa operação. Se o manipulador for implementado, as notificações para essa operação serão mostradas no PDV.
1. Vá para **Varejo e Comércio \> Funcionários \> Trabalhadores**.
1. Selecione a guia **Commerce**, selecione uma linha de trabalhador e, em seguida, selecione **Permissões de PDV**. Selecione a guia rápida **Notificações** para expandi-la e adicione as operações para as quais você habilitou notificações. Se estiver configurando uma única notificação para um trabalhador, verifique se o valor **Ordem de exibição** está definido como **1**. Se estiver configurando mais de uma operação, defina os valores da **Ordem de exibição** para indicar a ordem em que as notificações devem ser exibidas. 

      As notificações são mostradas somente para as operações adicionadas na guia rápida **Notificações**. Você só poderá adicionar operações ali se as caixas de seleção **Habilitar notificações** para essas operações tiverem sido selecionadas na página **Operações de PDV**. Além disso, as notificações para uma operação são mostradas aos trabalhadores somente se a operação for adicionada às permissões de PDV para esses trabalhadores.

    > [!NOTE]
    > As notificações podem ser substituídas no nível do usuário. Para fazer isso, abra o registro do trabalhador, selecione **Permissões do PDV** e, em seguida, edite a subscrição de notificação do usuário.

1. Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**. No campo **Intervalo de notificação**, especifique a frequência de recebimento de notificações. Para algumas notificações, o PDV deve fazer chamadas em tempo real para o aplicativo de back office. Essas chamadas consomem a capacidade de computação do seu aplicativo de back office. Portanto, ao definir o intervalo de notificação, você deve considerar suas necessidades comerciais e o impacto de chamadas em tempo real no aplicativo de back office. Um valor de **0** (zero) desativa as notificações.
1. Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**. Selecione a agenda **1060** (**Equipe**) para sincronizar as configurações de subscrição de notificação e, em seguida, selecione **Executar agora**. Em seguida, selecione a agenda **1070** (**Configuração do canal**) para sincronizar o intervalo de permissão e, em seguida, selecione **Executar agora**.

## <a name="view-notifications-in-the-pos"></a>Exibir notificações no PDV

Depois que você concluir as etapas anteriores, os trabalhadores poderão exibir as notificações no PDV. Para exibir as notificações, selecione o ícone de notificação no canto superior direito do PDV. Um painel de notificação aparece e mostra notificações para as operações configuradas para o trabalhador. 

Par a operação de **atendimento da ordem**, o painel de notificação mostrará os seguintes grupos:

- **Retirada na loja** – Este grupo mostra a contagem de linhas de ordem individuais que são agendadas para retirada na loja atual. Você pode selecionar o número no grupo para abrir a operação de **Atendimento da ordem** com um filtro para que mostre somente as linhas de ordem ativas que são configuradas para retirada da loja atual.
- **Remeter da loja** – esse grupo mostra o número de linhas de ordem individuais que foram configuradas para remeterem da loja atual do usuário. Você pode selecionar o número no grupo para abrir a operação de **Atendimento da ordem** com uma exibição filtrada que mostre somente as linhas de ordem ativas que são configuradas para retirada da loja atual.

Para a operação **cancelar ordem**, o painel de notificação mostrará os seguintes grupos:

- **Ordens a serem atendidas** – esse grupo mostra o número de ordens configuradas para a entrega ou a remessa para a loja atual do usuário. Você pode selecionar o número no grupo para abrir a operação **Cancelar ordem** com uma exibição filtrada que mostra somente as ordens abertas que precisam ser preenchidas pela loja atual do usuário para cenários de retirar na loja ou remeter da loja.
- **Ordens a serem retiradas** – este grupo mostra a contagem ordens que são agendadas para retirada na loja atual. Você pode selecionar o número no grupo para abrir a operação **Cancelar ordem** com uma exibição filtrada que mostra somente as ordens abertas que precisam ser atendidas para retirada pelo cliente na loja atual do usuário.
- **Ordens a serem remetidas** – este grupo mostra o número de ordens a serem remetidas da loja atual do usuário. Você pode selecionar o número no grupo para abrir a operação **Cancelar ordem** com uma exibição filtrada que mostra somente as ordens abertas que precisam ser atendidas para remessa pelo cliente na loja atual do usuário.

Para as notificações de atendimento da ordem e cancelamento da ordem, conforme novas ordens são selecionadas pelo processo, o ícone de notificação é alterado para indicar que há novas notificações, e a contagem dos grupos apropriados é atualizada. Embora os grupos sejam atualizados em intervalos regulares, os usuários do PDV podem atualizá-los manualmente a qualquer momento selecionando o botão **Atualizar** ao lado do grupo. Por fim, se um grupo tiver um novo item, que o trabalhador atual não viu, então o grupo mostrará um símbolo intermitente para indicar o novo conteúdo.

## <a name="enable-live-content-on-pos-buttons"></a>Habilitar conteúdo ao vivo nos botões do PDV

Os botões do PDV agora podem mostrar uma contagem para ajudar os trabalhadores a determinar facilmente quais tarefas exigem a sua atenção imediata. Para mostrar esse número em um botão do PDV, você deve concluir a configuração de notificação descrita anteriormente neste tópico (isto é, você deve habilitar as notificações para uma operação, configurar um intervalo de notificação e atualizar o grupo de permissões de PDV para o trabalhador). Além disso, você deve abrir o designer da grade de botões, exibir as propriedades do botão e marcar a caixa de seleção **Habilitar conteúdo ao vivo**. No campo **Alinhamento de conteúdo**, você pode selecionar se a contagem será exibida no canto superior direito do botão (**Superior direito**) ou no centro (**Centralizado**).

> [!NOTE]
> O conteúdo ao vivo poderá ser habilitado para operações somente se a caixa de seleção **Habilitar notificações** tiver sido selecionada para elas na página **Operações de PDV**, conforme descrito anteriormente neste tópico.

A ilustração a seguir mostra as configurações de conteúdo ao vivo no designer da grade de botões.

![Configurações de conteúdo dinâmico no designer de grade de botões](./media/ButtonGridDesigner.png "Configurações de conteúdo dinâmico no designer de grade de botões")

Para mostrar a contagem de notificação em um botão, você deve garantir que o layout de tela correto está sendo atualizado. Para determinar o layout de tela que está sendo usado pelo POS, selecione o ícone **Configurações** no canto superior direito e anote a **ID de layout de tela** e **Resolução de tela**. Agora, usando o navegador Microsoft Edge, acesse a página **Layout da tela**, encontre a **ID do layout da tela** e a **Resolução do layout** identificadas acima e marque a caixa de seleção **Habilitar conteúdo ativo**. Vá para **Retail e Commerce \> TI de Retail e Commerce \> Agenda de distribuição** e execute o trabalho 1090 (Registros) para sincronizar as alterações de layout.

![Localizar o layout de tela usado pelo PDV](./media/Choose_screen_layout.png "Localizar o layout de tela")

A ilustração a seguir mostra o efeito de selecionar **Superior direito** versus **Centralizado** no campo **Alinhamento de conteúdo** para botões de vários tamanhos.

![Conteúdo dinâmico nos botões do PDV](./media/ButtonsWithLiveContent.png "Conteúdo dinâmico nos botões do PDV")

[!INCLUDE[footer-include](../includes/footer-banner.md)]
