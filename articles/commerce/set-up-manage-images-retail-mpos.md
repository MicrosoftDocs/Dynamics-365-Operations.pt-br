---
title: Configurar e gerenciar imagens para Modern POS (MPOS)
description: Este artigo explica as etapas envolvidas na configuração e no gerenciamento de imagens para as diversas entidades que aparecem no Modern POS (MPOS).
author: athinesh99
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailChannelProfile, RetailMediaGallery, RetailImages,
audience: Application User
ms.reviewer: josaw
ms.custom: 52851
ms.assetid: 5c21385e-64e0-4091-98fa-6a662eb33010
ms.search.region: global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 31f325d2614d0a01192a0157ee0e89514bc51caa
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985752"
---
# <a name="set-up-and-manage-images-for-modern-pos-mpos"></a>Configurar e gerenciar imagens para Modern POS (MPOS)

[!include [banner](includes/banner.md)]

Este artigo explica as etapas envolvidas na configuração e no gerenciamento de imagens para as diversas entidades que aparecem no Modern POS (MPOS).

## <a name="setting-up-the-media-base-url-and-defining-media-templates-to-configure-the-format-for-image-urls"></a>Configuração da URL de base da mídia e definição de modelos de mídia para configurar o formato de URLs de imagem

As imagens que aparecem no Modern POS (MPOS) devem ser hospedadas externamente, fora do Commerce. Em geral, elas são hospedadas em um sistema de gerenciamento de conteúdo, em uma rede de entrega de conteúdo (CDN) ou em um servidor de mídia. O MPOS pesquisa e exibe as imagens das entidades apropriadas, como produtos e catálogos, acessando a URL de destino. Para obter essas imagens hospedadas externamente, o MPOS requer o formato de URL correto para as imagens. Você pode configurar o formato de URL exigido para as imagens configurando o valor **URL base da mídia** no perfil do canal e usando a funcionalidade **Definir modelo de mídia** para cada entidade. Também é possível substituir o formato padrão da URL para um subconjunto de entidades usando a funcionalidade **Editar no Excel**.

> [!IMPORTANT]
> Na versão atual do Commerce, você não pode mais configurar o formato da URL usando o atributo XML **Imagem** para MPOS no grupo de atributos **Padrão** para entidades. Se você estiver familiarizado com o Microsoft Dynamics AX 2012 R3 e estiver usando a versão atual do Commerce, procure sempre usar a nova funcionalidade **Definir modelo de mídia** para configurar imagens. Não use nem modifique o atributo **Imagem** no grupo de atributos **Padrão** para qualquer entidade, incluindo produtos. As alterações feitas diretamente no grupo de atributos **Padrão** para imagens não serão refletidas. Esta opção será desabilitada em uma versão futura.

Nos procedimentos a seguir, as imagens são configuradas para a entidade do catálogo como um exemplo. Esses procedimentos ajudarão a garantir que o caminho correto de destino da imagem seja definido implicitamente para todas as imagens de catálogo que usam um caminho comum. Por exemplo, se você configurou um servidor de mídia ou um CDN externamente, e deseja que as imagens apareçam no MPOS para um armazenamento, a funcionalidade **Definir modelo de mídia** ajuda a definir o caminho em que o MPOS pode pesquisar e recuperar as imagens.

> [!NOTE]
> Neste exemplo de dados de demonstração, o servidor de mídia é implantado no Commerce Scale Unit. No entanto, ele pode estar em qualquer lugar fora do Commerce.

### <a name="set-up-the-media-base-url-for-a-channel"></a>Configurar a URL base da mídia para um canal

1. Abra o portal do Headquarters do Commerce.
2. Clique em **Retail e Commerce** &gt; **Configuração de canal** &gt; **Perfis de canal**.

    [![Navegação](./media/channel-profile1.png)](./media/channel-profile1.png)

3. No perfil do canal que a loja usa para o MPOS, atualize o campo **URL base da mídia** com a URL base do servidor de mídia ou CDN. A URL base é a primeira parte da URL que é compartilhada por todas as pastas de imagem de entidades diferentes.

    [![Página Perfis de canal](./media/channel-profile2.png)](./media/channel-profile2.png)

### <a name="define-the-media-template-for-an-entity"></a>Definir o modelo da mídia para uma entidade

1. Clique em **Retail e Commerce** &gt; **Gerenciamento de catálogo** &gt; **Imagens de catálogo**.
2. Na página **Imagens de catálogo**, no Painel de Ação, clique em **Definir modelo da mídia**. Na caixa de diálogo **Definir modelo da mídia**, no campo **Entidade**, selecione **Catálogo** por padrão.
3. Na Guia Rápida **Caminho da mídia**, insira o caminho restante do local da imagem. O caminho da mídia dá suporte a **LanguageID** como uma variável. Por exemplo, para os dados de demonstração, você pode criar uma pasta **Catálogos** para todas as imagens de catálogo na URL base da mídia para o seu servidor de mídia (`https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer`). Você pode ter uma pasta para cada idioma, como en-US ou fr-FR, e copiar as imagens apropriados em cada pasta. Se você não tiver imagens diferentes para vários idiomas, poderá omitir a variável **LanguageID** da estrutura da pasta e apontar diretamente para a pasta Catálogos que contém as imagens do catálogo.

    > [!NOTE]
    > A versão atual do Commerce oferece suporte ao token **{LanguageId}** para as entidades Catálogo, Produto e Categoria. (O token **{LanguageID}** não tem suporte para as entidades Cliente e Trabalhador, de acordo com o padrão existente em vigor desde o Microsoft Dynamics AX 6.x).

4. Para imagens, o formato do nome de arquivo é codificado no nome do catálogo e não pode ser alterado. Então, renomeie as imagens para que tenham nomes apropriados do catálogo, ajudando a garantir que o MPOS trate-as corretamente.
5. No campo **Extensão do Arquivo**, selecione a extensão de nome de arquivo esperada, dependendo do tipo de imagens que você tem. Por exemplo, para os dados de demonstração, as imagens de catálogo são definidas para a extensão .jpg. (Os arquivos de imagem também são renomeados para que tenham nomes de catálogo.)
6. Clique em **OK**.
7. Para validar que o modelo de mídia para imagens foi salvo corretamente, na página **Imagens de catálogo**, clique novamente em **Definir modelo de mídia**. Para validar o modelo sem fechar a caixa de diálogo **Definir modelo de mídia**, você pode usar a Guia Rápida **Gerenciar URLs de Imagens para o Excel**. Verifique a aparência da URL de imagem, e se a URL está de acordo com o padrão de modelo citado anteriormente. A caixa de diálogo **Definir modelo de mídia** definiu o caminho da imagem implicitamente para todas as imagens de catálogo que usam este caminho comum da URL. Este caminho da URL se aplica a todas as imagens de catálogo, a menos que elas sejam substituídas. A primeira parte do caminho da imagem é obtida da URL base da mídia que foi definida no perfil do canal. A parte restante do caminho é obtida do caminho que foi definido no modelo de mídia. As duas partes são concatenadas para fornecer a URL completa do local da imagem. Por exemplo, um catálogo nos dados de demonstração é chamado de Fabrikam Base Catalog. Assim, o nome da imagem deve ser Fabrikam Base Catalog.jpg para que use o nome do catálogo e a extensão de nome de arquivo .jpg que é configurada no modelo. Nesse caso, após a concatenação, a URL será `https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer/Catalogs/en-US/Fabrikam Base Catalog.jpg`.
8. Execute os trabalho de sincronização para enviar por push o novo modelo ao banco de dados do canal, de forma que o MPOS possa usar o modelo para acessar as imagens.
9. Para atualizar o modelo de mídia para imagens de catálogo no canal, execute o **Trabalho do catálogo 1150** em **TI do Retail e Commerce** &gt; **Agenda de distribuição**.

    [![Caixa de diálogo Definir modelo de mídia](./media/catalog1.png)](./media/catalog1.png)

## <a name="previewing-an-image-from-the-entity-level"></a>Visualização de uma imagem em nível de entidade

1. Na página do item da entidade na matriz, você pode visualizar a imagem que usa a URL de imagem derivada do modelo da mídia. Neste exemplo, vá para o catálogo apropriado e, depois, no Painel de Ação, clique em **Mídia** &gt; **Imagens**. Use a lista suspensa para selecionar diferentes lojas que possam ter perfis de canal diferentes.
2. Para editar ou remover o modelo de mídia implícito, retorne à caixa de diálogo **Definir modelo de mídia** da página **Imagens do catálogo**.
3. Você pode usar os botões **Adicionar** e **Remover** para alterar manualmente o caminho que se baseia no modelo implícito e é usado para uma imagem específica. Para obter mais informações, consulte a seção [Substituição do modelo da mídia para itens da entidade](#overwriting-the-media-template-for-entity-items), mais adiante neste artigo.
4. Ao concluir a visualização de uma imagem e fazer as alterações necessárias, inicie a instância do MPOS para a loja adequada, e verifique se as imagens de catálogo são exibidas.

    [![Caixa de diálogo Imagens](./media/catalog4.png)](./media/catalog4.png)

> [!NOTE]
> Você pode usar o mesmo procedimento para todas as cinco entidades com suporte: Trabalhador, Cliente, Catálogo, Categoria e Produtos. “Produtos do Catálogo” (produtos que são definidos em nível de catálogo) e “Produtos do Canal” (produtos que são definidos em nível de canal) usam o modelo da mídia que é definido para a entidade Produtos. No modelo de mídia Produtos, você pode selecionar o número de imagens do produto para mostrar por produto. Também pode definir a imagem padrão para um produto específico. Dessa forma, você pode evitar imagens em branco no MPOS, e ajudar a controlar a imagem que é usada como a imagem padrão para um item de produto. No exemplo a seguir, cada produto tem cinco imagens, e a primeira imagem é definida como a imagem padrão. As variantes de produtos são tratadas da mesma forma que os produtos mestre. O nome de arquivo do arquivo de imagem deve se basear no número do produto. Há também caracteres de escape enquanto o nome de arquivo é gerado. Portanto, convém verificar o nome do arquivo usando a seção **Gerenciar URLs de Imagem para o Excel**. Consulte a seção [Substituir usando Editar no Excel](#overwrite-by-using-edit-in-excel) posteriormente neste artigo.

## <a name="synchronization-jobs-to-send-a-media-template-to-the-channel-side"></a>Trabalhos de sincronização para enviar um modelo de mídia ao lado do canal

Para as cinco entidades com suporte (Trabalhador, Cliente, Catálogo, Categoria e Produtos), sempre que você atualizar a caixa de diálogo **Definir modelo de mídia** para configurar uma imagem, verifique se executou o trabalho de catálogo (1150) de **TI de Retail e Commerce** &gt; **Agenda de distribuição**. Esse trabalho permite que o modelo de mídia atualizado seja sincronizado para o canal e usado pelo MPOS. Executar o trabalho do catálogo (1150) após fazer uma das seguintes alterações:

- Você atualiza o modelo de mídia de imagem do catálogo de **Imagens do catálogo** &gt; **Definir modelo de mídia**.
- Você atualiza o modelo de mídia de imagem do funcionário de **Imagens do funcionário** &gt; **Definir modelo de mídia**.
- Você atualiza o modelo de mídia de imagem do cliente de **Imagem do cliente** &gt; **Definir modelo de mídia**.
- Você atualiza o modelo de mídia de imagem do produto de **Imagens do produto** &gt; **Definir modelo de mídia**.
- Você atualiza o modelo de mídia de imagem da categoria de **Imagens da categoria** &gt; **Definir modelo de mídia**. Você também deve publicar o canal.

## <a name="overwriting-the-media-template-for-entity-items"></a>Substituição do modelo de mídia para itens da entidade

Como vimos na seção anterior, o modelo da mídia para determinada entidade dá suporte apenas a um caminho comum. Este campo se baseia na URL base da mídia que é configurada e no caminho da mídia que é definido. Mas, em muitos casos, um varejista quer usar imagens de fontes diferentes para um subconjunto de itens em uma entidade. Por exemplo, uma loja usa o servidor de mídia auto-hospedada para um conjunto de imagens do catálogo, mas usa URLs do CDN para outro conjunto. Para substituir as URLs de imagem que se baseiam em um modelo da mídia para imagens da entidade em nível de entidade, você pode usar a funcionalidade Editar no Excel e Edição manual da página **Visualização**.

### <a name="overwrite-by-using-edit-in-excel"></a>Substituir usando Editar no Excel

1. Clique em **Retail e Commerce** &gt; **Gerenciamento de catálogo** &gt; **Imagens de catálogo**.
2. Na página **Imagens de catálogo**, clique em **Definir modelo da mídia**. Na caixa de diálogo **Definir modelo da mídia**, no campo **Entidade**, selecione **Catálogo**.
3. Na Guia Rápida **Caminho da mídia**, observe o local da imagem.
4. Na Guia Rápida **Gerenciar URLs de Imagem para o Excel**, clique em **Gerar**.

    > [!IMPORTANT]
    > Sempre que o modelo de mídia for alterado, clique em **Gerar** para poder usar a funcionalidade Editar no Excel.

    Agora você tem uma visualização das URLs de imagem que foram geradas com base no último modelo de mídia salvo.

    [![Guia Rápida Gerenciar URLs de Imagem para o Excel após Gerar ser selecionado](./media/excel2.png)](./media/excel2.png)

    > [!NOTE]
    > As URLs que são geradas para o Excel usam o caminho e as convenções do modelo da mídia que é definido. Essas convenções incluem as convenções para nomes de arquivo. A expectativa é que você configure as imagens físicas fora do Commerce, e que as imagens possam ser recuperadas das URLs que derivam do modelo da mídia definido antes. Você pode substituir essas URLs derivadas usando a funcionalidade Editar no Excel.

5. Clique em **Editar no Excel**.
6. Depois que a planilha do Microsoft Excel for aberta, clique em **Habilitar edição** quando for solicitado.
7. Quando for solicitado, clique em **Confiar neste suplemento** no painel direito, e aguarde até o suplemento concluir a instalação.

    [![Confiar neste suplemento](./media/excel4.jpg)](./media/excel4.jpg)

8. Se você for solicitado a entrar, insira as credenciais usadas para entrar na matriz.

    [![Prompt de entrada](./media/excel5.png)](./media/excel5.png)

9. Após entrar, você verá a lista de URLs de imagem para as várias entradas de catálogo.
10. Você edita, adiciona e remove as URLs de imagem para vários itens da entidade.
11. Para todas as entidades, exceto Produtos, você pode substituir as URLs da imagem. Modifique a URL de imagem existente para que ela use a nova URL de destino da imagem, e atualize o nome do arquivo com o novo nome de arquivo para o arquivo de imagem. O nome de arquivo deve ser exclusivo para ajudar a garantir que o registro seja exclusivo.

    [![Substituir as URLs de imagem no Excel](./media/excel6.jpg)](./media/excel6.jpg)

    > [!NOTE]
    > Quando você substitui URLs de imagem para entidades Produtos usando a funcionalidade Editar no Excel ou a página do item da entidade, o MPOS sempre mostra todas as URLs de imagem do modelo da mídia, junto com as URLs de imagem substituídas.

12. Ao terminar de fazer as alterações, clique em **Publicar no Excel** para criar uma nova entrada de associação explícita.
13. Retorne à matriz e clique em **OK**.
14. Execute os trabalhos de sincronização apropriados para a entidade, e verifique a visualização na página de entidade ou no MPOS.

#### <a name="creating-new-records"></a>Criação de novos registros

Você pode criar novos registros no Excel. Contudo, verifique se forneceu as informações corretas. Por exemplo, para criar uma nova entrada para um catálogo, verifique se a ID do catálogo e o nome do catálogo estão corretos, e também forneça um nome de arquivo exclusivo. O nome de arquivo exclusivo é muito importante, pois a exclusividade de registros no Excel é validada durante a publicação. Primeiro, copie os detalhes do catálogo para o qual você deseja criar um novo registro, e copie o registro. Você precisa atualizar o nome do arquivo e a URL, pois as demais informações serão as mesmas. Para criar novos registros de itens da entidade Produto, use o mesmo procedimento básico. Na planilha do Excel, copie um registro existente do produto para o qual você deseja criar um novo registro. Depois, substitua a URL e o nome de arquivo da imagem. Verifique se o nome do arquivo é exclusivo.

#### <a name="deleting-an-existing-record"></a>Exclusão de um registro existente

Somente os registros de URL de imagem substituídos podem ser excluídos. Depois que uma imagem é excluída e a sincronização é concluída, a imagem não aparece mais na página **Visualização** ou no MPOS. Os registros da URL de imagem que derivam do modelo de mídia não podem ser excluídos, pois esses registros sempre derivam do modelo de mídia.

### <a name="overwrite-from-the-entity-level-preview-page"></a>Substituição da página Visualização em nível de entidade

Para todas as entidades, exceto Produtos, você pode substituir a URL de imagem para determinado item de entidade em nível de item de entidade na página **Visualização**. Para Produtos, você pode usar a página de entidade "Produtos do Catálogo". Este exemplo mostra como substituir uma imagem do catálogo.

1. Clique em **Catálogos** &gt; **Mídia** &gt; **Imagens**, e selecione a imagem do catálogo a ser atualizada.
2. Clique em **Adicionar** e insira a URL de imagem para substituir a URL do modelo da mídia.
3. Se você deseja que esta imagem apareça no MPOS do catálogo, defina-a como a imagem padrão.
4. Clique em **OK**. A URL de imagem é atualizada para esta imagem do catálogo e uma exibição é mostrada.

    [![URL atualizada na caixa de diálogo Nova imagem](./media/preview3.png)](./media/preview3.png)

5. Também é possível verificar a visualização de imagem para todas as URLs de imagem substituídas na página da galeria **Imagens de catálogo**.

    [![Página da galeria Imagens de catálogo](./media/preview-4.png)](./media/preview-4.png)

> [!NOTE]
> No momento, a galeria não mostra visualizações de imagem para URLs de imagem do modelo da mídia. Para as entidades Catálogo, Trabalhador, Cliente e Categoria, se o usuário fornece explicitamente uma URL através desta página, é recomendável indicar a imagem que é padrão, pois os clientes do Commerce Scale Unit mostram apenas uma imagem por Catálogo, Cliente, Trabalhador e Categoria. Se o usuário não especifica uma imagem padrão, o sistema determina a imagem padrão e a envia ao chamador de serviço do Commerce (MPOS ou comércio eletrônico).

### <a name="overwrite-the-image-url-for-catalog-product-images-from-the-preview-page"></a>Substituir a URL de imagem para imagens de produto do catálogo da página Visualização

Para substituir URLs de imagem para imagens de produto do catálogo, use a página **Visualização**. Não é possível usar a funcionalidade Editar no Excel.

1. Para substituir imagens de produto em nível de catálogo, selecione um catálogo e o produto onde a imagem será substituída.
2. Clique em **Atributos**.
3. Na próxima página, selecione **Imagem** e clique em **Editar**. A página **Visualização** é aberta como uma caixa de diálogo controle deslizante.
4. Clique em **Adicionar** e substitua a URL da imagem por uma nova URL.
5. Clique em **OK**. Agora você vê a visualização da nova imagem e pode defini-la como a imagem padrão.

    [![Visualização da imagem na caixa de diálogo Nova imagem](./media/cat3.png)](./media/cat3.png)

> [!NOTE]
> Após a associação da imagem de categoria, você deve publicar o canal e executar o trabalho do canal para ajudar a garantir que as alterações sejam publicadas no banco de dados do canal.

## <a name="setting-up-images-to-appear-in-offline-mode-for-mpos"></a>Configuração de imagens para aparecerem no modo Offline do MPOS

O MPOS pode ser executado no modo Online (quando o MPOS está conectado ao Commerce Scale Unit) ou no modo Offline (quando não há Commerce Scale Unit ou conectividade de rede, e as transações são armazenadas em um banco de dados offline local). Quando o MPOS é executado no modo Offline, ele não pode obter imagens do servidor de imagem externo para exibir do Commerce Scale Unit, pois a conectividade do Retail Server foi perdida. No entanto, você ainda pode configurar imagens para que sejam mostradas quando o MPOS é executado no modo Offline.

### <a name="set-up-product-images-to-appear-in-offline-mode-for-mpos"></a>Configuração de imagens de produto para aparecerem no modo Offline do MPOS

As imagens de produto que devem ser usadas no modo Offline podem ser configuradas carregando a imagem física necessária na imagem do produto base.

1. Clique em **Gerenciamento de informações do produto** &gt; **Produtos** &gt; **Produtos**.
2. Selecione o produto para definir a imagem offline.
3. Clique em **Editar** e na seta no canto direito para mostrar o painel direito.
4. Na Guia Rápida **Imagem do produto**, clique em **Alterar imagem** e carregue a imagem física a ser usada para o produto selecionado no modo Offline.
5. Salve e feche a página.
6. Enquanto o MPOS estiver no modo Online, execute o trabalho Catálogo na matriz, para verificar se os dados foram enviados pelo menos uma vez ao banco de dados offline.
7. Coloque o MPOS no modo Offline. Você deve ver a imagem que carregou para o produto específico na matriz.

    [![Imagem do produto no modo offline](./media/offline1.png)](./media/offline1.png)

### <a name="set-up-catalog-category-employee-and-customer-images-to-appear-in-offline-mode-for-mpos"></a>Configuração de imagens de catálogo, categoria, funcionário e cliente para aparecerem no modo Offline para MPOS

As imagens de catálogo, categoria, funcionário e cliente que devem ser usadas no modo Offline podem ser configuradas adicionando o link de destino da imagem necessária à galeria, e definindo a imagem como a imagem padrão da entidade selecionada.

1. Vá para o catálogo e, no Painel de Ação, clique em **Mídia** &gt; **Imagens**.
2. Siga as etapas na seção [Substituição da página Visualização em nível de entidade](#overwrite-from-the-entity-level-preview-page) para adicionar a URL externa de imagem.
3. Marque esta imagem como a imagem padrão do catálogo, marcando a caixa de seleção em relação à imagem listada na grade.
4. Execute o trabalho de Catálogo. Esta imagem será usada como a imagem Offline deste catálogo no MPOS.
5. Siga um processo semelhante para outras entidades, como Categoria, Funcionário e Cliente.

    [![Imagem Offline](./media/offline2.png)](./media/offline2.png)
