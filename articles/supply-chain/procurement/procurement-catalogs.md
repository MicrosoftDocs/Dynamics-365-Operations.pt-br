---
title: "Catálogos de compras"
description: "Este artigo descreve, em um alto nível, como os profissionais de compras podem configurar e manter os catálogos de aquisições. Os catálogos de compras definem os itens e os serviços que os funcionários da empresa podem solicitar para uso interno."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f51fb41e19a47a9db02166de91b9e027154d6a7d
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="procurement-catalogs"></a>Catálogos de compras

[!INCLUDE [banner](../includes/banner.md)]

Este artigo descreve, em um alto nível, como os profissionais de compras podem configurar e manter os catálogos de aquisições. Os catálogos de compras definem os itens e os serviços que os funcionários da empresa podem solicitar para uso interno.

Os profissionais de compra podem criar e manter catálogos de itens e serviços que podem ser comprados para uso interno em uma organização. Depois que os catálogos são configurados, os funcionários da empresa podem criar requisições de compra a partir deles. Os catálogos podem ser usados para aplicar as políticas de compras, de modo que os funcionários possam solicitar somente os itens e os serviços que permitidos para a entidade legal de compra. Ao criar um catálogo de compras, você deverá considerar as seguintes tarefas:

-   Configurar a hierarquia de categorias de compras antes de criar o catálogo.
-   Determine quais produtos você deseja que seus funcionários consigam solicitar. Você pode mostrar ou ocultar produtos específicos em um nó de catálogo, ou você pode mostrar ou ocultar todos os produtos em um nó.
-   Determine quantos catálogos de compras são necessários. Acesso a um catálogo de compras é determinado pela regra de políticas do catálogo que você configurar para a entidade legal e a unidade operacional a que um funcionário está atribuído.

Vários fatores determinam os produtos que os funcionários podem solicitar e as categorias de compras que podem ser usadas ao criar requisições de compra:

-   A regra da política de acesso da categoria na política de compras determina quais categorias de compra estão disponíveis na requisição de compra. Se nenhuma regra for definida, todas as categorias de compras ficarão disponíveis.
-   Os funcionários podem solicitar um produto somente se ele estiver no catálogo de compras ativo de sua organização e se ele estiverem em um nó habilitado e não oculto. O produto também deve estar em uma categoria que um funcionário específico possui acesso, de acordo com as regras de política de acesso da categoria.
-   A regra de política do catálogo especifica o catálogo que é usado. Se nenhuma regra de política de catálogo for definida, a regra de acesso de categoria sozinha determinará os produtos que um funcionário pode solicitar na requisição.

## <a name="prerequisites"></a>Pré-requisitos
A tabela a seguir descreve as tarefas que devem ser concluídas antes que o profissional possa criar um catálogo de compras.

| Tarefa                                                | Função               | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar uma hierarquia de categorias de compras.            | Gerente de compras | As hierarquias de categorias de compras classificam os itens ou transações para gerar relatórios e análises. Ao usar a hierarquia de categorias de compras, as empresas podem gerenciar categorias, produtos, fornecedores e outros fatores de compras de maneira estratégica para um local central. Uma hierarquia de categorias de compras é definida por uma organização inteira. O catálogo baseia-se na hierarquia de categorias de compras: as categorias na hierarquia se transformam em nós no catálogo. Os fornecedores e os produtos são incluídos no catálogo. |
| Adicionar fornecedores e produtos para as categorias de compras. | Gerente de compras | Quando a hierarquia de categorias de compras é criada para sua organização, cada categoria de compras pode ser associada aos fornecedores específicos, produtos, e assim por diante. Essas associações são copiadas automaticamente para o catálogo.                                                                                                                                                                                                                                                                                           |

## <a name="setting-up-a-catalog"></a>Configurando um catálogo
Depois que os pré-requisitos forem atendidos, você pode configurar catálogos. Você pode criar um catálogo que sua organização inteira usa ou vários catálogos que as diversas divisões de sua organização usam. Se você criar um catálogo para a organização inteira, o acesso ao catálogo será controlado pelas regras da política de compras.  

O catálogo define quais produtos estão disponíveis quando as requisições de compra são criadas, mas você pode usar as regras da política de acesso de categoria para aplicar restrições adicionais. Como os nós de um catálogo são categorias de compras, eles podem ser suprimidos por uma regra da política de acesso de categoria. Nesse caso, os produtos nessa categoria não estão disponíveis para os funcionários usarem em requisições. Você define regras de diretiva de acesso da categoria de compras na página **Políticas de compra**. A tabela a seguir descreve as tabelas que devem ser concluídas para configurar um catálogo.

| Tarefa                                                   | Função             | Descrição                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Criar um novo catálogo.                                  | Agente de compras | Quando você cria um catálogo, você especifica um nome e uma descrição para o catálogo. Também é possível definir se o catálogo é atualizado automaticamente ou manualmente, e especificar o proprietário do catálogo.                                                                                                                                      |
| Controlar se os produtos estão disponíveis no catálogo. | Agente de compras | Como os produtos são herdados das categorias de compra, todos aparecem nos nós apropriados do catálogo. É possível controlar se todos os produtos em um nó estão ocultos ou exibidos, quando o catálogo for usado em uma requisição de compra. Também é possível controlar se os produtos individuais em um nó ficam ocultos ou mostrados. |
| Publicar o catálogo.                                   | Agente de compras | Antes de um catálogo ficar disponível para os funcionários usarem em uma requisição, você deve definir uma regra da política do catálogo, definir o status de catálogo para **Ativo** e publicar o catálogo. Também é possível desativar quaisquer catálogos que você não deseja mais disponibilizar para seus usuários.                                              |

As atualizações são publicadas de forma automática ou manual, dependendo da opção selecionada para o catálogo no campo **Tipo de atualização padrão** na página **Catálogos**. Os seguintes tipos de atualização padrão estão disponíveis para catálogos:

-   **Dinâmico** – O catálogo é atualizado automaticamente sempre que for alterado.
-   **Estático** – Os catálogos devem ser atualizados manualmente.
-   **Ambos** – Se o catálogo tiver categorias de produto que têm um tipo de atualização padrão **Estática**, ele deverá ser atualizado manualmente quando essas categorias forem atualizadas. Se o catálogo tiver categorias de produtos com um tipo de atualização padrão **Dinâmica**, ele será atualizado sempre que ela for alterada.


<a name="see-also"></a>Consulte também
--------

[Configurar uma hierarquia de categorias de compras (guia de tarefas)](tasks/set-up-procurement-category-hierarchy.md)




