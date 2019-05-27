---
title: Visão geral do gerenciamento de recursos
description: Este tópico descreve o recurso de gerenciamento de recursos e como você pode usá-lo.
author: mikefalkner
manager: AnnBe
ms.date: 04/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: e75e42926db22d4fccda86c755b12d9d121a9c0e
ms.sourcegitcommit: be447fc81bc874982bc0185fcb4d87d99bd742c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538673"
---
# <a name="feature-management-overview"></a>Visão geral do gerenciamento de recursos

[!include[banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Os recursos são adicionados e atualizados em cada versão do Microsoft Dynamics 365 for Finance and Operations. A experiência de gerenciamento de recursos fornece um espaço de trabalho em que você pode exibir uma lista dos recursos que foram entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles.

## <a name="the-feature-management-workspace"></a>O espaço de trabalho do gerenciamento de recursos

Você pode abrir o espaço de trabalho **Gerenciamento de recursos** selecionando o bloco apropriado no painel. Você verá uma página que mostra uma lista de recursos para todas as versões com suporte na experiência de gerenciamento de recursos. Com o tempo, a Microsoft aprimorará a experiência de gerenciamento de recursos para que ela inclua funcionalidade adicional para ajudar a gerenciar recursos.

A lista recursos inclui as seguintes informações:

- **Nome do recurso** — uma descrição do recurso que foi adicionado.
- **Status habilitado** — um símbolo indica se um determinado recurso foi habilitado (marca de seleção), se não foi habilitado (em branco), se foi agendado para ser habilitado (relógio), ou se foi habilitado obrigatoriamente (cadeado). A configuração exibida aqui é usada para todas as entidades legais. Observe que, mesmo quando um recurso for ativado, ele ainda será controlado pela segurança. Portanto, o recurso estará disponível somente os para usuários que tiverem acesso a ele, com base em sua função de segurança. Ele também estará disponível somente para entidades legais às quais o usuário tem acesso.
- **Data da habilitação** — a data em que o recurso foi ativado ou será ativado se a data for uma data futura.
- **Recurso adicionado** — a data em que o recurso foi adicionado ao ambiente. Essa data é inserida automaticamente quando você atualiza seu ambiente durante ciclos mensais de lançamento.
- **Módulo** — o módulo que é afetado pelo novo recurso.

Ao selecionar um recurso, informações adicionais serão exibidas no painel de detalhes à direita da lista de recursos. Na parte superior do painel, você verá o nome do recurso, a data em que o recurso foi adicionado, o módulo que é afetado pelo recurso e um link **Saiba mais**. Selecione esse link para exibir a documentação do recurso. Se a documentação não estiver disponível, você será levado a uma página temporária. O painel de detalhes também inclui um campo **Comentários**, onde você pode adicionar seus próprios comentários sobre o recurso.

O espaço de trabalho **Gerenciamento de recursos** também contém várias guias com uma lista de recursos nele. 
- **Novo** — mostra todos os recursos que já foram adicionados desde a última atualização mensal. Se você ignorou alguma atualização mensal, ela conterá todos os novos recursos desde a última vez que você atualizou. Os recursos mais novos aparecem na parte superior da lista. O número total de novos recursos também é mostrado em um bloco na parte superior da página.
- **Não habilitado** — mostra todos os recursos que não foram ativados. Os recursos mais novos aparecem na parte superior da lista. O número total de novos recursos também é mostrado em um bloco na parte superior da página.
- **Agendado** — mostra todos recursos que foram agendados para serem habilitados em uma data futura. Os recursos com a data mais próxima agendada aparecerão na parte superior da lista. O número total de novos recursos também é mostrado em um bloco na parte superior da página.
- **Tudo** — mostra todos os recursos. Os recursos mais novos aparecem na parte superior da lista.


## <a name="enable-a-feature"></a>Habilitar um recurso

Se um determinado recurso não estiver habilitado, um botão **Habilitar** será exibido no painel de detalhes. Você poderá usar esse botão para habilitar o recurso.

1. Selecione o recurso que deseja habilitar e, no painel de detalhes, selecione **Habilitar**.
2. Um controle deslizante será exibido, em que você poderá especificar a data em que o recurso deve ser habilitado. Por padrão, essa data é definida como a data atual.
3. Selecione **Habilitar** para habilitar o recurso.

Alguns recursos não poderão ser desabilitados depois que forem habilitados. Se o recurso que estiver tentando habilitar não puder ser desabilitado, você receberá um aviso. Nesse ponto, você poderá selecionar **Cancelar** para cancelar a operação e deixar o recurso desabilitado. No entanto, se você selecionar **Habilitar** e habilitar o recurso, ele não poderá ser desabilitado posteriormente.

Depois que o recurso for habilitado, uma mensagem será exibida abaixo do link **Saiba mais** no painel de detalhes. Essa mensagem informa que o recurso foi habilitado ou indica quando o recurso será habilitado no futuro. Se você usar uma data futura, o recurso será exibido na lista **Agendado** . Essa mensagem será exibida sempre que você selecionar o recurso na lista de recursos. Os recursos que estão agendados para o futuro serão habilitados à meia-noite por um processo em lotes baseado no fuso horário representado na data do sistema. 

## <a name="reschedule-a-feature"></a>Reagendar um recurso

Se um recurso for habilitado no futuro, um botão **Reagendar** será exibido no painel de detalhes. Você poderá usar este botão para alterar a **Data da habilitação** para uma data diferente.

1. Selecione o recurso agendado que deseja reagendar e, no painel de detalhes, selecione **Reagendar**.
2. Um controle deslizante será exibido, em que você poderá especificar a data em que o recurso deve ser habilitado. 
3. Selecione **Habilitar** para reagendar o recurso ou **Desabilitar** para cancelar o agendamento.

## <a name="disable-a-feature"></a>Desabilitar um recurso

Se um recurso não já tiver sido habilitado, um botão **Desabilitar** será exibido no painel de detalhes. Você poderá usar esse botão para desabilitar o recurso. O botão **Desabilitar** não estará disponível se o recurso não puder ser desabilitado depois que tiver sido habilitado.

- Selecione o recurso que deseja desativar e, no painel de detalhes, selecione **Desabilitar**.

- O recurso será desabilitado e a data será removida.

Depois que o recurso for desabilitado, uma mensagem será exibida abaixo do link **Saiba mais** no painel de detalhes. Essa mensagem informa que o recurso ainda não foi habilitada e ele será exibido na lista **Não habilitado** . A mensagem será exibida sempre que você selecionar o recurso na lista de recursos.

## <a name="features-that-must-be-enabled"></a>Recursos que devem ser habilitados

Um recurso crítico que deve ser habilitado automaticamente pode ser entregue quando você faz uma atualização. Ele será habilitado automaticamente na **Data da habilitação**. Uma mensagem será exibida abaixo do link **Saiba mais** no painel de detalhes. Essa mensagem informa que o recurso foi habilitado ou será habilitado automaticamente na **Data da habilitação**. Ela será exibida sempre que você selecionar o recurso na lista de recursos.

## <a name="assigning-roles"></a>Atribuindo funções

O espaço de trabalho **Gerenciamento de recursos** pode ser aberto pelos administradores de sistema e pelos usuários atribuídos às funções de Gerente de recursos ou Visualizador de recursos, que foram criadas para oferecer suporte à experiência de gerenciamento de recursos. Os usuários na função de gerente o recursos poderá ativar ou desativar qualquer de recurso. Eles também poderão atualizar a seção de comentários do recurso. Os usuários na função de visualizador de recursos podem somente exibir o espaço de trabalho **Gerenciamento de recursos**. Eles não poderão ativar ou desativar recursos.

A função de gerente de recursos e a função de visualizador de recurso não substituem a segurança existente que um usuário tem. As funções somente controlam o acesso para a habilitação de recursos. Elas não fornecem acesso aos recursos em si.

## <a name="using-feature-management-to-enable-isv-features-or-custom-features"></a>Usando o gerenciamento de recursos para habilitar recursos de ISV ou recursos personalizados

O processo de gerenciamento de recursos está indisponível no momento para recursos de ISV ou recursos personalizados. Estamos adicionando funcionalidade adicional para aprimorar o gerenciamento de recursos e, quando esses aprimoramentos forem concluídos, abriremos o gerenciamento de recursos para todos os recursos e forneceremos instruções específicas sobre como atualizar o recurso para usá-lo.

## <a name="feature-management-and-flighting"></a>Gerenciamento recursos e liberação de versões

O gerenciamento de recursos permite que você controle os recursos que são enviados em cada versão. A liberação de versões permite que as equipes da Microsoft liberem recursos para um número limitado de clientes, de maneira que os recursos possam ser testados e validados sem afetar todos os clientes. O gerenciamento de recursos não controla a liberação de versões dos recursos.
