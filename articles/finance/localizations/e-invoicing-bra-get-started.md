---
title: Introdução ao complemento de faturamento eletrônico para o Brasil
description: Este tópico fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico para o Brasil no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: fb3ec2d60875d7a0747d64b397aafaa0a3d26348
ms.sourcegitcommit: f860ac2b18f6bbbfc4a46b497baec2477105b116
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2020
ms.locfileid: "4440532"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Introdução ao complemento de faturamento eletrônico para o Brasil 

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> O complemento de faturamento eletrônico para o Brasil no momento não oferece suporte a todas as funções disponíveis na integração da nota fiscal incorporada ao Microsoft Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management.

Este tópico fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico para o Brasil. Ele orienta você pelas etapas de configuração que dependem do país para os Regulatory Configuration Services (RCS) e no Finance e no Supply Chain Management. Ele também orienta você no processo de envio de uma NF-e (modelo de nota fiscal eletrônica 55) pelo serviço e explica como revisar os resultados do processamento e o status das notas fiscais.

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir as etapas deste tópico, você deve concluir as etapas em [Introdução ao complemento do faturamento eletrônico](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Configuração do RCS

Durante a configuração do RCS, você concluirá estas tarefas:

1. Importe o recurso de faturamento eletrônico para NF-e.
2. Revise os formatos de arquivo necessários para enviar as NF-e para autorização.
3. Revise os formatos de arquivo necessários para solicitar o cancelamento de uma NF-e aprovada.
4. Configure o evento necessário para enviar as NF-e para autorização.
5. Configure o evento necessário para solicitar o cancelamento de uma NF-e aprovada.
6. Atribua o recurso de faturamento eletrônico a um ambiente de complemento de faturamento eletrônico.
7. Publique o recurso de faturamento eletrônica.

> [!NOTE]
> O "recurso de faturamento eletrônico" é o nome genérico do recurso configurado e publicado para consumir o servidor do complemento de faturamento eletrônico. A configuração do recurso de faturamento eletrônico combina, entre outras coisas, o uso de formatos de configuração de Relatório eletrônico (RE) para criar arquivos de exportação e importação configuráveis, e o uso de ações e de fluxos de ações para habilitar a criação de regras configuráveis para enviar solicitações, importar respostas e analisar o conteúdo de respostas.

## <a name="import-the-e-invoicing-feature"></a>Importar o recurso de faturamento eletrônico

1. Entrar em sua conta do RCS
2. No espaço de trabalho **Recursos de globalização**, na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
3. Na página **Recursos de faturamento eletrônico**, selecione **Importar** para importar um recurso de faturamento eletrônico de NF-e do repositório Global.

    ![Botão Importar](media/e-Invoicing-services-get-started-BRA-Select-Import-e-Invoicing-feature.png)

4. Selecione o recurso de NF-e e, em seguida, selecione **Importar**.

    ![Importando o recurso de NF-e](media/e-Invoicing-services-get-started-BRA-Select-Import-NF-e-feature.png)

### <a name="create-a-new-version-of-the-nf-e-fiscal-document-feature"></a>Criar uma versão do recurso de NF-e

- Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione **Novo**.

![Adicionar uma nova versão do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-BRA-Select-New-e-Invoicing-feature-version.png)

### <a name="update-the-configuration-version"></a>Atualizar a versão de configuração

1. Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, selecione **Adicionar** ou **Excluir** para gerenciar as versões de configuração (configurações do formato de arquivo ER).

    ![Gerenciar configurações do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-configurations.png)

    - Ao criar uma versão do recurso de NF-e, todas as versões de configuração (formatos de arquivo de RE) são herdadas da versão mais recente.
    - Para enviar a NF-e para autorização, são necessárias as seguintes versões de configuração:

        - Formato de exportação de envio da NF-e
        - Importação da mensagem de resposta da NF-e
        - Importação de log de erros da NF-e

    - Para enviar o cancelamento da NF-e, é necessária a seguinte versão de configuração:

        - Formato de exportação de cancelamento da NF-e

2. Na lista, selecione uma versão de configuração e, em seguida, selecione **Editar** ou **Exibir** para abrir a página **Designer de formato**, na qual você pode editar ou exibir a configuração.

    ![Abrir a página Designer de formato](media/e-Invoicing-services-get-started-BRA-Configuration-ER-fomat-designer.png)

3. Use a página **Designer de formato** para editar ou exibir as configurações do arquivo de formato do RE. Para obter mais informações, consulte [Criar configurações do documento eletrônico](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Página do designer de formatos](media/e-Invoicing-services-get-started-BRA-ER-Format-designer.png)

### <a name="manage-the-e-invoicing-feature-setups"></a>Gerenciar as configurações do recurso de faturamento eletrônico

- Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, selecione **Adicionar** ou **Excluir** para gerenciar as configurações do recurso de faturamento eletrônico (ou seja, eventos de NF-e).

![Gerenciar as configurações do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-BRA-Manage-e-Invoicing-feature-setup.png)

Quando você cria uma versão do recurso de NF-e que é derivada de outro recurso de faturamento eletrônico, todas as configurações do recurso (eventos de NF-e) são herdadas da versão mais recente.

Para enviar as NF-e para autorização, é necessário configurar o recurso **Enviar**.

Para enviar o cancelamento de NF-e, é necessário configurar o recurso **Cancelamento**.

#### <a name="configure-the-submit-feature-setup"></a>Definir a configuração do recurso Enviar

1. Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, na coluna **Configuração do recurso**, selecione **Enviar**.
2. Selecione **Editar**.

    ![Editar configuração do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-BRA-Edit-e-Invoicing-feature-setup.png)

3. Na página **Configuração de versão do recurso**, selecione a guia **Ações** para gerenciar a lista de ações.

    ![Guia Ações](media/e-Invoicing-services-get-started-BRA-Select-Actions.png)

4. Revise as ações necessárias para enviar uma NF-e para autorização.

    | ID de ação | Nome da ação                  | Descrição da ação                                                |
    |-----------|------------------------------|-------------------------------------------------------------------|
    | 1         | Transformar documento           | Crie o arquivo XML da NF-e para envio.                          |
    | 2         | Assinar documento                | Aplique o certificado digital ao arquivo XML.                    |
    | 3         | Chamar serviço da SEFAZ do Brasil | Envie o arquivo XML assinado para os serviços Web para autorização. |
    | 4         | Processar resposta             | Obtenha a resposta do serviço Web.                                     |
    | 5         | Transformar documento           | Analise o conteúdo do arquivo recebido como resposta.     |
    | 6         | Transformar documento           | Crie o arquivo XML para consultar o status do envio.    |
    | 7         | Chamar serviço da SEFAZ do Brasil | Envie o arquivo XML que solicita o status do envio.          |
    | 8         | Processar resposta             | Obtenha a resposta do serviço Web.                                     |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Configurar a URL para os serviços Web da SEFAZ 

1. Na página **Configuração de versão do recurso**, na guia **Ações**, na Guia Rápida **Ações**, selecione **Chamar serviço da SEFAZ do Brasil** (ID da ação **3**).
2. Na Guia Rápida **Parâmetros**, no campo **Parâmetro de endereço de URL**, insira a URL do serviço Web da SEFAZ para o envio de NF-e.
3. Na Guia Rápida **Ações**, selecione **Chamar serviço da SEFAZ do Brasil** (ID da ação **7**).
4. Na Guia Rápida **Parâmetros**, no campo **Parâmetro de endereço de URL**, insira a URL do serviço Web da SEFAZ para o envio de NF-e.

#### <a name="configure-the-cancellation-feature-setup"></a>Definir a configuração do recurso Cancelamento

1. Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, na coluna **Configuração do recurso**, selecione **Cancelamento**.
2. Selecione **Editar**.
3. Na página **Configuração de versão do recurso**, selecione a guia **Ações** para gerenciar a lista de ações.
4. Revise as ações necessárias para solicitar o cancelamento de uma NF-e aprovada.

    | ID de ação | Nome da ação                  | Descrição da ação                                               |
    |-----------|------------------------------|------------------------------------------------------------------|
    | 1         | Transformar documento           | Crie o arquivo XML de cancelamento da NF-e para envio.            |
    | 2         | Assinar documento                | Aplique o certificado digital ao arquivo XML.                   |
    | 3         | Chamar serviço da SEFAZ do Brasil | Envie o arquivo XML assinado para os serviços Web para cancelamento. |
    | 4         | Processar resposta             | Obtenha a resposta do serviço Web.                                    |

#### <a name="set-up-the-url-for-sefaz-web-services"></a>Configurar a URL para os serviços Web da SEFAZ

1. Na página **Configuração de versão do recurso**, na guia **Ações**, na Guia Rápida **Ações**, selecione **Chamar serviço da SEFAZ do Brasil** (ID da ação **3**).
2. Na Guia Rápida **Parâmetros**, no campo **Parâmetro de endereço de URL**, insira a URL do serviço Web da SEFAZ para o cancelamento de uma NF-e aprovada.

### <a name="make-an-e-invoicing-environment-available-and-assign-a-draft-version"></a>Disponibilizar um ambiente de faturamento eletrônico e atribuir uma versão de rascunho

1. Na página **Recursos de faturamento eletrônico**, na guia **Ambientes**, selecione **Habilitar**.
2. No campo **Ambiente**, selecione o ambiente.
3. No campo **Efetivo a partir de**, selecione a data em que o ambiente deve entrar em vigor.
4. Selecione **Habilitar**.

![Habilitar um ambiente de faturamento eletrônico](media/e-Invoicing-services-get-started-BRA-Enable-e-Invoicing-environment.png)

### <a name="change-the-status-to-completed"></a>Alterar o status para Concluído

1. Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione a versão do recurso de faturamento eletrônico que tem o status **Rascunho**.
2. Selecione **Alterar status \> Concluir**.

### <a name="change-the-status-to-publish"></a>Alterar o status para Publicar

1. Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione a versão do recurso de faturamento eletrônico que tem o status **Concluído**.
2. Selecione **Alterar status \> Publicar**.

![Publicando o recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-BRA-Publish-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Configurar a integração do Complemento de faturamento eletrônico no Finance ou no Supply Chain Management

Durante a configuração, você concluirá estas tarefas:

1. Ative o recurso de NF-e Federal para o Brasil.
2. Importe o modelo de dados RE específicos, o mapeamento do modelo de dados e os formatos necessários para as NF-e.
3. Importe a configuração de RE e configure os tipos de resposta necessários para atualizar o status da nota fiscal depois que o processo de envio for retornado.

### <a name="turn-on-the-nf-e-federal-feature-for-brazil"></a>Ativar o recurso de NF-e Federal para o Brasil

1. Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
2. Na guia **Recursos**, marque a caixa de seleção **Habilitar** na linha para a referência do recurso **BR00053**.

### <a name="import-the-er-data-model-mapping-required-for-nf-e-fiscal-documents"></a>Importar o mapeamento do modelo de dados de RE necessário para as NF-e

1. Entre no Finance.
2. No espaço de trabalho **Relatório eletrônico**, na seção **Provedores de configuração**, selecione o bloco **Microsoft**. Verifique se este provedor de configuração está definido como **Ativo**. Para obter informações sobre como definir um provedor como **Ativo**, consulte [Criar provedores de configuração e marcá-los como ativos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Selecione **Repositórios**.
4. Selecione **Recurso global \> Abrir**.
5. Importe as configurações de **Mapeamento de notas fiscais**.

### <a name="import-er-configurations-and-set-up-the-response-types-for-fiscal-documents"></a>Importar configurações de RE e configurar os tipos de resposta para notas fiscais

1. No espaço de trabalho **Relatório eletrônico**, na seção **Provedores de configuração**, selecione o bloco **Microsoft**.
2. Selecione **Repositórios**.
3. Selecione **Recurso global \> Abrir**.
4. Importe a **Importação de log de erros da NF-e (BR)**, o **formato de importação dos dados de resposta da NF-e (Br)** e a **Importação da mensagem de resposta da NF-e (BR)**.
5. Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
6. Na guia **Documento eletrônico**, selecione **Adicionar**.
6. No campo **Nome da tabela**, insira o **Cabeçalho da nota fiscal**.
7. No campo **Contexto do documento**, selecione **Modelo de contexto da nota fiscal do cliente – Contexto da nota fiscal**.
8. Selecione **Tipos de resposta**.
9. Selecione **Novo** e, no campo **Tipo de resposta**, selecione **Resposta**.
10. No campo **Status de envio**, selecione **Pendente**.
11. No campo **Mapeamento de modelos**, selecione **Formato de importação de mensagem de resposta – mapeamento de modelo da mensagem de resposta**.
12. Selecione **Salvar**.
13. Selecione **Novo** e, no campo **Tipo de resposta**, insira **ResponseData**.
14. No campo **Status de envio**, selecione **Pendente**.
15. No campo **Mapeamento de modelos**, selecione **Formato de importação dos dados de resposta da NF-e – Importação dos dados de resposta**.
16. Selecione **Salvar**.

## <a name="electronic-invoice-processing"></a>Processamento de fatura eletrônica

Durante o processamento no Finance, você concluirá estas tarefas:

1. Envie uma nota fiscal por meio do complemento de faturamento eletrônico.
2. Exiba os logs de execução de envio e revise os resultados do processamento.
3. Envie o cancelamento de uma nota fiscal por meio do complemento de faturamento eletrônico.

### <a name="submit-nf-e-fiscal-documents-for-sefaz-authorization"></a>Enviar NF-e para autorização da SEFAZ 

Depois que você ativar o recurso **Integração do complemento de faturamento eletrônico configurável**, o processo antigo de envio de NF-e para autorização (**Processo de exportação/importação de NF-e**) não poderá mais ser usado. Ele é substituído por um novo processo chamado **Enviar documentos eletrônicos**.

> [!NOTE]
> Antes de continuar, verifique se você tem um ou mais modelos 55 de notas fiscais do cliente que foram emitidos pelo estabelecimento fiscal do cliente. A direção dessas notas fiscais deve ser definida como **Saída** e o status deve ser **Criado**. Para obter mais informações, consulte [Emitir nota fiscal do cliente (Brasil)](https://docs.microsoft.com/dynamics365/finance/localizations/tasks/br-00038-issuing-customer-fiscal-document).

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Enviar documentos eletrônicos**.
2. Para o primeiro envio de qualquer documento, sempre defina a opção **Reenviar documentos** como **Não**. Se você precisar reenviar um documento pelo serviço, defina esta opção como **Sim**.
3. Na Guia Rápida **Registros a serem incluídos**, selecione **Filtrar** para abrir a caixa de diálogo **Consulta**, na qual você pode criar uma consulta para selecionar documentos para envio.
4. Na guia **Intervalo**, selecione **Adicionar**.
5. No campo **Tabela**, selecione **Cabeçalho da nota fiscal**.
6. No campo **Tabela derivada**, selecione **Cabeçalho da nota fiscal**.
6. No campo **Campo**, selecione **Número**.
7. No campo **Critérios**, insira o número da nota fiscal que deve ser enviada.
8. Selecione **OK** para fechar a caixa de diálogo **Consulta**.
8. Selecione **OK** para enviar os documentos selecionados.

> [!NOTE]
> Na primeira tentativa de enviar um documento pelo serviço, você será solicitado a confirmar a conexão com o complemento do faturamento eletrônico. Selecione **Clique aqui para se conectar ao serviço de envio de documentos eletrônicos**.

### <a name="view-all-submission-logs"></a>Exibir todos os logs de envio

Depois que ativar o recurso **Integração do complemento de faturamento eletrônico configurável**, uma nova página será disponibilizar que permitirá acompanhar o processo de envio do documento. Você pode usar esta página para exibir os logs de envio para todos os documentos enviados.

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.
2. No campo **Tipo de documento**, selecione **Cabeçalho da nota fiscal** para filtrar somente notas fiscais.
3. No Painel de Ações, selecione **Consultas \> Detalhes de envio** para exibir os detalhes dos logs de execução de envio.

![Exibir os detalhes do log de envio](media/e-Invoicing-services-get-started-BRA-View-Submission-log-details.png)

> [!NOTE] 
> Para NF-e, a coluna **Código de erro** mostra o código de retorno que foi devolvido pelo serviços Web da SEFAZ.

### <a name="view-submission-logs-through-the-fiscal-document-page"></a>Exibir logs de envio pela página da nota fiscal

Depois que ativar o recurso **Integração do suplemento de faturamento eletrônico configurável**, você também poderá exibir os logs de envio por meio da página da nota fiscal.

1. Acesse **Contabilidade \> Consultas e relatórios \> Notas fiscais \> Todas as notas fiscais**.
2. Selecione uma nota fiscal que tenha sido enviada anteriormente por meio do complemento de faturamento eletrônico.
3. No Painel de Ações, na guia **NF-e Federal**, selecione **Registro de documento eletrônico**.

![Exibindo logs de envio pela página da nota fiscal](media/e-Invoicing-services-get-started-BRA-View-Submission-log-from-Fiscal-document-viewer.png)

### <a name="submit-approved-nf-e-fiscal-documents-for-sefaz-cancellation"></a>Enviar NF-e aprovada para cancelamento da SEFAZ

Depois que você ativar o recurso **Integração do complemento de faturamento eletrônico configurável**, o processo antigo de cancelamento de NF-e não poderá mais ser usado. Ele é substituído por um novo processo de cancelamento incorporado na página **Registro de envio de documentos eletrônicos**.

> [!NOTE]
> Verifique se você executou o cancelamento da nota fiscal do cliente para uma NF-e aprovada. Para obter mais informações, consulte [Cancelar nota fiscal do cliente (Brasil)](https://docs.microsoft.com/dynamics365/finance/localizations/latam-bra-cancel-customer-fiscal-documents).

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.
2. Selecione a nota fiscal e selecione **Funções \> Enviar envios relacionados**.
3. Insira uma descrição do envio relacionado e selecione **OK**.

### <a name="view-cancellation-submission-logs"></a>Exibir logs de envio de cancelamento

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.
2. No campo **Tipo de documento**, selecione **Cabeçalho da nota fiscal** para filtrar somente notas fiscais.
3. Selecione a nota fiscal e, no painel de Ações, selecione **Consultas \> Envio relacionado**.

    Os envios relacionados são envios que estão relacionados a um envio principal que foi feito primeiro. Por exemplo, o envio que autoriza uma NF-e específica é o envio principal. O envio que solicita o cancelamento da mesma NF-e na SEFAZ é um envio relacionado. Ele existe somente porque está solicitando o cancelamento do trabalho realizado por outro envio.

    A página **Envios relacionados** mostra todas os envios relacionados e o status do envio de uma determinada nota fiscal. Na ilustração a seguir, a primeira linha representa o envio que solicitou a aprovação da nota fiscal. A segunda linha representa o envio que cancelou essa nota fiscal.

    ![Exibir os logs de envio de cancelamento](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log.png)

4. No Painel de Ações, selecione **Consultas \> Detalhes de envio** para exibir os detalhes dos logs de execução de envio.

    ![Exibir os detalhes do log de envio de cancelamento](media/e-Invoicing-services-get-started-BRA-View-Cancellation-Submission-log-details.png)

## <a name="privacy-notice"></a>Aviso de privacidade
Habilitar o recurso BR-00053 (NF-e Federal) pode exigir o envio de dados limitados, que inclui a ID de registro de imposto da organização. Isso será transmitido a agências de terceiros autorizadas pela autoridade fiscal com a finalidade de enviar faturas eletrônicas a essa autoridade fiscal no formato predefinido exigido para integração com o serviço Web do governo. Um administrador pode habilitar e desabilitar o recurso BR-00053 (NF-e Federal) navegando até **Administração da organização \> Configurar \> Parâmetros do documento eletrônico**. Selecione a guia **Recursos**, selecione a linha que contém o recurso BR-00053 e, em seguida, faça a seleção apropriada. Os dados importados desses sistemas externos neste serviço online do Dynamics 365 estão sujeitos à nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte as seções de aviso de privacidade na documentação de recursos específicos do país para obter mais informações.


## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do complemento de faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução ao complemento de faturamento eletrônico](e-invoicing-get-started.md)
- [Configurar o complemento de faturamento eletrônico](e-invoicing-setup.md)
