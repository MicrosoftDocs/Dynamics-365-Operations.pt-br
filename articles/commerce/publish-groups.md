---
title: Trabalhar com grupos de publicações
description: Este tópico descreve o recurso grupos de publicações no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0a4f19af0cdf9c72add0ec18be84e36c807af9ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969867"
---
# <a name="work-with-publish-groups"></a>Trabalhar com grupos de publicações


[!include [banner](includes/banner.md)]

Este tópico descreve o recurso grupos de publicações no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Sites de comércio eletrônico são constantemente atualizados com novo conteúdo durante o ano. Geralmente, as atualizações são publicadas em lotes para eventos de comércio eletrônico, como feriados, campanhas de marketing sazonais ou lançamentos promocionais. Essas atualizações geralmente exigem que os grupos de conteúdo do site (por exemplo, páginas, imagens, fragmentos e modelos) sejam testados, validados e publicados simultaneamente em uma única ação.

A capacidade de agrupar itens em conjuntos lógicos que publicam itens juntos, em que cada conjunto tem seu próprio ciclo de vida, oferece várias vantagens para os autores do site. No Commerce, esses conjuntos lógicos são conhecidos como grupos de publicações. Eles permitem que os autores do site rastreiem conjuntos de atualizações como suas próprias entidades configuráveis, de teste e publicáveis.

Os autores podem visualizar atualizações em um grupo de publicações preparadas sem afetar o site ativo ou outros grupos de publicação independentes. Os autores podem então agendar a ação publicar para publicar simultaneamente todos os itens no grupo de publicação no site ativo. A capacidade de agrupar, visualizar e programar atualizações para publicação é importante para várias empresas de nível empresarial que geram uma receita anual considerável sobre marcos de atualização do site com base no evento.

As empresas podem incorrer em custos de distribuições de conteúdo lentas ou invalidadas que não ocorrem sem problemas. Os grupos de publicações ajudam a garantir que as inicializações sejam organizadas, validadas e publicadas no tempo. Independentemente de serem grandes ou pequenos, os grupos de publicação fornecem um conjunto de ferramentas valioso que ajuda os autores a organizar e simplificar tarefas contínuas de atualização de site.

## <a name="when-to-use-publish-groups"></a>Quando usar grupos de publicações

Você pode usar os grupos de publicações sempre que precisar preparar e publicar vários documentos juntos. Por exemplo, se o seu site atualiza o conteúdo de cada estação, você pode criar grupos de publicações para esses movimentos de marketing sazonais. O grupo de publicações "Atualização Sazonal de Outono" pode conter novas imagens sazonais, fragmentos que têm mensagens de marketing sazonais, páginas que incluem coleções de produtos sazonais ou outras atualizações de sites sazonais.

Uma vantagem dos grupos de publicações é que você pode testar várias atualizações em paralelo. Por exemplo, logo após a atualização para o grupo de publicações "Atualização Sazonal de Outono", pode haver uma atualização de conteúdo para um feriado específico. Nesse caso, você pode preparar o conteúdo do grupo de publicações "Atualização Sazonal de Outono" ao mesmo tempo em que você prepara o conteúdo de um grupo de publicações "Atualização de Feriados do Outono" subsequente. Cada grupo de publicação contém seu próprio conjunto exclusivo de páginas, imagens, fragmentos, modelos e assim por diante. Você pode preparar, visualizar e validar esses dois grupos de publicações independentemente, mas em uma linha de tempo simultânea. Cada grupo de publicação pode ser agendado para ser ativado no seu site em datas e horários específicos.

## <a name="turn-on-the-publish-groups-feature"></a>Ativar o recurso grupos de publicações

O recurso grupos de publicação é opcional e deve ser habilitado para o seu site.

Para ativar o recurso grupos de publicação do seu site nas ferramentas de criação do Commerce, siga estas etapas.

1. No painel de navegação esquerdo, selecione **Configurações de Site** para expandi-lo.
1. Em **Configurações de Site**, selecione **Recursos**.
1. Defina a opção de **Grupos de publicação** como **Ativada**.

## <a name="create-a-publish-group"></a>Criar um grupo de publicação

Para criar um grupo de publicação para seu site nas ferramentas de criação do Commerce, siga estas etapas.

1. No painel de navegação esquerdo, selecione **Grupos de Publicação**.
1. Na barra de comandos superior, selecione **Novo**.
1. Na caixa de diálogo **Criar Grupo de Publicação**, em **Publicar Nome do Grupo**, informe um nome descritivo. Em seguida, selecione **OK**.

## <a name="set-the-publish-group-authoring-context"></a>Definir o contexto de criação do grupo de publicações

No Commerce, o contexto de criação padrão é o contexto de site ativo. O contexto de criação do site ativo é o modo de exibição padrão, no qual você pode exibir e fazer alterações diretamente no seu site sem usar um grupo de publicações. Ele representa as atualizações diretas mais recentes para a versão publicada do seu site. Se o controle de contexto em **Grupos de Publicação** no painel de navegação esquerda mostrar o nome **Site ativo**, você está trabalhando no contexto de criação do site ativo. **Site ativo** é o nome padrão do controle de contexto. Caso contrário, o controle de contexto mostra o nome de um grupo de publicações.

Para trabalhar em um grupo de publicação, você deve alternar para o contexto de criação do grupo de publicação. Para definir o contexto do grupo de publicação, siga uma destas etapas.

- No painel de navegação esquerdo, selecione o controle de contexto diretamente em **Grupos de Publicação** e, em seguida, selecione o nome do grupo de publicação na lista de opções que é exibida. O controle de contexto é renomeado e mostra o nome do grupo de publicação.
- No painel de navegação esquerdo, selecione **Grupos de Publicação** e, em seguida, **Grupos de Publicação**, selecione o nome do grupo de publicações. O controle de contexto é renomeado e mostra o nome do grupo de publicação.

Depois de definir o contexto de criação do grupo de publicação, você estará trabalhando nesse contexto de grupo de publicação ao visualizar e editar o conteúdo do site.

Para retornar ao contexto de criação de site em tempo real padrão, selecione o controle de contexto e, em seguida, **Site ativo**.

## <a name="add-pages-or-other-items-to-a-publish-group"></a>Adicionar páginas ou outros itens a um grupo de publicações

Depois de selecionar um contexto de criação de grupo de publicação, e o controle de contexto no painel de navegação esquerdo mostrar seu nome, você pode criar conteúdo da mesma forma que faz no contexto do site ativo padrão. Você também pode adicionar páginas existentes ou outros itens de outros grupos de publicações ou do contexto do site ativo.

Para copiar páginas existentes para um grupo de publicação, siga estas etapas.

1. Selecione o contexto de criação a ser copiado e, em seguida, no painel de navegação esquerdo, selecione **Páginas**.
1. Selecione a página a ser adicionada a um grupo de publicações.
1. Na barra de comandos, selecione **Copiar para grupo de Publicações**.
1. Na caixa de diálogo **Selecionar um Grupo de Publicação** selecione o grupo de publicações para ser adicionado na página e selecione **OK**.

Você pode usar as mesmas etapas básicas para criar páginas de produtos, URLs, modelos, layouts, fragmentos e ativos da biblioteca de mídia personalizados, ou para adicionar itens existentes desses tipos a um grupo de publicações.

## <a name="validate-a-publish-group"></a>Validar um grupo de publicações

Para verificar se todas as dependências no conteúdo do grupo de publicações estão satisfeitas e se todas as validações foram passadas, você pode executar a validação para identificar quaisquer problemas que devam ser resolvidos antes da programação de uma ação publicada.

Para validar o grupo de publicações antes de agendá-lo, siga estas etapas.

1. No painel de navegação esquerdo, selecione **Grupos de Publicação**.
1. Selecione o grupo de publicação a ser validado.
1. Na barra de comandos, selecione **Validar**.

A validação é executada em todo o conteúdo no grupo de publicação. Quaisquer problemas que impeçam uma ação de publicação bem-sucedida são mostrados em uma caixa de notificação que aparece no canto superior direito.

> [!NOTE]
> A validação é sempre executada automaticamente quando um grupo de publicações é agendado. Porém, o botão **Validar** na barra de comandos é útil porque ajuda a identificar problemas que você deve corrigir antes de tentar agendar um grupo de publicação para ficar ativo.

## <a name="schedule-a-publish-group-to-go-live"></a>Agendar um grupo de publicações para ficar ativo

Para agendar um grupo de publicações para ficar ativo no seu site, siga estas etapas.

1. No painel de navegação esquerdo, selecione **Grupos de Publicação**.
1. Em **Grupos de Publicações**, selecione o grupo de publicação para agendar.
1. Na barra de comandos, selecione **Editar Agendar**. A caixa de diálogo **Editar Agenda** será exibida.
1. Selecione a data e a hora em que o grupo de publicação deve ficar ativo e selecione **OK**.

Para cancelar a agenda de um grupo de publicação, siga as mesmas etapas, mas selecione **Cancelar agenda do Grupo de publicação** na caixa de grupo **Editar Agendamento**.

> [!NOTE]
> Os grupos de publicações de grande porte podem levar até um minuto ou dois para serem publicados quando a hora agendada chegar. Lembre-se de que uma ação de publicação não é instantânea e que os grupos de publicações menores serão publicados mais rapidamente.

## <a name="publish-groups-faq"></a>Perguntas frequentes do grupos de publicação

**Quantos itens podem estar em um grupo de publicações?**

No momento, há um limite de 2.000 itens por grupo de publicação. Saiba que os grupos de publicações de grande porte podem levar vários minutos para serem publicados quando a hora agendada chegar.

**Os grupos de publicação são como "ramificações" de código na terminologia de desenvolvimento de software?**

Sim e não. Os grupos de publicações podem ser considerados versões ramificadas do seu site. Dessa forma, eles funcionam como ramificações. No entanto, não há o conceito de mesclagem no nível de itens individuais. O item que é publicado por último substitui apenas o que existia anteriormente e a ação de publicação mais recente sempre substitui as ações publicadas anteriores.

**Posso agendar dois grupos de publicação ao vivo ao mesmo tempo?**

Nº Por motivos de desempenho e conflito, o sistema forçará você a escalonar grupos de publicação agendados com pelo menos cinco minutos de diferença.

**Posso usar grupos de publicação para agendar itens de back-office do omnicanal, como descontos e atualizações de produtos?**

No momento, o recurso de grupos de publicação oferece suporte somente ao conteúdo do site. No entanto, a Microsoft está ciente de que a integração com cenários de mercadorias de back-office poderia ser valiosa para a coordenação e a automação de lançamentos da campanha do omnicanal.

## <a name="additional-resources"></a>Recursos adicionais

[Maneiras de adicionar conteúdo](add-manage-content.md)

[Glossário do modelo de página](page-elements-overview.md)

[Estados de documento e de ciclo de vida](document-states-overview.md)

[Habilitar e usar o compartilhamento entre canais](cross-channel-sharing.md)

[Trabalhar com módulos](work-with-modules.md)

[Trabalhar com fragmentos](work-with-fragments.md)

[Visão geral de modelos e layouts](templates-layouts-overview.md)

[Personalizar a navegação do site](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]