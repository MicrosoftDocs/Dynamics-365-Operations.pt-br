---
title: "Configurar classificações"
description: "Este artigo que descreve a classificação é e explica como configurar sortimentos no Microsoft Dynamics 365 para operações de varejo."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 906fc6eb42eb54cb3a3d5621377f250f59de20d7
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-assortments"></a>Configurar classificações

Este artigo que descreve a classificação é e explica como configurar sortimentos no Microsoft Dynamics 365 para operações de varejo.

Um sortimento é um conjunto de produtos relacionados atribuídos a um canal de varejo, como uma loja físicas almofariz ou um armazenamento online. Use classificações para identificar os produtos disponíveis em cada loja. Uma classificação pode incluir categorias de produtos. Portanto, todos os produtos atribuídos a uma categoria específica são incluídos na classificação. Uma classificação também pode incluir produtos específicos e variantes de produtos específicos. Configurando uma classificação, você pode atribuir milhares de produtos aos seus canais de varejo ao mesmo tempo, em qualquer combinação que suas lojas exigirem. É possível configurar quantas classificações de produtos forem necessárias. Cada produto pode ser incluído em uma ou várias classificações, e cada classificação pode ser atribuída a um ou mais canais de varejo. Por exemplo, você define uma classificação que inclui um conjunto básico de produtos. Todas as lojas recebem essa classificação. Em seguida, você define outra classificação que inclui apenas equipamentos esportivos grandes. Somente as lojas maiores recebem essa classificação. O diagrama a seguir mostra como os produtos podem ser atribuídos a classificações, e como essas classificações podem ser atribuídas aos canais de varejo. ![Relações de classificação de produtos](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Pré-requisitos
Antes de configurar uma classificação e atribuí-la a um canal de varejo, você deve concluir as tarefas a seguir.

| Tarefa                              | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurar um canal de varejo.          | Os canais de varejo representam uma loja tradicional, um loja online ou um mercado online. Você deve configurar pelo menos um canal de varejo e as opções para a loja. As classificações são atribuídas às lojas para identificar os produtos que determinada loja possui.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Criar uma hierarquia da organização. | Depois de configurar os canais de varejo para sua organização, você deve configurar uma hierarquia da organização de varejo que representa a estrutura organizacional dos seus canais de varejo. A hierarquia da organização pode ser usada para classificações, reabastecimento e relatórios. Adicionando seus canais de varejo a uma hierarquia da organização, você pode atribuir classificações a grupos de lojas. Em vez de atribuir a classificação individualmente a cada loja, você atribui a classificação ao nó da organização de nível superior. Assim, sempre que um novo canal de varejo for adicionado ao nó da organização de nível superior, esse canal herdará automaticamente todas as classificações atribuídas a esse nó. Você pode atribuir classificações somente a canais de varejo incluídos em uma hierarquia da organização atribuída à finalidade de **Classificação de varejo**. |
| Definir produtos.                  | Para poder adicionar produtos a uma classificação, você deve adicioná-los ao Microsoft Dynamics AX. Você pode adicionar produtos manualmente, ou importá-los de um fornecedor. Depois de adicionar os produtos, você deve liberá-los para uma entidade legal. Somente os produtos liberados para uma entidade legal podem ser disponibilizados em seus canais de varejo. Os produtos que ainda não foram liberados para uma entidade legal podem ser adicionados a uma classificação, e a classificação pode ser aprovada. No entanto, até que os produtos tenham sido liberados para uma entidade legal, elas não podem ser disponibilizados nos canais de varejo.                                                                                                                                                                                                                                                                                     |
| Configurar uma hierarquia de categoria.      | Quando você cria os produtos de varejo, é possível categorizar e agrupá-los usando o recurso de hierarquia de categoria em dynamics 365 para as operações. Você pode criar uma hierarquia principal para agrupar e categorizar todos os produtos que você distribui por meio dos seus canais de varejo. Você também pode criar hierarquias de categoria complementares à parte para agrupar ou categorizar seus produtos para finalidades especiais, como promoções ou classificações. Usando hierarquias de categoria, você pode atribuir todos os produtos de uma categoria específica a uma classificação. Todos os produtos adicionados à categoria a ser incluída na classificação são incluídos automaticamente na classificação. Assim, na próxima execução do agendador de classificações de varejo, esses produtos serão disponibilizado para os canais de varejo ao qual a classificação foi atribuída.                                            |

## <a name="setting-up-an-assortment"></a>Configurando uma classificação
Depois de concluir os pré-requisitos, você pode criar uma classificação e atribuí-la aos seus canais de varejo. Para configurar uma classificação, você deve concluir as seguintes tarefas.

1.  Crie uma nova classificação, ou copie uma classificação existente.
2.  Selecione os canais de varejo ou grupos de canais de varejo de nível superior aos quais a classificação se aplica.
3.  Adicione categorias de produto, produtos individuais ou variantes de produtos à classificação. Você pode incluir todos os produtos em uma categoria específica ou pode excluir produtos selecionados de uma categoria incluída na classificação.
4.  Publique a classificação. Quando você publica uma classificação, o agendador de classificações de varejo é executado automaticamente. Esse processo gera a lista de produtos. Quando esse processo é concluído, os produtos se tornam disponíveis nos canais de varejo aos quais a classificação de produtos foi atribuída. Se uma classificação publicada ou os canais de varejo aos quais a classificação é atribuída forem alterados, a classificação deverá ser atualizada. Para atualizar a classificação após alterações, você pode executar o agendador de classificações de varejo como um trabalho em lotes.



