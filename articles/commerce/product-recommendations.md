---
title: Visão geral de recomendações de produtos
description: Este tópico fornece informações gerais sobre as recomendações do produto. As recomendações de produtos permitem que os clientes encontrem com facilidade e rapidez os produtos que desejam e até produtos que não pretendiam comprar originalmente.
author: Moonma
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770037"
---
# <a name="product-recommendations-overview"></a>Visão geral de recomendações de produtos

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

O Microsoft Dynamics 365 Commerce pode ser usado para mostrar recomendações de produtos no site de comércio eletrônico e no dispositivo de ponto de venda (PDV). As recomendações de produtos são itens nos quais um cliente pode estar interessado. As recomendações baseiam-se em tendências de compra dos outros clientes em lojas online e físicas.

As recomendações de produtos permitem que os clientes encontrem com facilidade e rapidez os produtos que desejam, enquanto têm uma experiência que os atende bem. A venda cruzada e a adicional podem até ser usadas para ajudar os clientes a encontrar produtos adicionais que eles não pretendiam comprar originalmente. Quando as recomendações são usadas para ajudar na descoberta do produto, elas podem criar mais oportunidades de conversão, ajudar a aumentar a receita de vendas e até ajudar a aumentar a satisfação e retenção de clientes.

No Commerce, as recomendações de produtos são baseadas nas tecnologias de aprendizado de máquina do Microsoft Recommendations em larga escala.


## <a name="scenarios"></a>Cenários

As recomendações de produtos estão disponíveis para os seguintes cenários:

- **Em qualquer página da loja para navegação ou página inicial no comércio eletrônico:** Se os clientes ou associados da loja visitam uma página da loja, o mecanismo de recomendação pode sugerir produtos nas listas **Novo**, **Mais Vendidos** e **Mais Populares**.
- **Na página de detalhes do Produto:** Se os clientes ou associados da loja visitam uma página de **Detalhes do produto**, o mecanismo de recomendação sugere itens adicionais que provavelmente também serão comprados. Esses itens são exibidos na lista **As pessoas também gostam de** .
- **Na página da Transação ou na página de check-out:** O mecanismo de recomendação sugere itens, com base na lista completa de itens na cesta. Esses itens são exibidos na lista **Compra junto com frequência** .

## <a name="recommendation-service"></a>Serviço de recomendação

As recomendações de produtos usam as tecnologias de aprendizado de máquina das Recomendações da seguinte forma:

- Os dados no formato que o serviço de Recomendação exige é extraído do banco de dados operacional do Commerce e enviado à loja da Entidade.
- O serviço da recomendação usa os dados para treinar modelos da recomendação para as listas **As pessoas também gostam de**, **Frequentemente comprado junto**, **Novo**, **Mais vendidos** e **Mais populares** .

## <a name="additional-resources"></a>Recursos adicionais

[Habilitar recomendações de produtos](enable-product-recommendations.md)

[Criar curated listas organizadas de recomendação de produtos](create-editorial-recommendation-lists.md)

[Gerenciar resultados da recomendação de produtos com base em IA-ML](modify-product-recommendation-results.md)

[Adicionar listas de recomendações de produto às páginas](add-reco-list-to-page.md)
