---
title: Mapear canais para sites de comércio eletrônico
description: Este artigo descreve alguns dos cenários de mapeamento de canal mais comuns no Microsoft Dynamics 365 Commerce que podem ser extrapolados para a maioria dos outros requisitos de negócios.
author: samjarawan
ms.date: 05/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 94c43df26e8d6e55a5b6d459b65066d5873e1063
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902754"
---
# <a name="map-channels-to-e-commerce-sites"></a>Mapear canais para sites de comércio eletrônico

Este artigo descreve alguns dos cenários de mapeamento de canal mais comuns no Microsoft Dynamics 365 Commerce que podem ser extrapolados para a maioria dos outros requisitos de negócios.

O Dynamics 365 Commerce oferece suporte a muitos cenários de negócios para mapeamento de [canais online](#channels) que têm um conjunto configurado de produtos, preços e descontos para experiências de [sites de comércio eletrônico](#e-commerce-sites) para os clientes.

Este artigo abrange os seguintes cenários:

- **Um canal de idioma único que possui uma única experiência de site de comércio eletrônico.** Por exemplo, esse cenário pode envolver um site de marca única configurado para o mercado em inglês dos EUA.
- **Um canal com vários idiomas que tem uma única experiência de site localizada.** Por exemplo, esse cenário pode envolver um site de marca única configurado para o Canadá com suporte aos idiomas francês e inglês. Nesse cenário, os usuários que selecionam idiomas diferentes têm a mesma experiência no site, mas está localizada no idioma selecionado de cada usuário.
- **Um canal com vários idiomas que tem uma experiência de site diferente por idioma.** Por exemplo, esse cenário pode envolver um site de marca única configurado para o Canadá com suporte aos idiomas francês e inglês. Nesse cenário, há experiências de site únicas para cada idioma.
- **Vários canais (um único idioma e/ou vários idiomas) que têm uma única experiência de site localizada.** Por exemplo, esse cenário pode envolver um site de marca única configurado para a Austrália e Nova Zelândia. Nesse cenário, os dois países compartilham a mesma experiência do site em inglês, mas cada país é configurado com produtos, moedas, preços, descontos e modos de envio diferentes.
- **Vários canais (um único idioma e/ou vários idiomas) que têm uma experiência de site diferente por canal.** Por exemplo, esse cenário pode envolver um site de marca única configurado para a Austrália, Canadá e Alemanha em vários idiomas. Nesse cenário, cada país tem uma experiência de site exclusiva que é configurada com diferentes produtos, moedas, preços, descontos e modos de envio.

## <a name="channels"></a>Canais

Um canal (também conhecido como loja online ou canal online) representa uma vitrine de comércio eletrônico online usada para mapear produtos, preços, descontos, idiomas, métodos de pagamento, modos de entrega, centros de atendimento e outros aspectos da experiência online que estará disponível para seus clientes de comércio eletrônico. Os canais são criados e gerenciados no Commerce headquarters e mapeados para uma única [entidade legal](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json#legal-entities). A entidade legal geralmente está sediada em um único país que exige relatórios fiscais para o canal e pode ser configurada com apenas uma única moeda.

Para obter mais informações sobre os canais, consulte [Visão geral do canal](channels-overview.md). Para obter mais informações sobre como criar um canal online, consulte [Configurar um canal online](channel-setup-online.md).

A ilustração de exemplo a seguir do Commerce headquarters mostra os canais online padrão que são implantados com o Dynamics 365 Commerce se a opção de dados de demonstração estiver selecionada.

![Canais de dados de demonstração padrão no Commerce headquarters.](media/channel-mapping-1.png)

## <a name="e-commerce-sites"></a>Sites do comércio eletrônico

Um site de comércio eletrônico contém um conjunto de páginas do site que os clientes usam para navegar e fazer compras. Os sites de comércio eletrônico são gerenciados no construtor de sites do Commerce.

Para obter mais informações sobre como criar e gerenciar sites no construtor de sites, consulte [Visão geral do site de comércio eletrônico](online-store-overview.md).

## <a name="common-channel-mapping-scenarios"></a>Cenários comuns de mapeamento de canais

O Dynamics 365 Commerce oferece suporte a uma ampla variedade de cenários de mapeamento de canal. Os cenários de mapeamento de canal a seguir são apenas um subconjunto de todos os cenários de mapeamento de canal possíveis. Eles são um guia para ajudar você a planejar quaisquer cenários de negócios exclusivos que você tenha. A loja fictícia de artigos esportivos Adventure Works incluída nos dados de demonstração do Dynamics 365 Commerce é usada como exemplo para cada cenário.

### <a name="single-language-channel-that-has-a-single-e-commerce-site-experience"></a>Canal de idioma único que possui uma única experiência de site de comércio eletrônico

No cenário mais básico, um único canal possui um único idioma para venda em um único mercado. Um exemplo desse cenário é uma loja online Adventure Works configurada apenas para o mercado em inglês dos EUA.

A ilustração de exemplo a seguir mostra uma configuração de canal no Commerce headquarters. Nesta configuração, o canal online permite apenas um único idioma (**en-us**), uma única moeda (**USD**) e uma única entidade de negócio (**usrt**) que é usada para relatórios fiscais.

![Valores de entidade legal, moeda e idioma para a loja online Adventure Works destacados no Commerce headquarters.](media/channel-mapping-3.png)

O único canal online pode ser mapeado para um único site de comércio eletrônico no construtor de sites. Para obter informações sobre como criar um site e mapeá-lo para um canal, consulte a seção [Mapear um canal para um site no construtor de sites](#map-a-channel-to-a-site-in-site-builder) deste artigo.

### <a name="multi-language-channel-that-has-a-single-localized-site-experience"></a>Canal com vários idiomas que tem uma única experiência de site localizada

Nesse cenário, um único canal oferece suporte a mais de um idioma. Portanto, nomes de produtos, descrições e atributos podem ser localizados no Commerce headquarters. Para fornecer uma experiência completa de site localizado, o conteúdo de marketing no site também pode ser localizado no construtor de sites do Commerce.

A limitação deste cenário é que um único canal pode ser configurado com apenas uma moeda, uma entidade legal e um conjunto de produtos e preços. Essa configuração funciona melhor para países que têm uma única moeda e vários idiomas (por exemplo, Canadá, que tem os idiomas inglês e francês), uma única entidade legal e um único conjunto de produtos e preços.

Cada idioma em um canal pode ser configurado com seu próprio nome de domínio. Por exemplo, o domínio `www.adventure-works.ca` pode ser configurado para a versão em inglês do Canadá e o domínio `www.adventure-works-fr.ca` pode ser configurado para a versão em francês do Canadá. Como alternativa, diferentes idiomas em um canal podem ser configurados em um único domínio e depois um caminho diferente pode ser usado para cada idioma. Por exemplo, o domínio `www.adventure-works.ca` pode ser configurado para a versão em inglês do Canadá e depois o caminho `www.adventure-works.ca/fr` pode ser usado para a versão em francês do Canadá. A [detecção geográfica](geo-detection-redirection.md) também pode ser habilitada para redirecionar automaticamente um usuário para o site correto, com base na localização do usuário.

Para obter informações sobre como permitir que os clientes alternem manualmente entre os idiomas, consulte a seção [Adicionar e configurar o módulo seletor de sites](#add-and-configure-the-site-picker-module) deste artigo. Para obter informações sobre como personalizar páginas e fragmentos localizados, consulte a seção [Gerenciar o conteúdo do site que tem vários canais e idiomas](#manage-site-content-that-has-multiple-channels-and-languages).

### <a name="multi-language-channel-that-has-a-different-site-experience-per-language"></a>Canal com vários idiomas que tem uma experiência de site diferente por idioma

Você pode preferir um cenário em que um único canal oferece suporte a mais de um idioma, mas uma experiência de site completamente diferente é renderizada para cada idioma. O método recomendado para implementar esse cenário é usar [variantes de página](#implement-page-variants-for-each-language) em um único site.

Outro método é criar um site de comércio eletrônico para cada idioma no construtor de sites e depois mapear cada site para um único canal e idioma online. O resultado será um único canal online mapeado para vários sites de comércio eletrônico, um para cada idioma. Esse método de vários sites requer recursos de gerenciamento extras, pois haverá mais de um site para gerenciar no construtor de sites.

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-single-localized-site-experience"></a>Vários canais (um único idioma e/ou vários idiomas) que têm uma única experiência de site localizada

Um site de marca pode exigir vários canais online por região para oferecer suporte a uma moeda, um conjunto de produtos e um conjunto de preços diferentes para cada canal em um único site. Por exemplo, o site da Adventure Works pode ter um canal online para o mercado canadense com vários idiomas, um canal para o mercado americano com um idioma e um canal para o mercado alemão com um idioma. Nesse cenário, cada canal online será configurado para uma entidade legal específica da região e pode ter o mesmo conjunto de produtos que outros canais têm, um subconjunto desses produtos ou um conjunto diferente de produtos. Cada canal também terá seus próprios preços na moeda regional, impostos, descontos e modos de envio.

Nesse cenário, cada mercado pode ser configurado com seus próprios nomes de domínio. Por exemplo, o domínio `www.adventure-works.com` pode ser configurado para o mercado dos EUA, e o domínio `www.adventure-works.de` pode ser configurado para o mercado alemão. Como alternativa, cada mercado pode ser configurado para usar um caminho diferente. Por exemplo, o domínio `www.adventure-works.com` pode ser configurado para o mercado dos EUA e depois o caminho `www.adventure-works.com/de` pode ser usado para o mercado alemão. A [detecção geográfica](geo-detection-redirection.md) também pode ser habilitada para redirecionar automaticamente os usuários para o site correto, com base em sua região.

Também possível querer que seu site forneça uma lista suspensa que permita aos usuários alternar manualmente para um mercado específico. Para obter mais informações, consulte a seção [Adicionar e configurar o módulo seletor de sites](#add-and-configure-the-site-picker-module) deste artigo.

Para obter informações sobre como configurar vários canais em um único site, consulte a seção [Configurar vários canais em um site de comércio eletrônico](#configure-multiple-channels-on-an-e-commerce-site).

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-different-site-experience-per-channel"></a>Vários canais (um único idioma e/ou vários idiomas) que têm uma experiência de site diferente por canal

Talvez você queira ter vários canais para uma única marca em diferentes regiões e deseje que cada região tenha uma experiência de site diferente. Existem dois métodos para implementar tal cenário:

- Use [variantes de página](#implement-page-variants-for-each-language).
- Configure um site diferente para cada canal online no construtor de sites e mapeie cada site para um canal e idioma online diferentes. Esse método requer recursos de gerenciamento extras, pois haverá mais de um site para gerenciar no construtor de sites.

## <a name="cross-channel-sharing"></a>Compartilhamento entre canais

O compartilhamento entre canais é útil quando vários canais em um único site podem compartilhar conteúdo. Por exemplo, um varejista que tem várias marcas e lojas que são agrupadas em um único site pode compartilhar algum conteúdo entre algumas ou todas as lojas. O conteúdo compartilhado pode incluir páginas para termos e condições, condições de pagamento, métodos de remessa e perguntas frequentes (FAQ). Para obter mais informações, consulte [Habilitar e usar o compartilhamento entre canais](cross-channel-sharing.md).

## <a name="map-a-channel-to-a-site-in-site-builder"></a>Mapear um canal para um site no construtor de sites

Existem vários métodos para criar e configurar sites para usar diferentes canais online.

### <a name="create-a-new-site"></a>Criar um site

Você pode criar um site totalmente novo no construtor de sites acessando a página de lista de **Sites** e selecionando **Novo site**. Depois, na caixa de diálogo **Novo site** exibida, você pode selecionar o canal online padrão e o idioma do site, conforme mostrado na ilustração de exemplo a seguir.

![Criação de um canal no construtor de sites.](media/channel-mapping-4.png)

O site que você criar dessa forma ficará vazio e não incluirá nenhuma página do site (por exemplo, uma página inicial, páginas de categorias e páginas de produtos).

Para obter mais informações, consulte [Criar um site de comércio eletrônico](create-ecommerce-site.md).

### <a name="create-a-new-site-by-using-the-site-copy-operation"></a>Criar um site usando a operação de cópia do site

Em vez de criar um site novo e vazio conforme descrito na seção anterior, uma prática melhor é começar com uma cópia de um dos sites iniciais fornecidos na biblioteca do módulo Comércio, como o site da Fabrikam ou Adventure Works.

Para copiar um site existente, vá para a página de lista de **Sites** no construtor de sites e selecione **Copiar site**. Em seguida, na caixa de diálogo **Copiar site** exibida, você pode selecionar o site de origem e especificar o nome do site de destino.

Nesse momento, você ainda não pode selecionar o canal online padrão e o idioma do site. No entanto, você pode configurar essas propriedades após a conclusão da operação de cópia do site. Quando você seleciona o site pela primeira vez na página de lista de **Sites** no construtor de sites, é exibida a caixa de diálogo **Configurar seu site**, onde você pode selecionar o canal e o idioma padrão.

Para obter mais informações sobre a operação de cópia do site, consulte [Copiar um site de comércio eletrônico](copy-ecommerce-site.md).

### <a name="manage-an-existing-site-channel"></a>Gerenciar um canal de site existente

Depois que um site for configurado com um canal, você poderá gerenciar e atualizar o canal usando o site selecionado no criador de sites em **Configurações de site \> Canais**, conforme mostrado na ilustração de exemplo a seguir.

![Gerenciamento do mapeamento de canais no construtor de sites.](media/channel-mapping-7.png)

## <a name="support-multiple-sites-in-a-single-tenant"></a>Suporte a vários sites em um único locatário

Muitos sites de marca podem coexistir em um único locatário. A ilustração de exemplo a seguir mostra três sites de marca diferentes (Adventure Works, Adventure Works Business e Fabrikam), cada um mapeado para um único canal online diferente.

![Lista de sites no construtor de sites.](media/channel-mapping-8.png)

## <a name="configure-a-single-domain-name-with-paths-for-multiple-sites"></a>Configurar um único nome de domínio com caminhos para vários sites

Um único nome de domínio pode ser usado para vários sites e os caminhos podem ser usados para separar sites ou idiomas. Por exemplo, o domínio `www.mycompany.com` está configurado para dois sites de comércio eletrônico diferentes: um para a Fabrikam e outro para a Adventure Works. Nesse caso, o caminho padrão (`www.mycompany.com`), também conhecido como caminho em branco, pode ser usado para o site da Fabrikam, e outro caminho (por exemplo, `www.mycompany.com/adventureworks`) pode ser usado para o site da Adventure Works. Outra opção é usar um caminho personalizado (por exemplo, `www.mycompany.com/fabrikam`) em vez do caminho padrão para o site da Fabrikam também.

Como alternativa, um nome de domínio diferente pode ser usado para cada site (por exemplo, `www.adventure-works.com` e `www.fabrikam.com`). Os caminhos podem ser usados para diferentes idiomas ou regiões (por exemplo, `www.adventure-works.com/fr-ca` para francês do Canadá).

## <a name="configure-multiple-languages-on-a-site"></a>Configurar vários idiomas em um site

Os idiomas podem ser configurados para o site de comércio eletrônico no construtor de sites em **Configurações de site \> Canais**. Na ilustração de exemplo a seguir, cada idioma foi configurado usando a localidade para o caminho, para que cada idioma tenha uma URL exclusiva.

![Vários idiomas configurados em um site.](media/channel-mapping-10.png)

Para adicionar um novo idioma de canal, acesse **Configurações de site \> Canais** e selecione o link do canal. No painel que aparece à direita, selecione **Adicionar uma localidade** para selecionar o canal e a localidade que deseja adicionar. Em seguida, especifique o caminho a ser usado para o canal selecionado.

### <a name="add-and-configure-the-site-picker-module"></a>Adicionar e configurar o módulo seletor de sites

Depois de configurar um site com vários idiomas e/ou canais, convém adicionar um seletor de idioma ao cabeçalho da página do site para que os usuários possam selecionar manualmente seu idioma ou país. O [módulo de cabeçalho](author-header-module.md) da biblioteca de módulos tem suporte integrado para que os usuários selecionem um idioma usando o [módulo de seletor de sites](site-selector.md). O módulo seletor de sites pode ser adicionado ao módulo de cabeçalho no fragmento de cabeçalho.

Para obter mais informações sobre como adicionar e configurar o módulo seletor de sites, consulte [Módulo de seletor de sites](site-selector.md).

### <a name="implement-page-variants-for-each-language"></a>Implementar variantes de página para cada idioma

Nesse cenário, há apenas um canal, mas existem vários idiomas. Você pode alterar a aparência de uma página com base no idioma selecionado criando uma variante de página para ela. Você pode adicionar conteúdo localizado à variante.

Quando você tem uma página aberta no construtor de sites e seleciona o link no canto superior direito que mostra o canal e o idioma atuais, um seletor de canal e idioma é exibido, conforme mostrado na ilustração de exemplo a seguir. Se você quiser substituir a página pelo idioma atual, selecione outra localidade e depois selecione **Alterar**. Você também pode alterar o canal se estiver [gerenciando um site com vários canais e idiomas](#manage-site-content-that has-multiple-channels-and-languages).

![Alteração do idioma de uma página no construtor de sites.](media/channel-mapping-14.png)

Se a variante da página ou fragmento selecionado ainda não tiver sido criada, você receberá uma mensagem de aviso, conforme mostrado na ilustração de exemplo a seguir. Nesse caso, selecione o link **Criar grade de página** no texto da mensagem. A caixa de diálogo que aparece oferece opções que permitem que você comece com uma cópia de uma variante existente ou crie uma página totalmente nova a partir de um modelo.

![Solicitar a criação de uma variante de página no construtor de sites](media/channel-mapping-16.png)

Se você não criar uma variante, a página original será renderizada e mostrará o idioma apropriado para cadeias de caracteres de módulo e informações de produto do Commerce headquarters. Contudo, se um texto como um título de página ou outro conteúdo de marketing tiver sido especificado diretamente nos módulos de página padrão, as cadeias de caracteres desse texto permanecerão no idioma original.

Em vez de criar manualmente cada página e fragmento, você pode exportar cada página e fragmento para um arquivo XLIFF (XML Localization Interchange File Format) que pode ser enviado para localização. Após a localização de cada XLIFF, ele pode ser importado como uma variante de página localizada. Para exportar um arquivo XLIFF de uma página ou fragmento no construtor de sites ou importar um arquivo XLIFF para uma página ou fragmento, selecione **Localização** na barra de comandos. Em seguida, selecione **Exportar XLIFF** ou **Importar XLIFF**, conforme mostrado na ilustração de exemplo a seguir.

![Importação ou exportação de uma página ou fragmento no formato XLIFF.](media/channel-mapping-18.png)

## <a name="manage-site-content-that-has-multiple-channels-and-languages"></a>Gerenciar o conteúdo do site que tem vários canais e idiomas

Um site com vários canais e/ou idiomas armazena uma variante exclusiva de cada página e fragmento para cada combinação de canal e idioma. Esse comportamento permite que as variantes de página contenham dados localizados, mas também oferece a flexibilidade de alterar a aparência de uma página para uma variante específica.

Para obter informações sobre como trabalhar com variantes de página, consulte a seção [Implementar variantes de página para cada idioma](#implement-page-variants-for-each-language) deste artigo.

## <a name="configure-multiple-channels-on-an-e-commerce-site"></a>Configurar vários canais em um site de comércio eletrônico

Você pode adicionar canais a um site de comércio eletrônico no criador de sites acessando **Configurações de site \> Canais** e selecionando **Adicionar um canal**. Depois, na caixa de diálogo **Adicionar um canal** exibida, você pode selecionar o canal online e a localidade padrão.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de canais](channels-overview.md)

[Configurar um canal online](channel-setup-online.md)

[Visão geral de organizações e hierarquias organizacionais](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md)

[Configurar detecção e redirecionamento geográfico](geo-detection-redirection.md)

[Habilitar e usar o compartilhamento entre canais](cross-channel-sharing.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Copiar um site de comércio eletrônico](copy-ecommerce-site.md)

[Módulo de seletor de sites](site-selector.md)
