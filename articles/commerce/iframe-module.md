---
title: Módulo iFrame
description: Este artigo abrange o módulo iFrame e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 248da5132d1a2c6dcf8f246628f969c8a200b26c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269886"
---
# <a name="iframe-module"></a>Módulo iFrame

[!include [banner](includes/banner.md)]

Este artigo abrange o módulo iFrame e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.

Um módulo iFrame fornece um iframe (quadro embutido) que hospeda o conteúdo externo em um site. Por exemplo, ele pode ser usado para hospedar um vídeo do YouTube ou visualizador de arquivos de vídeo de PDF em qualquer página do site. 

Um módulo iframe requer uma URL de destino. Em seguida, ele hospeda o conteúdo da página de destino dentro de um elemento do **iFrame** de HTML. As URLs externas devem estar na lista de permissões pelas diretivas do CSP (política de segurança de conteúdo) do site. Para conteúdo iframe, as URLs devem ser permitidas usando a diretiva **ancestral do quadro**. Para obter mais informações, consulte [Gerenciar a Política de Segurança de Conteúdo (CSP)](manage-csp.md).

> [!NOTE]
> O módulo iframe está disponível na versão 10.0.13 do Dynamics 365 Commerce.

A imagem a seguir mostra exemplos de módulos iframe que demonstram vídeos externos nas páginas do site.

![Exemplo de módulos iframe que demonstram vídeos externos.](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a>Propriedades do módulo iframe

| Nome da propriedade             | Alíquota                 | Descrição |
|---------------------------|-----------------------|-------------|
| Título | Texto | O título do módulo. |
| URL de Destino | URL | A URL que está hospedada no módulo. |
| Altura | Número ou porcentagem | A altura do módulo, em pixels ou como uma porcentagem. Por exemplo, o valor **100** será tratado como um número de pixels e o valor **100%** será tratado como uma porcentagem. |
| Etiqueta aria | Texto | Uma etiqueta acessível por Rich Internet Applications (ARIA) pode ser definida para fins de acessibilidade. |

## <a name="add-an-iframe-module-to-a-page"></a>Adicionar um módulo iFrame a uma página

Para adicionar um módulo iFrame a uma página para mostrar um vídeo externo, siga estas etapas.

1. Acesse **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo modelo**, em **Nome do modelo**, insira **Modelo de marketing** e selecione **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Criar uma nova página**, em **Nome da página**, insira **Página de marketing** e, depois, selecione **Avançar**.
1. Em **Escolher um modelo**, selecione o **Modelo de marketing** que você criou e, depois, selecione **Avançar**.
1. Em **Escolher um layout**, selecione um layout de página (por exemplo, **Layout flexível**) e selecione **Avançar**.
1. Em **Revisar e concluir**, revise a configuração da página. Se você precisar editar as informações da página, selecione **Voltar**. Se as informações da página estiverem corretas, selecione **Criar página**. 
1. No slot **Principal** da nova página, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **iFrame** e, depois, **OK**.
1. No painel propriedades do módulo, defina o valor **URL de Destino** como uma URL externa para um vídeo.
1. Defina outras propriedades, como **Título** e **Altura**, conforme necessário.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
1. Acesse a página de marketing do site. Você verá que o vídeo é processado no módulo iframe.

> [!NOTE]
> Como o módulo iframe hospeda conteúdo externo, os autores do site devem garantir que o conteúdo hospedado em um módulo iframe não viole as políticas de restrição de conteúdo no respectivo mercado. Se houver uma violação de conteúdo em uma página que usa o módulo iframe, o autor do site poderá remover o módulo iframe abrindo a página no construtor de sites, selecionando **Remover módulo** no slot do módulo iframe e salvando e republicando a página.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Gerenciar a Política de Segurança de Conteúdo (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
