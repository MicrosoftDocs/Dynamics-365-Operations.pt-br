---
title: Verificar acessibilidade do conteúdo da página
description: Este artigo descreve como verificar a acessibilidade do conteúdo da página no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: caccb6085947193e4a5f8a8555722dd073f0c275
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884751"
---
# <a name="verify-page-content-accessibility"></a>Verificar acessibilidade do conteúdo da página

[!include [banner](includes/banner.md)]

Este artigo descreve como verificar a acessibilidade do conteúdo da página no Microsoft Dynamics 365 Commerce.

Quando tiver terminado de alterar uma página, verifique se o conteúdo está acessível a todos na Web. Nas ferramentas de criação do Commerce, você pode facilmente verificar a acessibilidade do conteúdo da página usando o serviço integrado [Insights de Acessibilidade da Microsoft](https://accessibilityinsights.io/). Este serviço verifica o conteúdo da página em relação às diretrizes de [Acessibilidade da World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility) mais recentes.

A integração do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) deve ser ativada no nível de site ou locatário antes de você usá-la.

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a>Ative o Microsoft Accessibility Insights para todos os sites de seu locatário.

Para ativar a integração do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para todos os sites do Commerce em seu locatário, siga estas etapas.

> [!NOTE]
> Para acessar as configurações de locatários, você deve fazer logon no Commerce como um administrador de sistema.

1. Faça logon no Commerce como um administrador do sistema.
1. No painel de navegação esquerdo, selecione **Configurações do Locatário** (próximo ao símbolo de engrenagem) para expandi-las.
1. Em **Configurações do Locatário**, selecione **Recursos**.
1. Defina a opção de **Verificação de Acessibilidade** como **Ativada**.

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a>Ative o Microsoft Accessibility Insights para um único site

Para ativar a integração do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para um site único do Commerce, siga estas etapas.

1. Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).
1. No painel de navegação esquerdo, selecione **Configurações de Site** para expandi-lo.
1. Em **Configurações de Site**, selecione **Recursos**.
1. Defina a opção de **Verificação de Acessibilidade** como **Ativada**.

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a>Verifique a acessibilidade do conteúdo na home page

Para usar o serviço integrado do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para digitalizar e verificar o conteúdo de sua home page no Commerce, siga estas etapas.

1. Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).
1. No painel de navegação à esquerda, selecione **Páginas**.
1. Localize e selecione a home page para abri-la no editor de páginas.
1. Na barra de comandos, selecione **Verificar acessibilidade**. A página **Verificar Acessibilidade** é exibida.
1. Depois que a digitalização for concluída, revise o conteúdo do relatório.
1. Se houver falha nas verificações, selecione cada item de verificação com falha para expandi-lo, de forma que você possa exibir mais detalhes.
1. Para fechar o relatório depois de concluir a revisão, role até a parte inferior da página **Verificar acessibilidade** e selecione **OK**.

## <a name="additional-resources"></a>Recursos adicionais

[Modificar uma página de site existente](modify-existing-page.md)

[Adicionar uma nova página do site](add-new-page.md)

[Selecionar layouts de página](select-page-layouts.md)

[Gerenciar metadados de SEO](manage-seo-metadata.md)

[Salvar, visualizar, e publicar uma página](save-preview-publish-page.md)

[Enriquecer uma página de produto](enrich-product-page.md)

[Enriquecer uma página de aterrissagem da categoria](enrich-category-page.md)

[Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
