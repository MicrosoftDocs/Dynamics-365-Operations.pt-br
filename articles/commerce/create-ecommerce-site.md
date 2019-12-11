---
title: Criar um site de comércio eletrônico
description: Este tópico descreve as tarefas associadas à criação de um novo site comercial online no Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/31/2019
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
ms.openlocfilehash: fd87a51b73deae64867b0420c00db9fce7c79336
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697120"
---
# <a name="create-an-e-commerce-site"></a>Criar um site de comércio eletrônico

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico descreve as tarefas associadas à criação de um novo site comercial online no Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Para começar a desenvolver seu site comercial online, primeiro você deve estabelecer um novo site no ambiente de criação de site. Antes de criar um novo site, pelo menos uma loja online deve ser criada no Dynamics 365 Retail. 

## <a name="set-up-your-site"></a>Configurar seu site

Para configurar seu site, faça o seguinte.

1. No Microsoft Lifecycle Services (LCS), selecione o link do ambiente de criação do site. 
1. Na página inicial do ambiente de criação local, selecione **Novo site**.
1. Na caixa de diálogo **Novo site**, forneça as seguintes informações.

| Campo                               | Descrição |
|-------------------------------------|-------------|
| Nome do site                           | Insira o nome para exibição a ser usado para o site no ambiente de criação do site. Este nome é visível somente no ambiente de criação e não será exibido a clientes. |
| Grupo de segurança dos administradores de sistema | Especifique o grupo de segurança do Microsoft Azure Active Directory (Azure AD) que gerencia os usuários com a função de administrador de site nesse site. |
| Canal padrão (número da unidade operacional) | Selecione a loja online para a qual esse site servirá de loja da Web. Se desejar que seu site de comércio online dê suporte a vários armazenamentos online, você deve associar as lojas com o site nas **Configurações de site** depois de configurar o site. |
| Idioma padrão                            | Especifique o idioma padrão para esses armazenamento e marketing online. Uma loja online pode oferecer suporte a vários idiomas. Se desejar oferecer suporte a vários idiomas para esta armazenamento online ou outra loja online, você pode configurar o suporte em **Configurações de site** depois de configurá-lo.  |
| Domínio                              | Selecione um nome de domínio que servirá como o domínio para essa loja online. Se você não tiver configurado quaisquer domínios no LCS, você pode deixar esse campo em branco. Depois de seu domínio ser configurado no LCS, você deve adicioná-lo em sua loja online em **Configurações de site**.  |
| Caminho                              | Quando o site oferece suporte a mais de um idioma em determinado nome de domínio, use o campo de caminho para criar uma URL de site única para esse domínio e combinação de idioma. Se o idioma especificado no campo **Idioma padrão** é o único idioma para o qual você oferecerá suporte nesse domínio ou continuará a ser o idioma padrão após ter localizado seu site em idiomas adicionais, recomendamos que você deixe essa campo em branco. |


Depois que o site for criado, você pode verificar se está associado ao repositório online selecionando a guia **Produtos**. Você deve verificar a classificação do produto que foi atribuída à loja online. Você também pode usar o menu suspenso na parte superior esquerda da página para acessar os produtos alocados por categoria.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de loja online](online-store-overview.md)

[Implantar um novo site de comércio eletrônico](deploy-ecommerce-site.md)

[Associar um site online a um canal](associate-site-online-store.md)

[Configure seu nome de domínio](configure-your-domain-name.md)

[Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

[Habilitar detecção de lojas com base na localização](enable-store-detection.md)

[Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

[Visão geral da home page de Criação](authoring-home-overview.md)

[Adicionar uma nova página do site](add-new-page.md)
