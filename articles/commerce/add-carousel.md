---
title: Módulo do carrossel
description: Este artigo abrange os módulos do carrossel e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: b99fea773f18c65b73ea3f519705d3043820cfd4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864998"
---
# <a name="carousel-module"></a>Módulo do carrossel

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos do carrossel e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.

Um módulo de carrossel é usado para colocar vários itens promocionais (incluindo imagens sofisticadas) em uma faixa de carrossel rotatória na qual os clientes possam navegar. Por exemplo, um varejista pode usar um módulo de carrossel em uma home page para exibir vários novos produtos ou promoções.

Você pode adicionar módulos de bloco de conteúdo dentro de um módulo de carrossel. As propriedades do módulo de carrossel definem como esses módulos são renderizados.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Exemplos de módulos de carrossel no comércio online

- Um carrossel que possui vários módulos promocionais pode ser usado em uma home page.
- Um carrossel que possui vários módulos promocionais pode ser usado em uma página de detalhes do produto.
- Um carrossel pode ser usado em qualquer página de marketing para promover várias promoções ou produtos.

A imagem a seguir mostra um exemplo de um módulo de carrossel que é usado em uma home page. Este módulo de carrossel contém vários itens de bloco de conteúdo.

![Exemplo de um módulo de carrossel.](./media/Hero.PNG)

## <a name="carousel-module-properties"></a>Propriedades do módulo de carrossel

| Nome da propriedade             | Alíquota                 | descrição |
|---------------------------|-----------------------|-------------|
| Reprodução automática                  | **Verdadeiro** ou **Falso** | Se o valor estiver definido como **Verdadeiro**, a transição entre os itens dentro no carrossel ocorrerá automaticamente. Se o valor estiver definido como **Falso**, nenhuma transição ocorrerá, a menos que o cliente use o teclado ou o mouse para passar de um item para o próximo. |
| Intervalo de transição de slides | Um valor em segundos    | O intervalo para transições entre itens. |
| Tipo de transação           | **Slide** ou **Fade** | O efeito de transição entre itens. |
| Ocultar palheta do carrossel     | **Verdadeiro** ou **Falso** | Se o valor for definido como **True**, a palheta do carrossel e o indicador de sequência ficarão ocultos. |
| Permitir descarte do carrossel    | **Verdadeiro** ou **Falso** | Se o valor estiver definido como **True**, os usuários poderão dispensar o carrossel. |

## <a name="add-a-carousel-module-to-a-page"></a>Adicionar um módulo de carrossel a uma página

Para adicionar um módulo de carrossel a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Acesse **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo Modelo**, em **Nome do Modelo**, insira **Modelo de carrossel** e selecione **OK**.
1. No slot **Corpo**, adicione um módulo **Página padrão**.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.  
1. Use o modelo de carrossel que criou para criar uma página nomeada **Página do carrossel**.
1. No slot **Principal** da nova página, adicione um módulo de contêiner. 
1. No painel à direita, defina o valor da **Largura** como **Preencher Tela**.
1. Em **Estrutura de Tópicos de Página**, adicione um módulo de carrossel ao módulo de contêiner.
1. Adicione um módulo de bloco de conteúdo ao módulo de carrossel. Defina as propriedades do módulo de bloco de conteúdo fornecendo **Título**, **Link**, **Layout** e outras propriedades.
1. Adicione e configure outro módulo de bloco de conteúdo.
1. Defina propriedades adicionais para o módulo do carrossel conforme necessário.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página. A página deve mostrar um carrossel que possui dois módulos (um módulo de hero e um módulo de recurso). Você pode alterar propriedades adicionais para os módulos de carrossel, hero e recurso, para obter o efeito desejado.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de banner de promoção](add-alert.md)

[Módulo de bloco de texto](add-content-rich-block.md)

[Módulo de bloco de conteúdo](add-hero-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
