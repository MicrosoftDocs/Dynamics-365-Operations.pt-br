---
title: Módulo seletor de país/região
description: Este tópico aborda o módulo seletor de país/região e descreve como configurá-lo no Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: 1a8eebb589372051272573895a0ae5b4203eef62
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109772"
---
# <a name="countryregion-picker-module"></a>Módulo seletor de país/região

[!include [banner](includes/banner.md)]

Este tópico aborda o módulo seletor de país/região e descreve como configurá-lo no Microsoft Dynamics 365 Commerce.

O módulo seletor de país/região usa o recurso de [detecção e redirecionamento geográfico](geo-detection-redirection.md) no Dynamics 365 Commerce para mostrar as URLs recomendadas aos clientes que solicitam uma URL de site de comércio eletrônico que não esteja associada ao próprio país ou região.

Por exemplo, um cliente no Canadá solicita uma URL de site que não está associada ao Canadá. Nesse caso, o módulo seletor de país/região mostra uma caixa de diálogo que recomenda as URLs de site associadas ao Canadá. A seguinte ilustração mostra um exemplo da caixa de diálogo do seletor de país/região.

![Exemplo de uma caixa de diálogo de seletor de país/região em uma página inicial.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Propriedades do módulo seletor de país/região

| Nome da propriedade              | Alíquota       | descrição |
| -------------------------- | ----------- | ----------- |
| Título                    | Texto        | O cabeçalho que é exibido na parte superior da caixa de diálogo. |
| Subtítulo                 | Texto        | O subtítulo que é exibido abaixo do título. |
| País: cadeia de caracteres para exibição    | Texto        | O nome de exibição de uma opção de URL (por exemplo, "Canadá"). |
| País: substring de exibição | Texto        | Uma substring de exibição opcional para uma opção de URL (por exemplo, "inglês" ou "francês"). |
| País: imagem do país     | Ativo de mídia | Uma imagem opcional associada a uma opção de URL (por exemplo, uma imagem da bandeira do Canadá). |
| País: URL do país       | Texto        | A URL que corresponde ao canal e à localidade que estão configurados para o país ou a região na página **Canais** no construtor de sites do Commerce (**Configurações do site \> Canais**). Essa URL deve corresponder exatamente à URL configurada na página **Canais**. |
| Link de ação                | Link de ação | Um link opcional que é exibido na parte inferior da caixa de diálogo. Por exemplo, esse link pode apontar para uma página interna que fornece uma lista de todos os países e regiões compatíveis com o site. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Adicionar um módulo seletor de país/região a uma página

O módulo seletor de país/região pode ser adicionado ao módulo de cabeçalho diretamente ou por meio de um fragmento compartilhado. Para obter mais informações sobre módulos de cabeçalho, consulte [Módulo de cabeçalho](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Configurar o módulo seletor de país/região no construtor de sites do Commerce

> [!NOTE]
> As URLs que você recomenda aos seus clientes precisam ser configuradas como objetos de país no módulo seletor de país/região.

Para cada URL que você deseja mostrar e recomendar aos clientes, siga estas etapas no construtor de sites do Commerce.

1. Selecione o slot do módulo seletor de país/região.
1. No painel de propriedades, em **Lista de países**, selecione **Adicionar país**.
1. Selecione a caixa de novo **País**.
1. No campo **Exibir cadeia de caracteres**, digite um nome de exibição (por exemplo, **Canadá**).
1. Opcional: no campo **Exibir substring**, insira uma substring de exibição (por exemplo, **Francês** ou **fr-ca**).
1. Opcional: selecione uma imagem na biblioteca de mídia.
1. No campo **URL do país**, insira a URL. Essa URL precisa corresponder exatamente à URL que aparece na página **Canais** e é mapeada para o canal, incluindo a localidade associada ao país ou à região.
1. Selecione **OK**.
1. Repita essas etapas para todas as outras URLs de país que você deseja que o módulo seletor de país/região mostre.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar detecção e redirecionamento geográfico](geo-detection-redirection.md)

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de seletor de sites](site-selector.md)

[Módulo de trilha de navegação](add-breadcrumb.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
