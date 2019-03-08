---
title: Visão geral das informações do produto
description: Este tópico fornece informações sobre o gerenciamento de informações do produto. O gerenciamento de informações do produto funciona com uma definição, categorização e identificação de produtos compartilhados em todas as entidades legais, bem como configurações específicas de um produto, para se adequar aos processos de negócios.
author: cvocph
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0ac817fc4e8329563e524cea967c8337262fe2c3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "363007"
---
# <a name="product-information-overview"></a>Visão geral das informações do produto

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Este tópico fornece informações sobre o gerenciamento de informações do produto. O gerenciamento de informações do produto funciona com uma definição, categorização e identificação de produtos compartilhados em todas as entidades legais, bem como configurações específicas de um produto, para se adequar aos processos de negócios. 

A informação do produto é a espinha dorsal da cadeia de suprimentos e aplicações de varejo em todas as indústrias. Refere-se a processos e tecnologias que se concentram no gerenciamento centralizado de informações sobre produtos (por exemplo, através de cadeias de suprimentos). É crucial que as definições, documentação, atributos e identificadores de produtos compartilhados sejam usados. Nos vários módulos de uma solução de negócios, são necessárias informações e configuração específicas do produto para gerenciar os processos de negócios relacionados a produtos específicos, famílias de produtos ou categorias de produtos.

## <a name="product-definition"></a>Definição de produto

Um produto é definido principalmente por um número de produto, nome e descrição. No entanto, outros dados também são necessários para descrever um produto ou serviço:

- Tipo de produto: Item ou serviço
- Subtipo de produto: produtos distintos ou mestres de produtos
- Definição do modelo da variante do produto:

     - Dimensões do produto e grupos de dimensão
     - Nomenclatura de produto
     - Modelos de configuração do produto

- Associação do produto a uma ou mais categorias
- Definição dos atributos de categoria e produto
- Imagens do produto
- Anexos
- Unidades de medida e conversões relacionadas
- Traduções para todos os nomes e descrições

## <a name="distribution-export-and-import-of-product-data"></a>Distribuição, exportação e importação de dados do produto

A definição do produto pode ser criada no Microsoft Dynamics 365 for Finance and Operations. Também pode ser importado do gerenciamento do ciclo de vida do produto (PLM), do gerenciamento de dados do produto (PDM) ou dos sistemas de gerenciamento de informações do produto (PIM). Quando mais de uma instância do Finance and Operations é usada, uma instância normalmente é usada como o mestre dos dados do produto para todas as outras instâncias. Esta abordagem é suportada por um grande conjunto de entidades de dados que permitem exportar e importar dados de definição de produto de uma instância para outra.

Para suportar a distribuição de dados do produto em muitas instâncias, o Finance and Operations permite que você use o Common Data Service. As definições de produto podem ser exportadas de uma instância do Finance and Operations para o Common Data Service. As definições dos produtos podem então ser usadas para fornecer outros aplicativos de negócios, como o Microsoft Dynamics 365 for Sales, com dados do produto.

Observe que, em organizações dinâmicas e ágeis, os dados da informação do produto são alterados todos os dias. Portanto, a manutenção de dados de produtos precisos e reais é um processo de negócios crítico por conta própria.

## <a name="product-masters-and-product-variants"></a>Mestres de produtos e variantes de produtos

Em um mundo ágil, onde os produtos devem ser rapidamente adaptados aos requisitos do cliente, as definições dos produtos especificam um conjunto de produtos em vez de produtos distintos. No Microsoft Dynamics 365 for Finance and Operations, esses produtos genéricos são conhecidos como *produtos mestres*. Os mestres de produtos possuem a definição e as regras que especificam a forma como os produtos distintos são descritos e se comportam nos processos comerciais. Com base nessas definições, produtos distintos podem ser gerados. Esses produtos distintos são conhecidos como *variantes de produto*.

No Finance and Operations, um mestre de produto está associado a um grupo de dimensão de produto e a uma tecnologia de configuração para especificar as regras de negócios. As dimensões do produto (cor, tamanho, estilo e configuração) são um conjunto específico de atributos que podem ser usados ​​em todo o aplicativo para definir e rastrear comportamentos específicos dos produtos relacionados. Essas dimensões também ajudam os usuários a procurar e identificar os produtos.

## <a name="configuration-technologies"></a>Tecnologias de configuração

Você pode escolher entre três tecnologias de configuração:

- As variantes predefinidas são definidas por dimensões de produto predefinidas. A definição variante inclui a definição de uma combinação de dimensões válida específica, como cor, estilo e tamanho. Cada combinação produz uma variante de produto distinta.
- A configuração baseada em dimensão geralmente é usada em cenários de fabricação e permite que você use a dimensão de configuração na definição de contas de materiais (BOMs). Depois que uma configuração específica é selecionada, o sistema usa o subconjunto de linhas BOM que são válidas para essa configuração para planejamento e produção. O conceito é conhecido como *BOM global*, pois uma BOM compartilhada é usada para todas as configurações de um produto.
- A configuração baseada em restrições usa um modelo de configuração do produto para descrever todos os atributos e componentes possíveis que são necessários para descrever todas as variantes possíveis de um produto em um único modelo. As restrições de combinações de atributos podem ser descritas através de expressões regulares ou restrições baseadas em tabelas. Os modelos e configuradores de configuração tornam-se mais importantes no gerenciamento de informações do produto e são usados ​​em todas as indústrias.

Quando você planeja a implementação do Finance and Operations, é muito importante que você escolha a tecnologia de configuração correta para um processo comercial. Um produto não pode ser convertido de um modelo para outro após a implementação.

## <a name="product-variant-model-definition-workspace"></a>Área de trabalho de definição de modelo de variante de produto

A área de trabalho **Definição de modelo de variante de produto** apresenta uma visão geral dos mestres de produto. Também mostra o status do lançamento de mestres e variantes relacionadas a entidades legais específicas.

## <a name="released-products"></a>Produtos liberados

Os produtos que são lançados para uma entidade legal específica são conhecidos como *produtos lançados*. Os produtos podem ser lançados em massa para uma entidade legal ou para muitas entidades legais de cada vez. Uma vez que várias propriedades e atributos dos produtos podem ter que ser adicionados por entidade legal, a área de trabalho **Manutenção do produto liberado** permite monitorar e completar os produtos recentemente lançados em cada entidade legal ou nas suborganizações de uma entidade legal.

### <a name="released-product-maintenance-workspace"></a>Área de trabalho de manutenção de produto liberado

Você pode definir a área de trabalho **Manutenção do produto liberado** no item de menu **Configurar minha área de trabalho**. Selecione uma hierarquia de categorias e uma categoria para filtrar a área de trabalho. Para ajustar os dados relevantes de produto na área de trabalho, você também pode definir, em dias, os limites de tempo para **Produtos lançados recentemente** e **Produtos liberados interrompidos**.

A área de trabalho consiste em um resumo dos blocos e duas listas. A lista **Casos abertas** mostra casos de alteração de produto que possuem produtos na hierarquia de categoria de produto selecionada que não estão completos e fechados. A lista **Liberado recentemente** mostra produtos que foram liberados dentro da barreira de tempo configurada na configuração do espaço de trabalho. Para cada item da lista, a validação é executada e o status da validação é exibido. Esse status pode indicar que as configurações necessárias para a entidade legal não foram concluídas. Da lista, você pode acessar as páginas **Detalhes do produto liberado**, **Manutenção de atributos do produto**, **Manutenção da categoria de produtos**, **Configurações de ordem padrão**, e **Traduções de texto** para concluir a configuração necessária de produto.

### <a name="manually-creating-a-new-released-product"></a>Criando manualmente um novo produto lançado

Você pode criar manualmente um produto lançado em uma única execução, dependendo dos processos comerciais da organização e de quaisquer regras sobre se essa função deve ser usada. Esta função cria um novo produto e o libera automaticamente para a entidade legal atual. Para criar um novo produto, clique em **Produtos liberados** na área de trabalho **Manutenção do produto liberado** ou na página **Produtos lançados**.
