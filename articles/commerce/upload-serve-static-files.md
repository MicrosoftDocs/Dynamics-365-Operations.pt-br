---
title: Carregar e fornecer arquivos estáticos
description: Este tópico descreve como carregar um arquivo estático no assistente para construtor de sites do Microsoft Dynamics 365 Commerce e como criar uma URL personalizada e um nome de arquivo que podem ser usados para solicitar esse arquivo.
author: StuHarg
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d5f092042b3dda65b041ab2f25f7319dd8e158d1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801376"
---
# <a name="upload-and-serve-static-files"></a>Carregar e fornecer arquivos estáticos

[!include [banner](includes/banner.md)]

Este tópico descreve como carregar um arquivo estático no assistente para construtor de sites do Microsoft Dynamics 365 Commerce e como criar uma URL personalizada e um nome de arquivo que podem ser usados para solicitar esse arquivo.

Alguns conectores de terceiros exigem que um arquivo seja hospedado e fornecido usando o site de comércio eletrônico. Esses conectores esperam que o arquivo seja retornado por solicitações a um caminho de URL de retorno de chamada e nome de arquivo específicos. Portanto, este tópico explica como carregar e fornecer um arquivo estático que possui uma URL e um nome de arquivo definidos pelo usuário em um site de comércio eletrônico do Dynamics 365 Commerce.

## <a name="create-a-site-url-that-returns-a-static-file"></a>Criar uma URL de site que retorne um arquivo estático

Para criar uma URL de site que retorna um arquivo estático no assistente de criação de sites do Commerce, siga estas etapas:

1. Acesse a Biblioteca de Mídia do seu site e carregue o arquivo que deve ser fornecido por solicitações para a URL que você definirá. Se você já carregou o arquivo, pode ignorar essa etapa.
1. Vá para **URLs** do seu site.
1. Selecione **Novo \> Nova URL**.
1. Na caixa de diálogo **Nova URL**, selecione **Ativo de biblioteca de mídia**.
1. No campo **Caminho da URL**, insira o caminho da URL. Inclua o nome do arquivo no caminho.
1. Selecione **Avançar**. A Biblioteca de Mídia é aberta e mostra todos os ativos de mídia do tipo **documento** que foram carregados.
1. Selecione o arquivo que deve ser fornecido por solicitações à URL que você definiu na etapa 5.
1. Selecione **Salvar**.

Nesse momento, a URL que você criou está em estado de rascunho. O arquivo para o qual a URL aponta não será retornado até que você publique a URL. Antes de publicar a URL, você pode validar se ela retornará os dados corretos.

## <a name="validate-and-publish-a-url"></a>Validar e publicar uma URL

Para validar uma URL antes de publicá-la, siga as etapas a seguir.

1. Vá até **URLs** do seu site e selecione a URL para exibição.
2. No painel de propriedades à direita, abaixo do botão **Editar**, selecione o link de URL correto. Uma nova janela do navegador é aberta e você deve receber um erro 404.
3. Anexe a cadeia de caracteres de consulta **?preview=inprogress** à URL (por exemplo, `https://yoursite.com/callback.html?preview=inprogress`) e recarregue a página. O arquivo que você carregou na Biblioteca de Mídia deve ser retornado na resposta.

Depois de validar a URL, você pode publicá-la.

1. Vá até **URLs** do seu site e selecione a URL.
2. Selecione **Publicar** na barra de comandos.

## <a name="update-the-file-that-a-url-points-to"></a>Atualizar o arquivo para o qual uma URL aponta

Após a publicação de uma URL, você pode atualizá-la para que aponte para um arquivo diferente. Como alternativa, você pode atualizar a URL para que aponte para um tipo diferente de recurso, conforme descrito na próxima seção. Por exemplo, você pode apontar a URL para uma página interna ou um redirecionamento.

Para atualizar o arquivo para o qual uma URL aponta, siga estas etapas:

1. Vá até **URLs** do seu site e selecione a URL para atualização.
1. No painel de propriedades à direita, selecione **Editar**.
1. Em **Atribuição de URL**, selecione a caixa **Etapa 2** e, em seguida, selecione um novo documento na Biblioteca de Mídia.
1. Selecione **Aplicar**.

## <a name="update-the-asset-type-that-a-url-points-to"></a>Atualizar o tipo de ativo para o qual uma URL aponta

Você também pode atualizar uma URL para que aponte para um tipo diferente de ativo (recurso), como uma página interna ou um redirecionamento.

Para atualizar o tipo de ativo para o qual uma URL aponta, siga estas etapas:

1. Vá até **URLs** do seu site e selecione a URL para atualização.
1. No painel de propriedades à direita, selecione **Editar**.
1. Em **Atribuição de URL**, em **Etapa 1**, selecione um tipo de ativo diferente.
1. Selecione a caixa **Etapa 2** e, em seguida, selecione o novo ativo.
1. Selecione **Aplicar**.

## <a name="change-the-url-path"></a>Alterar o caminho da URL

Depois que uma URL é criada, seu caminho não pode ser alterado. Se você precisar alterar o caminho da URL que atende a um arquivo ou qualquer outro tipo de recurso, será necessário criar uma nova URL, mapeá-la para o arquivo existente ou outro recurso e, em seguida, cancelar a publicação e excluir a URL antiga.

Para alterar o caminho do URL, siga estas etapas:

1. Para criar uma nova URL e mapeá-la para o arquivo existente ou outro recurso, siga as instruções na seção [Criar uma URL de site que retorna um arquivo estático](#create-a-site-url-that-returns-a-static-file) anteriormente neste tópico.
1. Selecione a novo URL e selecione **Publicar** na barra de comandos. A nova URL é publicada.
1. Para cancelar a publicação da URL antiga, selecione-a e depois escolha **Cancelar publicação** na barra de comandos. Agora é possível excluir a URL antiga, se desejar.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do gerenciamento de ativos digitais](dam-overview.md)

[Carregar imagens](dam-upload-images.md)

[Carregar vídeos](dam-upload-video.md)

[Carregar arquivos diferentes de imagens e vídeos](dam-upload-files.md)

[Cortar imagens](dam-crop-images.md)

[Personalizar pontos focais da imagem](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]