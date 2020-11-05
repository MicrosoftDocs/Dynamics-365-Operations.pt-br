---
title: Conectar um experimento e editar variações
description: Este tópico descreve como conectar um experimento em um serviço de terceiros ao Dynamics 365 Commerce e como editar variações para o experimento.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: ea1da0a7dc90b7197f3ee532bccc55d2ddbe4ddd
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930142"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Conectar um experimento e editar variações

Este tópico descreve como conectar seu experimento no Commerce e fazer alterações nas variações para que elas se alinhem com a hipótese. O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce. Etapas adicionais são abordadas em tópicos separados.

[ ![Jornada de usuário de experimentação - conectar e editar](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Depois de [configurar seu experimento](experimentation-setup.md) em um serviço de terceiros, você conectará o experimento no Dynamics 365 Commerce e editará as variações do experimento.

## <a name="planning-considerations"></a>Considerações de planejamento

Antes de conectar seu experimento no Commerce, você precisará tomar algumas decisões que afetam a forma como o Commerce gerencia o conteúdo.

### <a name="determine-the-scope-of-your-experiment"></a>Determine o escopo do seu experimento
Ao conectar um experimento, você é solicitado a definir o escopo do experimento. Os experimentos são definidos como escopo **parcial** ou escopo **inteiro**.
- Escolha **parcial** se desejar conduzir um experimento em uma parte específica de uma página. Se você selecionar essa opção, deverá identificar os módulos incluídos no experimento. As alterações feitas nas partes da página ou no fragmento padrão que não estão relacionados ao experimento são automaticamente sincronizadas entre variações.
- Escolha **inteiro** se desejar conduzir um experimento em uma página ou fragmento inteiro. Cópias separadas da página ou do fragmento padrão são criadas. Você não precisará selecionar quais módulos serão incluídos no experimento porque toda a superfície de edição está disponível para alteração. Você pode adicionar, excluir e reordenar os módulos conforme necessário. No entanto, se forem feitas alterações na página padrão ou no fragmento ao qual o experimento está associado, essas alterações precisarão ser sincronizadas manualmente em todas as variações.

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> Se você associar seu experimento a uma página que usa um layout, só poderá criar o escopo do experimento como **inteiro**.

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a>Decida se deseja agendar quando seu experimento será publicado
Se você deseja agendar quando seu experimento será publicado no seu site ativo, certifique-se de que o conteúdo que você deseja associar ao experimento esteja disponível em um grupo de publicação *antes* de conectar o experimento. 

Para obter mais informações sobre grupos de publicações, consulte [Trabalhar com grupos de publicação](publish-groups.md).


## <a name="connect-your-experiment"></a>Conectar seu experimento
Para conectar seu experimento, você iniciará o assistente **Conectar experimento**. O assistente o conduz pelas etapas necessárias para conectar seu experimento. Quando você concluir o assistente, seu experimento será conectado e as variações serão criadas e estarão prontas para serem editadas.

1. Para iniciar o assistente, selecione a guia **Experimentos** no construtor de sites e selecione **Conectar**. Como alternativa, o assistente pode ser acessado de um editor de página ou fragmento. No modo de edição, selecione **Conectar experimento** na barra de comandos.

> [!NOTE]
> Uma página pode ser conectada somente a um experimento de cada vez. Para conectar uma página a um experimento diferente, primeiro exclua o experimento ao qual a página está conectada no momento.

1. Escolha a página ou o fragmento em que você deseja executar o experimento.
1. Defina o escopo de experimentação como **parcial** ou **inteiro**, com base na opção feita na seção [Determinar o escopo do seu experimento](#determine-the-scope-of-your-experiment) acima.
    > [!NOTE]
    > O sinalizador de recursos **Experimento em páginas ou fragmentos** deverá estar habilitado se você quiser experimentar em uma página inteira ou fragmento. Consulte o tópico [Experimentação no Dynamics 365 Commerce](experimentation-overview.md) para obter mais informações.
    
1. Na etapa final do assistente, selecione **Gerar variações e sair do assistente**. As variações são criadas para o experimento. 

## <a name="edit-your-variations"></a>Editar suas variações
Quando você sair do assistente, as variações serão criadas para você. 

Em seguida, edite as variações para que reflitam as opções que você precisa verificar na hipótese de experimento. Escolha um dos procedimentos a seguir que corresponda ao escopo escolhido para seu experimento na seção [Determinar o escopo do experimento](#determine-the-scope-of-your-experiment) acima.

### <a name="edit-variations-for-experiments-with-partial-scope"></a>Editar variações de experimentos com escopo parcial
Siga estas etapas se você tiver definido o escopo do seu experimento como **parcial** no assistente **Conectar experimento**.

1. Na exibição do editor, use o menu suspenso de variações abaixo da barra de comandos para editar cada variação com base na hipótese original. Também pode ser necessário estabelecer um controle ou uma variação de base, deixando uma das variações inalteradas.
1. Selecione o módulo a ser experimentado, selecione as reticências (...) e, em seguida, selecione **Adicionar ao experimento**.

### <a name="edit-variations-for-experiments-with-entire-scope"></a>Editar variações de experimentos com escopo inteiro
Se você tiver definido o escopo do seu experimento como **inteiro** no assistente **Conectar experimento**, na exibição do editor, use o menu suspenso de variações abaixo da barra de comandos para editar cada variação com base na hipótese original. 

> [!NOTE]
> Em qualquer um dos casos, também poderá ser necessário estabelecer um controle ou uma variação de base, deixando uma das variações inalteradas.

## <a name="previous-step"></a>Etapa anterior
[Configurar um experimento](experimentation-setup.md) 


## <a name="next-step"></a>Próxima etapa
[Visualizar e publicar um experimento](experimentation-preview-publish.md)