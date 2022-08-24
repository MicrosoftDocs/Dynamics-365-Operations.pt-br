---
title: Módulo de resultados de pesquisa
description: Este artigo abrange os módulos de resultados de pesquisa e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: d10e9ed78dfc90833ff3c09021f863f6ef0b80d9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286801"
---
# <a name="search-results-module"></a>Módulo de resultados de pesquisa

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de resultados de pesquisa e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

O módulo de resultados da pesquisa retorna resultados de pesquisa de produtos e uma lista de refinadores aplicáveis para os produtos. Os módulos de resultados de pesquisa em sites do Dynamics 365 Commerce podem ser usados para processar páginas para os seguintes cenários:

- Resultados de pesquisa iniciados por uma pesquisa do usuário
- Resultados de pesquisa que mostram um conjunto específico de produtos, como "comprar visuais semelhantes"
- Lista de produtos que pertencem uma categoria

Para obter mais informações sobre as páginas de categoria e de resultados de pesquisa, consulte [Visão geral da página inicial de categorias e da página de resultados de pesquisa](category-search-page-overview.md).

A ilustração a seguir mostra um exemplo de uma página de resultados de pesquisa para uma categoria do site da Fabrikam.

![Exemplo de uma página de resultados de pesquisa no site da Fabrikam.](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a>Propriedades do módulo de resultados de pesquisa

A tabela a seguir lista as propriedades dos módulos de resultados de pesquisa, juntamente com seus valores e descrições.

| Propriedade | Valores | descrição |
|----------|--------|-------------|
| Itens por página | Inteiro | O número de itens que devem ser mostrados em cada página. |
| Permitir voltar no PDP | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, quando um usuário selecionar um produto na página de resultados de pesquisa, a navegação estrutural na página de detalhes do produto (PDP) que for aberta mostrará um link "Voltar para os resultados". |
| Expandir Refinadores | **Todos**, **1**, **2**, **3** ou **4** | O número de refinadores principais que devem ser expandidos quando uma página é carregada. Por exemplo, se esta propriedade for definida como **3**, os três primeiros refinadores na página serão expandidos. |
| Ocultar exibição da hierarquia de categoria | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, a exibição da hierarquia de categoria na página ficará oculta. Essa propriedade deve ser definida como **Verdadeiro** se você estiver usando o [módulo de trilha de navegação](add-breadcrumb.md) para mostrar a hierarquia de categoria.|
| Incluir atributos de produto nos resultados da pesquisa | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, os atributos serão devolvidos para os produtos nos resultados da pesquisa. Embora esses atributos possam ser mostrados em um site do Commerce, é necessária uma extensão.|
| Mostrar preços de afiliação | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, os preços de afiliação para produtos serão mostrados nos resultados da pesquisa quando um usuário conectado navegar na página. |
| Atualizar painel do refinador | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, o painel do refinador será atualizado quando os refinadores forem selecionados. Neste modo, alguns refinadores de seleção múltipla se comportarão como refinadores de seleção única quando o painel do refinador for atualizado. |

> [!IMPORTANT]
> No Commerce versão 10.0.16 e posterior, a configuração **Mostrar preços de afiliação** pode ser usada para mostrar os preços de afiliação na página.
>
> No Commerce versão 10.0.20 e posterior, a configuração **Atualizar painel do refinador** pode ser usada para atualizar o painel do refinador durante a seleção do refinador.

## <a name="supported-modules"></a>Módulos com suporte

O módulo de resultados de pesquisa oferece suporte ao [módulo de exibição rápida](quick-view-module.md), que permite que os usuários vejam informações sobre o produto e adicionem itens ao carrinho usando uma página de resultados de pesquisa.

## <a name="add-a-search-results-module-to-a-category-page"></a>Adicionar um módulo de resultados de pesquisa a uma página de categoria

Para adicionar um módulo de resultados de pesquisa a uma página de categoria no construtor de sites, siga estas etapas.

1. Acesse **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo modelo**, digite o nome **Resultados de pesquisa** e selecione **OK**.
1. No slot **Corpo**, selecione as reticências (...) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Página Padrão** e, depois, **OK**.
1. No slot **Principal** do módulo **Página padrão**, selecione as reticências (...) e, em seguida, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (...) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Trilha** e, depois, **OK**.
1. No painel de propriedades **Trilha de navegação**, digite o valor **1** para **Mínimo ocorrer**.
1. No slot **Contêiner**, selecione as reticências (...) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Resultados da pesquisa** e, depois, **OK**.
1. No painel **Propriedades de resultados da pesquisa**, digite o valor **1** para **Mínimo ocorrer** e, em seguida, defina outras propriedades necessárias para o módulo de resultados da pesquisa. Ao definir essas propriedades no modelo, você garante que todas as personalizações em uma página de categoria específica incluam automaticamente essas configurações.
1. Selecione **Concluir edição** e depois selecione **Publicar** para publicar o modelo.
1. Acesse **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Criar uma nova página**, em **Nome da página**, insira **Página da categoria** e selecione **Avançar**.
1. Em **Escolher um modelo**, selecione o módulo **Resultados da pesquisa** que você criou e escolha **Avançar**.
1. Em **Escolher um layout**, selecione um layout de página (por exemplo, **Layout flexível**) e selecione **Avançar**.
1. Em **Revisar e concluir**, revise a configuração da página. Se você precisar editar as informações da página, selecione **Voltar**. Se as informações da página estiverem corretas, selecione **Criar página**.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="enable-inventory-awareness-for-the-search-results-module"></a>Habilitar o reconhecimento de estoque para o módulo de resultados de pesquisa

Geralmente, os clientes esperam que o site de comércio eletrônico reconheça o estoque em toda a experiência de navegação para que possam decidir o que fazer se não houver estoque para um produto. O módulo de resultados de pesquisa pode ser configurado para incorporar dados de estoque e fornecer as seguintes experiências:

- Mostre um rótulo de disponibilidade de estoque junto com o produto.
- Oculte produtos com estoque esgotado da lista de produtos.
- Mostre produtos com estoque esgotado ao final da lista de produtos.
- Filtre produtos nos resultados de pesquisa por nível de estoque.

Para habilitar essas experiências, você deve primeiro habilitar o recurso **Descoberta aprimorada de produtos de comércio eletrônico para ter reconhecimento do estoque** no espaço de trabalho **Gerenciamento de recursos**.

> [!NOTE]
> O recurso **Descoberta aprimorada de produtos de comércio eletrônico para ter reconhecimento do estoque** está disponível no Commerce versão 10.0.20 e posterior.

A pesquisa de produtos com reconhecimento de estoque usa atributos de produto para obter informações sobre a disponibilidade de estoque. Como um pré-requisito para o recurso, os atributos de produto dedicados devem ser criados, os dados de estoque devem ser inseridos para eles e eles devem ser adicionados ao canal online. 

Para criar atributos de produto dedicados para oferecer suporte ao módulo de resultados de pesquisa com reconhecimento de estoque, siga estas etapas:

1. No headquarters, acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Produtos e estoque**.
1. Selecione e abra **Preencher atributos de produto com nível de estoque**.
1. Na caixa de diálogo, insira as seguintes informações:

    1. No campo **Atributo do produto e nome do tipo**, especifique um nome para o atributo de produto dedicado que será criado para capturar os dados do estoque.
    1. No campo **Disponibilidade de estoque com base em**, selecione o tipo de quantidade no qual o cálculo do nível de estoque deve se basear (por exemplo, **Quantidade física disponível**). 

1. Execute o trabalho em segundo plano. Como o estoque do produto muda com constância em um ambiente de omnicanal, é altamente recomendável que você agende esse trabalho como um processo em lote.

> [!NOTE]
> Para um cálculo de nível de estoque consistente nas páginas e módulos no seu site de comércio eletrônico, certifique-se de selecionar o mesmo tipo de quantidade para a configuração **Disponibilidade de estoque com base em** no Commerce headquarters e na configuração **Nível de estoque com base em** no construtor de sites do Commerce. Para obter mais informações sobre configurações de estoque no construtor de sites, consulte [Aplicar configurações de estoque](inventory-settings.md).

Para configurar os atributos do produto para um canal online, siga estas etapas: 

1. No headquarters, acesse **Varejo e Comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.
1. Selecione um canal online para habilitar o módulo de resultados de pesquisa com reconhecimento de estoque.
1. Selecione e abra um grupo de atributos associado e, em seguida, adicione o atributo de produto recém-criado a ele.
1. Para as versões do Commerce anteriores à 10.0.27, selecione **Definir metadados de atributo**, selecione o atributo de produto recém-adicionado e, em seguida, ative as opções **Mostrar atributo no canal**, **Recuperável**, **Pode ser refinado** e **Pode ser consultado**.
1. Acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de Distribuição** e execute o trabalho **1150 (Catálogo)**. Se você agendar o trabalho **Preencher atributos de produto com nível de estoque** com um processo em lote recomendamos que você também agende o trabalho 1150 como um processo em lote que seja executado na mesma frequência.

> [!NOTE]
> Para os produtos mostrados no módulo de resultados da pesquisa, o nível de estoque é exibido no nível do produto mestre, e não no nível de grade individual. Ele tem apenas dois valores possíveis: "disponível" e "esgotado". O rótulo real para o valor é recuperado da definição do [perfil de nível de estoque](inventory-buffers-levels.md). Um produto mestre só é considerado fora do estoque quando todas as suas variantes estão fora do estoque.

Depois que todas as etapas de configuração anteriores forem concluídas, os refinadores nas páginas de resultados da pesquisa mostrarão um filtro baseado em estoque e o módulo de resultados da pesquisa recuperará os dados de estoque em segundo plano. Em seguida, você pode definir a configuração **Configurações de estoque para páginas de listagem de produtos** no construtor de sites do Commerce para controlar como o módulo de resultados de pesquisa mostra produtos esgotados. Para obter mais informações, consulte [aplicar configurações de estoque](inventory-settings.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da página de aterrissagem da categoria padrão e da página de resultados da pesquisa](category-search-page-overview.md)

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de exibição rápida](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
