---
title: Considerações de otimização do mecanismo de pesquisa (SEO) para seu site
description: Este artigo abrange considerações de otimização do mecanismo de pesquisa (SEO) para seu site desde o desenvolvimento até a produção.
author: josaw1
ms.date: 05/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: 77bbc04e849cf1cdeb7ce19226f43354635ddbe0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275610"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Considerações de otimização do mecanismo de pesquisa (SEO) para seu site


[!include [banner](includes/banner.md)]

Este artigo abrange considerações de otimização do mecanismo de pesquisa (SEO) para seu site desde o desenvolvimento até a produção.

## <a name="a-site-that-is-under-development"></a>Um site que está em desenvolvimento

Para garantir que os mecanismos de pesquisa não indexem um site em desenvolvimento, todas as páginas do site devem ter as metatags **noindex** e **nofollow**. Uma boa prática é criar um fragmento baseado no [Módulo de metamarcas](metatags-module.md) que contém a seguinte entrada de meta tag e garantir que o fragmento seja adicionado à seção HTML \<head\> de todos os modelos usado em seu site.

```html
<meta name="robots" content="noindex,nofollow" /> 
```

## <a name="soft-launch-of-a-site"></a>Inicialização flexível de um site

Durante uma "inicialização flexível", um site é disponibilizado para um público ou mercado limitado antes que ocorra o lançamento completo. Se não fizer uma inicialização flexível de seu site, deixe as meta marcas **noindex** no lugar. Assim, você ajuda a garantir que a inicialização flexível permaneça restrita ao público limitado que você deseja alcançar.

## <a name="a-site-that-is-in-production"></a>Um site que está em produção

Quando um site estiver em produção, certifique-se de que todas as páginas do site estão marcadas corretamente. O Microsoft Dynamics 365 Commerce usa as informações inseridas em uma página para renderizar todas as informações de SEO nessa página. Os seguintes módulos fornecem essa funcionalidade: resumo da página da categoria, resumo da página da lista e resumo da página do produto.

Para otimizar a indexação do mecanismo de pesquisa, a estrutura de renderização usa as informações das propriedades de SEO configuradas no Dynamics 365 Commerce e as informações específicas do módulo. Para um site em produção, verifique se o arquivo robots.txt permite a indexação de todo o site e se ele contém links para o documento do mapa do site publicado. Você deve ativar a funcionalidade de geração do mapa de site em **Configurações de Site\> Mapas de site habilitados**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Configurações de SEO da página para visualização interna, público limitado e todos os públicos.

Como o Dynamics 365 Commerce oferece suporte de visualizações autenticadas "você vê como vai aparecer" (WYSIWYG) no construtor de página visual, os autores podem preparar o conteúdo da página sem se preocupar com o fato de as informações ficarem visíveis para os visitantes do site. Se uma página deve ser publicada, mas sua exposição deve ser limitada, ela deve ter a marca meta **noindex** , de forma que não será indexada pelos mecanismos de pesquisa. Então, quando a página estiver pronta para todos os públicos, todos os metadados básicos de SEO deverão estar presentes, para maximizar a eficiência da indexação do mecanismo de pesquisa. Além disso, a marca meta **nolimit** deverá ser removida.

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciar usuários e funções de comércio online](manage-ecommerce-users-roles.md)

[Adicionar o código de script a páginas do site para oferecer suporte à telemetria](add-telemetry.md)

[Gerenciar a política de segurança de conteúdo (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
