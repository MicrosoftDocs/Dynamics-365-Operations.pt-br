---
title: Módulo de compartilhamento social
description: Este tópico abrange os módulos de compartilhamento social e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: d145602a217b32b97142251c65d51945569be9ac
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780884"
---
# <a name="social-share-module"></a>Módulo de compartilhamento social

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de compartilhamento social e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

Os modelos de compartilhamento social permitem que os usuários compartilhem as URLs de páginas de site de comércio eletrônico em mídias sociais, como Facebook, Twitter, Pinterest e LinkedIn. As URLs da página do site também podem ser compartilhadas por email. Os módulos de compartilhamento social são geralmente usados em páginas de detalhes do produto (PDPs) para ajudar os usuários a compartilhar informações.

Cada módulo de compartilhamento social é um contêiner de módulos de item de compartilhamento social. Cada módulo de item de compartilhamento social pode ser configurado para apontar para um site de mídia social específico. A integração com o Facebook, o Twitter, o Pinterest, o LinkedIn e o email tem suporte imediato. Quando um usuário do site seleciona um símbolo de mídia social, um iFrame HTML é iniciado para o respectivo site de mídia social. No iFrame, o usuário pode entrar e publicar o conteúdo da página sendo exibida.

Cada plataforma de mídia social pode rastrear cookies, portanto, este módulo requer que os usuários do site aceitem a mensagem de notificação de consentimento de cookie. Quando o consentimento do cookie não foi aceito, o módulo ficará oculto na página. Para obter mais informações, consulte [Conformidade do cookie](cookie-compliance.md).

A ilustração a seguir destaca um exemplo de módulo de compartilhamento social usado na página de detalhes de um produto.

![Exemplo de um módulo de compartilhamento social.](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a>Propriedades do módulo de compartilhamento social

| Nome da propriedade             | Alíquota                 | descrição |
|---------------------------|-----------------------|-------------|
| Legenda                  | Texto | Esta propriedade especifica uma legenda para o módulo. |
| Orientação | **Horizontal** ou **Vertical**  | Esta propriedade define a orientação do layout para os itens de mídia social. |

## <a name="social-share-item-module-properties"></a>Propriedades do módulo do item de compartilhamento social
| Nome da propriedade             | Alíquota                 | descrição |
|---------------------------|-----------------------|-------------|
| Mídia social              | **Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Email** | Um menu suspenso com uma lista de plataformas de mídia social. |
| Ícone |Imagem    | Esta será a imagem que será exibida para a respectiva mídia social. Como prática recomendada, consulte o SDK da plataforma de mídia social para obter a imagem recomendada a ser usada para cada plataforma. |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a>Adicionar um módulo de compartilhamento social a um módulo de caixa de compra

Para adicionar um módulo de compartilhamento social a um módulo de caixa de compra, execute as seguintes etapas.

1. No site Fabrikam, selecione **Páginas** e depois selecione a página **DefaultPDP** para abrir a página de detalhes do produto. 
1. No slot **Caixa de compra (obrigatório)**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Compartilhamento Social** e, depois, **OK**.
1. No slot **Compartilhamento Social**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Compartilhamento Social** e, depois, **OK**.
1. No painel de propriedades do módulo **Compartilhamento Social**, em **Orientação**, selecione **Horizontal**. Adicione uma legenda conforme necessário.
1. No slot **Compartilhamento Social**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Compartilhamento Social** e, depois, **OK**.
1. No painel de propriedades do módulo **Item de Compartilhamento Social**, em **Mídia Social**, selecione **Facebook**.
1. No painel de propriedades do módulo Item de **Item de Compartilhamento Social**, em **Ícone**, selecione **+ Adicionar imagem**.
1. Na caixa de diálogo **Seletor de mídia**, selecione a imagem do logotipo do Facebook e selecione **OK**. Se não houver uma imagem de logotipo do Facebook, selecione **Carregar novo item de mídia** para carregar uma imagem.
1. Adicione e configure módulos adicionais de **Item de Compartilhamento Social** conforme necessário.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página. A página exibirá o módulo de compartilhamento social.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de caixa de compra](add-buy-box.md)

[Compatível com cookies](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
