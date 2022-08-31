---
title: Personalizar títulos e instruções de etapas para o aplicativo móvel Warehouse Management
description: Este artigo descreve como criar e mostrar instruções personalizadas para cada etapa de cada fluxo de tarefa que você configurou para o aplicativo móvel Warehouse Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-11
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: faa9bfa320823664603153601c56654170e7e23a
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334466"
---
# <a name="customize-step-titles-and-instructions-for-the-warehouse-management-mobile-app"></a>Personalizar títulos e instruções de etapas para o aplicativo móvel Warehouse Management

> [!IMPORTANT]
> Os recursos descritos neste artigo se aplicam apenas ao novo aplicativo móvel do Warehouse Management. Eles não afetam o antigo aplicativo de depósito, que foi preterido.

Este artigo descreve como criar e mostrar instruções personalizadas para cada etapa de cada fluxo de tarefa que você configurou para o aplicativo móvel Warehouse Management. Quando os funcionários do depósito recebem instruções bem escritas, eles podem começar imediatamente a usar novos fluxos sem precisar de treinamento prévio. Esse recurso oferece os seguintes benefícios:

- **Preparar os trabalhadores mais rapidamente, permitindo que sigam instruções simples para cada etapa da tarefa.** Cada etapa de um fluxo fornece instruções que permitem que os funcionários da linha de frente entendam a tarefa.
- **Fornecer instruções que correspondam a seus próprios processos.** Escrever suas próprias instruções para corresponder a seus processos de negócios e de depósito. Por exemplo, você pode ajustar a terminologia a seu espaço físico e às abreviações locais.

## <a name="turn-the-warehouse-app-step-instructions-feature-on-or-off"></a>Ativar ou desativar o recurso Instruções da etapa do aplicativo de depósito

Para poder usar esse recurso, você deve habilitá-lo para o seu sistema. A partir do Supply Chain Management versão 10.0.29, este recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão ativar ou desativar essa funcionalidade pesquisando o recurso *Instruções da etapa do aplicativo de depósito* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="step-titles-and-step-instructions-in-the-app"></a>Títulos e instruções de etapas no aplicativo

Cada etapa em um fluxo de tarefa no aplicativo móvel Warehouse Management é identificada por uma ID de etapa. Além disso, cada etapa tem um título, um ícone e uma instrução. (Para obter mais informações, consulte [Atribuir ícones de etapas e títulos para o aplicativo móvel Warehouse Management](step-icons-titles.md).)

### <a name="step-titles"></a>Títulos de etapas

Um *título de etapa* é uma breve descrição do que um trabalhador deve fazer durante uma etapa. Ele é mostrado como um texto grande na parte superior da tela, conforme indicado na ilustração a seguir.

![Exemplo de título de etapa no aplicativo móvel Warehouse Management](media/wma-step-title.png "Exemplo de título de etapa no aplicativo móvel Warehouse Management")

> [!TIP]
> Devido ao tamanho de texto grande, você deve tentar manter os títulos das etapas o mais curtos possível. Caso contrário, o texto pode ser cortado. No entanto, para títulos longos, os trabalhadores ainda podem pressionar e segurar o título para abrir uma caixa de diálogo que mostra o texto completo.

### <a name="step-instructions"></a>Instruções da etapa

Uma *instrução de etapa* é uma descrição mais longa que fornece mais informações sobre o que um trabalhador deve fazer durante uma etapa. É mostrada em uma caixa de diálogo pop-up, conforme indicado na ilustração a seguir.

![Exemplo de uma instrução de etapa no aplicativo móvel Warehouse Management](media/wma-step-instructions.png "Exemplo de uma instrução de etapa no aplicativo móvel Warehouse Management")

A instrução da etapa é mostrada automaticamente quando uma etapa é aberta. Os trabalhadores podem ignorá-la tocando em qualquer lugar fora da caixa de diálogo pop-up. Além disso, a caixa de diálogo inclui uma caixa de seleção **Não mostrar novamente** que os trabalhadores podem marcar para evitar que a instrução seja mostrada na próxima vez que executarem a mesma tarefa.

## <a name="load-the-default-setup"></a>Carregar a configuração padrão

Quando você ativar o recurso *Instruções da etapa do aplicativo de depósito* pela primeira vez, seu sistema não conterá títulos de etapas ou instruções personalizáveis. Portanto, a primeira ação que você deve executar é carregar a configuração padrão. A configuração padrão fornece textos para todas as IDs de etapas disponíveis em todos os idiomas com suporte. Para carregar a configuração padrão, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Etapas do dispositivo móvel**.
1. No Painel de Ação, selecione **Criar configuração padrão**. A página é preenchida com as etapas padrão.

## <a name="customize-step-titles-and-instructions"></a>Personalizar os títulos e as instruções das etapas

Para personalizar o título e/ou a instrução de uma etapa em qualquer número de idiomas, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Etapas do dispositivo móvel**.

    A página **Etapas do dispositivo móvel** lista todas as etapas disponíveis para seu sistema. Cada ID de etapa pode ser compartilhada entre qualquer número de itens de menu do dispositivo móvel. Se uma ID de etapa for compartilhada entre vários itens de menu, o mesmo título e instrução serão mostrados para todos esses itens de menu. No entanto, você pode criar substituições para personalizar o título e a instrução para itens de menu específicos. (Para obter mais informações, consulte a próxima seção.)

    A grade inclui as seguintes colunas:

    - **Nome do item de menu** — as linhas em que essa coluna está em branco usam o título de etapa padrão e as instruções que se aplicam a todos os itens de menu do dispositivo móvel para os quais nenhuma substituição foi definida. As linhas em que essa coluna é definida com o nome de um item de menu têm substituições que se aplicam apenas ao item de menu especificado.
    - **ID da etapa** — a ID exclusiva da etapa.
    - **Título para entrada** — o título que é mostrado quando o aplicativo solicita novas informações. Normalmente, os campos da página estão em branco (ou seja, não têm valores predefinidos).
    - **Título para confirmação** — o título que é mostrado quando o aplicativo solicita a confirmação de um valor que já está armazenado no sistema. Normalmente, os campos da página têm valores predefinidos.

1. Encontre a combinação de valores de **ID da etapa** e **Nome do item de menu** que deseja editar e selecione o valor na coluna **ID da etapa**. A página que é aberta lista todas as traduções disponíveis para o título e a instrução da etapa selecionada.
1. Siga uma dessas etapas para personalizar o texto para qualquer idioma. Ambas as opções permitem editar textos para idiomas existentes. No entanto, apenas a primeira opção permite adicionar textos para novos idiomas, enquanto apenas a segunda opção permite exibir e editar textos para todas as substituições específicas de menu existentes do idioma selecionado.

    - Na barra de ferramentas, selecione **Adicionar** para abrir uma caixa de diálogo em que você pode adicionar ou editar textos para qualquer idioma com suporte. Defina o campo **Idioma de referência** com o idioma para o qual deseja exibir os valores. Os valores são mostrados na coluna da esquerda. Defina o campo **Idioma das traduções** com o idioma que você deseja adicionar ou personalizar. Na coluna à direita, edite os valores dos campos **Título para entrada**, **Instrução para entrada**, **Título para confirmação** e **Instrução para confirmação** conforme necessário. Em seguida, selecione **OK**.
    - Na grade, localize e selecione a linha em que o campo **Idioma** está definido com o idioma que você deseja editar. Na barra de ferramentas, selecione **Exibir traduções de &lt;idioma&gt; desta etapa** para abrir uma caixa de diálogo em que você pode editar textos para todas as substituições disponíveis no idioma selecionado. A caixa de diálogo inclui uma grade que tem linhas para os textos padrão (em que o campo **Nome do item de menu** está em branco) e para cada texto de substituição disponível (em que o campo **Nome do item de menu** é definido com o nome do item de menu ao qual a substituição se aplica). Edite os valores dos campos **Título para entrada**, **Instrução para entrada**, **Título para confirmação** e **Instrução para confirmação** conforme necessário. Em seguida, selecione **OK**.

1. Continue a trabalhar até definir todos os títulos e instruções necessários para todos os idiomas exigidos.

## <a name="add-menu-specific-overrides"></a>Adicionar substituições específicas do menu

Conforme mencionado na seção anterior, você pode criar qualquer número de substituições específicas de menu para cada ID de etapa. Você pode usar esse recurso para editar e alterar a instrução para que se ajuste melhor a seu processo de negócios local para um item de menu específico. Por exemplo, para separação de vendas, se sua empresa geralmente fornece IDs de trabalho aos trabalhadores em um documento impresso, você pode fornecer uma dica de que os trabalhadores devem começar digitalizando uma ID de trabalho.

Cada substituição se aplica a um item de menu de dispositivo móvel específico e pode conter qualquer número de traduções. Se não houver substituição para um item de menu, o item de menu usará os textos padrão. Se nenhuma tradução de substituição for definida para um idioma, os textos padrão serão usados, mesmo para itens de menu em que uma substituição esteja definida para outros idiomas.

Para criar e configurar uma substituição, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Etapas do dispositivo móvel**.
1. Na grade, localize e selecione a linha para a qual deve ser criada uma substituição.
1. No Painel de Ações, selecione **Adicionar configuração de etapa**.
1. Na caixa de diálogo suspensa **Adicionar configuração de etapa**, defina o campo **Item de menu** com o nome do item de menu do dispositivo móvel ao qual sua substituição se aplica. Em seguida, selecione **OK**.
1. A página exibida mostra todos os textos disponíveis para a nova substituição. Inicialmente, apenas um idioma é criado. Todos os outros idiomas continuarão a usar os textos padrão, a menos que você adicione esses idiomas aqui. Edite os textos e adicione novos idiomas conforme necessário, como descrito na seção anterior.
