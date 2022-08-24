---
title: Colocar ordens de sites B2B rapidamente
description: Este artigo descreve os recursos do Microsoft Dynamics 365 Commerce que permitem que os usuários de sites business-to-business (B2B) coloquem ordens repetidas e em massa.
author: ShalabhjainMSFT
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.23
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: a153be1da43b63e8d29d6ece3dcbf47d5bbec487
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275111"
---
# <a name="place-b2b-website-orders-quickly"></a>Colocar ordens de sites B2B rapidamente

[!include [banner](../../includes/banner.md)]

Este artigo descreve os recursos do Microsoft Dynamics 365 Commerce que permitem que os usuários de sites business-to-business (B2B) coloquem ordens repetidas e em massa.

Os sites de comércio eletrônico B2B do Dynamics 365 Commerce permitem que os usuários executem operações padrão, como descobrir novos produtos por meio de pesquisa e navegação, exibir detalhes do produto, adicionar itens ao carrinho e finalizar compra. No entanto, enquanto os clientes dos sites business-to-consumer (B2C) geralmente encomendam itens em pequenas quantidades e os encomendam apenas uma vez, os clientes B2B normalmente encomendam itens em grandes quantidades e os encomendam novamente várias vezes. Como esses clientes geralmente sabem exatamente quais itens desejam comprar, eles geralmente ignoram a fase de descoberta de produtos e avançam diretamente para a encomenda. Para atender às necessidades desses clientes, os sites de comércio eletrônico B2B do Commerce fornecem vários recursos que ajudam a colocar ordens rapidamente.

## <a name="bulk-order-by-item-number"></a>Ordem em massa por número de item

Sites de comércio eletrônico B2B do Commerce permitem que os usuários dos sites adicionem itens ao carrinho inserindo números de item do produto juntamente com a quantidade desejada.

A ilustração a seguir mostra um exemplo de uma entrada de ordem rápida por número de item do produto.

![Entrada de ordem rápida por número de item de produto.](../media/QuickAddByItem.png)

## <a name="bulk-order-by-variant"></a>Ordem em massa por variante

Sites de comércio eletrônico B2B do Commerce permitem que os usuários de sites adicionem rapidamente variantes diferentes do mesmo produto em uma única exibição, que mostra a disponibilidade do estoque por tamanho, cor e estilo. Além disso, os usuários dos sites podem inserir facilmente a mesma quantidade para todos os produtos em estoque, selecionando **Inserir todas as quantidades**.

A ilustração a seguir mostra um exemplo de entrada de ordem rápida em que a funcionalidade "Inserir todas as quantidades" é usada.

![Entrada de ordem rápida que usa a funcionalidade "Inserir todas as quantidades".](../media/MatrixView.png)

## <a name="use-order-templates-for-quick-order-entry"></a>Usar modelos de ordem para entrada de ordem rápida

Os compradores em sites B2B geralmente solicitam itens específicos em conjunto. Por exemplo, se você estiver colocando ordens para um site de construção, talvez queira encomendar camisas, casacos, calças, sapatos e capacetes também. Se você estiver colocando ordens para um hospital, no qual médicos, enfermeiros e a equipe de limpeza têm uniformes diferentes, pode ser necessário agrupar cada tipo uniforme para facilitar a encomenda. Para esses tipos de cenários, os sites B2B do Commerce permitem que modelos de ordem sejam criados. Os usuários de sites podem criar qualquer número de modelos personalizados e, em seguida, encomendar todos ou alguns itens desses modelos, conforme necessário.

A ilustração a seguir mostra um exemplo de um modelo de ordem.

![Exemplo de um modelo de ordem.](../media/OrderTemplateHeader.png)

A ilustração a seguir mostra um exemplo da exibição de detalhes para um modelo de ordem.

![Exemplo da exibição de detalhes de um modelo de ordem.](../media/OrderTemplateLines.png)

## <a name="reorder-from-order-history"></a>Encomendar novamente no histórico de ordens

Sites de comércio eletrônico B2B do Commerce permitem que os usuários de sites encomendem rapidamente itens no seu histórico de ordens. Os usuários de sites podem comprar itens selecionados no histórico de ordens ou adicionar todos os itens comprados anteriormente ao carrinho.

A ilustração a seguir mostra um exemplo do histórico de ordens de um usuário e as opções para encomendar itens dele.

![Encomendar novamente no histórico de ordens.](../media/Reorder.png)

Este artigo descreveu apenas algumas maneiras pelas quais os sites B2B do Commerce ajudam os usuários a encontrar, encomendar e encomendar de novo os produtos desejados com rapidez. Mais recursos estão em desenvolvimento para simplificar ainda mais o processo de captura de ordens em massa.
