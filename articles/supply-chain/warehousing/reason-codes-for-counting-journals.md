---
title: Códigos de motivo de contagem de estoque
description: Este tópico descreve como configurar e aplicar códigos de motivo para tarefas de contagem.
author: perlynne
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 95f7ceb39d2afef1871f395ed562632865022b39
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345257"
---
# <a name="reason-codes-for-inventory-counting"></a>Códigos de motivo de contagem de estoque

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Os códigos de motivo permitem analisar os resultados de um processo de contagem e quaisquer discrepâncias que ocorrem durante esse processo. Você pode especificar o motivo da contagem como um palete quebrado ou um ajuste de estoque que é baseado nas amostras de estoque. Ao mesmo tempo, você pode usar a funcionalidade de ajuste para lançar o valor de ajustes de estoque disponível na contrapartida apropriada, com base no motivo para cada ajuste de estoque.

## <a name="recommendation"></a>Recomendação

Antes de você configurar o sistema, recomendamos que você defina uma estratégia para trabalhar com códigos de motivo. Por exemplo, tente responder às seguintes questões:

- Os códigos de motivos devem ser obrigatórios nos depósitos?
- Os códigos de motivo devem ser obrigatórios ou opcionais em alguns itens?
- Quantos códigos de motivo você precisa?
- Você precisa selecionar previamente uma lista limitada de códigos de motivo para ajustes?
- Como os usuários do scanner de código de barras usam os códigos de motivo? Os códigos de motivo devem ser pré-selecionados, obrigatórios ou não editáveis?
- Os funcionários do depósito precisam de código de motivo diferente nos scanners móveis? Se a resposta for sim, você pode criar mais itens de menu e atribuí-los a pessoas diferentes.
- Os códigos de motivo devem acionar o lançamento da contrapartida financeira?

## <a name="turn-on-reason-code-features-in-your-system"></a>Ativar recursos de código de motivo no seu sistema

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Se você não vir todos os recursos descritos neste tópico no seu sistema, provavelmente precisará ativar o recurso *Ajustes de lançamento disponível usando códigos de motivo configuráveis associados a contrapartidas*. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Ajustes de lançamento disponível usando códigos de motivo configuráveis associados a contrapartidas*

## <a name="set-up-reason-codes"></a>Configurar códigos de motivo

### <a name="set-up-reason-code-policies"></a>Configurar políticas de código de motivo

Você pode criar várias políticas de código de motivo para controlar quando e como os códigos de motivo de contagem são aplicados. Cada diretiva de código de motivo pode ter um dos dois tipos de código de motivo de contagem (*Opcional* ou *Obrigatório*). As políticas de código de motivo de contagem podem ser usadas para o nível de item ou de depósito.

Para criar uma diretiva de código de motivo, siga estas etapas.

1. Acesse **Gerenciamento de estoque** \> **Configuração** \> **Estoque** \> **Políticas de código de motivos para contagem**.
1. No Painel de Ação, selecione **Novo** para adicionar uma política à grade.
1. Defina o campo **Nome** para a nova política.
1. No campo **Tipo de código de motivo de contagem**, selecione *Obrigatório* ou *Opcional* para especificar se a seleção de um código de motivo deve ser opcional ou obrigatório em um destes processos de ajuste de estoque:

    - Contagem cíclica do (dispositivo móvel)
    - Contagem pontual (dispositivo móvel)
    - Contagem do limite (dispositivo móvel)
    - Ajuste de Entrada (dispositivo móvel)
    - Ajuste de Saída (dispositivo móvel)
    - Diário de Contagem (cliente avançado)
    - Ajuste de quantidade/contagem online (cliente avançado)

Você pode configurar políticas de código de motivo para depósitos individuais e para produtos. A configuração de código de motivo para um produto pode anular a configuração do depósito do produto.

> [!NOTE]
> Para depósitos e itens em que o campo **Política de código de motivo para contagem** esteja definido como *Obrigatório*, o diário de contagem não poderá ser concluído e fechado até que um código de motivo seja fornecido. Para obter mais informações, consulte a próxima seção.

### <a name="assign-counting-reason-code-policies-to-warehouses"></a>Atribuir políticas do código de motivo da contagem a depósitos.

Para atribuir uma política de código de motivo de contagem a um depósito, siga estas etapas.

1. Acesse **Gerenciamento do estoque** \> **Configuração** \> **Divisão do estoque** \> **Depósitos**.
1. No painel da lista, selecione um depósito.
1. No Painel de Ação, na guia **Depósito**, no grupo **Configurar**, selecione **Política de código de motivo para contagem**. Em seguida, na caixa de diálogo **Atribuir política de código de motivo para contagem**, siga uma destas etapas:

    - Para usar a configuração de política para cada item e determinar se os diários de contagem são obrigatórios, não insira um valor (ou exclua o valor existente).
    - Para exigir um código de motivo em diários de contagem para o depósito, selecione uma política de motivo na qual o campo **Tipo de código de motivo para contagem** esteja definido como *Obrigatório*.
    - Se um código de motivo for opcional em diários de contagem para o depósito, selecione uma política de motivo na qual o campo **Tipo de código de motivo para contagem** esteja definido como *Opcional*.

### <a name="assign-counting-reason-code-policies-to-products"></a>Atribuir políticas do código de motivo da contagem a produtos.

Para atribuir uma política de código de motivo de contagem a um produto, siga estas etapas.

1. Acesse **Gerenciamento de informações do produto** \> **Produtos** \> **Produtos liberados**.
1. Selecione um produto na grade.
1. No Painel de Ação, na guia **Produto**, no grupo **Configurar**, selecione **Política de código de motivo para contagem**. Em seguida, na caixa de diálogo **Atribuir política de código de motivo para contagem**, siga uma destas etapas:

    - Para usar a configuração de política para o depósito e determinar se os diários de contagem são obrigatórios para o produto, não insira um valor (ou exclua o valor existente).
    - Para exigir um código de motivo em diários de contagem para o produto, selecione uma política de motivo na qual o campo **Tipo de código de motivo para contagem** esteja definido como *Obrigatório*. Essa configuração substitui qualquer configuração de código de motivo em nível de depósito.
    - Se um código de motivo for opcional em diários de contagem para o produto, selecione uma política de motivo na qual o campo **Tipo de código de motivo para contagem** esteja definido como *Opcional*. Essa configuração substitui qualquer configuração de código de motivo em nível de depósito.

### <a name="set-up-counting-reason-codes"></a>Configurar códigos de motivo para contagem

Para configurar os códigos de motivo para contagem, siga estas etapas.

1. Acesse **Gerenciamento de estoque** \> **Configuração** \> **Estoque** \> **Códigos de motivos para contagem**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.
1. Defina os campos **Código de motivo para contagem** e **Descrição** para a nova linha.
1. Para atribuir uma contrapartida, insira ou selecione um valor no campo **Contrapartida**.

    > [!NOTE]
    > Se uma contrapartida for atribuída a um código de motivo para contagem, quando você lançar um diário de contagem usando o código de motivo para contagem, o valor será lançado na contrapartida atribuída, e não na conta de perfil de lançamentos de estoque padrão.

### <a name="set-up-counting-reason-code-groups"></a><a name="reason-groups"></a>Configurar grupos de código de motivo para contagem

Os *Grupos de códigos de motivo para contagem* podem ser usados como parte dos itens de menu *Ajuste de entrada* e *Ajuste de saída* no aplicativo móvel Warehouse Management para limitar a lista de códigos de motivo para contagem. (Para obter mais informações sobre grupos de código de motivo para contagem, consulte a seção [Configurar itens de menu do dispositivo móvel para ajuste de saída e de entrada](#setup-adjustment-in-out) posteriormente neste tópico.)

1. Acesse **Gerenciamento de estoque** \> **Configuração** \> **Estoque** \> **Grupos de código de motivos para contagem**.
1. No Painel de Ações, selecione **Novo** para adicionar um grupo.
1. Defina os campos **Grupo de motivo para contagem** e **Descrição do grupo** para o novo grupo.
1. No Painel de ações, selecione **Salvar**.
1. Na seção **Detalhes**, selecione **Novo** na barra de ferramentas para adicionar uma linha à grade. Depois, defina o campo **Código de motivo para contagem** para a nova linha. 
1. Repita a etapa anterior para atribuir mais códigos, conforme necessário. Se você tiver que remover um código do grupo, selecione-o e depois selecione **Excluir** na barra de ferramentas.

### <a name="set-up-reason-codes-for-mobile-device-menu-items"></a>Configurar códigos de motivo para itens de menu do dispositivo móvel

Você pode configurar códigos de motivo para os seguintes tipos de ajuste disponíveis:

- Contagem Cíclica
- Contagem Pontual
- Contagem do Limite
- Ajuste de Entrada
- Ajuste de Saída

Na maioria dos casos, você pode definir as seguintes informações para cada item de menu de dispositivo móvel relevante:

- Se o código será for mostrado ao trabalhador do dispositivo móvel durante a contagem.
- O código de motivo padrão que é mostrado em um item de menu do dispositivo móvel.
- Se o usuário pode editar o código de motivo.

#### <a name="set-up-mobile-device-menu-items-for-a-counting-process"></a>Configurar itens de menu do dispositivo móvel para um processo de contagem

Para configurar um item de menu do dispositivo móvel para um processo de contagem, siga as etapas a seguir.

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Itens de menu do dispositivo móvel**.
1. Selecione o item de menu relevante no painel de lista ou crie um novo item de menu.
1. No Painel de Ação, selecione **Contagem cíclica**.
1. No campo **Código de motivo de contagem padrão** , defina o código de motivo padrão que deve ser registrado quando o item de menu de dispositivo móvel é usado para fazer a contagem.
1. No campo **Exibir código de motivo para contagem**, selecione um dos valores a seguir:

    - *Linha* – Mostra o código de motivo após cada variação ser registrada.
    - *Ocultar* – Não mostra o código de motivo.

1. Defina a opção **Editar código de motivo para contagem** como *Sim* para permitir que o trabalhador edite o código de motivo quando ele for mostrado no dispositivo móvel durante a contagem. Defina-o como *Não* para impedir que o trabalhador edite o código.

> [!NOTE]
> O botão **Contagem cíclica** pode ser habilitado em qualquer item de menu de dispositivo móvel onde a contagem pode ser feita. Os exemplos incluem itens de menu para contagens pontuais, trabalho direcionado ao usuário e trabalho direcionado ao sistema.

#### <a name="set-up-mobile-device-menu-items-for-adjustment-in-and-adjustment-out"></a><a name="setup-adjustment-in-out"></a>Configurar os itens de menu do dispositivo móvel para Ajuste de entrada e Ajuste de saída

Para configurar um item de menu do dispositivo móvel para ajuste de entrada e de saída, siga as etapas a seguir.

1. Acesse **Gerenciamento de depósito** \> **Configuração** \> **Dispositivo móvel** \> **Itens de menu do dispositivo móvel**.
1. No Painel de Ação, selecione **Novo** para criar um item de menu.
1. Defina os campos **Nome do item móvel** e **Cargo** para o novo item de menu.
1. Defina o campo **Modo** como *Trabalho*.
1. Defina a opção **Usar trabalho existente** como *Não*.
1. No campo **Processo de criação de trabalho**, selecione *Ajuste de entrada* ou *Ajuste de saída*.
1. Na FastTab **Geral**, defina os seguintes campos. (Todos esses campos são adicionados quando você seleciona *Ajuste de entrada* ou *Ajuste de saída* no campo **Processo de criação de trabalho**.)

    - **Usar guia de processos** – Se você estiver criando um processo de *Ajuste de saída*, certifique-se de definir esta opção como *Sim*. Se você estiver criando um processo de *Ajuste de saída*, esta opção será sempre definida como *Sim*.
    - **Código de motivo de contagem padrão** - Defina o código de motivo padrão que deve ser registrado quando o item de menu de dispositivo móvel é usado para fazer a contagem.
    - **Exibir código de motivo para contagem** - Selecione um dos valores a seguir:

        - *Linha* – Mostra o código de motivo após cada variação ser registrada.
        - *Ocultar* – Não mostra o código de motivo.

    - **Editar código de motivo para contagem** - Defina esta opção como *Sim* para permitir que o trabalhador edite o código de motivo quando ele for mostrado no dispositivo móvel durante a contagem. Defina-o como *Não* para impedir que o trabalhador edite o código.
    - **Grupo de códigos de motivo para contagem** – Selecione um grupo de códigos de motivo se quiser limitar a lista de opções que é apresentada aos trabalhadores. Para obter informações sobre como configurar grupos de códigos de motivo, consulte a seção [Configurar grupos de códigos de motivo para contagem](#reason-groups) anteriormente neste tópico. 

> [!NOTE]
> Quando você atribui um grupo de códigos de motivo para contagem aos itens de menu *Ajuste de entrada* e *Ajuste de saída* em que a opção **Usar guia de processos** esteja definida como *Sim*, você pode obter uma lista limitada dos códigos de motivo para contagem como parte do processamento no aplicativo móvel Warehouse Management.
>
> A opção **Usar guia de processos** também pode ajudar a evitar que grandes quantidades de ajuste ocorram por engano. (Por exemplo, um trabalhador pode digitalizar acidentalmente um código de barras de um número de item em vez de um valor de quantidade.) Para definir essa funcionalidade, defina a opção **Usar guia de processos** como *Sim* para cada item de menu relevante. Em seguida, Acesse **Warehouse Management \> Configuração \> Trabalhador** e defina o campo **Limite de quantidade do ajuste** para cada trabalhador de depósito relevante para especificar a quantidade de ajuste máximo que o trabalhador pode registrar.

## <a name="processing-that-uses-counting-reason-codes"></a>Processamento que usa códigos de motivo para contagem

Quando os trabalhadores usam o aplicativo móvel Warehouse Management, os códigos de motivo são registrados. A menos que um processo de aprovação de contagem tenha sido definido, os códigos de motivo registrados são usados imediatamente como parte do lançamento do diário de contagem, a seguir.

### <a name="cycle-count-approvals"></a>Aprovações de contagem cíclica

Antes de uma contagem ser aprovada, o trabalhador pode alterar o código de motivo associado à contagem. Quando a contagem for aprovada, o código de motivo será inserido nas linhas de diário da contagem.

#### <a name="modify-reason-codes-for-cycle-count-approvals"></a>Modificar códigos de motivo para aprovações de contagem de ciclos

Para modificar uma aprovação de contagem de ciclo, siga estas etapas.

1. Acesse **Gerenciamento de depósito** \> **Contagem cíclica** \> **Trabalho de contagem cíclica com revisão pendente**.
1. Selecione um contagem de ciclo na grade.
1. No Painel de ações, na guia **Trabalho**, selecione **Contagem cíclica**. Em seguida, no código **Motivo**, selecione um novo código de motivo.

Os códigos de motivo são adicionados às linhas do diário nos diários de contagem do tipo *Diário de contagem* .

1. Acesse **Gerenciamento de estoque** \> **Entradas de diário** \> **Contagem de itens** \> **Contagem**.
2. Nos detalhes da linha do diário de contagem, no campo **Código de motivo para contagem**, selecione o código de motivo que corresponde à sua situação atual.

### <a name="view-the-reason-codes-recorded-in-the-counting-history"></a>Visualizar os códigos de motivo registrados no histórico de contagem

Para exibir os códigos de motivo que foram registrados no histórico de contagem, siga estas etapas.

1. Acesse **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Histórico de contagem**.
1. Selecione um registro de contagem de itens no painel de lista.
1. No campo **Código de motivo de contagem**, exiba o histórico de contagem que foi registrado por meio de um código de motivo.

### <a name="use-reason-codes-for-quantity-adjustment-or-online-counting"></a>Usar códigos de motivo para ajuste de quantidade ou contagem online

Para usar um código de motivo para um ajuste de quantidade ou contagem online, siga estas etapas.

1. Acesse **Gerenciamento de estoque \> Consultas e relatórios \> Lista disponível**.
1. No Painel de Ações, selecione **Ajuste de quantidade**.
1. Selecione **Ajuste de quantidade** e no campo **Código de motivo de contagem**, selecione um código de motivo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
