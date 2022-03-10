---
title: Glossário do modelo de página
description: Este tópico descreve os diversos elementos usados nas páginas de um site do Microsoft Dynamics 365 Commerce .
author: phinneyridge
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: intro-internal
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c5ec6dfd9147fd5e054303b4fd612caef78b7467d7f6f4850e46fcc9fb1346f2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758303"
---
# <a name="page-model-glossary"></a>Glossário do modelo de página


[!include [banner](includes/banner.md)]

Este tópico descreve os diversos elementos usados nas páginas de um site do Microsoft Dynamics 365 Commerce .

## <a name="page-element-definitions"></a>Definições de elementos de página

A tabela a seguir fornece um resumo dos termos com os quais você deve se familiarizar quando altera a aparência e o conteúdo do seu site. Para explicações e procedimentos mais detalhados, siga os links.

| Termo | Descrição e notas |
|------|-----------------------|
| [Módulo](work-with-modules.md) | <p>**Definição:** Módulos são blocos de construção que podem ser criados e compõem o esqueleto de uma página da web. Os exemplos incluem os módulos de cabeçalho, herói e de carrossel.</p><p>**Onde estão selecionados:** Os módulos implantados podem ser selecionados e configurados em vários estágios do fluxo de trabalho de criação do site, como os estágios de criação de modelo, layout, página e fragmento.</p><p>**Onde são editados:** Os módulos personalizados são criados no código usando o kit de desenvolvimento de software (SDK). Eles são carregados no seu site, onde ficam disponíveis para seleção.</p> |
| Propriedade do módulo | <p>**Definição:** Propriedades do módulo são configurações específicas que são definidas pelo módulo. Podem ser editadas nas ferramentas de criação de Comércio eletrônico. Por exemplo, as propriedades do módulo são usadas para definir o título e a imagem de plano de fundo de um módulo da faixa.</p><p>**Onde são configuradas:** As propriedades do módulo são selecionadas e configuradas no painel de propriedades que aparece nos ambientes de criação (editores) para modelos, layouts, páginas, fragmentos e configurações de aplicativos.</p> |
| [Modelo](templates-layouts-overview.md) | <p>**Definição:** Os modelos definem as combinações e opções de módulos que devem ser usadas para uma categoria de páginas (por exemplo, páginas de marketing, páginas de categorias e páginas de produtos).</p><p>**Onde são selecionados:** Os modelos podem ser selecionados durante fluxos de trabalho de criação de página ou layout.</p><p>**Onde são editados:** Os modelos são criados no editor do modelo. Nenhum código é necessário para criá-los ou modificá-los.</p> |
| [Layout](templates-layouts-overview.md) | <p>**Definição:** Os layouts definem a seleção final e a organização dos módulos do conjunto de opções do modelo pai. Um layout pode ser configurado para uma única página (*layout personalizado*) ou pode ser compartilhado por várias página (*layout predefinido*).</p><p>**Onde são selecionados:** Os layouts podem ser selecionados durante a criação da nova página ou quando um layout diferente for necessário para uma página existente.</p><p>**Onde são editados:** Os layouts são criados no editor de layout. Nenhum código é necessário para criá-los ou modificá-los.</p> |
| [Instância da página](modify-existing-page.md) | <p>**Definição:** As instâncias da página definem o conteúdo localizado final específico da página para uma única página. Este conteúdo é derivado dos valores das propriedades do módulo.</p><p>**Onde são selecionadas:** As páginas são selecionadas quando as URLs são atribuídas.</p><p>**Onde são editadas:** As páginas são editadas no editor de páginas. Nenhum código é necessário para criá-los ou modificá-los.</p> |
| [Tema](select-site-theme.md) | <p>**Definição:** Os temas definem a Folha de Estilos em Cascata (CSS) e determinam a aparência dos módulos que são renderizados em uma página.</p><p>**Onde é selecionado:** Depois que um tema é carregado para seu site usando o Microsoft Dynamics Lifecycle Services (LCS), ele pode ser selecionado como uma propriedade do módulo do contêiner da página.</p><p>**Onde são editados:** Os temas atualmente são criados e editados usando o SDK. Em seguida, são carregados para seu site usando a LCS.</p> |
| [Fragmento](work-with-fragments.md) | <p>**Definição:** Fragmentos são módulos totalmente configurados que possuem conteúdo localizado que pode ser reutilizado e atualizado centralmente em várias páginas. Por exemplo, um fragmento criado a partir de um módulo de cabeçalho pode ser usado em todos os modelos e em todas as páginas do site e atualizado centralmente em um único local.</p><p>**Onde são selecionados:** Fragmentos podem ser selecionados onde quer que os módulos possam ser selecionados. Eles podem ser substituídos por um módulo para ajudar a aumentar a eficiência por meio da criação reutilizável e centralizada.</p><p>**Onde são editados:** Os fragmentos são editados no editor de fragmentos. Nenhum código é necessário para criá-los ou modificá-los.</p> |
| [URL](create-page-URL.md) | <p>**Definição:** URLs (Uniform resource locators) são endereços que apontam para páginas da Web ou outras URLs.</p><p>**Onde são selecionadas:** as URLs serão selecionadas se os links entre as páginas forem necessários.</p><p>**Onde são editadas:** As URLs são editadas no editor de URL. Nenhum código é necessário para criá-los ou modificá-los.</p> |
| Ativo | <p>**Definição:** Ativos são binários de arquivos que têm uma extensão como .jpg, .docx, .pdf ou .mpg.</p><p>**Onde são selecionados:** Os ativos são selecionados como propriedades do módulo para módulos que os exigem.</p><p>**Onde são editados:** Os ativos são carregados e os metadados associados são editados no gerenciador de ativos.</p> |

## <a name="additional-resources"></a>Recursos adicionais

[Maneiras de adicionar conteúdo](add-manage-content.md)

[Estados de documento e de ciclo de vida](document-states-overview.md)

[Trabalhar com grupos de publicações](publish-groups.md)

[Habilitar e usar o compartilhamento entre canais](cross-channel-sharing.md)

[Trabalhar com módulos](work-with-modules.md)

[Trabalhar com fragmentos](work-with-fragments.md)

[Visão geral de modelos e layouts](templates-layouts-overview.md)

[Personalizar a navegação do site](customize-site-navigation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]