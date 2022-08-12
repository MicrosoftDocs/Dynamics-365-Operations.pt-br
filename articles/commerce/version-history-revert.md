---
title: Exibir histórico de versões para reverter páginas e fragmentos
description: Este artigo descreve como exibir o histórico de versões de uma página ou fragmento e reverter para uma versão mais antiga no construtor de sites do Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 06/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: fa2ecdd9d9bc7e60b279d850573b5caa6df2c659
ms.sourcegitcommit: 9cfccb5c260ce56a3457f9ea12e80f54ea55a3b4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183668"
---
# <a name="view-version-history-to-revert-pages-and-fragments"></a>Exibir histórico de versões para reverter páginas e fragmentos

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo descreve como exibir o histórico de versões de uma página ou fragmento e reverter para uma versão mais antiga no construtor de sites do Microsoft Dynamics 365 Commerce.

O construtor do site de comércio permite que você exiba o histórico de versões de uma página ou fragmento e reverta para uma versão anterior específica de um documento, se necessário. Enquanto um documento está aberto, você pode selecionar **Mostrar histórico** na barra de comandos para abrir uma caixa de diálogo do **Histórico de versões**, na qual a guia **Versão** lista o histórico de todas as versões e salvar atividades para a página ou o fragmento. Em seguida, você poderá selecionar uma versão anterior do documento na lista, visualizar e restaurá-la como a versão atual. A guia **Atividade** da caixa de diálogo lista todo o histórico de atividades do documento, incluindo todos os eventos de salvar, publicar e cancelar publicação.

> [!NOTE]
> Sempre que um autor do site faz alterações e seleciona **Edição concluída**, uma nova versão do documento é criada. 

Para exibir o histórico de versões de uma página ou fragmento e reverter para uma versão anterior, conclua as etapas a seguir.

1. No construtor de sites, abra a página ou o fragmento para o qual você quer exibir o histórico de versões.
1. Na barra de comandos, selecione **Mostrar histórico**.

    ![Botão Mostrar histórico.](./media/version-history-1.png)

1. Na caixa de diálogo **Histórico de versões**, guia **Versão**, selecione uma versão anterior do documento. O painel Propriedades à direita mostra uma miniatura da versão selecionada e informações sobre quem a modificou e quando.

    ![Visualização em lista do histórico de versões.](./media/version-history-2.png)

1. Para exibir uma visualização totalmente processada da versão do documento, selecione **Versão preliminar**. Para fechar a versão preliminar e retornar à caixa de diálogo **Histórico de versões**, selecione **Sair da versão preliminar**.
1. Para restaurar uma versão anterior de um documento, selecione-a na lista da guia **Versão** e selecione **Restaurar**. Uma caixa de mensagem **Restaurar versão \<version number\>** é exibida e solicita que você confirme a ação de restauração. 

    ![Botão Restaurar e caixa da mensagem de confirmação.](./media/version-history-3.png)

1. Para continuar com a ação de restaurar, selecione **Restaurar**. O criados de sites será atualizado e mostrará a versão restaurada da página ou do fragmento.
1. Para publicar a versão restaurada, selecione **Concluir edição** e **Publicar**.
