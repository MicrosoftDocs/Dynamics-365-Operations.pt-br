---
title: Pesquisa de produtos e pesquisa de cliente no PDV
description: "Este tópico fornece uma visão geral de melhorias feitas à funcionalidade de pesquisa de produto e cliente no Dynamics 365 for Retail."
author: shalabhjain
manager: AnnBe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 66859535ee118ffc04a847dfe6e8e0bae1cd9d6c
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="overview-of-product-and-customer-search-in-point-of-sale"></a>Visão geral da pesquisa de produto e de cliente no ponto de venda

O Modern Point of Sale (MPOS) e o Cloud Point of Sale (CPOS) oferecem uma funcionalidade de pesquisa fácil de usar que permite armazenar pesquisa de funcionários rapidamente para produtos e clientes. A barra de pesquisa está sempre presente na parte superior do MPOS e do CPOS, de forma que os funcionários possam localizar produtos e clientes rapidamente.

Os funcionários podem procurar produtos nos catálogos e classificações que estão associados ao armazenamento atual e nos catálogos e classificações que estão associados a qualquer outro armazenamento da empresa. Portanto, os caixas podem vender e devolver produtos de fora da classificação de armazenamento. Da mesma forma, os funcionários podem procurar clientes que estão associados ao armazenamento atual ou a qualquer loja da empresa. Além disso, os funcionários podem procurar clientes que estão associados a uma empresa diferente na organização pai.

## <a name="product-search"></a>Pesquisa de produtos 

Por padrão, uma pesquisa de produtos é feita na classificação de armazenamento. Este tipo de pesquisa é conhecido como *pesquisa local do produto*. No entanto, os funcionários podem alternar facilmente para qualquer catálogo associado ao armazenamento atual, ou podem pesquisar em um armazenamento diferente. Este tipo de pesquisa é conhecido como *pesquisa remota do produto*. Para alterar o catálogo, selecione o botão **Categorias** no lado esquerdo da página. Na parte superior do painel que é exibido, selecione o botão **Alterar catálogo** e, em seguida, selecione um dos catálogos disponíveis para busca. O sistema pesquisará o catálogo de produtos selecionado.

Na página **Alterar catálogo**, os funcionários podem selecionar facilmente qualquer armazenamento ou podem procurar os produtos em todos os armazenamentos.

![Alterando o catálogo](./media/Changecatalog.png "Alterando o catálogo")
 
Uma pesquisa local do produto pesquisa dentro das seguintes propriedades do produto:

- Número do produto
- Nome do produto
- descrição
- Dimensões
- Código de barras
- Nome de pesquisa

### <a name="enhancements-to-local-product-searches"></a>Aprimoramentos em pesquisas locais do produto

A experiência de pesquisas locais de produto foram feitas de forma mais amigável. Os seguintes aperfeiçoamentos foram feitos:

- Os menus suspensos de produto e cliente foram adicionados à barra de pesquisa, dessa forma, esses funcionários podem selecionar **Produto** ou **Cliente** antes de fazerem a pesquisa. Por padrão, **Produto** é selecionado, conforme mostra a ilustração que segue.
- Para pesquisa de várias palavras-chave (isto é, para pesquisas que usam termos de pesquisa) os varejistas podem configurar se os resultados da pesquisa incluem resultados que correspondem a qualquer termo de pesquisa ou somente a resultados que correspondem a todos os termos da pesquisa. Esta configuração está disponível no perfil da funcionalidade de PDV, em um novo grupo chamado **Pesquisa de produto**. A configuração padrão é **Corresponder qualquer termo de pesquisa**. Esta configuração também é a configuração recomendada. Quando a configuração **Corresponder qualquer termo de pesquisa** for usada, todos os produtos que correspondem parcialmente ou totalmente a um ou mais termos de pesquisa são retornados como resultados e os resultados são classificados automaticamente em ordem ascendente de produtos que têm a maior parte das palavras-chaves (total ou parcial).

    A configuração **Corresponder todos os termos de pesquisa** retorna apenas os produtos que correspondem a todos os termos da pesquisa (total ou parcial.) Essa configuração é útil quando os nomes de produto são mais longos e os funcionários querem ver somente produtos limitados nos resultados da pesquisa. Porém, esse tipo de pesquisa têm duas limitações:

    - A pesquisa é feita em propriedades de produto individuais. Por exemplo, somente os produtos que têm todas as palavras-chave pesquisadas em pelo menos uma propriedade de produto são retornados.
    - As dimensões não são pesquisadas.

- Fornecedores podem agora configurar a pesquisa de produtos para mostrar sugestões de pesquisa como nomes de produto do tipo de usuário. Uma nova configuração para esta funcionalidade está disponível para o perfil da funcionalidade de PDV, em um grupo chamado **Pesquisa de produto**. A configuração é chamada **Mostrar sugestões de pesquisa ao digitar**. Esta funcionalidade pode ajudar funcionários a encontrar rapidamente o produto que eles estão pesquisando, porque eles não precisam digitar o nome completo manualmente.
- O algoritmo de pesquisa do produto agora também procura os termos pesquisados na propriedade **Pesquisar nome** do produto.

![Sugestões de produto](./media/Productsuggestions.png "Sugestões de produto")

## <a name="customer-search"></a>Pesquisa de Cliente

A pesquisa de cliente será usada para localizar clientes para várias finalidades. Por exemplo, os caixas podem querer ver uma lista de desejos do cliente ou o histórico de vendas, ou adicionar o cliente a uma transação. No caso de pesquisas de várias palavras-chave, o algoritmo de pesquisa do cliente retorna todos os clientes que correspondem a qualquer uma das palavras-chave pesquisadas. Porém, os clientes correspondentes à maioria de palavras-chave aparecem na parte superior dos resultados. Esse comportamento é análogo a forma como outros mecanismos pesquisa mostram a resultados. Primeiro eles mostram os resultados que correspondem aos termos mais pesquisados e depois, eles mostram os resultados que correspondem parcialmente às palavras-chave da pesquisa. Esse comportamento ajuda os caixas em situações que eles usam várias palavras-chave para suas pesquisas, mas uma das palavras-chave tem um erro de ortografia.

Por padrão, uma pesquisa de cliente é feita em catálogos de endereços do cliente associados ao armazenamento. Este tipo de pesquisa é conhecido como *pesquisa local do cliente*. Porém, os funcionários também podem pesquisar os clientes globalmente. Em outras palavras, eles podem pesquisar nos armazenamentos da empresa e em outras entidades legais. Este tipo de pesquisa é conhecido como *pesquisa remota do cliente*.

Para pesquisar globalmente, os funcionários podem selecionar o botão **Resultados de filtragem** na parte inferior da página e selecionar a opção **Pesquisa todos os armazenamentos** , conforme mostra a ilustração que segue. Nesse caso, não são retornados apenas os clientes. Todos os tipos de participantes que fazem parte do catálogo de endereços da sede também são retornados. Esses participantes incluem trabalhadores, fornecedores, contatos e concorrentes.

> [!NOTE]
> Um número mínimo de quatro caracteres deve ser inserido para uma pesquisa remota de cliente para retornar os resultados.

Em uma pesquisa remota de cliente, o ID do cliente não é mostrado para os clientes de outras entidades legais porque nenhum ID de cliente foi criado para essas partes na empresa atual. Porém, se um funcionário abrir a página de detalhes do cliente, o sistema automaticamente gerará um ID de cliente para a parte e também associará os catálogos de endereço do cliente de armazenamento ao cliente. Portanto, o cliente ficará visível em pesquisas locais de armazenamento feitas posteriormente.

![Pesquisa global do cliente](./media/Globalcustomersearch.png "Pesquisa global do cliente")

### <a name="enhancements-to-local-customer-searches"></a>Aprimoramentos em pesquisas locais do cliente

As pesquisas locais do cliente ajudam os funcionários a localizar os clientes rapidamente pelo número de telefone. Os funcionários não precisam digitar nenhum caractere especial que foi adicionado ao número de telefone de um cliente, como espaços, hífens, ou colchetes. Embora os caixas possam armazenar telefones de qualquer formato (por exemplo, podem incluir os colchetes, hifens, símbolos etc.), eles podem, procurar os clientes digitando um número de telefone parcial. Se um caixa incluiu caracteres especiais ao inserir um telefone, os outros caixas podem localizar a conta digitando os números exibidos após os caracteres especiais. Por exemplo, se o número de telefone de um cliente foi inserido como **123-456-7890**, um caixa pode procurar o cliente digitando **123**, **456**, **7890** ou **1234567890**, ou digitando parcialmente alguns dos primeiros números do telefone.
