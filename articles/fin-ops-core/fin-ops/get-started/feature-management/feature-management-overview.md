---
title: Visão geral do gerenciamento de recursos
description: Este artigo descreve o Gerenciamento de recursos e como você pode usá-lo.
author: Peakerbl
ms.date: 01/10/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: IT Pro, Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 0691bc34ac8b57d20cfbeb58b6a2e2a03a57d067
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850041"
---
# <a name="feature-management-overview"></a>Visão geral do gerenciamento de recursos

[!include [banner](../../includes/banner.md)]


[!INCLUDE [PEAP](../../../../includes/peap-1.md)]

Os recursos são adicionados e atualizados em cada versão. A experiência de gerenciamento de recursos fornece um espaço de trabalho em que você pode exibir uma lista dos recursos que foram entregues em cada versão. Você poderá usar o espaço de trabalho para visualizar a documentação de recursos e para habilitar ou desabilitar recursos.

## <a name="the-feature-management-workspace"></a>O espaço de trabalho do gerenciamento de recursos

Você pode abrir o espaço de trabalho **Gerenciamento de recursos** selecionando o bloco apropriado no painel. Você verá uma página que mostra uma lista de recursos para todas as versões com suporte na experiência de gerenciamento de recursos. 

A lista recursos inclui as seguintes informações:

- **Nome do recurso** — uma descrição do recurso que foi adicionado.
- **Status** — Um símbolo indica se um recurso está ativado (marca de seleção) ou desativado (em branco), se está agendado para ser ativado (relógio), se é obrigatório (cadeado), se exige atenção antes de ser ativado (símbolo de aviso) ou se não pode ser ativado (X). A configuração exibida é usada para todas as entidades legais. Observe que, mesmo quando um recurso for ativado, ele ainda será controlado pela segurança. Portanto, o recurso estará disponível somente para os usuários que tiverem acesso a ele com base na função de segurança. Ele também estará disponível somente em entidades legais às quais o usuário tem acesso.
- **Data da habilitação** – A data em que o recurso foi ativado ou está agendado para ser ativado.
- **Recurso adicionado** — a data em que o recurso foi adicionado ao ambiente. Essa data é inserida automaticamente quando você atualiza seu ambiente durante ciclos mensais de lançamento.
- **Estado do recurso** – O estado de ciclo de vida atual do recurso: **Versão prévia**, **Liberado** (mostrado como em branco), **Ativado por padrão** e **Obrigatório**. Os estados serão abordados em mais detalhes posteriormente neste artigo. 
- **Módulo** — o módulo que é afetado pelo novo recurso.

> [!NOTE]
> A coluna **Estado do recurso** foi incluída na versão 10.0.21.

Ao selecionar um recurso, mais informações serão exibidas no painel de detalhes à direita da lista de recursos. Na parte superior do painel, você verá o nome do recurso, a data em que o recurso foi adicionado, o módulo que é afetado pelo recurso e um link **Saiba mais**. Selecione esse link para exibir a documentação do recurso. Se a documentação não estiver disponível, você será levado a uma página temporária. O painel de detalhes também inclui um campo **Comentários**, onde você pode adicionar seus próprios comentários sobre o recurso.

O espaço de trabalho **Gerenciamento de recursos** também possui várias guias, cada uma mostrando uma lista de recursos.

- **Novo** – Esta guia mostra todos os recursos que foram adicionados desde a última atualização mensal. Se você tiver ignorado todas as atualizações mensais, a guia mostrará todos os novos recursos que foram adicionados desde a última atualização. Os recursos mais novos aparecem na parte superior da lista. O número total de novos recursos também é mostrado em um bloco na parte superior da página.
- **Não habilitado** – Esta guia mostra todos os recursos que não estão ativados. Os recursos mais novos aparecem na parte superior da lista. Além disso, um bloco na parte superior da página mostra o número total de novos recursos que, no momento, estão desativados.
- **Agendado** – Esta guia mostra todos os recursos que foram programados para serem ativados no futuro. Os recursos com a data mais próxima agendada aparecerão na parte superior da lista. Além disso, um bloco na parte superior da página mostra o número total de recursos agendados.
- **Tudo** – Esta guia mostra todos os recursos. Os recursos mais novos aparecem na parte superior da lista.

## <a name="feature-states"></a>Estados de recurso
Os recursos podem assumir vários estados, desde serem introduzidos no Gerenciamento de recursos a se tornarem obrigatórios no produto. Esta seção descreve os estados de recurso válidos.

### <a name="preview-features-optional"></a>Versões prévias de recursos (opcionais)

As equipes de produto podem optar por lançar um novo recurso inicialmente como sendo uma versão prévia do recurso. As versões prévias dos recursos não são habilitadas por padrão e são opcionais. A equipe proprietária do produto atualizará os recursos para o estado lançado depois que eles concluírem um período de versão prévia bem-sucedido.

> [!NOTE]
> As versões prévias dos recursos estão sujeitas a [termos e condições](https://go.microsoft.com/fwlink/?linkid=2105274) específicos. 

### <a name="released-features-optional"></a>Recursos liberados (opcionais)

A coluna **Estado do recurso** desses recursos fica em branco. Os recursos inicialmente adicionados como liberados não são ativados por padrão, e sua ativação é opcional. Os recursos atualizados a partir de uma versão prévia manterão o status de habilitação.

### <a name="on-by-default-features-optional"></a>Recursos ativados por padrão (opcionais)

Os recursos atualizados para **Ativado por padrão** são ativados por padrão, mas podem ser desabilitados. Depois que os recursos que podem ser desabilitados ficarem no estado **Liberado** durante pelo menos seis meses, deverão passar para esse estado na próxima versão principal. Os recursos que fazem a transição para o estado **Ativado por padrão** devem ser anunciados no artigo [Novidades](../whats-new-changed.md) da versão. A atualização é iniciada pela equipe proprietária do produto.

> [!NOTE]
> Como esses recursos serão habilitados automaticamente, é importante determinar se a organização está pronta para adotá-los ou se é preciso mais tempo. Nesse caso, pode ser necessário desabilitar esses recursos temporariamente. Observe que a transição de um recurso para **Ativado por padrão** geralmente é feita na versão principal antes que ele seja planejado para se tornar **Obrigatório**. Nesse momento, você não terá a opção de desabilitar o recurso. 

### <a name="mandatory"></a>Obrigatório

**Obrigatório** é o estado final esperado dos recursos. Ele indica que os recursos estão ativados e que você não pode desabilitá-los sem contatar a Microsoft. Os recursos opcionais devem se tornar obrigatórios após duas versões principais. Excepcionalmente, os recursos críticos podem ser introduzidos como obrigatórios.

## <a name="example-of-expected-feature-lifecycles"></a>Exemplo de ciclos de vida de recursos esperados

Os recursos que podem ser desabilitados e que foram adicionados como liberados e opcionais antes ou como parte do lançamento de abril devem fazer a transição para **Ativado por padrão** no próximo lançamento de outubro. Por isso, espera-se que eles mudem para o estado **Obrigatório** em abril do ano seguinte.

Os recursos que podem ser desabilitados e que foram adicionados como liberados e opcionais antes ou como parte do lançamento de abril devem fazer a transição para **Obrigatório** em abril do ano seguinte.

## <a name="enable-a-feature"></a>Habilitar um recurso

Se um recurso não foi ativado, um botão **Habilitar agora** será exibido no painel de detalhes. Você poderá usar esse botão para habilitar o recurso.

Alguns recursos não poderão ser desabilitados depois que forem habilitados. Se o recurso que você está tentando ativar não puder ser habilitado, você receberá um aviso. Nesse momento, você poderá selecionar **Cancelar** para cancelar a operação e deixar o recurso desabilitado. No entanto, se você selecionar **Habilitar** para habilitar o recurso, ele não poderá ser desabilitado posteriormente.

Alguns recursos exibirão uma mensagem que fornece informações adicionais antes de você habilitá-los. Esses recursos são indicados por um símbolo de aviso amarelo. Você deve ler as informações adicionais cuidadosamente para garantir que compreendeu o que acontecerá quando o recurso for habilitado. Entretanto, você ainda poderá selecionar **Habilitar** para habilitar o recurso.

Alguns recursos exibirão uma mensagem de que o recurso não pode ser habilitado até uma ação ser executada. Esses recursos são indicados por um símbolo X vermelho. Você deve executar as ações indicadas na descrição para que o recurso esteja habilitado. Por exemplo, se você não puder usar um recurso até uma chave de configuração ser desabilitada, você precisará desabilitar a chave de configuração antes e depois para retornar ao gerenciamento de recursos para habilitar o recurso.

Depois que um recurso for habilitado, uma mensagem será exibida abaixo do link **Saiba mais** no painel de detalhes. Essa mensagem informa que o recurso foi habilitado ou indica a data futura em que ele está agendado para ser habilitado. Ela será exibida sempre que você selecionar o recurso na lista de recursos.

Os recursos que estão agendados para serem habilitados no futuro aparecem na guia **Agendado**. Um processo em lote vai habilitá-los à meia-noite na data especificada com base no fuso horário representado pela data do sistema.

## <a name="reschedule-a-feature"></a>Reagendar um recurso

Se um recurso tiver sido agendado para ser habilitado no futuro, um botão **Agenda** será exibido no painel de detalhes. Você poderá usar este botão para alterar o valor **Data da habilitação** para uma data diferente.

1. Selecione o recurso agendado para reagendar e, no painel de detalhes, selecione **Agenda**.
2. Na caixa de diálogo exibida, no campo **Data da habilitação**, especifique a nova data em que o recurso deve ser habilitado.
3. Selecione **Habilitar** para reagendar o recurso ou **Desabilitar** para cancelar o agendamento.

## <a name="disable-a-feature"></a>Desabilitar um recurso

Se um recurso tiver sido habilitado, um botão **Desabilitar** será exibido no painel de detalhes. Você poderá usar esse botão para desabilitar o recurso. O botão **Desabilitar** não estará disponível se o recurso não puder ser desabilitado. 

Depois que um recurso for desabilitado, será exibida uma mensagem abaixo do link **Saiba mais** no painel de detalhes. Essa mensagem indica que o recurso não foi habilitado. Ela será exibida sempre que você selecionar o recurso na lista de recursos. Os recursos que não foram habilitados são exibidos na guia **Não habilitado**.

## <a name="features-that-must-be-enabled"></a>Recursos que devem ser habilitados

Às vezes, um recurso crítico que deve ser habilitado automaticamente é entregue quando você faz uma atualização. Esses recursos serão habilitados automaticamente na data especificada no campo **Data da habilitação**. No caso desses recursos, uma mensagem será exibida abaixo do link **Saiba mais** no painel de detalhes. Essa mensagem informa que o recurso foi habilitado ou indica a data futura em que o recurso será habilitado. Ela será exibida sempre que você selecionar o recurso na lista de recursos.

## <a name="enable-all-features"></a>Habilitar todos os recursos

Você pode habilitar todos os recursos selecionando o botão **Habilitar tudo**. 

Quando você seleciona **Habilitar tudo**, é exibida uma opção em que você deve fornecer as seguintes informações:

- Uma lista de todos os recursos que exigem confirmação antes de serem habilitados. Se você deseja habilitar os recursos na lista, selecione **Sim** para o botão **Habilitar recursos que exijam confirmação**.
- Aparecerá uma lista de todos os recursos que não podem ser habilitados. Esses recursos não serão habilitados.

Todos os recursos que possam ser habilitados serão habilitados. Se determinado recurso já estiver agendado para ser habilitado no futuro, a agenda não será alterada. 

## <a name="enable-all-features-automatically"></a>Habilitar todos os recursos automaticamente

Caso você deseje habilitar todos os novos recursos automaticamente, é possível usar a lista suspensa sob o título do espaço de trabalho para alterar o que ocorre quando novos recursos são adicionados.

- Selecione **Habilitar novos recursos automaticamente** para habilitar automaticamente todos os novos recursos quando forem adicionados ao ambiente.
- Selecione **Não habilitar novos recursos automaticamente** se todos os novos recursos aplicáveis tiverem de ser desativados por padrão quando forem adicionados ao ambiente.

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

- Se você alterar o valor do campo **Habilitado** para **Sim**, o recurso será habilitado e o campo **Data da habilitação** será definido com a data atual.
- Se você alterar o valor do campo **Habilitado** para **Não** ou deixar o campo **Data da habilitação** em branco, o recurso será desabilitado e o campo **Data da habilitação** será desmarcado. Não é possível desabilitar um recurso obrigatório ou um recurso que não pode ser desabilitado depois de habilitado.
- Se você alterar o valor do campo **Data da habilitação** para uma data futura, o recurso será agendado para essa data.
- Se você alterar o valor do campo **Habilitado** para **Sim** e alterar o valor do campo **Data da habilitação** para uma data futura, o recurso será agendado para essa data. 
- Se você alterar o valor do campo **Habilitado** para **Não**, mas também alterar o valor do campo **Data da habilitação** para uma data futura, o recurso será agendado para essa data.
- Se um recurso estiver habilitado e você adicionar um campo **Data da habilitação** definido com uma data futura, o recurso permanecerá habilitado. Para reagendar o recurso, você deve alterar o valor do campo **Habilitado** para **Não**.

## <a name="feature-management-and-flighting"></a>Gerenciamento recursos e liberação de versões

O gerenciamento de recursos permite que você controle os recursos que são entregues em cada versão. A liberação de versões permite que as equipes da Microsoft liberem recursos para um número limitado de clientes, de maneira que os recursos possam ser testados e validados sem afetar todos os clientes. O gerenciamento de recursos não controla a liberação de versões dos recursos.

## <a name="using-feature-management-to-turn-on-isv-features-or-custom-features"></a>Usando o gerenciamento de recursos para desativar recursos de ISV ou recursos personalizados

Atualmente, o gerenciamento de recursos não está disponível para recursos de fornecedores de software independentes (ISVs) e recursos personalizados. Contudo, a Microsoft está adicionando mais funcionalidades para aprimorar o gerenciamento de recursos. Após a conclusão de aprimoramentos, a Microsoft disponibilizará o gerenciamento de recursos para todos os recursos e fornecerá instruções para atualizar seus recursos para usá-lo.

## <a name="frequently-asked-questions-faq"></a>Perguntas frequentes

### <a name="when-are-features-added-removed-or-changed"></a>Quando os recursos são adicionados, removidos ou alterados? 
Recursos são adicionados, removidos e alterados por meio de alterações de código feitas pelas equipes proprietárias dos produtos. Os ambientes devem ser atualizados para receber essas alterações.

### <a name="does-a-feature-become-mandatory-automatically"></a>Um recurso se torna obrigatório automaticamente? 
Não, um recurso não se torna obrigatório automaticamente. A equipe proprietária do produto deve fazer uma alteração no código.

### <a name="why-isnt-there-a-specific-mandatory-enabled-date"></a>Por que não há uma "data de habilitação obrigatória" específica? 
O tempo de liberação das atualizações é variável, o tempo de atualização de ambiente é variável, e os clientes podem optar por ignorar algumas atualizações. Como resultado, datas específicas são difíceis de determinar. 

### <a name="wheres-the-documentation-for-features-that-are-mandatory"></a>Onde está a documentação dos recursos que são obrigatórios? 
Essa documentação vem de cada equipe de aplicativo do Dynamics 365. Frequentemente, esses recursos serão mencionados nos recursos [Atualizações para os estados de recursos do cliente](/dynamics365-release-plan/2021wave1/finance-operations/finance-operations-crossapp-capabilities/updates-client-feature-states) ou [Removidos ou preteridos](../../../dev-itpro/migration-upgrade/deprecated-features.md). 

### <a name="is-there-an-in-product-notification-or-signal-that-a-feature-is-going-to-be-mandatory-enabled"></a>Há uma notificação ou um sinal no produto de que um recurso terá a habilitação obrigatória? 
Atualmente, não existe um mecanismo de notificação para informar que um recurso se tornará obrigatório.

### <a name="do-features-ever-get-enabled-without-the-customer-knowing-about-it"></a>Os recursos podem ser habilitados sem que o cliente saiba disso? 
Sim, recursos podem ser habilitados sem o conhecimento do cliente nas seguintes situações:
- Um recurso muda para **Ativado por padrão**. Nesse estado, o recurso ainda pode ser desabilitado. 
- Um recurso é atualizado para **Obrigatório**. Essa alteração ocorrerá somente em combinação com uma versão principal. Excepcionalmente, recursos críticos podem mudar para o estado **Obrigatório** em qualquer atualização.

### <a name="what-is-feature-flighting-and-how-does-it-relate-to-feature-management"></a>O que é a liberação de versões dos recursos e como ela se relaciona com o gerenciamento de recursos? 
As liberações de versões de pré-lançamento dos recursos são botões ligar/desligar em tempo real que a Microsoft controla. Eles são separados do controle do cliente fornecido pelo Gerenciamento de Recursos. 
- Os recursos de versão preliminar privada não serão listados no Gerenciamento de Recursos até que sejam liberadas versões de pré-lançamento. Na produção, o cliente deve concordar em fazer parte de um programa especial para que isso ocorra.
- Os recursos em Versão Preliminar Pública e Liberados (em disponibilidade geral) serão listados no Gerenciamento de Recursos, a menos que sejam sejam disponibilizados em versão piloto. A liberação de versões de pré-lançamento de um recurso é considerada uma última opção para as equipes de produto, caso um problema crítico seja encontrado e geralmente seja uma operação por cliente.

### <a name="do-features-ever-get-flighted-off-without-the-customer-knowing-about-it"></a>Os recursos podem ter liberação de versões de pré-lançamento sem que o cliente saiba disso? 
Sim, se um recurso estiver causando impacto no funcionamento de um ambiente que não tenha um impacto funcional, eles poderão ser habilitados por padrão.

### <a name="how-can-feature-enablement-be-checked-in-code"></a>Como a habilitação do recurso pode ser verificada no código?
Use o método **isFeatureEnabled** na classe **FeatureStateProvider**, passando uma instância da classe feature. Exemplo: 

```xpp
if (FeatureStateProvider::isFeatureEnabled(BatchContentionPreventionFeature::instance()))
```

### <a name="how-can-feature-enablement-be-checked-in-metadata"></a>Como a habilitação do recurso pode ser verificada nos metadados?
A propriedade **FeatureClass** pode ser usada para indicar que alguns metadados estão associados a um recurso. O nome da classe para o recurso deve ser usado, como **BatchContentionPreventionFeature**. Esses metadados estão visíveis somente nesse recurso. A propriedade **FeatureClass** está disponível em menus, itens de menu, valores de enumeração e campos de tabela/exibição.

### <a name="what-is-a-feature-class"></a>O que é uma classe de recurso?
Os recursos no Gerenciamento de Recursos são definidos como *classes de recursos*. Uma classe de recurso **implementa IFeatureMetadata** e usa o atributo de classe do recurso para se identificar para o espaço de trabalho Gerenciamento de Recursos. Há vários exemplos de classes de recursos disponíveis que podem ser verificadas em caso de habilitação no código usando a API **FeatureStateProvider** e em metadados usando a propriedade **FeatureClass**. Exemplo: 

```xpp
[ExportAttribute(identifierStr(Microsoft.Dynamics.ApplicationPlatform.FeatureExposure.IFeatureMetadata))]
internal final class BankCurrencyRevalGlobalEnableFeature implements IFeatureMetadata
```

### <a name="what-is-the-ifeaturelifecycle-implemented-by-some-feature-classes"></a>O que é o IFeatureLifecycle implementado por algumas classes de recursos?
O IFeatureLifecycle é um mecanismo interno da Microsoft para indicar o estágio do ciclo de vida do recurso. Os recursos podem ser:
- `PrivatePreview` - Precisa um versão piloto visível.
- `PublicPreview` - Mostrado por padrão, mas com um aviso de que o recurso está em versão preliminar.
- `Released` - Totalmente liberado.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
