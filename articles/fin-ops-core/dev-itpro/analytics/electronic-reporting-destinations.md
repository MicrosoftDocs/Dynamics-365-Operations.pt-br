---
title: Destinos de Relatório eletrônico (ER)
description: Este tópico fornece informações sobre o gerenciamento de destinos de relatório eletrônico, os tipos de destinos com suporte e considerações de segurança.
author: nselin
ms.date: 09/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: e8e176b8d4e14eee2050b3c66f7547ff878b5174
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647084"
---
# <a name="electronic-reporting-er-destinations"></a>Destinos de Relatório eletrônico (ER)

[!include [banner](../includes/banner.md)]

Você pode configurar uma meta para cada configuração de formato de relatório eletrônico (ER)e seu componente de saída (uma pasta ou um arquivo). Os usuários que têm direitos de acesso apropriados também podem modificar configurações de destino em tempo de execução. Este tópico explica o gerenciamento de destinos de ER, os tipos de destinos que têm suporte e considerações de segurança.

As configurações de formato de ER geralmente contêm pelo menos um componente de saída: um arquivo. Normalmente, as configurações contêm vários componentes de saída de arquivos de diferentes tipos (por exemplo, XML, TXT, XLSX, DOCX ou PDF) que são agrupados em uma única pasta ou em várias pastas. Gerenciamento de destino do ER permite pré-configurar o que ocorre quando cada componente é executado. Por padrão, quando uma configuração é executada, aparece uma caixa de diálogo que permite salvar ou abrir o arquivo. O mesmo comportamento também ocorre quando você importa uma configuração ER e não configura destinos específicos para ele. Após a criação de um destino para um componente de saída principal, esse destino substitui o comportamento padrão e a pasta ou o arquivo é enviado de acordo com as configurações do destino.

## <a name="availability-and-general-prerequisites"></a>Disponibilidade e pré-requisitos gerais

A funcionalidade de destinos de ER não está disponível no Microsoft Dynamics AX 7.0 (fevereiro de 2016). Por isso você deve instalar o Microsoft Dynamics 365 for Operations versão 1611 (novembro a 2016) ou posterior para usar os seguintes tipos de destino:

- [Email](er-destination-type-email.md)
- [Arquivar](er-destination-type-archive.md)
- [Arquivo](er-destination-type-file.md)
- [Tela](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)

Se preferir,, você pode instalar um dos seguintes pré-requisitos. Entretanto, essas alternativas proporcionam uma experiência de destino de ER mais limitada.

- Versão 7.0.1 do aplicativo Microsoft Dynamics AX (maio de 2016)
- [Hotfix do aplicativo de gerenciamento de destino de relatório eletrônico](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

Também existe um tipo de destino [Impressão](er-destination-type-print.md). Para usá-lo, você deve instalar o Microsoft Dynamics 365 Finance versão 10.0.9 (abril de 2020).

## <a name="overview"></a>Visão geral

Você pode configurar destinos somente para as configurações ER [importadas](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) para a instância atual do Finance e para os formatos disponíveis na página **Configurações de Relatórios eletrônicos**. A funcionalidade de gerenciamento de destino de ER está disponível em **Administração da organização** \> **Relatório eletrônico** \> **Destino de relatório eletrônico**.

### <a name="default-behavior"></a>Comportamento padrão

O comportamento padrão de uma configuração de formato ER depende do tipo de execução que você especifica quando um formato ER é iniciado.

Na caixa de diálogo **Relatório Intrastat**, na Guia Rápida **Executar o plano de fundo**, se você definir a opção de **Processamento em lotes** como **Não**, um formato ER será executado imediatamente no modo interativo. Quando essa execução é concluída com êxito, um documento de saída gerado é disponibilizado para download.

Se você definir a opção de **Processamento em lotes** como **Sim**, um formato ER será executado no modo de [Lotes](../sysadmin/batch-processing-overview.md). O trabalho em lotes apropriado é criado com base nos parâmetros especificados na guia **Executar no plano de fundo** da caixa de diálogo **Parâmetros de ER**.

> [!NOTE]
> A descrição do trabalho informa você sobre a execução de um mapeamento de formato ER. Também contém o nome do componente ER que é executado.

[![Execução de um formato ER.](./media/ER_Destinations-RunInBatchMode.png)](./media/ER_Destinations-RunInBatchMode.png)

Você pode encontrar informações sobre esse trabalho em vários locais:

- Acesse **Comum** \> **Consultas** \> **Trabalhos em lotes** \> **Meus trabalhos em lotes** para verificar o status da tarefa agendada.
- Acesse **Administração da organização** \> **Relatório eletrônico** \> **Trabalhos de relatórios eletrônicos** para verificar o status do trabalho agendado e os resultados da execução do trabalho concluído. Quando a execução do trabalho for concluída com êxito, selecione **Mostrar arquivos** na página **Trabalhos de relatório eletrônicos** para obter um documento de saída gerado.

    > [!NOTE]
    > Este documento está armazenado como um anexo do registro de trabalho atual e é controlado pela estrutura [Gerenciamento de documentos](../../fin-ops/organization-administration/configure-document-management.md). O [tipo de documento](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) usado para armazenar artefatos ER deste tipo é configurado nos [parâmetros ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

- Na página **Trabalhos de relatório eletrônicos**, selecione **Mostrar arquivos** para exibir a lista de erros e avisos que foram gerados durante a execução do trabalho.

    [![Examinando a lista de trabalhos ER.](./media/ER_Destinations-ReviewERJobs.png)](./media/ER_Destinations-ReviewERJobs.png)

### <a name="user-configured-behavior"></a>Comportamento configurado pelo usuário

Na página **Destino de relatório eletrônico**, é possível substituir o comportamento padrão de uma configuração. As configurações importadas não são mostradas nessa página até você selecionar **Novo** e, no campo **Referência**, selecionar uma configuração para criar configurações de destino.

[![Selecionando uma configuração no campo Referência.](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

Depois de criar uma referência, você pode criar um destino de arquivo para cada componente de saída **Pasta** ou **Arquivo** do formato de ER referenciado.

[![Criando um destino do arquivo.](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

Em seguida, na caixa de diálogo **Configurações de destino**, você pode habilitar e desabilitar destinos individuais para o destino do arquivo. O botão **Configurações** é usado para controlar todos os destinos de um destino de arquivo selecionado. Na caixa de diálogo **Configurações de destino**, você pode controlar cada destino separadamente, definindo a opção **Ativado** para ele.

Em versões do Finance **antes da versão 10.0.9**, você pode criar **um destino de arquivo** para cada componente de saída do mesmo formato, como uma pasta ou um arquivo selecionado no campo **Nome do arquivo**. No entanto, na **versão 10.0.9 e posterior**, você pode criar **vários destinos de arquivo** para cada componente de saída do mesmo formato.

Por exemplo, você pode usar esse recurso para configurar destinos de arquivo para um componente de arquivo usado para gerar um documento de saída no formato Excel. Um destino ([Arquivo](er-destination-type-archive.md)) pode ser configurado para armazenar o arquivo do Excel original no arquivo de trabalhos de ER, e outro destino ([Email](er-destination-type-email.md)) pode ser configurado para simultaneamente [converter](#OutputConversionToPDF) o arquivo do Excel em formato PDF e enviar o arquivo PDF por email.

[![Configurando vários destinos para um único elemento de formato.](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

Quando você executa um formato de ER, todos os destinos que foram configurados para componentes do formato são sempre executados. Além disso, no Finance **versão 10.0.17 e posterior**, a funcionalidade de destinos de ER foi aperfeiçoada e agora permite que você configure conjuntos diferentes de destinos para um único formato de ER. Essa configuração marca cada conjunto como configurado para uma ação de usuário específica. A API de ER foi [estendida](er-apis-app10-0-17.md) para que seja possível fornecer uma ação que o usuário realiza executando um formato de ER. O código de ação fornecido é passado para destinos de ER. Você pode executar diferentes destinos de um formato de ER, dependendo do código de ação fornecido. Para obter mais informações, consulte [Configurar destinos de ER dependentes da ação](er-action-dependent-destinations.md).

## <a name="destination-types"></a>Tipos de destino

No momento, os destinos a seguir são aceitos para os formatos de ER. Você pode desativar ou ativar todos os tipos ao mesmo tempo. Dessa forma, você pode não fazer nada ou enviar o componente para todos os destinos configurados.

- [Email](er-destination-type-email.md)
- [Arquivar](er-destination-type-archive.md)
- [Arquivo](er-destination-type-file.md)
- [Tela](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)
- [Imprimir](er-destination-type-print.md)

## <a name="applicability"></a>Aplicabilidade

Você pode configurar destinos somente para configurações ER que foram importadas e para os formatos que estão disponíveis na página **Configurações de relatório eletrônicas**.

> [!NOTE]
> Os destinos configurados são específicos da empresa. Se você planeja usar um formato de ER em diferentes empresas da instância atual do Finance, deve configurar destinos para esse formato de ER para cada uma dessas empresas.

Quando você configura destinos de arquivo para um formato selecionado, eles são configurados para todo o formato.

[![Link de configuração.](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

Ao mesmo tempo, você pode ter várias [versões](general-electronic-reporting.md#component-versioning) do formato que foram importadas para a instância atual do Finance. É possível vê-las selecionando o link **Configuração** que é exibido quando você seleciona o campo **Referência**.

[![Versões da configuração.](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

Por padrão, os destinos configurados são aplicados somente quando você executa uma versão do formato de ER que tem o status **Concluído** ou **Compartilhado**. No entanto, às vezes você deve usar destinos configurados quando a versão de rascunho de um formato de ER é executada. Por exemplo, você modifica uma versão de rascunho do seu formato e quer usar destinos configurados para testar como a saída gerada será entregue. Siga estas etapas para aplicar os destinos de um formato de ER quando a versão de rascunho for executada.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Defina a opção **Usar destinos para status de rascunho** como **Sim**.

[![Opção Usar destinos para status de rascunho.](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

Para usar a versão de rascunho de um formato de ER, você deve marcar o formato de ER adequadamente.

1. Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3. Defina a opção **Executar configuração** como **Sim**.

[![Opção Executar configuração.](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

Depois de concluir essa configuração, a opção **Executar rascunho** fica disponível para os formatos de ER que você modificar. Defina esta opção como **Sim** para começar a usar a versão de rascunho do formato quando o formato for executado.

[![Opção Executar rascunho.](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="destination-failure-handling"></a><a name="DestinationFailure"></a>Tratamento de falha no destino

Normalmente, um formato de ER é executado no escopo de um processo de negócios específico. No entanto, às vezes, a entrega de um documento de saída gerado durante a execução de um formato de ER deve ser considerada como parte desse processo de negócios. Nesse caso, se a entrega de um documento de saída gerado em um destino configurado não for bem-sucedida, a execução do processo de negócios deverá ser cancelada. Para configurar o destino de ER apropriado, selecione a opção **Interromper processamento em caso de falha**.

Por exemplo, você configura o processamento de pagamentos de fornecedor para que o formato de ER **Transferência de Crédito ISO20022** seja executado para gerar o arquivo de pagamento e os documentos complementares (por exemplo, a carta de apresentação e o relatório de controle). Se um pagamento tiver de ser considerado como tendo o processamento bem-sucedido somente se a carta de apresentação for entregue com êxito por email, você deverá marcar a caixa de seleção **Interromper processamento em caso de falha** para o componente **CoveringLetter** no destino de arquivo apropriado, conforme mostrado na ilustração a seguir. Nesse caso, o status do pagamento selecionado para processamento mudará de **Nenhum** para **Enviado** somente quando a carta de apresentação gerada for aceita com êxito para entrega por um provedor de email configurado na instância do Finance.

[![Configurando o tratamento de processos em caso de falha no destino de arquivo.](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

Se você desmarcar a caixa de seleção **Interromper processamento em caso de falha** para o componente **CoveringLetter** no destino, um pagamento será considerado como tendo o processamento bem-sucedido mesmo que a carta de apresentação não seja entregue com êxito por email. O status do pagamento mudará de **Nenhum** para **Enviado** mesmo que a carta de apresentação não possa ser enviada porque, por exemplo, o endereço de email do destinatário ou remetente está ausente ou incorreto.

## <a name="output-conversion-to-pdf"></a><a name="OutputConversionToPDF"></a>Conversão de saída em PDF

Você pode usar a opção de conversão em PDF para converter a saída em formato do Microsoft Office (Excel/Word) para PDF.

### <a name="make-pdf-conversion-available"></a>Disponibilizar conversão em PDF

Para disponibilizar a opção de conversão em PDF na instância atual do Finance, abra o espaço de trabalho **Gerenciamento de recursos** e ative o recurso **Converter documentos de saída do Relatório Eletrônico de formatos do Microsoft Office em PDF**.

[![Ativando a conversão em PDF do recurso de documentos de saída no Gerenciamento de recursos.](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>Aplicabilidade

Nas versões do Finance **antes da versão 10.0.18**, a opção de conversão do PDF pode ser ativada apenas para componentes **Excel\\Arquivo** usados para gerar saída no formato do Office (Excel ou Word). Quando esta opção está ativada, a saída gerada no formato do Office é convertida automaticamente para o formato PDF. No entanto, na **versão 10.0.18 e posterior**, também é possível ativar essa opção para componentes do tipo **Arquivo\\Comum**.

> [!NOTE]
> Preste atenção à mensagem de aviso recebida ao ativar a opção de conversão em PDF para um componente ER do tipo **Arquivo\\Comum**. Esta mensagem informa que não há como garantir, em tempo de design, que o componente de arquivo selecionado exporá o conteúdo no formato PDF ou o conteúdo convertido por PDF no runtime. Portanto, você deve ativar a opção somente se tiver certeza de que o componente de arquivo selecionado foi configurado para expor o conteúdo no formato PDF ou o conteúdo convertido em PDF no runtime.
> 
> Se você ativar a opção de conversão de PDF para um componente do formato, se esse componente expuser conteúdo em um formato diferente de PDF, e se o conteúdo exposto não puder ser convertido em formato PDF, ocorrerá uma exceção no runtime. A mensagem recebida informa que o conteúdo gerado não pode ser convertido para o formato PDF.

### <a name="limitations"></a>Limitações

A opção de conversão em PDF só está disponível para implantações em nuvem.

O documento PDF produzido pode ter um número máximo de 300 páginas.

No Finance **versão 10.0.9**, apenas a orientação de página paisagem tem suporte no documento PDF produzido de uma saída do Excel. No Finance **versão 10.0.10 (maio de 2020) e posterior**, você pode [especificar orientação de página](#SelectPdfPageOrientation) do documento PDF produzido a partir de um Excel enquanto você configura um destino de ER.

Somente as fontes de sistema comuns do sistema operacional Windows são usadas para converter uma saída que não contém fontes incorporadas.

### <a name="use-the-pdf-conversion-option"></a>Usar a opção de conversão em PDF

Para ativar a conversão em PDF para um destino de arquivo, marque a caixa de seleção **Converter em PDF**.

[![Ativando a conversão em PDF para um destino de arquivo.](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

### <a name=""></a><a name="SelectPdfPageOrientation">Selecione uma orientação de página para conversão em PDF</a>

Se você gerar uma configuração ER no formato Excel e quiser convertê-la em formato PDF, poderá especificar explicitamente a orientação de página do documento PDF. Quando você marca a caixa de seleção **Converter para PDF** para ativar a conversão em PDF para um arquivo de destino que produz um arquivo de saída no formato Excel, o campo **Orientação da página** fica disponível na página **Configurações de conversão para PDF**. No campo **Orientação da página**, você pode selecionar a orientação de sua preferência.

[![Selecionando uma orientação de página para conversão em PDF.](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)

Para ter a opção de selecionar a orientação da página PDF, instale o Finance versão 10.0.10 ou posterior. Nas versões do Finance **antes da versão 10.0.23**, essa opção oferece as seguintes opções de orientação de página:

- Retrato
- Paisagem

A orientação de página selecionada é aplicada a todas as páginas de um documento de saída gerado no formato Excel e, em seguida, convertidas para o formato PDF.

No entanto, na **versão 10.0.23 e posterior**, a lista de opções de orientação de página foi estendida da seguinte maneira:

- Retrato
- Paisagem
- Específico da planilha

Quando você seleciona a opção **Específico para a planilha**, todas as planilhas de uma pasta de trabalho do Excel gerada são convertidas para PDF usando a orientação de página configurada para essa planilha no modelo usado no Excel. Portanto, você pode ter um documento PDF final contendo página com orientação retrato e paisagem. 

Se uma configuração ER no formato Word for convertida para o formato PDF, a orientação de página do documento PDF será sempre baseada do documento do Word.

## <a name="output-unfolding"></a>Desdobramento de saída

Ao configurar um destino para o componente **Pasta** do seu formato de ER, você pode especificar como a saída desse componente será entregue ao destino configurado.

### <a name="make-output-unfolding-available"></a>Disponibilizar desdobramento de saída

Para tornar a opção de desdobramento de saída disponível na atual instância do Finance, abra o espaço de trabalho **Gerenciamento de recursos** e ative o recurso **Permitir a configuração de destinos de ER para enviar conteúdo de pastas como arquivos separados**.

### <a name="applicability"></a>Aplicabilidade

A opção de desdobramento de saída pode ser configurada somente para os componentes de formato do tipo **Pasta**. Quando você começa a configurar um componente **Pasta**, a Guia Rápida **Geral** fica disponível na página **Destino do relatório eletrônico**. 

### <a name="use-the-output-unfolding-option"></a>Usar a opção de desdobramento de saída

Na Guia Rápida **Geral**, no campo **Enviar pasta como**, selecione um dos seguintes valores:

- **Arquivo ZIP** – entrega um arquivo gerado como um arquivo zip.
- **Arquivos separados** – entrega cada arquivo de um arquivo zip gerado como um arquivo individual.

    > [!NOTE]
    > Quando você seleciona **Arquivos separados**, a saída gerada é coletada na memória em um estado zipado. Portanto, o [limite de tamanho de arquivo](er-compress-outbound-files.md) máximo é aplicado à saída compactada quando o tamanho real do arquivo pode exceder esse limite. É recomendável selecionar este valor quando você espera que o tamanho da saída gerada seja muito grande.

[![Configurando um destino para um componente de formato de Pasta.](./media/er_destinations-set-unfolding-option.png)](./media/er_destinations-set-unfolding-option.png)

### <a name="limitations"></a>Limitações

Se você definir o campo **Enviar pasta como** para **Separar arquivos** para um componente de **Pasta** que contém outros componentes de **Pasta** aninhada, a configuração não será aplicada recursivamente aos componentes de **Pasta** aninhados.

## <a name="security-considerations"></a>Considerações de segurança

Dois tipos de direitos e privilégios são usados para destinos de ER. Um tipo controla a capacidade geral do usuário de manter os destinos que estão configurados para uma entidade legal (isto é, controla o acesso à página **Destinos de Relatório eletrônico**). O outro tipo controla a capacidade de um usuário do aplicativo de substituir, em tempo de execução, as configurações de destino feitas por um desenvolvedor de ER ou consultor funcional ER.

| Função (nome da AOT)                     | Nome da função                                  | Direito (nome da AOT)                     | Nome da obrigação                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Desenvolvedor de relatório eletrônico             | ERFormatDestinationConfigure        | Configurar destino de formato de relatório eletrônico                |
| ERFunctionalConsultant              | Consultor funcional de relatório eletrônico | ERFormatDestinationConfigure        | Configurar destino de formato de relatório eletrônico                |
| PaymAccountsPayablePaymentsClerk    | Auxiliar de pagamentos de contas a pagar            | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de relatório eletrônico durante o tempo de execução |
| PaymAccountsReceivablePaymentsClerk | Auxiliar de pagamentos de contas a receber         | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de relatório eletrônico durante o tempo de execução |

> [!NOTE]
> Dois privilégios são usados em tarefas anteriores. Esses privilégios têm os mesmos nomes que as tarefas correspondentes: **ERFormatDestinationConfigure** e **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>Importei configurações eletrônicas e vejo na página de configurações de relatório eletrônico. Mas por que eu não os vejo na página de destinos de relatórios eletrônicos?

Selecione **Novo** e, depois, escolha uma configuração no campo **Referência**. A página **Destinos de Relatório eletrônico** mostra apenas as configurações definidas para os destinos.

### <a name="is-there-any-way-to-define-which-microsoft-azure-storage-account-and-azure-blob-storage-are-used"></a>Existe alguma forma de definir qual conta de armazenamento do Microsoft Azure e qual armazenamento de Blob do Azure são usados?

Nº É utilizado o armazenamento de Blob padrão do Microsoft Azure que é definido e usado para o sistema de gerenciamento de documentos.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>Qual é a finalidade do destino do arquivo nas configurações de destino? O que faz essa configuração?

O destino do **Arquivo** é usado para controlar uma caixa de diálogo do navegador da Web quando você executa um formato de ER no modo interativo. Se você habilitar esse destino, ou se nenhum destino for definido para uma configuração, será exibida no seu navegador uma caixa de diálogo para abrir ou salvar após a criação de um arquivo de saída.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>Pode dar um exemplo de fórmula que se refere a uma conta de fornecedor que eu possa enviar e-mail para?

A fórmula é específica da configuração ER. Por exemplo, se você usa a configuração de transferência de crédito ISO 20022, você pode usar **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** ou **model.Payments.Creditor.Identification.SourceID** para obter uma conta de fornecedor associada.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Uma das minhas configurações de formato contém vários arquivos agrupados em uma pasta (por exemplo, Pasta1 contém Arquivo1, Arquivo2 e Arquivo3). Como posso configurar destinos de forma que a Pasta1.zip não seja criada, o Arquivo1 seja enviado por email, o Arquivo2 seja enviado ao SharePoint e eu possa abrir o Arquivo3 logo depois que a configuração for executada?

O formato deve estar disponível primeiro nas configurações ER. Se esse pré-requisito for atendido, abra a página **Destino de relatório eletrônico** e crie uma nova referência para a configuração. Em seguida, você deve ter quatro destinos de arquivo, um para cada componente de saída. Crie o destino do arquivo primeiro, dê a ele um nome como **Pasta** e selecione um nome de arquivo que representa uma pasta na sua configuração. Depois, selecione **Configurações** e certifique-se de que todos os destinos estão desabilitados. Para este destino do arquivo, a pasta não será criada. Por padrão, por causa das dependências hierárquicas entre os arquivos e pastas pai, os arquivos irão se comportar da mesma maneira. Em outras palavras, eles não serão enviados em qualquer lugar. Para substituir esse comportamento padrão, você deve criar três destinos mais de arquivo, um para cada arquivo. Nas configurações de destino de cada um, você deve habilitar o destino em que o arquivo deve ser enviado para.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)

[Configurar destinos de ER dependentes da ação](er-action-dependent-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
