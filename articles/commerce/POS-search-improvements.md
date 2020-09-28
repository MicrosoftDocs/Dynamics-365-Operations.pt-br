---
title: Pesquisa de produto e de cliente no ponto de venda (PDV)
description: Este tópico fornece uma visão geral de melhorias feitas à funcionalidade de pesquisa de produto e cliente no Dynamics 365 Commerce.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 07/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 10c843670a280c86790185c8a39cb2943e2838f9
ms.sourcegitcommit: 5472005274f2f94fba82dda90de128f39d8b8390
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759926"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Pesquisa de produto e de cliente no ponto de venda (PDV)

[!include [banner](includes/banner.md)]

O Modern Point of Sale (MPOS) e o Cloud Point of Sale (CPOS) oferecem uma funcionalidade de pesquisa fácil de usar para produtos e clientes. Como a barra de pesquisa está sempre presente na parte superior das janelas MPOS e do CPOS, os funcionários podem localizar produtos e clientes rapidamente.

Os funcionários podem procurar produtos nos sortimentos e nos catálogos que estão associados ao armazenamento atual. Eles também podem pesquisar nos sortimentos e nos catálogos que estão associados a qualquer outro armazenamento na empresa. Portanto, os caixas podem vender e devolver produtos de fora da classificação de armazenamento. Da mesma forma, os funcionários podem procurar clientes que estão associados ao armazenamento atual ou a qualquer loja da empresa. Além disso, os funcionários podem procurar clientes que estão associados a uma empresa diferente na organização pai.

## <a name="product-search"></a>Pesquisa de produtos

Por padrão, as pesquisas de produtos são feitas na classificação de armazenamento. Este tipo de pesquisa é conhecido como *pesquisa local do produto*. No entanto, os funcionários podem alternar facilmente para qualquer catálogo associado ao armazenamento atual, ou podem pesquisar em um armazenamento diferente. Este tipo de pesquisa é conhecido como *pesquisa remota do produto*. Para alterar o catálogo, selecione o botão **Categorias** no lado esquerdo da página. Na parte superior do painel que é exibido, selecione o botão **Alterar catálogo** e, em seguida, selecione um dos catálogos disponíveis para busca. O sistema pesquisará o catálogo de produtos selecionado.

Na página **Alterar catálogo**, os funcionários podem selecionar facilmente qualquer armazenamento ou podem procurar os produtos em todos os armazenamentos.

![Alterar o catálogo](./media/Changecatalog.png "Mudança de catálogo")

Uma pesquisa local do produto faz a pesquisa dentro das seguintes propriedades do produto:

- Número do produto
- Nome do produto
- descrição
- Dimensões
- Código de barras
- Nome de pesquisa

### <a name="enhancements-to-local-product-searches"></a>Aprimoramentos em pesquisas locais do produto

A experiência de pesquisas locais de produto agora é feita de forma mais amigável. Os seguintes aperfeiçoamentos foram feitos:

- Os menus suspensos de produto e cliente foram adicionados à barra de pesquisa, dessa forma, esses funcionários podem selecionar **Produto** ou **Cliente** antes de fazerem a pesquisa. Por padrão, **Produto** é selecionado, conforme mostra a ilustração que segue.
- Para pesquisa de várias palavras-chave (isto é, para pesquisas que usam termos de pesquisa) os varejistas podem configurar se os resultados da pesquisa incluem resultados que correspondem a *qualquer* termo de pesquisa ou somente a resultados que correspondem a *todos* os termos da pesquisa. A configuração desta funcionalidade está disponível no perfil da funcionalidade de PDV, em um novo grupo chamado **Pesquisa de produto**. A configuração padrão é **Corresponder qualquer termo de pesquisa**. Esta configuração também é a configuração recomendada. Quando a configuração **Corresponder a qualquer termo da pesquisa** for usada, todos os produtos que correspondam totalmente ou parcialmente um ou mais termos de pesquisa são retornados como resultados. Os resultados são classificados em ordem crescente automaticamente de produtos com a maioria de resultados da palavra-chave (total ou parcial.)

    A configuração **Corresponder todos os termos de pesquisa** retorna apenas os produtos que correspondem a todos os termos da pesquisa (total ou parcial.) Essa configuração é útil quando os nomes de produto são mais longos e os funcionários querem ver somente produtos limitados nos resultados da pesquisa. Porém, esse tipo de pesquisa têm duas limitações:

    - A pesquisa é feita em propriedades de produto individuais. Por exemplo, somente os produtos que têm todas as palavras-chave pesquisadas em pelo menos uma propriedade de produto são retornados.
    - As dimensões não são pesquisadas.

- Fornecedores podem agora configurar a pesquisa de produtos para mostrar sugestões de pesquisa como nomes de produto do tipo de usuário. Uma nova configuração para esta funcionalidade está disponível no perfil da funcionalidade de PDV, em um grupo chamado **Pesquisa de produto**. A configuração é chamada **Mostrar sugestões de pesquisa ao digitar**. Esta funcionalidade pode ajudar funcionários a encontrar rapidamente o produto que eles estão pesquisando, porque eles não precisam digitar o nome completo manualmente.
- O algoritmo de pesquisa do produto agora também procura os termos pesquisados na propriedade **Pesquisar nome** do produto.

![Sugestões de produtos](./media/Productsuggestions.png "Sugestões de produtos")

## <a name="customer-search"></a>Pesquisa de Cliente

A pesquisa de cliente será usada para localizar clientes para várias finalidades. Por exemplo, os caixas podem querer ver uma lista de desejos do cliente ou o histórico de vendas, ou adicionar o cliente a uma transação. O algoritmo de pesquisa corresponde às condições de pesquisa em relação aos valores que estão apresentados nas seguintes propriedades de clientes:

- Nome
- Endereço de email
- Número de telefone
- Número do cartão de fidelidade
- Endereço
- Número da conta

Entre essas propriedades, o nome fornece a maior flexibilidade para pesquisas de várias palavras-chave, pois o algoritmo retorna todos os clientes que correspondem às palavras-chave pesquisadas. Os clientes que correspondem à maioria das palavras-chave aparecem na parte superior dos resultados. Esse comportamento ajuda os caixas em situações em que eles pesquisam digitando o nome completo, mas o sobrenome e o nome foram trocados durante a entrada de dados inicial. Entretanto, por razões de desempenho, todas as outras propriedades preservam a ordem das palavras-chave de pesquisa. Portanto, se a ordem das palavras-chave de pesquisa não coincidirem com a ordem em que os dados são armazenados, nenhum resultado será retornado.

Por padrão, uma pesquisa de cliente é feita em catálogos de endereços do cliente associados ao armazenamento. Este tipo de pesquisa é conhecido como *pesquisa local do cliente*. Porém, os funcionários também podem pesquisar os clientes globalmente. Em outras palavras, eles podem pesquisar nos armazenamentos da empresa e em outras entidades legais. Este tipo de pesquisa é conhecido como *pesquisa remota do cliente*.

Para pesquisar globalmente, os funcionários podem selecionar o botão **Resultados de filtragem** na parte inferior da página e selecionar a opção **Pesquisa todos os armazenamentos** , conforme mostra a ilustração que segue. Nesse caso, não são retornados apenas os clientes. Todos os tipos de participantes que fazem parte do catálogo de endereços da sede também são retornados. Esses participantes incluem trabalhadores, fornecedores, contatos e concorrentes.

> [!NOTE]
> Um número mínimo de quatro caracteres deve ser inserido para uma pesquisa remota de cliente para retornar os resultados.

Em uma pesquisa remota de cliente, o ID do cliente não é mostrado para os clientes de outras entidades legais porque nenhum ID de cliente foi criado para essas partes na empresa atual. Porém, se um funcionário abrir a página de detalhes do cliente, o sistema automaticamente gerará um ID de cliente para a parte e também associará os catálogos de endereço do cliente de armazenamento ao cliente. Portanto, o cliente ficará visível em pesquisas locais de armazenamento feitas posteriormente.

![Pesquisa de cliente global](./media/Globalcustomersearch.png "Pesquisa de cliente global")

### <a name="enhancements-to-local-customer-search"></a>Aprimoramentos em pesquisa local do cliente

As pesquisas baseadas no número do telefone foram simplificadas. Essas pesquisas ignoram agora caracteres especiais, como espaços, hífens e colchetes, que podem ter sido adicionados quando o cliente for criado. Portanto, os caixas não devem se preocupar sobre o formato de telefone durante a pesquisa. Por exemplo, se o número de telefone de um cliente foi inserido como **123-456-7890**, um caixa pode procurar o cliente digitando **1234567890** ou digitando alguns dos primeiros números do telefone.

> [!NOTE]
> Um cliente pode ter vários números de telefone e vários emails. O algoritmo de pesquisa de cliente também pesquisa esses emails e números de telefone secundários, mas a página de resultados de pesquisa de cliente exibe somente o email e o número de telefone principais. Isso pode causar certa confusão, pois os resultados exibidos do cliente não mostram o email ou o número de telefone pesquisado. Em uma futura versão, planejamos aprimorar a tela de resultados de pesquisa de cliente para mostrar essas informações.

A busca tradicional do cliente pode levar muito tempo porque ela faz a pesquisa em vários campos. Em vez disso, os caixas agora podem pesquisar em uma única propriedade de cliente, como nome, endereço de email ou número de telefone. As propriedades que o algoritmo de pesquisa do cliente usa são conhecidas coletivamente como *critérios de pesquisa do cliente*. O sistema administrativo pode configurar facilmente um ou mais critérios como os atalhos que aparecerão no PDV. Como a pesquisa é limitada a um único critério, somente resultados de pesquisa relevantes são exibidos, e o desempenho é muito melhor do que o desempenho de uma pesquisa de clientes padrão. A ilustração a seguir mostra os atalhos pesquisa de cliente no PDV.

![Atalhos de pesquisa de cliente](./media/SearchShortcutsPOS.png "Atalhos de pesquisa de cliente")

Para definir os critérios de pesquisa como atalhos, o administrador deve abrir a página **Parâmetros de comércio** no Commerce e, na guia **Critérios de pesquisa de PDV**, selecionar os critérios a serem mostrados como atalhos.

![Configurar atalhos de pesquisa](./media/ConfigureShortcutsAX.png "Configurar atalhos de pesquisa")

> [!NOTE]
> Se você adicionar muitos atalhos, o menu suspenso na barra de pesquisa no PDV se tornará confuso e a experiência de pesquisa do funcionário poderá ser afetada. Recomendamos que você adicione somente o número de atalhos que precisar.

O campo **Ordem de exibição** determina a ordem em que os atalhos são exibidos no PDV. Os critérios que são mostrados são propriedades prontas para uso que o algoritmo de pesquisa do cliente usa para pesquisar clientes. Entretanto, os parceiros podem adicionar propriedades personalizadas como atalhos de pesquisa. Para adicionar propriedades personalizadas como atalhos de pesquisa, o administrador do sistema deve aumentar a enumeração extensível que é usada para os critérios de pesquisa do cliente e, em seguida, marcar as propriedades personalizadas do parceiro como atalhos. Os parceiros são responsáveis por gravar o código para localizar os resultados quando seus atalhos personalizados são usados para pesquisas.

> [!NOTE]
> Uma propriedade personalizada que é adicionada à enumeração não afeta o algoritmo de pesquisa do cliente padrão. Em outras palavras, o algoritmo de pesquisa do cliente não pesquisará a propriedade personalizada. Os usuários podem usar uma propriedade personalizado somente para pesquisas se essa propriedade personalizada for adicionada como um atalho, ou se o algoritmo de pesquisa padrão for substituído.

Na próxima versão do Commerce, os varejistas poderão definir o modo de pesquisa de cliente padrão no PDV como **Pesquisar todas as lojas**. Esta configuração pode ser útil em cenários em que os clientes criados fora do PDV podem ser pesquisados imediatamente (por exemplo, mesmo antes do trabalho de distribuição ser executado.) Uma nova opção **Modo de pesquisa de cliente padrão** estará disponível no perfil de funcionalidade do PDV. Defina-a como **Ativo** para definir o modo de pesquisa padrão como **Pesquisar todas as lojas**. Cada tentativa de pesquisa de cliente executará uma chamada em tempo real para a sede.

Para ajudar a evitar problemas inesperados de desempenho, essa configuração está oculta por trás do sinalizador de liberação de versões de pré-lançamento denominada **CUSTOMERSEARCH_ENABLE_DEFAULTSEARCH_FLIGHTING**. Assim, para mostrar a configuração de **Modo de pesquisa de cliente padrão** na interface de usuário, o varejista deve criar um tíquete de suporte para o teste de aceitação de usuário (UAT) e ambientes de produção. Depois do tíquete ser recebido, a equipe da engenharia trabalhará com o varejista para garantir que ele faça testes nos ambientes de não produção para avaliar o desempenho e a implementação de otimizações necessárias.

