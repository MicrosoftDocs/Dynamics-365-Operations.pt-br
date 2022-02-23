---
title: Módulo de consentimento de cookie
description: Este tópico abrange os módulos de consentimento de cookie e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 60ce530575841c22355e4a14e8b0bbec6c0e35ab
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410088"
---
# <a name="cookie-consent-module"></a>Módulo de consentimento de cookie

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de consentimento de cookie e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

O módulo de consentimento de cookie solicita que os usuários do site forneçam explicitamente o consentimento para permitir cookies para qualquer recurso ou módulo que rastreie os cookies do navegador. O consentimento é necessário na primeira vez que um usuário navega por um site em uma nova sessão do navegador. Quando o consentimento é recebido, ele é rastreado e não é solicitado novamente. Para obter mais informações, consulte [Conformidade do cookie](cookie-compliance.md).

Se o consentimento de cookie do usuário do site não for recebido, os recursos ou módulos que exigirem esse consentimento não serão renderizados na página. Por exemplo, o módulo de finalização da compra, o módulo de compartilhamento social e o recurso de loja preferida exigem o consentimento de cookie e não serão renderizados se o consentimento do usuário do site não for recebido. 

Um módulo de consentimento de cookie pode ser configurado no fragmento de cabeçalho de uma página para que possa ser imposto quando ela for carregada. O módulo de consentimento de cookie deve ter uma mensagem clara informando o usuário sobre o uso de cookies no site e deve fornecer um link para a página de privacidade do site.

A ilustração a seguir destaca um exemplo de mensagem de consentimento de cookie com um link para a página de política de privacidade do site exibida no cabeçalho de uma página do site.
![Exemplo de um módulo de consentimento de cookie](./media/ecommerce-cookieconsent.png)

## <a name="cookie-consent-module-properties"></a>Propriedades do módulo de consentimento de cookie

| Nome da propriedade             | Alíquota                 | descrição |
|---------------------------|-----------------------|-------------|
| Rich Text                  | Rich Text | Especifica uma notificação de Rich Text para os usuários informando que o site usa cookies do navegador e que os usuários devem aceitar o uso de cookies para que o site seja totalmente funcional. |
| Links | URL | Um ou mais links podem ser adicionados à página de privacidade de um site que descreve os tipos de cookies que são rastreados nele. |

## <a name="add-a-cookie-consent-module-to-site-pages"></a>Adicionar um módulo de consentimento de cookie a páginas do site

Para adicionar com eficiência um módulo de consentimento de cookie a várias páginas do site, ele pode ser adicionado a um fragmento de cabeçalho de página compartilhado. Depois que o fragmento de cabeçalho for adicionado a todas as páginas do site, uma notificação de consentimento de cookie será automaticamente renderizada na primeira vez em que o usuário navegar até qualquer página do site.

Para obter mais informações sobre fragmentos e módulos de cabeçalho, consulte [Módulo de cabeçalho](author-header-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de cabeçalho](author-header-module.md) 

[Compatível com cookies](cookie-compliance.md)
