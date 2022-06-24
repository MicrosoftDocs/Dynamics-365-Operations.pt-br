---
title: Pesquisa de produto e de cliente no ponto de venda (PDV)
description: Este artigo fornece uma visão geral de melhorias feitas à funcionalidade de pesquisa de produto e cliente no Dynamics 365 Commerce.
author: ShalabhjainMSFT
ms.date: 05/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 5f2d8162c810f63dc889a03d33fd111de69783de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858991"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Pesquisa de produto e de cliente no ponto de venda (PDV)

[!include [banner](includes/banner.md)]

O Modern Point of Sale (MPOS) e o Cloud Point of Sale (CPOS) oferecem uma funcionalidade de pesquisa fácil de usar para produtos e clientes. Como a barra de pesquisa está sempre presente na parte superior das janelas MPOS e do CPOS, os funcionários podem localizar produtos e clientes rapidamente.

Os funcionários podem procurar produtos nos sortimentos e nos catálogos que estão associados ao armazenamento atual. Eles também podem pesquisar nos sortimentos e nos catálogos que estão associados a qualquer outro armazenamento na empresa. Portanto, os caixas podem vender e devolver produtos de fora da classificação de armazenamento. Da mesma forma, os funcionários podem procurar clientes que estão associados ao armazenamento atual ou a qualquer loja da empresa. Além disso, os funcionários podem procurar clientes que estão associados a uma empresa diferente na organização pai.

## <a name="product-search"></a>Pesquisa de produtos

Por padrão, as pesquisas de produtos são feitas na classificação de armazenamento. Este tipo de pesquisa é conhecido como *pesquisa local do produto*. No entanto, os funcionários podem alternar facilmente para qualquer catálogo associado ao armazenamento atual, ou podem pesquisar em um armazenamento diferente. Este tipo de pesquisa é conhecido como *pesquisa remota do produto*. Para alterar o catálogo, selecione o botão **Categorias** no lado esquerdo da página. Na parte superior do painel que é exibido, selecione o botão **Alterar catálogo** e, em seguida, selecione um dos catálogos disponíveis para busca. O sistema pesquisará o catálogo de produtos selecionado.

Na página **Alterar catálogo**, os funcionários podem selecionar facilmente qualquer armazenamento ou podem procurar os produtos em todos os armazenamentos.

![Alterar o catálogo.](./media/Changecatalog.png "Mudança de catálogo")

Uma pesquisa local do produto faz a pesquisa dentro das seguintes propriedades do produto:

- Código do produto
- Nome do produto
- descrição
- Dimensões
- Código de barras
- Pesquisar nome

### <a name="additional-local-product-search-capabilities-conventional-sql-full-text-search"></a>Recursos adicionais de pesquisa local do produto (pesquisa de texto completo de SQL convencional) 

- Para pesquisa de várias palavras-chave (isto é, para pesquisas que usam termos de pesquisa) os varejistas podem configurar se os resultados da pesquisa incluem resultados que correspondem a *qualquer* termo de pesquisa ou somente a resultados que correspondem a *todos* os termos da pesquisa. A configuração desta funcionalidade está disponível no perfil da funcionalidade de PDV, em um novo grupo chamado **Pesquisa de produto**. A configuração padrão é **Corresponder qualquer termo de pesquisa**. Esta configuração também é a configuração recomendada. Quando a configuração **Corresponder a qualquer termo da pesquisa** for usada, todos os produtos que correspondam totalmente ou parcialmente um ou mais termos de pesquisa são retornados como resultados. Os resultados são classificados em ordem crescente automaticamente de produtos com a maioria de resultados da palavra-chave (total ou parcial.)

    A configuração **Corresponder todos os termos de pesquisa** retorna apenas os produtos que correspondem a todos os termos da pesquisa (total ou parcial.) Essa configuração é útil quando os nomes de produto são mais longos e os funcionários querem ver somente produtos limitados nos resultados da pesquisa. Porém, esse tipo de pesquisa têm duas limitações:

    - A pesquisa é feita em propriedades de produto individuais. Por exemplo, somente os produtos que têm todas as palavras-chave pesquisadas em pelo menos uma propriedade de produto são retornados.
    - As dimensões não são pesquisadas.
> [!NOTE]
> As configurações a seguir de **Corresponder qualquer termo de pesquisa**/**Corresponder todos os termos de pesquisa** nos perfis de funcionalidade de PDV só são aplicáveis a pesquisas de produtos **locais** (pesquisa de texto completo de SQL convencional). Essa configuração não tem efeito nas experiências de pesquisa habilitadas na nuvem. O novo mecanismo de pesquisa tem seu próprio algoritmo avançado que reforça a relevância da pesquisa para os resultados da pesquisa de produtos. 

- Fornecedores podem configurar a pesquisa de produtos para mostrar sugestões de pesquisa como nomes de produto do tipo de usuário. Uma nova configuração para esta funcionalidade está disponível no perfil da funcionalidade de PDV, em um grupo chamado **Pesquisa de produto**. A configuração é chamada **Mostrar sugestões de pesquisa ao digitar**. Esta funcionalidade pode ajudar funcionários a encontrar rapidamente o produto que eles estão pesquisando, porque eles não precisam digitar o nome completo manualmente.
- O algoritmo de pesquisa do produto agora também procura os termos pesquisados na propriedade **Pesquisar nome** do produto.

![Sugestões de produtos.](./media/Productsuggestions.png "Sugestões de produtos")

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

Para pesquisar globalmente, os funcionários podem selecionar o botão **Resultados de filtragem** na parte inferior da página e selecionar a opção **Pesquisa todos os armazenamentos**, conforme mostra a ilustração que segue. Nesse caso, não são retornados apenas os clientes. Todos os tipos de participantes que fazem parte do catálogo de endereços do headquarters também são retornados. Esses participantes incluem trabalhadores, fornecedores, contatos e concorrentes.

> [!NOTE]
> Um número mínimo de quatro caracteres deve ser inserido para uma pesquisa remota de cliente para retornar os resultados.

O ID do cliente não é mostrado para os clientes consultados de outras entidades legais porque nenhum ID de cliente foi criado para essas partes na empresa atual. Porém, se um funcionário abrir a página de detalhes do cliente, o sistema automaticamente gerará um ID de cliente para a parte e também associará os catálogos de endereço do cliente de armazenamento ao cliente. Portanto, o cliente ficará visível em pesquisas locais de armazenamento feitas posteriormente.

![Pesquisa de cliente global.](./media/Globalcustomersearch.png "Pesquisa de cliente global")

### <a name="additional-local-customer-search-capabilities"></a>Recursos adicionais de pesquisa local de cliente

Quando o usuário pesquisa um número de telefone, o sistema ignora caracteres especiais (como espaços, hífens e colchetes) que podem ter sido adicionados quando o cliente foi criado. Portanto, os caixas não devem se preocupar sobre o formato de telefone durante a pesquisa. Por exemplo, se o número de telefone de um cliente foi inserido como **123-456-7890**, um caixa pode procurar o cliente digitando **1234567890** ou digitando alguns dos primeiros números do telefone.

> [!NOTE]
> Um cliente pode ter vários números de telefone e vários emails. O algoritmo de pesquisa de cliente também pesquisa esses emails e números de telefone secundários, mas a página de resultados de pesquisa de cliente exibe somente o email e o número de telefone principais. Isso pode causar certa confusão, pois os resultados exibidos do cliente não mostram o email ou o número de telefone pesquisado. Em uma futura versão, planejamos aprimorar a tela de resultados de pesquisa de cliente para mostrar essas informações.

A busca tradicional do cliente pode levar muito tempo porque ela faz a pesquisa em vários campos. Em vez disso, os caixas agora podem pesquisar em uma única propriedade de cliente, como nome, endereço de email ou número de telefone. As propriedades que o algoritmo de pesquisa do cliente usa são conhecidas coletivamente como *critérios de pesquisa do cliente*. O sistema administrativo pode configurar facilmente um ou mais critérios como os atalhos que aparecerão no PDV. Como a pesquisa é limitada a um único critério, somente resultados de pesquisa relevantes são exibidos, e o desempenho é muito melhor do que o desempenho de uma pesquisa de clientes padrão. A ilustração a seguir mostra os atalhos pesquisa de cliente no PDV.

![Atalhos de pesquisa de cliente.](./media/SearchShortcutsPOS.png "Atalhos de pesquisa de cliente")

Para definir os critérios de pesquisa como atalhos, o administrador deve abrir a página **Parâmetros de comércio** no Commerce e, na guia **Critérios de pesquisa de PDV**, selecionar os critérios a serem mostrados como atalhos.

![Configurar atalhos de pesquisa.](./media/ConfigureShortcutsAX.png "Configurar atalhos de pesquisa")

> [!NOTE]
> Se você adicionar muitos atalhos, o menu suspenso na barra de pesquisa no PDV se tornará confuso e a experiência de pesquisa do funcionário poderá ser afetada. Recomendamos que você adicione somente o número de atalhos que precisar.

O campo **Ordem de exibição** determina a ordem em que os atalhos são exibidos no PDV. Os critérios que são mostrados são propriedades prontas para uso que o algoritmo de pesquisa do cliente usa para pesquisar clientes. Entretanto, os parceiros podem adicionar propriedades personalizadas como atalhos de pesquisa. Para adicionar propriedades personalizadas como atalhos de pesquisa, o administrador do sistema deve aumentar a enumeração extensível que é usada para os critérios de pesquisa do cliente e, em seguida, marcar as propriedades personalizadas do parceiro como atalhos. Os parceiros são responsáveis por gravar o código para localizar os resultados quando seus atalhos personalizados são usados para pesquisas.

Traduções para atalhos são necessárias se você quiser que os atalhos sejam renderizados no PDV. Se o idioma do seu canal for diferente do idioma padrão do sistema, você deverá definir a tradução para cada atalho no idioma esperado. Você pode definir traduções selecionando **Traduzir** para cada atalho. 

> [!NOTE]
> Uma propriedade personalizada que é adicionada à enumeração não afeta o algoritmo de pesquisa do cliente padrão. Em outras palavras, o algoritmo de pesquisa do cliente não pesquisará a propriedade personalizada. Os usuários podem usar uma propriedade personalizado somente para pesquisas se essa propriedade personalizada for adicionada como um atalho, ou se o algoritmo de pesquisa padrão for substituído.

Os varejistas também podem definir o modo de pesquisa de cliente padrão no PDV para **Pesquisar todas as lojas**. Esta configuração pode ser útil em cenários em que os clientes criados fora do PDV podem ser pesquisados imediatamente (por exemplo, mesmo antes do trabalho de distribuição ser executado.) Para isso, o varejista deve ativar a opção **Modo de pesquisa de cliente padrão** no perfil da funcionalidade PDV. Depois de definida como **Sim**, cada tentativa de pesquisa de cliente executará uma chamada em tempo real para o headquarters.

Para ajudar a evitar problemas inesperados de desempenho, essa configuração está oculta por trás do sinalizador de liberação de versões de pré-lançamento denominada **CUSTOMERSEARCH_ENABLE_DEFAULTSEARCH_FLIGHTING**. Assim, para mostrar a configuração de **Modo de pesquisa de cliente padrão** na interface de usuário, o varejista deve criar um tíquete de suporte para o teste de aceitação de usuário (UAT) e ambientes de produção. Depois do tíquete ser recebido, a equipe da engenharia trabalhará com o varejista para garantir que ele faça testes nos ambientes de não produção para avaliar o desempenho e a implementação de otimizações necessárias.

## <a name="cloud-powered-customer-search"></a>Pesquisa do cliente habilitada para a nuvem

A demonstração pública do recurso de pesquisa do cliente usando o serviço de Pesquisa Cognitiva do Azure foi lançada como parte da versão 10.0.18 do Commerce. Além das melhorias de desempenho, os usuários do serviço também se beneficiam de recursos avançados de refinamento e relevância. As melhorias de desempenho são evidentes principalmente quando o recurso de pesquisa global ("Pesquisar todas as lojas") do PDV é usado. Isso ocorre porque os resultados da pesquisa são buscados no índice de pesquisa do Azure, e não consultados nos dados do Commerce headquarters. 

### <a name="enable-the-cloud-powered-search-feature"></a>Habilitar o recurso de pesquisa habilitada para a nuvem

> [!NOTE]
> É necessário que tanto o Commerce headquarters quanto a Commerce Scale Unit sejam atualizados para a versão 10.0.18. Não é necessário atualizar o PDV.

Para habilitar o recurso de recurso de pesquisa habilitada para a nuvem no Commerce headquarters, siga estas etapas.

1. Acesse **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recursos**.
1. Localize e selecione o recurso **Pesquisa do cliente habilitada para a nuvem (visualização)** e, em seguida, selecione **Habilitar agora**.
1. Acesse **Varejo e Comércio > Configuração do headquarters > Agendador do Commerce > Inicializar agendador do Commerce** e selecione **OK** para exibir a nova tarefa **1010_CustomerSearch** no formulário **Agenda de distribuição**.
1. Acesse **Varejo e Comércio > TI de Varejo e Comércio > Agenda de distribuição**.
1. Execute o trabalho **1010_CustomerSearch**. Este trabalho publica a data para o índice de pesquisa do Azure. Quando a publicação do índice for concluída, o status do trabalho será definido como **Aplicado**.
1. Depois que o status do trabalho **1010_CustomerSearch** for definido como **Aplicado**, execute o trabalho **1110 - Configuração global** para atualizar os canais de PDV do recurso mais recente habilitado no **Gerenciamento de recursos**.
1. Em seguida, execute o trabalho **1010_CustomerSearch** em intervalos regulares para enviar as atualizações do cliente para o índice de pesquisa.

> [!NOTE]
> Para a publicação do índice inicial, o trabalho **1010_CustomerSearch** pode levar algumas horas para ser concluído, pois ele enviará todos os registros do cliente para o índice de pesquisa do Azure. As atualizações subsequentes devem demorar alguns minutos. No período de tempo em que o recurso de pesquisa habilitada para a nuvem é habilitado, mas a publicação do índice ainda não foi concluída, a pesquisa do cliente a partir do PDV será padronizada para a pesquisa baseada em SQL existente. Isso garante que não haja interrupções nas operações da loja.

### <a name="functional-differences-from-the-existing-search"></a>Diferenças funcionais da pesquisa existente

A lista a seguir mostra como a funcionalidade de pesquisa habilitada para a nuvem é diferente da funcionalidade de pesquisa existente. 

- Os clientes criados e editados no Commerce headquarters são enviados para o índice de pesquisa do Azure quando o trabalho **1010_CustomerSearch** é executado. Essas atualizações levam, no mínimo, 15 a 20 minutos para atualizar o índice. Os usuários do PDV poderão procurar novos clientes (ou pesquisar com base nas informações atualizadas) de cerca de 15 a 20 minutos depois que as atualizações ocorrerem no Commerce headquarters. Se o processo comercial exigir que os clientes criados no Commerce headquarters sejam pesquisados imediatamente no PDV, isso pode não ser o serviço certo para você.
- Novos clientes criados no PDV são enviados para o índice de pesquisa do Azure da Commerce Scale Unit e são pesquisados imediatamente em qualquer loja. No entanto, se o recurso de criação de cliente assíncrono estiver ativado, os novos registros de clientes não serão publicados no índice de pesquisa do Azure do Commerce Scale Unit e não poderão ser pesquisados do PDV até que as informações do cliente sejam sincronizadas com o Commerce headquarters e as IDs do cliente sejam geradas para clientes assíncronos. O trabalho **1010_CustomerSearch** será então capaz de enviar os registros de cliente assíncrono para o índice de pesquisa do Azure. Em média, haverá cerca de 30 minutos para que clientes assíncronos recém-criados possam ser pesquisados no PDV. Essa estimativa pressupõe que os trabalhos **1010_CustomerSearch**, **P-Job** e **Sincronizar clientes e parceiros comerciais do modo assíncrono** estão programados para serem executados a cada 15 minutos.
- A pesquisa habilitada para a nuvem também pesquisa os emails secundários e os números de telefone dos clientes, mas os resultados de pesquisa do cliente exibem somente o número de telefone principal e o endereço de email principal dos clientes. À primeira vista, pode parecer que resultados de pesquisa irrelevantes foram devolvidos, mas verificar o número de telefone e o email secundário de um cliente nos resultados da pesquisa podem ajudar a verificar se a palavra-chave pesquisada resultou em uma correspondência do cliente. Para evitar essa confusão, há planos de melhorar a página de resultados da pesquisa para que os usuários saibam por que um resultado de pesquisa foi devolvido.
- A necessidade de pesquisa usando pelo menos 4 caracteres em uma pesquisa global ("Pesquisar todas as lojas") não é aplicável a este serviço.

> [!NOTE]
> O recurso de pesquisa de cliente usando o serviço de pesquisa cognitiva do Azure está disponível em regiões limitadas para visualização. O recurso de pesquisa do cliente *não está* disponível nas seguintes regiões:
> - Brasil
> - Índia

[!INCLUDE[footer-include](../includes/footer-banner.md)]
