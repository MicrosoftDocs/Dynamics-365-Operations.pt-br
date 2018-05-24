---
title: "Destinos de relatório eletrônico"
description: "Você pode configurar uma meta para cada configuração de formato de relatório eletrônico (ER)e seu componente de saída (uma pasta ou um arquivo). Os usuários que têm direitos de acesso apropriados também podem modificar as configurações de destino em tempo de execução. Este artigo explica gerenciamento de destino do ER, os tipos de destinos que têm suporte e considerações de segurança."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fb7d0dc8b3ff9e8f1e4ade5cacfeed8f1a6871ab
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="electronic-reporting-destinations"></a>Destinos de relatório eletrônico

[!include [banner](../includes/banner.md)]

Você pode configurar uma meta para cada configuração de formato de relatório eletrônico (ER)e seu componente de saída (uma pasta ou um arquivo). Os usuários que têm direitos de acesso apropriados também podem modificar as configurações de destino em tempo de execução. Este artigo explica gerenciamento de destino do ER, os tipos de destinos que têm suporte e considerações de segurança.

Configurações de formato (ER) geralmente contêm pelo menos um componente de saída de relatório eletrônico: um arquivo. Normalmente, as configurações contém vários componentes de saída de arquivos de tipos diferentes (por exemplo, XML, TXT ou XLSX) que são agrupados em uma única pasta ou várias pastas. Gerenciamento de destino do ER permite pré-configurar o que ocorre quando cada componente é executado. Por padrão, quando uma configuração é executada, uma caixa de diálogo é exibida que permite que o usuário salve ou abra o arquivo. O mesmo comportamento também é usado quando você importar uma configuração de ER e não configurar os destinos específicos para ele. Após a criação de um destino para um componente de saída principal, esse destino substitui o comportamento padrão e a pasta ou o arquivo é enviado de acordo com as configurações do destino.

## <a name="availability-and-general-prerequisites"></a>Disponibilidade e pré-requisitos gerais
A funcionalidade de destinos de ER não está disponível no Microsoft Dynamics AX 7.0 (fevereiro de 2016). Portanto, você deve instalar o Microsoft Dynamics 365 for Operations, versão 1611, (novembro de 2016) para usar todas as funções que serão descritas neste tópico. Se preferir,, você pode instalar um dos seguintes pré-requisitos. Entretanto, note que essa alternativa permite uma experiência de destino de ER mais limitada.

-   Aplicativo Microsoft Dynamics AX versão 7.0.1 (maio de 2016)
-   Gerenciamento de destino do ER [hotfix do aplicativo](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

Você pode configurar destinos somente para configurações de ER que foram importadas e para os formatos que estão disponíveis na página **Configurações de relatório eletrônicas**.

## <a name="overview"></a>Visão Geral
A funcionalidade de gerenciamento de destino do ER está disponível em **Administração da organização** &gt; **Relatório eletrônico**. Aqui, você pode substituir o comportamento padrão para uma configuração. Configurações importadas não são mostradas aqui até que você clique em **Novo** e, em seguida, no campo **Referência**, selecione uma configuração para criar configurações de destino.

[![Selecionando uma configuração no campo Referência](./media/ger-destinations-2-1611-1024x574.jpg)](./media/ger-destinations-2-1611.jpg) 

Após você ter criado uma referência, você pode criar um destino de arquivo para cada pasta ou para um arquivo. 

[![Criando um destino do arquivo](./media/ger-destinations-1611-1024x586.jpg)](./media/ger-destinations-1611.jpg)

> [!NOTE] 
> Você pode criar um destino de arquivo para cada componente de saída do mesmo formato, como uma pasta ou um arquivo que é selecionado no campo **Nome do arquivo**. Você pode ativar e desativar os destinos individuais para o destino do arquivo na caixa de diálogo **Configurações de destino**. O botão **Configurações** é usado para controlar todos os destinos de um destino de arquivo selecionado. Na caixa de diálogo **Configurações de destino**, você pode controlar cada destino separadamente, definindo a opção **Ativado** para ele.

[![Caixa de diálogo de configurações de destino](./media/ger-destinations-settings-1611-1024x589.jpg)](./media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Tipos de destino
Há suporte para vários tipos de destinos. Você pode desativar ou ativar todos os tipos ao mesmo tempo. Dessa forma, você pode não fazer nada ou enviar o componente para todos os destinos configurados. As seções a seguir descrevem os destinos que são suportados.

### <a name="email-destination"></a>Destino de email

Definir **Habilitado** para **Sim** para enviar um arquivo de saída por e-mail. Depois que esta opção for ativada, você pode especificar os destinatários de e-mail e editar o assunto e o corpo da mensagem de email. Você pode configurar textos constantes do assunto e do corpo de email, ou você pode usar ER de fórmulas para criar textos de email dinamicamente. Você pode configurar endereços de email para o ER de duas formas. A configuração pode ser concluída da mesma forma que o recurso de gerenciamento de impressão no Finance and Operations a conclui. Se preferir, você pode resolver um endereço de email usando uma referência direta para a configuração de ER através de uma fórmula.

### <a name="email-address-types"></a>Tipos de endereço de email

Quando você clica em **Editar** para o campo **Para** ou **Cc**, a caixa de diálogo **Email para** é exibida. Você pode selecionar o tipo de endereço de email para uso.

[![Caixa de diálogo Email para](./media/ger-destinations-email-1-1611-1024x588.jpg)](./media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Gerenciamento de impressão

Se selecionar o tipo **Imprimir email de gerenciamento**, você pode inserir os endereços de e-mail fixos no campo **Para**. Para usar os endereços de e-mail não fixos, você deve selecionar o tipo de origem de e-mails para um destino de arquivo. Os valores a seguir são suportados: **Cliente**, **Fornecedor**, **Cliente potencial**, **Contato**, **Concorrente**, **Trabalhador**, **Candidato**, **Fornecedor potencial** e **Fornecedor não permitido**. Após selecionar um tipo de origem de email, use o botão ao lado do campo **Conta de origem do email** para abrir o formulário **Designer de fórmulas**. Você pode usar este formulário para anexar uma fórmula que representa a conta de participante selecionada para o destino de email.

[![Configurar tipo de email do gerenciamento de impressão](./media/ger-destinations-email-2-1611-1024x588.jpg)](./media/ger-destinations-email-2-1611.jpg) 

Observe que as fórmulas são específicas da configuração de ER. Em **Fórmula**, digite uma referência específica a um tipo da parte do cliente ou fornecedor. Em vez de digitar, você pode encontrar um nó da fonte de dados que representa a conta de cliente ou fornecedor, e clicar no botão **Adicionar fonte de dados** para atualizar a fórmula. Exemplo: Se você usar a configuração da transferência de crédito ISO 20022, o nó que representa uma conta de fornecedor é **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. Caso contrário, insira qualquer valor da cadeia de caracteres, como **DE-001**, para salvar a fórmula.

[![Designer de fórmulas](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

Na caixa de diálogo **Email para**, clique na lixeira ao lado do campo **Conta de origem do email** para excluir permanentemente a fórmula para a conta de origem de email. Se preferir, abra o designer de fórmula para alterar uma fórmula que foi salva anteriormente. Para atribuir endereços de email, clique em **Editar** para abrir a caixa de diálogo **Atribuir endereços de email**.

[![Atribuindo endereços de email para destino de email](./media/ger-destinations-email-3-1611-1024x587.jpg)](./media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Email de configuração

Use este tipo de email se a configuração que você usar tiver um nó nas fontes de dados que representam um endereço de email. Você pode usar fontes de dados e as funções no designer de fórmulas para obter um endereço de email corretamente formatado.

[![Atribuindo uma fonte de dados do endereço de email para um destino de email](./media/ger-destinations-email-4-1611-1024x587.jpg)](./media/ger-destinations-email-4-1611.jpg) 

**Observação:** um servidor Simple Mail Transfer Protocol (SMTP) deve ser configurado e disponível. Você pode especificar o servidor SMTP no Finance and Operations em **Administração do sistema** &gt; **Configuração** &gt; **E-mail** &gt; **Parâmetros de e-mail**.

### <a name="archive-destination"></a>Local do arquivo morto

Você pode usar esta opção para enviar a saída para uma pasta do Microsoft SharePoint ou Microsoft Azure Storage. Definir **Habilitado** para **Sim** para enviar a saída para um destino que é definido pelo tipo de documento selecionado. Somente tipos de documento onde o grupo está definido para **Arquivo** estão disponíveis para seleção. Você define os tipos de documentos em **Administração da organização** &gt; **Gerenciamento de documentos** &gt; **Tipos de documentos**. A configuração de destinos de ER é o mesma que a configuração para o sistema de gerenciamento de documentos.

[![Página Tipos de documento](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg) 

O local determina onde o arquivo foi salvo. Depois que o destino do **Arquivo** for ativado, os resultados da execução da configuração podem ser salvos no arquivo de trabalho. Você pode exibir os resultados em **Administração da organização** &gt; **Relatório eletrônico** &gt; **Trabalhos arquivados de relatórios eletrônicos**. **Observação:** Você pode selecionar um tipo de documento para o arquivo de trabalho no Finance and Operations, em **Administração da organização** &gt; **Espaços de trabalho** &gt; **Relatório eletrônico** &gt; **Parâmetros de relatório eletrônico**.

#### <a name="sharepoint"></a>SharePoint

Você pode salvar um arquivo em uma pasta designada do SharePoint. Você define o servidor padrão do SharePoint em **Administração da organização** &gt; **Gerenciamento de documentos** &gt; **Parâmetros de gerenciamento de documentos** na guia **SharePoint**. Depois que a pasta do SharePoint for configurada, você pode selecioná-la como a pasta onde a saída ER será salva para o tipo de documento. 

[![Selecionando uma pasta do SharePoint](./media/ger_sharepointfolderselection-1024x543.jpg)](./media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Armazenamento do Azure

Quando o local de tipo de documento é definido como **Diretório de arquivo morto**, você pode salvar um arquivo para o armazenamento do Azure.

### <a name="file-destination"></a>Destino de arquivo

Se você definir **Ativado** como **Sim**, uma caixa de diálogo abrir ou salvar será exibida quando a configuração terminar a execução.

### <a name="screen-destination"></a>Destino da tela

Se você definir **Ativado** como **Sim**, será criada uma visualização da saída. Você pode exibir alguns tipos de arquivo, como o XML, TXT, ou PDF diretamente em uma janela do navegador. Para outros tipos de arquivos, como Microsoft Excel ou Word, o serviço do Microsoft Office Online será usado.

### <a name="power-bi-destination"></a>Destino do Power BI

Defina **Ativado** como **Sim** para usar sua configuração de ER para organizar a transferência de dados da sua instância do Finance and Operations para os serviços do Microsoft Power BI. Os arquivos transferidos são armazenados em uma instância do Microsoft SharePoint Server que deve ser configurada para esse fim. Para obter mais informações, consulte [Usar uma configuração de relatório eletrônico para fornecer o Power BI com dados do Finance and Operations](general-electronic-reporting-report-configuration-get-data-powerbi.md). **Dica:** para substituir o comportamento padrão (ou seja, a caixa de diálogo para uma configuração), você pode criar uma referência de destino e um destino de arquivo para o componente de saída principal e, em seguida, desabilitar todos os destinos.

## <a name="security-considerations"></a>Considerações de segurança
Dois tipos de direitos e privilégios são usados para destinos de ER. Um tipo controla a capacidade de manter os destinos gerais que estão configurados para uma entidade legal (isto é, controla o acesso à página **Destinos de relatório eletrônico**). O outro tipo controla a capacidade de um usuário do aplicativo para substituir, em tempo de execução, as configurações de destino são configuradas por um desenvolvedor de ER ou consultor funcional ER.

| Função (nome da AOT)                     | Nome da função                                  | Direito (nome da AOT)                     | Nome do direito                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Desenvolvedor de relatório eletrônico             | ERFormatDestinationConfigure        | Configurar destino de formato de relatório eletrônico                |
| ERFunctionalConsultant              | Consultor funcional de relatório eletrônico | ERFormatDestinationConfigure        | Configurar destino de formato de relatório eletrônico                |
| PaymAccountsPayablePaymentsClerk    | Auxiliar de pagamentos de contas a pagar            | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de relatório eletrônico durante o tempo de execução |
| PaymAccountsReceivablePaymentsClerk | Auxiliar de pagamentos de contas a receber         | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de relatório eletrônico durante o tempo de execução |

> [!NOTE]
> Dois privilégios são usados em tarefas anteriores. Esses privilégios têm os mesmos nomes que as tarefas correspondentes: **ERFormatDestinationConfigure** e **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Importei configurações eletrônicas e vejo na página de configurações de relatório eletrônico. Mas por que eu não os vejo na página de destinos de relatórios eletrônicos?

Certifique-se de clicar em **Novo** e selecione uma configuração no campo **Referência**. Na página **Destinos de relatório eletrônico**, você pode ver apenas as configurações que foram configuradas para destinos.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Existe alguma maneira para definir qual conta de armazenamento do Azure e armazenamento de BLOBs do Azure são usados?

Não. O armazenamento de Blob do Azure padrão que é definido e usado para o sistema de gerenciamento de documentos é usado.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Qual é a finalidade do destino do arquivo nas configurações de destino? O que faz essa configuração?

O destino **Arquivo** é usado para controlar uma caixa de diálogo. Se você habilitar esse destino, ou se nenhum destino for definido para uma configuração, você verá uma caixa de diálogo abrir ou salvar após a criação de um arquivo de saída.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Pode dar um exemplo de fórmula que se refere a uma conta de fornecedor que eu possa enviar e-mail para?

A fórmula é específica da configuração de ER. Por exemplo, se você usa a configuração de transferência de crédito ISO 20022, você pode usar **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** ou **model.Payments.Creditor.Identification.SourceID** para obter uma conta de fornecedor associada.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Uma das minhas configurações de formato contém vários arquivos de grupo em uma pasta (por exemplo, Pasta1 contém Arquivo1, Arquivo2 e Arquivo3). Como posso configurar destinos de forma que a Pasta1.zip não seja criada, o Arquivo1 seja enviado por email, o Arquivo2 seja enviado ao SharePoint e eu possa abrir o Arquivo3 imediatamente depois que a configuração for executada?

O pré-requisito é que o formato deve estar disponível nas configurações de ER. Se você tiver o formato, abra a página **Destino de relatórios eletrônico** e crie uma nova referência para esta configuração. Em seguida, você deve ter quatro destinos de arquivo, um para cada componente de saída. Crie o destino do arquivo primeiro, dê a ele um nome como **Pasta** e selecione um nome de arquivo que representa uma pasta na sua configuração. Em seguida, clique em **Configurações** e certifique-se de que todos os destinos estão desativados. Para este destino do arquivo, a pasta não será criada. Por padrão, por causa das dependências hierárquicas entre os arquivos e pastas pai, os arquivos irão se comportar da mesma maneira. Em outras palavras, eles não serão enviados em qualquer lugar. Para substituir esse comportamento padrão, você deve criar três destinos mais de arquivo, um para cada arquivo. Nas configurações de destino de cada um, você deve habilitar o destino em que o arquivo deve ser enviado para.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório eletrônico](general-electronic-reporting.md)




