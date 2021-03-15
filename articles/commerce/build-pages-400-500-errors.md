---
title: Criar páginas de resposta personalizadas para erros do código de status 4xx/5xx
description: Este tópico descreve como criar páginas de resposta personalizada para erros de código de status 4xx e 5xx usando as ferramentas de criação no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d21ce20b2c7ac8c656a718749dabd76f33893da8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991456"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Criar páginas de resposta personalizadas para erros do código de status 4xx/5xx


[!include [banner](includes/banner.md)]

Este tópico descreve como criar páginas de resposta personalizada para erros de código de status 4xx e 5xx usando as ferramentas de criação no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Se uma solicitação não tiver êxito, o servidor emite respostas de erro do código de status do HTTP. O código de status 404 é capturado e retornado se uma página não for encontrada e o código de status 500 é capturado e retornado se um erro de servidor ocorrer. No Dynamics 365 Commerce, os usuários do aplicativo podem criar as páginas de resposta de erro de código de status personalizado que são exibidas para usuários dessas respostas de erro de código de status.

## <a name="build-a-status-code-error-response-page"></a>Criar uma página de resposta de erro do código de status

Para começar a criar uma página de resposta de erro do código de status, siga essas etapas.

1. Em seu navegador preferido, conecte-se ao Dynamics 365 Commerce. 
1. Selecione o site no qual você deseja criar uma página de resposta de erro de código do status 4xx/5xx.

### <a name="build-the-template"></a>Criar o modelo

Para criar o modelo para a página de resposta de erro do código de status, siga essas etapas.

1. Vá para **Modelos**.
1. Selecione **Novo** para criar um modelo de página.
1. Na caixa de diálogo **Novo Modelo**, em **Nome do Modelo**, insira um nome para o novo modelo e selecione **OK**.
1. Crie modelo, com base na estrutura que deseja que a página de resposta de erro do código de status apareça.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo. 

### <a name="build-the-status-code-error-response-page"></a>Crie a página de resposta de erro do código de status

Para criar a página de resposta de erro do código de status, siga essas etapas.

1. Vá para **Páginas**.
1. Selecione **Novo** para criar uma página.
1. Na caixa de diálogo **Escolha um modelo**, selecione um modelo e, em **Nome da página**, insira um nome para a página da resposta do erro do código de status. Deixe o campo **URL da Página** em branco.
1. Crie a página.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

> [!NOTE]
> Você pode criar páginas de resposta de erro de código do status separada para erros de código do status 4xx e 5xx. Alternativamente, você pode usar a mesma página geral da resposta de erro do código de status para ambas as categorias de erro.

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a>Configurar um redirecionamento para a página de resposta de erro do código de status

Para configurar um redirecionamento para a página de resposta de erro do código de status, siga essas etapas.

1. Vá para **URLs \> Novo \> Novo alias**, e selecione a página de resposta de erro do código de status que você compilou anteriormente.
1. No campo **Alias**, **default-4xx** ou **default-5xx**, dependendo da página de resposta de erro do código de status para a qual você está configurando o redirecionamento. Essas alias devem ser publicados. Caso contrário, o redirecionamento não funcionará.
1. Selecione **OK** para enviar o link.

> [!NOTE]
> Se estiver usando uma única página de resposta de erro do código de status para ambas as categorias de erro, repita este procedimento para vincular uma apelido da outra categoria de erro na mesma página.

## <a name="additional-resources"></a>Recursos adicionais

[Trabalhar com modelos](work-with-templates.md)

[Adicionar uma nova página do site](add-new-page.md)

[Criar uma URL da página](create-page-url.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]