---
title: Considerações de otimização do mecanismo de pesquisa (SEO) para seu site
description: Este tópico abrange considerações de otimização do mecanismo de pesquisa (SEO) para seu site desde o desenvolvimento até a produção.
author: psimolin
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: df92aeae967bbf248b90dffc6bc2239a8d2959183acb9e9181bc344b9e3eff8d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716848"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Considerações de otimização do mecanismo de pesquisa (SEO) para seu site


[!include [banner](includes/banner.md)]

Este tópico abrange cada consideração de otimização do mecanismo de pesquisa (SEO) para seu site desde o desenvolvimento até a produção.

## <a name="a-site-that-is-under-development"></a>Um site que está em desenvolvimento

Quando um site estiver em desenvolvimento, todas as páginas do local deverão ter a meta de **NOINDEX** e **NOFOLLOW** , de forma que os mecanismos de pesquisa não indexem páginas e versões de desenvolvimento de armazenamento do site no cache. Para fazer essa configuração, você deve adicionar o módulo de marcas meta padrão ao modelo de página do site. As propriedades de marcas meta padrão ficarão disponíveis na seção de propriedades de SEO no editor de páginas. Você pode usar essas propriedades para gerenciar as marcas meta.

## <a name="soft-launch-of-a-site"></a>Inicialização flexível de um site

Durante uma "inicialização flexível", um site é disponibilizado para um público ou mercado limitado antes que ocorra o lançamento completo. Se não fizer uma inicialização flexível de seu site, deixe as meta marcas **NOINDEX** no lugar. Assim, você ajuda a garantir que a inicialização flexível permaneça restrita ao público limitado que você deseja alcançar.

## <a name="a-site-that-is-in-production"></a>Um site que está em produção

Quando um site estiver em produção, certifique-se de que todas as páginas do site estão marcadas corretamente. O Microsoft Dynamics 365 Commerce usa as informações inseridas em uma página para renderizar todas as informações de SEO nessa página. Os seguintes módulos fornecem essa funcionalidade: resumo da página da categoria, resumo da página da lista e resumo da página do produto.

Para otimizar a indexação do mecanismo de pesquisa, a estrutura de renderização usa as informações das propriedades de SEO configuradas no Dynamics 365 Commerce e as informações específicas do módulo. Para um site em produção, verifique se o arquivo robots.txt permite a indexação de todo o site e se ele contém links para o documento do mapa do site publicado. Você deve ativar a funcionalidade de geração do mapa de site em **Configurações de Site\> Mapas de site habilitados**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Configurações de SEO da página para visualização interna, público limitado e todos os públicos.

Como o Dynamics 365 Commerce oferece suporte de visualizações autenticadas "você vê como vai aparecer" (WYSIWYG) no construtor de página visual, os autores podem preparar o conteúdo da página sem se preocupar com o fato de as informações ficarem visíveis para os visitantes do site. Se uma página deve ser publicada, mas sua exposição deve ser limitada, ela deve ter a marca meta **NOINDEX** , de forma que não será indexada pelos mecanismos de pesquisa. Então, quando a página estiver pronta para todos os públicos, todos os metadados básicos de SEO deverão estar presentes, para maximizar a eficiência da indexação do mecanismo de pesquisa. Além disso, a marca meta **NOLIMIT** deverá ser removida.

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciar usuários e funções de comércio online](manage-ecommerce-users-roles.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)

[Gerenciar a política de segurança de conteúdo (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]