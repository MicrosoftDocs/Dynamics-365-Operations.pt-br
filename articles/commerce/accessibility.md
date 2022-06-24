---
title: Recursos e funcionalidades de acessibilidade
description: Este artigo fornece informações sobre os recursos de acessibilidade e funcionalidades no Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8f4e73ebaf6dc3fc6eb97f69df8545c9ab9fa9df
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853893"
---
# <a name="accessibility-features-and-capabilities"></a>Recursos e funcionalidades de acessibilidade

[!include [banner](includes/banner.md)]

Este artigo fornece informações sobre os recursos de acessibilidade e funcionalidades no Microsoft Dynamics 365 Commerce.

Recursos de acessibilidade e funcionalidades fornecem os meios funcionais para todos os usuários acessarem e executarem ações para que possam atingir suas metas. Essa variedade de usuários pode exigir ferramentas de assistência para audição, visão, mobilidade ou neurodiversidade.

Vários recursos do Dynamics 365 Commerce permitem que você crie seu site para que ele inclua funcionalidades auxiliares. Ao criar o site, você deve considerar as áreas de funcionalidade de acessibilidade mencionadas no [Microsoft Accessibility Center](https://www.microsoft.com/accessibility). 

Este artigo descreve algumas áreas adicionais de funcionalidade de acessibilidade que você deve considerar ao usar Dynamics 365 Commerce.

## <a name="image-alt-text"></a>Imagem de texto alt

O Dynamics 365 Commerce tem um sistema de gerenciamento de ativos digitais interno para rastrear os ativos de imagem e vídeo usados no site. Legendas de imagem, descrições e texto alt podem ser adicionados no painel de propriedades para uma imagem quando for selecionada ou carregada.

## <a name="video-accessibility"></a>Acessibilidade de vídeo

O sistema de gerenciamento de ativos digitais Dynamics 365 Commerce oferece suporte a vários recursos de acessibilidade para conteúdo de vídeo. A tabela a seguir lista alguns exemplos.

| Recurso de vídeo               | Descrição |
|-----------------------------|-------------|
| Legendagem oculta (CC)      | Texto que pode ser mostrado para os elementos descritivos de áudio e áudio de um vídeo, para ajudar os usuários surdos ou com dificuldades auditivas |
| Subtítulos                   | Arquivos de legenda que mostram o texto de pistas de contexto ou diálogos na tela |
| Transcrições de áudio           | Um transcrição textual de palavras faladas que é gerado pelo áudio de um ativo de vídeo |
| Áudio descritivo           | Um canal de áudio não primário que descreve o conteúdo ou contexto que está ocorrendo na tela |
| Portão de idade mínima            | Um atributo que pode armazenar a idade mínima que um telespectador deve ter para ver um vídeo (apenas metadados) |

### <a name="configure-video-accessibility-elements"></a>Configurar elementos de acessibilidade de vídeo

Na seção **Biblioteca de Mídia** do Commerce do site, você pode carregar ativos de vídeo que tenham arquivos separados para legendas ocultas, áudio regular e áudio descritivo. As legendas ocultas também podem ser gerados automaticamente quando um ativo de vídeo é carregado.

#### <a name="generate-or-upload-closed-caption-files-during-video-asset-upload"></a>Gerar ou carregar arquivos de legendas ocultas durante o carregamento de ativos de vídeo

Para que um arquivo de legendas ocultas seja gerado automaticamente quando você carregar um vídeo, siga esta etapa.

- Na caixa de diálogo **Carregar ativo**, selecione **Gerar automaticamente legendas ocultas**. Se você estiver gerando um arquivo de legendas ocultas, o seletor de arquivo para arquivos de legendas ocultas não estará disponível na caixa de diálogo.

Para carregar manualmente um arquivo de legendas ocultas quando você carregar um vídeo, siga esta etapa.

- Na caixa de diálogo **Carregar ativo**, desmarque **Gerar automaticamente legendas ocultas**.

Para carregar arquivos de áudio ou descritivos regulares para o vídeo, use o seletor de arquivos na caixa de diálogo **Carregar ativo**.

> [!NOTE]
> Legendas ocultas, áudio regular e ativos de áudio descritivos também podem ser adicionados depois que um ativo de vídeo for carregado. Acesse **Biblioteca de Mídia**, selecione o ativo de vídeo e depois **Editar** para finalizar a compra. Em seguida, no painel de propriedades do ativo de vídeo, carregue os ativos adicionais.

#### <a name="edit-cc-and-audio-transcript-files"></a>Editar arquivos de transcrição de áudio e CC

Os arquivos de transcrição de CC e de áudio podem ser editados diretamente na ferramenta de criação. A reprodução de vídeo está disponível durante a edição.

Para editar os arquivos de transcrição de áudio e de CC, siga estas etapas.

1. Acesse **Biblioteca de Mídia** e selecione o nome do arquivo do ativo do vídeo. O editor de conteúdo de transcrição e legendas ocultas é exibido.
1. Selecione **Editar**.
1. Edite as legendas ocultas ou o texto da transcrição.
1. Quando terminar, selecione **Salvar** e depois **Concluir a edição**.
1. Quando estiver pronto para publicar, selecione **Publicar**.

#### <a name="set-the-minimum-age-attribute"></a>Definir o atributo de idade mínima

Um atributo de metadados de **Idade mínima** pode ser associado a ativos de vídeo.

Para definir o atributo de **Idade mínima** de um ativo de vídeo, siga estas etapas.

1. Acesse **Biblioteca de Mídia** e selecione o ativo de vídeo.
1. Selecione **Editar**.
1. No painel de propriedades do ativo de vídeo, defina o atributo **Idade mínima**.

> [!NOTE]
> O painel de propriedades é usado somente para definir e armazenar o valor do atributo de metadados. Os módulos personalizados devem ser criados para usar esse atributo para a execução da reprodução.

## <a name="additional-resources"></a>Recursos adicionais

[Acessibilidade em formulários, produtos e controles](/dynamics365/unified-operations/dev-itpro/user-interface/enable-accessibility)

[Microsoft Accessibility Center](https://www.microsoft.com/accessibility)

[Central de acessibilidade do Dynamics 365](/dynamics365/get-started/accessibility/index)

[Visão geral de conformidade](compliance-overview.md)

[Compatível com cookies](cookie-compliance.md)

[Adicionar página de política de privacidade](add-privacy-page.md)

[Substitua os IDs de usuário associados às alterações de conteúdo controladas](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]