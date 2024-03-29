---
title: Módulo de banner de promoção
description: Este artigo abrange os módulos de faixa promocional e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: fbde146923d1448e382cbf2458880f7e300f605c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279726"
---
# <a name="promo-banner-module"></a>Módulo de banner de promoção

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de faixa promocional e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

Os módulos de faixa promocional são usados para mostrar mensagens informativas em linha em uma página. Eles podem ser usados para mostrar promoções em todo o site que aparecem em todas as páginas de um site de comércio eletrônico. 

Os módulos de faixa promocional fornecem suporte a uma mensagem de texto e um link. Se várias mensagens forem adicionadas a um módulo de faixa promocional, ele se tornará uma faixa de carrossel giratória que permite aos clientes percorrerem todas as mensagens. 

Os módulos de faixa promocional são controlados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>Exemplos de uso de faixas promocionais no comércio eletrônico

As faixas promocionais podem ser usadas no cabeçalho do site para mostrar promoções ou mensagens em todo o site, como nos exemplos a seguir.

"A venda anual termina em 10 dias"

"Economize bastante com a venda na volta às aulas. Compre agora."

"Comprar em VENDA de ação de graças!" 

A imagem a seguir mostra um exemplo de uma faixa promocional.

![Exemplo de um módulo de faixa promocional.](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a>Propriedades do módulo de faixa promocional

| Nome da propriedade             | Alíquota                              | Descrição |
|---------------------------|------------------------------------|-------------|
| Mensagens da faixa           | Textos e links                     | Uma matriz de texto e links. |
| Reprodução automática                  | **Verdadeiro** ou **Falso**              | Um valor que indica se é possível percorrer automaticamente as mensagens caso várias mensagens estejam configuradas. |
| Intervalo de transição de slides | Um número de milissegundos (ms)      | O intervalo usado para percorrer as mensagens. |
| Permitir ignorar             | **Verdadeiro** ou **Falso**              | Se o valor estiver definido como **Verdadeiro**, os clientes poderão dispensar o alerta. |
| Mostrar palheta do carrossel     | **Verdadeiro** ou **Falso**              | Um valor que indica se as palhetas do carrossel devem ser mostradas, de forma que os clientes possam percorrer vários itens de faixa manualmente. |
| Alinhamento de texto            | **Direito**, **Esquerdo** ou **Centro** | O alinhamento do texto no módulo de faixa promocional. |
| Vínculo                      | URL A                              | A URL para um link opcional. |
|Alinhamento de texto             | **Direito**, **Esquerdo** ou **Centro** | Esta propriedade está disponível como uma extensão de tema no tema Adventure Works. Isso permite que um usuário defina o alinhamento do texto no banner da promoção. |

> [!IMPORTANT]
> O tema Adventure Works está disponível a partir da versão 10.0.20 do Dynamics 365 Commerce.

## <a name="add-a-promo-banner-module-to-a-page"></a>Adicionar um módulo de faixa promocional a uma página 

Para adicionar um módulo de faixa promocional a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Acesse **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo modelo**, em **Nome do Modelo**, insira **Modelo do banner da promoção** e, depois, selecione **OK**.
1. Em **Estrutura de Tópicos de Página**, adicione um módulo **Página padrão** ao slot **Corpo**. 
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo. 
1. Use o modelo que você acabou de criar para criar uma página com o nome **Página de faixa promocional**. 
1. No slot **Principal** da nova página, adicione um módulo de contêiner. 
1. No painel à direita, defina o valor da **Largura** como **Preencher Contêiner**.
1. Em **Estrutura de Tópicos de Página**, adicione um módulo de faixa promocional ao módulo de contêiner.
1. Nas configurações do módulo de faixa, adicione uma ou mais mensagens de faixa. Cada mensagem pode ter texto juntamente com um link. É possível editar as outras propriedades para personalizar ainda mais o módulo.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página. Na parte superior da página, você verá um alerta que mostra o texto que você adicionou.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

> [!NOTE]
> Em geral, uma faixa promocional é usada no slot do cabeçalho da página ou em um slot de subcabeçalho.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo do carrossel](add-carousel.md)

[Módulo de bloco de texto](add-content-rich-block.md)

[Módulo de bloco de conteúdo](add-hero-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
