---
title: Editar guias e modelos de integração no Dynamics 365 Talent - Onboard
description: Este tópico explica como adicionar atividades e outras informações a guias e modelos de integração no Microsoft Dynamics 365 Talent - Onboard.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0f4c68acfe021e736c259e91a40ce7d43d401246
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551993"
---
# <a name="edit-onboarding-guides-and-templates-in-dynamics-365-talent---onboard"></a>Editar guias e modelos de integração no Dynamics 365 Talent - Onboard

[!include [banner](includes/banner.md)]

Depois de criar um guia ou modelo de integração no Microsoft Dynamics 365 Talent: Onboard, você deve adicionar uma introdução, atividades, contatos e recursos. O Onboard permite que você inclua conteúdo avançado nos seus guias de integração, incluindo:

- Vídeos do YouTube
- Apresentações do Microsoft Sway
- Aplicativos Microsoft PowerApps
- Vídeos do Microsoft Stream
- Formulários do Microsoft Forms
- Iframes que contém o conteúdo da Web

## <a name="edit-introductions-or-activities-imported-from-a-template"></a>Editar introduções ou atividades importados de um modelo

Se criar um guia de integração de um modelo ou importar atividades de um modelo para outro, você verá um botão **Bloquear** nas atividades importadas. Elas são chamadas *atividades gerenciadas*.

[![Atividades gerenciadas](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)

Ao selecionar uma atividade gerenciada, você poderá ver o modelo de origem na parte superior da atividade.

[![Origem da atividade gerenciada](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)

Se você editar uma atividade em um modelo, o Onboard enviará as alterações para todos os modelos e guias não enviados que são baseados nesse modelo. Se você selecionar um guia não enviado com base em um modelo editado e depois selecionar a guia **Atividades**, será exibido um aviso informando que seu guia foi alterado. Para ignorar a notificação, selecione **OK**. 

[![Alterar notificação](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)

Você verá um ponto preto próximo às atividades atualizadas.

[![Atividade alterada](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)

Você não pode editar atividades gerenciadas fora do modelo original, exceto para adicionar um destinatário, data de vencimento ou outras informações na seção direita da atividade.

Se quiser editar uma atividade gerenciada ou se não quiser que uma atividade receba atualizações do modelo de origem, selecione o botão **Bloquear** dessa atividade. O botão **Bloquear** desaparecerá. A atividade não será gerenciada por método original, e não receberá mais atualizações desse modelo. As atualizações feitas a uma atividade não afetarão o modelo original.

Se você excluir uma atividade de um guia e enviar alterações do modelo desse guia, a atividade permanecerá excluída no guia.

> [!NOTE]
> Os contatos e recursos não são gerenciados por modelos. Além disso, as seções não são gerenciadas; portanto, se você adicionar ou editar uma seção em um modelo, as alterações não serão enviadas a nenhum guia ou modelo que use esse modelo.
> 
> Se você adicionar novas atividades a um modelo, as novas atividades serão enviadas aos guias e aos modelos baseados nesse modelo, e as novas atividades serão exibidas na parte superior.

## <a name="import-activities-from-another-template"></a>Importar atividades de outro modelo

Você pode importar atividades de um ou mais modelos em um guia ou em um modelo.

1. Selecionar o guia ou modelo que deseja editar.

2. Selecione a guia **Atividades**.

3. Selecione a guia **Importar** na seção à direita.

   [![Importar atividades](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)

4. Para visualizar as tarefas em uma nova guia de seu navegador, selecione o botão **Abrir em nova guia** em qualquer modelo.

   [![Importar atividades](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)

5. Arraste e solte o modelo desejado para o local do modelo de guia em que deseja que as atividades apareçam. Continue editando seu guia ou modelo.

Atividades importadas conterão um botão **Bloquear** , que indica que as atividades são gerenciadas pelo modelo que você importou. Quando você fizer alterações no modelo importado, essas atividades serão atualizadas no modelo para o qual você importou. Contudo, as alterações não serão enviadas automaticamente a nenhum guia criado do modelo importado.

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a>Enviar alterações de um modelo para outros modelos ou guias

Se você editar um modelo que contém as atividades que são usadas em outros modelos ou guias, você deve enviar as alterações, se quiser que elas apareçam em outros guias ou modelos.

Se você não tiver certeza se as atividades do seu modelo são usadas em outros modelos ou guias, selecione a guia **Usado em** para exibir onde as atividades serão exibidas.

   [![Exibir atividades de guias e modelos usados em](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)

Para enviar as alterações:

1. Salve suas alterações selecionando o botão **Salvar**. Se você não fizer isso, será solicitado que você salve as alterações na próxima etapa.

2. Selecione **Enviar estas alterações**.

   
## <a name="add-or-edit-an-introduction"></a>Adicionar ou editar uma introdução

1. Na guia **Introdução** , digite um título para o guia e uma mensagem de abertura. Para usar o texto de exemplo, selecione **Usar esta mensagem**.

    [![Guia Introdução em um modelo do Onboard](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)

2. Use os botões de formatação para chamar o texto, conforme necessário, ou para adicionar links ou imagens.
3. Selecione **Salvar** para salvar seu trabalho.

## <a name="add-or-edit-activities"></a>Adicionar ou editar atividades

1. Na guia **Atividades** , arraste os itens da direita para a área de edição.
2. Para organizar seu guia em seções, arraste o item **Nova seção** para a área de edição e informe um nome e uma descrição opcional para a seção.

    ![[Adicionando uma nova seção a um guia ou modelo de integração](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. Para adicionar atividades para sua nova contratação concluir, arraste o item **Nova atividade** para a área de edição e insira um nome e descrição para a atividade.

    ![[Adicionando uma nova atividade a um guia ou modelo de integração](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. Adicionar o conteúdo avançado ao seu guia de integração:

    - Para adicionar um vídeo do YouTube, arraste o item do **YouTube** para a área de edição, informe um nome e descrição para a atividade e insira o URL do vídeo do YouTube.
    - Para adicionar uma apresentação ou boletim, arraste o item **Sway** para a área de edição, informe um nome e descrição da atividade e informe o URL incorporado para a apresentação ou boletim Sway.
    - Para adicionar um aplicativo do PowerApps, arraste o item **PowerApps** para a área de edição, insira um nome e uma descrição para a atividade e selecione o aplicativo do PowerApps ou insira a ID do aplicativo do PowerApps.
    - Para adicionar um vídeo do Microsoft Stream, arraste o item do **Microsoft Stream** para a área de edição, informe um nome e descrição para a atividade e insira o URL do vídeo do Microsoft Stream.
    - Para adicionar um form do Microsoft Forms, arraste o item do **Microsoft Forms** para a área de edição, informe um nome e uma descrição da atividade, informe o URL do formulário do Microsoft Forms e especifique o tamanho da área da tela.
    - Para adicionar um iframe que contém conteúdo da Web, arraste o item de **Conteúdo da Web (iframe)** para a área de edição, informe um nome e uma descrição para a atividade, informe o URL do conteúdo da Web e especifique o tamanho da área da tela.

    ![[Adicionando conteúdo avançado a um guia ou modelo de integração](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. Opcional: na área à direita de cada atividade, atribua a atividade a uma pessoa ou função específica, adicione uma data de vencimento e pessoa de contato e atribua uma cor de categoria. Ao atribuir uma atividade a uma pessoa ou função, uma tarefa será criada para cada pessoa. Esta tarefa aparece no menu **Tarefas** no Onboard.

    [![Atribuindo uma atividade a um guia ou modelo de integração](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)

3. Selecione **Salvar** para salvar seu trabalho.

Para excluir uma atividade ou seção, selecione o botão **Excluir** (o símbolo de lixeira) no canto superior direito da atividade ou da seção.

Para reorganizar atividades e seções, arraste-as para um novo local.

## <a name="add-or-edit-contacts"></a>Adicionar ou editar contatos

Você pode adicionar pessoas de contato que podem ajudar sua nova contratação a ter sucesso desde o primeiro dia. Esses contatos podem ser recrutadores, colegas de equipe, companheiros de integração, mentores, administradores e equipe de suporte de TI.

1. Na guia **Contatos**, selecione **Novo contato**.
2. Na caixa de diálogo **Adicionar membro da equipe**, informe o nome da pessoa de contato ou o endereço de email, informe uma descrição curta que explica como a pessoa de contato pode ajudar a nova contratação e selecione **Adicionar**. 

    ![[Adicionando contatos a um guia ou modelo de integração](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    Se preferir, você pode selecionar um ou mais contatos em **Sugestões**.

3. Selecione **Salvar** para salvar seu trabalho.

Para excluir um contato, selecione o botão **Excluir** (o símbolo de lixeira) à direita do contato.

Para editar um contato, selecione o botão **Editar** (o símbolo de lápis) à direita do contato.

## <a name="add-or-edit-resources"></a>Adicionar ou editar recursos

Você pode adicionar arquivos, mapas e links úteis à seção **Recursos** de seu guia de integração.

1. Na guia **Recursos**, selecione **Novo recurso**.
2. Siga uma destas etapas:

    - Para adicionar um arquivo, selecione a guia **Arquivo** e arraste o arquivo para a área designada. (Se preferir, clique em qualquer lugar nessa área para procurar o arquivo em seu computador ou selecione **Procurar OneDrive**). Informe um nome para o arquivo e selecione **Adicionar**.
    - Para adicionar um link, selecione a guia **Link**, informe um nome e endereço para o link e selecione **Adicionar**.
    - Para adicionar um mapa, seleciona a guia **Mapa**, informe o nome e endereço do mapa e selecione **Adicionar**. O Onboard incluirá um mapa do endereço que você especificar.

    ![[Adicionando um recurso a um guia ou modelo de integração](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. Selecione **Salvar** para salvar seu trabalho.

Para excluir um recurso, selecione o botão **Excluir** (o símbolo de lixeira) à direita do recurso.

Para editar um contato, selecione o botão **Editar** (o símbolo de lápis) à direita do recurso.

## <a name="next-steps"></a>Próximas etapas

- [Compartilhar conteúdo com outros contribuintes](./onboard-share-template.md)
- [Exibir o status de tarefas e da integração de funcionários](./onboard-view-status.md)
- [Criar equipes de contratação no Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Consulte também

- [Experimentar ou comprar o Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Novidades](./whats-new.md)
- [Notas de versão](https://docs.microsoft.com/business-applications-release-notes/index)
- [Obter suporte](./talent-support.md)
