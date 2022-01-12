---
title: Interface do usuário no estilo do Microsoft Office no Gerenciamento de documentos comerciais (contém vídeo)
description: Este tópico explica como usar a nova interface de usuário no recurso Gerenciamento de documentos comerciais da estrutura do relatório eletrônico (ER).
author: v-anamir
ms.date: 04/12/2021
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
ms.openlocfilehash: b0c481e73daf74803d3582e4089e76dcd383e8a4
ms.sourcegitcommit: ef0dd4245fc499907ffe00e2a32f59a6cd96e45d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2021
ms.locfileid: "7937547"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Interface do usuário no estilo do Microsoft Office no Gerenciamento de documentos comerciais

[!include [banner](../includes/banner.md)]

O Gerenciamento de documentos comerciais permite que os usuários empresariais editem modelos de documento comercial usando um serviço do Microsoft 365 ou o aplicativo da área de trabalho apropriado do Microsoft Office. As edições podem incluir alterações de design ou novas implantações, ou os usuários podem adicionar espaços reservados para incluir dados adicionais sem precisar alterar o código-fonte. Para obter mais informações sobre como trabalhar com o Gerenciamento de documentos comerciais, consulte [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md).

A nova interface de usuário (IU) está mais clara e mais confortável para uso. A área **Documento comercial** mostra apenas os modelos disponíveis para o provedor atual. Na interface do usuário anterior, a guia **Modelo** listava todos os modelos disponíveis para qualquer fornecedor. Ela também mostrava todos os modelos criados e editados por qualquer usuário com a mesma função.

Você pode usar o botão **Novo documento** para criar e editar um modelo em uma configuração de formato do ER (Relatório Eletrônico) que é fornecido por outro provedor. No exemplo deste tópico, o provedor é a Microsoft. Outra opção é criar um modelo carregando seu próprio modelo no formato Excel.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

O vídeo [Criar um novo documento comercial usando o Gerenciamento de documentos comerciais](https://youtu.be/gAIYl-mM_pw) (mostrado acima) está incluído na [playlist do Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Disponibilizar a nova interface de usuário de documento no Gerenciamento de documentos comerciais

Para começar a usar a nova interface de usuário de documento no Gerenciamento de documentos comerciais, você deve executar o recurso **Experiência de interface de usuário semelhante à do Office para o Gerenciamento de documentos comerciais** no espaço de trabalho **Gerenciamento de recursos**.

Siga estas etapas a fim de ativar esse recurso para todas as entidades legais.

1. No espaço de trabalho **Gerenciamento de recursos**, na guia **Tudo**, selecione na lista o recurso **Experiência de interface de usuário semelhante à do Office para o Gerenciamento de documentos comerciais**.
2. Selecione **Habilitar agora** para ativar o recurso selecionado.
3. Atualize a página para acessar o novo recurso.

## <a name="edit-templates-that-are-owned-by-other-providers"></a>Editar modelos que são de propriedade de outros provedores

1. No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.

    ![Espaço de trabalho Gerenciamento de documentos comerciais.](./media/BDM_overview_new_template1.png)

2. Na guia **Selecionar**, selecione o documento a ser usado como um modelo e, depois, **Criar documento**.

    ![Caixa de diálogo Documentos comerciais.](./media/BDM_overview_new_template2.png)

3. Na nova caixa de diálogo, no campo **Título**, altere o título conforme necessário. O texto do título é usado para nomear a nova configuração de formato do ER criada automaticamente. A versão de rascunho dessa configuração (**Cópia do relatório de FTI do cliente (GER)**) conterá o modelo editado e será usada para executar esse formato de ER para o usuário atual. O modelo original da configuração base do formato de ER será usado para executar esse formato de ER para qualquer outro usuário.
4. No campo **Nome**, altere o nome da primeira revisão do modelo editável que será automaticamente criado.
5. No campo **Comentário**, atualize os comentários para a revisão do modelo editável que será automaticamente criado.
6. Selecione **OK** para confirmar o início do processo de edição.

    ![Caixa de diálogo Criação de documento.](./media/BDM_overview_new_template3.png)

O botão **Novo documento** é usado para criar e editar um modelo em uma configuração de formato do ER que é fornecido por outro provedor. Neste exemplo, o provedor é a Microsoft. Ao selecionar **Novo documento**, você pode ver todos os modelos que pertencem ao provedor atual e a outros. Depois que você seleciona o modelo, ele é aberto para edição. O modelo editado será armazenado em uma nova configuração de formato de ER que é gerada automaticamente.

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a>Carregar um modelo que usa um formato Excel existente
Siga estas etapas para fornecer as informações necessárias antes de carregar um modelo.

1. No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.

    ![Espaço de trabalho Gerenciamento de documentos comerciais.](./media/BDM_overview_new_template1.png)
    
2. Na página **Criar um novo modelo**, na guia **Carregar**, na guia **Modelo**, selecione **Procurar** para localizar e selecionar o arquivo Excel a ser usado como modelo. Na seção **Modelo**, os campos **Título** e **Descrição** são preenchidos automaticamente. Eles especificam o nome e a descrição da nova configuração de formato ER que é criada automaticamente. Você pode editar esses campos, conforme necessário.
3. Na seção **Tipo de Documento**, no campo **Nome**, especifique o tipo de documento comercial. Esse valor será usado para pesquisar a fonte de dados correta (ou seja, a configuração do modelo de ER).

    ![Guia Modelo.](./media/BDM_overview_new_UI_import_21.jpg)

4. Na guia **Fonte de dados**, na FastTab **Filtro**, selecione **Aplicar filtro**. Na seção **Fonte de dados**, o campo **Nome** é preenchido automaticamente ou você pode selecionar um valor manualmente. Você pode usar o filtro para procurar o nome da fonte de dados apropriada por nome, descrição, código do país/região e tipo de documento comercial.

    ![Guia Fonte de dados.](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > A FastTab **Filtro** é usada para pesquisar a fonte de dados correta (ou seja, a configuração do modelo de ER). Você pode editar todos os campos de filtro para localizar a fonte de dados mais apropriada para o documento carregado.
    > 
    > As condições na FastTab **Filtro** são usadas como condições **OR**.
    
5. Na guia **Mapeamento**, selecione **Detecção automática**. O campo **Definição raiz** é preenchido automaticamente ou você pode selecionar um valor manualmente. Esta guia mostra o mapeamento final dos elementos do modelo e o modelo.

    ![Guia Mapeamento.](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > O mapeamento na seção **Estrutura de modelos** usa a correspondência total das etiquetas ou descrições da fonte de dados no idioma do usuário e no nome da célula no modelo.

6. Selecione **Criar documento** para confirmar se deseja criar um modelo e iniciar o processo de edição.

Para obter mais informações, consulte [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md).

Se não houver um provedor de relatórios eletrônicos, você poderá criar um. Se não houver um provedor ativo, você poderá optar por ativar um.

- Para criar um provedor, altere o nome do provedor no campo **Nome**, atualize o endereço na Internet do novo provedor no campo **Endereço na Internet** e selecione **OK** para confirmar.

    ![Criar novo provedor em BDM.](./media/bdm_create_provider.png)
    
- Para ativar o provedor existente, escolha o nome do provedor no campo **Provedor de configuração** e selecione **OK** para definir o provedor como ativo.

    ![Ativar provedor em BDM.](./media/bdm_choose_provider.png)

> [!NOTE]
> Cada modelo de BDM se refere ao fornecedor como o autor da configuração. É por isso que um provedor ativo é necessário para o modelo.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
