---
title: Módulo iframe
description: Este tópico abrange o módulo iframe e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b7b5935a81377e0cb6acfc497eece6148bf1eeee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993360"
---
# <a name="iframe-module"></a>Módulo iframe

[!include [banner](includes/banner.md)]

Este tópico abrange o módulo iframe e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Um módulo iframe fornece um iframe (quadro embutido) que hospeda o conteúdo externo em um site. Por exemplo, ele pode ser usado para hospedar um vídeo do YouTube ou visualizador de arquivos de vídeo de PDF em qualquer página do site. 

Um módulo iframe requer uma URL de destino. Em seguida, ele hospeda o conteúdo da página de destino dentro de um elemento do **iframe** de HTML. As URLs externas devem estar na lista de permissões pelas diretivas do CSP (política de segurança de conteúdo) do site. Para conteúdo iframe, as URLs devem ser permitidas usando a diretiva **ancestral do quadro**. Para obter mais informações, consulte [Gerenciar a Política de Segurança de Conteúdo (CSP)](manage-csp.md).

> [!NOTE]
> O módulo iframe está disponível na versão 10.0.13 do Dynamics 365 Commerce.

A imagem a seguir mostra exemplos de módulos iframe que demonstram vídeos externos nas páginas do site.

![Exemplo de módulos iframe que demonstram vídeos externos](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a>Propriedades do módulo iframe

| Nome da propriedade             | Alíquota                 | descrição |
|---------------------------|-----------------------|-------------|
| Título | Texto | O título do módulo. |
| URL de Destino | URL | A URL que está hospedada no módulo. |
| Altura | Número ou porcentagem | A altura do módulo, em pixels ou como uma porcentagem. Por exemplo, o valor **100** será tratado como um número de pixels e o valor **100%** será tratado como uma porcentagem. |
| Etiqueta aria | Texto | Uma etiqueta acessível por Rich Internet Applications (ARIA) pode ser definida para fins de acessibilidade. |

## <a name="add-an-iframe-module-to-a-page"></a>Adicionar um módulo iframe a uma página

Para adicionar um módulo iframe a uma página para mostrar um vídeo externo, siga estas etapas.

1. Vá para **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira **Modelo de marketing** e selecione **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Vá para **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Escolher um modelo**, selecione o modelo **Modelo de marketing**. Em **Nome da página**, informe **página de Marketing** e, em seguida, selecione **OK**.
1. No slot **Principal** da nova página, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **iframe** e, depois, **OK**.
1. No painel propriedades do módulo, defina o valor **URL de Destino** como uma URL externa para um vídeo.
1. Defina outras propriedades, como **Título** e **Altura**, conforme necessário.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
1. Acesse a página de marketing do site. Você verá que o vídeo é processado no módulo iframe.
 
## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Gerenciar a Política de Segurança de Conteúdo (CSP)](manage-csp.md)
