---
title: Módulo de trilha de navegação
description: Este artigo abrange os módulos de trilha de navegação e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: fe5dfea7e579d54d11be35eb657a1c1f617a5724
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277076"
---
# <a name="breadcrumb-module"></a>Módulo de trilha de navegação

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de trilha de navegação e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.

Os módulos de trilha de navegação são usados para fornecer navegação secundária em páginas do site. Em geral, são mostradas na parte superior de uma página, abaixo do cabeçalho. Embora os módulos de trilha de navegação possam ser adicionados a qualquer página, eles costumam ser usados em páginas de detalhes do produto (PDPs), para mostrar a hierarquia de categoria de produtos e fornecer uma maneira rápida de se movimentar em um site. Um módulo de trilha de navegação também pode ser usado para mostrar um link "Voltar para resultados" quando os usuários abrem um PDP de uma página de pesquisa ou de listagem. Dessa forma, os usuários podem retornar rapidamente à página de listagem filtrada para continuar comprando.

Nas páginas que têm contexto de categoria de produto, como as páginas PDPs e de categoria, os módulos de trilha de navegação mostram a hierarquia de categoria. Em páginas sem contexto de categoria, os módulos de trilha de navegação mostram **&lt;Site raiz&gt; / &lt;Página atual&gt;** por padrão. Os módulos de trilha de navegação também podem ser configurados manualmente em outros tipos de páginas do site para mostrar links para páginas específicas no site.

> [!NOTE]
> O módulo de trilha de navegação está disponível na versão 10.0.12 do Dynamics 365 Commerce.

A imagem a seguir mostra um exemplo de um módulo de trilha de navegação que mostra a hierarquia de categoria em um PDP.

![Exemplo de um módulo de trilha de navegação.](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a>Configurações do módulo de trilha de navegação

O módulo de trilha de navegação depende da configuração de **Tipo de exibição de trilha de navegação em PDP**, que é definido em **Configurações de site \> Extensões** no assistente para criação de sites. Esta configuração tem três valores possíveis:

- **Mostrar hierarquia de categoria** – quando esse valor for selecionado, o módulo de trilha de navegação mostrará a hierarquia de categoria completa do produto exibido no PDP.
- **Mostrar voltar para resultados** – quando esse valor for selecionado, o módulo de trilha de navegação mostrará um link "Voltar para resultados" em um PDP se o usuário abrir o PDP a partir de um módulo que permita um link "Voltar para resultados". Essa funcionalidade está disponível quando os usuários navegam em páginas de listagem de categorias, pesquisa, listas e recomendação. Para dar suporte a essa funcionalidade, a coleção de produtos e os módulos de resultados de pesquisa têm uma propriedade denominada **Permitir voltar para resultados em PDP**. Essa propriedade oferece a flexibilidade de definir quais módulos devem dar suporte à funcionalidade de link "Voltar para resultados" no PDP. Por exemplo, quando **Mostrar voltar para resultados** for selecionado para a configuração **Tipo de exibição de trilha de navegação no PDP** do módulo de trilha de navegação e **Permitir voltar para resultados no PDP** for selecionado para o módulo de resultados de pesquisa da página de pesquisa, um link "Voltar para resultados" será mostrado quando os usuários navegarem da página de pesquisa para um PDP.
- **Mostrar hierarquia de categoria e voltar para resultados** – esse valor é uma combinação dos dois anteriores. Quando esse valor for selecionado, o módulo de trilha de navegação mostrará a hierarquia de categoria completa e um link "Voltar para resultados" (se estiver configurado) em um PDP.

> [!IMPORTANT]
> Essas configurações estão disponíveis na versão 10.0.12 do Dynamics 365 Commerce. Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="breadcrumb-module-properties"></a>Propriedades do módulo de trilha de navegação

| Nome da propriedade | Valores | Descrição |
|---------------|--------|-------------|
| Raiz | Texto ou link| Essa propriedade opcional especifica o texto do link e um destino de link para a raiz do site de trilha de navegação. Se essa propriedade não estiver configurada, nenhuma raiz será definida. |
| Link de trilha de navegação | Vínculo | Esta propriedade opcional especificará links para uma trilha de navegação configurada manualmente se esses links forem necessários. Os links aparecem na ordem em que estão listados. |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a>Adicionar um módulo de trilha de navegação a uma nova página

Para adicionar um módulo de trilha de navegação a um PDP e definir as propriedades necessárias, siga estas etapas.

1. Acesse **Configurações do Site \> Extensões**. Depois, para a configuração **Tipo de exibição de trilha de navegação em PDP**, selecione **Mostrar hierarquia de categoria**.
1. Acesse **Modelos** e selecione o modelo PDP.
1. No slot **Contêiner** que contém o módulo de caixa de compra, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Trilha** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e abra um PDP que utilize o modelo PDP. Se ainda não existir um PDP, crie um.
1. No slot **Contêiner** que contém o módulo de caixa de compra, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Trilha** e, depois, **OK**.
1. No painel de propriedades do slot **Trilha de navegação**, em **Raiz**, selecione **Texto do link**.
1. Na caixa de diálogo **Vincular texto**, digite **Início** e, em **Destino do link**, selecione **Adicionar um link**.
1. Na caixa de diálogo **Adicionar um link**, selecione um link para a raiz da trilha de navegação, e selecione **OK**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulos de menu de navegação](nav-menu-module.md)

[Módulo de seletor de sites](site-selector.md)

[Visão geral da página de aterrissagem da categoria padrão e da página de resultados da pesquisa](category-search-page-overview.md)

[Módulos de coleção de produtos](product-collection-module-overview.md)

[Módulo de caixa de compra](add-buy-box.md)

[SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
