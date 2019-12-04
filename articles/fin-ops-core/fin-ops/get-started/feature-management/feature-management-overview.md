---
title: Visão geral do gerenciamento de recursos
description: Este tópico descreve o recurso de gerenciamento de recursos e como você pode usá-lo.
author: mikefalkner
manager: AnnBe
ms.date: 09/12/2019
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
ms.openlocfilehash: a9be51c4a5cdadd968de160dc0b1406c95382eeb
ms.sourcegitcommit: 260a820038c29f712e8f1483cca9315b6dd3df55
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "2778696"
---
# <a name="feature-management-overview"></a>Visão geral do gerenciamento de recursos

[!include [banner](../../includes/banner.md)]

Os recursos são adicionados e atualizados em cada versão. A experiência de gerenciamento de recursos fornece um espaço de trabalho em que você pode exibir uma lista dos recursos que foram entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles.

## <a name="the-feature-management-workspace"></a>O espaço de trabalho do gerenciamento de recursos

Você pode abrir o espaço de trabalho **Gerenciamento de recursos** selecionando o bloco apropriado no painel. Você verá uma página que mostra uma lista de recursos para todas as versões com suporte na experiência de gerenciamento de recursos. Com o tempo, a Microsoft aprimorará a experiência de gerenciamento de recursos para que ela inclua funcionalidade adicional para ajudar a gerenciar recursos.

A lista recursos inclui as seguintes informações:

- **Nome do recurso** — uma descrição do recurso que foi adicionado.
- **Status habilitado** — Um símbolo indica se uma função foi ativada (marca de seleção), se não foi ativada (em branco), se está agendada para ser ativada (relógio), se está obrigatoriamente ativada (bloqueio), exige atenção antes de ser ativada (aviso) ou se não pode ser ativada (X). A configuração exibida é usada para todas as entidades legais. Observe que, mesmo quando um recurso for ativado, ele ainda será controlado pela segurança. Portanto, o recurso estará disponível somente os para usuários que tiverem acesso a ele, com base em sua função de segurança. Ele também estará disponível somente em entidades legais às quais o usuário tem acesso.
- **Data da habilitação** – A data em que o recurso foi ativado ou está agendado para ser ativado.
- **Recurso adicionado** — a data em que o recurso foi adicionado ao ambiente. Essa data é inserida automaticamente quando você atualiza seu ambiente durante ciclos mensais de lançamento.
- **Módulo** — o módulo que é afetado pelo novo recurso.

Ao selecionar um recurso, informações adicionais serão exibidas no painel de detalhes à direita da lista de recursos. Na parte superior do painel, você verá o nome do recurso, a data em que o recurso foi adicionado, o módulo que é afetado pelo recurso e um link **Saiba mais**. Selecione esse link para exibir a documentação do recurso. Se a documentação não estiver disponível, você será levado a uma página temporária. O painel de detalhes também inclui um campo **Comentários**, onde você pode adicionar seus próprios comentários sobre o recurso.

O espaço de trabalho **Gerenciamento de recursos** também possui várias guias, cada uma mostrando uma lista de recursos.

- **Novo** – Esta guia mostra todos os recursos que foram adicionados desde a última atualização mensal. Se você tiver ignorado todas as atualizações mensais, a guia mostrará todos os novos recursos que foram adicionados desde a última atualização. Os recursos mais novos aparecem na parte superior da lista. O número total de novos recursos também é mostrado em um bloco na parte superior da página.
- **Não habilitado** – Esta guia mostra todos os recursos que não foram ativados. Os recursos mais novos aparecem na parte superior da lista. O número total de novos recursos que não foram ativados também é mostrado em um bloco na parte superior da página.
- **Agendado** – Esta guia mostra todos os recursos que foram programados para serem ativados no futuro. Os recursos com a data mais próxima agendada aparecerão na parte superior da lista. O número total de novos recursos da agenda também é mostrado em um bloco na parte superior da página.
- **Tudo** – Esta guia mostra todos os recursos. Os recursos mais novos aparecem na parte superior da lista.

## <a name="turn-on-a-feature"></a>Ativar um recurso

Se um recurso não foi ativado, um botão **Habilitar agora** será exibido no painel de detalhes. Você pode usar esse botão para ativar o recurso.

- Selecione o recurso para ativar e, no painel de detalhes, selecione **Habilitar agora**. O recurso está ativado.

Alguns recursos não podem ser desativados depois que você os liga. Se o recurso que você está tentando ativar não puder ser desativado, você receberá um aviso. Nesse ponto, você poderá selecionar **Cancelar** para cancelar a operação e deixar o recurso desativado. No entanto, se você selecionar **Habilitar** para ativar o recurso, você não poderá desativá-lo mais tarde.

Alguns recursos exibirão uma mensagem que fornece informações adicionais antes de você ativá-los. Esses recursos são indicados por um símbolo de aviso amarelo. Você deve ler as informações adicionais cuidadosamente para compreender melhor o que acontecerá quando o recurso for habilitado. Entretanto, você ainda poderá selecionar **Habilitar** para ativar o recurso.

Alguns recursos exibirão uma mensagem de que o recurso não pode ser habilitado até uma ação ser executada. Esses recursos são indicados por um símbolo X vermelho. Você deve executar as ações indicadas na descrição para que o recurso esteja habilitado. Por exemplo, se você não puder usar um recurso até uma chave de configuração ser desabilitada, você precisará desabilitar a chave de configuração antes e depois para retornar ao gerenciamento de recursos para habilitar o recurso.

Depois que um recurso é ativado, uma mensagem será exibida abaixo do link **Saiba mais** no painel de detalhes. Essa mensagem informa que o recurso foi ativado ou indica a data futura em que o recurso está agendado para ser ativado. Ela será exibida sempre que você selecionar o recurso na lista de recursos.

Os recursos que estão agendados para serem ativados no futuro aparecem na guia **Agendado**. Um processo em lote vai ativá-los à meia-noite na data especificada, com base no fuso horário representado pela data do sistema.

## <a name="reschedule-a-feature"></a>Reagendar um recurso

Se um recurso tiver sido agendado para ser ativado no futuro, um botão **Agenda** será exibido no painel de detalhes. Você poderá usar este botão para alterar o valor **Data da habilitação** para uma data diferente.

1. Selecione o recurso agendado para reagendar e, no painel de detalhes, selecione **Agenda**.
2. Na caixa de diálogo exibida, no campo **Data da habilitação**, especifique a nova data em que o recurso deve ser ativado.
3. Selecione **Habilitar** para reagendar o recurso ou **Desabilitar** para cancelar o agendamento.

## <a name="turn-off-a-feature"></a>Desativar um recurso

Se um recurso não já tiver sido desativado, um botão **Desabilitar** será exibido no painel de detalhes. Você pode usar esse botão para desativar o recurso. O botão **Desabilitar** não estará disponível se o recurso não puder ser desativado depois de ser ativado.

- Selecione o recurso a ser desativado e, no painel de detalhes, selecione **Desabilitar**. O recurso está desativado e o campo **Data da habilitação** é desmarcado.

Depois que um recurso é desativado, uma mensagem será exibida abaixo do link **Saiba mais** no painel de detalhes. Esta mensagem indica que o recurso ainda não foi ativado. Ela será exibida sempre que você selecionar o recurso na lista de recursos. Os recursos que não foram ativados aparecem na guia **Não habilitado**.

## <a name="features-that-must-be-turned-on"></a>Recursos que devem ser ativados

Às vezes, um recurso crítico que deve ser ativado automaticamente é entregue quando você faz uma atualização. Esses recursos serão ativados automaticamente na data especificada no campo **Data da habilitação**. No caso desses recursos, uma mensagem será exibida abaixo do link **Saiba mais** no painel de detalhes. Essa mensagem informa que o recurso foi ativado ou indica a data futura em que o recurso será ativado. Ela será exibida sempre que você selecionar o recurso na lista de recursos.

## <a name="enable-all-features"></a>Habilitar todos os recursos

Por padrão, todos os recursos que são adicionados ao seu ambiente são desativados. Você pode habilitar todos os recursos selecionando o botão **Habilitar tudo**. 

Quando você selecionar **Habilitar tudo**, aparecerá uma opção em que você precisa fornecer as seguintes informações:
- Uma lista de todos os recursos que exigem confirmação antes de serem habilitados. Se você deseja habilitar os recursos na lista, selecione **Sim** para o botão **Habilitar recursos que exijam confirmação**.
- Aparecerá uma lista de todos os recursos que não podem ser habilitados. Esses recursos não serão habilitados.

Todos os recursos que possam ser habilitados serão habilitados. Se determinado recurso já estiver agendado para ser habilitado no futuro, a agenda não será alterada. 

## <a name="turn-on-all-features-automatically"></a>Ativar todos os recursos automaticamente

Por padrão, todos os recursos adicionados ao seu ambiente são desativados, a menos que sejam obrigatórios. Contudo, caso você deseje ativar automaticamente todos os novos recursos, é possível usar a lista suspensa sob o título do espaço de trabalho para alterar o que ocorre quando novos recursos são adicionados.

- Selecione **Habilitar novos recursos automaticamente** para ativar automaticamente todos os novos recursos quando forem adicionados ao ambiente.
- Selecione **Não habilitar novos recursos automaticamente** para desativar todos os novos recursos quando forem adicionados ao ambiente.


Quando você habilita todos os recursos automaticamente, isso habilita todos os recursos que seriam habilitados se você clicasse no botão **Habilitar tudo**. Isso não habilitará os recursos que exijam confirmação ou os recursos que não possam ser habilitados até uma ação ser executada.

## <a name="check-for-updates"></a>Verificar se há atualizações

Os recursos são adicionados a seu ambiente após cada atualização. Entretanto, você pode verificar manualmente a existência de atualizações clicando no botão **Verificar se há atualizações**. Qualquer recurso adicionado ao sistema após a atualização será adicionada à lista de recursos. Por exemplo, se um recurso liberado for habilitado após uma versão, você poderá verificar a existência de atualizações e o recurso será adicionado à sua lista.

## <a name="assigning-roles"></a>Atribuindo funções

O espaço de trabalho **Gerenciamento de recursos** pode ser aberto pelos administradores do sistema e também pelos usuários que estão atribuídos à função de gerente de recursos ou à função de visualizador de recursos. Essas duas funções foram criadas para oferecer suporte à experiência de gerenciamento de recursos. Os usuários na função de gerente o recursos poderá ativar ou desativar qualquer de recurso. Eles também poderão atualizar o campo **Comentários** do recurso. Os usuários na função de visualizador de recursos podem somente exibir o espaço de trabalho **Gerenciamento de recursos**. Eles não poderão ativar ou desativar recursos.

A função de gerente de recursos e a função de visualizador de recurso não substituem a segurança existente que um usuário tem. Eles apenas controlarão se o usuário pode ativar e desativar recursos. Eles não fornecem acesso aos próprios recursos.

## <a name="features-that-use-configuration-keys"></a>Recursos que usam chaves de configuração

Se um recurso usar uma chave de configuração, mas a chave de configuração não estiver ativada, o espaço de trabalho **Gerenciamento de recursos** não mostrará o recurso na lista de recursos disponíveis. Após a ativação da chave de configuração, você deverá atualizar a lista de recursos usando o item de menu **Verificação de atualização**. O recurso aparece na lista de recursos.

Se você desativar a chave de configuração, o recurso não será removido da lista de recursos.

## <a name="data-entities"></a>Entidades de dados

Uma entidade de dados chamada **Gerenciamento de recursos** permite exportar as configurações de gerenciamento de recursos de um ambiente e depois importá-las para outro ambiente. Essa entidade atualiza apenas os recursos existentes. A lógica comercial na entidade também ajuda a garantir que as mesmas regras usadas no espaço de trabalho **Gerenciamento de recursos** serão aplicadas quando a importação for concluída. Por exemplo, não é possível substituir uma configuração de recursos obrigatória removendo a data durante a importação.

Os exemplos a seguir descrevem o que ocorre quando você usa a entidade **Gerenciamento de recursos** para importar dados.

- Se você alterar o valor do campo **Habilitado** como **Sim**, o recurso será ativado e o campo **Data da habilitação** será definido como a data atual.
- Se você alterar o valor do campo **Habilitado** como **Não** ou deixar o campo **Data da habilitação** em branco, o recurso será desativado e o campo **Data da habilitação** será desmarcado. Você não pode desativar um recurso obrigatório ou um recurso que não pode ser desativado depois de ativado.
- Se você alterar o valor do campo **Data da habilitação** para uma data futura, o recurso será agendado para essa data.
- Se você alterar o valor do campo **Habilitado** para **Sim** e alterar o valor do campo **Data da habilitação** para uma data futura, o recurso será agendado para essa data. 
- Se você alterar o valor do campo **Habilitado** para **Não**, mas também alterar o valor do campo **Data da habilitação** para uma data futura, o recurso será agendado para essa data.
- Se um recurso estiver ativado e você adicionar um campo **Data da habilitação** definido como uma data futura, o recurso permanecerá ativado. Para reagendar o recurso, você deve alterar o campo **Habilitado** como **Não**.

## <a name="feature-management-and-flighting"></a>Gerenciamento recursos e liberação de versões

O gerenciamento de recursos permite que você controle os recursos que são entregues em cada versão. A liberação de versões permite que as equipes da Microsoft liberem recursos para um número limitado de clientes, de maneira que os recursos possam ser testados e validados sem afetar todos os clientes. O gerenciamento de recursos não controla a liberação de versões dos recursos.

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>Usando o gerenciamento de recursos para desativar recursos de ISV ou recursos personalizados

Atualmente, o gerenciamento de recursos não está disponível para recursos de fornecedores de software independentes (ISVs) e recursos personalizados. Contudo, a Microsoft está adicionando mais funcionalidades para aprimorar o gerenciamento de recursos. Após a conclusão de aprimoramentos, a Microsoft disponibilizará o gerenciamento de recursos para todos os recursos e fornecerá instruções para atualizar seus recursos para usá-lo.
