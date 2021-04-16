---
title: Nova interface de usuário de documento no Gerenciamento de documentos comerciais
description: Este tópico fornece informações sobre como usar a nova interface de usuário de documento no recurso Gerenciamento de documentos comerciais do relatório eletrônico.
author: v-anamir
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4c430e21e3bf7f1c01c7b60c0bef58fb49c0c601
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748332"
---
# <a name="new-document-user-interface-in-business-document-management"></a>Nova interface do usuário do documento no Gerenciamento de documentos comerciais

[!include [banner](../includes/banner.md)]

O Gerenciamento de documentos comerciais permite que os usuários empresariais editem modelos de documento comercial usando um serviço do Microsoft 365 ou o aplicativo da área de trabalho apropriado do Microsoft Office. As edições podem incluir alterações de design ou novas implantações, ou os usuários podem adicionar espaços reservados para incluir dados adicionais sem precisar alterar o código-fonte. Para obter mais informações sobre como trabalhar com o Gerenciamento de documentos comerciais, consulte [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md).

A nova interface de usuário de documento está menos poluída e mais confortável de usar. A área **Documento comercial** mostra apenas os modelos disponíveis para o provedor atual.

O botão **Novo documento** permite que os usuários criem e editem um modelo em uma configuração de formato do ER (Relatório eletrônico) que é fornecido por outro provedor. No exemplo deste tópico, o provedor é a Microsoft.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Disponibilizar a nova interface de usuário de documento no Gerenciamento de documentos comerciais

Para começar a usar a nova interface de usuário de documento no Gerenciamento de documentos comerciais, você deve executar o recurso **Experiência de interface de usuário semelhante à do Office para o Gerenciamento de documentos comerciais** no espaço de trabalho **Gerenciamento de recursos**.

Siga estas etapas a fim de ativar esse recurso para todas as entidades legais.

1. No espaço de trabalho **Gerenciamento de recursos**, na guia **Novo**, selecione na lista o recurso **Experiência de interface de usuário semelhante à do Office para o Gerenciamento de documentos comerciais**.
2. Selecione **Habilitar agora** para ativar o recurso selecionado.
3. Atualize a página para acessar o novo recurso.

### <a name="edit-templates-that-are-owned-by-other-providers"></a>Editar modelos que são de propriedade de outros provedores

1. No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.

    ![Espaço de trabalho Gerenciamento de documentos comerciais](./media/BDM_overview_new_template1.png)

2. Na caixa de diálogo, selecione o documento a ser usado como um modelo e selecione **Criar documento**.

    ![Caixa de diálogo Documentos comerciais](./media/BDM_overview_new_template2.png)

3. Na nova caixa de diálogo, no campo **Título**, altere o título conforme necessário. O texto do título é usado para nomear a nova configuração de formato do ER criada automaticamente. A versão de rascunho dessa configuração (**Cópia do relatório de FTI do cliente (GER)**) conterá o modelo editado e será usada para executar esse formato de ER para o usuário atual. O modelo original da configuração base do formato de ER será usado para executar esse formato de ER para qualquer outro usuário.
4. No campo **Nome**, altere o nome da primeira revisão do modelo editável que será automaticamente criado.
5. No campo **Comentário**, atualize os comentários para a revisão do modelo editável que será automaticamente criado.
6. Selecione **OK** para confirmar o início do processo de edição.

    ![Caixa de diálogo Criação de documento](./media/BDM_overview_new_template3.png)

O botão **Novo documento** é usado para criar e editar um modelo em uma configuração de formato do ER que é fornecido por outro provedor. Neste exemplo, o provedor é a Microsoft. Ao selecionar **Novo documento**, você pode ver todos os modelos que pertencem ao provedor atual e a outros. Depois que você seleciona o modelo, ele é aberto para edição. O modelo editado será armazenado em uma nova configuração de formato de ER que é gerada automaticamente.

Para obter mais informações, consulte [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]