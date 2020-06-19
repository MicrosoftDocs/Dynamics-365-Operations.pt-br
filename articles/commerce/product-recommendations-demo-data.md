---
title: Criar recomendações com dados de demonstração
description: Este tópico oferece orientações sobre como aproveitar recomendações de produtos do omnicanal em ambientes de uma caixa da Camada 1 usando dados de demonstração personalizáveis pré-preenchidos.
author: bebeale
manager: AnnBe
ms.date: 05/26/20
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 68275f3e36bce0f641b0273cf3b3b8c8ce9db137
ms.sourcegitcommit: fdc5dd9eb784c7d8e75692c8cdba083fe0dd87ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2020
ms.locfileid: "3404316"
---
# <a name="create-recommendations-with-demo-data"></a>Criar recomendações com dados de demonstração

[!include [banner](includes/banner.md)]

Este tópico oferece orientações sobre como aproveitar recomendações de produtos do omnicanal em ambientes de uma caixa da Camada 1 usando dados de demonstração personalizáveis pré-preenchidos.

As recomendações de produtos do omnicanal fornecem um conjunto de listas de produtos editorialmente organizados ou gerados de forma programática. Essas listas podem ser usadas em vários cenários, conforme a necessidade comercial. Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](product-recommendations.md)

Para ambientes do Dynamics 365 da Camada 2 e mais altas, as recomendações de produtos são computadas automaticamente com base nos dados do cliente. Usar dados de demonstração das recomendações de produtos não desabilita nenhuma solução de recomendações de produtos já provisionada no ambiente e nenhum custo associado ao seu uso.

Para ambientes da Camada 1, as recomendações de produtos são baseadas somente nos dados estáticos de demonstração armazenados em um arquivo .csv.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Ativando dados de demonstração das recomendações de produtos em um ambiente
Para habilitar a data de demonstração das recomendações do produto, você precisa implantar a Extensão da Demonstração da Versão Prévia do Dynamics 365 Commerce para o respectivo ambiente. Esta ação habilita automaticamente os dados de demonstração das recomendações.

## <a name="default-demo-data"></a>Dados de demonstração padrão
Cada tipo de ambiente do OneBox vem com um conjunto pré-carregado de dados de demonstração das recomendações de produtos no arquivo separado por vírgulas 'reco_demo_data.csv', localizado no Commerce Scale Unit.

Os dados são estruturados ao longo das seguintes colunas:

| Nome da coluna         | Início de obrigatoriedade da entrega no curso do ano calendário          | descrição                                                                                                                                 | Valores possíveis                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | O tipo específico da lista de recomendações de produtos que o ponto de dados de demonstração vai gerar.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | O número específico da unidade operacional na qual espera-se que surjam as recomendações de produtos.                                        |                                                                              |
| Categoria            |                    |    A categoria para a qual a lista específica deve ser retornada. Se nenhuma categoria for especificada, a lista será somente para a parte superior da hierarquia de navegação.    |                                                                              |
| SeedItemId          |                    |    Para listas que exigem semente (RecoPeopleAlsoBuy and RecoCart), o produto para o qual essas listas devem mostrar produtos adicionais.            |                                                                              |
| ID do Cliente          |                    |    Para listas que exigem um identificador de cliente (RecoPicks).  O valor padrão '0' se aplica a todos os clientes.          |                                                                              |
| ItemIds             | :heavy_check_mark: | Um ou mais produtos a serem retornados como o resultado, separados por ';'.                                                                  |                                                                              |

## <a name="customize-demo-data"></a>Personalizar dados de demonstração
Você pode editar os dados de demonstração padrão com quaisquer informações de produtos e categorias configurados na matriz. Depois que o .csv for atualizado, as recomendações de produtos retornadas para os clientes refletirão imediatamente as alterações.

A extensão contém um arquivo de dados chamado 'RecoMockDataset.csv', que permite que você controle o conjunto de dados usado para fornecer os resultados fictícios das recomendações. O nome de arquivo pode ser controlado por meio da configuração da extensão usando a configuração **ext.Recommendations.DemoFilePath** . Isso permite que você tenha vários conjuntos de dados disponíveis que podem ser alternados com facilidade por meio da configuração.


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das recomendações dos produtos](product-recommendations.md)

[Habilitar Azure Data Lake Storage em um ambiente do Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendações dos produtos](enable-product-recommendations.md)

[Habilitar recomendações personalizadas](personalized-recommendations.md)

[Cancelar recomendações personalizados](personalization-gdpr.md)

[Adicionar recomendações de produtos no PDV](product.md)

[Adicionar recomendações à tela de transação](add-recommendations-control-pos-screen.md)

[Ajustar os resultados das recomendações de AI-ML](modify-product-recommendation-results.md)

[Criar manualmente recomendações selecionadas](create-editorial-recommendation-lists.md)

[Perguntas frequentes sobre recomendações de produtos](faq-recommendations.md)
