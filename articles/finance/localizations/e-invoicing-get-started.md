---
title: Introdução ao complemento de faturamento eletrônico
description: Este tópico fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 10/08/2020
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
ms.openlocfilehash: 7b2a3aae43d42060c7fcd9e1ea3db814fc5d8f22
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039837"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Introdução ao complemento de faturamento eletrônico

[!include [banner](../includes/banner.md)]

Este tópico fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico. Primeiro, ele orienta você nas etapas de configuração no Microsoft Dynamics Lifecycle Services (LCS), no Regulatory Configuration Services (RCS) e no Dynamics 365 Finance. Em seguida, ele descreve o processo de envio de documentos por meio do serviço usando o Dynamics 365 Finance ou o Dynamics 365 Supply Chain Management. Você também aprenderá a interpretar os logs de envio.

## <a name="availability"></a>Disponibilidade

O complemento de faturamento eletrônico está inicialmente disponível para vários países. O suplemento oferece suporte à criação de faturas eletrônicas e ao envio dos seguintes documentos comerciais:

| País/Região  | Documento comercial                          |
|-----------------|--------------------------------------------|
| Áustria         | Faturas de vendas e de projetos                 |
| Bélgica         | Faturas de vendas e de projetos                 |
| Brasil          | Documento fiscal eletrônico modelo 55 (NF-e) |
| Dinamarca         | Faturas de vendas e de projetos                 |
| Estônia         | Faturas de vendas e de projetos                 |
| Finlândia         | Faturas de vendas e de projetos                 |
| França          | Faturas de vendas e de projetos                 |
| Alemanha         | Faturas de vendas e de projetos                 |
| Itália           | Faturas de vendas e de projetos                 |
| México          | Fatura CFDI                               |
| Países Baixos     | Faturas de vendas e de projetos                 |
| Noruega          | Faturas de vendas e de projetos                 |
| Espanha           | Faturas de vendas e de projetos                 |
| Europa          | Faturas de vendas e de projetos PEPPOL          |
    
## <a name="licensing"></a>Licenciamento

Você pode usar o Complemento de faturamento eletrônico com sua licença atual. Nenhuma licença adicional é necessária para usar o serviço.

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir as etapas neste tópico, você precisa preencher os seguintes pré-requisitos:

- Acesso à sua conta LCS.
- Um projeto de implantação do LCS que inclui o Finance ou o Supply Chain Management versão 10.0.13 ou posterior.
- Acesso à sua conta RCS.
- Ative o recurso Globalização para sua conta RCS por meio do módulo **Gerenciamento de recursos**. Para obter mais informações, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md)
- Crie um recurso de cofre de chaves e uma conta de armazenamento no Azure. Para obter mais informações, consulte [Criar conta de armazenamento do Azure e cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="overview"></a>Visão Geral

A ilustração a seguir mostra as cinco etapas principais que serão concluídas neste tópico.

![Visão geral das cinco etapas deste tópico](media/e-invoicing-services-get-started-overview-5-steps.png)

1. **Configuração de recursos do Azure:** configure o armazenamento do Azure e o carregamento de certificados digitais no Azure Key Vault.
2. **Configuração do LCS:** instale o complemento para microsserviços.
3. **Configuração do RCS:** configure os recursos de ambiente, acesso de usuário e faturamento eletrônico.
4. **Configuração do cliente:** configure a conexão entre o cliente e o Complemento de faturamento eletrônico e desative os recursos antigos para enviar e receber respostas de documentos eletrônicos.
5. **Enviar faturas:** enviar documentos eletrônicos por meio do Complemento de faturamento eletrônico e receber respostas.

> [!NOTE]
> Algumas etapas de configuração neste tópico são comuns e independem do país/região. As etapas e procedimentos de configuração específicos de país/região são descritos em tópicos específicos de país/região.

## <a name="lcs-setup"></a>Configuração do LCS

1. Entre em sua conta do LCS.
2. Selecione o bloco **Gerenciamento de versão preliminar pública** e, no grupo de campos **Recursos de versão preliminar pública** , selecione **BusinessDocumentSubmission**.
3. Marque o campo **Recurso de versão preliminar habilitado**.
4. Selecione o projeto de implantação de LCS. Antes de poder selecionar o projeto, ele deve estar em execução.
5. Na Guia Rápida **Complementos do ambiente** , selecione **Instalar um novo complemento**.
6. Selecione **Envio de Documento Comercial**.
7. Na caixa de diálogo **Suplemento de configuração** , no campo **ID do aplicativo do AAD** , insira **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Esse valor é um valor fixo.
8. No campo **ID de locatário AAD** , insira a ID da sua conta de assinatura do Azure.

    ![Caixa de diálogo Suplemento de configuração no LCS](media/e-invoicing-services-get-started-lcs-addin-setup.png)

9. Marque a caixa de seleção para aceitar os termos e condições.
10. Selecione **Instalar**.

## <a name="rcs-setup"></a>Configuração do RCS

Durante a configuração do RCS, você concluirá estas tarefas:

1. Configure o cofre de chaves no RCS.
2. Configure a integração do RCS com o servidor do Complemento de faturamento eletrônico.
3. Crie um ambiente do Complemento de faturamento eletrônico para sua organização.

### <a name="set-up-the-key-vault-in-rcs"></a>Configurar o cofre de chaves no RCS

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recursos de globalização** , na seção **Ambientes** , selecione o bloco **Faturamento eletrônico**.
3. Selecione **Ambientes de serviço**.

    ![Selecionar Ambientes de serviço](media/e-invoicing-services-get-started-select-service-environments.png)

> [!NOTE]
> A opção **Aplicativos conectados** concede acesso para a configuração automática do Complemento de faturamento eletrônico no Finance ou no Supply Management por meio do RCS. No entanto, esse recurso ainda está em desenvolvimento.

4. No Painel de Ações, selecione **Parâmetros de Key Vault**.

    ![Selecionar parâmetro de Key Vault](media/e-invoicing-services-get-started-select-key-vault-parameters.png)

5. No Painel de Ações, selecione **Novo** para adicionar um cofre de chaves.
6. No campo **URI do Key Vault** , insira o valor do atributo **Nome do DNS** do recurso cofre de chaves configurado no Azure. Para obter informações sobre onde encontrar o valor **Nome do DNS** , consulte [Criar conta de armazenamento do Azure e Key Vault](e-invoicing-create-azure-storage-account-key-vault.md).

    ![Campo URI do Key Vault](media/e-invoicing-services-get-started-enter-key-vault-uri.png)

7. Na Guia Rápida **Certificados** , selecione **Adicionar** para inserir todos os nomes de certificado digital e segredos do cofre de chaves necessários para estabelecer conexões confiáveis. Na coluna **Tipo** , você pode especificar se é um Certificado ou um Segredo. Os dois conjuntos de valores são configurados no recurso cofre de chaves no Azure.

    ![Adicionar certificados](media/e-invoicing-services-get-started-add-digital-certificates.png)

8. Se a fatura específica de país/região exigir uma cadeia de certificados para aplicar uma assinatura digital, selecione **Cadeia de certificados** no Painel de Ações e digite a sequência de certificados ou segredos do cofre de chaves que compõem a cadeia.

### <a name="set-up-the-rcs-integration-with-the-electronic-invoicing-add-on-server"></a>Configurar a integração do RCS com o servidor do Complemento de faturamento eletrônico

1. No espaço de trabalho **Recursos de globalização** , na seção **Configurações relacionadas** , selecione o link **Parâmetros de relatório eletrônico**.
2. Selecione **Clique aqui para conectar-se ao Lifecycle Service**. Se não desejar se conectar ao LCS, selecione **Cancelar**.
3. Na guia **Serviços de faturamento eletrônico** , no campo **URI de ponto de extremidade de serviço** , insira o valor de acordo com as regiões geográficas disponíveis: `https://businessdocumentsubmission.us.operations365.dynamics.com/` ou `https://businessdocumentsubmission.eu.operations365.dynamics.com/`.
4. No campo **ID do aplicativo** , verifique se ele mostra a ID **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Esse valor é um valor fixo.
5. No campo **ID de Ambiente do LCS** , insira a ID da sua conta de assinatura do LCS.

![Inserir parâmetros de Complemento de faturamento eletrônico](media/e-invoicing-services-get-started-enter-e-invoicing-parameters.png)

### <a name="add-an-electronic-invoicing-add-on-environment"></a>Adicionar um ambiente de Complemento de faturamento eletrônico

Você pode criar diferentes ambientes para o Complemento de faturamento eletrônico, como Desenvolvimento, Teste ou Produção.

1. No espaço de trabalho **Recursos de globalização** , na seção **Ambientes** , selecione o bloco **Faturamento eletrônico**.
2. Selecione **Novo** para criar um ambiente.
3. No campo **Conta de token SAS de armazenamento** , insira o nome do segredo do cofre de chaves que você configurou no cofre de chaves no RCS.

    ![Campo Conta de token SAS de armazenamento](media/e-invoicing-services-get-started-enter-sas-token-secret.png)

4. Na Guia Rápida **Usuários** , selecione **Novo** para conceder acesso a usuários para esse ambiente.

    ![Adicionar usuários de serviço](media/e-invoicing-services-get-started-enter-service-users.png)

5. No Painel de Ações, selecione **Publicar** para publicar o ambiente no servidor do Complemento de faturamento eletrônico.

    ![Botão Publicar](media/e-invoicing-services-get-started-publish-service-environment.png)

### <a name="e-invoicing-feature-setup"></a>Configuração do recurso de faturamento eletrônico

O "recurso de faturamento eletrônico" é o nome genérico do recurso configurado e publicado para consumir o servidor do complemento de faturamento eletrônico. A configuração do recurso de faturamento eletrônico combina, entre outras coisas, o uso de formatos de configuração de Relatório eletrônico (ER) para criar arquivos de exportação e importação configuráveis, e o uso de ações e de fluxos de ação para habilitar a criação de regras configuráveis para enviar solicitações, importar respostas e analisar o conteúdo de respostas.

Devido a variações nos formatos de fatura e fluxos de ação, a configuração do recurso de faturamento eletrônico depende do país/região.

## <a name="set-up-electronic-invoicing-add-on-integration-in-finance-or-supply-chain-management"></a>Configurar a integração do Complemento de faturamento eletrônico no Finance ou no Supply Chain Management 

Durante esta configuração, você concluirá as seguintes tarefas:

1. Abrir recurso liberado
2. Ative o recurso de integração Complemento de faturamento eletrônico para habilitar a integração com o Finance.
3. Configure a URL do ponto de extremidade de Complemento de faturamento eletrônico.
4. Importe as configurações ER relacionadas ao recurso de faturamento eletrônico específico de país/região.
5. Ative o recurso de faturamento eletrônico específico do país/região aplicável.
6. Importe as configurações de ER e configure os tipos de resposta necessários para atualizar seu documento de fatura específico de país/região como resultado do processo de envio.

### <a name="open-flighted-feature"></a>Abrir recurso liberado
O recurso Integração de fatura eletrônica é habilitado via liberação. A liberação é um conceito que permite que um recurso esteja ATIVADO ou DESATIVADO por padrão. As etapas a seguir permitem uma liberação em um ambiente de não produção. 

1. Execute o seguinte comando SQL:

    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)
    
2. Depois de fazer a alteração acima, execute um IISReset em todos os itens do AOS

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Ativar o recurso Integração do complemento de faturamento eletrônico

1. Entre no Finance ou no Supply Chain Management.
2. No espaço de trabalho **Gerenciamento de recursos** , procure o novo recurso, **Integração do complemento de faturamento eletrônico configurável**. Se o recurso ainda não aparecer na página Gerenciamento de recursos, execute a função **Verificar se há atualizações**
3. Selecione o recurso e **Habilitar agora**.

### <a name="set-up-the-service-endpoint-url"></a>Configurar a URL do ponto de extremidade de serviço

1. Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
2. Na guia **Serviço de envio** , no campo **URL de ponto de extremidade do serviço** , insira `https://businessdocumentsubmission.us.operations365.dynamics.com/`.
3. No campo **Ambiente** , insira o nome do ambiente de Complemento de faturamento eletrônico criado durante a configuração do RCS.

![Inserir parâmetros de serviço](media/e-invoicing-services-get-started-enter-service-endpoint.png)

### <a name="import-the-er-configurations"></a>Importar as configurações de ER

Para habilitar os dados comerciais a serem coletados e enviados ao Complemento de faturamento eletrônico, você deve importar o modelo de dados ER e a configuração de modelo de dados ER que estão relacionados ao recurso de faturamento eletrônico específico de país/região que você deseja usar.

1. No espaço de trabalho **Relatório eletrônico** , na seção **Provedores de configuração** , selecione o bloco **Microsoft**. Verifique se este provedor de configuração está definido como **Ativo**. Para obter informações sobre como definir um provedor como **Ativo** , consulte [Criar provedores de configuração e marcá-los como ativos](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).
3. Selecione **Repositórios**.
4. Selecione **Recurso global** e, depois, **Abrir**.
5. Na caixa de diálogo **Conectar-se ao Lifecycle Services** , selecione **Clique aqui para conectar-se ao Lifecycle Service**.
6. Dependendo do país ou região em que você deseja usar o recurso de faturamento eletrônico, você deve importar o modelo de dados aplicável, o mapeamento do modelo de dados e os formatos. Para obter informações sobre as configurações de ER que devem ser importadas, consulte o tópico específico de país/região "Introdução ao Complemento de faturamento eletrônico".
7. Importar **Modelo de contexto de fatura de cliente**. Esse modelo contém parâmetros adicionais que descrevem, entre outras coisas, o ambiente no Finance usado para o Complemento de faturamento eletrônico durante o envio de dados corporativos.

### <a name="turn-on-countryregion-specific-e-invoicing-features"></a><a name="region-specific"></a>Ativar recursos de faturamento eletrônico específicos de país/região

Para ativar os recursos de faturamento eletrônico específicos de país/região para que funcionem com o Complemento de faturamento eletrônico, você deve ativar o recurso em cada entidade legal na qual deseja usá-lo. Depois disso, a integração de faturamento eletrônico anterior não poderá mais ser usada e a integração com o novo Complemento de faturamento eletrônico será ativada.

1. Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
2. Na guia **Recursos** , na linha do recurso relacionado ao seu recurso de faturamento eletrônico específico de país/região, marque a caixa de seleção na coluna **Habilitado**. Para obter informações sobre o recurso que deve ser ativado, consulte o tópico específico de país/região "Introdução ao Complemento de faturamento eletrônico".

![Ativar o recurso de faturamento eletrônico](media/e-invoicing-services-get-started-enable-invoicing-feature.png)

> [!NOTE]
> Se você tiver várias entidades legais configuradas para diferentes países ou regiões, poderá ativar o recurso de faturamento eletrônico específico de país/região para cada entidade legal.

### <a name="import-er-configurations-and-set-up-the-response-types-to-update-your-countryregion-specific-invoice-document"></a>Importar configurações ER e configurar os tipos de resposta para atualizar o documento de fatura específico de país/região

Se o documento de fatura enviado exigir uma atualização após a resposta do envio para os serviços de autorização do governo, você deverá importar um modelo de dados e configurações especiais para habilitar o status do documento da fatura ou de qualquer outro campo adicional a ser atualizado.

1. No espaço de trabalho **Relatório eletrônico** , na seção **Provedores de configuração** , selecione o bloco **Microsoft**.
2. Selecione **Repositórios**.
3. Selecione **Recurso global** e, depois, **Abrir**.
4. Importe **Modelo de mensagem de resposta** , **Formato de importação de mensagem de resposta** , **Mapeamento do modelo de mensagem de resposta para destino** e **Formato de importação de conteúdo de arquivo**.
5. Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
6. Na guia **Documento eletrônico** , selecione **Adicionar** para inserir o nome da tabela que está relacionada ao documento de fatura específico do país/região. Para obter informações sobre nomes de tabelas a serem selecionados, consulte o tópico específico de país/região "Introdução ao Complemento de faturamento eletrônico".
7. Selecione **Tipos de resposta** para configurar os tipos de resposta. Para obter informações sobre nomes de tabelas a serem selecionados, consulte o tópico específico de país/região "Introdução ao Complemento de faturamento eletrônico".

![Configurar tipos de resposta](media/e-invoicing-services-get-started-set-up-response-types.png)

## <a name="e-invoicing-feature-names-by-country"></a>Nomes de recursos de faturamento eletrônico por país 
A tabela a seguir descreve outros recursos de faturamento eletrônico disponíveis para download no Repositório global de relatório eletrônico para gerar faturas eletrônicas.
No RCS, você pode baixar os recursos de faturamento eletrônico listados nesta tabela, as configurações de ER e as configurações do recurso de faturamento eletrônico disponível.
No Finance, você pode habilitar as referências de recursos relacionados na página **Parâmetros de documento eletrônico** para emitir faturas eletrônicas para esses países. Para obter mais informações, consulte a seção, [Ativar recursos de faturamento eletrônico específicos do país/região](#region-specific), anteriormente neste tópico.

| Nome do recurso                      | descrição                                 | Configurações de ER                                                                                                  | Configurações                                                                                                                                                         | País/Região  | Referência de recursos      |
|-----------------------------------|---------------------------------------------|--------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|------------------------|
| Faturas eletrônicas austríacas (AT) | Faturas de vendas e de projetos para a Áustria      | - Fatura de vendas OIOUBL <br>- Fatura de projeto OIOUBL <br>- Nota de crédito de vendas OIOUBL <br>- Nota de crédito de projeto OIOUBL | - Geração de fatura de venda (AT) <br>- Geração de fatura de projeto (AT) <br>- Geração de nota de crédito de venda (AT) <br>- Geração de nota de crédito de projeto (AT)         | Áustria         | EUR-00023              |
| Fatura eletrônica belga (BE)   | Faturas de vendas e de projetos para a Bélgica      | - Fatura de venda UBL BE <br>- Fatura de projeto UBL BE <br>- Nota de crédito de projeto UBL BE <br>- Nota de crédito de venda UBL BE | - Geração de fatura de venda (BE)<br>- Geração de fatura de projeto (BE) <br>- Geração de nota de crédito de venda (BE) <br>- Geração de nota de crédito de projeto (BE)         | Bélgica         | EUR-00023              |
| Fatura eletrônica dinamarquesa (DK)    | Faturas de vendas e de projetos para a Dinamarca      | - Fatura de vendas OIOUBL <br>- Fatura de projeto OIOUBL <br>- Nota de crédito de vendas OIOUBL <br>- Nota de crédito de projeto OIOUBL | - Geração de fatura de venda (DK) <br>- Geração de fatura de projeto (DK) <br>- Geração de nota de crédito de venda (DK)<br>- Geração de nota de crédito de projeto (DK)         | Dinamarca         | EUR-00023<br> DK-00001 |
| Fatura eletrônica holandesa (NL)     | Faturas de vendas e de projetos para os Países Baixos  | - Fatura de venda UBL NL <br>- Fatura de projeto UBL NL <br>- Nota de crédito de venda UBL NL <br>- Nota de crédito de projeto UBL NL | - Geração de fatura de venda (NL) <br> - Geração de fatura de projeto (NL) <br> - Geração de nota de crédito de venda (NL) <br>- Geração de nota de crédito de projeto (NL)          | Os Países Baixos | EUR-00023              |
| Fatura eletrônica estoniana (EE)  | Faturas de vendas e de projetos para a Estônia      | - Fatura de venda (EE) <br> - Fatura de projeto (EE)                                                                     | - Geração de fatura de venda (EE) <br>- Geração de fatura de projeto (EE)                                                                                           | Estônia         | EUR-00023              |
| Fatura eletrônica finlandesa (FI)   | Faturas de vendas e de projetos para a Finlândia      | - Fatura de venda (FI) <br>- Geração de fatura de projeto (FI)                                                          | - Geração de fatura de venda (FI) <br>- Geração de fatura de projeto (FI)                                                                                           | Finlândia         | EUR-00023              |
| Fatura eletrônica francesa (FR)    | Faturas de vendas e de projetos para a França    | - Fatura de venda UBL FR <br> - Fatura de projeto UBL FR <br> - Nota de crédito de venda UBL FR <br>- Nota de crédito de projeto UBL FR | - Geração de fatura de venda (FR) <br> - Geração de fatura de projeto (FR) <br>- Geração de nota de crédito de venda (FR) <br>- Geração de nota de crédito de projeto (FR)         | França          | EUR-00023              |
| Fatura eletrônica alemã (DE)    | Faturas de vendas e de projetos para a Alemanha      |- Fatura de venda (DE) <br> - Fatura de projeto <DE>                                                                     | - Geração de fatura de venda (DE) <br>- Geração de fatura de projeto (DE)                                                                                           | Alemanha         | EUR-00023              |
| Fatura eletrônica norueguesa (NO) | Faturas de vendas e de projetos para a Noruega       | - Fatura de vendas OIOUBL <br>- Fatura de projeto OIOUBL <br>- Nota de crédito de vendas OIOUBL <br>- Nota de crédito de projeto OIOUBL | - Geração de fatura de venda (NO) <br>- Geração de fatura de projeto (NO) <br>- Geração de nota de crédito de venda (NO) <br>- Geração de nota de crédito de projeto (NO)          | Noruega          | EUR-00023<br> NO-00010 |
| Fatura eletrônica espanhola (ES)   | Faturas de vendas e de projetos para a Espanha        | - Fatura de venda (ES) <br>- Fatura de projeto (ES)                                                                     | - Geração de fatura de venda (ES) <br>- Geração de fatura de projeto (ES)                                                                                           | Espanha           | EUR-00023 <br>ES-00025 |
| Fatura eletrônica italiana (TI)   | Faturas de vendas e de projetos para a Itália        | - (Versão prévia) Nota fiscal de venda (TI) <br> - Fatura de projeto (TI)                                                           | - Fatura de venda <br> - Fatura de projeto                                                                                                                           | Itália           | EUR-00023 <br>IT-00036 |
| Fatura eletrônica PEPPOL         | Geração de faturas de vendas e de projetos PEPPOL | - Fatura de vendas PEPPOL <br>- Fatura de projeto PEPPOL <br>- Nota de crédito de vendas PEPPOL <br> - Nota de crédito de projeto PEPPOL | - Geração de fatura de venda PEPPOL <br>- Geração de fatura de projeto PEPPOL <br>- Geração de nota de crédito de venda PEPPOL <br>- Geração de nota de crédito de projeto PEPPOL |                 | EUR-00023              |


## <a name="electronic-invoice-processing-in-finance-and-supply-chain-management"></a>Processamento de fatura eletrônica no Finance e no Supply Chain Management

Durante o processamento, você concluirá estas tarefas:

1. Envie um documento comercial (fatura) por meio do Complemento de faturamento eletrônico.
2. Exiba os logs de execução de envio.

### <a name="submit-business-documents"></a>Enviar documentos comerciais

Durante o processo de envio regular, a comunicação entre o cliente e o Complemento de faturamento eletrônico é bidirecional. A finalidade é realizar duas tarefas principais durante o envio de documentos eletrônicos:

1. Envie todos os documentos eletrônicos que estão aguardando envio do Finance, que têm o status correto para envio e atendam aos critérios de seleção.
2. Importe, para o Finance, a resposta que o Complemento de faturamento eletrônico retorna para documentos eletrônicos enviados anteriormente. Após a importação, as respostas são analisadas e o status dos documentos comerciais é atualizado de acordo.

Você pode enviar documentos comerciais manualmente ou com base em requisitos de agendamento.

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Enviar documentos eletrônicos**.
2. Para o primeiro envio de qualquer documento, sempre defina a opção **Reenviar documentos** como **Não**. Se você precisar reenviar um documento pelo serviço, defina esta opção como **Sim**.
3. Na Guia Rápida **Registros a serem incluídos** , selecione **Filtrar** para abrir a caixa de diálogo **Consulta** , na qual você pode criar uma consulta para selecionar documentos para envio.

![Caixa de diálogo Enviar documentos eletrônicos](media/e-invoicing-services-get-started-submission-form.png)

### <a name="filter-query"></a>Consulta de filtro

1. Na caixa de diálogo **Consulta** , na guia **Intervalo** , insira critérios de filtro usando os campos **Tabela** , **Tabela derivada** , **Campo** e **Critérios**.
2. Selecione **Adicionar** para adicionar quantos critérios adicionais forem necessários para selecionar os documentos comerciais.

    ![Configurar critérios de filtro de envio](media/e-invoicing-services-get-started-set-up-submission-filter-criteria.png)

3. Selecione **OK** para fechar a caixa de diálogo **Consulta**.
4. Selecione **OK** para enviar os documentos comerciais selecionados ao Complemento de faturamento eletrônico.

    > [!NOTE]
    > Na primeira tentativa de enviar um documento pelo serviço, você será solicitado a confirmar a conexão com o complemento do faturamento eletrônico. Selecione **Clique aqui para se conectar ao serviço de envio de documentos eletrônicos**.
    >
    > ![Caixa de mensagem Conectar-se ao serviço de envio de documentos eletrônicos](media/e-invoicing-services-get-started-dialog-form-connect-e-Invoicing-services.png)
    >
    > Se a conexão tiver êxito, você receberá uma mensagem de confirmação.
    >
    > ![Confirmação de conexão com o Complemento de faturamento eletrônico](media/e-invoicing-services-get-started-confirmation-connection-e-invoicing-services.png)

5. Feche a caixa de diálogo.

> [!NOTE]
> Após cada envio, a Central de ações mostra o número de documentos enviados.
>
> ![Mensagens da Central de ações](media/e-invoicing-services-get-started-view-action-center-messages.png)

### <a name="submission-by-batch"></a>Envio por lote

Em vez de enviar documentos manualmente, você pode automatizar o processo de envio e executá-lo em segundo plano, com base em uma frequência configurada de execução em lotes.

1. Na caixa de diálogo **Enviar documentos eletrônicos** , na Guia Rápida **Executar em segundo plano** , defina a opção **Processamento em lotes** como **Sim**.
2. Na guia **Recorrência** , configure a frequência de processamento em lotes.

![Configurar o envio por lote](media/e-invoicing-services-get-started-set-up-submission-batch.png)

### <a name="view-all-submission-logs"></a>Exibir todos os logs de envio

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.
2. No campo **Tipo de documento** , selecione o tipo de documento para filtragem.

    ![Selecionar o tipo de documento para exibir logs de envio](media/e-invoicing-services-get-started-select-document-type-for-viewing-submission-log.png)

    > [!IMPORTANT]
    > O valor mostrado na coluna **Status do envio** representa o status relacionado à conclusão do próprio processo de envio. Ele indica se o fluxo de ações configurado no RCS foi executado até o fim, independentemente de o documento eletrônico ter sido aprovado ou rejeitado. O valor na coluna **Status do envio** não representa o status do documento enviado. Você pode exibir o status do documento enviado (isto é, se o documento foi aprovado ou rejeitado) na Guia Rápida **Log da ação de processamento** nos detalhes do log de envio, conforme descrito a seguir.

3. No Painel de Ações, selecione **Consultas \> Detalhes de envio**.
4. Exiba os detalhes do log de envio.

    ![Detalhes do log de envio](media/e-invoicing-services-get-started-view-submission-log-form.png)

Os resultados mostrados no log de envio dependem de como o recurso de faturamento eletrônico foi configurado no RCS. No entanto, seja qual for a configuração, o log de envio sempre terá três FastTabs:

- **Ações de processamento** – esta Guia Rápida mostra o log de execução para as ações configuradas na versão do recurso que foi configurada no RCS. A coluna **Status** mostra se a ação foi executada com êxito.
- **Arquivos de ação** – esta Guia Rápida mostra os arquivos intermediários que foram gerados durante a execução das ações. Você pode selecionar **Exibir** para baixar o arquivo e exibir o conteúdo.
- **Log de ação de processamento** – esta Guia Rápida mostra os resultados da comunicação entre o complemento do faturamento eletrônico e o serviço Web de destino. Ela também mostra o que foi retornado pelo processamento do serviço Web.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do complemento de faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução ao complemento de faturamento eletrônico para o Brasil](e-invoicing-bra-get-started.md)
- [Introdução ao complemento de faturamento eletrônico para o México](e-invoicing-mex-get-started.md)
- [Introdução ao complemento de faturamento eletrônico para a Itália](e-invoicing-ita-get-started.md)
- [Configurar o complemento de faturamento eletrônico](e-invoicing-setup.md)
