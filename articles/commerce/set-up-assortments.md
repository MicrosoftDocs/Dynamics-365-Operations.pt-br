---
title: Configurar classificações
description: Este artigo descreve o que é um sortimento e explica como configurar sortimentos no Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 32edf6534716236706847556a14b951f18ef40ae
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969817"
---
# <a name="set-up-assortments"></a>Configurar classificações

[!include [banner](includes/banner.md)]

Este artigo descreve o que é um sortimento e explica como configurar sortimentos no Dynamics 365 Commerce.

Classificação é um conjunto de produtos relacionados atribuídos a um canal de comércio, como uma loja tradicional ou uma loja online. Use classificações para identificar os produtos disponíveis em cada loja. Uma classificação pode incluir categorias de produtos. Portanto, todos os produtos atribuídos a uma categoria específica são incluídos na classificação. Uma classificação também pode incluir produtos específicos e variantes de produtos específicos. Configurando uma classificação, você pode atribuir milhares de produtos aos seus canais ao mesmo tempo, em qualquer combinação que suas lojas exigirem. É possível configurar quantas classificações de produtos forem necessárias. Cada produto pode ser incluído em uma ou várias classificações, e cada classificação pode ser atribuída a um ou mais canais. Por exemplo, você define uma classificação que inclui um conjunto básico de produtos. Todas as lojas recebem essa classificação. Em seguida, você define outra classificação que inclui apenas equipamentos esportivos grandes. Somente as lojas maiores recebem essa classificação. O diagrama a seguir mostra como os produtos podem ser atribuídos a classificações, e como essas classificações podem ser atribuídas aos canais.

![Relações de classificação de produtos](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar uma classificação e atribuí-la a um canal de comércio, você deve concluir as tarefas a seguir.

| Tarefa                              | Descrição |
|-----------------------------------|-------------|
| Configurar um canal.          | Os canais representam uma loja tradicional, um loja online ou um mercado online. Você deve configurar pelo menos um canal e as opções para a loja. As classificações são atribuídas às lojas para identificar os produtos que determinada loja possui. |
| Criar uma hierarquia da organização. | Depois de configurar os canais de comércio para sua organização, você deve configurar uma hierarquia da organização de varejo que representa a estrutura organizacional dos seus canais. A hierarquia da organização pode ser usada para classificações, reabastecimento e relatórios. Adicionando seus canais a uma hierarquia da organização, você pode atribuir classificações a grupos de lojas. Em vez de atribuir a classificação individualmente a cada loja, você atribui a classificação ao nó da organização de nível superior. Assim, sempre que um novo canal for adicionado ao nó da organização de nível superior, esse canal herdará automaticamente todas as classificações atribuídas a esse nó. Você pode atribuir classificações somente a canais incluídos em uma hierarquia da organização atribuída à finalidade de **Classificação do Commerce**. |
| Definir produtos.                  | Para poder adicionar produtos a um sortimento, você deve adicioná-los ao Commerce. Você pode adicionar produtos manualmente, ou importá-los de um fornecedor. Depois de adicionar os produtos, você deve liberá-los para uma entidade legal. Somente os produtos liberados para uma entidade legal podem ser disponibilizados em seus canais de comércio. Os produtos que ainda não foram liberados para uma entidade legal podem ser adicionados a uma classificação, e a classificação pode ser aprovada. No entanto, até que os produtos tenham sido liberados para uma entidade legal, elas não podem ser disponibilizados nos canais. |
| Configurar uma hierarquia de categoria.      | Ao criar seus produtos de comércio, você pode agrupá-los e categorizá-los usando o recurso de hierarquia de categoria. Você pode criar uma hierarquia principal para agrupar e categorizar todos os produtos que você distribui por meio dos seus canais. Você também pode criar hierarquias de categoria complementares à parte para agrupar ou categorizar seus produtos para finalidades especiais, como promoções ou classificações. Usando hierarquias de categoria, você pode atribuir todos os produtos de uma categoria específica a uma classificação. Todos os produtos adicionados à categoria a ser incluída na classificação são incluídos automaticamente na classificação. Assim, na próxima execução do agendador de classificações de comércio, esses produtos serão disponibilizado para os canais ao qual a classificação foi atribuída. |

## <a name="setting-up-an-assortment"></a>Configurando uma classificação

Depois de concluir os pré-requisitos, você pode criar uma classificação e atribuí-la aos seus canais. Para configurar uma classificação, você deve concluir as seguintes tarefas.

1. Crie uma nova classificação, ou copie uma classificação existente.
2. Selecione os canais ou grupos de canais de nível superior aos quais a classificação se aplica.
3. Adicione categorias de produto, produtos individuais ou variantes de produtos à classificação. Você pode incluir todos os produtos em uma categoria específica ou pode excluir produtos selecionados de uma categoria incluída na classificação.
4. Publique a classificação. Quando você publica uma classificação, o agendador de classificações é executado automaticamente. Esse processo gera a lista de produtos. Quando esse processo é concluído, os produtos se tornam disponíveis nos canais aos quais a classificação de produtos foi atribuída. Se uma classificação publicada ou os canais aos quais a classificação é atribuída forem alterados, a classificação deverá ser atualizada. Para atualizar a classificação após alterações, você pode executar o agendador de classificações como um trabalho em lotes.


[!INCLUDE[footer-include](../includes/footer-banner.md)]