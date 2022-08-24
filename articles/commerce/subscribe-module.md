---
title: Módulo de assinatura
description: Este artigo abrange módulos de assinatura e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 7ea9364f77455e7189b6f8784eabb793f9b6bad6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268251"
---
# <a name="subscribe-module"></a>Módulo de assinatura

[!include [banner](includes/banner.md)]

Este artigo abrange módulos de assinatura e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

Os módulos de assinatura podem ser usados nas páginas do site para capturar informações do cliente para boletins informativos ou promoções.

A ilustração a seguir mostra um exemplo de um módulo de assinatura no cabeçalho de uma página da Adventure Works.

![Exemplo de um módulo de assinatura no cabeçalho de uma página da Adventure Works](./media/Subscribe.PNG)

> [!IMPORTANT]
> - O módulo de assinatura está disponível na biblioteca de módulos do Commerce a partir da versão 10.0.20 do Dynamics 365 Commerce.
> - O módulo de assinatura é apresentado no tema Adventure Works.
> - O módulo de assinatura requer uma extensão de ação de dados para trabalhar com alguns provedores de email de marketing, de forma que os emails de boletins informativos ou promocionais possam ser enviados após a obtenção das informações do cliente.

## <a name="subscribe-module-properties"></a>Propriedades do módulo de assinatura

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Título       | Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Um cabeçalho de texto para o módulo de assinatura, por exemplo, **Inscrever-se no boletim informativo** ou **Inscrever-se para ganhar 10% de desconto**. |
| Parágrafo     | Texto de parágrafo | O módulo de assinatura oferece suporte a texto de parágrafo no formato rich text, para fornecer detalhes adicionais para o plano de ação no cabeçalho. |

## <a name="add-a-subscribe-module-to-a-new-page"></a>Adicionar um módulo de assinatura a uma nova página

Para adicionar um módulo de assinatura a uma nova página e definir as propriedades necessárias criador de sites do Commerce, siga as etapas a seguir.

1. Acesse **Modelos** e abra o modelo de marketing para a página inicial do seu site (ou crie um novo modelo de marketing).
1. No slot **Principal** da página padrão, selecione as reticências (**...**) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Inscrever-se** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e abra a página inicial do site (ou crie uma nova página inicial usando o modelo de marketing).
1. No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Inscrever-se** e, depois, **OK**.
1. No painel de propriedades do módulo inscrever, adicione um título, por exemplo, **Inscrever-se**.
1. Adicionar texto de parágrafo, como **Tendências, estilos, promoções mais recentes. Você está na lista? Inscreva-se e receba as melhores e mais recentes ofertas!**
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Visão geral do tema Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
