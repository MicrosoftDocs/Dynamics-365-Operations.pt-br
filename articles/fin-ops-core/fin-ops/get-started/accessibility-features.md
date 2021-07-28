---
title: Recursos de acessibilidade
description: Este tópico descreve a funcionalidade desenvolvida para ajudar usuários com diversas deficiências.
author: TLeforMicrosoft
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 5e9d1f33102ed08d9e5c486d4d1490d4b278a28e
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6360278"
---
# <a name="accessibility-features"></a>Recursos de acessibilidade

[!include [banner](../includes/banner.md)]

Este tópico descreve a funcionalidade desenvolvida para ajudar usuários com diversas deficiências a usar este aplicativo. Por exemplo, há recursos para pessoas que usam tecnologias assistivas visuais, como o Narrador do Microsoft Windows.

## <a name="windows-narrator-and-keyboard-only-access"></a>Acesso exclusivo pelo teclado e Narrador do Windows

Cada campo e controle tem uma etiqueta e uma descrição de atalhos aplicáveis. Um leitor de tela pode ler a etiqueta e a descrição.

## <a name="shortcuts-for-the-most-frequently-performed-actions"></a>Atalhos das ações mais executadas

Para a maioria dos usuários, o uso diário do sistema envolve muita entrada de dados e interação com o teclado. Para aperfeiçoar a experiência do usuário, criamos atalhos para auxiliar a movimentação pela tela e atalhos para ações especializadas. Para obter mais informações, consulte [Atalhos de teclado](shortcut-keys.md).

## <a name="navigation-search"></a>Pesquisa de navegação

Qualquer página que é acessada usando o menu Painel de Navegação, o painel à esquerda, também está disponível na caixa de **Pesquisa**. Pressione Alt+G para mover o foco para a caixa de **Pesquisa** e, em seguida, digite o nome ou a descrição da página.

![“Contas bancárias” inserido na caixa de Pesquisa](media/6d08b0be32808221023e2aa92d69fd70.png "'contas bancárias' inserido na caixa de Pesquisa")

Para obter mais informações, consulte [Pesquisa de navegação](navigation-search.md).

> [!NOTE]
> É possível navegar diretamente apenas para as páginas de nível superior. Páginas secundárias dependem de informações ou contexto da página pai.

## <a name="action-search-for-keyboard-only-users-or-for-heads-down-data-entry"></a>Pesquisa de ação para usuários exclusivos do teclado ou para entradas de dados sem erro

Cada ação que é fornecida em uma página pode ser acessada de um teclado pela sequência de tabulação. Informações sobre a sequência de tabulação serão fornecidas posteriormente neste tópico. Para executar ações de forma mais direta, você pode usar a funcionalidade de pesquisa de ação.

### <a name="example"></a>Exemplo

Você deseja executar a ação **Log de notificação por email** exibida no grupo **Notificação por email** na guia **Ordem de venda** no Painel de Ação.

![Ação Log de notificação por email no Painel de Ação.](media/f0d78399e7fafcd85ded1cd1e3d34f3c.jpg "Ação 'Log de notificação por email' no Painel de Ação")

Uma opção é usar o teclado. Pressione Ctrl+F6 para mover o foco para o Painel de Ação e, em seguida, pressione Tab repetidamente para se mover por todas as guias e ações, até focalizar a ação **Log de notificação por email**.

No entanto, também é possível executar a ação de forma mais direta. Em qualquer lugar da página, pressione Ctrl+Apóstrofo (') para exibir a caixa de pesquisa para ações.

![Caixa de pesquisa para ações.](media/80f7e8c5ac412fdf2c8a12f7728f135a.jpg "Caixa de pesquisa para ações")

Na caixa de pesquisa, digite palavras que descrevam a ação. A ação será disponibilizada e você poderá executá-la diretamente. Por exemplo, digitando **email**, **notific** (uma palavra parcial) ou **log**, você pode ir para a funcionalidade de log de notificação por email.

![“Email” inserido na caixa de pesquisa](media/image4.png "'email' inserido na caixa de pesquisa")

![“Notificação” inserido na caixa de pesquisa](media/image5.png "'notificação” inserido na caixa de pesquisa")

![“Log” inserido na caixa de pesquisa](media/image6.png "'log' inserido na caixa de pesquisa")

Quando terminar, pressione Ctrl+Apóstrofo novamente para retornar o foco para o campo com o qual você estava trabalhando antes de executar a pesquisa de ação.

Para obter mais informações, consulte [Pesquisa de ação](action-search.md).

## <a name="tab-sequence"></a>Sequência de tabulação

No uso diário do sistema, nem todo campo será necessário para executar tarefas comuns. Portanto, por padrão, a sequência de tabulação “é otimizada”. As paradas de tabulação são definidas apenas nos campos essenciais para cenários típicos.

No entanto, talvez você note que alguns campos usados por você com frequência para executar tarefas não são incluídos na sequência de tabulação padrão. Nesse caso, se você usa o Narrador do Windows, pode usar as ações do teclado do Narrador do Windows para acessar esses campos e verificar seu conteúdo. Como alternativa, você pode ativar a opção **Sequência de tabulação avançada** na página **Opções**. Essa opção torna todos os campos editáveis e somente leitura parte da sequência de tabulação. Você poderá usar a personalização de página para criar uma sequência de tabulação personalizada e omitir campos que não precisam fazer parte da sequência de tabulação. Para obter mais informações sobre personalização, consulte [Personalizar a experiência do usuário](personalize-user-experience.md).

![Opção de "Sequência de tabulação avançada"](media/8c0f12bbb3f26032997ef0ba95d89b6a.png "Opção de 'Sequência de tabulação avançada'")

## <a name="form-patterns"></a>Padrões de formulário

Quase 90% das páginas do aplicativo são baseadas em um pequeno conjunto de padrões. Esses padrões são referidos como *padrões de formulário*. Cada padrão de formulário é usado para fornecer as ações que são executadas com mais frequência na página. Um padrão do formulário ajuda a garantir familiaridade e facilidade de compreensão, pois ações e dados frequentemente usados estão sempre presentes no mesmo local em páginas diferentes. Devido ao pequeno número de padrões de formulário, os usuários podem entender facilmente o sistema, independentemente do número de páginas nele, e podem usá-lo com segurança depois que eles reconhecerem os padrões de formulário.

Para saber mais sobre padrões de formulário, consulte [Estilos e padrões de formulário](../../dev-itpro/user-interface/form-styles-patterns.md).

## <a name="responsive-layout"></a>Layout responsivo

O produto foi desenvolvido para funcionar em vários dispositivos e fatores forma, das telas menores às maiores com resolução mais alta. Nosso mecanismo de layout responsivo permite que os usuários apliquem zoom em um nível de ampliação de 200 por cento (ou, em alguns cenários, mais de 200 por cento).

Em smartphones e outras telas pequenas, os controles e o layout do formulário se adaptam de forma responsivo para garantir que os dados principais sejam favorecidos. Esses comportamentos responsivos também podem incluir a redução do número de colunas em grupos e guias para uma única coluna, a ocultação de elementos do Shell e o recolhimento do painel de ações.

## <a name="guidance-to-help-developers-and-customers-incorporate-accessible-thinking-in-their-customizations"></a>Orientações para ajudar os desenvolvedores e clientes a incorporar pensamento acessível em suas personalizações

Para saber mais sobre as práticas recomendadas da Microsoft para ativar a acessibilidade, consulte [Acessibilidade em formulários, produtos e controles](../../dev-itpro/user-interface/enable-accessibility.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]