---
title: Módulo seletor de país/região
description: Este artigo aborda o módulo seletor de país/região e descreve como configurá-lo no Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2021-08-12
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: d20b3be008a37b1c86e6fefe0ccc90c581e18340
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861983"
---
# <a name="countryregion-picker-module"></a>Módulo seletor de país/região

[!include [banner](includes/banner.md)]

Este artigo aborda o módulo seletor de país/região e descreve como configurá-lo no Microsoft Dynamics 365 Commerce.

O módulo seletor de país/região usa o recurso de [detecção e redirecionamento geográfico](geo-detection-redirection.md) no Dynamics 365 Commerce para mostrar as sites recomendados aos clientes que solicitam uma URL de site de comércio eletrônico que não esteja associada ao próprio país ou região.

Por exemplo, um cliente no Canadá solicita uma URL de site que está associada a um país que não seja o Canadá. Nesse caso, o módulo seletor de país/região mostra uma caixa de diálogo que recomenda as URLs de site associadas ao Canadá. 

## <a name="how-it-works"></a>Como funciona

Quando a detecção geográfica e o redirecionamento são habilitados para um site, e um cliente solicita uma URL do site, o país que é detectado para o cliente e a URL solicitada são usados para determinar se a URL está mapeada para o país em que o cliente está. O mapeamento entre URLs e países é definido na página **Canais** em **Configurações do site** no criador de sites do Commerce. 

Se a URL da solicitação não corresponder a qualquer URL mapeada para o país do cliente, a lista de uma ou mais URLs mapeadas para aquele país será retornada na resposta. O seletor de país/região compara cada URL nessa lista com as URLs que foram configuradas no módulo de país/região. Para cada combinação exata que é encontrada, o seletor de país/região processa o título de exibição, subtítulo e imagem para essa URL e vincula esses elementos usando a URL.

Quando um cliente seleciona uma opção no seletor de país/região, eles são levados para a URL do hiperlink. Essa URL é gravada no cookie **\_msdyn365\_\_\_site\_** para ser usada como a preferência de site do cliente. Em seguida, na próxima vez em que o cliente solicitar a URL que não esteja associada ao seu país ou região, ele será redirecionado automaticamente para o país preferido. Portanto, recomendamos que você também use o [módulo do seletor de sites](site-selector.md) em seu site de comércio eletrônico para que os clientes tenham uma forma de substituir ou atualizar a preferência de site. 

Se um cliente fechar a caixa de diálogo Seletor de país/região, nenhum cookie será gravado, e o cliente permanecerá no site atual. 

A seguinte ilustração mostra um exemplo da caixa de diálogo do seletor de país/região.

![Exemplo de uma caixa de diálogo de seletor de país/região em uma página inicial.](./media/Geo_country-region-module-insitu.png)

## <a name="countryregion-picker-module-properties"></a>Propriedades do módulo seletor de país/região

| Nome da propriedade              | Alíquota       | descrição                                                  |
| -------------------------- | ----------- | ------------------------------------------------------------ |
| Título                    | Texto        | O cabeçalho que é exibido na parte superior da caixa de diálogo.       |
| Subtítulo                 | Texto        | O subtítulo que é exibido abaixo do título.               |
| País: cadeia de caracteres para exibição    | Texto        | O nome de exibição de uma opção de URL (por exemplo, "Canadá").   |
| País: substring de exibição | Texto        | Uma substring de exibição opcional para uma opção de URL (por exemplo, "inglês" ou "francês"). |
| País: imagem do país     | Ativo de mídia | Uma imagem opcional associada a uma opção de URL (por exemplo, uma imagem da bandeira do Canadá). |
| País: URL do país       | Texto        | O URL do site do país/região que está sendo configurado. Essa URL deve corresponder exatamente à URL especificada para este país/região na página **Canais** em **Configurações de site** no criador de sites do Commerce. Além disso, o domínio da URL deve ser o domínio personalizado especificado no campo **Coincidir domínio** na página **Canais**, não o endereço do site que o Commerce oferece quando você cria seu ambiente de comércio eletrônico (por exemplo, a URL `https://<yourcompany>.commerce.dynamics.com/`). |
| Link de ação                | Link de ação | Um link opcional que é exibido na parte inferior da caixa de diálogo. Por exemplo, esse link pode apontar para uma página interna que fornece uma lista de todos os países e regiões compatíveis com o site. |

## <a name="add-a-countryregion-picker-module-to-a-page"></a>Adicionar um módulo seletor de país/região a uma página

O módulo seletor de país/região pode ser adicionado ao módulo de cabeçalho diretamente ou por meio de um fragmento compartilhado. Para obter mais informações sobre módulos de cabeçalho, consulte [Módulo de cabeçalho](author-header-module.md).

## <a name="configure-the-countryregion-picker-module-in-commerce-site-builder"></a>Configurar o módulo seletor de país/região no construtor de sites do Commerce

> [!NOTE]
> As URLs que você recomenda aos seus clientes precisam ser configuradas como objetos de país no módulo seletor de país/região.

Para cada URL de site que você deseja mostrar e recomendar aos clientes, siga estas etapas no construtor de sites do Commerce.

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
