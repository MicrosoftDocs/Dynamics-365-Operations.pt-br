---
title: "Mostrar notificações de ordem no ponto de venda"
description: "Este tópico descreve como habilitar notificações de ordem no ponto de venda e a estrutura de notificação. Com o tempo, os desenvolvedores poderão estender essas notificações a operações além das operações de atendimento da ordem."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 03/13/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailOperations, RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: ShalabhjainMSFT
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 0d409b3b7f19ca31d9c720bca191f1ddba81caa3
ms.openlocfilehash: a55af4c26d74cc392d3c53aacb66e0a8bc97abf2
ms.contentlocale: pt-br
ms.lasthandoff: 03/13/2018

---

# <a name="show-order-notifications-in-the-point-of-sale"></a>Mostrar notificações de ordem no ponto de venda

[!include [banner](includes/banner.md)]

No ambiente de varejo moderno, são atribuídas várias tarefas aos associados da loja, como auxiliar os clientes, inserir transações, executar contagens de estoque e receber ordens na loja. O cliente do ponto de venda (PDV) fornece um único aplicativo no qual os associados podem executar todas essas tarefas e muitas outras. Como várias tarefas devem ser executadas durante o dia, os associados talvez precisem ser notificados quando algo exigir sua atenção. A estrutura de notificação no PDV ajuda, permitindo que os varejistas configurem notificações baseadas em funções. No Microsoft Dynamics 365 for Retail com atualização de aplicativo 5, essas notificações podem ser configuradas somente para operações de PDV.

No momento, o sistema pode mostrar notificações somente para operações de atendimento da ordem. No entanto, como a estrutura é criada para ser extensível, os desenvolvedores poderão gravar um manipulador de notificação para qualquer operação e mostrar as notificações para essa operação no PDV.

## <a name="enable-notifications-for-order-fulfillment-operations"></a>Habilitar notificações para operações de atendimento da ordem

Para habilitar as notificações para operações de atendimento da ordem, siga estas etapas.

1. Vá para **Varejo** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Operações**.
2. Procure a operação **Atendimento da ordem** e marque a caixa de seleção **Habilitar notificações** para que ela especifique que a estrutura de notificação deve detectar o manipulador para essa operação. Se o manipulador for implementado, as notificações para essa operação serão mostradas no PDV.
3. Vá para **Varejo** &gt; **Funcionários** &gt; **Trabalhadores** &gt;, na guia Varejo, abra as permissões de PDV associadas ao trabalhador. Expanda a Guia Rápida **Notificações**, adicione a operação **Atendimento da ordem** e defina o campo **Ordem de exibição** como **1**. Se mais de uma notificação for configurada, esse campo será usado para organizar as notificações. As notificações que têm um valor de **Ordem de exibição** mais baixo aparecem acima das notificações que têm um valor mais alto. As notificações em que o valor de **Ordem de exibição** é **1** aparecem na parte superior.

    As notificações são mostradas somente para operações adicionadas na Guia Rápida **Notificações**, e você só poderá adicionar operações lá se a caixa de seleção **Habilitar notificações** para essas operações tiver sido selecionada na página **Operações de PDV**. Além disso, as notificações para uma operação são mostradas aos trabalhadores somente se a operação for adicionada às permissões de PDV para esses trabalhadores.

    > [!NOTE]
    > As notificações podem ser substituídas no nível do usuário. Abra o registro do trabalhador, selecione **Permissões do PDV** e, em seguida, edite a subscrição de notificação do usuário.

4. Vá para **Varejo** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **Perfis de PDV** &gt; **Perfis de funcionalidade**. No campo **Intervalo de notificação**, especifique a frequência de recebimento de notificações. Para algumas notificações, o PDV deve fazer chamadas em tempo real para o aplicativo de back office. Essas chamadas consomem a capacidade de computação do seu aplicativo de back office. Portanto, ao definir o intervalo de notificação, você deve considerar suas necessidades comerciais e o impacto de chamadas em tempo real no aplicativo de back office. Um valor de **0** (zero) desativa as notificações.
5. Vá para **Varejo** &gt; **TI de varejo** &gt; **Agenda de distribuição**. Selecione a agenda **1060** (**Equipe**) para sincronizar as configurações de subscrição de notificação e, em seguida, selecione **Executar agora**. Em seguida, selecione a agenda **1070** (**Configuração do canal**) para sincronizar o intervalo de permissão e, em seguida, selecione **Executar agora**.

## <a name="view-notifications-in-the-pos"></a>Exibir notificações no PDV

Depois que você concluir as etapas anteriores, os trabalhadores poderão exibir as notificações no PDV. Para exibir as notificações, pressione o ícone de notificação no canto superior direito do PDV. Um centro de notificações aparecerá e mostrará as notificações para a operação de atendimento da ordem. O centro de notificações deve mostrar os seguintes grupos na operação de atendimento da ordem:

- **Retirada na loja** – Este grupo mostra a contagem de ordens que têm o modo de entrega **Retirada** e cuja retirada está agendada na loja atual. Você pode pressionar o número no grupo para abrir a página **Atendimento da ordem**. Nesse caso, a página será filtrada para mostrar somente as ordens ativas configuradas para retirada na loja atual.
- **Remeter da loja** – Este grupo mostra a contagem de ordens que têm o modo de entrega **Remessa** e cuja remessa está agendada na loja atual. Você pode pressionar o número no grupo para abrir a página **Atendimento da ordem**. Nesse caso, a página será filtrada para mostrar somente as ordens ativas configuradas para remessa da loja atual.

Quando novas ordens são atribuídas à loja para o atendimento, o ícone de notificação é alterado para indicar que há novas notificações, e a contagem dos grupos apropriados é atualizada. Embora os grupos sejam atualizados em intervalos regulares, os usuários do PDV podem atualizá-los manualmente a qualquer momento selecionando o botão **Atualizar** ao lado do grupo. Por fim, se um grupo tiver um novo item, que o trabalhador atual não viu, então o grupo mostrará um símbolo intermitente para indicar o novo conteúdo.

## <a name="enable-live-content-on-pos-buttons"></a>Habilitar conteúdo ao vivo nos botões do PDV

Os botões do PDV agora podem mostrar uma contagem para ajudar os trabalhadores a determinar facilmente quais tarefas exigem a sua atenção imediata. Para mostrar esse número em um botão do PDV, você deve concluir a configuração de notificação descrita anteriormente neste tópico (isto é, você deve habilitar as notificações para uma operação, configurar um intervalo de notificação e atualizar o grupo de permissões de PDV para o trabalhador). Além disso, você deve abrir o designer da grade de botões, exibir as propriedades do botão e marcar a caixa de seleção **Habilitar conteúdo ao vivo**. No campo **Alinhamento de conteúdo**, você pode selecionar se a contagem será exibida no canto superior direito do botão (**Superior direito**) ou no centro (**Centralizado**).

> [!NOTE]
> O conteúdo ao vivo poderá ser habilitado para operações somente se a caixa de seleção **Habilitar notificações** tiver sido selecionada para elas na página **Operações de PDV**, conforme descrito anteriormente neste tópico.

A ilustração a seguir mostra as configurações de conteúdo ao vivo no designer da grade de botões.

![Configurações de conteúdo ao vivo no designer da grade de botões](./media/ButtonGridDesigner.png "Configurações de conteúdo ao vivo no designer da grade de botões")

A ilustração a seguir mostra o efeito de selecionar **Superior direito** versus **Centralizado** no campo **Alinhamento de conteúdo** para botões de vários tamanhos.

![Conteúdo ao vivo nos botões do PDV](./media/ButtonsWithLiveContent.png "Conteúdo ao vivo nos botões do PDV")

