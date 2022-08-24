---
title: Gerenciamento de sortimentos
description: Este artigo explica os conceitos básicos do gerenciamento de classificação no Dynamics 365 Commerce e apresenta considerações de implementação do projeto.
author: josaw1
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-11-21
ms.dyn365.ops.version: Application update 5
ms.openlocfilehash: 255e0ccfd9e5cb41cdd0a3713d611f1e8008aadf
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279699"
---
# <a name="assortment-management"></a>Gerenciamento de classificação

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Visão Geral

O Dynamics 365 Commerce fornece *classificações* que permitem gerenciar a disponibilidade de produtos nos canais. As classificações determinam quais produtos estão disponíveis em lojas específicas e durante um período específico.

No Commerce, uma classificação é um mapeamento de um ou mais canais (ou grupos de canais, quando hierarquias de organização são usadas) para um ou mais produtos (ou grupos de produtos, quando hierarquias de categoria são usadas).

A combinação geral de produtos de um canal é determinada pelas classificações publicadas que são atribuídas ao canal. Portanto, você pode configurar várias classificações ativas por canal.

### <a name="basic-assortment-setup"></a>Configuração de classificação básica

No exemplo a seguir, uma classificação exclusiva é configurada para cada loja. Neste caso, somente o produto 1 está disponível na loja 1, e somente o produto 2 está disponível na loja 2.

![Cada produto está disponível em uma loja.](./media/Managing-assortments-figure1.png)

Para disponibilizar o produto 2 na loja 1, você pode adicioná-lo à classificação 1.

![Produto 2 adicionado à classificação 1.](./media/Managing-assortments-figure2.png)

Como alternativa, você pode adicionar a loja 1 à classificação 2.

![Loja 1 adicionada à classificação 2.](./media/Managing-assortments-figure3.png)

### <a name="organization-hierarchies"></a>Hierarquias da organização

Nas situações em que vários canais compartilham as mesmas classificações de produtos, você pode configurar as classificações usando a hierarquia da organização de classificação do Commerce. Quando os nós dessa hierarquia forem adicionados, todos os canais desse nó e seus nós secunDiários serão incluídos.

![Hierarquia da organização.](./media/Managing-assortments-figure4.png)

### <a name="product-categories"></a>Categorias de produto

Da mesma forma, no lado do produto, você pode incluir grupos de produtos usando hierarquias de categoria de produto. Você pode configurar classificações incluindo um ou mais nós da hierarquia de categoria. Nesse caso, a classificação incluirá todos os produtos nesse nó de categoria e seus nós secunDiários.

![Categorias de produto.](./media/Managing-assortments-figure5.png)

### <a name="excluded-products-or-categories"></a>Categorias ou produtos excluídos

Além de incluir produtos e categorias em classificações, você pode usar a opção Excluir para definir categorias ou produtos específicos que devem ser excluídos das classificações. No exemplo a seguir, você deseja incluir todos os produtos em uma categoria específica, exceto o produto 2. Nesse caso, você não precisa definir a classificação produto por produto ou criar nós de categoria adicionais. Em vez disso, você poderá apenas incluir a categoria, mas excluir o produto.

> [!NOTE]
> Se um produto for incluído e excluído em uma ou mais classificações por definição, ele sempre será considerado excluído.

![Produtos excluídos.](./media/Managing-assortments-figure6.png)

### <a name="global-and-released-products"></a>Produtos globais e liberados

As classificações são definidas em nível global e podem conter canais de várias entidades legais. Os produtos e as categorias incluídos em classificações também são compartilhados entre entidades legais. No entanto, um produto deve ser liberado antes que possa ser efetivamente vendido, encomendado, contado ou recebido no canal (por exemplo, no ponto de venda \[PDV\]). Portanto, embora duas lojas em entidades legais diferentes possam compartilhar uma classificação que contenha os mesmos produtos, os produtos ficam disponíveis somente se tiverem sido liberados para essas entidades legais.

### <a name="dynamic-and-static-assortments"></a>Classificações dinâmicas e estáticas

As classificações podem ser definidas com canais e produtos específicos ou incluindo unidades organizacionais e categorias. As classificações que incluem referências a esses grupos são consideradas dinâmicas. Se a definição ou o conteúdo desses grupos forem alterados enquanto a classificação estiver ativa, a definição da classificação também será alterada.

Por exemplo, uma classificação é originalmente definida e publicada para fazer referência a uma categoria de produtos. Se mais produtos forem adicionados posteriormente à categoria, esses produtos serão incluídos automaticamente na definição da classificação existente. Não é necessário adicionar os produtos à classificação manualmente. Da mesma forma, se uma unidade organizacional for adicionada a um nó diferente, a classificação da unidade organizacional será ajustada automaticamente com base nessa definição.

### <a name="stopped-products"></a>Produtos parados

Você pode “parar” produtos liberados para o processo de vendas ativando uma configuração nas configurações de **Ordem padrão**. Essa configuração costuma ser usada quando um produto está no final de sua vida útil e não deve ser vendido em nenhum canal. As classificações respeitam essa configuração, e os produtos parados não serão classificados, independentemente da configuração de classificação.

### <a name="blocked-products"></a>Produtos bloqueados

Além de interromper as vendas de um produto, você poderá bloqueá-las temporariamente. Você pode definir esta configuração na guia **Comércio** de um produto liberado. Os produtos bloqueados ainda são classificados, mas você receberá uma mensagem no PDV informando que o produto não pode ser vendido.

### <a name="date-effectivity"></a>Efetividade de data

As classificações têm data efetiva. Portanto, os varejistas podem configurar quando os produtos devem estar disponíveis ou não por canal. Você pode definir e publicar classificações com antecedência, e especificar as datas inicial e final. Os produtos ficarão automaticamente disponíveis ou indisponíveis nas datas especificadas.

### <a name="process-assortments-batch-job"></a>Processe o trabalho em lotes de classificações

As classificações definidas no Commerce devem ser processadas antes de entrarem em vigor. Esse processamento é feito pelos seguintes motivos:

- As definições de classificação devem deixar de ser normalizadas para que os canais possam consumi-las com mais facilidade. Uma combinação de produtos para um canal pode ser definida por meio de várias classificações que englobem vários intervalos de datas. Quando algumas dessas informações são calculadas com antecedência no servidor, o desempenho no canal melhora.
- Os produtos e canais na classificação podem mudar fora da classificação em si. As classificações dinâmicas que contêm referências a categorias ou unidades organizacionais devem ser processadas periodicamente para incluir ou excluir registros, com base na sua atribuição atual.

## <a name="implementation-considerations"></a>Considerações de implementação

Considere os seguintes requisitos de implementação ao planejar e gerenciar classificações para a sua implementação do Commerce:

- **Replicação de dados e tamanho do banco de dados** – Embora as classificações ajudem a servir a necessidade comercial de gerenciar a disponibilidade de produtos, elas também são uma ferramenta importante para gerenciar o tamanho de bancos de dados offline e de canal. Classificações bem gerenciadas ajudam a reduzir a quantidade de dados que deve ser processada e replicada para bancos de dados offline e de canal. Elas também ajudam a reduzir o número de registros que devem ser persistidos. Menos registros nesses bancos de dados aumentarão o desempenho quando você adicionar itens a uma transação, pesquisar e procurar produtos.
- **Classificações expirando/com data efetiva** – Uma das ferramentas mais eficazes para gerenciar o número de produtos em bancos de dado offline e de canal é a efetividade de data das classificações. Se você deixar classificações abertas (que não expiram) para produtos sazonais ou produtos que estejam no final de sua vida útil, esses bancos de dados crescerão indefinidamente. Você pode usar várias abordagens para ajudar a gerenciar essa situação. Por exemplo, você pode manter classificações separadas para produtos sazonais e produtos que estão sempre disponíveis.
- **Vendas e devoluções fora de classificações** – Este recurso ajuda os varejistas a gerenciar efetivamente suas classificações permitindo que eles limitem o número de produtos disponíveis para produtos que pertençam à combinação de produtos principal da loja. Esse recurso também ajuda os varejistas a lidar com situações em que um produto tenha sido omitido de uma classificação por engano, ou em que um produto tenha sido devolvido fora das datas efetivas da classificação.

Se os dados do produto não existirem no banco de dados do canal, o PDV realiza chamadas em tempo real para o headquarters a fim de recuperar as informações necessárias, para que o produto possa ser vendido, devolvido ou colocado em uma ordem de cliente. Informações sobre produtos recuperadas dessa forma estarão disponíveis somente durante o escopo dessa transação. O produto não é adicionado à definição de classificação. Portanto, as chamadas em tempo real subsequentes serão feitas conforme necessário.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
