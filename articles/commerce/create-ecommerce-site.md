---
title: Criar um site de comércio eletrônico
description: Este tópico descreve as etapas e informações necessárias para criar um novo site de comércio eletrônico no assistente para criação de sites do Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7d552f29fd8f52b512a7c21b36b0a814cac50646
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517175"
---
# <a name="create-an-e-commerce-site"></a>Criar um site de comércio eletrônico

[!include [banner](includes/banner.md)]

Este tópico descreve as etapas e informações necessárias para criar um novo site de comércio eletrônico no assistente para criação de sites do Dynamics 365 Commerce.

Quando você licenciar os recursos do Dynamics 365 Commerce, o construtor de sites será provisionado com um site de início que você poderá usar como base para seu próprio site. Mas se você quiser começar do zero ou estabelecer um segundo site, precisará estabelecer um novo site no ambiente de criação de sites. 

## <a name="set-up-your-site"></a>Configurar seu site

Para configurar seu site, faça o seguinte.

1. Abra o ambiente do assistente para criação de sites. Você pode encontrar um link para o assistente de criação de sites no Microsoft Lifecycle Services (LCS), na página de recursos do ambiente do Commerce.
1. Na página inicial do ambiente de criação local, selecione **Novo site**.
1. Na caixa de diálogo **Novo site**, forneça as seguintes informações.

| Campo                               | Descrição |
|-------------------------------------|-------------|
| Nome do site                           | Insira o nome para exibição a ser usado para o site no ambiente de criação do site. Este nome é visível somente no ambiente de criação e não será exibido a clientes. |
| Grupo de segurança dos administradores de sistema | Especifique o grupo de segurança do Microsoft Azure Active Directory (Azure AD) que gerencia os usuários com a função de administrador de site nesse site. |
| Canal padrão (número da unidade operacional) | Selecione a loja online para a qual esse site servirá de loja da Web. Se desejar que o site de comércio eletrônico dê suporte a várias lojas online, associe as lojas ao site em **Configurações de site** depois de configurar o site. |
| Idioma padrão                            | Especifique o idioma padrão para esses armazenamento e marketing online. Uma loja online pode oferecer suporte a vários idiomas. Se desejar oferecer suporte a vários idiomas para esta armazenamento online ou outra loja online, você pode configurar o suporte em **Configurações de site** depois de configurá-lo.  |
| Domínio                              | Selecione um nome de domínio que servirá como o domínio para essa loja online. Se você não tiver configurado quaisquer domínios no LCS, você pode deixar esse campo em branco. Depois de seu domínio ser configurado no LCS, você deve adicioná-lo em sua loja online em **Configurações de site**.  |
| Caminho                              | Quando o site oferece suporte a mais de um idioma em determinado nome de domínio, use o campo de caminho para criar uma URL de site única para esse domínio e combinação de idioma. Se o idioma especificado no campo **Idioma padrão** é o único idioma para o qual você oferecerá suporte nesse domínio ou continuará a ser o idioma padrão após ter localizado seu site em idiomas adicionais, recomendamos que você deixe essa campo em branco. |


Depois que o site for criado, você pode verificar se está associado ao repositório online selecionando a guia **Produtos**. Você deve verificar a classificação do produto que foi atribuída à loja online. Você também pode usar o menu suspenso na parte superior esquerda da página para acessar os produtos alocados por categoria.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar seu nome de domínio](configure-your-domain-name.md)

[Implantar um novo locatário de comércio eletrônico](deploy-ecommerce-site.md)

[Associar um site do Dynamics 365 Commerce a um canal online](associate-site-online-store.md)

[Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

[Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

[Configurar um locatário B2C do Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-B2C-tenants.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]