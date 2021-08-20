---
title: Criar a interface de execução de piso de produção
description: Este tópico descreve como criar o conteúdo da interface do usuário para cada configuração.
author: johanhoffmann
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration, JmgProductionFloorExecutionConfigurationTab
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 6332b4b15b277faca506da4ea67fcc3ddb9799153a6fe73a711050ab93bdf565
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782458"
---
# <a name="design-the-production-floor-execution-interface"></a>Criar a interface de execução de piso de produção

[!include [banner](../includes/banner.md)]

Você pode criar o conteúdo da interface do usuário para cada configuração usada pela interface de execução de piso de produção. Por exemplo, os trabalhadores em uma célula de trabalho podem precisar abrir instruções de trabalho no piso de produção, enquanto que, em outra célula de trabalho, instruções não são necessárias. Nesse caso, duas configurações devem ser criadas, uma com um botão para abrir anexos de documentos e uma sem esse botão.

## <a name="design-a-tab"></a>Criar uma guia

Na página **Configurar execução de piso de produção**, você pode criar e configurar guias selecionando **Criar guias** no Painel de Ações.

Cada guia é dividida em quatro seções, conforme mostrado na ilustração a seguir.

![Layout da guia.](media/pfe-tab-layout.png "Layout da guia")

Os seguintes elementos são mostrados na ilustração:

1. Barra de ferramentas principal
1. Barra de ferramentas secundária
1. Exibição principal
1. Exibição detalhada

Para criar e configurar uma nova guia, siga estas etapas:

1. Acesse **Controle de produção \> Configuração \> Execução de fabricação \> Configurar execução de piso de produção**.

1. Selecione **Criar guias** no Painel de Ações para abrir a página **Criar guias**.

    ![A página Criar guias.](media/pfe-design-tabs.png "A página Criar guias")

1. Selecione **Novo** no Painel de Ações.

1. Faça as seguintes configurações no cabeçalho da página:

    - **Nome da guia** - Especifique um nome para a guia.
    - **Exibição principal** - Selecione entre as duas listas de trabalhos predefinidas (*Trabalhos ativos*, *Todos os trabalhos* ou *Minha máquina*).
    - **Exibição detalhada** - Selecione entre um valor em branco ou **Detalhes do trabalho**. Se você selecionar o valor em branco, não haverá uma exibição detalhada na guia. Se você selecionar **Detalhes do trabalho**, a exibição detalhada conterá uma descrição detalhada do trabalho selecionado na lista de trabalhos na exibição principal.

1. Na seção **Barra de ferramentas principal**, escolha quais botões devem estar disponíveis na barra de ferramentas principal. A coluna **Ações disponíveis** mostra uma lista de todos os botões que podem ser adicionados. As colunas **Ações selecionadas** mostram uma lista de todos os botões incluídos na configuração atual. Use os botões para mover itens selecionados entre as colunas, conforme necessário. Use os botões para cima e para baixo ao lado da coluna **Ações selecionadas** para controlar a ordem na qual os botões são apresentados na interface do usuário.

1. Na seção **Barra de ferramentas** **secundária**, escolha quais botões devem estar disponíveis na barra de ferramentas secundária. A coluna **Ações disponíveis** mostra uma lista de todos os botões que podem ser adicionados. As colunas **Ações selecionadas** mostram uma lista de todos os botões incluídos na configuração atual. Use os botões para mover itens selecionados entre as colunas, conforme necessário. Use os botões para cima e para baixo ao lado da coluna **Ações selecionadas** para controlar a ordem na qual os botões são apresentados na interface do usuário.

## <a name="associate-a-tab-with-a-configuration"></a>Associar uma guia a uma configuração

Depois de criar todas as guias necessárias, você pode associá-las a uma configuração.

1. Acesse **Controle de produção \> Configuração \> Execução de fabricação \> Configurar execução de piso de produção**.

    ![Configurar execução de chão de produção.](media/pfe-config-prod-floor-execution.png "Configurar execução de chão de produção")

1. Na FastTab **Seleção de guias**, selecione **Adicionar**.

1. Uma nova linha será adicionada à grade. Para essa nova linha, selecione o nome de uma guia que você deseja adicionar à configuração.

1. Continue adicionando outras guias, conforme necessário.

1. Use os botões **Mover para cima** e **Mover para baixo** na barra de ferramentas para organizar as guias, conforme necessário. As guias serão exibidas da esquerda para a direita na ordem mostrada na captura de tela acima (a guia na parte superior é mostrada à esquerda).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]