---
title: Introdução ao Faturamento eletrônico para a Itália
description: Este tópico fornece informações que ajudarão você a começar a usar o Faturamento eletrônico para a Itália.
author: gionoder
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 23cb0523b6d6d065ad19f6c3bddf881b0dc82a7d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840091"
---
# <a name="get-started-with-electronic-invoicing-for-italy"></a>Introdução ao Faturamento eletrônico para a Itália

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> O Faturamento eletrônico para a Itália talvez não ofereça suporte no momento a todas as funções disponíveis para faturas eletrônicas no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management. 

Este tópico fornece informações que ajudarão você a começar a usar o Faturamento eletrônico para a Itália. Ele o orienta você pelas etapas de configuração que dependem do país para os Regulatory Configuration Services (RCS) e no Finance. Ele também o orienta durante o processo de envio de faturas eletrônicas geradas no formato **FatturaPA** específico da Itália pelo serviço e explica como revisar os resultados do processamento.

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir as etapas deste tópico, você deve concluir as etapas em [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Configuração do RCS

Durante a configuração do RCS, você concluirá estas tarefas:

1. Importe o recurso de faturamento eletrônico para a exportação de faturas eletrônicas de clientes no formato **FatturaPA**.
2. Examine as configurações de formato necessárias para gerar, enviar e receber respostas sobre faturas eletrônicas.
3. Configure os eventos que dão suporte a cenários de envio de fatura eletrônica.
4. Publique o recurso de faturamento eletrônica.

> [!NOTE]
> O "recurso de faturamento eletrônico" é o nome genérico do recurso configurado e publicado para consumir o servidor do faturamento eletrônico. Neste caso, a exportação de faturas eletrônicas de clientes é o recurso de faturamento eletrônico que você configurará.

## <a name="import-the-e-invoicing-feature"></a>Importar o recurso de faturamento eletrônico

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recursos de globalização**, na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
3. Na página **Recursos de faturamento eletrônico**, selecione **Importar** para importar o recurso de faturamento eletrônico do Repositório global.

    > [!NOTE]
    > Se você não vir a lista de recursos disponíveis, selecione **Sincronizar**. 

4. Selecione o recurso **Exportação de Faturas Eletrônicas (TI)** e, em seguida, selecione **Importar**.

![Importa o recurso de exportação de faturas eletrônicas (TI)](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

Quando você importa o recurso **Exportação de faturas eletrônicas (TI)** do Repositório global, todas as configurações descritas nas próximas seções também são importadas.

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a>Criar uma nova versão do recurso Exportação de Faturas Eletrônicas (TI)

1. Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione **Novo**. 

    ![Adicionar uma nova versão do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    Em seguida, você configurará os formatos ER (relatório eletrônico) associados ao recurso de faturamento eletrônico.

2. Na guia **Configurações**, selecione **Adicionar** para gerenciar as versões de configuração.

    ![Gerenciar as versões de configuração do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    Nesta etapa, você está adicionando e configurando os formatos ER de arquivos diferentes que são usados para exportar faturas eletrônicas italianas. Para faturas eletrônicas italianas FatturaPA, use as seguintes configurações padrão ou as configurações personalizadas reais usadas para faturamento eletrônico:

    - Fatura de venda (TI)
    - Fatura de projeto (TI)

    Quando você cria um recurso de faturamento eletrônico que deriva de outro recurso de faturamento eletrônico, todos os formatos ER são herdados do recurso original.

3. Selecione uma configuração de arquivo de formato ER específica.
4. Selecione **Editar** ou **Exibir** para abrir a página **Designer de formato**.

    ![Abrir a página Designer de formato](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. Use a página **Designer de formato** para editar e exibir as configurações do arquivo de formato ER.

    ![Página do designer de formatos](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Gerenciar as configurações do recurso de faturamento eletrônico

- Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, selecione **Adicionar**, **Excluir** ou **Editar** para gerenciar as configurações do recurso de faturamento eletrônico.

![Gerenciar as configurações do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

Nesta etapa, você configura os eventos aplicáveis a faturas eletrônicas, incluindo a geração de arquivos de saída XML no formato **FatturaPA** e na assinatura digital (se necessário).

### <a name="configure-the-sales-invoice-feature-setup"></a>Definir a configuração do recurso de fatura de venda

1. Na página **Recursos de faturamento eletrônico**, na guia **Configurações**, na coluna **Configuração do recurso**, selecione **Fatura de venda**.
2. Selecione **Editar**.
3. Na página **Configuração de versão do recurso**, selecione a guia **Ações** para gerenciar a lista de ações. As ações definem uma lista de operações que devem ser executadas na ordem sequencial para realizar a execução total do evento.

    ![Guia Ações](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | ID de ação | Nome da ação        | Descrição da ação                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | 1         | Transformar documento | Crie o arquivo XML de faturamento eletrônico no formato **FatturaPA**. |
    | 2         | Assinar documento      | Aplique uma assinatura digital ao arquivo XML.             |

4. Selecione a guia **Regras de aplicabilidade** para exibir e manter as regras de aplicabilidade. As regras de aplicabilidade definem o contexto em que a ação será executada.

    ![Guia Regras de aplicabilidade](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. Selecione a guia **Variáveis** para exibir e manter as variáveis.

    ![Guia Variáveis](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. Defina as variáveis públicas necessárias para executar as ações.

### <a name="configure-the-project-invoice-feature-setup"></a>Definir a configuração do recurso de fatura do projeto 

As etapas e as configurações necessárias para definir a configuração do recurso **Fatura do projeto** são semelhantes às etapas e definições de configuração do recurso **Fatura de venda**. Ao trabalhar com faturas de projeto, consulte os procedimentos para faturas de vendas.

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a>Atribuir o recurso de faturamento eletrônico ao ambiente

1. Na página **Recursos de faturamento eletrônico**, na guia **Ambientes**, selecione **Habilitar**.
2. No campo **Ambiente**, selecione o ambiente.
3. No campo **Efetivo a partir de**, selecione a data em que o ambiente deve entrar em vigor.
4. Selecione **Habilitar**. 

![Habilitar o ambiente de faturamento eletrônico](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a>Publicar o recurso de faturamento eletrônico

Você pode publicar o recurso de faturamento eletrônico alterando o status da versão para **Concluído** ou **Publicado**.

### <a name="change-the-version-status-to-completed"></a>Alterar o status da versão para Concluído

1. Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione a versão do recurso de faturamento eletrônico que tem o status **Rascunho**.
2. Selecione **Alterar status \> Concluir**. 

### <a name="change-the-version-status-to-published"></a>Alterar o status da versão para Publicado 

1. Na página **Recursos de faturamento eletrônico**, na guia **Versões**, selecione a versão do recurso de faturamento eletrônico que tem o status **Concluído**.
2. Selecione **Alterar status \> Publicar**.

![Alterar o status do recurso de faturamento eletrônico](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-integration-in-finance"></a>Configurar integração do Faturamento eletrônico no Finance

Durante a configuração do Finance, você concluirá estas tarefas:

1. Importe o modelo de dados ER, o mapeamento do modelo de dados ER e as configurações de contexto para faturas eletrônicas FatturaPA.
2. Configure o certificado necessário para assinar digitalmente faturas eletrônicas italianas.

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a>Importar o modelo de dados ER, mapeamento de modelos de dados e formatos

1. No espaço de trabalho **Relatório eletrônico**, verifique se o provedor de configuração do **Serviço de Documento Comercial** está definido como **Ativo**.
2. Selecione **Repositórios**.
3. Selecione **Recurso global \> Abrir**.
4. Importar **Modelo de fatura**, **Mapeamento de modelo de fatura** e **Modelo de contexto de fatura de cliente**.

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a>Ative o recurso para exportar faturas eletrônicas de clientes para a Itália

1. Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
2. Na guia **Recursos**, marque a caixa de seleção **Habilitado** na linha para a referência do recurso **IT00036**.

![Ativar o recurso FatturaPA](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a>Configurar documentos eletrônicos

1. Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
2. Na guia **Documento eletrônico**, selecione **Adicionar** e insira as tabelas necessárias para gerar faturas eletrônicas italianas:

    - **Nome da tabela:** diário de fatura do cliente
    - **Nome da tabela:** fatura do projeto

3. Para cada tabela, defina um contexto de documento relacionado:

    - Para o **Diário de faturas de clientes**, selecione **Contexto de fatura de cliente**.
    - Para **Fatura de projeto**, selecione **Contexto de fatura de projeto**.

![Configurar tipos de resposta](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a>Processamento de fatura eletrônica

Durante o processamento no Finance, você concluirá estas tarefas:

1. Gerar faturas eletrônicas italianas por meio do Faturamento eletrônico
2. Exibir os logs de execução e revisar os resultados do processamento

### <a name="generate-electronic-invoices"></a>Gerar faturas eletrônicas

Depois que você ativar os recursos **Integração do Faturamento eletrônico configurável** e **IT00036**, o processo antigo do Finance para gerar faturas eletrônicas italianas não poderá mais ser usado. Ele é substituído por um novo processo chamado **Enviar documentos eletrônicos**.

Você pode enviar os documentos manualmente, com base na demanda de documentos de fatura eletrônica.

> [!NOTE]
> Antes de continuar, verifique se a configuração necessária para as faturas eletrônicas italianas foi concluída. Para obter mais informações, consulte [Faturas eletrônicas do cliente](https://docs.microsoft.com/dynamics365/finance/localizations/emea-ita-e-invoices). Lembre-se de que algumas das etapas de configuração descritas nesse tópico podem não estar disponíveis devido à ativação do Faturamento eletrônico.

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Enviar documentos eletrônicos**.
2. Para o primeiro envio de qualquer documento, defina a opção **Reenviar documentos** como **Não**. Se você precisar reenviar um documento pelo serviço, defina esta opção como **Sim**.
3. Na Guia Rápida **Registros a serem incluídos**, selecione **Filtrar** para abrir a caixa de diálogo **Consulta**, na qual você pode criar uma consulta para selecionar documentos para envio.

![Caixa de diálogo Enviar documentos eletrônicos](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a>Consulta de filtro

1. Na caixa de diálogo **Consulta**, configure as condições de filtragem para as faturas de venda e de projeto, ou deixe as condições em branco para incluir todas as faturas não enviadas.

    ![Configurar critérios de filtro de envio](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. Selecione **OK** para fechar a caixa de diálogo **Consulta**.
3. Selecione **OK** para enviar os documentos selecionados.

> ![OBSERVAÇÃO] Na primeira tentativa de enviar um documento pelo serviço, você será solicitado a confirmar a conexão com o Faturamento eletrônico. Selecione **Clique aqui para se conectar ao serviço de envio de documentos eletrônicos**.

#### <a name="view-submission-logs"></a>Exibir logs de envio

Você pode exibir os logs de envio para todos os documentos enviados.

1. Vá para **Administração da organização \> Periódico \> Documentos eletrônicos \> Log de envio de documentos eletrônicos**.
2. No campo **Tipo de documento**, selecione **Diário de faturas de clientes** ou **Fatura de projeto** para filtrar os documentos eletrônicos necessários.

    ![Selecionar um tipo de documento para exibir os logs de envio](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    O valor mostrado na coluna **Status do envio** representa o status do processo de envio. Ele indica se o processo foi executado como configurado e se uma ação adicional é necessária.

3. No Painel de Ações, selecione **Consultas \> Detalhes de envio** para exibir os detalhes dos logs de execução de envio.

    ![Exibir os detalhes do log de envio](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. Na Guia Rápida **Ações de processamento**, você pode exibir o log de execução para as ações configuradas na versão do recurso que foi configurada no RCS. A coluna **Status** mostra se a ação foi executada com êxito.
5. Na Guia Rápida **Arquivos de ação**, você pode exibir os arquivos intermediários que foram gerados durante a execução das ações. Você pode selecionar **Exibir** para baixar o arquivo XML de saída no formato **FatturaPA** e exibir o conteúdo.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do Faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md)
- [Configurar Faturamento eletrônico](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
