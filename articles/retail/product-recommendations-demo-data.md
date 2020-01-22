---
title: Dados de demonstração das recomendações de produtos do Omnicanal
description: Este documento visa oferecer orientações sobre como aproveitar recomendações de produtos do omnicanal em ambientes de uma caixa da Camada 1 usando dados de demonstração personalizáveis pré-preenchidos.
author: bebeale
manager: AnnBe
ms.date: 12/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 31aa5dbd2fa814fd572024a4ae36b9d9b46a2fb0
ms.sourcegitcommit: 398c0652acde12c953de007d06055456d6e0a516
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2019
ms.locfileid: "2872317"
---
# <a name="omni-channel-product-recommendations-demo-data"></a>Dados de demonstração das recomendações de produtos do Omnicanal

Este documento visa oferecer orientações sobre como aproveitar recomendações de produtos do omnicanal em ambientes de uma caixa da Camada 1 usando dados de demonstração personalizáveis pré-preenchidos.

As recomendações de produtos do omnicanal fornecem um conjunto de listas de produtos editorialmente organizado ou gerado de forma programática. Essas listas podem ser usadas em vários cenários, conforme a necessidade comercial. Para obter mais informações sobre listas de recomendações de produtos, consulte [Visão geral das recomendações de produtos.](../commerce/product-recommendations.md)

Para Ambientes do Dynamics da Camada 2 e mais altas, as recomendações de produtos são computadas automaticamente com base nos dados do cliente.
Usar dados de demonstração das recomendações de produtos não desabilita nenhuma solução de recomendações de produtos já provisionada no ambiente e nenhum custo associado ao seu uso.

Para ambientes da Camada 1, as recomendações de produtos são baseadas somente nos dados estáticos de demonstração armazenados em um arquivo csv.

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>Ativando dados de demonstração das recomendações de produtos em um ambiente

Os clientes devem implantar a **Extensão da Demonstração da Versão Prévia do Dynamics 365 Commerce** ao respectivo ambiente, a qual habilita automaticamente os dados de demonstração das recomendações de produtos.

## <a name="default-demo-data"></a>Dados de demonstração padrão
Cada tipo de ambiente do Onebox vem com um conjunto pré-carregado de dados de demonstração das recomendações de produtos armazenados no arquivo separado por vírgulas **“reco_demo_data.csv”**, localizado na mesma pasta que este documento no Retail Server.

Esses dados são estruturados ao longo das seguintes colunas

| Nome da coluna         | Obrigatório          | Descrição                                                                                                                                 | Valores Possíveis                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| RecoList            | :heavy_check_mark: | O tipo específico da lista de recomendações de produtos que o ponto de dados de demonstração vai gerar.                                                    | <ul><li>RecoBestSelling</li><li>RecoNew</li><li>RecoTrending</li><li>RecoCart</li><li>RecoPeopleAlsoBuy</li></ul> |
| OperatingUnitNumber | :heavy_check_mark: | O número específico da unidade operacional na qual espera-se que surjam as recomendações de produtos.                                        |                                                                              |
| Categoria            |                    |    A categoria para a qual a lista específica deve ser retornada. Se nenhuma categoria for especificada, a lista será somente para a parte superior da hierarquia de navegação.    |                                                                              |
| SeedItemId          |                    |    Para listas que exigem a semente (RecoPeopleAlsoBuy e RecoCart) os produtos para os quais essas listas devem mostrar produtos adicionais.            |                                                                              |
| ItemIds             | :heavy_check_mark: | Um ou mais produtos a serem retornados como o resultado, separados por **“;”**.                                                                  |                                                                              |


## <a name="customize-demo-data"></a>Personalizar dados de demonstração
Os clientes podem editar os dados de demonstração padrão com todas as informações de produtos e categorias que são configurada na matriz. Depois que o CSV for atualizado, as recomendações de produtos retornadas para os clientes refletirão imediatamente as alterações.

A extensão contém um arquivo de dados chamado RecoMockDataset.csv que permite que o cliente controle o conjunto de dados usado para fornecer os resultados fictícios de recomendações. O nome de arquivo pode ser controlado por meio da configuração da extensão usando a configuração **ext.Recommendations.DemoFilePath** . Isso permite que os clientes tenham vários conjunto de dados disponíveis que podem ser alternados com facilidade por meio da configuração.

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de recomendações de produtos](../commerce/product-recommendations.md)

[Planejamento de ambiente](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
