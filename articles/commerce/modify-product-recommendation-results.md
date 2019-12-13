---
title: Gerenciar resultados da recomendação de produtos com base em IA-ML
description: Este tópico explica como personalizar os resultados da recomendação do produto com base em aprendizado de máquina de inteligência artificial (AI-ML) para sua empresa.
author: bebeale
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
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 669b056c38614c8ac9be2d7b244a0ab0c73bc9f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770061"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a>Gerenciar resultados da recomendação de produtos com base em IA-ML

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico explica como personalizar os resultados da recomendação do produto com base em aprendizado de máquina de inteligência artificial (AI-ML) para sua empresa. 

Depois de habilitar as recomendações do produto, as configurações padrão entrarão em vigor; esses parâmetros funcionarão, podem funcionar para muitas necessidades. É melhor planejar gastar algum tempo avaliando se os resultados se encaixam no movimento de venda dos produtos. Sugerimos avaliar os resultados por alguns dias antes de alterar os parâmetros, conforme necessário, antes de testar novamente. 

## <a name="understanding-recommendation-list-parameters"></a>Compreendendo os parâmetros da lista de recomendação

Antes de alterar os parâmetros, saiba como eles afetarão os resultados a seguir.

### <a name="trending-product-list"></a>Lista de produtos mais populares

A lista de produtos **Mais populares** tem dois parâmetros que podem ser alterados: ![Exemplo de parâmetros padrão da lista Mais populares](./media/exampletrendingparameters.png)
1. **Incluir novos produtos dos últimos X dias** - Os produtos que foram adicionados dentro do número especificado de dias, antes da data atual, podem ser usados para selecionar candidatos ao produto. O valor padrão na imagem sugere que produtos antigos com 180 dias podem ser usados na lista de tendências de produtos.
1. **Incluir vendas dos últimos X dias** - As transações de vendas que ocorreram dentro do número especificado de dias, antes da data atual, podem ser usadas para solicitar os produtos. O valor padrão acima sugere que todas as compras de um produto, feitas nos últimos 30 dias, seriam usadas para determinar a colocação do produto na lista de produtos mais populares. 

### <a name="best-selling-product-list"></a>Lista de produtos mais vendidos

Dependendo do seu negócio, o mais vendido pode trazer resultados diferentes do mais popular, mesmo que os dois usem dados de transação para solicitar produtos. Como a melhor venda não tem suspensão com base na data do sortimento, ela ainda pode destacar produtos muito populares e antigos que podem ter sido retirados da lista de tendências. 

A lista de produtos de **Melhor venda** tem um parâmetro que pode ser alterado:

![Exemplo de parâmetro padrão da lista de Melhor venda](./media/examplebestsellingparameters.PNG)
1. **Incluir vendas dos últimos X dias** - As transações de vendas que ocorreram dentro do número especificado de dias, antes da data atual, podem ser usadas para solicitar os produtos. O valor padrão acima sugere que todas as compras de um produto, feitas nos últimos 30 dias, seriam usadas para determinar a colocação do produto na lista de produtos Mais vendidos. 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a>Adicionar ou remover manualmente produtos das listas de recomendação

### <a name="for-new-trending-or-best-selling"></a>Para Novo, Mais Populares ou Mais vendidos

1.  Vá para **Varejo** > **Recomendações do produto** > **Parâmetros de recomendação**.
1.  Na lista de parâmetros de varejo compartilhados, selecione **Listas de recomendação**.
1.  Selecione a lista da qual serão adicionados ou removidos os produtos.
1.  Para adicionar produtos à tabela, selecione **Adicionar linha**. 
1.  Na coluna Produto, procure um produto por **Nome** ou **Número do produto.**
![Exemplo de como procurar um produto na lista Novo produto](./media/examplenewlistconfiguration1.png)
1.  Na coluna Tipo de linha, selecione uma das duas opções:
    -   **Incluir** – coloca um produto à frente da lista
    -   **Excluir** – impede que um produto apareça na lista ![Exemplo de Como Incluir ou Excluir um produto da lista Novo produto](./media/examplenewlistconfiguration2.png)
1.  Alterar a **Ordem de exibição** alterará a ordem na qual os produtos marcados como **incluir** aparecerão na lista.
    - Se dois produtos tiverem o mesmo valor de **ordem de exibição**, então a ordem final desses dois resultados pode ser diferente do back office.
1.  Para remover os produtos da tabela: selecione a linha para remover e selecione **Remover**.


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a>Para as listas de As pessoas também gostam ou Frequentemente comprado junto

No contexto das listas **Frequentemente comprado junto** ou **As pessoas também gostam**, o aprendizado de máquina é usado para analisar os padrões de compra do consumidor para recomendar produtos relacionados, geralmente adquiridos juntos, para um produto de origem exclusivo. 
 
Um **produto de origem** é o produto para o qual você deseja gerar resultados. No contexto de ajuste manual das listas de recomendação, você está adicionando ou removendo resultados desse produto. 

Siga estas etapas para adicionar ou remover manualmente os resultados de um produto de origem:
1.  Selecione o **Produto de origem**. 
1.  Na coluna **Produto**, procure um produto por **Nome** ou **Número do produto.**
![Exemplo de como procurar um produto na lista Frequentemente comprado junto](./media/exampleFBTlistconfiguration1.png)
1. Na coluna **Tipo de linha**, selecione uma das duas opções:
    - **Incluir** – coloca um produto à frente da lista
    - **Excluir** – impede que um produto apareça na lista     
![Exemplo de Como Incluir ou Excluir um produto na lista de Frequentemente comprado junto](./media/exampleFBTlistconfiguration2.png)
1.  Para remover os produtos da tabela: selecione a linha para remover e selecione Remover.


## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de recomendações de produtos](product-recommendations.md)

[Habilitar recomendações de produtos](enable-product-recommendations.md)

[Adicionar listas de recomendações de produto às páginas](add-reco-list-to-page.md)
