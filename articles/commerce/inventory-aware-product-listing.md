---
title: Listagem de produtos com reconhecimento de estoque
description: Este artigo descreve como as organizações podem configurar páginas de listagem de produtos no site de comércio eletrônico do Microsoft Dynamics 365 Commerce para que reconheçam o estoque.
author: boycez
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-23
ms.openlocfilehash: 2a65dedf2da62fcd92169077d75a0f3b7832a86d
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473724"
---
# <a name="inventory-aware-product-listing"></a>Listagem de produtos com reconhecimento de estoque

[!include [banner](../includes/banner.md)]

Este artigo descreve como as organizações podem configurar páginas de listagem de produtos no site de comércio eletrônico do Microsoft Dynamics 365 Commerce para que reconheçam o estoque. As páginas de listagem de produtos incluem páginas de aterrissagem da categoria e de resultados de pesquisa.

Os compradores, em geral, esperam que uma descoberta de produtos em todo o site de comércio eletrônico reconheça o estoque para que possam decidir o que fazer se um produto estiver esgotado. É possível configurar a categoria [biblioteca de módulos do Commerce](starter-kit-overview.md) e os módulos de resultados de pesquisa para incorporar dados de estoque. Dessa forma, eles podem fornecer as seguintes experiências:

- Exiba etiquetas de nível de estoque junto com produtos.
- Oculte produtos com estoque esgotado da lista de produtos.
- Mova produtos esgotados para a parte inferior de páginas de lista de produtos.
- Ofereça suporte à filtragem de produtos com base no estoque.

Para habilitar essas experiências, você deve primeiro habilitar o recurso **Descoberta aprimorada de produtos de comércio eletrônico para ter reconhecimento do estoque** no Commerce headquarters.

> [!NOTE]
> No Commerce versão 10.0.29 e posterior, o recurso **Descoberta aprimorada de produtos de comércio eletrônico para ter reconhecimento do estoque** é habilitado por padrão.

## <a name="set-up-product-attribute-for-inventory-availability"></a>Configurar atributo de produto para disponibilidade de estoque

A listagem de produtos com reconhecimento de estoque usa a estrutura de atributos do produto. Como pré-requisito, um atributo de produto dedicado deve ser criado para capturar dados de disponibilidade de estoque.

Para configurar o atributo de produto para disponibilidade de estoque no Commerce headquarters, siga estas etapas.

1. Acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Produtos e estoque \> Preencher atributos de produto com nível de estoque**.
1. Na caixa de diálogo **Preencher atributos de produto com nível de estoque**, no campo **Atributo do produto e nome do tipo**, insira um nome personalizado para o atributo de produto dedicado que será criado para capturar dados de inventário.
1. No campo **Disponibilidade de estoque baseada em**, selecione o tipo de quantidade no qual o cálculo do nível de estoque deve se basear: **Quantidade física disponível** ou **Total disponível**.
1. Defina a opção **Processamento em lotes** como **Sim**.
1. Selecione **OK**.

> [!NOTE]
> Para um cálculo de nível de estoque consistente nas páginas no site de comércio eletrônico, selecione o mesmo tipo de quantidade no campo **Disponibilidade de estoque com base em** para o trabalho **Preencher atributos de produto com nível de estoque** e a configuração **Nível de estoque com base em** no assistente para criação de sites do Commerce.

Após a criação do atributo de produto dedicado, a próxima etapa é configurar o atributo para o canal online.

Para configurar o atributo para o canal online no Commerce headquarters, siga estas etapas.

1. Acesse **Varejo e Comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.
1. Selecione o canal online para habilitar a experiência de listagem de produtos com reconhecimento de estoque.
1. Selecione e abra um grupo de atributos associado e, depois, adicione o novo atributo de produto a ele.
1. Acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição** e execute o trabalho **1150** (**Catálogo**). É recomendável agendar este trabalho como um processo em lote executado na mesma frequência que o trabalho **Preencher atributos de produto com nível de estoque**.

> [!NOTE]
> No Commerce versão 10.0.26 e anterior, depois de adicionar o atributo de produto de disponibilidade de estoque a um grupo de atributos, você também deve selecionar **Definir metadados de atributo** e ativar as opções **Mostrar atributo no canal**, **Recuperável**, **Pode ser refinado** e **Pode ser consultado** para o novo atributo de produto.

## <a name="configure-the-display-behavior-for-out-of-stock-products-on-product-listing-pages"></a>Configurar o comportamento de exibição para produtos esgotados em páginas de listagem de produtos

Depois que todas as etapas de configuração anteriores forem concluídas, os refinadores nas páginas de resultados de pesquisa e categoria terão uma opção de filtro com base em estoque. Uma etiqueta de nível de estoque será exibida para cada bloco de produto que aparecer na página.

A página resultados da categoria e da pesquisa exibe produtos no nível mestre, não no nível da grade de produto. O nível de estoque exibido junto com cada produto é um nível de estoque agregado determinado pelo nível de estoque de todas as grades do produto. O nível de estoque de uma grade é calculado com base no estoque disponível dessa grade no depósito padrão do canal online no Commerce headquarters. O nível de estoque de um produto mestre tem dois valores possíveis que representam os estados em estoque e esgotado. Um produto mestre é considerado esgotado quando todas as variantes estão esgotadas. Caso contrário, o produto é considerada em estoque. A etiqueta do valor é recuperada da definição do [nível de estoque](inventory-buffers-levels.md). Se nenhum nível de estoque for definido, as etiquetas padrão (em inglês) serão **Disponível** e **Esgotado**.

Você pode definir a configuração **Configurações de estoque para páginas de listagem de produtos** no assistente para criação de sites do Commerce para controlar como a página resultados da categoria e da pesquisa exibe produtos esgotados. Para obter mais informações, consulte [aplicar configurações de estoque](inventory-settings.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
