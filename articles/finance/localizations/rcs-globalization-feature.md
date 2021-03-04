---
title: Regulatory Configuration Service (RCS) — Recursos de globalização
description: Este tópico explica como usar o Microsoft Regulatory Configuration Services (RCS) e o Repositório global para criar e usar Recursos de globalização.
author: JaneA07
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: ae46dab5250fbe8096f43e420cb7ef33a5862af0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440259"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a>Regulatory Configuration Service (RCS) — Recursos de globalização

[!include [banner](../includes/banner.md)]

Você pode usar o Microsoft Regulatory Configuration Services (RCS) para criar um Recurso de globalização que pode ser usado nos Serviços de globalização, como um serviço de faturamento eletrônico. O RCS permite executar estas tarefas:

- Definir componentes relacionados de um recurso.
- Gerenciar o ciclo de vida do recurso por meio do status de um recurso.
- Disponibilizar um recurso para ambientes definidos.
- Compartilhar um recurso com outras organizações.

Os procedimentos a seguir explicam como um usuário no RCS pode adicionar um recurso de globalização e componentes relacionados, atualizar o status do recurso e disponibilizar o recurso para que possa ser usado nos serviços de globalização.

Antes de concluir os procedimentos, você deverá concluir as etapas relacionadas às seguintes tarefas:

- Acessar uma instância RCS.
- Criar e ativar um provedor de configuração. Para obter mais informações, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Na sua instância de aplicativos do Finance and Operations, siga estas etapas.

1. Vá para **Administração da organização** \> **Espaços de trabalho** \> **Relatório eletrônico**.
2. Se não tiver o ambiente do RCS provisionado para sua empresa, selecione **Regulatory services – Configuração** e siga as instruções para provisionar um.

> [!NOTE]
> Se um ambiente RCS já tiver sido provisionado para sua empresa, use a URL da página para acessá-lo selecionando a opção de entrada.

## <a name="turn-on-the-globalization-features"></a>Ativar os Recursos de globalização

1. Na instância RCS, selecione o bloco **Gerenciamento de recursos**.
2. No espaço de trabalho **Gerenciamento de recursos** , selecione **Recursos de globalização** na lista e, em seguida, selecione **Habilitar agora**.

    ![Recursos de globalização no Gerenciamento de recursos](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a>Recursos de globalização

Para usar um Recurso de globalização, primeiro você deverá importá-lo do Repositório global e criar sua própria versão. Há duas maneiras de adicionar Recursos de globalização:

- Adicione um recurso derivado que se baseia em um recurso existente que foi publicado ou compartilhado.
- Adicione um novo recurso criado do zero.

## <a name="access-globalization-features"></a>Acessar Recursos de globalização

1. Verifique se o recurso **Recursos de globalização** está ativado no Gerenciamento de recursos conforme descrito anteriormente neste tópico.
2. Abra o novo espaço de trabalho **Recursos de Globalização** e, em seguida, em **Recursos**, selecione o bloco **Faturamento eletrônico**.

    ![Espaço de trabalho Recursos Globais](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    A página **Recursos de faturamento eletrônico** é aberta.

    ![Página Recursos de faturamento eletrônico](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a>Adicionar um Recurso de globalização derivado

Você pode adicionar um novo Recurso de globalização derivando-o de um recurso existente que foi publicado ou compartilhado.

1. Selecione **Importar** para abrir a página **Importar recurso do Repositório global**.

    ![Página Importar recurso do Repositório global](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. Selecione **Sincronizar** para obter os recursos mais recentes.

    A lista sincronizada inclui recursos que estão disponíveis para você porque foram publicados pela Microsoft ou porque foram compartilhados com você por outro provedor de configuração.

    ![Lista de recursos sincronizados](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. Na lista, selecione os recursos a serem importados e, em seguida, selecione **Importar**. Você receberá uma mensagem quando os recursos selecionados tiverem sido importados com êxito.

    ![Mensagem de importação bem-sucedida](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. Selecione **Adicionar** e , na caixa de diálogo suspensa, selecione a opção **Com base na versão existente**.
5. Digite um nome e uma descrição para o recurso.
6. Na lista de recursos disponíveis, selecione a versão base do recurso e selecione **Criar recurso**.

    ![Adição de um recurso derivado](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    O recurso adicionado é criado e tem um status **Rascunho**.

    ![Recurso derivado com status Rascunho](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. Revise os componentes do recurso para determinar se as atualizações são necessárias:

    - Revise as configurações, caso precise personalizar os formatos de Relatório eletrônico (ER) e sua associação com mapeamentos de formato para a versão do recurso.
    - Revise a configuração caso precise personalizar a guia **Ações**, **Regras de aplicabilidade** ou a guia **Variáveis** para a versão do recurso.

8. Na guia **Versões**, selecione uma data **Início da vigência** e digite uma descrição se o campo **Descrição** estiver em branco.
9. Selecione **Alterar status** para concluir o recurso. Os recursos completos podem ser disponibilizados para um ambiente específico, de forma que possam ser usados nos serviços de globalização ou podem ser publicados no Repositório global.

> [!NOTE]
> Os recursos com um **Status de versão do recurso** **Publicado** podem ser compartilhados com organizações externas.

## <a name="add-a-new-globalization-feature"></a>Adicionar um novo Recurso de globalização

Você pode adicionar um novo Recurso de globalização, criando-o do zero.

1. Na página **Importar recurso do Repositório global** , selecione **Adicionar** e, na caixa de diálogo suspensa, selecione a opção **Novo recurso**.
2. Digite um nome e uma descrição para o recurso.
3. Selecione **Criar recurso**.

    ![Adição de um novo recurso](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. Na guia **Versões**, selecione uma data **Início da vigência** e, em seguida, selecione **Alterar status** para concluir o recurso. Os recursos completos podem ser disponibilizados para um ambiente específico, de forma que possam ser usados nos serviços de globalização ou podem ser publicados no Repositório global.

> [!NOTE]
> Os recursos com um **Status de versão do recurso** **Publicado** podem ser compartilhados com organizações externas.

## <a name="feature-component-overview"></a>Visão geral do componente de recurso

Os recursos de globalização têm vários componentes:

- **Versão** – esse componente oferece suporte ao gerenciamento de ciclo de vida de recursos e permite que os usuários gerenciem o status de versões diferentes do recurso.
- **Configurações** – esse componente permite que os usuários gerenciem, exibam e editem formatos de ER e mapeamentos de formato relacionados.
- **Configurações** – esse componente permite que os usuários dos Serviços de globalização, como um serviço de faturamento eletrônica, gerenciem a configuração da versão do recurso relacionado. Portanto, ele oferece suporte à construção flexível de regras de comunicação e respostas.
- **Ambiente** – esse componente permite que os usuários dos serviços de globalização, como um serviço de faturamento eletrônico, gerenciem o ambiente no qual a configuração da versão do recurso é usada e conceda autorização aos usuários que terão acesso a ele.
- **Organizações** – esse componente permite que os usuários compartilhem o recurso com organizações externas.

## <a name="configuring-feature-components"></a>Como configurar componentes de recursos

### <a name="version-and-status"></a>Versão e status

A versão é usada para gerenciar o ciclo de vida do Recurso de globalização.

O status pode ser alterado no campo **Status** na guia **Versão**. Os seguintes status estão disponíveis:

- **Rascunho** – o recurso só poderá ser editado quando estiver com esse status.
- **Concluído** – o recurso e todos os componentes relacionados foram finalizados (concluídos) e não podem ser editados.
- **Publicado** – o recurso e todos os componentes relacionados foram publicados no Repositório global.
- **Compartilhado** – o recurso e todos os componentes relacionados foram compartilhados com organizações externas.
- **Habilitado** – o recurso e todos os componentes relacionados foram habilitados para uso em um Serviço de globalização, por exemplo, um serviço de faturamento eletrônico.

> [!NOTE]
> Os recursos devem ser movidos sequencialmente por alguns desses status. Portanto, nem todo status pode estar disponível em todos os estágios do ciclo de vida.

### <a name="configurations"></a>Configurações

As ações a seguir estão disponíveis para configurações:

- **Exibir** – exiba as configurações de recursos subjacentes que não exigem atualização.
- **Editar** – cria uma versão de rascunho de uma configuração selecionada para que você possa editar o formato ou o mapeamento de formato no Designer de formatação.
- **Excluir** – exclui uma configuração selecionada do recurso.
- **Alterar base** – baseie o recurso novamente. Para obter mais informações, consulte a seção [Trocar base de Recursos de globalização derivados](#rebase) posteriormente neste tópico.

### <a name="setups"></a>Configurações

As ações a seguir estão disponíveis para configurações de recurso:

- **Adicionar** – crie uma nova configuração de recurso. Essa configuração de recurso pode ser derivada de uma configuração de recurso existente ou criada do zero.
- **Excluir** – exclui uma configuração de recurso selecionada.
- **Exibir** – exibe uma configuração de recurso subjacente que não exige alterações.
- **Editar** – crie, exclua ou modifique os atributos dos três componentes principais de uma configuração de recurso:

    - Ações e seus parâmetros
    - Regras de aplicabilidade
    - Variáveis

![Página Configuração da versão do recurso](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a>Ambientes

As ações a seguir estão disponíveis para ambientes:

- **Habilitar** – para uma versão do recurso selecionada, selecione um ambiente publicado e selecione uma data **Início da vigência** quando ela deverá estar disponível. Para obter mais informações, consulte a seção [Configurar ambientes para habilitação](#configureenvironment) posteriormente neste tópico.
- **Cancelar** – remova um ambiente para uma configuração de recurso.

### <a name="organizations"></a>Organizações

Siga estas etapas para compartilhar um Recurso de globalização com uma organização externa.

1. Na página **Recursos de faturamento eletrônico**, selecione o recurso e a versão do recurso a serem compartilhados.
2. Na guia **Organizações**, selecione **Compartilhar com** e, na caixa de diálogo suspensa, insira o nome de domínio da organização.
3. Selecione **Compartilhar**.

    ![Compartilhamento de um recurso com uma organização](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

O recurso é compartilhado com a organização selecionada e está disponível para essa organização no Repositório global. A partir daí, o recurso pode ser importado para a instância da organização do RCS ou do Dynamics 365 Finance para que possa ser usado.

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a>Trocar base de Recursos de globalização derivados

Você pode alterar a base de um Recurso de globalização derivado para a versão do recurso base nova ou atualizada. Dessa forma, as alterações ocorridas na versão base podem ser atualizadas automaticamente. A versão do recurso base atualizada é criada pelo provedor de configuração original e, em seguida, é publicada ou compartilhada.

![Versão do recurso de base atualizada](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

Por exemplo, se desejar alterar a base da versão derivada de um recurso criado, você primeiro obterá a versão mais recente do recurso importando-a do repositório global.

1. Na página **Recursos de faturamento eletrônico**, selecione **Importar**.
2. Selecione **Sincronizar** para obter os recursos mais recentes.
3. Na lista de recursos, selecione os recursos a serem importados e, em seguida, selecione **Importar**.

    ![Importação da versão mais recente de um recurso](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. Na lista de recursos, selecione o recurso a ter a base trocada.
5. Na guia **Versão**, selecione **Nova** para criar uma versão de rascunho.

    ![Nova versão de rascunho criada](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. Selecione **Trocar base**.
7. Na caixa de diálogo **Trocar base**, selecione a última versão do recurso para o qual a base será trocada.

    ![Caixa de diálogo Trocar base](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. Selecione **OK**.
9. Revise os componentes do recurso e faça as alterações necessárias.
10. Selecione **Alterar status** para concluir o recurso com a base trocada. Quando a troca de base é concluída, você pode executar ações adicionais. Por exemplo, você pode publicar o recurso e torná-lo disponível para uso nos Serviços de globalização.

    ![Status do recurso atualizado para Concluído](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a>Configurar ambientes para Recursos de globalização

Os usuários dos Serviços de globalização podem gerenciar o ambiente para configurar um Recurso de globalização e conceder autorização a outros usuários que terão acesso a ele.

1. No espaço de trabalho **Recursos de Globalização** e, em seguida, em **Ambientes**, selecione o bloco **Faturamento eletrônico**.

    ![Espaço de trabalho Recursos de Globalização](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. Selecione **Parâmetros de de Key Vault** e, em seguida, selecione **Novo** para criar um segredo do Azure Key Vault.
3. Insira um nome e uma descrição para o key vault e, em seguida, no campo **URI do Key Vault**, insira a URL que identifica o recurso Key Vault no Azure.
4. Na Guia Rápida **Certificados**, selecione **Adicionar** para adicionar o certificado e insira um nome e uma descrição para cada certificado.

    ![Certificado adicionado](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. Selecione **Novo** para criar um novo ambiente.
6. Digite um nome, uma descrição e o segredo do token de assinatura de acesso compartilhado necessário para o armazenamento.
7. Na Guia Rápida **Usuários**, selecione **Novo** para adicionar um usuário que terá permissão para acessar esse ambiente.
8. Insira a ID de usuário e o endereço de email do usuário.
9. Repita as etapas 7 e 8 para adicionar mais usuários.
10. Selecione **Publicar** para publicar o ambiente.

    ![Ambiente publicado](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]