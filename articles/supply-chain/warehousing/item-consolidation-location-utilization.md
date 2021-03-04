---
title: Consolidação de itens - utilização do local
description: Este tópico fornece informações sobre a funcionalidade que facilita para os gerentes de depósito exibir e filtrar a utilização volumétrica de locais no depósito. Os gerentes podem selecionar locais e criar um trabalho de movimentação de estoque diretamente na página Consolidação de Itens para consolidar itens e, assim, fazer melhor uso do espaço do depósito.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6a328b20c1cfb2fc376ab4656c64cf585a5aa015
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422508"
---
# <a name="item-consolidation---location-utilization"></a>Consolidação de itens - utilização do local

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre a funcionalidade que facilita para os gerentes de depósito exibir e filtrar a utilização volumétrica de locais no depósito. Os gerentes podem selecionar locais e criar um trabalho de movimentação de estoque diretamente na página **Consolidação de Itens** para consolidar itens e, assim, fazer melhor uso do espaço do depósito.

## <a name="turn-on-the-features"></a>Ativar os recursos

Para poder usar os recursos descritos neste tópico, você deve ativá-los no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status dos recursos e ativá-los se necessário. Ative os dois recursos a seguir, na ordem em que aparecem listados. (Os dois recursos são para o módulo **Gerenciamento de depósito**.)

1. Status da localização do depósito
2. Utilização do local de consolidação do item

## <a name="warehouse-location-status"></a>Status da localização do depósito

O recurso *Status da localização do depósito* adiciona quatro novos campos à página **Locais** para rastrear mais informações sobre o estado atual do local:

- **Número do item** — o item que está no local no momento. Se o local contiver vários itens, este campo ficará em branco.
- **Data e hora da última atividade** — o carimbo de data/hora da última transação de depósito executada no local.
- **Data de classificação por vencimento** — a data em que o estoque no local foi trazido para o depósito. Essa data é calculada com base na data de classificação por vencimento da placa de licença. Embora essa data seja precisa para locais rastreados por placa de licença, ela pode não ser precisa em locais que não são rastreados por placa de licença.
- **Status do local** – o status do local. Há quatro valores disponíveis:

    - **Indeterminado** – O perfil de localização não rastreia o status. Portanto, o status atual é desconhecido.
    - **Vazio** – Não há estoque no local no momento.
    - **Separação** – Transações de saída foram executadas no local depois do último esvaziamento.
    - **Armazenamento** – Apenas transações de entrada foram executadas desde o último esvaziamento do local.

Esses campos permitem que os gerentes de depósito tenham uma visão geral melhor do status dos locais no depósito. Eles também permitem relatórios e filtragem mais avançados.

## <a name="set-up-item-consolidation-and-location-utilization"></a>Configurar a consolidação de itens e a utilização do local

Esta seção descreve como preparar o sistema para usar a consolidação de itens e a utilização do local. Os procedimentos usam valores de exemplo dos dados de demonstração padrão. Se você pretende trabalhar no cenário de exemplo fornecido mais adiante neste tópico, selecione a entidade legal **USMF** (que contém os dados de demonstração padrão) e crie cada registro descrito nesta seção. Se você não planeja trabalhar no cenário de exemplo, os valores fornecidos aqui podem ser considerados exemplos dos tipos de configuração que você deve executar para usar os recursos.

### <a name="released-product"></a>Produto liberado

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. No campo **Número do item**, selecione *M9201* e abra a página de detalhes.
1. No Painel de Ação, na guia **Gerenciar estoque**, no grupo **Depósito**, selecione **Dimensões físicas**.
1. Na página **Dimensão Física**, no Painel de Ação, selecione **Novo**.

    Uma nova linha é adicionada à grade. O campo **Nº de itens** é predefinido.

1. No campo **Unidade**, selecione *unidade*. Os demais campos na linha são definidos automaticamente.
1. Selecione **Salvar** e feche a página.

### <a name="location-profile"></a>Perfil de localização

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.
1. Na lista de perfis de localização, selecione **FLOOR-05**.
1. No Painel de Ações, selecione **Editar**.
1. Na FastTab **Geral**, verifique se as duas opções a seguir estão definidas como *Sim*:

    - Habilitar o item no local
    - Habilitar o status local

1. Selecione **Salvar**.

    > [!IMPORTANT]
    > Se as opções **Habilitar o item no local** e **Habilitar o status do local** já tiverem sido definidas como *Sim*, vá para as instruções para configurar a FastTab **Dimensões** na etapa 10. Se as opções ainda não estiverem definidas como *Sim*, você deverá executar uma verificação de consistência do módulo **Gerenciamento de depósito** depois de defini-las manualmente. Nesse caso, vá para a próxima etapa.

1. Para executar a verificação de consistência, vá para **Administração do sistema \> Tarefas periódicas \> Banco de dados \> Verificação de consistência**.
1. Na caixa de diálogo **Verificação de consistência**, defina os seguintes valores:

    - **Módulo:** *Gerenciamento de Depósito*
    - **Verificar/Corrigir:** *Corrigir*
    - **Data inicial:** deixe esse campo em branco.
    - **Verificação de consistência do status local do depósito:** marque essa caixa de seleção.

1. Selecione **OK**.

    > [!TIP]
    > Você receberá uma notificação quando a verificação de consistência for concluída. Abra a [Central de Ações](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) para ver a mensagem. Selecione **Detalhes da mensagem** para exibir os detalhes.
    >
    > Se a mensagem da verificação de consistência afirmar "Informações de status local incorretas encontradas para local XXXX no depósito XX", você deverá executar a verificação novamente. Desta vez, defina o campo **Verificar/Corrigir** como *Corrigir erro*. Veja as mensagens para ter certeza de que nenhum erro foi encontrado.

1. Agora você deve terminar de configurar o perfil de localização. Volte para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de locação**, selecione o perfil de localização **FLOOR-05** e, no Painel de Ação, selecione **Editar**.
1. Na FastTab **Dimensões**, defina os seguintes valores:

    - **Porcentagem de utilização de volume:** *100*
    - **Método volumétrico usado para a localização de estoque:** *Usar volume da localização*
    - **Altura real da localização:** *10*
    - **Largura real da localização:** *10*
    - **Profundidade real da localização:** *10*
    - **Peso máximo:** *100*

1. Selecione **Salvar**.

### <a name="mobile-device-menu-items"></a>Itens de menu do dispositivo móvel

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. No Painel de Ação, selecione **Novo** para criar um item de menu para classificação.
1. No cabeçalho, defina os seguintes valores:

    - **Nome do item de menu:** *Ajustar em*
    - **Título:** *Ajustar em*
    - **Modo:** *Trabalho*
    - **Usar trabalho existente:** *Não*

1. Na FastTab **Geral**, defina os seguintes valores:

    - **Processo de criação de trabalho:** *Ajuste em*
    - **Tipos de ajuste de estoque:** *Ajustar em*

1. Selecione **Salvar**.

### <a name="mobile-device-menu"></a>Menu de dispositivos móveis

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
1. Na lista de menus, selecione **Estoque**.
1. No Painel de Ações, selecione **Editar**.
1. Na lista **Menus e Itens de Menu Disponíveis**, localize e selecione o item de menu **Ajustar em**.
1. Selecione o botão de seta para a direita para mover **Ajustar em** para a lista **Estrutura de menu**. Dessa forma, você adiciona o novo item de menu ao menu selecionado.
1. Selecione **Salvar**.

### <a name="movement-types"></a>Tipos de movimento

1. Vá para **Gerenciamento de depósito \> Configuração \> Estoque \> Tipos de movimento**.
1. No Painel de Ação, selecione **Novo** e, depois, defina os seguintes valores:

    - **Código do tipo de movimento:** *CONSOLIDAR*
    - **Descrição:** *Consolidar locais*
    - **ID da classe de trabalho:** *InvMov*

1. Selecione **Salvar**.

## <a name="example-scenario"></a>Cenário de exemplo

O cenário a seguir usa o aplicativo de depósito em um dispositivo móvel para fazer um *ajuste em* estoque em dois locais no depósito.

### <a name="add-inventory-to-locations"></a>Adicionar estoque a locais

1. Entre no dispositivo móvel como um usuário configurado para o depósito *51*.
1. Vá para **Estoque \> Ajustar em**.

    Agora você vai inserir o primeiro ajuste de local.

1. Na tarefa **Ajuste em**, selecione o local para fazer o ajuste de estoque. No campo **LOC**, selecione *LP-001*.
1. Confirme o local.
1. Crie uma ID de placa de licença para o item que será adicionado ao local. No campo **LP**, insira *LP00101*.
1. Confirme a placa de licença.
1. Insira o item que será adicionado à placa de licença. No campo **ITEM**, insira *M9201*.
1. Confirme o item.
1. Insira a quantidade do item que será adicionado. No campo **QTD**, insira *10*.
1. Confirme a quantidade.

    Você receberá uma mensagem "Trabalho Concluído". Agora você vai inserir o segundo ajuste de local.

1. Na tarefa **Ajuste em**, selecione o local para fazer o ajuste de estoque. No campo **LOC**, selecione *LP-002*.
1. Confirme o local.
1. Crie uma ID de placa de licença para o item que será adicionado ao local. No campo **LP**, insira *LP00201*.
1. Confirme a placa de licença.
1. Insira o item que será adicionado à placa de licença. No campo **ITEM**, insira *M9201*.
1. Confirme o item.
1. Insira a quantidade do item que será adicionado. No campo **QTD**, insira *15*.
1. Confirme a quantidade.

    Você receberá uma mensagem "Trabalho Concluído".

1. Selecione o botão Menu (também chamado de hambúrguer ou botão de hambúrguer) e clique em **Cancelar** para sair da tarefa **Ajuste em**.

### <a name="consolidate-locations"></a>Consolidar locais

1. Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Consolidação de itens**.
1. No cabeçalho, selecione um depósito para fazer a consolidação. No campo **Depósito**, insira *51*.

    É mostrado um registro para cada local onde o item *M9201* foi ajustado. A coluna **Porcentagem de utilização** mostra a utilização volumétrica de cada local.

1. Para consolidar o estoque, selecione todos os locais que devem ser consolidados e, no Painel de Ação, selecione **Consolidar Estoque**.
1. Na caixa de diálogo **Consolidar estoque**, especifique o tipo de local e movimento que deve ser usado para criar o trabalho de movimento de estoque. Defina os seguintes valores:

    - **Local:** *LP-001*
    - **Código do tipo de movimento:** *CONSOLIDAR*

1. Selecione **OK**.
1. Você receberá uma mensagem informativa que mostra o trabalho de movimento criado. Anote a ID do trabalho de movimento.

### <a name="view-movement-work"></a>Exibir trabalho de movimento

1. Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.
1. Exiba o trabalho que foi criado. Use a ID do trabalho de movimento da consolidação do estoque para filtrar ou pesquisar a grade de trabalho.

    Nesse cenário, um local existente que tinha estoque foi usado como local da consolidação de estoque. Por isso apenas uma ID de trabalho foi criada.

    > [!NOTE]
   > O sistema cria uma ID de trabalho para cada movimento a ser concluído. Se você especificar um local que já contém estoque, somente uma ID de trabalho será criada. Se especificar um novo local, duas IDs de trabalho serão criadas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]