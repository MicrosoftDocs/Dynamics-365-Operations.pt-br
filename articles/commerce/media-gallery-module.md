---
title: Módulo de galeria de mídia
description: Este artigo abrange os módulos de galeria de mídia e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 5e2d0a4422341badee906c71bebdd491e18a38cc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273449"
---
# <a name="media-gallery-module"></a>Módulo de galeria de mídia

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de galeria de mídia e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

Os módulos de galeria de mídia mostram uma ou mais imagens em uma exibição da galeria. Os módulos de galeria de mídia oferecem suporte a imagens em miniatura, que podem ser organizadas horizontalmente (como uma linha abaixo da imagem) ou verticalmente (como uma coluna ao lado da imagem). Os módulos de galeria de mídia também fornecem recursos que permitem que as imagens sejam ampliadas (aumentadas) ou exibidas no modo de tela inteira. Para ser renderizada em um módulo de galeria de mídia, uma imagem deve estar disponível na Biblioteca de Mídia do construtor de sites do Commerce. No momento, os módulos de galeria de mídia oferecem suporte somente a imagens.

No modo padrão, um módulo de galeria de mídia usa a ID do produto disponível no contexto da página de uma página de detalhes do produto (PDP) para renderizar as imagens de produto correspondentes. Um caminho de arquivo de mídia deve ser definido para todos os produtos no Commerce headquarters. Em seguida, as imagens devem ser carregadas na Biblioteca de Mídia do construtor de sites de acordo com o caminho do arquivo definido para os produtos no Commerce headquarters. Essas imagens incluem imagens de produtos e de variantes de produto. Para obter mais informações sobre como carregar imagens na Biblioteca de Mídia do construtor de sites, consulte [Carregar imagens](dam-upload-images.md).

Como alternativa, um módulo de galeria de mídia pode hospedar um conjunto de imagens totalmente organizado em uma página da galeria de imagens, em que não haja nenhuma dependência na ID do produto ou no contexto da página. Nesse caso, as imagens devem ser carregadas na Biblioteca de Mídia do construtor de sites e especificadas no site construtor de sites.

Veja alguns exemplos de uso dos módulos de galeria de mídia:

- Renderização de imagens de produtos em uma PDP
- Renderização de imagens do produto em uma página de marketing do produto
- Apresentação de um conjunto de imagens organizado em uma página de marketing, como uma página da galeria

No exemplo da ilustração a seguir, uma caixa de compra em uma PDP hospeda imagens de produto usando um módulo de galeria de mídia.

![Exemplo de uma caixa de compra em uma página de detalhes do produto que hospeda imagens do produto usando um módulo de galeria de mídia.](./media/ecommerce-pdp-buybox.PNG)

## <a name="media-gallery-properties"></a>Propriedades da galeria de mídia

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Origem da imagem | **Contexto da página** ou **ID do produto** | O valor padrão é **Contexto de página**. Se a propriedade **Contexto da página** estiver selecionada, o módulo esperará que a página forneça as informações de ID do produto. Se **ID do produto** estiver selecionada, a ID do produto de uma imagem deverá ser fornecida como o valor da propriedade **ID do produto**. Esse recurso está disponível no Commerce versão 10.0.12. |
| ID do produto | Uma ID do produto | Essa propriedade é aplicável somente se o valor da propriedade **Origem da imagem** for **ID do produto**. |
| Zoom da imagem | **Inline** ou **Contêiner** | Essa propriedade permite que o usuário aplique zoom às imagens no módulo de galeria de mídia. Uma imagem pode ser ampliada inline ou em um contêiner separado ao lado da imagem. Esse recurso está disponível na versão 10.0.12. |
| Fator de zoom | Um número decimal | Essa propriedade especifica o fator de escala para a ampliação de imagens. Por exemplo, se o valor for definido como **2,5**, as imagens serão ampliadas 2,5 vezes. |
| Tela inteira | **Verdadeiro** ou **Falso** | Essa propriedade especifica se as imagens podem ser exibidas no modo de tela inteira. No modo de tela inteira, as imagens também poderão ser ampliadas ainda mais se a capacidade de zoom estiver ativada. Esta capacidade está disponível na versão 10.0.13 do Commerce. |
| Qualidade de imagem ampliada | Um número de 1 a 100 que representa uma porcentagem e é selecionado usando um controle TrackBar | Esta propriedade define a qualidade da imagem para imagens ampliadas. Ela pode ser definida como 100% para garantir que uma imagem ampliada sempre use a maior resolução possível. Esta propriedade não se aplica a arquivos PNG, pois eles usam um formato sem perdas. Esta capacidade está disponível desde a versão 10.0.19 do Commerce. |
| Imagens | Imagens selecionadas na Biblioteca de Mídia do construtor de sites | Além de serem renderizadas de um produto, as imagens podem ser organizadas para um módulo de galeria de mídia. Essas imagens serão anexadas a qualquer imagem de produto disponível. Esse recurso está disponível no Commerce versão 10.0.12. |
| Orientação de miniatura | **Vertical** ou **Horizontal** | Essa propriedade especifica se as imagens em miniatura devem ser exibidas em uma faixa vertical ou em uma faixa horizontal. |
| Ocultar imagens de produto mestre para grade | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, quando uma grade for selecionada, as imagens do produto mestre ficarão ocultas, a menos que a grade não tenha imagens. Esta propriedade não afeta produtos sem grades. |
| Atualizar mídia na seleção de dimensão | **Verdadeiro** ou **Falso** | Se esta propriedade estiver definida como **Verdadeiro**, as imagens na biblioteca de mídia serão atualizadas quando qualquer dimensão (como cor, estilo ou tamanho) for selecionada, e se houver alguma imagem disponível. Esta propriedade ajuda a simplificar a experiência de navegação, porque nem todas as dimensões da grade de produto devem ser selecionadas para que a imagem correspondente seja atualizada. Esta propriedade está disponível na guia **Avançado**. |

> [!IMPORTANT]
> A propriedade **Atualizar mídia na seleção de dimensão** está disponível a partir da versão 10.0.21 do Commerce. Ela requer que o pacote de biblioteca do módulo da versão 9.31 do Commerce esteja instalado.

A ilustração a seguir mostra um exemplo de um módulo de galeria de mídia no qual as opções de tela inteira e de zoom estão disponíveis.

![Exemplo de um módulo de galeria de mídia no qual as opções de tela inteira e de zoom estão disponíveis.](./media/ecommerce-media-zoom.png)

A ilustração a seguir mostra um exemplo de um módulo de galeria de mídia com imagens organizadas (isto é, as imagens especificadas não dependem da ID do produto ou do contexto da página).

![Exemplo de um módulo de galeria de mídia com imagens organizadas.](./media/ecommerce-media-curated.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interação do Commerce Scale Unit

Quando a origem da imagem é derivada do contexto da página, a ID do produto da PDP é usada para recuperar as imagens. O módulo de galeria de mídia recupera o caminho do arquivo da imagem dos produtos usando as interfaces de programação de aplicativos (APIs) de Commerce Scale Unit. As imagens são então extraídas da Biblioteca de Mídia para que possam ser renderizadas no módulo.

## <a name="add-a-media-gallery-module-to-a-page"></a>Adicionar um módulo de galeria de mídia a uma página

Para adicionar um módulo de galeria de mídia a uma página de marketing, siga estas etapas:

1. Acesse **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo modelo**, em **Nome do modelo**, insira **Modelo de marketing** e selecione **OK**.
1. No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Página Padrão** e, depois, **OK**.
1. No slot **Principal** da página padrão, selecione as reticências (**...**) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Criar uma nova página**, em **Nome da página**, insira **Página de galeria de mídia** e selecione **Avançar**.
1. Em **Escolher um modelo**, selecione o **Modelo de marketing** que você criou e, depois, selecione **Avançar**.
1. Em **Escolher um layout**, selecione um layout de página (por exemplo, **Layout flexível**) e selecione **Avançar**.
1. Em **Revisar e concluir**, revise a configuração da página. Se você precisar editar as informações da página, selecione **Voltar**. Se as informações da página estiverem corretas, selecione **Criar página**. 
1. No slot **Principal** da nova página, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Galeria de mídia** e, depois, **OK**.
1. No painel de propriedades do módulo de galeria de mídia, em **Origem da imagem**, selecione **Productid**. Em seguida, no campo **ID do produto**, insira uma ID do produto.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página. Você poderá ver as imagens do produto em uma exibição de galeria.
1. Para usar somente imagens organizadas, no painel de propriedades, em **Origem da imagem**, selecione **Productid**. Em seguida, em **Imagens**, selecione **Adicionar uma imagem** quantas vez for necessário para adicionar imagens da Biblioteca de Mídia.
1. Defina as propriedades adicionais que você quiser definir, como **Zoom de imagem**, **Fator de zoom** e **Orientação de miniaturas**.
1. Depois que terminar, selecione **Salvar** e **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-la.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de contêiner](add-container-module.md)

[Carregar imagens](dam-upload-images.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
