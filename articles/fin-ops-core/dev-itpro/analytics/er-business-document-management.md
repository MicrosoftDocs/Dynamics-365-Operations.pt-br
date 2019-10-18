---
title: Visão geral de gerenciamento de documentos comerciais
description: Este tópico fornece informações sobre como usar o recurso de gerenciamento de documentos comerciais da estrutura de ER.
author: NickSelin
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3c84b08ec45dfa7aa9c7b913087a2518bfeedf87
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181556"
---
# <a name="business-document-management-overview"></a>Visão geral de gerenciamento de documentos comerciais

Os usuários comerciais usam a [estrutura de Relatório eletrônico (ER)](general-electronic-reporting.md) para configurar formatos para documentos de saída de acordo com os requisitos legais de vários países/regiões. Os usuários também podem definir o fluxo de dados para especificar quais dados do aplicativo são colocados nos documentos gerados. A estrutura de ER gera documentos de saída nos formatos do Microsoft Office (pastas de trabalho do Excel ou documentos do Word) usando modelos predefinidos. Os modelos são preenchidos com os dados necessários de acordo com o fluxo de dados configurado enquanto os documentos necessários são gerados. Cada formato configurado pode ser publicado como parte de uma solução de ER para gerar documentos de saída específicos. Isso é representado por uma configuração de formato de ER que pode conter modelos usados para gerar diferentes documentos de saída. Os usuários comerciais podem usar essa estrutura para gerenciar os documentos comerciais necessários.

O **gerenciamento de documentos comerciais** é baseado na estrutura de ER e permite que os usuários comerciais editem modelos de documentos comerciais usando o serviço do Microsoft Office 365 ou o aplicativo de área de trabalho apropriado do Microsoft Office. As edições nos documentos podem incluir a alteração dos designs dos documentos comerciais e a adição de espaços reservados para dados adicionais sem alterações no código-fonte e novas implantações. Não é necessário conhecimento da estrutura de ER para atualizar modelos de documentos comerciais.

> [!NOTE]
> Saiba que o gerenciamento de documentos comerciais permite modificar modelos usados para produzir documentos comerciais, como pedidos, faturas etc. Embora um modelo tenha sido modificado e uma nova versão tenha sido publicada, essa versão é usada para gerar documentos comerciais necessários. O gerenciamento de documentos comerciais não pode ser usado para modificar documentos comerciais já gerados.

## <a name="supported-deployments"></a>Implantações com suporte

Atualmente, o recurso de gerenciamento de documentos comerciais é implementado apenas para implantações na nuvem. Se esse recurso for essencial para sua implantação local, avise-nos deixando comentários sobre o site [Ideias](https://experience.dynamics.com/ideas/).

## <a name="supported-microsoft-office-applications"></a>Aplicativos Microsoft Office com suporte

Para usar o gerenciamento de documentos comerciais para editar modelos nos formatos Excel ou Word usando aplicativos da área de trabalho do Microsoft Office, você deve ter o Microsoft Office 2010 ou posterior instalado. Isso tem suporte em implantações locais e na nuvem.

## <a name="business-document-availability"></a>Disponibilidade de documentos comerciais

Os seguintes relatórios, com modelos baseados no Excel, estarão disponíveis com o lançamento da visualização pública:

**Contas a receber** (agosto de 2019)

- Fatura antecipada de venda
- Guia de remessa de ordem de venda

**Contas a pagar** (agosto de 2019)

- Fatura antecipada de compra
- Ordem de Compra
- Guia de remessa de ordem de compra

Mais relatórios estarão disponíveis. Notificações especiais sobre relatórios adicionais serão enviadas separadamente. 

Uma lista completa de todos os relatórios planejados para a versão de outubro de 2019 pode ser encontrada em [Relatório configurável de documentos comerciais em Word e Excel](https://docs.microsoft.com/en-us/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details).

# <a name="example-enable-configure-and-use-business-document-management"></a>Exemplo: habilitar, configurar e usar o gerenciamento de documentos comerciais

Para saber mais sobre este recurso, conclua o exemplo neste tópico.

## <a name="configure-er-parameters"></a>Configurar parâmetros de ER

Como o gerenciamento de documentos comerciais é baseado na estrutura de ER, você deve configurar os parâmetros de ER para começar a trabalhar com o gerenciamento de documentos comerciais. Para isso, você precisa configurar os parâmetros de ER, conforme descrito em [Configurar a estrutura de ER](electronic-reporting-er-configure-parameters.md). Você também precisa adicionar um novo provedor de configuração, conforme descrito em [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Espaço de trabalho ER](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>Importar soluções de ER

Você deve importar configurações de ER que contêm modelos de documentos comerciais para a instância atual. Baixe e armazene localmente os seguintes arquivos para concluir este procedimento.

**Solução de faturamento de cliente de ER**

| **Arquivo**                                  | **Conteúdo**                                |
|-------------------------------------------|--------------------------------------------|
| Customer invoicing model.version.2.xml    | [Configuração do modelo de dados de ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Customer FTI report (GER).version.2.3.xml | [Configuração de formato de ER de fatura de texto livre](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**Exemplo de solução de cheques de pagamento de ER**

| **Arquivo**                                  | **Conteúdo**                                |
|-------------------------------------------|--------------------------------------------|
| Model for cheques.version.10.xml          | [Configuração do modelo de dados de ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Cheques printing format.version.10.9.xml  | [Configuração de formato de ER de cheque de pagamento](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**Exemplo de solução de comércio exterior de ER**

| **Arquivo**                                  | **Conteúdo**                                |
|-------------------------------------------|--------------------------------------------|
| Intrastat model.version.1.xml             | [Configuração do modelo de dados de ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Intrastat report.version.1.9.xml          | [Configuração de formato de ER do relatório Controle intrastat](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Use o procedimento a seguir para importar cada arquivo. Importe a configuração de ER *modelo de dados* de cada solução de ER nas tabelas acima antes de importar a configuração correspondente de ER *formato*.

1. Abra a página **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na parte superior da página, selecione **Troca**.
3. Selecione **Carregar do arquivo XML**.
4. Selecione **Procurar** para carregar o arquivo XML necessário.
5. Selecione **OK** para confirmar a importação da configuração.

![Página de configurações de ER](./media/BDM-Overview-ERSolutions.png)

Para obter mais informações sobre como importar configurações de ER, consulte [Gerenciar o ciclo de vida da configuração de relatório eletrônico (ER)](general-electronic-reporting-manage-configuration-lifecycle.md).

## <a name="enable-business-document-management"></a>Habilitar gerenciamento de documentos comerciais

Para iniciar o gerenciamento de documentos comerciais, é necessário abrir o espaço de trabalho **Gerenciamento de recursos** e habilitar o recurso **Gerenciamento de documentos comerciais**.

Use o procedimento a seguir para habilitar a funcionalidade de gerenciamento de documentos comerciais para todas as entidades legais.

1. Abra o espaço de trabalho **Gerenciamento de recursos**.
2. Na guia **Novo**, selecione o recurso **Gerenciamento de documentos comerciais** na lista.
3. Selecione **Habilitar agora** para ativar o recurso selecionado.
4. Atualize a página para acessar o novo recurso.

![Espaço de trabalho do gerenciamento de recursos](./media/BDM-Overview-FMEnabling.png)

Para obter mais informações sobre como ativar novos recursos, consulte [Visão geral do gerenciamento de recursos](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-parameters"></a>Configurar parâmetros

Use as informações nas seções a seguir para configurar os parâmetros básicos para o gerenciamento de documentos comerciais.

### <a name="prerequisites-for-parameter-setup"></a>Pré-requisitos para configuração de parâmetros
Antes de poder configurar o gerenciamento de documentos comerciais, você deve configurar o tipo de documento necessário na estrutura de gerenciamento de documentos. Esse tipo de documento é usado para especificar um armazenamento temporário de documentos nos formatos do Office (Excel e Word) usados como modelos de relatórios de ER. O modelo de armazenamento temporário pode ser editado usando os aplicativos da área de trabalho do Office.

Para esse tipo de documento, os valores de atributo a seguir devem ser selecionados.

| **Nome do atributo**  | **Valor do atributo**   |
|---------------------|-----------------------|
| Classe               | Anexar arquivo           |
| Agrupar               | Arquivo                  |
| Local            | SharePoint            |

Para obter informações sobre como configurar os parâmetros e tipos de documento necessários para gerenciamento de documentos, consulte [Configurar gerenciamento de documentos](../../fin-and-ops/organization-administration/configure-document-management.md).

![Configurar o tipo de documento de gerenciamento de documentos](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a>Configurar parâmetros

Os parâmetros básicos de gerenciamento de documentos comerciais podem ser configurados na página **Parâmetros do documento comercial**. Somente usuários específicos podem acessar a página. Isso inclui:

- Usuários atribuídos à função **Administrador do sistema**.
- Usuários atribuídos a qualquer função configurada para executar a obrigação **Manter parâmetros de gerenciamento de documentos comerciais** (nome da AOT **ERBDMaintainParameters**).

Use o procedimento a seguir para configurar os parâmetros básicos de todas as entidades legais.

1. Entre como um usuário com acesso à página **Parâmetros do documento comercial**.
2. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Gerenciamento de documentos comerciais** \> **Parâmetros do documento comercial**.
3.  Na página **Parâmetros do documento comercial**, na guia **Anexos**, no campo **Tipo de documento do SharePoint**, defina o tipo de documento que deve ser usado para armazenar temporariamente modelos nos formatos do Office enquanto eles são editados usando os aplicativos da área de trabalho do Office. 

> [!NOTE]
> Somente tipos de documentos configurados usando um local do SharePoint estão disponíveis para esse parâmetro.

![Configuração dos parâmetros de gerenciamento de documentos comerciais](./media/BDM-Overview-BDMSetting.png)

O tipo de documento selecionado é específico da empresa e será usado quando o usuário estiver trabalhando com o gerenciamento de documentos comerciais na empresa para a qual o tipo de documento selecionado está configurado. Quando o usuário estiver trabalhando com o gerenciamento de documentos comerciais em outra empresa, o mesmo tipo de documento selecionado será usado se um não tiver sido configurado para esta empresa. Quando um tipo de documento for configurado, ele será usado em vez daquele selecionado no campo **Tipo de documento do SharePoint**.

## <a name="configure-access-permissions"></a>Configurar permissões de acesso

Por padrão, quando o acesso às permissões de gerenciamento de documentos comerciais não está habilitado, todos os usuários com acesso ao espaço de trabalho Gerenciamento de documentos comerciais verão todos os modelos de solução de ER disponíveis. O espaço de trabalho Gerenciamento de documentos comerciais mostrará apenas os modelos que residem nas configurações do formato de ER e que são marcados por uma etiqueta **Tipo de documento comercial**.

![Página de configurações de ER](./media/BDM-Overview-ERFormatTags.png)

A lista de modelos disponíveis no espaço de trabalho Gerenciamento de documentos comerciais pode ser restringida por meio da configuração de permissões de acesso. Isso pode ser importante quando modelos diferentes são usados para produzir documentos comerciais para diferentes domínios comerciais (áreas funcionais) e você deseja permitir que usuários específicos acessem modelos diferentes para edição no espaço de trabalho Gerenciamento de documentos comerciais.

As permissões de acesso ao gerenciamento de documentos comerciais podem ser definidas em **Configurador de permissões de acesso**. Somente os seguintes usuários podem acessar a página:

- Usuários atribuídos à função **Administrador do sistema**.
- Usuários atribuídos a qualquer outra função configurada para executar a obrigação **Configurar permissões para acessar modelos de documento comercial para edição** (nome da AOT **ERBDTemplatesSecurity**).

Use o procedimento a seguir para configurar as permissões de gerenciamento de documentos comerciais de acesso para todas as entidades legais.

1. Entre no como um usuário com acesso à página **Configurador de permissões de acesso**.
2. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Gerenciamento de documentos comerciais** \> **Gerenciar permissões de acesso**.

Preste atenção na notificação informando que o uso de permissões de acesso para gerenciamento de documentos comerciais não está habilitado no momento.

![Página do configurador de permissões de acesso ao gerenciamento de documentos comerciais](./media/BDM-Overview-TemplatesAccess1.png)

Com essa configuração, todos os usuários atribuídos a qualquer função de segurança configurada para executar a obrigação **Gerenciar modelos de documento comercial** (nome da AOT **ERBDManageTemplates**) podem abrir o espaço de trabalho Gerenciamento de documentos comerciais e podem editar qualquer modelo disponível.

O gráfico a seguir mostra o que está disponível no espaço de trabalho Gerenciamento de documentos comerciais para usuários atribuídos à função **Auxiliar de contas a receber**. Com a configuração atual de permissões de acesso, o usuário pode editar modelos de documentos comerciais de diferentes áreas funcionais, incluindo faturamento, relatórios regulatórios e pagamentos.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-TemplatesForAlice1.png)

3. Na página **Configurador de permissões de acesso**, selecione **Configuração de permissões de acesso**.
4. Na caixa de diálogo **Configurações de permissões de acesso para editar modelos**, habilite a opção **Aplicar permissões de acesso configuradas**.
5. Selecione **OK** para confirmar se as permissões de acesso ao gerenciamento de documentos comerciais foram habilitadas.

![Página do configuração de permissões de acesso de gerenciamento de documentos comerciais](./media/BDM-Overview-TemplatesAccess2.png)

6. Selecione **Adicionar** para inserir uma nova função comercial para a qual as permissões para acessar os modelos de gerenciamento de documentos comerciais devem ser configuradas.
7. Na caixa de diálogo **Funções de segurança**, selecione a função **Auxiliar de contas a receber** e selecione **OK** para confirmar a seleção de função.
8. Na guia **Permissões de acesso por marcas de configurações**, selecione **Novo**.
9. No campo **Tipo de etiqueta**, selecione **Área funcional** e, no campo **ID**, selecione **Faturamento**.
10. Selecione **Salvar** para armazenar permissões de acesso configuradas da função selecionada.

  A configuração atual significa que, para qualquer usuário que é atribuído à função **Auxiliar de contas a receber** e realizando a obrigação **Gerenciar modelos de documento comercial** (nome da AOT **ERBDManageTemplates**), modelos de configuração de formato de ER com o valor **Faturamento** da etiqueta **Área funcional** estarão disponíveis para edição no espaço de trabalho Gerenciamento de documentos comerciais.

11. Alterne o painel **Informações relacionadas** no lado direito da página atual. O painel **Informações relacionadas** mostra como as permissões de acesso configuradas serão aplicadas, incluindo quais modelos de configuração de ER estarão disponíveis para usuários atribuídos à função **Auxiliar de contas a receber**.

![Página do configuração de permissões de acesso de gerenciamento de documentos comerciais](./media/BDM-Overview-TemplatesAccess3.png)

12. Na guia **Permissões de acesso por marcas de configurações**, selecione a opção **Adicionar**.
13. Na caixa de diálogo **Select configuration**, marque a configuração de formato de ER **Relatório intrastat**.
14. Selecione **OK** para confirmar a entrada das configurações selecionadas e selecione **Salvar** para armazenar as permissões de acesso configuradas da função selecionada.

A configuração atual significa que, para qualquer usuário que é atribuído à função **Auxiliar de contas a receber** e realizando a obrigação **Gerenciar modelos de documento comercial** (nome da **ERBDManageTemplates**), os modelos a seguir estarão disponíveis para edição no espaço de trabalho Gerenciamento de documentos comerciais:

- Modelos que possuem o valor **Faturamento** da etiqueta **Área funcional**.
- Modelos de configurações de formato de ER listadas na guia **Permissões de acesso por configurações** (modelos da configuração de formato **Relatório intrastat** do domínio **Relatório estatutário** neste exemplo).

![Página do configuração de permissões de acesso de gerenciamento de documentos comerciais](./media/BDM-Overview-TemplatesAccess4.png)

O gráfico a seguir mostra o que o espaço de trabalho Gerenciamento de documentos comerciais fornece para um usuário atribuído à função **Auxiliar de contas a receber**. Com a configuração atual de permissões de acesso ao gerenciamento de documentos comerciais, o usuário pode editar modelos de documentos comerciais usando o domínio **Faturamento** e a configuração de formato de ER **Relatório intrastat**. Os modelos do domínio **Pagamentos** não estão acessíveis para a função **Auxiliar de contas a receber**.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> As regras **Permissões de acesso por configurações** são armazenadas usando a ID exclusiva de uma configuração de formato de ER. Isso significa que essas regras não serão excluídas quando uma configuração de ER que se refere a elas for excluída. Quando você importa configurações excluídas novamente para essa instância, essas regras vão se referir a elas novamente. Não há necessidade de definir as regras novamente depois que as configurações excluídas forem importadas novamente.

## <a name="use-business-document-management-to-edit-templates"></a>Usar o gerenciamento de documentos comerciais para editar modelos

Os usuários comerciais podem acessar os modelos de documentos comerciais para edição no espaço de trabalho Gerenciamento de documentos comerciais. Somente os seguintes usuários podem acessar o espaço de trabalho Gerenciamento de documentos comerciais:

- Usuários atribuídos à função **Administrador do sistema**.
- Usuários atribuídos a qualquer função configurada para executar a obrigação **Gerenciar modelos de documento comercial** (nome da AOT **ERBDManageTemplates**).

Use o procedimento a seguir para editar modelos de fatura de texto livre no espaço de trabalho Gerenciamento de documentos comerciais. Antes de concluir esse procedimento, você precisa ter concluído todos os procedimentos anteriores neste tópico.

1. Entre como um usuário com acesso ao espaço de trabalho Gerenciamento de documentos comerciais.
2. Abra o espaço de trabalho Gerenciamento de documentos comerciais.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-EditingTemplate1.png)

A guia **Modelo** apresenta o conteúdo do modelo selecionado. Selecione a guia **Detalhes** para analisar os detalhes do modelo selecionado, bem como os detalhes de uma configuração de formato de ER em que esse modelo está. Observe que todos os modelos têm o status de **Publicado** e não contêm detalhes na coluna **Revisão**. Isso significa que esses modelos não estão sendo editados no momento.

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>Iniciar modelos de edição pertencentes ao seu provedor de configuração

1. No espaço de trabalho Gerenciamento de documentos comerciais, selecione o modelo **Formato de impressão de cheques** na lista.
2. Selecione a guia **Detalhes**.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-EditingTemplate2.png)

A opção **Editar modelo** está disponível para o modelo selecionado. Essa opção está sempre disponível para um modelo em uma configuração de formato de ER que pertence ao provedor de configuração de ER ativo (**Litware, Inc.** neste exemplo). Quando **Editar modelo** é selecionado, o modelo existente da versão de rascunho da configuração subjacente do formato de ER estará disponível para edição.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>Iniciar modelos de edição pertencentes a outros provedores

1. No espaço de trabalho Gerenciamento de documentos comerciais, selecione o modelo **Relatório de FTI do cliente (GER)** na lista.
2. Selecione a guia **Detalhes**.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-EditingTemplate3.png)

A opção **Novo documento** está disponível para o modelo selecionado. Essa opção está sempre disponível para um modelo em uma configuração de formato de ER fornecida por outro provedor (**Litware, Inc.** neste exemplo). Quando **Novo documento** é selecionado, um novo modelo estará disponível para edição. O modelo editado será armazenado em uma nova configuração de formato de ER que é gerada automaticamente.

### <a name="start-editing-a-template"></a>Começar a editar um modelo

1. No modelo selecionado, selecione **Novo documento**.
2. No campo **Cargo**, altere o título do modelo editável, se necessário. O texto será usado para nomear a configuração de formato de ER criada automaticamente. Observe que a versão de rascunho dessa configuração (**Cópia do relatório de FTI do cliente (GER)**) que conterá o modelo editado será automaticamente marcada para executar esse formato de ER para o usuário atual. Ao mesmo tempo, o modelo original não modificado da configuração básica do formato de ER será usado para executar esse formato de ER para qualquer outro usuário.
3. No campo **Nome**, altere o nome da primeira revisão do modelo editável que será criado automaticamente.
4. No campo **Comentário**, altere a observação para a revisão criada automaticamente do modelo editável.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-EditingTemplate4.png)

5. Selecione **OK** para confirmar o início do processo de edição.

A página **Editor de modelo de BDM** será aberta. O modelo selecionado estará disponível para edição online usando o Office 365.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-office-365"></a>Editar um modelo no Office 365

Modifique o modelo usando a funcionalidade do Office 365. Por exemplo, no Office online, altere a fonte dos avisos do campo no cabeçalho do modelo de **Regular** para **Negrito**. Essas alterações são armazenadas automaticamente para o modelo editável armazenado no armazenamento do modelo principal (por padrão, o armazenamento de blob do Azure) configurado para a estrutura de ER.

![Página do editor de modelo de gerenciamento de documentos comerciais](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a>Editar um modelo no aplicativo da área de trabalho do Office

1. Selecione a opção **Abrir no Aplicativo de Área de Trabalho** para modificar o modelo usando a funcionalidade do aplicativo de área de trabalho do Office (Excel neste exemplo). O modelo editável é copiado do armazenamento permanente para o armazenamento temporário configurado nos parâmetros de gerenciamento de documentos comerciais como uma pasta do SharePoint.
2. Confirme se deseja abrir o modelo do armazenamento de arquivos temporário no aplicativo de área de trabalho do Excel no Office.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-EditingLayout3.png)

3. Modifique o modelo. Por exemplo, altere a fonte dos avisos dos campos no cabeçalho do modelo, atualizando a cor de **Preto** para **Azul**.

![Página do editor de modelo de gerenciamento de documentos comerciais](./media/BDM-Overview-EditingLayout4.png)

4. Selecione **Salvar** no aplicativo de área de trabalho do Excel para armazenar as alterações de modelo no armazenamento temporário.

![Página do editor de modelo de gerenciamento de documentos comerciais](./media/BDM-Overview-EditingLayout5.png)

5. Feche o aplicativo da área de trabalho do Excel.
6. Selecione **Sincronizar cópia armazenada** para sincronizar o armazenamento de modelos temporário com o armazenamento de modelos permanente.

> [!NOTE]
> A cópia do modelo editável no armazenamento de arquivos temporário é mantida apenas para a sessão atual de edição do modelo. Quando você termina essa sessão fechando a página **Editor de modelo de BDM**, essa cópia será excluída. Se você ajustou o modelo no armazenamento de arquivos temporário e não selecionou **Sincronizar cópia armazenada**, ao tentar fechar a página **Editor de modelo de BDM**, uma mensagem perguntará se você deseja armazenar as alterações introduzidas. Selecione **Sim** se você deseja salvar suas alterações no modelo no local do arquivo permanente.

### <a name="validate-a-template"></a>Validar um modelo

1. Na página **Editor de modelo de BDM**, selecione **Verificar se há problemas** para validar o modelo modificado em relação à configuração de formato de ER subjacente. Siga as recomendações (se houver) para alinhar o modelo com a estrutura do formato na configuração básica de formato de ER.
2. Selecione **Mostrar formato** para exibir a estrutura atual do formato na configuração básica de formato de ER que deve estar alinhada com o modelo editável. 
3. Selecione **Ocultar formato** para fechar o painel.

![Página do editor de modelo de BDM](./media/BDM-Overview-EditingTemplate6.png)

4. Feche a página **Editor de modelo de BDM**.

O modelo atualizado é mostrado na guia **Modelo**. Observe que o status do modelo editado agora é **Rascunho** e a revisão atual não está mais vazia. Isso significa que o processo de edição deste modelo foi iniciado.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>Testar o modelo modificado 

1. No aplicativo, mude para a empresa **USMF**.
2. Acesse **Contas a receber** \> **Faturas** \> **Todas as faturas de texto livre**.
3. Selecione a fatura **FTI-00000002** e **Gerenciamento de impressão**.
4. Selecione o nível **Módulo - Contas a receber** \> **Documentos** \> **Fatura de texto livre** \> **Documento original** para especificar o escopo das faturas para processamento.
5. No campo **Formato de relatório**, selecione o formato de ER **Cópia do relatório de FTI do cliente (GER)** para o nível do documento especificado.

![Página de configuração de gerenciamento de impressão](./media/BDM-Overview-TestRun1.png)

6. Pressione **Esc** para fechar a página atual.
7. Selecione **Imprimir** e clique em **Selecionado**.
8. Baixe o documento e abra-o usando o aplicativo da área de trabalho do Excel.

![Página de faturas de texto livre](./media/BDM-Overview-TestRun2.png)

O modelo modificado é usado para gerar o relatório de fatura de texto livre para o item selecionado. Para analisar como esse relatório é afetado pelas alterações introduzidas no modelo, você pode executá-lo em uma sessão do aplicativo logo após modificar o modelo em outra sessão do aplicativo.

### <a name="create-an-alternative-template-revision"></a>Criar uma revisão de modelo alternativa

1. Abra a página **Editor de modelo de BDM** e selecione o modelo **Cópia do relatório de FTI do cliente (GER)**.
2. Na guia **Revisões**, selecione **Novo**.
3. Se necessário, no campo **Nome**, altere o nome da segunda revisão e baseie-o na primeira revisão atualmente ativa.
4. Se necessário, no campo **Comentário**, altere a observação para a revisão criada automaticamente do modelo editável.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-AddRevision.png)

Você criou uma revisão do seu modelo que foi armazenada no armazenamento permanente do modelo. Agora você pode continuar editando o modelo da segunda revisão atualmente selecionada como ativa.

5. Selecione a primeira revisão e selecione **Definir como ativo**. É possível selecionar outra revisão como ativa para retornar a essa revisão do modelo a qualquer momento.
6. Selecione a segunda revisão e selecione **Excluir**.
7. Selecione **OK** para confirmar que você deseja excluir a revisão selecionada. É possível excluir qualquer uma das revisões inativas quando elas não forem mais necessárias.

### <a name="delete-a-modified-template"></a>Excluir um modelo modificado

1. Na página **Editor de modelo de BDM**, selecione a guia **Modelo**.
2. Selecione **Excluir**.
3. Se você selecionar **OK** para confirmar a exclusão, o formato de ER **Cópia do relatório de FTI do cliente (GER)** com o modelo modificado será excluído. Selecione **Cancelar** para explorar outras opções.

### <a name="revoke-changes-of-template"></a>Revogar alterações do modelo

Ao editar o modelo de um formato de ER que pertence ao provedor ativo atual, você terá a opção de revogar as alterações introduzidas no modelo.

![Página do espaço de trabalho de gerenciamento de documentos comerciais](./media/BDM-Overview-RevokeChanges.png)

1. Na página **Editor de modelo de BDM**, selecione a guia **Modelo**.
2. Selecione **Desfazer**.
3. Se você selecionar **OK** para revogar as alterações introduzidas no modelo, o modelo modificado será substituído pelo modelo original e todas as alterações serão removidas. Ao revogar alterações no modelo, você poderá excluir o modelo. Selecione **Cancelar** para explorar outras opções.

### <a name="publish-a-modified-template"></a>Publicar um modelo modificado
1. Na página **Editor de modelo de BDM**, na guia **Modelo**, selecione **Publicar**.
2. Se você selecionar **OK** para confirmar a publicação, a versão de rascunho do formato de ER derivado **Cópia do relatório de FTI do cliente (GER)** que contém o modelo modificado será marcada como concluída. O modelo modificado fica disponível para outros usuários. As versões completas desse formato de ER manterão apenas a última revisão ativa do seu modelo. Outras revisões serão excluídas. Selecione **Cancelar** para explorar outras opções.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

#### <a name="i-selected-new-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-office-365-web-page"></a>Selecionei **Novo documento**, mas, em vez de abrir a página **Editor de modelo de BDM** no Finance and Operations, fui direcionado à página da Web do Office 365.
Esse é um problema conhecido de redirecionamento do Office 365. Isso acontece quando você entra no Office 365 pela primeira vez. Para contornar esse problema, selecione o botão **Voltar** do navegador para retornar.

#### <a name="i-understand-how-to-edit-a-template-by-using-office-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-adjusting-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-do-this-using-the-office-desktop-application"></a>Entendo como editar um modelo usando o Office 365 na primeira sessão do aplicativo e como usar o modelo na segunda sessão do aplicativo ajustando o modelo para ver como minhas alterações afetam o documento comercial gerado. Posso fazer isso usando o aplicativo da área de trabalho do Office?
Sim, você pode. Na primeira sessão do aplicativo, selecione **Abrir no Aplicativo de Área de Trabalho**. Seu modelo será armazenado no armazenamento de arquivos temporário e aberto no aplicativo da área de trabalho do Office. Em seguida, conclua as etapas a seguir para visualizar suas alterações de modelo no documento comercial gerado:

1. Faça alterações no modelo usando o aplicativo da área de trabalho do Office.
2. Selecione **Salvar** no aplicativo da área de trabalho do Office.
3. Na página **Editor de modelo de BDM** da primeira sessão do aplicativo, selecione **Sincronizar cópia armazenada**.
4. Execute esse modelo de formato de ER na segunda sessão do aplicativo.

#### <a name="i-get-the-error-value-cannot-be-null-parameter-name-externalid-when-i-select-open-in-desktop-app-how-do-i-work-around-this"></a>Recebo o erro: O valor não pode ser nulo. Nome do parâmetro: externalId quando seleciono **Abrir no Aplicativo de Área de Trabalho**. Como faço para resolver isso? 
Provavelmente, você entrou na instância atual do aplicativo do domínio do Azure AD, diferente do domínio do Azure AD que foi usado para implantar essa instância. Como o serviço do SharePoint, usado para armazenar modelos para disponibilizá-los para edição usando os aplicativos da área de trabalho do Office, pertence ao mesmo domínio, não temos permissões para acessar o serviço do SharePoint. Para resolver esse problema, entre na instância atual usando as credenciais de um usuário com o domínio correto do Azure AD.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório eletrônico](general-electronic-reporting.md)

[Criar uma configuração para gerar relatórios no formato OPENXML](tasks/er-design-reports-openxml-2016-11.md)

[Criar configurações de ER para gerar relatórios no formato do Word](tasks/er-design-configuration-word-2016-11.md)

[Inserir imagens e formas em documentos que você gerar usando ER](electronic-reporting-embed-images-shapes.md)

[Configurar Relatório eletrônico para efetuar pull de dados no Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)
