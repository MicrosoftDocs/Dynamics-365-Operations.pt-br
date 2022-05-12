---
title: Guia de localização de comércio eletrônico do Dynamics 365 Commerce
description: Este tópico descreve como localizar um site de comércio eletrônico do Microsoft Dynamics 365 Commerce em idiomas adicionais e como configurar o site para oferecer suporte a vários canais.
author: bicyclingfool
ms.date: 04/29/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1e9d91036ceeb9161dc8ee903532b2cf3ca435e2
ms.sourcegitcommit: 26c726bd0b00935e3d2c31fdc5a3b2ae03a8a2b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661519"
---
# <a name="dynamics-365-commerce-e-commerce-localization-guide"></a>Guia de localização de comércio eletrônico do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico descreve como localizar um site de comércio eletrônico do Microsoft Dynamics 365 Commerce em idiomas adicionais e como configurar o site para oferecer suporte a vários canais, além de abranger os conceitos e a terminologia relacionados ao processo.

Os recursos de comércio eletrônico no Dynamics 365 Commerce foram criados para habilitar experiências online que podem ser adaptadas a países/regiões e idiomas específicos, mas ao mesmo tempo permitindo a reutilização máxima de modelos, páginas, conteúdo e mídia. Você também pode criar um site básico e expandir para novos mercados adicionando suporte para países/regiões e idiomas adicionais ao longo do tempo.

## <a name="definitions"></a>Definições

**Localidade, ID de localidade**: uma localidade (também conhecida como ID de localidade) define um idioma associado a um país ou uma região. Por exemplo, a ID de localidade "fr-CA" está associada ao francês canadense.

**Idioma base**: o idioma em que você desenvolve o conteúdo do site antes de exportá-lo para localização.

**Canal, loja online**: um canal (também conhecido como uma loja online) define as formas de pagamento, grupos de preços, hierarquias de produtos, sortimentos e produtos para uma vitrine de comércio eletrônico online.

## <a name="concepts"></a>Conceitos

### <a name="url-driven-experience"></a>Experiência orientada por URL

Os sites de comércio eletrônico do Dynamics 365 Commerce fornecem experiências de comercialização e localização exclusivas para clientes por meio de canais e IDs de localidade. Os canais definem os produtos, as categorias, as moedas e as formas de pagamento exclusivos de um mercado, e as IDs de localidade determinam o idioma do conteúdo que os clientes veem. Um site de comércio eletrônico usa URLs para diferenciar as experiências de comercialização e localização. As URLs de site para essas experiências exclusivas de canal e localidade são definidas para um site na página **Configurações do site \> Canais** no criador de sites do Dynamics 365 Commerce.

No criador de sites, uma URL é uma combinação de um domínio e um caminho que define o ponto de entrada para uma combinação exclusiva de um canal e uma localidade. No exemplo a seguir, uma loja online fictícia chamada Fabrikam Inc. define quatro combinações exclusivas de um canal e uma localidade e mapeia cada combinação para uma URL exclusiva que fornece conteúdo aos clientes.

| Domínio                     |  Caminho      | Canal       |   Localidade     |
|------------------------|--------|--------------------------------|--------|
| `https://fabrikam.com` | /      | Loja online estendida da Fabrikam | pt-BR  |
| `https://fabrikam.com` | /es    | Loja online estendida da Fabrikam | es     |
| `https://fabrikam.ca`  | /      | Loja online da Contoso    | fr-ca  |
| `https://fabrikam.ca`  | /en-ca | Loja online da Contoso    | en-ca  |

#### <a name="domain"></a>Domínio

Os domínios são estabelecidos quando você configura o site de comércio eletrônico no Microsoft Dynamics Lifecycle Services (LCs). Depois que o ambiente de comércio eletrônico for provisionado, você poderá adicionar mais domínios abrindo uma solicitação de serviço. Para obter mais informações sobre como configurar domínios para o site de comércio eletrônico, consulte [Domínios no Dynamics 365 Commerce](domains-commerce.md)

#### <a name="path"></a>Caminho

- Um caminho é uma cadeia de caracteres arbitrária que, em combinação com o domínio, é mapeada para uma combinação exclusiva de um canal e uma localidade. No exemplo anterior, a cadeia de caracteres usada como o caminho corresponde à ID de localidade para a qual o caminho está mapeado. No entanto, você pode usar uma abordagem diferente.
- Uma combinação de um canal e uma localidade pode ser mapeada para um domínio e um caminho vazio ("/"). No exemplo anterior, os clientes que acessam `https://fabrikam.ca/` obterão os produtos e sortimentos do mercado canadense em francês canadense.
- O criador de sites do Commerce impede que você crie combinações duplicadas de um domínio e um caminho. No entanto, você pode mapear combinações duplicadas de um canal e uma localidade para uma combinação diferente de um domínio e um caminho.

#### <a name="channel"></a>Canal

- Os canais (também conhecidos como lojas) definem as formas de pagamento, grupos de preços, hierarquias de produtos, sortimentos e produtos para uma vitrine de comércio eletrônico online.
- Os canais são definidos, configurados e publicados na matriz do Dynamics 365 Commerce.
- O criador de sites pode detectar as lojas online que foram configuradas na matriz do Commerce e estão disponíveis para serem mapeadas para um site.

Para obter mais informações sobre os canais, consulte [Visão geral dos canais](channels-overview.md). Para obter mais informações sobre como configurar um canal online, consulte [Configurar um canal online](channel-setup-online.md).

#### <a name="locale"></a>Localidade

- A localidade é o identificador real usado ao entregar arquivos XLIFF (XML Localization Interchange File Format) para localização. As localidades são definidas e publicadas para cada canal na matriz do Commerce. Para obter informações sobre como configurar idiomas e canais no criador de sites, consulte a próxima seção.
- A mesma localidade pode ser mapeada para vários canais. Dessa forma, um idioma comum pode ser oferecido em vários mercados.

## <a name="configure-languages-and-channels-for-your-e-commerce-site"></a>Configurar idiomas e canais para o site de comércio eletrônico

Prontos para uso, todos os sites de comércio eletrônico do Dynamics 365 Commerce são configurados para usar um único canal online e um único idioma, independentemente de você começar com o site de demonstração da Fabrikam ou criar um novo site do zero.

Nessa configuração, os clientes e parceiros normalmente desenvolvem todos os ativos que serão usados em todos os países/regiões e idiomas. Esses ativos incluem modelos, páginas, fragmentos, conteúdo e mídia. Todo o conteúdo do site é desenvolvido no primeiro idioma selecionado para o site ou, se você estiver usando o site de demonstração da Fabrikam, o conteúdo do site será desenvolvido em inglês.

![Site de comércio eletrônico do Dynamics 365 Commerce pronto para uso](media/loc-guide-1.png)

> [!NOTE]
> Você pode configurar o site de demonstração da Fabrikam para um idioma adicional para que o desenvolvimento de conteúdo possa ser feito nesse idioma. Para obter informações sobre como adicionar um novo idioma a um site e um canal, consulte a seção [Configurar um idioma adicional para o site](#configure-an-additional-language-for-your-site) posteriormente neste tópico.

No entanto, o sistema de gerenciamento de conteúdo (CMS) e o modelo de página para sites de comércio eletrônico do Dynamics 365 Commerce foram criados para permitir a expansão em novos mercados e localidades. Portanto, por meio de um único site de comércio eletrônico, é possível gerenciar os ativos de uma loja online que abrange vários mercados e idiomas.

![Site de comércio eletrônico do Dynamics 365 Commerce que abrange vários mercados e idiomas](media/loc-guide-2.png)

### <a name="configure-an-additional-language-for-your-site"></a>Configurar um idioma adicional para o site

O processo de configuração de um novo idioma para um site de comércio eletrônico tem três etapas.

#### <a name="step-1-add-the-language-to-your-channel-online-store-in-commerce-headquarters"></a>Etapa 1: Adicionar o idioma ao canal (loja online) na matriz do Commerce

1. Na matriz do Commerce, vá para o canal ao qual deseja adicionar o novo idioma. Para encontrar a lista de canais que você configurou na matriz do Commerce, acesse **Varejo e Comércio \> Canais \> Lojas online**.
1. Abra a loja online mapeada para o site selecionando seu valor de **ID do Canal de Varejo**. Você pode verificar a loja online mapeada para o site abrindo a página de configuração do site **Canais** no criador de sites do Commerce e olhando o nome da loja online na coluna **Canais**. 
1. Na guia rápida **Idiomas**, selecione **Adicionar**. No campo **Idioma**, selecione o código de localidade para o novo idioma. Selecione **Salvar**.
1. Acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição** e execute o trabalho **Configuração do canal 1070**. Quando a execução do trabalho terminar, você poderá passar para a etapa 2 e adicionar o idioma a um canal do site no criador de sites.

![Guia rápida Idiomas de uma loja online na matriz do Commerce](media/loc-guide-3.png)

#### <a name="step-2-add-the-language-to-a-channel-in-site-builder"></a>Etapa 2: Adicionar o idioma a um canal no criador de sites

Para adicionar um idioma a um canal no criador de sites, siga estas etapas.

1. No criador de sites do Commerce, abra o site e abra a página **Canais** nas configurações do site.
1. Selecione o nome do canal ao qual você deseja adicionar o idioma.
1. No painel à direita, selecione **Adicionar uma localidade**.
1. Na caixa de diálogo **Adicionar uma localidade**, em **Adicionar uma localidade**, selecione a localidade do idioma adicionado anteriormente ao canal na matriz do Commerce.
1. Selecione o domínio e o caminho que os clientes solicitarão para exibir o site neste canal e neste idioma.
1. Se você quiser que o idioma seja o idioma padrão para exibição, criação e atualização das páginas e fragmentos do criador de sites, marque a caixa de seleção **Usar como idioma padrão de criação de canal**. 
    > [!NOTE]
    > Esta configuração afeta somente o criador de sites. Ela não influencia a experiência do site publicado para os clientes.
1. Selecione **OK**.
1. Selecione **Salvar e publicar**.

#### <a name="step-3-localize-your-site-content"></a>Etapa 3: Localizar o conteúdo do site

Quando você retornar ao modo de exibição **Páginas** no criador de sites do Commerce, o novo idioma estará disponível no seletor de canal e localidade no canto superior direito. Agora é possível criar versões localizadas das páginas no idioma base.

O processo de localização do conteúdo de páginas e fragmentos é abordado na seção [Localizar conteúdo de site de comércio eletrônico](#localize-e-commerce-site-content) posteriormente neste tópico.

### <a name="configure-a-new-channel-for-your-site"></a>Configurar um novo canal para o site

Os sites de comércio eletrônico do Dynamics 365 Commerce podem fornecer experiências definidas em vários canais online configurados na matriz do Commerce. Um site usa vários canais para mostrar aos clientes uma configuração exclusiva de formas de pagamento, grupos de preços, hierarquias de produtos, sortimentos e um conjunto de produtos. Geralmente, um canal é usado para configurar essas dimensões de acordo com as necessidades e preferências da experiência associada a países/regiões individuais. No entanto, essa abordagem é uma decisão comercial do cliente. Ela não é um requisito.

Os pré-requisitos e as tarefas associadas à configuração de um canal (loja online) não fazem parte do escopo deste documento. Para obter mais informações sobre como configurar um canal online na matriz do Commerce, consulte [Noções básicas da configuração de canal](channels-overview.md#channel-setup-basics). Para obter informações sobre as etapas e os requisitos específicos para canais online, consulte [Configurar um canal online](channel-setup-online.md).

Para adicionar um canal ao site no criador de sites, siga estas etapas.

1. No criador de sites do Commerce, acesse **Configurações do site \> Canais**. 
1. Selecione **Adicionar um canal**.
1. Na caixa de diálogo **Adicionar um canal**, em **Canal**, selecione o canal que deseja adicionar. 
    > [!NOTE]
    > Só é possível adicionar canais que ainda não foram adicionados ao site.
1. Selecione a localidade padrão para o canal. Se você adicionar novos idiomas ao canal, poderá alterar o idioma padrão para um deles.
1. Especifique o domínio e o caminho que constituirão a URL que veiculará conteúdo e experiências para essa combinação de canal e idioma.
1. Selecione **OK**.
1. Selecione **Salvar e publicar**.

## <a name="localize-e-commerce-site-content"></a>Localizar conteúdo do site de comércio eletrônico

### <a name="xliff-basics"></a>Noções básicas sobre XLIFF

XLIFF é um formato de arquivo padrão do setor para transmitir conteúdo localizável entre ferramentas de gerenciamento de conteúdo. O criador de sites do Commerce usa o formato de arquivo XLIFF para exportar conteúdo de metadados de página, fragmento e imagem, de forma que possa ser localizado e reimportado.

Normalmente, os clientes do Microsoft Dynamics trabalham com fornecedores de localização terceirizados, como [Translated.com](https://translated.com/welcome) para traduzir os arquivos XLIFF para os idiomas necessários.

### <a name="localize-assets-in-site-builder"></a>Localizar ativos no criador de sites

Os seguintes ativos do site de comércio eletrônico podem ser localizados no criador de sites:

- Páginas
- Fragmentos
- Ativos de mídia
- Módulos

Todas as novas páginas, fragmentos e ativos de mídia são criados no contexto do canal e do idioma selecionados no momento no seletor de canal e localidade. Geralmente, esse idioma é seu "idioma base", desde que você não tenha configurado outros idiomas ou canais. Em sites nos quais vários canais e idiomas são configurados, o "idioma base" é definido pelo canal e pela localidade que você definiu como padrão na página **Canais** nas configurações do site.

As etapas para localizar conteúdo para páginas, fragmentos e ativos de mídia são semelhantes. Exceções e diferenças serão indicadas nas seções a seguir. No entanto, as etapas para localizar o conteúdo do módulo são diferentes. Para obter mais informações, consulte a seção [Localizar módulos](#localize-modules) posteriormente neste tópico.

#### <a name="step-1-export-an-xliff-file"></a>Etapa 1: Exportar um arquivo XLIFF

Para exportar um arquivo XLIFF para uma página, fragmento ou imagem no criador de sites, siga estas etapas.

1. Abra o ativo para o qual deseja exportar o conteúdo do idioma base, de forma que ele possa ser localizado.
1. Na barra de comandos, selecione **Localização \> Exportar XLIFF**.
    > [!NOTE]
    > A opção **Localização** ficará visível somente quando o ativo estiver em um estado **Edição**.

Um arquivo XLIFF chamado **\<assetname\>.xlf** será baixado para a pasta de download do navegador. Esse arquivo XLIFF é específico para o ativo que está sendo localizado. Você exportará um arquivo XLIFF para cada ativo que deseja localizar.

#### <a name="step-2-localize-the-xliff-file"></a>Etapa 2: Localizar o arquivo XLIFF

Na maioria dos casos, você trabalhará com um fornecedor de localização para traduzir os arquivos XLIFF. No entanto, se você estiver localizando ativos internamente ou se apenas quiser testar o processo de localização, será necessário fazer as seguintes alterações em um arquivo XLIFF:

- Adicione um atributo de idioma de destino ao elemento /xliff/file e defina o valor para a ID de localidade do idioma para o qual você está localizando. 
    > [!NOTE]
    > Essa ID de localidade deve corresponder à ID de localidade da página **Canais** nas configurações do site.
- Para cada elemento //source, adicione um irmão do elemento de destino em que o valor do texto seja a versão localizada do conteúdo desse elemento de origem.

Para obter informações sobre o esquema que controla os arquivos XLIFF, consulte a [Especificação do XLIFF 1.2](http://docs.oasis-open.org/xliff/xliff-core/xliff-core.html).

> [!NOTE]
> Para localizar um ativo em vários idiomas, é necessário criar um arquivo XLIFF localizado para cada um desses idiomas.

#### <a name="step-3-import-the-localized-xliff-file"></a>Etapa 3: Importar o arquivo XLIFF localizado

Para importar um arquivo XLIFF para um ativo, siga estas etapas.

1. No criador de sites do Commerce, abra o ativo para o qual você deseja importar um arquivo XLIFF.
1. No seletor de canal e localidade, no canto superior direito, selecione o canal e o idioma para os quais você está importando conteúdo localizado.
1. Na barra de comandos, selecione **Localização \> Importar XLIFF**. Em seguida, procure e selecione o arquivo XLIFF localizado para o ativo e o idioma selecionados.

Depois que o arquivo XLIFF é importado com êxito, uma "variante" da página, do fragmento ou do ativo é criada. Desse ponto em diante, todas as alterações feitas na variante localizada afetarão somente essa variante. Elas não afetarão o ativo base do qual a variante foi derivada. Da mesma forma, as alterações no ativo base não afetarão a variante desse ativo. 

No entanto, no caso das páginas, você pode fazer alterações nas variantes modificando o modelo ou o layout ao qual essas páginas estão vinculadas. Da mesma forma, as alterações em um fragmento afetarão todas as páginas que assumem uma dependência dessa variante.

### <a name="images"></a>Imagens

As imagens podem ser processadas em uma variante de página ou módulo somente se os metadados de conteúdo associados a essas imagens estiverem localizados. No momento, os seguintes metadados em um ativo de mídia são localizáveis:

- Texto alternativo
- Descrição
- Cargo

No momento, não é possível localizar o binário para um ativo digital como uma imagem ou um vídeo. A equipe do produto Dynamics 365 Commerce está trabalhando nesta capacidade no momento.

### <a name="localize-modules"></a>Localizar módulos

As sequências de caracteres que são renderizadas como parte do próprio módulo (por exemplo, "Anterior" e "Próximo" em um módulo carrossel) são localizadas separadamente do conteúdo do módulo. Para obter instruções, consulte [Localizar um módulo](e-commerce-extensibility/localize-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Glossário do modelo de página](page-elements-overview.md)

[Compartilhamento entre canais](cross-channel-sharing.md)

[Localizar um módulo](e-commerce-extensibility/localize-module.md)

[Arquivo de definição do módulo](e-commerce-extensibility/module-definition-file.md)

[Localizar recursos de extensão e arquivos de etiquetas do Commerce](dev-itpro/extension-resource-localization.md)

[Globalizar módulos usando a classe CultureInfoFormatter](e-commerce-extensibility/globalize-modules.md)

[Configurações de aplicativo: temas](e-commerce-extensibility/app-settings.md#themes-section)
