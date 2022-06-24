---
title: Conectar um experimento e editar variações
description: Este artigo descreve como conectar um experimento em um serviço de terceiros ao Dynamics 365 Commerce e como editar variações para o experimento.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: dcdbd61976402ddd719ece184a86692fbc7c628d
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942813"
---
# <a name="connect-an-experiment-and-edit-variations"></a>Conectar um experimento e editar variações

Este artigo descreve como conectar seu experimento no Commerce e fazer alterações nas variações para que elas se alinhem com a hipótese. 

O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce. Etapas adicionais são abordadas em artigos separados.

[ ![Jornada de usuário de experimentação - Conectar e editar.](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)

Depois de [configurar seu experimento](experimentation-setup.md) em um serviço de terceiros, você conectará o experimento no Dynamics 365 Commerce e editará as variações do experimento.

## <a name="connect-your-experiment"></a>Conectar seu experimento
Para conectar seu experimento, você iniciará o assistente **Conectar experimento**. O assistente o conduz pelas etapas necessárias para conectar seu experimento. Quando você concluir o assistente, seu experimento será conectado e as variações serão criadas e estarão prontas para serem editadas.

Para começar a conectar sua experiência no construtor de sites do Commerce, siga estas etapas.

1. Para iniciar o assistente **Conectar experimento**, selecione **Experimentos** no painel de navegação esquerdo e selecione **Conectar**. Como alternativa, você pode acessar o assistente de uma página ou o editor de fragmentos editando-o e selecionando **Conectar experimento** na barra de comandos.

    > [!NOTE]
    > - Uma página pode ser conectada somente a um experimento de cada vez. Para conectar uma página a um experimento diferente, primeiro exclua o experimento ao qual a página está conectada no momento.
    > - Só é possível executar experimentos em páginas com um layout personalizado. Se a página tiver um layout predefinido, converta-o em um layout personalizado primeiro. Você pode fazer isso acessando a página e selecionando **Converter em layout personalizado** na barra de comandos. Para obter mais informações sobre layouts, consulte [Layouts predefinidos e personalizados](templates-layouts-overview.md#preset-and-custom-layouts). 

1. Se você estiver se conectando a um experimento na guia **Experimentos** no painel de navegação esquerdo, selecione o nome do experimento na lista que é exibida.
1. Selecione a página ou o fragmento em que você deseja executar o experimento.
1. Na etapa final do assistente, selecione **Gerar variações e sair do assistente**. As variações são criadas para o experimento. 

> [!NOTE]
> Se você deseja agendar quando seu experimento será publicado no seu site ativo, certifique-se de que o conteúdo que você deseja associar ao experimento esteja disponível em um grupo de publicação *antes* de conectar o experimento. Para obter mais informações sobre grupos de publicações, consulte [Trabalhar com grupos de publicação](publish-groups.md).

## <a name="edit-your-variations"></a>Editar suas variações

Ao sair do assistente **Conectar o experimento**, as variações são criadas para você. Siga as etapas abaixo para editar as variações de modo que elas reflitam as opções que você precisa verificar na hipótese de experimento.

1. Na exibição do editor, use o menu suspenso de variações abaixo da barra de comandos para editar cada variação com base na hipótese original. Também pode ser necessário estabelecer um controle ou uma variação de base, deixando uma das variações inalteradas.
1. Selecione o módulo a ser experimentado, selecione as reticências (...) e, em seguida, selecione **Adicionar ao experimento**.

> [!NOTE]
> Pense na possibilidade de estabelecer um controle ou uma variação de base, deixando uma das variações inalteradas.

## <a name="previous-step"></a>Etapa anterior
[Configurar um experimento](experimentation-setup.md) 


## <a name="next-step"></a>Próxima etapa
[Visualizar e publicar um experimento](experimentation-preview-publish.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
