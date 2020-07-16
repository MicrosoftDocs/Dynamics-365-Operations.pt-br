---
title: Gerenciar arquivos robots.txt
description: Este tópico descreve como gerenciar os arquivos robots. txt no Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: brishoo
ms.search.validFrom: 2019-12-18
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4b3856a7a0b4b198e71ce9af6691b1d90362f3e7
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533404"
---
# <a name="manage-robotstxt-files"></a>Gerenciar arquivos robots.txt


[!include [banner](includes/banner.md)]

Este tópico descreve como gerenciar os arquivos robots. txt no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

O padrão de exclusão de robôs, ou robots. txt é um padrão que os sites usam para comunicar-se com os robôs da Web. Ele instrui os robôs da Web sobre as áreas de um site que não devem ser visitadas. Os robôs geralmente são usados por mecanismos de pesquisa para indexar sites.

Para excluir os robôs de um servidor, crie um arquivo no servidor. Neste arquivo, especifique uma política de acesso para robôs. O arquivo deve ser acessível via HTTP no URL local **/robots.txt**. O arquivo robots. txt ajuda os mecanismos de pesquisa a indexar o conteúdo no site.

O Dynamics 365 Commerce permite carregar um arquivo robots. txt para o seu domínio. Para cada domínio no seu ambiente de Commerce, você pode carregar um arquivo robots. txt e associá-lo a esse domínio.

Para obter mais informações sobre o arquivo robots. txt, visite [As Páginas de Robôs da Web](https://www.robotstxt.org/).

## <a name="upload-a-robotstxt-file"></a>Carregar um arquivo robots. txt

Depois de criar e editar o arquivo robots. txt de acordo com o [padrão de exclusão de robôs](https://www.robotstxt.org/orig.html), verifique se o arquivo está acessível no computador em que você usará as ferramentas de criação do Commerce. O arquivo deve ter o nome **robots.txt**. Para obter melhores resultados, ele deve estar no formato observado no padrão. Cada cliente do Commerce é responsável por validar e manter o conteúdo do arquivo robots. txt. Para carregar um arquivo robots.txt, você deve fazer logon no Commerce como um administrador de sistema.

Para carregar um arquivo robots. txt no Commerce, siga estas etapas.

1. Faça logon no Commerce como um administrador do sistema.
2. No painel de navegação esquerdo, selecione **Configurações do Locatário** (próximo ao símbolo de engrenagem) para expandi-las.
3. Em **Configurações do Locatário**, selecione **Robots.txt**. Uma lista de todos os domínios associados ao seu ambiente aparece na parte principal da janela.
4. Selecione **Gerenciar** para carregar um arquivo robots. txt para um domínio no seu ambiente.
5. No menu à direita, selecione o botão **Carregar** (a seta apontando para cima) próximo ao domínio associado ao arquivo robots. txt. Uma caixa de diálogo do navegador de arquivos é exibida.
6. Na caixa de diálogo, procure e selecione o arquivo robots. txt que deseja carregar para o domínio associado e, em seguida, selecione **Abrir** para concluir o carregamento.

> [!NOTE] 
> Durante o carregamento, o Commerce verifica se o arquivo é um arquivo de texto, mas não valida o conteúdo do arquivo.

## <a name="download-a-robotstxt-file"></a>Baixar um arquivo robots. txt

Para baixar um arquivo robots. txt no Commerce, siga estas etapas.

1. Faça logon no Commerce como um administrador do sistema.
2. No painel de navegação esquerdo, selecione **Configurações do Locatário** (próximo ao símbolo de engrenagem) para expandi-las.
3. Em **Configurações do Locatário**, selecione **Robots.txt**. Uma lista de todos os domínios associados ao seu ambiente aparece na parte principal da janela.
4. Selecione **Gerenciar** para baixar um arquivo robots. txt para um domínio no seu ambiente.
5. No menu à direita, selecione o botão **Baixar** (a seta apontando para baixo) próximo ao domínio associado ao arquivo robots. txt. Uma caixa de diálogo do navegador de arquivos é exibida.
6. Na caixa de diálogo, vá para o local desejado na unidade local, confirme ou insira um nome de arquivo e selecione **Salvar** para concluir o download.

> [!NOTE]
> Este procedimento pode ser usado para baixar somente os arquivos robots. txt que foram previamente carregados por meio das ferramentas de criação do Commerce.

## <a name="delete-a-robotstxt-file"></a>Excluir um arquivo robots. txt

Para excluir um arquivo robots. txt no Commerce, siga estas etapas.

1. Faça logon no Commerce como um administrador do sistema.
2. No painel de navegação esquerdo, selecione **Configurações do Locatário** (próximo ao símbolo de engrenagem) para expandi-las.
3. Em **Configurações do Locatário**, selecione **Robots.txt**. Uma lista de todos os domínios associados ao seu ambiente aparece na parte principal da janela.
4. Selecione **Gerenciar** para excluir um arquivo robots. txt para um domínio no seu ambiente.
5. No menu à direita, selecione o botão **Excluir** (o símbolo de lata de lixo) próximo ao domínio associado ao arquivo robots. txt. Uma janela do navegador de arquivos é exibida.
6. Na janela do navegador de arquivos, procure e selecione o arquivo robots. txt que deseja excluir do domínio e, em seguida, selecione **Abrir**. Uma caixa de mensagem de aviso é exibida.
7. Na caixa de mensagem, selecione **Excluir** para confirmar a exclusão do arquivo robots. txt.

> [!NOTE] 
> Este procedimento pode ser usado para excluir somente os arquivos robots. txt que foram previamente carregados por meio das ferramentas de criação do Commerce.

## <a name="additional-resources"></a>Recursos adicionais

[Configure seu nome de domínio](configure-your-domain-name.md)

[Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md)

[Criar um site de comércio eletrônico](create-ecommerce-site.md)

[Associar um site online a um canal](associate-site-online-store.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar um locatário B2C do Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-B2C-tenants.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)
