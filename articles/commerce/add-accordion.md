---
title: Módulo de Accordion
description: Este artigo abrange os módulos de acordeão e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: ec895476770f297825d6c88d0b0a5fef43a5c6ef
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279147"
---
# <a name="accordion-module"></a>Módulo de Accordion

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de acordeão e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

Os módulos de acordeão são como contêineres usados para organizar as informações ou os módulos em uma página, com capacidade semelhante a uma gaveta recolhível. Um módulo de acordeão pode ser usado em qualquer página.

Dentro de cada módulo de acordeão, um ou mais módulos de item acordeão podem ser adicionados. Cada módulo de item de acordeão representa uma gaveta recolhível. Dentro de cada módulo de item de acordeão, um ou mais módulos podem ser adicionados. Não há restrições quanto aos tipos de módulos que podem ser adicionados a um módulo de item de acordeão.

A imagem a seguir mostra um exemplo de um módulo de acordeão usado para organizar informações na página perguntas frequentes de uma loja.

![Exemplo de um módulo de acordeão.](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a>Propriedades do módulo de acordeão

| Nome da propriedade | Valores | Descrição |
|---------------|--------|-------------|
| Título | Texto | Esta propriedade especifica um cabeçalho de texto opcional para o módulo de acordeão. |
| Expandir Tudo | **Verdadeiro** ou **Falso** | Se o valor estiver definido como **verdadeiro**, a funcionalidade expandir/recolher será ativada para que todos os itens no módulo de acordeão possam ser expandidos e recolhidos. |
| Estilo de interação | **Independente** ou **Expandir somente um item** | Esta propriedade define o estilo de interação para itens do acordeão. Se o valor estiver definido como **Independente**, cada item de acordeão poderá ser expandido ou recolhido de forma independente. Se o valor estiver definido como **Expandir somente um item**, apenas um item poderá ser expandido por vez. Conforme os itens são expandidos, os itens expandidos anteriormente são recolhidos. |

## <a name="accordion-item-module-properties"></a>Propriedades do módulo item do acordeão

| Nome da propriedade | Valores | descrição |
|----------------|--------|-------------|
| Cargo | Texto | Esta propriedade especifica o texto do título para o módulo item do acordeão. Ao selecionar a região do título, os usuários podem expandir ou recolher a seção. |
| Expandir por padrão | **Verdadeiro** ou **Falso** | Se o valor for definido como **verdadeiro**, o item do acordeão será expandido por padrão quando a página for carregada. |

## <a name="add-an-accordion-module-to-a-faq-page"></a>Adicionar um módulo do acordeão a uma página perguntas frequentes

Para adicionar um módulo de acordeão a uma página perguntas frequentes e definir suas propriedades no assistente para criação de sites, siga as etapas a seguir.

1. Acesse **Páginas** e use o modelo de marketing da Fabrikam (ou qualquer modelo que não tenha restrições) para criar uma nova página denominada **Perguntas frequentes de loja**.
1. No slot **Principal** da **Página padrão**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Acordeão** e, depois, **OK**.
1. No painel de propriedades do módulo de acordeão, selecione **Título** ao lado do símbolo de lápis.
1. Na caixa de diálogo **Título**, em **Texto do título**, digite **Perguntas frequentes**. Em seguida, selecione **OK**.
1. No painel de propriedades do módulo de acordeão, marque a caixa de seleção **Mostrar expandir tudo** e, no campo **Estilo de interação**, selecione **Independente**.
1. No slot **Acordeão**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Item de acordeão** e, depois, **OK**.
1. No painel de propriedades do módulo de item do acordeão, em **Título**, digite o texto do título (por exemplo, **Como os retornos funcionam?**).
1. No slot **Item do acordeão**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Bloco de texto** e, depois, **OK**.
1. No painel de propriedades do módulo bloco de texto, insira um parágrafo de texto (por exemplo, **As devoluções devem ser processadas via call center. Contate 1-800-FABRIKAM para devoluções. Os produtos têm uma política de devolução de 30 dias. As devoluções devem ser iniciadas neste intervalo de tempo.**).
1. No slot **Acordeão**, adicione mais alguns módulos de item do acordeão. Em cada módulo de item do acordeão, adicione um módulo de bloco de texto que tenha conteúdo.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página. A página mostrará um módulo de acordeão que tem o conteúdo adicionado.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de guia](add-tab.md)

[Módulo de bloco de texto](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
