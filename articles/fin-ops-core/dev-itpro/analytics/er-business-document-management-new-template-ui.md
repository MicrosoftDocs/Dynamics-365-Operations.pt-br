---
title: Interface do usuário no estilo do Microsoft Office no Gerenciamento de documentos comerciais (contém vídeo)
description: Este tópico explica como usar a nova interface de usuário no recurso Gerenciamento de documentos comerciais da estrutura do relatório eletrônico (ER).
author: v-anamir
ms.date: 01/05/2022
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
ms.openlocfilehash: e33830e2147d92ad5ee53ad11da55a50613b8ef9
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8074732"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Interface do usuário no estilo do Microsoft Office no Gerenciamento de documentos comerciais

[!include [banner](../includes/banner.md)]

O Gerenciamento de documentos comerciais permite que os usuários empresariais editem modelos de documento comercial usando um serviço do Microsoft Office 365 ou o aplicativo da área de trabalho apropriado do Microsoft Office. As edições podem incluir alterações de design ou novas implantações, ou os usuários podem adicionar espaços reservados para incluir dados adicionais sem precisar alterar o código-fonte. Para obter mais informações sobre como trabalhar com o Gerenciamento de documentos comerciais, consulte [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md).

A nova interface de usuário (IU) está mais clara e mais confortável para uso. A área do **Documento comercial** mostra apenas os modelos que pertencem ao [provedor](general-electronic-reporting.md#Provider) [ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md) e que estão localizados na instância atual do Dynamics 365 Finance. Na IU anterior, a guia **Modelo** listava todos os modelos disponíveis para qualquer fornecedor. Ela também mostrava todos os modelos criados e editados por qualquer usuário com a mesma função.

Você pode usar o botão **Novo documento** no espaço de trabalho **Gerenciamento de documentos comerciais** para criar e editar um modelo em uma [configuração](general-electronic-reporting.md#Configuration) no formato de [Relatório Eletrônico (ER)](general-electronic-reporting.md), fornecido por outro provedor e localizado na atual instância do Finance, ou para carregar um novo modelo de uma pasta de trabalho do Excel. Além disso, na versão 10.0.25 e posterior, você pode usar o botão **Novo documento** para criar e editar um modelo em uma configuração de formato ER armazenada no [Repositório global](general-electronic-reporting.md#Repository).

Nos exemplos deste tópico, o provedor ativo é Contoso e você o usa para criar um modelo que se baseia em um modelo fornecido pela Microsoft. Outra opção é criar um modelo carregando seu próprio modelo no formato Excel.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWAVQg]

O vídeo [Criar um novo documento comercial usando o Gerenciamento de documentos comerciais](https://youtu.be/gAIYl-mM_pw) (mostrado acima) está incluído na [playlist do Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Disponibilizar a nova interface de usuário de documento no Gerenciamento de documentos comerciais

Para começar a usar a nova interface de usuário de documento no Gerenciamento de documentos comerciais, você deve executar o recurso **Experiência de interface de usuário semelhante à do Office para o Gerenciamento de documentos comerciais** no espaço de trabalho **Gerenciamento de recursos**.

Siga estas etapas a fim de ativar esse recurso para todas as entidades legais.

1. No espaço de trabalho **Gerenciamento de recursos**, na guia **Tudo**, selecione na lista o recurso **Experiência de interface de usuário semelhante à do Office para o Gerenciamento de documentos comerciais**.
2. Selecione **Habilitar agora** para ativar o recurso selecionado.
3. Atualize a página para acessar o novo recurso.

## <a name="add-or-activate-a-provider"></a>Adicionar ou ativar um provedor

Cada modelo de um documento comercial é armazenado em uma configuração de formato ER que é marcada como pertencente a um provedor de configuração específico. Quando você cria um novo modelo, uma nova configuração de formato ER é criada para contê-la. Portanto, um provedor deve ser identificado para essa configuração. O provedor ativo da estrutura ER é usado para essa finalidade. Se não houver um provedor em ER, você poderá criar um. Se não houver um provedor *ativo*, você poderá ativar um dos provedores existentes. Uma caixa de diálogo para adicionar ou ativar um provedor é aberta quando é necessário sempre que você começa a adicionar um novo modelo.

### <a name="add-a-new-provider"></a>Adicionar um novo provedor

Para criar um novo provedor, siga estas etapas na caixa de diálogo **Provedor de configuração**:

1.  Na guia **Escolher provedor de configuração**, no campo **Nome**, insira o nome do novo provedor.
2.  No campo **Endereço de Internet**, insira o endereço de Internet (URL) do novo provedor. 
3.  Selecione **OK**.

    ![Criar um novo provedor no Gerenciamento de documentos comerciais.](./media/bdm_create_provider.png)

O provedor adicionado será ativado automaticamente.

### <a name="activate-a-provider"></a>Ativar um provedor

Para ativar um provedor, siga estas etapas na caixa de diálogo **Provedor de configuração**:

1.  Na guia **Escolher provedor de configuração**, no campo **Provedor de configuração**, selecione o provedor.
2.  Selecione **OK**.

    ![Ativar um provedor no Gerenciamento de documentos comerciais.](./media/bdm_choose_provider.png)

O provedor selecionado será ativado.

> [!NOTE]
> Cada modelo de Gerenciamento de documentos comerciais está localizado em uma configuração de formato ER que se refere ao provedor como autor da configuração. Um provedor ativo é necessário para cada modelo.

## <a name="edit-a-template-that-is-owned-by-another-provider"></a>Editar um modelo que é de propriedade de outro provedor

Este exemplo mostra como usar o botão **Novo documento** no espaço de trabalho **Gerenciamento de documentos comerciais** para criar e editar um modelo em uma configuração no formato ER, fornecido por outro provedor e localizado na atual instância do Finance, ou para carregar um novo modelo de uma pasta de trabalho do Excel. Neste exemplo, o provedor ativo é a Contoso, que usa a configuração de formato ER fornecida pela Microsoft. Depois que você seleciona **Novo documento**, a guia **Selecionar** na página **Criar um novo modelo** mostra todos os modelos da instância do Finance atual que pertencem ao provedor atual e a outros fornecedores. Selecione um modelo para abri-lo. Você pode criar uma nova cópia editável do modelo. O modelo editado é armazenado em uma nova configuração de formato de ER que é gerada automaticamente.

1. No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.

    ![Espaço de trabalho Gerenciamento de documentos comerciais.](./media/BDM_overview_new_template1.png)

2. Na página **Criar um novo modelo**, na guia **Selecionar**, selecione o documento a ser usado como modelo e, depois, **Criar documento**.

    ![Caixa de diálogo Documentos comerciais.](./media/BDM_overview_new_template2.png)

3. Na nova caixa de diálogo, no campo **Título**, altere o título conforme necessário. O texto do título é usado para nomear a nova configuração de formato do ER criada automaticamente. A versão de rascunho dessa configuração (**Cópia do relatório de FTI do cliente (GER)**) conterá o modelo editado e será usada para executar esse formato de ER para o usuário atual. O modelo original da configuração base do formato de ER será usado para executar esse formato de ER para qualquer outro usuário.
4. No campo **Nome**, altere o nome da primeira revisão do modelo editável que será automaticamente criado.
5. No campo **Comentário**, atualize os comentários para a revisão do modelo editável que será automaticamente criado.
6. Selecione **OK** para confirmar o início do processo de edição.

    ![Caixa de diálogo Criação de documento.](./media/BDM_overview_new_template3.png)

## <a name="upload-a-template-that-uses-an-existing-excel-workbook"></a>Carregar um modelo que usa uma pasta de trabalho do Excel existente

Este exemplo mostra como usar o botão **Novo documento** no espaço de trabalho **Gerenciamento de documentos comerciais** para criar e editar um modelo em uma configuração no formato ER, com base na pasta de trabalho do Excel. Neste exemplo, o provedor ativo é a Contoso e você usa o [modelo de dados](er-overview-components.md#data-model-component) ER e as configurações de [mapeamento de modelo](er-overview-components.md#model-mapping-component) ER fornecidas pela Microsoft. Depois de selecionar **Novo documento**, selecione a guia **Carregar** na página **Criar um novo modelo**. Nela, você pode especificar os detalhes de um carregamento de pasta de trabalho do Excel. Após carregar a pasta de trabalho do Excel, ela é transformada em um modelo de documento comercial que é aberto para edição. O modelo editado será armazenado em uma nova configuração de formato de ER gerada automaticamente.

Siga estas etapas para fornecer as informações necessárias antes de carregar um modelo.

1. No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.
2. Na página **Criar um novo modelo**, na guia **Carregar**, na guia **Modelo**, selecione **Procurar** para localizar e selecionar o arquivo Excel a ser usado como modelo. Na seção **Modelo**, os campos **Título** e **Descrição** são preenchidos automaticamente. Eles especificam o nome e a descrição da nova configuração de formato ER que é criada automaticamente. Você pode editar esses campos, conforme necessário.
3. Na seção **Tipo de Documento**, no campo **Nome**, especifique o tipo de documento comercial. Esse valor será usado para pesquisar a fonte de dados correta (ou seja, a configuração do modelo de ER).

    ![Guia Modelo na guia Carregar da página Criar um novo modelo.](./media/BDM_overview_new_UI_import_21.jpg)

4. Na guia **Fonte de dados**, na FastTab **Filtro**, selecione **Aplicar filtro**. Na seção **Fonte de dados**, o campo **Nome** é preenchido automaticamente ou você pode selecionar um valor manualmente. Você pode usar o filtro para procurar o nome da fonte de dados apropriada por nome, descrição, código do país/região e tipo de documento comercial.

    ![Guia Fonte de dados na guia Carregar da página Criar um novo modelo.](./media/BDM_overview_new_UI_import_31.jpg)

    > [!NOTE]
    > A FastTab **Filtro** é usada para pesquisar a fonte de dados correta (ou seja, a configuração do modelo de ER). Você pode editar todos os campos de filtro para localizar a fonte de dados mais apropriada para o documento carregado.
    > 
    > As condições na FastTab **Filtro** são usadas como condições **OR**.

5. Na guia **Mapeamento**, selecione **Detecção automática**. O campo **Definição raiz** é preenchido automaticamente ou você pode selecionar um valor manualmente. Esta guia mostra o mapeamento final dos elementos do modelo e o modelo.

    ![Guia Mapeamento na guia Carregar da página Criar um novo modelo.](./media/BDM_overview_new_UI_import_41.jpg)

    > [!NOTE]
    > O mapeamento na seção **Estrutura de modelos** usa a correspondência total das etiquetas ou descrições da fonte de dados no idioma do usuário e no nome da célula no modelo.

6. Selecione **Criar documento** para confirmar se deseja criar um modelo e iniciar o processo de edição.

Para obter mais informações, consulte [Visão geral do Gerenciamento de documentos comerciais](er-business-document-management.md).

## <a name="upload-a-template-from-the-global-repository"></a>Carregar um modelo do Repositório global

Este exemplo mostra como usar o botão **Novo documento** no espaço de trabalho **Gerenciamento de documentos comerciais** para criar e editar um modelo em uma configuração no formato de ER, fornecido pela Microsoft e localizado no Repositório global. Neste exemplo, o provedor ativo é a Contoso, que usa a configuração de formato ER fornecida pela Microsoft. Depois que você seleciona **Novo documento**, a guia **Importar do repositório global** na página **Criar um novo modelo** mostra todos os modelos de documentos comerciais que estão armazenados no Repositório global, mas que estão ausentes na instância do Finance atual. Depois de selecionar um modelo, ele é importado do Repositório global para a instância do Finance atual para criar uma nova cópia editável. O modelo editado é armazenado em uma nova configuração de formato de ER que é gerada automaticamente.

1. No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.
2. Na página **Criar um novo modelo**, na guia **Importar do Repositório global**, selecione o documento a ser usado como modelo e, depois, **Criar documento**.

    ![Importar da guia Repositório global na página Criar um novo modelo.](./media/BDM_overview_new_template22.png)

3. Na caixa de mensagem, selecione **Sim** para confirmar que deseja importar o documento selecionado do Repositório global para a instância do Finance atual. Se você for solicitado para autorização, siga as instruções na tela.
4. Na nova caixa de diálogo, no campo **Título**, altere o título conforme necessário. O texto do título é usado para nomear a nova configuração de formato do ER criada automaticamente. A versão de rascunho dessa configuração (**Cópia da Nota de carta de cobrança (Excel)**) conterá o modelo editado e será usada para executar esse formato de ER para o usuário atual. O modelo original da configuração base do formato de ER será usado para executar esse formato de ER para qualquer outro usuário.
5. No campo **Nome**, altere o nome da primeira revisão do modelo editável que será automaticamente criado.
6. No campo **Comentário**, atualize os comentários para a revisão do modelo editável que será automaticamente criado.
7. Selecione **OK** para confirmar o início do processo de edição.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
