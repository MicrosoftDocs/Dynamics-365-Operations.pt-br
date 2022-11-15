---
title: Automação de fornecimento sob encomenda
description: Este artigo descreve como configurar e usar os vários aprimoramentos adicionados pelo recurso Automação de fornecimento sob encomenda.
author: t-benebo
ms.date: 07/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-27
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d376c2f4d8514a4e6122e2e94455d57a39d2babf
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740185"
---
# <a name="make-to-order-supply-automation"></a>Automação de fornecimento sob encomenda

[!include [banner](../includes/banner.md)]

O recurso *Automação de fornecimento sob encomenda* adiciona vários aprimoramentos ao Microsoft Dynamics 365 Supply Chain Management. Esses aperfeiçoamentos permitem a realização das seguintes tarefas:

- Exibir a capacidade máxima do recurso para um período definido pelo usuário e, portanto, habilitar a avaliação de longo prazo da capacidade de carga.
- Melhorar a flexibilidade controlando a tolerância de atraso (dias negativos) para cada plano mestre.
- Manter os produtos disponíveis para os pedidos de última hora e otimizar o uso do fornecimento existente, vinculando o último fornecimento possível a uma demanda, em vez de usar o primeiro fornecimento possível.
- Manter a atribuição de componentes flexível para ordens de produção após a confirmação, de forma que o sistema possa otimizar as alterações de demanda de última hora. Em outras palavras, limitar a marcação em um nível.
- Controlar a política de processamento para cada ordem de venda. As configurações padrão são extraídas da configuração do cliente.
- Aprimorar o fluxo de informações intercompanhia. As ordens de compra são atualizadas para incluir campos para o modo de entrega, condições de entrega e número de item externo. Essa alteração garante que as informações de demanda detalhadas possam fluir para a empresa fornecedora.

Este artigo descreve como configurar e usar cada aprimoramento.

## <a name="turn-on-the-make-to-order-supply-automation-feature"></a>Ativar o recurso Automação de fornecimento sob encomenda

Para poder usar o recurso descrito neste artigo, você deve ativá-lo para seu sistema. Os administradores podem usar o espaço de trabalho [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), onde o recurso é indicado da seguinte forma:

- **Módulo:** *Planejamento mestre*
- **Nome do recurso** *Automação de fornecimento sob encomenda*

## <a name="set-the-number-of-days-to-show-on-capacity-load-page"></a>Definir o número de dias para mostrar na página Capacidade máxima

A página **Capacidade máxima** permite revisar a capacidade disponível de um recurso. O recurso *Automação de fornecimento sob encomenda* aprimora a página **Capacidade máxima** adicionando um campo **Número de dias**. É possível usar esse campo para limitar o número de dias mostrado pela grade **Visão geral**. O valor definido é salvo na memória. Portanto, se você sair da página e retornar mais tarde, a grade **Visão geral** ainda mostrará o número de dias especificado por último.

Para abrir a página **Capacidade máxima**, de forma que você possa revisar a capacidade disponível de um recurso individual, siga estas etapas.

1. Acesse **Administração da organização \> Recursos \> Recursos**.
1. Selecione um recurso para inspecionar.
1. No Painel de Ações, na guia **Recurso**, no grupo **Exibir**, selecione **Capacidade máxima**.
1. Use o filtro **Número de dias** para limitar o número de dias mostrado pela grade **Visão geral**.

Para abrir a página **Capacidade máxima**, de forma que você possa revisar a capacidade disponível de um grupo de recursos, siga estas etapas.

1. Acesse **Administração da organização \> Recursos \> Grupos de recursos**.
1. Selecione um grupo de recursos para inspecionar.
1. No Painel de Ações, na guia **Grupo de recursos**, no grupo **Exibir**, selecione **Capacidade máxima**.
1. Use o filtro **Número de dias** para limitar o número de dias mostrado pela grade **Visão geral**.

## <a name="apply-a-single-level-of-marking-when-you-firm-planned-orders"></a>Aplicar um único nível de marcação ao confirmar ordens planejadas

A *marcação* é usada para vincular fornecimento e demanda. Ela é semelhante à *vinculação*, que indica como o planejamento mestre espera cobrir a demanda. No entanto, a marcação é mais permanente do que a vinculação. O recurso *Automação de fornecimento sob encomenda* adiciona a capacidade de limitar a marcação de estoque a um único nível quando as ordens planejadas são confirmadas. Ele adiciona as novas opções a seguir ao campo **Atualizar marcação** na caixa de diálogo **Confirmação** quando você está confirmando uma ordem planejada:

- *Padrão de nível único* – a marcação de nível único é usada. A marcação de nível único marca somente o item principal, não os componentes da lista de materiais (BOM). Portanto, você pode manter flexível a atribuição de componentes para ordens de produção após a confirmação. A marcação de nível único permite que o sistema otimize as alterações de demanda de última hora. Na marcação de nível único *padrão*, as ordens de requisito são marcadas em relação às ordens de processamento, mas estas não serão marcadas se tiverem quantidade pendente.
- *Nível único estendido* – a marcação de nível único é usada. Na marcação de nível único *estendido*, as ordens de requisito são marcadas em relação às ordens de processamento, e estas serão sempre marcadas, tenham ou não quantidade pendente.

Essas opções também estão disponíveis no campo **Atualizar marcação** na guia **Atualização padrão** da página **Parâmetros do planejamento mestre**, na qual você define a seleção padrão para a caixa de diálogo **Confirmação**.

Para obter mais informações, consulte [Marcação de estoque](planning-optimization/marking.md).

## <a name="set-delay-tolerance-negative-days-at-the-master-plan-level"></a>Definir tolerância de atraso (dias negativos) no nível do plano mestre

O recurso *Automação de fornecimento sob encomenda* adiciona a capacidade de configurar a tolerância de atraso (dias negativos) no nível do plano mestre. A configuração também está disponível nos níveis de cobertura de item e grupo de cobertura. Se os dias negativos forem atribuídos em mais de um nível, o sistema aplicará a hierarquia a seguir para decidir qual configuração usar:

- Se os dias negativos estiverem configurados na página **Planos mestre**, essa configuração substituirá todas as outras configurações de dias negativos quando o plano for executado.
- Se os dias negativos forem configurados na página **Cobertura de item**, essa configuração substituirá a configuração do grupo de cobertura.
- Os dias negativos configurados na página **Grupos de cobertura** se aplicarão somente se os dias negativos não foram configurados para um item ou um plano mestre relevante.

Para definir dias negativos para um plano mestre, siga estas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. Selecione um plano mestre no painel de lista ou crie um.
1. Na guia rápida **Limites de tempo em dias**, defina a opção **Dias negativos** como *Sim*.
1. No campo próximo, insira o número de dias negativos a serem permitidos.

Para obter mais informações sobre como usar dias negativos, consulte [Tolerância de atraso (dias negativos)](planning-optimization/delay-tolerance.md).

## <a name="control-the-pegging-sequence-used-during-master-planning"></a>Controlar a sequência de vinculação usada durante o planejamento mestre

O planejamento mestre usa uma *sequência de vinculação* para determinar qual fornecimento cobrirá qual demanda. O recurso *Automação de fornecimento sob encomenda* adiciona a nova opção **Usar o fornecimento mais recente possível** que oferece maior controle sobre a sequência de vinculação. A nova opção permite manter os produtos disponíveis para os pedidos de última hora e otimizar o uso do fornecimento existente, vinculando o último fornecimento possível a uma demanda, em vez de usar o primeiro fornecimento possível.

Você pode definir a sequência de vinculação no nível do plano mestre, da cobertura de item ou do grupo de cobertura. Se uma sequência de vinculação for configurada em mais de um nível, o sistema aplicará a hierarquia a seguir para decidir qual configuração usar:

- Se uma sequência de vinculação estiver configurada na página **Planos mestre**, ela substituirá todas as outras configurações da sequência de vinculação quando o plano for executado.
- Se uma sequência de vinculação estiver configurada na página **Cobertura de item**, ela substituirá a configuração do grupo de cobertura.
- A sequência de vinculação configurada na página **Grupos de cobertura** se aplicará somente se as configurações de sequência de vinculação não tiverem sido configuradas para um item ou um plano mestre relevante.

Para configurar a vinculação no nível do grupo de cobertura, siga estas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Cobertura \> Grupos de cobertura**.
1. Selecione um grupo no painel de lista ou crie um.
1. Na guia rápida **Geral**, na seção **Sequência de vinculação**, use os campos **Consumir estoque disponível** e **Usar o fornecimento mais recente** para configurar a sequência de vinculação. A tabela mais adiante nesta seção mostra como essas configurações são combinadas para definir a sequência de vinculação.

Para configurar a vinculação no nível da cobertura de item, siga estas etapas.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione um produto na grade ou crie um.
1. No Painel de Ações, na guia **Plano**, selecione **Cobertura do item**.
1. A página **Cobertura de item** fornece linhas que permitem definir regras de cobertura aplicáveis ao item em cada depósito. Selecione uma linha existente na grade ou crie uma.
1. Na guia **Geral**, marque a caixa de seleção **Substituir sequência de vinculação**.
1. Use os campos **Consumir estoque disponível** e **Usar o fornecimento mais recente** para configurar a sequência de vinculação. A tabela mais adiante nesta seção mostra como essas configurações são combinadas para definir a sequência de vinculação.

Para configurar a vinculação no nível do plano mestre, siga estas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. Selecione um plano mestre no painel de lista ou crie um.
1. Na guia rápida **Geral**, defina a opção **Substituir sequência de vinculação** como *Sim*.
1. Use os campos **Consumir estoque disponível** e **Usar o fornecimento mais recente** para configurar a sequência de vinculação. A tabela mais adiante nesta seção mostra como essas configurações são combinadas para definir a sequência de vinculação.

A tabela a seguir mostra como as configurações **Consumir estoque disponível** e **Usar o fornecimento mais recente** são combinadas para estabelecer a sequência de vinculação.

| | Usar o fornecimento mais recente = Sim | Usar o fornecimento mais recente = Não |
|---|---|---|
| **Consumir estoque disponível** = *Antes de todos os outros suprimentos* | <ol><li>Disponível</li><li>Fornecimento existente que pode atender à data da demanda</li><li>O fornecimento existente que não atende à data da demanda, mas que ainda está dentro dos dias negativos</li><li>Criar fornecimento (ordem planejada)</li></ol> | <ol><li>Disponível</li><li>Fornecimento existente que pode atender à data da demanda</li><li>O fornecimento existente que não atende à data da demanda, mas que ainda está dentro dos dias negativos</li><li>Criar fornecimento (ordem planejada)</li></ol> |
| **Consumir estoque disponível** = *Depois de todos os outros suprimentos* | <ol><li>Fornecimento existente que pode atender à data da demanda</li><li>Disponível</li><li>O fornecimento existente que não atende à data da demanda, mas que ainda está dentro dos dias negativos</li><li>Criar fornecimento (ordem planejada)</li></ol> | <ol><li>Fornecimento existente que pode atender à data da demanda</li><li>O fornecimento existente que não atende à data da demanda, mas que ainda está dentro dos dias negativos</li><li>Disponível</li><li>Criar fornecimento (ordem planejada)</li></ol> |

## <a name="review-and-set-the-fulfillment-policy-that-applies-to-each-sales-order"></a>Revisar e definir a política de processamento aplicável a cada ordem de venda

As políticas de processamento controlam a porcentagem do preço ou da quantidade total da ordem que deve ser fisicamente reservada para que você possa liberar uma ordem de venda para o depósito. Você pode definir uma política de processamento padrão global e substituí-la para clientes específicos conforme necessário. O recurso *Automação de fornecimento sob encomenda* adiciona a capacidade de exibir a política padrão que realmente se aplica a qualquer ordem e aplicar uma substituição específica da ordem, conforme necessário.

- Para definir o padrão de política de processamento global para ordens de venda, consulte **Contas a receber \> Configuração \> Parâmetros de contas a receber**. Em seguida, na guia **Gerenciamento de depósito**, defina o campo **Política de processamento de ordem de venda** como o nome da política que você deseja usar. 
- Para definir uma política de processamento específica do cliente para ordens de venda, acesse **Contas a receber \> Clientes \> Todos os clientes**. Em seguida, na guia **Depósito**, defina o campo **Política de processamento** como o nome da política que você deseja usar.

Para exibir a política padrão aplicável a qualquer ordem e aplicar uma substituição específica da ordem, siga estas etapas.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Abra a ordem de vendas a ser inspecionada ou editada.
1. Selecione a exibição **Cabeçalho**.
1. Na guia rápida **Depósito**, revise e edite os seguintes campos conforme necessário:

    - **Política de processamento de ordem** – selecione a política de processamento a ser usada para a ordem selecionada. A política padrão será substituída. Para usar a política de processamento padrão que é mostrada no campo **Política de processamento padrão**, deixe esse campo em branco.
    - **Política de processamento padrão** – esse campo mostra a política de processamento padrão que será aplicada se o campo **Politica de processamento da ordem** estiver em branco. O campo é somente leitura. Se estiver em branco, nenhuma política de processamento padrão global ou específica do cliente será definida.

    Se o campo **Política de processamento da ordem** e **Política de processamento padrão** estiverem em branco, nenhuma política de processamento será aplicada. No entanto, outras restrições podem estar em vigor e exigir que as reservas ou outras condições sejam atendidas para que a ordem seja liberada.

## <a name="set-the-delivery-mode-and-terms-on-individual-purchase-order-lines"></a>Definir o modo de entrega e os termos em linhas de ordem de compra individuais

Todas as ordens de compra incluem as configurações **Termos de entrega** e **Modo de entrega** no cabeçalho da ordem. O recurso *Automação de fornecimento sob encomenda* adiciona essas configurações a cada linha da ordem. Portanto, você pode definir substituições dos valores **Termos de entrega** e/ou **Modo de entrega** para todas as linhas da ordem, conforme necessário. Para as linhas em que não há substituição definida, o valor do cabeçalho é usado. É possível especificar se uma alteração no valor de um ou dos dois campos no cabeçalho da ordem também deve atualizar todas as linhas.

Para especificar o que deve acontecer com as configurações de linha se um usuário alterar os valores **Termos de entrega** e/ou **Modo de entrega** em um cabeçalho de ordem, siga estas etapas.

1. Acesse **Compras e fornecimento \> Configuração \> Parâmetros de compras**.
1. Na guia **Geral**, na guia rápida **Valores e parâmetros padrão**, selecione o link **Atualizar linhas da ordem**.
1. Na caixa de diálogo **Atualizar linhas da ordem**, nos campos **Atualizar termos de entrega** e **Atualizar modo de entrega**, selecione um dos seguintes valores:

    - *Nunca* – nunca atualizar as linhas da ordem depois que as configurações forem alteradas no cabeçalho da ordem.
    - *Sempre* – sempre atualizar todas as linhas da ordem depois que as configurações forem alteradas no cabeçalho da ordem.
    - *Solicitar* – se um usuário alterar uma ou as duas configurações no cabeçalho da ordem, abra um bot de caixa de diálogo que pergunte se o usuário deseja atualizar todas as linhas para que correspondam à alteração a uma ou às duas configurações.

Para definir as informações de entrega em um cabeçalho da ordem de compra, siga estas etapas.

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. Abra a ordem de compra a ser editada.
1. Selecione a exibição **Cabeçalho**.
1. Na guia rápida **Entrega**, defina os campos **Modo de entrega** e **Termos de entrega**, conforme necessário.
1. Dependendo das configurações na página **Parâmetros de compras**, é possível que o sistema pergunte se você deseja aplicar suas alterações a todas as linhas da ordem.

Para definir as substituições das informações de entrega de uma linha da ordem de compra, siga estas etapas.

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. Abra a ordem de compra a ser editada.
1. Selecione a exibição **Linhas**.
1. Na guia rápida **Linhas de ordem de compra**, selecione a linha a ser editada.
1. Na guia rápida **Detalhes da linha**, na guia **Entrega**, defina os campos **Modo de entrega** e **Termos de entrega**, conforme necessário. Desmarque um ou os dois campos para usar as configurações correspondentes no cabeçalho.

Para ordens intercompanhia, os valores dos campos **Modo de entrega** e **Termos de entrega** em cada linha da ordem de compra serão sincronizados entre a ordem de compra e a ordem de venda relacionada.

## <a name="sync-external-item-ids-and-descriptions-for-intercompany-orders"></a>Sincronizar IDs e descrições de itens externos para ordens intercompanhia

Para ordens intercompanhia, o recurso *Automação de fornecimento sob encomenda* permite que IDs de itens externos e descrições de texto nas linhas da ordem de compra sejam sincronizados com as linhas da ordem de venda intercompanhia relacionada, independentemente de a ordem de compra ser para entrega direta. O recurso também adiciona a capacidade de especificar a conta de cliente externo final em uma ordem de compra intercompanhia. O sistema então extrairá automaticamente os IDs de itens externos e as descrições de texto do registro de cliente externo em vez do registro de fornecedor intercompanhia (interno).

Para configurar um fornecedor intercompanhia para sincronizar IDs de itens externos e nomes de item entre as ordens de compra intercompanhia e suas ordens de venda intercompanhia relacionadas, siga estas etapas.

1. Acesse **Aquisição e fornecimento \> Fornecedores \> Todos os fornecedores**.
1. Selecione o fornecedor intercompanhia a ser configurado.
1. No Painel de Ações, na guia **Geral**, no grupo **Configurar**, selecione **Intercompanhia**.
1. Na página **Intercompanhia**, na guia **Políticas de ordem de compra**, na seção **Ordem de compra intercompanhia -\> Ordem de venda intercompanhia**, marque a caixa de seleção **ID do item externo e nome do item**.

Para especificar a conta de cliente externo final para uma ordem de compra intercompanhia, siga estas etapas. O campo **Conta do cliente** se aplica a ordens de compra intercompanhia. Use-o para especificar o número da conta do cliente que receberá as mercadorias. Quando este campo for definido, as linhas da ordem de compra receberão descrições e números de itens externos da conta do cliente especificada, em vez do fornecedor intercompanhia especificado na ordem de compra. Se você alterar a conta do cliente posteriormente, as descrições e os IDs de itens externos serão atualizados para que correspondam aos valores da nova conta. As descrições de itens externos e os IDs de cada linha também serão sincronizados com a ordem de venda intercompanhia correspondente.

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. Abra a ordem de compra que deseja configurar ou crie uma.
1. Selecione a exibição **Cabeçalho**.
1. Na seção **Referência**, defina o campo **Conta do cliente** como a conta de cliente externo relevante.

Para especificar IDs de itens externos e descrições de texto para uma linha de ordem de compra de uma ordem intercompanhia, siga estas etapas. Os valores que você definir serão sincronizados com as linhas da ordem de venda intercompanhia relacionada, independentemente de a ordem de compra ser para entrega direta.

1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. Abra a ordem de compra que deseja configurar ou crie uma.
1. Selecione a exibição **Linhas**.
1. Na guia rápida **Linhas de ordem de compra**, selecione a linha a ser editada.
1. Na guia rápida **Detalhes da linha**, guia **Geral**, seção **Linha da ordem**, campo **Texto**, forneça uma descrição externa do item especificado na linha da ordem selecionada. Esse valor será sincronizado com a linha da ordem de venda intercompanhia relacionada.
1. Na seção **Referência**, campo **Externo**, forneça um ID de item externo para o item especificado na linha da ordem selecionada. Esse valor será sincronizado com a linha da ordem de venda intercompanhia relacionada.

Para obter mais informações, consulte [Criar e faturar uma ordem de venda intercompanhia para um cliente externo](../sales-marketing/intercompany-sales-order-for-external-customer.md).
