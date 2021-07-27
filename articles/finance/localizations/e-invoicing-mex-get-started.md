---
title: Introdução ao Faturamento eletrônico para o México
description: Este tópico fornece informações que ajudarão você a começar a usar o Faturamento eletrônico para o México.
author: gionoder
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 26091a068ed15ec9ff14c9194c3e0e0ad0779351
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344773"
---
# <a name="get-started-with-electronic-invoicing-for-mexico"></a>Introdução ao Faturamento eletrônico para o México

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> O Faturamento eletrônico para o México no momento talvez não ofereça suporte a todas as funções disponíveis no documento CFDI (Comprovante Fiscal Digital por Internet) e na integração relacionada incorporada ao Microsoft Dynamics 365 Finance ou ao Dynamics 365 Supply Chain Management.

Este tópico fornece informações que ajudarão você a começar a usar o Faturamento eletrônico para o México. Ele o orienta você pelas etapas de configuração que dependem do país para os Regulatory Configuration Services (RCS) e no Finance. Ele também o orienta pelas etapas que devem ser seguidas no Finance para enviar faturas de CFDI pelo serviço e explica como revisar os resultados do processamento e o status de faturas de CFDI.

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir as etapas deste tópico, você deve concluir as etapas em [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Configuração do RCS

Durante a configuração do RCS, você concluirá estas tarefas:

1. Importe o recurso de faturamento eletrônico para processar faturas de CFDI.
2. Examine as configurações de formato necessárias para gerar, enviar e receber respostas sobre as faturas de CFDI e para enviar e receber respostas sobre o cancelamento.
3. Configure os eventos que dão suporte a cenários de envio de fatura de CFDI.
4. Publique o recurso de faturamento eletrônico para faturas de CFDI.

> [!NOTE]
> O "recurso de faturamento eletrônico" é o nome genérico do recurso configurado e publicado para consumir o servidor do faturamento eletrônico. Neste caso, as faturas de CFDI (MX) são o recurso de faturamento eletrônico que você configurará.

## <a name="import-the-e-invoicing-feature"></a>Importar o recurso de faturamento eletrônico

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recursos de globalização**, na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
3. Na página **Recursos de faturamento eletrônico**, selecione **Importar** para importar o recurso **Faturas de CFDI (MX)** do Repositório global.

    > [!NOTE]
    > Se o recurso não for exibido na lista, selecione **Sincronizar** e repita a etapa 3.

![Importar o recurso Faturas de CFDI (MX).](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

Quando você importa o recurso **Faturas de CFDI (MX)** do Repositório global, todas as definições do recurso, incluindo configurações e ações, também são importadas.

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a>Criar uma nova versão do recurso Faturas de CFDI (MX)

Você poderá criar uma nova versão se, por exemplo, as URLs precisarem ser atualizadas. Para obter mais informações, consulte [Faturamento eletrônico CFDI](tasks/mx-00010-e-invoicing-cfdi.md).

- Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione **Novo**.

![Adicionar uma nova versão do recurso de faturamento eletrônico.](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a>Atualizar a versão de configuração

1. Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, selecione **Adicionar** ou **Excluir** para gerenciar as versões de configuração (configurações do formato de arquivo ER).

    ![Gerenciar configurações do recurso de faturamento eletrônico.](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    Quando você cria uma nova versão, todas as configurações são herdadas da última versão publicada. Para processar as faturas de CFDI, são necessárias as seguintes configurações:

    - Fatura de CFDI (BusinessDocumentService)
    - Importação da mensagem de resposta de CFDI
    - Importação de log de erros de CFDI
    - Solicitação de cancelamento de CFDI (MX) (BusinessDocumentService)
    - Fatura de CFDI (BusinessDocumentService)

2. Na lista, selecione uma versão de configuração e, em seguida, selecione **Editar** ou **Exibir** para abrir a página **Designer de formato**, na qual você pode editar ou exibir a configuração.

    ![Abrir a página Designer de formato.](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. Use a página **Designer de formato** para editar e exibir as configurações do arquivo de formato ER. Para obter mais informações, consulte [Criar configurações do documento eletrônico](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md).

    ![Página do designer de formatos.](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Gerenciar as configurações do recurso de faturamento eletrônico

- Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, selecione **Adicionar**, **Excluir** ou **Editar** para gerenciar as configurações do recurso de faturamento eletrônico.

![Gerenciar as configurações do recurso de faturamento eletrônico.](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

Para enviar faturas de CFDI para autorização (gerar o arquivo XML, enviar o arquivo XML e processar a resposta), é necessário configurar o recurso **Fatura de venda**.

Para enviar o cancelamento da fatura de CFDI, são necessárias as configurações de recurso **Cancelamento** e **Cancelar**.

### <a name="configure-the-sales-invoice-feature-setup"></a>Definir a configuração do recurso de fatura de venda

1. Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, na coluna **Configuração do recurso**, selecione **Fatura de venda**.
2. Selecione **Editar** para configurar as ações, regras de aplicabilidade e variáveis.

    ![Editar a configuração do recurso de faturamento eletrônico.](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. Na página **Configuração de versão do recurso**, selecione a guia **Ações** para gerenciar a lista de ações. As ações definem uma lista de operações que devem ser executadas na ordem sequencial para realizar a execução total do evento.

    ![Guia Ações.](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | ID de ação | Ação                   | Nome da ação                                  | Descrição da ação                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | 1         | Transformar documento       | Gerar fatura eletrônica de CFDI sem assinatura digital | Gerar fatura eletrônica de CFDI.                                |
    | 2         | Assinar documento            | Assinatura digital                                 | Assinar digitalmente a fatura eletrônica para envio.                |
    | 3         | Chamar serviço da PAC mexicana | Enviar fatura eletrônica de CFDI                        | O cliente Windows Communication Foundation (WCF) envia a fatura eletrônica de CFDI. |
    | 4         | Processar resposta         | Analisar resposta do serviço Web                 | Analise a resposta do serviço Web e retorne o log de erros. |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a>Configurar a URL para serviços Web da PAC mexicana 

1. Na página **Configuração de versão do recurso**, na guia **Ações**, na Guia Rápida **Ações**, selecione **Chamar serviço da PAC mexicana**.
2. Na Guia Rápida **Parâmetros**, no campo **Endereço da URL**, insira a URL do serviço Web para envio da fatura de CFDI.

> [!NOTE]
> Use as mesmas etapas para atualizar a URL para a ação **Chamar serviço da PAC mexicana** para as configurações de recurso **Cancelar** e **Solicitação de cancelamento**.

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a>Atribuir a versão de rascunho a um ambiente de faturamento eletrônico

1. Na página **Recursos de faturamento eletrônico**, na guia **Ambientes**, selecione **Habilitar**.
2. No campo **Ambiente**, selecione o ambiente.
3. No campo **Efetivo a partir de**, selecione a data em que o ambiente deve entrar em vigor.
3. Selecione **Habilitar**.

![Habilitar um ambiente de faturamento eletrônico.](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a>Alterar o status da versão para Concluído

1. Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione a versão do recurso de faturamento eletrônico que tem o status **Rascunho**.
2. Selecione **Alterar status \> Concluir**.

## <a name="change-the-version-status-to-published"></a>Alterar o status da versão para Publicado

- Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione **Alterar status \> Publicar**.

## <a name="publish-the-e-invoicing-feature"></a>Publicar o recurso de faturamento eletrônico

1. Na página **Recursos de faturamento eletrônico**, selecione a guia **Versões** para gerenciar o status do recurso **Faturas de CFDI (MX)**.
2. Selecione **Alterar status** para alterar o status do recurso.

![Alterar o status do recurso de faturamento eletrônico.](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing--integration-in-finance"></a>Configurar integração do Faturamento eletrônico no Finance

Para configurar o Faturamento eletrônico no Finance, você executará estas tarefas:

1. Importe o modelo de dados ER, o mapeamento do modelo de dados ER e os formatos necessários para faturas de CFDI.
2. Configure tipos de resposta para atualizar as faturas de CFDI. Esses tipos de respostas são usados para a resposta do servidor PAC (provedor de certificação autorizado).

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a>Importar o modelo de dados ER, o mapeamento do modelo de dados ER e as configurações de contexto para faturas de CFDI

1. Entre no Finance.
2. No espaço de trabalho **Relatório eletrônico**, na seção **Provedores de configuração**, selecione o título **Microsoft**. Verifique se este provedor de configuração está definido como **Ativo**. Para obter informações sobre como definir um provedor como **Ativo**, consulte [Criar provedores de configuração e marcá-los como ativos](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Selecione **Repositórios**.
4. Selecione **Recurso global \> Abrir**.
5. Importar **Modelo de fatura**, **Mapeamento de modelo de fatura**, **Formato de fatura de CFDI (MX)**, **Formato de solicitação de cancelamento de fatura de CFDI (MX)** e **Formato de cancelamento de fatura de CFDI (MX)**.

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a>Ativar o recurso de processamento de faturas de CFDI

1. Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
2. Na guia **Recursos**, marque a caixa de seleção **Habilitar** nas linhas para referências do recurso **MX-00010** e **MX-00016**.

![Ativar os recursos de processamento de faturas de CFDI.](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a>Importar configurações de ER e configurar os tipos de resposta para atualizar faturas de CFDI

#### <a name="import-er-configurations"></a>Importar configurações de ER

1. No espaço de trabalho **Relatório eletrônico**, na seção **Provedores de configuração**, selecione o título **Microsoft**.
3. Selecione **Repositórios**.
4. Selecione **Recurso global \> Abrir**.
5. Importe **Modelo de mensagem de resposta**, **Importação de log de erros de CFDI (MX)**, **Importação de log de erros (MX)**.

#### <a name="set-up-the-response-types"></a>Configurar os tipos de resposta

1. Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
2. Na guia **Documento eletrônico**, selecione **Adicionar**.
3. Insira o diário de faturas do cliente e, em seguida, no campo **Nome da tabela**, selecione a fatura do projeto.
4. Para cada tabela, defina um contexto de documento relacionado:

    - Para **Diário de faturas de clientes**, insira **Contexto de fatura de cliente**.
    - Para **Fatura de projeto**, insira **Contexto de fatura de projeto**.

4. Selecione **Tipos de resposta** para configurar os tipos de resposta que podem ser retornados do Faturamento eletrônico e incluídos em um diário de faturas de clientes ou em uma fatura de projeto.
5. Selecione **Novo** e, no campo **Tipo de resposta**, selecione **Resposta**.
6. No campo **Status de envio**, selecione **Pendente**.
7. No campo **Mapeamento de modelos**, selecione **Formato de importação de mensagem de resposta – mapeamento de modelo da mensagem de resposta**.
8. Selecione **Salvar**.
9. Selecione **Novo** e, no campo **Tipo de resposta**, selecione **ResponseData**.
10. No campo **Status de envio**, selecione **Pendente**.
11. No campo **Mapeamento de modelos**, selecione **Formato de importação de dados de resposta de CFDI (detalhes) – importação dos dados de resposta**.
12. Selecione **Salvar**.

## <a name="process-electronic-invoices-in-finance"></a>Processar faturas eletrônicas no Finance 

Durante o processamento de faturas de CFDI no Finance por meio do Faturamento eletrônico, você pode executar as seguintes tarefas:

- Envie faturas de CFDI.
- Exiba os logs de execução de envio.
- Envie o cancelamento de uma fatura de CFDI.

### <a name="submit-cfdi-invoices"></a>Enviar faturas de CFDI

Depois que você ativar o recurso **Integração do Faturamento eletrônico configurável**, o processo **Exportar/Importar fatura eletrônica** (**Contas a receber \> Faturas \> Faturas eletrônicas**) para enviar faturas de CFDI não poderá mais ser usado. Ele é substituído por um novo processo chamado **Enviar documentos eletrônicos**.

> [!NOTE]
> Antes de usar o novo processo **Enviar documentos eletrônicos**, verifique se a configuração necessária para faturas eletrônicas mexicanas foi concluída. Para obter mais informações, consulte [Layout do CFDI versão 3.3](./latam-mex-cfdi-3-3.md).

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Enviar documentos eletrônicos**.
2. Para o primeiro envio de qualquer documento, sempre defina a opção **Reenviar documentos** como **Não**. Se você precisar reenviar um documento pelo serviço, defina esta opção como **Sim**.
3. Na Guia Rápida **Registros a serem incluídos**, selecione **Filtrar** para abrir a caixa de diálogo **Consulta**, na qual você pode criar uma consulta para selecionar documentos para envio.

![Enviar um documento de CFDI.](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> Na primeira tentativa de enviar um documento pelo serviço, você será solicitado a confirmar a conexão com o Faturamento eletrônico. Selecione **Clique aqui para se conectar ao serviço de envio de documentos eletrônicos**.

### <a name="view-submission-logs"></a>Exibir logs de envio

Você pode exibir os logs de envio para todos os documentos enviados ou apenas para um documento enviado.

#### <a name="view-all-submission-logs"></a>Exibir todos os logs de envio

Depois que ativar o recurso **Integração do Faturamento eletrônico configurável**, uma nova página será disponibilizada, permitindo acompanhar o processo de envio do documento. Você pode usar esta página para exibir os logs de envio para todos os documentos enviados.

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.
2. No campo **Tipo de documento**, selecione **Diário de faturas de clientes** para filtrar os documentos eletrônicos necessários.

    ![Selecionar um tipo de documento para exibir os logs de envio.](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. No Painel de Ações, selecione **Consultas \> Detalhes de envio** para exibir os detalhes dos logs de execução de envio.

    ![Exibir os detalhes do log de envio.](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

As informações nos logs de envio são divididas entre as três FastTabs:

- **Ações de processamento** – esta Guia Rápida mostra o log de execução para as ações configuradas na versão do recurso que foi configurada no RCS. A coluna **Status** mostra se a ação foi executada com êxito.
- **Arquivos de ação** – esta Guia Rápida mostra os arquivos intermediários que foram gerados durante a execução das ações. Você pode selecionar **Exibir** para baixar e exibir o arquivo.
- **Log de ação de processamento** – esta FastTab mostra os resultados da comunicação entre o Faturamento eletrônico e o serviço Web de destino. Ela também mostra o que foi retornado pelo processamento do serviço Web. A coluna **Código de erro** mostra o código de retorno que foi retornado pelo serviço Web de autorização.

Quando a fatura de CFDI enviada é autorizada, o status é atualizado para **Aprovado**.

#### <a name="view-submission-logs-from-cfdi-invoices"></a>Exibir logs de envio de faturas de CFDI

Depois que ativar o recurso **Integração do Faturamento eletrônico configurável**, você também poderá exibir os logs de envio de faturas de CFDI.

1. Vá para **Contas a receber \> Consultas e relatórios \> CFDI (faturas eletrônicas)**.
2. Selecione uma fatura de CFDI que foi enviada após a ativação do recurso **Integração do Faturamento eletrônico configurável**.
3. No Painel de Ações, na guia **Histórico**, selecione **Registro de documento eletrônico**.

![Exibir logs de envio de faturas de CFDI.](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> Para faturas de CFDI enviadas antes da ativação do recurso **Integração de Faturamento eletrônico configurável**, o botão **Histórico** está disponível. O botão **Histórico** não está disponível para faturas de CFDI enviadas após a ativação do recurso **Integração de Faturamento eletrônico configurável**.

### <a name="submit-cancellation-of-cfdi-invoices"></a>Enviar cancelamento de faturas de CFDI

Depois que você ativar o recurso **Integração do Faturamento eletrônico configurável**, o processo antigo de cancelamento de faturas de CFDI não poderá mais ser usado. Ele é substituído por um novo processo de cancelamento incorporado na página **Registro de envio de documentos eletrônicos**.

1. Vá para **Contas a receber \> Consultas e relatórios \> CFDI (faturas eletrônicas)**.
2. Se a fatura de CFDI tiver um status **Aprovado**, selecione **Funções \> Cancelar CFDI**.
3. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.
4. Selecione a fatura de CFDI e selecione **Funções \> Enviar envios relacionados**.
5. Insira uma descrição do envio relacionado e selecione **OK**.

#### <a name="view-cancellation-submission-logs"></a>Exibir logs de envio de cancelamento

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.
2. No campo **Tipo de documento**, selecione **Diário de faturas de clientes** para filtrar apenas por documentos do diário de faturas do cliente.
3. Selecione a fatura de CFDI e, no Painel de Ações, selecione **Consultas \> Envio relacionado**.

    A página **Envios relacionados** mostra todas os envios relacionados e o status do envio de determinada fatura de CFDI. Na ilustração a seguir, a primeira linha representa o envio que solicitou aprovação da fatura de CFDI. A segunda linha representa o envio que cancelou essa fatura de CFDI.

    ![Exibir os logs de envio de cancelamento.](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. No Painel de Ações, selecione **Consultas \> Detalhes de envio** para exibir os detalhes dos logs de execução de envio.

    ![Exibir os detalhes do log de envio de cancelamento.](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a>Aviso de privacidade
A habilitação do recurso **Fatura eletrônica mexicana CFDI (MX)** pode exigir o envio de dados limitados, que incluem a ID de registro de imposto da organização. Isso será transmitido a agências de terceiros autorizadas pela autoridade fiscal com a finalidade de enviar faturas eletrônicas a essa autoridade fiscal no formato predefinido exigido para integração com o serviço Web do governo. Um administrador pode habilitar e desabilitar o recurso **Fatura eletrônica mexicana CFDI (MX)** ao navegar até **Administração da organização \> Configuração \> Parâmetros do documento eletrônico**. Selecione a guia **Recursos**, selecione as linhas que contêm o recurso **Fatura eletrônica mexicana CFDI (MX)** e, em seguida, faça a seleção apropriada. Os dados importados desses sistemas externos neste serviço online do Dynamics 365 estão sujeitos à nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=512132). Consulte as seções de aviso de privacidade da documentação de recursos específicos do país para obter mais informações.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md)
- [Configurar Faturamento eletrônico](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]