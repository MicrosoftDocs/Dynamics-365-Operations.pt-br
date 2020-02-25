---
title: Declaração de imposto do SPED-Reinf (Brasil)
description: Este tópico fornece informações sobre a configuração de eventos do SPED-Reinf usando Livros fiscais e a estrutura de registro de relatórios SII no Microsoft Dynamics 365 Finance para o Brasil.
author: sndray
manager: AnnBe
ms.date: 01/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 3368b40169aef55d0818a04dc317359ff949742f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003892"
---
# <a name="sped-reinf-tax-statement-brazil"></a>Declaração de imposto do SPED-Reinf (Brasil)

[!include [banner](../includes/banner.md)]


O SPED-Reinf é um novo relatório de declaração de imposto que coleta informações sobre imposto retido na fonte e outras informações fiscais de interesse da Receita Federal do Brasil (RFB) e da Previdência Social. (Reinf significa "Retenções e Outras Informações Fiscais".) A declaração consiste em um conjunto de eventos que devem ser entregues, em layouts específicos, por meio do ambiente do Sistema Público de Escrituração Digital (SPED). Além disso, eles devem ser entregues usando um certificado digital válido, emitido por uma entidade credenciada pela Infraestrutura de Chaves Públicas Brasileira (ICP-Brasil). A declaração será considerada válida após a confirmação do recebimento e a validação do conteúdo dos arquivos.

O SPED-Reinf foi criado para apurar impostos federais retidos, para fins de imposto de renda e Previdência Social, em atividades que não estão relacionadas ao trabalho. Exemplos dessas atividades incluem notas fiscais, pagamentos e outros eventos.

O Microsoft Dynamics oferece suporte à geração de eventos do SPED-Reinf por meio do módulo **Livros fiscais** e da estrutura de registro de relatórios SII. Os usuários podem trocar mensagens XML para cada evento exigido pela autoridade fiscal.

**Escopo**

-   Versão do SPED-Reinf compatível: 1.3.

-   Versões com suporte: Microsoft Dynamics AX 2012 R3 e Microsoft Dynamics 365 for Finance and Operations.

-   A procuração eletrônica não tem suporte.

**Tabela de eventos**

| Evento | Descrição                                                   | Tipo de evento             | Com suporte no Microsoft Dynamics | Comentários                                                                                                                                                                |
|-----------|-------------------------------------------------------------------|----------------------------|-------------------------------------|----------------------------------------|
| R-1000    | Informações do contribuinte                                              | Inicial                    | **Sim**                             | Suporte para contribuintes como entidades legais.   |
| R-1070    | Processo administrativo e judicial                               | Quando um processo está em vigor | **Sim**                             |                                              |
| R-2010    | Serviços adquiridos                                                 | Evento periódico             | **Sim**                             | Sem suporte para estabelecimentos fiscais compradores como construções civis. (As construções civis exigem um CNO em vez de um CNPJ.)                                                |
| R-2020    | Serviços fornecidos                                                 | Evento periódico             | **Sim**                             | Sem suporte para tomadores de serviço (clientes) como construções civis. (As construções civis exigem um CNO em vez de um CNPJ.)                                                    |
| R-2030    | Valores recebidos por associações esportivas                            | Evento periódico             | **Não**                              |                                              |
| R-2040    | Valores pagos a associações esportivas                                | Evento periódico             | **Não**                              |                                              |
| R-2050    | Comércio da produção rural por entidades legais rurais ou pelo agronegócio | Evento periódico             | **Não**                              |                                               |
| R-2060    | Apuração do INSS-CPRB                                              | Evento periódico             | **Sim**                             | Sem suporte para apuração do imposto CPRB das operações do Commerce.  |
| R-2070    | Retenção em pagamentos (IR, CSLL, PIS, COFINS)                   | Evento periódico             | **Não**                              | O suporte será incluído como um recurso separado na próxima versão. Para obter mais informações, consulte **Sped REINF - evento R-2070** no Microsoft Dynamics Lifecycle Services (LCS). |
| R-2098    | Reabertura de atividades periódicas                                             | Evento periódico             | **Sim**                             |                                                |
| R-2099    | Fechamento                                                           | Evento periódico             | **Sim**                             |                                              |
| R-3010    | Receita de espetáculo de esporte                                           | Evento não periódico         | **Não**                              |                                                |
| R-5001    | Base de cálculo de impostos consolidada por contribuinte                    | Evento não periódico         | **Não**                              |                                               
| R-5011    | Base consolidada e valor do imposto                                  | Evento não periódico         | **Sim**                             | Este evento é usado para consultar o status do evento de fechamento R-2099. |
| R-9000    | Exclusão                                                           | Evento não periódico         | **Sim**                             |                                                |

-   Somente os contribuintes em conformidade com o SPED-ECD têm suporte.

-   Sem suporte para contribuintes como departamentos públicos.

-   Sem suporte para serviços fornecidos em projetos de construções civis.

-   Sem suporte para tomadores de serviço em projetos de construções civis.

-   Escrituração manual do pagamento para liquidação do valor de CPRB devido.

-   O pagamento do valor de CPRB devido está fora do escopo.

**Configuração do SPED-Reinf**

Esta seção descreve a configuração necessária.

### <a name="set-up-electronic-messages-functionality"></a>**Configurar a funcionalidade Mensagens eletrônicas**

A funcionalidade Mensagens eletrônicas é nova no Dynamics 365 Finance. Ela permite manter e acompanhar vários processos de mensagens eletrônicas quando há uma troca de informações entre o Finance e os serviços Web da autoridade fiscal.

Antes de entregar eventos do SPED-Reinf ao site do governo, use a configuração predefinida que a Microsoft preparou para atender aos requisitos do SPED-Reinf. Essa configuração é fornecida como uma entidade de dados. Depois de importada para o Finance, os usuários poderão gerar, validar e entregar todos os eventos descritos no escopo do SPED-Reinf.

#### <a name="import-the-configuration-from-the-data-entity"></a>Importar a configuração da entidade de dados

Para configurar a funcionalidade Mensagens eletrônicas para comunicações de eventos do SPED-Reinf, use a configuração predefinida disponível no LCS.

1.  Ir para <https://lcs.dynamics.com>.

2.  Entre.

3.  Selecione **Biblioteca de ativos compartilhados**.

4.  Na guia **Pacote de dados**, selecione as entidades de dados de comunicações de eventos do SPED Reinf e salve o arquivo no local onde as entidades de dados devem ser armazenadas.

5.  Entre no Finance.

6.  Vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Importar**.

7.  Insira uma descrição e um nome para identificar o trabalho, como **SpedReinf**.

8.  No campo **Formato de dados de origem**, selecione **Pacote**.

9.  Selecione **Carregar** e, em seguida, selecione o arquivo que você salvou do LCS (**SPEDReinf_EMSettings.zip**).

10. Selecione **Salvar** e aguarde até que todas as entidades de dados sejam exibidas na página.

11. Selecione **Importar**.

    Você receberá uma notificação sobre o processo de importação. Também é possível atualizar a página manualmente para ver o andamento do processo de importação. Quando o processo for concluído, você poderá visualizar a página **Resumo de execução**.

    ![Página Resumo de execução](media/bra-execution-summary-page.png)

#### <a name="structure-of-electronic-messages"></a>Estrutura de mensagens eletrônicas

Cada evento criado, entregue e recebido é representado por uma mensagem e um item de mensagem.

![Estrutura de mensagens eletrônicas](media/bra-electronic-messages-structure.png)

O item de mensagem é representado pela mensagem de evento XML e também inclui as seguintes informações adicionais que são armazenadas na mensagem ou atualizadas no Microsoft Dynamics:

-   O CNPJ do estabelecimento fiscal (número completo)

-   O CNPJ raiz

-   O período de escrituração

-   A data inicial do período para o qual a mensagem é válida

-   O número do protocolo de recebimento

-   Um valor que indica se a mensagem está registrada no Microsoft Dynamics

Você pode encontrar essa configuração em **Imposto \> Configuração \> Mensagens eletrônicas \> Campos adicionais**.

![Campos adicionais de mensagens eletrônicas](media/bra-electronic-messaging-additional-fields.png)

> [!NOTE]
> Não remova esta configuração. Essa configuração está incluída no pacote.

Os tipos de item de mensagem são classificados pelo tipo de evento em **Imposto \> Configuração \> Mensagens eletrônicas \> Tipos de item de mensagem**.

![Message-types](media/bra-message-types.png)

> [!NOTE]
> Não remova esta configuração. A configuração desses tipos está incluída no pacote.*

Vá para **Imposto \> Configuração \> Parâmetros \> Parâmetros da contabilidade** e, em seguida, na guia **Sequências numéricas**, selecione **Mensagem** e **Item de mensagem** para configurar a sequência numérica para itens de mensagem.

![Sequências numéricas de mensagens eletrônicas](media/bra-electronic-messages-number-sequences.png)

> [!NOTE]
> A sequência numérica deve ser definida como não contínua.

#### <a name="certificates"></a>Certificados

Certificados confiáveis devem ser configurados e usados pelo Microsoft Dynamics, pois o SPED-Reinf deve ser sempre assinado por um certificado e-CNPJ autorizado pela entidade ICP-Brasil, independentemente de quaisquer outras assinaturas. Esse certificado e-CNPJ deve corresponder aos oito primeiros dígitos do CNPJ do estabelecimento fiscal matriz, pois o relatório é enviado por esse estabelecimento e pelos estabelecimentos fiscais relacionados.

No Finance, você deve registrar o certificado do Key Vault no Microsoft Azure.

Para obter informações sobre como configurar um cliente do Key Vault, consulte [Configuração do Cliente do Azure Key Vault](https://support.microsoft.com/help/4040305).

1.  Vá para **Administração do sistema \> Configuração \> Parâmetros do Key Vault**.

2.  Digite as seguintes informações:

    -  URL do Key Vault

    -  Cliente do Key Vault

    -  Chave secreta do Key Vault

    -  ID secreta do Key Vault

Após o registro, associe o certificado nos parâmetros de configuração para a ação **Geração de relatório**, conforme descrito na seção a seguir.

#### <a name="setup-parameters"></a>Parâmetros de configuração 

Sempre que uma mensagem é criada, preparada, validada, entregue ou recebida, a ação relacionada deve ser identificada por meio de uma classe X++ em **Imposto \> Configuração \> Mensagens eletrônicas \> Configurações de classe executável**.

-   **Preparação dos eventos –** Esta ação é usada para criar e preparar a mensagem XML. Ela solicita parâmetros adicionais, como **Data de escrituração**, **CNPJ** e **CNPJ raiz**, pois os eventos são gerados com base nessas informações.

    ![Itens de preparação](media/bra-preparation-items.png)

-   **Processo de resposta** – Esta ação é usada para atualizar a mensagem entregue quando ela for aprovada pelo governo usando um número de protocolo. Além disso, a mensagem é atualizada conforme registrado no site do governo.

    ![Resposta ao processo de itens de preparação](media/bra-preparation-items-process-response.png)

-   **Geração de relatório** – Esta ação é usada para enviar e receber o item de mensagem.

    ![Gerar parâmetros de relatórios](media/bra-generate-reports-parameters.png)

> [!NOTE]
> Não remova esta configuração. Essa configuração está incluída no pacote.

#### <a name="specific-actions"></a>Ações específicas

Antes que uma mensagem seja entregue, você deve configurar a validação do esquema XML para evitar rejeições do site do governo.

Vá para **Administração da organização \> Gerenciamento de documentos \> Parâmetros de gerenciamento de documentos** e habilite arquivos XSD adicionando **XSD** como um novo tipo de arquivo.

![Parâmetros de gerenciamento de documentos](media/bra-document-management-parameters.png)

Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Ações de processamento de mensagens** e selecione **Novo \> Arquivo** para anexar os esquemas (arquivos .xsd) para as seguintes ações:

-   Validar

-   Re-Validar

-   Exclusão-Validar

Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Ações de processamento de mensagens**, selecione a ação **Preencher** (**Incluir**) e, em seguida, no campo **Ação de preencher registros**, selecione **Registrar transações**.

![Ações de Processamento de Mensagens](media/bra-message-processing-actions.png)

Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Configurações de serviço Web** e configure uma conexão de serviços Web e certificados para enviar e consultar eventos.

![Configurações de serviços Web](media/bra-web-service-settings.png)

> [!NOTE]
> Nas configurações do **SPED Reinf assíncrono**, inclua o endereço do serviço Web para consultar o evento R-5011.

### <a name="set-up-service-types"></a>Configurar tipos de serviço

A tabela de tipos de serviço representa a tabela 06 que as autoridades fiscais estabeleceram para classificar os serviços fornecidos, com base na atribuição de trabalho. Uma lista detalhada de valores disponíveis está à disposição no site do SPED.

1.  Vá para **Livros fiscais \> Configuração \> SPED Reinf \> Tipos de serviço**.

2.  Selecione **Novo**, insira um código de classificação que tenha sido estabelecido pelas autoridades fiscais e insira uma descrição.

    ![Tipos de serviço](media/bra-service-type-setup.png)

Depois que a lista de tipos de serviço for criada, eles devem ser atribuídos a códigos de serviço. Vá para **Gerenciamento de estoque \> Configuração \> Informações fiscais \> Código de serviço** e, em seguida, para cada serviço, atribua o tipo de serviço relacionado.

**Configurar códigos de classificação de imposto**

Vá para **Livros fiscais \> Configuração \> SPED Reinf \> Códigos de classificação de imposto** e insira os tipos de classificação disponíveis.

![Classificação de imposto](media/bra-tax-classification-codes.png)

Essa informação é atribuída à organização fiscal na FastTab **Geral** em **Livros fiscais \> Configuração \> Organização fiscal**.

![Organização fiscal](media/bra-fiscal-organization-setup.png)

### <a name="set-up-codes-explanation-suspension"></a>Configurar suspensão da explicação de códigos

Vá para **Livros fiscais \> Configuração \> SPED Reinf \> Suspensão da explicação de códigos** e configure os códigos que são usados no evento R-1070 quando a suspensão da retenção se aplica. Esses códigos são atribuídos em **Livros fiscais \> Atividades periódicas \> SPED Reinf \> Processo administrativo e judicial**.

![Códigos de explicação](media/bra-codes-explanation-suspension.png)

### <a name="set-up-fiscal-books-parameters"></a>Configurar parâmetros de livros fiscais

Vá para **Livros fiscais \> Configuração \> Parâmetros de livros fiscais** e configure a sequência numérica para os eventos R-2010 e R-2020.

![Parâmetros de livros fiscais](media/bra-sped-fiscal-books-parameters.png)

> [!NOTE]
> Se as sequências numéricas não tiverem sido inicializadas durante a lista de verificação da configuração para a instalação de KB, você poderá gerá-las usando um assistente. Para iniciar o assistente, vá para **Administração da organização \> Sequências numéricas \> Sequências numéricas** e selecione **Gerar**. Assim você poderá configurar a sequência numérica relacionada.

-   **Área:** Livros fiscais

-   **Referência**: ID de evento do SPED-Reinf

**Eventos do SPED-Reinf**

Todas as informações que o SPED-Reinf fornece sobre impostos e contribuições em um determinado período de apuração são conhecidas como uma *movimentação*. Portanto, cada movimentação pode conter um ou mais eventos.

Para encerrar a transmissão de eventos periódicos para uma determinada movimentação em um período de apuração específico, você deve enviar o evento R-2099 "Fechamento de evento periódico”. Depois que o evento de fechamento é processado e validado, ele é aceito. A aceitação do evento de fechamento finaliza a soma das bases de cálculo incluídas na movimentação. O crédito de imposto poderá então ser calculado e o DARF poderá ser gerado para coletar os impostos e as contribuições devidos.

Se for necessário enviar uma correção ou novos eventos para uma movimentação que já foi fechada, você deverá reabri-la enviando o evento R-2098, “Reabertura de evento periódico”. Após a reabertura de uma movimentação, você deve enviar um novo evento de fechamento.

**Quando não há movimentações no período de apuração**

A situação “sem movimentação” para um contribuinte ocorre somente quando não há informações a serem enviadas ao grupo de eventos periódicos do evento R-2010 ao evento R-2070. Nesse caso, o evento R-2099, "Fechamento de evento periódico”, que fornece as informações para o fechamento, declara a não ocorrência de transações no primeiro período de apuração do ano em que essa situação ocorre. Se a situação “sem movimentação” persistir nos anos seguintes, o contribuinte deverá repetir esse procedimento no mês de janeiro de cada ano.

**Protocolo de recebimento**

O protocolo de recebimento confirma que as informações enviadas foram validadas e entregues com êxito ao ambiente do SPED-Reinf. O protocolo de recebimento é o ponto inicial para corrigir ou excluir um determinado evento, se a correção e a exclusão forem permitidas.

Cada evento transmitido tem um protocolo de recebimento. Para corrigir um evento, é necessário inserir o número do protocolo de recebimento dele.

A quantidade de tempo que os protocolos de recebimento são mantidos no banco de dados do governo não é definida. Portanto, como precaução, é importante que o contribuinte os guarde, pois eles comprovam que a obrigação tributária acessória foi entregue e cumprida.

> [!NOTE]
> O protocolo de entrega consiste em informações transitórias que comprovam que o evento foi transmitido e que a validação apropriada será processada. Ele não demonstra conformidade com a obrigação acessória.

**Aditamento e correção**

O procedimento para aditar as informações enviadas ao SPED-Reinf ocorre somente nos eventos R-1000, “Informações do contribuinte” e R-1070, "Tabela legal e administrativa".

Em todos os outros casos em que as informações enviadas devem ser corrigidas, o procedimento para a correção ou exclusão deve ser usado.

**Eventos de exclusão**

Para excluir eventos que foram aprovados pela autoridade fiscal, mas entregues incorretamente, você deve enviar o evento R-9000, "Evento de exclusão". Nesse evento, é necessário identificar o evento a ser excluído preenchendo a marca **Tipo de evento** (**TpEvento**). Você também deve preencher o **Número de recebimento do evento** (**NRRECEVT**), que especifica o número do protocolo de recebimento do arquivo que foi enviado e deve ser excluído.

**Assinatura digital**

O certificado digital usado no SPED-Reinf deve ser emitido por uma autoridade de certificação credenciada pela ICP-Brasil.

O certificado digital deve pertencer à série ”A”. Os certificados podem pertencer a duas séries: série ”A” e série “S”. A série ”A” inclui os certificados de assinatura digital usados para confirmação de identidade na Web em emails, redes virtuais privadas (VPNs) e documentos eletrônicos, com verificação da integridade de suas informações. A série “S” inclui os certificados de confidencialidade usados na codificação de documentos, bancos de dados, mensagens e outras informações eletrônicas confidenciais.

O certificado digital deve ser do tipo “A1” ou “A3”. Certificados digitais do tipo “A1” são armazenados no computador em que são usados. Certificados digitais do tipo “A3” são armazenados em um dispositivo portátil à prova de adulterações com um chip capaz de realizar a assinatura digital. Exemplos desses dispositivos incluem cartões inteligentes e tokens. Esses dispositivos são razoavelmente seguros porque cada operação é feita pelo chip no dispositivo e não há nenhum acesso externo à chave privada do certificado digital.

Os certificados digitais são necessários em dois momentos:

-   **Para ações de entrega**: antes da solicitação de entrega ao SPED-Reinf ser iniciada, o certificado digital do solicitante é usado para ajudar a garantir a segurança do tráfego de informações na Internet. Para que o certificado digital seja aceito como uma função de transmissor, ele deve ser do tipo e-CNPJ.

-   **Para assinatura de documentos**: os eventos podem ser gerados por qualquer estabelecimento fiscal da entidade legal ou seu proxy. No entanto, o assinante digital desses eventos deve pertencer ao estabelecimento fiscal principal (matriz), seu representante legal ou um advogado concedido por meio de proxy eletrônico e não eletrônico.

Os certificados digitais que são usados para assinar os eventos enviados ao SPED-Reinf devem ser habilitados para a função de assinatura digital de acordo com a política de certificação.

Os eventos no SPED-Reinf devem ser transmitidos usando um certificado digital válido. No entanto, uma exceção será feita para micro e pequenas empresas (ME e EPP) que atendam aos critérios do Simples Nacional e possuam sete funcionários ou menos. Essas empresas podem transmitir seus eventos usando um código de acesso.

### <a name="general-process"></a>Processo geral

1.  Use uma mensagem eletrônica para criar, validar e entregar o evento ou lote de eventos por meio de itens de mensagem eletrônica.

2.  O serviço Web da autoridade fiscal recebe o lote e valida seu conteúdo.

3.  O serviço Web retorna o resultado do processamento. Se os eventos ou o lote de eventos forem recebidos com êxito, um protocolo de recebimento será retornado. Caso contrário, uma mensagem de erro será retornada. Nesse caso, o contribuinte pode resolver os erros e renviar o evento por meio de um novo lote.

![Texto alternativo gerado por máquina: Contribuinte Eventos Gera Evento XML Assina Digitalmente & 80 T rata Rsultados Lote de Ev Clialte Notificaqäo de Retomo EFD-REINF Rec.cäo e Val idacäo (Lotede Eventosi BD Controle ](media/bra-general-process.png)

Os eventos são transmitidos às autoridades fiscais usando a funcionalidade Mensagens eletrônicas para estabelecer um relacionamento bidirecional, automatizado e instantâneo entre o contribuinte e os serviços Web do governo.

As ilustrações a seguir mostram as ações que são realizadas e os status de itens de mensagem que causam a aprovação ou rejeição de cada evento ao ser entregue pela primeira vez (Inserção), atualizado (Aditamento/Atualização) ou cancelado ou excluído (Cancelamento/Exclusão).

![Ações de fluxo](media/bra-flow-actions.png)

#### <a name="insertion"></a>Inserção

Este fluxo é usado para entregar qualquer evento pela primeira vez.

![Inserção](media/bra-insertion-flow.png)

#### <a name="amendmentupdate"></a>Aditamento/Atualização

![Atualização](media/bra-amendment-update-flow.png)

#### <a name="canceldelete"></a>Cancelamento/Exclusão

![Cancelar](media/bra-cancel-delete-flow.png)

#### <a name="inquire-event-5011-from-event-r-2099"></a>Consultar evento 5011 (do evento R-2099)

![Consultar evento 5011](media/bra-inquire-event-5011.png)

#### <a name="manage-electronic-messages"></a>Gerenciar mensagens eletrônicas 

Todos os eventos são gerenciados e controlados em **Imposto \> Consultas e relatórios \> Mensagens eletrônicas \> Itens de mensagem eletrônica**.

| Nome do campo      | Descrição do campo                                                                                                                                         |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tipo de item de mensagem   | O tipo de evento:                                                                                                                                            |
| Status de item de mensagem | O status atual do evento. Este campo é automaticamente preenchido e atualizado, com base na troca de mensagens entre a autoridade fiscal e o contribuinte. |

-   Processo administrativo e judicial (R-1070)

-   Serviços adquiridos (R-2010)

-   Apuração do INSS-CPRB (R-2060)

-   Serviços fornecidos (R-2020)

-   Informações do contribuinte (R-1000)

-   Fechamento (R-2099)

-   **Criado** – O evento foi adicionado ao registro, mas ainda não foi enviado aos serviços Web.

-   **Rejeitado** – O evento foi enviado aos serviços Web, mas foi rejeitado pelo sistema da autoridade fiscal. Um grupo de marcas específico no arquivo XML que é retornado pelo governo especifica o código de erro e fornece uma descrição.

-   **Aceito** – O evento foi enviado aos serviços Web e aceito pelo sistema da autoridade fiscal.

-   **Aceito com erros** – O evento foi enviado aos serviços Web e aceito pelo sistema da autoridade fiscal, apesar de haver erros.


### <a name="event-r-1000-taxpayer-information"></a>Evento R-1000, "Informações do contribuinte"

O evento R-1000 é usado para entregar informações sobre a empresa. Esse evento deve ser entregue apenas uma vez para registrar as informações no site do governo. No entanto, após esse registro inicial de informações, pode ser entregue quantas vezes for necessário para ações de manutenção como atualizações e exclusões de dados.

Portanto, sempre que qualquer atributo do contribuinte ou a data válida de informações que foi fornecida anteriormente precisarem ser alterados, o evento R-1000 deve ser entregue novamente. Quando for entregue novamente, o grupo de marcas correto para a ação desejada deve ser especificado.

Como as comunicações podem falhar devido a problemas técnicos, como tempo limite ou falhas de Internet, o contador tributário deve ser capaz de renviar o evento. Além disso, como a validação do arquivo pelo serviço Web pode falhar, o contador tributário deve ser capaz de visualizar os detalhes e corrigir os erros relacionados. Após a validação do arquivo, o protocolo de recebimento que é retornado pelo serviço Web deve ser salvo e o contador tributário deve ser capaz de visualizar seus detalhes, como o número e o carimbo de data/hora.

#### <a name="repro-step--insertion"></a>Etapa de reprodução – Inserção

1.  Vá para **Imposto \> Consultas e relatórios \> Mensagens eletrônicas \> Itens de mensagem eletrônica**.

2.  No Painel de Ação, selecione **Executar processamento**. Em seguida, na caixa de diálogo **Executar processamento**, no campo **Processamento**, selecione **SPED Reinf**.

3.  Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Incluir**.

    ![Executar processamento](media/bra-run-processing.png)

4.  Selecione **OK** para confirmar as configurações.

    Um item de mensagem do tipo **Informações do contribuinte** é criado e seu status é definido como **Anexado**.

    ![Inserção de itens de mensagem eletrônica](media/bra-electronic-message-items-insertion.png)

5.  Selecione **Executar processamento** novamente e, na caixa de diálogo, no campo **Processamento**, selecione **SPED Reinf**.

6.  Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Parâmetros adicionais** para atualizar as informações relacionadas nos campos adicionais.

    ![Executar parâmetros adicionais de processamento](media/bra-run-processing-additional-parameters.png)

    ![Itens de preparação](media/bra-preparation-items.png)

7.  Selecione **OK** para confirmar as configurações. O item de mensagem do tipo **Informações do contribuinte** é atualizado e seu status é alterado para **Preparado**.

    ![Status de itens de mensagem eletrônica](media/bra-electronic-message-items-status.png)

8.  Selecione **Executar processamento** novamente e, na caixa de diálogo, no campo **Processamento**, selecione **SPED Reinf**.

9.  Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Gerar** para gerar o XML.

10.  Selecione **OK** para confirmar as configurações. A caixa de diálogo **Gerar relatórios** aparece automaticamente. Na FastTab **Registros a serem incluídos**, nas opções de filtro, a ID do tipo de item de mensagem que está solicitando a geração de um arquivo XML é selecionada no campo **Item de mensagem**.

     ![Gerar relatórios](media/bra-generate-reports.png)

11.  Selecione **OK** para confirmar as configurações. O item de mensagem do tipo **Informações do contribuinte** é atualizado e seu status é alterado para **Gerado**.

12.  Repita essas etapas até concluir todas as ações no fluxo [Inserção](#insertion).

#### <a name="repro-step--amendment"></a>Etapa de reprodução – Aditamento 

Se algum dado da organização fiscal foi alterado ou se for necessário excluir o evento por algum motivo, o evento R-1010 deve ser transmitido novamente, mas o status deve ser diferente.

Use o mesmo processo descrito na seção “Etapa de reprodução – Inserção” e conclua todas as ações no fluxo [Aditamento/Atualização](#amendmentupdate).

O Microsoft Dynamics AX detectará quaisquer diferenças entre as informações no último evento e as informações atuais.

> [!NOTE]
> Se as alterações não afetarem o evento R-1010 relacionado, você receberá a seguinte mensagem: “0 registros foram adicionados”.

#### <a name="repro-step--cancel"></a>Etapa de reprodução – Cancelamento

Se, por algum motivo, o contribuinte quiser cancelar/excluir um evento aceito, selecione **Cancelar** e confirme a operação. O status do evento será atualizado para **Excluído**. Conclua todas as ações no fluxo [Cancelamento/Exclusão](#canceldelete).

### <a name="event-r-1070-administrative-and-judicial-process"></a>Evento R-1070, "Processo administrativo e judicial"

O evento R-1070 é usado para relatar informações sobre os processos legais e administrativos ao sistema da autoridade fiscal.

Os processos legais e administrativos podem ser iniciados pelo contribuinte ou pelo trabalhador quando valores da previdência social forem contestados. Os procedimentos (judiciais ou administrativos) são realizados pelo tribunal. Após o juiz chegar a um veredito, ele tem o poder de suspender (ou não) os valores que foram retidos.

A finalidade desse evento é comunicar a existência de procedimentos desse tipo ao banco de dados do SPED-Reinf. Depois que os procedimentos recebem a decisão final do tribunal que suspende a elegibilidade da retenção de valores, o evento se refere a essa decisão para explicar por que os valores foram relatados como suspensos nos eventos periódicos.

Além das informações típicas que identificam o contribuinte e o evento, o evento R-1070 contém os seguintes grupos:

-   Identificador do processo ou dos procedimentos

-   Informações da suspensão

-   Informações complementares sobre os procedimentos

Antes da entrega do evento R-1070, você deve criar o processo relacionado e incluir todas as informações relacionadas.

#### <a name="repro-step--create-process"></a>Etapa de reprodução – Criar processo

1.  Vá para **Livros fiscais \> Atividades periódicas \> SPED Reinf \> Processo administrativo e judicial**.

    ![Processo judicial administrativo](media/bra-administrative-judicial-process.png)

1.  Selecione **Novo** e defina os campos a seguir.

    | **Campo**                    | **Descrição**        |
    |------------------------------|-----------------------|
    | Número do processo        | Insira o número do processo atribuído pelas autoridades competentes. O sistema da autoridade fiscal valida o formato, pois há uma regra específica a ser considerada. |
    | Autor do processo            | Selecione a origem do processo:                                                                                                                   |
    | Tipo de processo              | Selecione o tipo de processo:                                                                                                                                           |
    | Cidade da vara judicial | Selecione a cidade relacionada onde o processo foi originado.                                                                                                                 |
    | Código da vara judicial | Insira o código da vara judicial.                                                                                                                              |

    -   Contribuinte

    -   Outros terceiros

    -   Administrativo

    -   Judicial

1.  Na seção **Detalhes**, insira os detalhes das notas fiscais registradas no Microsoft Dynamics e que são afetadas pelo processo registrado, pois algumas delas podem ter exceções nos impostos retidos na fonte. Você pode adicionar notas fiscais ou remover as que foram adicionadas anteriormente.

    | **Campo**                        | **Descrição**                                                                                           |
    |----------------------------------|-----------------------------------------------------------------------------------------------------------|
    | Demonstrativo                        | O identificador exclusivo da relação entre o número do processo e a nota fiscal.                 |
    | Código                             | Selecione o código de suspensão da explicação.                                                                   |
    | Tipo de serviço                     | Selecione o tipo de serviço relacionado que é aplicável à nota fiscal.                               |
    | Nota fiscal                  | Selecione a nota fiscal.                                                                               |
    | Data da decisão                 | A data da decisão, da sentença ou do despacho administrativo.                                           |
    | Valor da retenção            | O valor da retenção que foi suspenso devido a um processo legal ou administrativo.            |
    | Valor da retenção adicional | O valor adicional da retenção que foi suspenso devido a um processo legal ou administrativo. |

    > [!NOTE]
    > Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

### <a name="event-r-2010-acquired-services"></a>Evento R-2010, "Serviços adquiridos"

O evento periódico R-2010 é usado para relatar, ao sistema da autoridade fiscal, as informações sobre os valores de retenção para a previdência social que estão presentes em notas fiscais de serviço recebidas pelo estabelecimento fiscal. Esse evento não tem nenhuma outra finalidade além de relatar essas notas fiscais para o governo.

Esse evento deve ser enviado até o décimo quinto dia do mês seguinte. Por ser um evento periódico, não é recomendável enviá-lo apenas uma vez, próximo à data de vencimento. Em vez disso, você deve enviá-lo regularmente e com frequência durante o período.

Além disso, a geração desse evento requer a adoção de novas semânticas para o tratamento de eventos em livros fiscais. As novas semânticas são desacopladas de uma apuração de imposto, mas ainda estão no contexto do período de escrituração. Depois que todas as notas fiscais no módulo **Livros fiscais** estiverem no contexto de um período de escrituração, o evento R-2010 também deverá ser gerado por período de escrituração.


Somente o imposto INSS Retido e o imposto sobre serviços devem ser selecionados para gerar esse evento no período de escrituração.

**Principais critérios**

-   As notas fiscais são registradas e sincronizadas no estabelecimento fiscal e no período relacionado.

-   As notas fiscais têm o status de **Aprovada** ou **Cancelada**.

-   O modelo da nota fiscal é **SE**.

-   O tipo de imposto é **INSS** e ele é retido (a caixa de seleção **Imposto retido/recuperável** é marcada).

![Impostos brasileiros](media/bra-brazilian-taxes.png)

> [!NOTE]
> Nunca use o tipo de imposto **INSS-CPRB**.

O relatório é agrupado por um valor **Tipo de código de serviço** (tabela 06 da documentação do SPED-Reinf). Portanto, você deve modificar o lançamento de notas fiscais de serviço para habilitar a captura dessas informações. Caso contrário, não é possível gerar o evento.

O evento envia quatro tipos de valores para o banco de dados do governo:

-   **Retenção** – O tipo de imposto INSS Retido calculado que está vinculado à linha da nota fiscal.

-   **Retenção adicional** – Uma variação do tipo de imposto INSS que está vinculado à linha da nota fiscal.

-   **Retenção suspensa** – O valor do tipo de imposto INSS Retido suspenso.

-   **Retenção adicional suspensa** – O valor suspenso da variação do tipo de imposto INSS que está vinculado à linha da nota fiscal.

Sempre que uma suspensão de valores ocorrer, o processo legal ou administrativo associado deve ser especificado no evento para oferecer suporte aos motivos da suspensão ou explicá-los. Essas informações devem ser inseridas manualmente nos campos **Valor da retenção** e **Valor da retenção adicional** na página **Processo administrativo e judicial** que é descrita na seção anterior.

O evento R-2010 usa o conceito de fechamento. Depois que esse evento for fechado, o serviço Web recusará quaisquer novas entradas ou modificações nele, a menos que seja reaberto manualmente.

> [!NOTE]
> Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

### <a name="event-r-2020-provided-services"></a>Evento R-2020, "Serviços fornecidos"

O evento periódico R-2020 é usado para relatar, ao sistema da autoridade fiscal, as informações sobre os valores de retenção para a previdência social que estão presentes em notas fiscais de serviço emitidas pelos estabelecimentos fiscais de uma organização fiscal.

Esse evento funciona como o evento R-2010, mas você deve considerar as contas de cliente e o modelo de nota fiscal SE (saída) que é emitido pelo estabelecimento fiscal.

> [!NOTE]
> Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

### <a name="event-r-2060-inss-cprb"></a>Evento R-2060, "INSS CPRB"

O evento periódico R-2060 é usado para enviar informações sobre a apuração de imposto da retenção para a previdência social ao SPED-Reinf quando a organização fiscal escolher calcular a previdência social com base na receita bruta em vez da folha de pagamento.

Portanto, antes de gerar o evento, você deve realizar a apuração de imposto por organização fiscal no módulo **Livros fiscais**. Quando essa opção é estabelecida nos parâmetros do SPED-Reinf, os usuários podem criar a apuração de imposto para o INSS-CPRB e os impostos são calculados automaticamente com base nos critérios definidos nos Parâmetros de livros fiscais.

O Microsoft Dynamics pegará todas as notas fiscais que estão registradas no período relacionado e que representam a receita e aplicará a alíquota de imposto ao valor base. A alíquota de imposto aplicada pode variar, dependendo do produto ou serviço que gerou a receita. O resultado será o valor de CPRB.

Para essa finalidade, um novo tipo de imposto brasileiro, o **INSS-CPRB**, foi criado. Esse tipo de imposto só é usado na apuração do imposto INSS-CPRB.

> [!NOTE]
> Não use o tipo de imposto **INSS-CPRB** para outras finalidades.

Como a apuração do imposto INSS-CPRB é um tipo de apuração de imposto, ajustes podem ser necessários. Esses ajustes devem ser inseridos manualmente como adições ou reduções.

Por fim, a apuração do imposto e os ajustes determinam o valor de CPRB que deve ser pago. No entanto, a geração do diário de pagamento e o registro nesse pagamento não são o escopo desse recurso.

Os períodos nessa nova apuração de imposto devem ser gerenciados da mesma forma que em outras apurações. Em outras palavras, a apuração de imposto pode ser criada ou atualizada somente enquanto estiver aberta. Após ser finalizada, não poderá mais ser alterada a menos que seja reaberta.

Após a criação da apuração de imposto e a realização dos ajustes necessários, o evento periódico R-2060 pode ser gerado.

O evento R-2060 inclui os totais da apuração de impostos e detalhes dos cálculos de impostos por código de atividade econômica, ajustes (adições e reduções, quando aplicável) e referências a processos legais e administrativos.

#### <a name="repro-step--setup"></a>Etapa de reprodução – Configuração

1.  Vá para **Livros fiscais \> Configuração \> Organização fiscal**.

2.  Defina a opção **CPRB** como **Sim** para habilitar a criação da apuração do INSS-CPRB e a transmissão do evento R-2060.

3.  Vá para **Livros fiscais \> Configuração \> Sped Reinf \> Códigos de atividades econômicas**. Os códigos de atividades econômicas devem ser configurados para habilitar o cálculo automático dos valores do imposto INSS-CPRB, pois a nota fiscal não possui informações relacionadas sobre esse imposto. Essa abordagem foi implementada para facilitar a configuração da matriz de impostos.

4.  Selecione **Novo** para criar um código de atividade econômica e insira uma descrição. Você deve verificar a Tabela 09 do Sped REINF no site da autoridade fiscal.

5.  Selecione o código de imposto que contém a alíquota de imposto para aplicar ao produto ou serviço. Você deve criar um tipo de imposto INSS Retido.

6.  Na guia **Linha**, insira os produtos ou serviços que estão relacionados pela atividade econômica. Os produtos são identificados pelo código de classificação fiscal e os serviços pelo código de serviço (federal).

#### <a name="repro-step--create-tax-assessment-option-1"></a>Etapa de reprodução – Criar apuração de imposto (opção 1)

1.  Vá para **Livros fiscais \> Comum \> Período de escrituração**.

2.  Selecione um período de escrituração.

3.  No Painel de Ação, selecione **INSS-CPRN** e, em seguida, selecione **Novo** para criar uma apuração de imposto. O Microsoft Dynamics automaticamente cria a apuração de imposto para o período de escrituração selecionado.

#### <a name="repro-step--create-tax-assessment-option-2"></a>Etapa de reprodução – Criar apuração de imposto (opção 2)

1.  Vá para **Livros fiscais \> Comum \> Apuração de imposto \> INSS-CPRB** e, em seguida, selecione **Apuração do imposto INSS-CPRB**.

2.  Selecione o período de escrituração e, em seguida, selecione **OK**.

> [!NOTE]
> Você poderá receber o seguinte aviso: “Linha XXXX: não foi possível identificar o código da atividade econômica”. Esse aviso indica que o Microsoft Dynamics não encontrou o código da atividade econômica para a linha e a nota fiscal relacionadas. Nesse caso, você deve concluir a configuração que é descrita na etapa de reprodução anterior.

**Excluir**

Você poderá excluir uma apuração do imposto INSS-CPRB existente se o status for **Aberto**.

**Notas fiscais e operações não fiscais**

Quando os impostos INSS-CPRB são apurados, o valor tributável da nota fiscal é considerado e classificado durante o processo de apuração. Você pode visualizar as operações não fiscais e as notas fiscais relacionadas que fazem parte do cálculo do imposto.

**Transações de imposto**

Quando os impostos INSS-CPRB são apurados, você pode visualizar os detalhes das transações de imposto que são gerados pelo processo.

**Ajuste**

Você pode inserir transações de ajuste adicionais para ajustar (aumentar ou diminuir) o valor do INSS-CPRB calculado. Configure os códigos de ajuste em **Livros fiscais \> Configuração \> Códigos de ajuste de imposto \> Tabela de códigos de ajustes de INSS-CPRB**.

1.  Selecione **Ajuste** para adicionar uma transação de ajuste que diminuirá ou aumentará o valor do imposto (débito) que é calculado.

2.  Selecione o código de ajuste.

3.  Insira uma descrição da transação relacionada.

4.  Especifique o valor do ajuste e a atividade econômica.

5.  Especifique a data do ajuste.

    > [!NOTE]
    > Os ajustes de INSS-CPRB estão disponíveis apenas por meio desse procedimento. Esse tipo de ajuste não está disponível em **Livros fiscais \> Diários \> Ajuste geral de imposto/benefício/incentivo**.

**Finalizar e reabrir**

Você pode finalizar ou reabrir a apuração do imposto INSS-CPRB relacionada.

Quando uma apuração do imposto INSS-CPRB é finalizada, nenhuma modificação é permitida nessa apuração para esse período, a menos que ela seja reaberta. Um comprovante é criado para lançar o imposto INSS-CPRB para coleta e as contas contábeis são definidas no lançamento contábil para o imposto INSS em **Imposto \> Configuração \> Imposto sobre vendas \> Grupos de lançamento contábil**.

> [!NOTE]
> Na atual arquitetura do SPED-Reinf definida pelo governo, o processo de pagamento e liquidação do passivo criado pela apuração de imposto será relatado a outro sistema chamado de DCTF Web. Esse sistema consome a saída não apenas do SPED-Reinf, mas também de outros sistemas, como o eSocial e o PER/DCOMP. Portanto, o processo de pagamento atualmente está fora do escopo e é entregue por meio de outro recurso do Microsoft Dynamics.

A ação de reabertura estará disponível se o evento R-2060 já tiver sido fechado para o estabelecimento fiscal matriz e se a apuração de imposto já estiver finalizada. A ação de reabertura reverte o comprovante anterior que foi gerado pela ação de fechamento.

> [!NOTE]
> Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

### <a name="events-r-2090-closing-and-r-2098-reopen"></a>Eventos R-2090, "Fechamento" e R-2098, "Reabertura"

**Fechamento**

Os eventos periódicos R-2010, R-2010 e R-2060 devem ser fechados ao final de um período, quando não houver mais nenhuma transação a ser relatada nesse período.

#### <a name="repro-step"></a>Etapa de reprodução

1.  Finalize a apuração do imposto INSS-CPRB, mesmo que você não apure o imposto INSS-CPRB.

2.  Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

**Reabrir**

Depois que os eventos periódicos R-2010, R-2010 e R-2060 forem fechados por meio de um evento R-2099, eles poderão ser reabertos por meio de um evento R-2098. Você poderá então relatar novas transações ou modificar transações existentes para o período.

#### <a name="repro-step"></a>Etapa de reprodução

1.  Reabra a apuração do imposto INSS-CPRB, mesmo que você não apure o imposto INSS-CPRB.

2.  Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.

**Consultar evento 5011**

1.  Após a entrega do R-2090 ao governo e a atualização de seu status para **Aguardando resposta** (**Resposta pendente)**, selecione **Executar processamento** e, em seguida, selecione **SPED Reinf**.

2.  Defina a opção **Escolher ação** como **Habilitar** e, em seguida, selecione a ação **Gerar** para gerar a mensagem XML.

3.  Selecione **OK** para confirmar a ação.

4.  Depois que o item de mensagem é criado, o tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Consulta Gerada**.

5.  Selecione **Executar processamento** e, em seguida, selecione **SPED Reinf** novamente.

6.  Defina a opção **Escolher ação** como **Habilitar** e selecione a ação **Enviar consulta** para entregar a consulta relacionada às autoridades fiscais.

7.  Selecione **OK** para confirmar a ação.

8.  O tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Consulta Enviada**.

9.  Selecione **Executar processamento** e, em seguida, selecione **SPED Reinf** novamente.

10. Defina a opção **Escolher ação** como **Habilitar** e selecione a ação **Obter consulta resposta** para obter a aprovação da autoridade fiscal e o número do protocolo final, para poder fechar o período do SPED-Reinf.

11. Selecione **OK** para confirmar a ação.

12. O tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Aceito**.
