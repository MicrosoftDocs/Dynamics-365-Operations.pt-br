---
title: "Destinos de relatório eletrônico"
description: "Você pode configurar uma meta para cada configuração de formato de relatório eletrônico (ER)e seu componente de saída (uma pasta ou um arquivo). Os usuários que têm direitos de acesso apropriados também podem modificar as configurações de destino em tempo de execução. Este artigo explica gerenciamento de destino do ER, os tipos de destinos que têm suporte e considerações de segurança."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: d38d05fe445bf0326d408038dff84ccf8c0ff64c
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-destinations"></a>Destinos de relatório eletrônico

Você pode configurar uma meta para cada configuração de formato de relatório eletrônico (ER)e seu componente de saída (uma pasta ou um arquivo). Os usuários que têm direitos de acesso apropriados também podem modificar as configurações de destino em tempo de execução. Este artigo explica gerenciamento de destino do ER, os tipos de destinos que têm suporte e considerações de segurança.

Configurações de formato (ER) geralmente contêm pelo menos um componente de saída de relatório eletrônico: um arquivo. Normalmente, as configurações contém vários componentes de saída de arquivos de tipos diferentes (por exemplo, XML, TXT ou XLSX) que são agrupados em uma única pasta ou várias pastas. Gerenciamento de destino do ER permite pré-configurar o que ocorre quando cada componente é executado. Por padrão, quando uma configuração é executada, uma caixa de diálogo aparece deixe que o usuário abrir ou salvar o arquivo. O mesmo comportamento também é usado quando você importar uma configuração de ER e não configurar os destinos específicos para ele. Após a criação de um destino para um componente de saída principal, esse destino substitui o comportamento padrão e a pasta ou o arquivo é enviado de acordo com as configurações do destino.

## <a name="availability-and-general-prerequisites"></a>Disponibilidade e pré-requisitos gerais
A funcionalidade de destinos de ER não está disponível no Microsoft Dynamics 365 para a versão de operações (7.0). em fevereiro de 2016 Portanto, você deve instalar o Microsoft Dynamics 365 (para operações em novembro de 2016 versão) usar todas as funções que serão descritas neste tópico. Alternativamente, você pode instalar um dos seguintes pré-requisitos. Entretanto, note que esse a alternativa permite uma experiência limitada mais de destino de ER.

-   Microsoft Dynamics 365 para a versão 7.0.1 do aplicativo de operações (em maio de 2016)
-   Gerenciamento de destino do ER [hotfix do aplicativo](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

Você pode configurar destinos somente para configurações de ER que foram importadas e para os formatos que estão disponíveis na página **Configurações de relatório eletrônicas**.

## <a name="overview"></a>Visão Geral
A funcionalidade gerenciamento de destino de ER disponível ** administração organizacional ** &gt; ** no relatório eletrônico **. Aqui, você pode substituir o comportamento padrão para uma configuração. Configurações importadas não são mostradas aqui até que você clique em **Novo** e, em seguida, no campo **Referência**, selecione uma configuração para criar configurações de destino.

[![que selecionar uma configuração no campo de referência (]. /media/ger-destinations-2-1611-1024x574.jpg)](. /media/ger-destinations-2-1611.jpg) 

Depois de criar uma referência, você pode criar um alvo para cada arquivo de pasta, ou para um arquivo. 

[![que criar um alvo de arquivo (]. /media/ger-destinations-1611-1024x586.jpg)](. /media/ger-destinations-1611.jpg)

**Observação:** você pode criar um destino de arquivo para cada componente de saída do mesmo formato, como uma pasta que é selecionada no campo **Nome do arquivo**. Você poderá habilitar ou desabilitar destinos individuais para o destino de arquivo ** configurações de destino ** a caixa de diálogo. O botão **Configurações** é usado para controlar todos os destinos de um destino de arquivo selecionado. Na caixa de diálogo **Configurações de destino**, você pode controlar cada destino separadamente, definindo a opção **Ativado** para ele.

[caixa de diálogo configurações do destino do![(]. /media/ger-destinations-settings-1611-1024x589.jpg)](. /media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Tipos de destino
Há suporte para vários tipos de destinos. Você pode desativar ou ativar todos os tipos ao mesmo tempo. Dessa forma, você pode não fazer nada ou enviar o componente para todos os destinos configurados. As seções a seguir descrevem os destinos que são suportados.

### <a name="email-destination"></a>Destino de email

Definir **Habilitado **para **Sim** para enviar um arquivo de saída por e-mail. Após esta opção estiver habilitada, você poderá especificar os destinatários de email, edita e o assunto e o corpo da mensagem de email eletrônico. Você pode configurar textos constantes do assunto e o corpo de email, ou você pode usar ER de fórmulas para criar textos dinamicamente de email. Você pode configurar endereços de email para o ER de duas formas. A configuração pode ser completada da mesma forma que o recurso de gerenciamento de impressão em dynamics 365 para operações a terminar. Alternativamente, você pode resolver um endereço de email direto com uma referência à configuração de ER em uma fórmula.

### <a name="email-address-types"></a>Tipos endereço de email

Quando você clica ** ** para edição ou ** ** ** campo, cc ** ** email ** a caixa de diálogo aparece. Você pode selecionar o tipo de endereço de email para uso.

[email do![a caixa de diálogo (]. /media/ger-destinations-email-1-1611-1024x588.jpg)](. /media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Gerenciamento de impressão

Se selecionar ** imprima o email de gerenciamento ** digite, você pode inserir endereços de email ** ** fixos no campo. Para usar os endereços de email que não são fixos, você deve selecionar o tipo de origem de email de destino para um arquivo. Os valores a seguir são suportados: ** Cliente **, ** ** ** fornecedor, cliente potencial, ** ** ** ** contato, concorrentes **, ** trabalhador ** **, candidato ** **, fornecedor e, possivelmente ** ** fornecedor não permitido. ** Após selecionar um tipo de origem de email, use o botão ao lado de e-mail ** enviar a conta fonte ** campo para abrir ** designer de fórmulas ** o formulário. Você pode usar este formulário para anexar uma fórmula que represente a conta selecionada de participantes alvo do email.

[![configure o tipo de email de gerenciamento de impressão (]. /media/ger-destinations-email-2-1611-1024x588.jpg)](. /media/ger-destinations-email-2-1611.jpg) 

Observe que as fórmulas são específicas da configuração de ER. Em **Fórmula**, digite uma referência específica a um tipo da parte do cliente ou fornecedor. Em vez de digitar, você pode encontrar um nó da fonte de dados que representa a conta de cliente ou fornecedor, e clicar no botão **Adicionar fonte de dados** para atualizar a fórmula. Exemplo: Se você usar a configuração da transferência de crédito ISO 20022, o nó que representa uma conta de fornecedor é **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID**. Caso contrário, insira qualquer valor da cadeia de caracteres, como **DE-001**, para salvar a fórmula.

[![Formula designer](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

** Email ** na caixa de diálogo, clique na lixeira próximas ** conta de origem de email ** de excluir permanentemente a fórmula para a conta de origem de email. Alternativamente, abra o designer de fórmulas para alterar uma fórmula que esteja salvas anteriormente. Atribuir endereços de email, clique ** edição ** para abrir ** endereços de email de atribuir ** a caixa de diálogo.

[endereços de email de atribuição do![por uma meta de email (]. /media/ger-destinations-email-3-1611-1024x587.jpg)](. /media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Email de configuração

Usar este tipo de email caso a configuração o usar um nó tiver fontes de dados que represente um endereço de email. Você pode usar fontes de dados e as funções no designer de fórmulas para obter um endereço de email corretamente formatado.

[![que atribui uma fonte de dados do endereço de email de um alvo de email (]. /media/ger-destinations-email-4-1611-1024x587.jpg)](. /media/ger-destinations-email-4-1611.jpg) 

**Observação:** um servidor Simple Mail Transfer Protocol (SMTP) deve ser configurado e disponível. É possível especificar seu servidor SMTP em dynamics 365 para operações, ** administração de sistema ** &gt; ** em de instalação ** &gt; ** email ** &gt; ** ** parâmetros de email.

### <a name="archive-destination"></a>Local do arquivo morto

Você pode usar esta opção para enviar a saída para uma pasta do Microsoft SharePoint ou Microsoft Azure Storage. Definir **Habilitado** para **Sim **para enviar a saída para um destino que é definido pelo tipo de documento selecionado. Somente tipos de documento onde o grupo está definido para **Arquivo** estão disponíveis para seleção. Definir tipos de documento ** administração organizacional ** &gt; ** o gerenciamento de documentos ** &gt; ** ** tipos de documento. A configuração de destinos de ER é o mesma que a configuração para o sistema de gerenciamento de documentos.

[página tipos de documento do![(]. /media/ger_documenttypefile-1024x542.jpg)](. /media/ger_documenttypefile.jpg) 

O local determina onde o arquivo foi salvo. Após ** arquivo morto ** o destino estiver habilitado, os resultados de execução de configuração podem ser salvas no arquivo morto de trabalho. Você pode exibir os resultados ** administração organizacional ** &gt; ** no relatório eletrônico ** &gt; ** relatório eletrônico arquivados ** trabalho. ** Observação: ** Você pode selecionar um tipo de documento do arquivo morto de trabalho em dynamics 365 para operações, ** administração organizacional ** &gt; ** os espaços de trabalho ** &gt; ** relatório eletrônico ** &gt; ** parâmetros de relatório eletrônicos **.

#### <a name="sharepoint"></a>SharePoint

Você pode salvar um arquivo em uma pasta designada do SharePoint. Defina o servidor padrão do SharePoint ** administração organizacional ** &gt; ** o gerenciamento de documentos ** &gt; ** parâmetros de gerenciamento de documentos, ** ** SharePoint ** na guia. Depois da pasta de O SharePoint é configurada, você poderá marcá-la como a pasta onde as saídas de ER serão salvas para o tipo de documento. 

[![que selecionar uma pasta de O SharePoint (]. /media/ger_sharepointfolderselection-1024x543.jpg)](. /media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Armazenamento do Azure

Quando o local de tipo de documento é definido como **Diretório de arquivo morto**, você pode salvar um arquivo para o armazenamento do Azure.

### <a name="file-destination"></a>Destino de arquivo

Se você definir ** habilitado ** ** Sim **, um aberto ou uma caixa de diálogo salvar aparecem quando a configuração concluiu executar.

### <a name="screen-destination"></a>Alvo de tela

Se você definir ** habilitado ** ** Sim **, uma visualização de saída seja criado. Você pode exibir alguns tipos de arquivo, como o XML, TXT, ou o, PDF diretamente em uma janela do navegador. Para outros tipos de arquivos, Microsoft Excel ou como Word, o serviço Microsoft Office Online é usada.

### <a name="power-bi-destination"></a>Meta do power BI

Conjunto ** habilitado ** ** Sim ** usar a configuração de ER para organizar a transferência de dados da sua instância do 365 para operações serviços de O power BI Microsoft. Os arquivos são transferidos armazenados em uma instância do Microsoft SharePoint que pode ser configurada para essa finalidade. Para obter mais informações, consulte [use uma configuração eletrônica de fornecer o power BI com dados do 365 para as operações general-electronic-reporting-report-configuration-get-data-powerbi.md] (). **Dica:** para substituir o comportamento padrão (ou seja, a caixa de diálogo para uma configuração), você pode criar uma referência de destino e um destino de arquivo para o componente de saída principal e, em seguida, desabilitar todos os destinos.

## <a name="security-considerations"></a>Considerações de segurança
Dois tipos de direitos e privilégios são usados para destinos de ER. Um tipo controla a capacidade de manter os destinos totais configurados para uma pessoa jurídica (isto é, controlar o acesso eletrônicos ** destinos de relatório ** a página). O outro tipo controla a capacidade de um usuário do aplicativo para substituir, em tempo de execução, as configurações de destino são configuradas por um desenvolvedor de ER ou consultor funcional ER.

| Função (nome da AOT)                     | Nome da função                                  | Direito (nome da AOT)                     | Nome do direito                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Desenvolvedor de relatório eletrônico             | ERFormatDestinationConfigure        | Configurar destino de formato de relatório eletrônico                |
| ERFunctionalConsultant              | Consultor funcional de relatório eletrônico | ERFormatDestinationConfigure        | Configurar destino de formato de relatório eletrônico                |
| PaymAccountsPayablePaymentsClerk    | Auxiliar de pagamentos de contas a pagar            | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de relatório eletrônico durante o tempo de execução |
| PaymAccountsReceivablePaymentsClerk | Auxiliar de pagamentos de contas a receber         | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de relatório eletrônico durante o tempo de execução |

**Observação:** dois privilégios são usados em tarefas anteriores. Esses privilégios têm os mesmos nomes que as tarefas correspondentes: **ERFormatDestinationConfigure** e **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Importei configurações eletrônicas e vejo na página de configurações de relatório eletrônico. Por que eu mas não os consulto na página eletrônico alvos de relatório?

Verifique se você clicar ** ** novo e selecione uma configuração ** ** referência no campo. Na página **Destinos de relatório eletrônico**, você pode ver apenas as configurações que foram configuradas para destinos.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>Existe alguma forma de definir que o armazenamento da conta de Azure de armazenamento e do blob de Azure é usado?

Não. Armazenamento padrão do blob de Azure definido e usado para o sistema de gerenciamento de documentos é usado.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>A finalidade de destino de Arquivo em configurações de destino? O que faz essa configuração?

O destino **Arquivo** é usado para controlar uma caixa de diálogo. Se você habilitar este destino ou, se nenhum alvo está definido para uma configuração, você verá uma caixa de diálogo abrir ou salvar de depois que um arquivo de saída seja criado.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Pode dar um exemplo de fórmula que se refere a uma conta de fornecedor que eu possa enviar e-mail para?

A fórmula é específica da configuração de ER. Por exemplo, se você usa a configuração de transferência de crédito ISO 20022, você pode usar **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** ou **model.Payments.Creditor.Identification.SourceID** para obter uma conta de fornecedor associada.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Uma das minhas configurações de formato contém vários arquivos de grupo em uma pasta (por exemplo, Pasta1 contém Arquivo1, Arquivo2 e Arquivo3). Como posso configurar destinos de forma que a Pasta1.zip não seja criada, o Arquivo1 seja enviado por email, o Arquivo2 seja enviado ao SharePoint e eu possa abrir o Arquivo3 imediatamente depois que a configuração for executada?

Um pré-requisito é que o formato deve estar disponível nas configurações de ER. Se você tiver o formato, abra a página **Destino de relatórios eletrônico** e crie uma nova referência para esta configuração. Em seguida, você deve ter quatro destinos de arquivo, um para cada componente de saída. Crie o destino do arquivo primeiro, dê a ele um nome como **Pasta** e selecione um nome de arquivo que representa uma pasta na sua configuração. Em seguida, clique em **Configurações** e certifique-se de que todos os destinos estão desativados. Para este destino do arquivo, a pasta não será criada. Por padrão, por causa das dependências hierárquicas entre os arquivos e pastas pai, os arquivos irão se comportar da mesma maneira. Em outras palavras, eles não serão enviados em qualquer lugar. Para substituir esse comportamento padrão, você deve criar três destinos mais de arquivo, um para cada arquivo. Nas configurações de destino de cada um, você deve habilitar o destino em que o arquivo deve ser enviado para.

# <a name="see-also"></a>Consulte também

[Visão geral do relatório eletrônico](general-electronic-reporting.md)


