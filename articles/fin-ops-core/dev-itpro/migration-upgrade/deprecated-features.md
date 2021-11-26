---
title: Recursos removidos ou obsoletos em versões anteriores
description: Este tópico descreve os recursos que foram removidos ou que foram planejados para remoção do Dynamics 365 for Finance and Operations e versões anteriores.
author: sericks007
ms.date: 02/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2e03becf2572aeaf213e8c3a0e874405ed0d5613
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753017"
---
# <a name="removed-or-deprecated-features-in-previous-releases"></a>Recursos removidos ou obsoletos em versões anteriores

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!IMPORTANT]
> Este tópico não é mais atualizado. Para ver uma lista atual de recursos que foram removidos ou descontinuados dos aplicativos do Finance and Operations, pesquise o conteúdo **"Recursos removidos ou obsoletos"** relacionado ao aplicativo que você está usando.

Este tópico descreve os recursos que foram removidos ou descontinuados do Dynamics 365 for Finance and Operations e versões anteriores desse produto.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](/dynamics/s-e/global/axtechrefrep_61). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="finance-1007-with-platform-update-31"></a>Finance 10.0.7 com atualização de plataforma 31

### <a name="chinese-voucher-types-without-account-groups-selection"></a>Tipos de comprovantes chineses sem seleção de Grupos de conta
|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Recurso alterado para a seleção de grupos de contas. |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Substituído: até 1º de dezembro de 2020, não planejamos mais oferecer suporte à configuração de tipos de comprovantes chineses sem a seleção de Grupos de contas. Obtenha mais detalhes sobre o novo design do recurso em Novidades no 10.0.7 |

## <a name="finance-and-operations-1006-with-platform-update-30"></a>Finance and Operations 10.0.6 com Platform update 30


### <a name="dimensionhashgethashstr-_message"></a>DimensionHash.getHash(str _message)

|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O Windows está substituindo o uso de SHA1, como documentado em [Imposição de certificados SHA1 feita pelo Windows](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx).  |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Solicitação de Emprego |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: em 1º de abril de 2020, os desenvolvedores devem usar as APIs de plataforma encontradas na classe **HasFunction**. |

### <a name="hashcomputesha1hashstring-message"></a>Hash.ComputeSHA1Hash(mensagem de cadeia de caracteres)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O Windows está substituindo o uso de SHA1, como documentado em [Imposição de certificados SHA1 feita pelo Windows](https://social.technet.microsoft.com/wiki/contents/articles/32288.windows-enforcement-of-sha1-certificates.aspx).  |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Plataforma |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: em 1º de abril de 2020, os desenvolvedores devem usar as APIs de plataforma encontradas na classe **HasFunction**. |


### <a name="formdatetimecontrolsetutcstring"></a>FormDateTimeControl.setUtcString()

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos desativando o método **setUtcString()**, pois há um método de substituição melhor disponível. |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Plataforma |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: até 1 de outubro de 2020, planejamos não dar mais suporte ao método **setUtcString()**. Os desenvolvedores devem usar o método **setUtcDateTime()** em seu lugar. |

### <a name="blocklist-report-it--feature-reference-it-00001"></a>Relatório da lista de bloqueios (TI) – Referência de recursos IT-00001

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Não é legalmente obrigatório. |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Localização em italiano |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: até 1º de outubro de 2020, nós planejamos não oferecer mais suporte a este relatório. |

### <a name="domestic-tax-report--feature-reference-it-00003"></a>Relatório de imposto doméstico – Referência de recursos IT-00003

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Não é legalmente obrigatório. |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Localização em italiano |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: até 1 de outubro de 2020, planejamos não dar mais suporte a **Relatório de imposto doméstico – Referência de recursos IT-00003**. |

## <a name="october-2019-deprecation-announcement"></a>Anúncio de depreciação de outubro de 2019

### <a name="flowchart-diagrams-in-business-process-modeler"></a>Diagramas do fluxograma no modelador de processo de negócios

<table>
<tbody>
<tr>
<td><strong>Motivo para a reprovação/remoção</strong></td>
<td>Estamos preterindo o componente de diagramas de fluxograma no BPM (Business Process Modeler), porque o projeto herdado causou baixo uso.</td>
</tr>
<tr>
<td><strong>Substituída por outro recurso?</strong></td>
<td>Não</td>
</tr>
<tr>
<td><strong>Áreas afetadas</strong></td>
<td>Modelador de processo de negócios</td>
</tr>
<tr>
<td><strong>Status</strong></td>
<td>Preterido: o componente de diagramas de fluxograma no BPM deve ser removido em 2020. A seguinte funcionalidade estará indisponível:
<ul>
<li>Todos os fluxogramas serão somente leitura e não estarão disponíveis para edição. As propriedades de forma associadas a atividades de fluxograma também não estarão disponíveis. Esses fluxogramas incluem os fluxogramas padrão gerados automaticamente e personalizados que são modificados com base nesses fluxogramas padrão.</li>
<li>As etapas do processo serão somente leitura e não estarão disponíveis para edição.</li>     
<li>O recurso análise de lacuna/ajuste herdado não estará disponível. Portanto, nenhuma lista de lacunas será criada automaticamente ou estará disponível para exportação.
<p><strong>Observação:</strong> este recurso foi substituído anteriormente e substituído pelas integrações do Microsoft Azure DevOps.</p>
</li>
<li>O histórico da versão do fluxograma não estará disponível.</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="finance-and-operations-1005-with-platform-update-29"></a>Finance and Operations 10.0.5 com Platform update 29

### <a name="us-payroll-tax-updates"></a>Atualizações de impostos de Folha de pagamento dos EUA

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos desativando atualizações de impostos para a funcionalidade de Folha de pagamento dos EUA devido à baixa utilização e funcionalidade aprimorada que agora é oferecida por meio de integrações estratégicas.  |
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Payroll |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: em 31 de julho de 2024, pretendemos não fornecer mais atualizações de impostos para clientes de Folha de Pagamento dos EUA. A funcionalidade permanecerá no produto; mas os aprimoramentos não atualizarão a funcionalidade e os defeitos de produtos serão avaliados caso a caso. |

>[!NOTE]
> Isso representa uma alteração da data de descontinuação original de 1º de outubro de 2021. Para obter mais informações, consulte [Atualizações de impostos serão desativadas para o recurso Folha de pagamento dos EUA no Microsoft Dynamics 365 for Finance and Operations](https://aka.ms/financepayrollfaq).


### <a name="data-management-staging-clean-up"></a>Limpeza de preparo de gerenciamento de dados
|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Não atende aos principais requisitos necessários para agendar a limpeza periódica. |
| **Substituída por outro recurso?**   | Sim, o recurso de limpeza de histórico de trabalho será adicionado para atender holisticamente aos cenários. |
| **Áreas afetadas do produto**         | Gerenciamento de dados |
| **Opção de implantação**              | Todas  |
| **Status**                         | Preterido: o período determinado para a remoção da funcionalidade é dezembro de 2020. |

## <a name="finance-and-operations-1004-with-platform-update-28"></a>Finance and Operations 10.0.4 com Platform update 28

### <a name="france-fec-accounting-data-export-in-xml"></a>França: exportação de dados de contabilidade de FEC em XML

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por formato TXT, **Arquivo de auditoria de FEC da França** está disponível por meio de **Contabilidade** \> **Tarefas periódicas** \> **Exportação de dados**.
| **Substituída por outro recurso?**   | Sim |
| **Áreas afetadas do produto**         | Contabilidade |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido. O período determinado para a remoção da funcionalidade é julho de 2020. |


### <a name="legacy-navigation-bar"></a>Barra de navegação herdada

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Alinhamento de cabeçalho com outros produtos do Dynamics e Office. Para obter mais detalhes, consulte [Barra de navegação atualizada que se alinha com o cabeçalho do Office](/business-applications-release-notes/April19/dynamics365-finance-operations/updatednavbar).
| **Substituída por outro recurso?**   | A partir da atualização 24 da plataforma, uma barra de navegação reestilizada que apresenta a pesquisa foi introduzida. |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir de abril de 2020, a barra de navegação herdada não estará mais disponível. Até esse ponto, os clientes podem reverter para a barra de navegação legada por meio das opções **Opções de desempenho do cliente**. |


## <a name="finance-and-operations-1002-with-platform-update-26"></a>Finance and Operations 10.0.2 com Platform update 26


### <a name="legacy-default-action-behavior"></a>Comportamento de ação padrão herdada

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O comportamento herdado de ações padrão nas grades faz com que uma coluna inesperada tenha o link de ação padrão depois que as colunas da grande forem reordenadas por meio de personalização. O novo recurso de ação de aderência padrão corrige isso. Para obter mais detalhes, consulte [Ações de aderência padrão em grades](/business-applications-release-notes/October18/dynamics365-finance-operations/sticky-default-action). |
| **Substituída por outro recurso?**   | A partir da Platform update 21, foi introduzido um recurso para "ações de aderência padrão". Esse recurso pode ser habilitado na página **Opções de desempenho do cliente**. |
| **Áreas afetadas do produto**         | Grades no cliente Web |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir de abril de 2020, as ações de aderência padrão serão o comportamento padrão, sem um mecanismo para reverter ao comportamento herdado. |

### <a name="legacy-is-one-of-filtering-experience"></a>Experiência de filtragem "é um de" herdada

|&nbsp;   | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A experiência de filtragem “é um de” foi remodelada na Platform update 22, sendo que o plano é que esta seja a única experiência de filtragem "é um de". |
| **Substituída por outro recurso?**   | A partir da Platform update 22, foi disponibilizada uma experiência de filtragem "é um de" aprimorada na página **Opções de desempenho do cliente**. Para obter mais informações, consulte [Experiência de filtragem "é um de" otimizada](/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering). |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: a partir de abril de 2020, a experiência aprimorada "é um de" será o comportamento padrão, sem um mecanismo para reverter ao comportamento herdado. |

### <a name="parameter-to-enable-sales-orders-with-multiple-project-contract-funding-sources"></a>Parâmetro para permitir ordens de venda com várias fontes de financiamento do contrato de projeto
Suporte à criação de ordens de venda baseadas no projeto em que o contrato de projeto com várias fontes de financiamento está habilitado com a configuração **Parâmetros de gerenciamento do projeto** e **Permitir ordens de venda para projetos com várias fontes de financiamento**. Por padrão, esse parâmetro não está habilitado. 

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A funcionalidade será sempre habilitada depois que o parâmetro for removido. |
| **Substituída por outro recurso?**   | Nº A funcionalidade para dar suporte a ordens de venda baseadas no projeto com várias fontes de financiamento estará sempre habilitada.   |
| **Áreas afetadas do produto**         |O parâmetro **Permitir ordens de venda para projetos com várias fontes de financiamento** será removido. Os seguintes métodos serão modificados quando o parâmetro for removido: método **ctrlSalesOrderTable** na classe **ProjStatusType**, método **validar** para o campo **ProjId** e o método de **execução** no formulário **SalescreateOrder**. Os seguintes métodos serão substituídos quando o parâmetro for removido: **IsSalesOrderAllowedForMultipleFundingSources** no arquivo da tabela **ProjTable**, o método **IsAllowSalesOrdersForMultipleFundingSourcesParamEnabled** no arquivo da tabela **ProjTable**, o campo de dados **AllowSalesOrdersForMultipleFundingSources** no formulário **ProjParameters** e nos arquivos **ProjParameterEntity**, o método privado **IsAssociatedToMultipleFundingSourcesContract** no arquivo da tabela **ProjTable**. |
| **Opção de implantação**              | Todas  |
| **Status**                         | A substituição está planejada para a liberação da onda de abril de 2020. |

### <a name="legacy-workflow-reports-for-tracking-and-instance-status"></a>Relatórios do fluxo de trabalho herdados para rastreamento e status de instância

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O relatórios de fluxo de trabalho herdados para rastreamento e status de instância estão sendo preteridos porque não se faz mais referência a eles na navegação. Os nomes dos relatórios são WorkflowWorkflowInstanceByStatusReport e WorkflowWorkflowTrackingReport. |
| **Substituída por outro recurso?**   | O formulário de histórico do fluxo de trabalho poderá ser utilizado no lugar deles. |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: o período determinado para a remoção da funcionalidade é abril de 2020. |

## <a name="finance-and-operations-1001-with-platform-update-25"></a>Finance and Operations 10.0.1 com Platform update 25

### <a name="deprecated-apis-and-potential-breaking-changes"></a>APIs preteridas e alterações significativas possíveis


#### <a name="deriving-from-internal-classes-is-deprecated"></a>A derivação de classes internas é obsoleta

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Antes da Platform update 25, era possível criar uma classe ou tabela derivada de uma classe/tabela interna definida em outro pacote/módulo. Esta não é uma prática de codificação segura. A partir da Platform update 25, o compilador exibirá um aviso. |
| **Substituída por outro recurso?**   | O aviso do compilador será substituído por um erro na Platform update 26. Essa alteração é compatível com versões anteriores no tempo de execução, significando que, a Platform update 25 ou mais recente poderá ser implantada em qualquer ambiente de área restrita ou de produção sem a necessidade de modificar o código personalizado. Essa alteração afeta apenas o tempo de desenvolvimento e compilação.|
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: o aviso se tornará um erro de compilação na Platform update 26. |

#### <a name="overriding-internal-methods-is-deprecated"></a>A substituição de métodos internos está obsoleta

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Antes da Platform update 25, era possível substituir um método interno em uma classe derivada definida em outro pacote/módulo. Esta não é uma prática de codificação segura. A partir da Platform update 25, o compilador exibirá um aviso. |
| **Substituída por outro recurso?**   | Esse aviso será substituído por um erro do compilador na Platform update 26. Essa alteração é compatível com versões anteriores no tempo de execução, significando que, a Platform update 25 ou mais recente poderá ser implantada em qualquer ambiente de área restrita ou de produção sem a necessidade de modificar o código personalizado. Essa alteração afeta apenas o tempo de desenvolvimento e compilação. |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: o aviso se tornará um erro de compilação na Platform update 26. |

## <a name="finance-and-operations-1000-with-platform-update-24"></a>Finance and Operations 10.0.0 com Platform update 24

### <a name="renaming-released-products"></a>Renomeação de produtos liberados 
| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Quando você usa a função **Renomear chave primária** para alterar a ItemId de um produto lançado, apenas as referências diretas à chave estrangeira são atualizadas. Quaisquer outras referências ao produto lançado, como ordens de produção, manterão a antiga ItemId. Como resultado, pode haver dados inconsistentes que por fim bloquearão os processos de negócios. |
| **Substituída por outro recurso?**   | Nº |
| **Áreas afetadas do produto**         | Gerenciamento de informações do produto |
| **Opção de implantação**              | Todas  |
| **Status**                         | Removido a partir do Finance and Operations 10.0.0 com atualização de plataforma 24.|


## <a name="finance-and-operations-813-with-platform-update-23"></a>Finance and Operations 8.1.3 com Platform update 23

### <a name="sql-server-reporting-services-reportviewer-control"></a>Controle ReportViewer do SQL Server Reporting Services
Os clientes podem usar a ação **Exportar** fornecida pelo controle ReportViewer do SQL Server Reporting Services (SSRS) para baixar documentos produzidos por aplicativos do Finance and Operations. Essa apresentação baseada em HTML do relatório oferece aos usuários uma visualização não paginada do documento.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A natureza não paginada da experiência de visualização baseada em HTML **não** oferece fidelidade aos documentos físicos produzidos pelo Finance and Operations. Ao adotar totalmente o PDF como o formato padrão para documentos comerciais, os usuários poderão aproveitar uma experiência de exibição moderna com aumento de desempenho quando gerarem relatórios de aplicativos. |
| **Substituída por outro recurso?**   | A partir de agora, os documentos PDF serão o formato padrão para relatórios renderizados pelo Finance and Operations.   |
| **Áreas afetadas do produto**         | Essa mudança **não** afeta os cenários do cliente em que os relatórios são distribuídos eletronicamente ou enviados diretamente para as impressoras.    |
| **Opção de implantação**              | Todas  |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. A funcionalidade para visualizar automaticamente os relatórios de aplicativos usando um visualizador de PDF está planejada para a atualização da plataforma de maio de 2019. |

### <a name="client-kpi-controls"></a>Controles do KPI do cliente
Os principais indicadores de desempenho (KPIs) incorporados podem ser modelados no Visual Studio por um desenvolvedor e ainda personalizados pelo usuário final.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os controles de clientes nativos usados para definir KPIs têm baixa aceitação do cliente e contam com um desenvolvedor para adicionar métricas rastreáveis. |
| **Substituída por outro recurso?**   | O serviço PowerBI.com oferece ferramentas de primeira classe para definir e gerenciar KPIs com base em dados de fontes externas.  Em uma próxima versão, planejamos permitir que você incorpore soluções hospedadas no PowerBI.com em espaços de trabalho de aplicativos.   |
| **Áreas afetadas do produto**         | Essa atualização impedirá os desenvolvedores de introduzir novos controles de KPI no designer do Visual Studio.    |
| **Opção de implantação**              | Todas  |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="deprecated-apis-and-future-breaking-changes"></a>APIs preteridas e alterações significativas futuras

#### <a name="field-groups-containing-invalid-field-references"></a>Grupos de campos contendo referências de campo inválidas

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | É possível que as definições de metadados de tabela tenham grupos de campos contendo referências de campo inválidas. Se implantada, ela pode causar falhas de tempo de execução no Financial Reporting e no SQL Server Reporting Services (SSRS). Esse problema é atualmente classificado como um *aviso do compilador* em vez de um *erro*, ou seja, a implantação e a criação de pacote implantável podem continuar sem corrigir o problema. Para corrigir esse problema:<br><br>1. Remova a referência de campo inválida da definição do grupo de campos da tabela.<br><br>2. Recompile.<br><br>3. Certifique-se de que qualquer aviso ou erro seja tratado. |
| **Substituída por outro recurso?**   | Esse aviso será substituído por um erro de compilação no futuro. |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido : O aviso é um erro de tempo de compilação nas atualizações de plataforma para a versão 10.0.11 dos aplicativos do Finance and Operations. |

#### <a name="complete-list"></a>Lista completa
Para acessar a lista completa das APIs que estão sendo substituídas, consulte [Substituição de métodos e elementos de metadados](deprecation-deletion-apis.md).

## <a name="finance-and-operations-81-with-platform-update-20"></a>Finance and Operations 8.1 com Platform update 20

### <a name="batch-transfer-rules-for-subledger-journal-account-entries"></a>Regras de transferências de lote para entradas de conta no diário-razão auxiliar
O modo de transferência Síncrono está ficando obsoleto nos parâmetros da Contabilidade.  Esse modo é substituído por lote Assíncrono e programado somente, o que já existe como opções para transferência. Para obter informações adicionais, consulte o blog [Parâmetros da contabilidade — regras de transferência em lote](https://community.dynamics.com/365/financeandoperations/b/financials/archive/2019/03/15/general-ledger-parameters-batch-transfer-rules).

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos removendo a opção síncrona devido ao impacto de desempenho ao sistema. |
| **Substituída por outro recurso?**   | Lote assíncrono e programado são opções a serem usadas no lugar de Síncrona.   |
| **Áreas afetadas do produto**         | Contabilidade, Contas a Pagar, Contas a Receber, Compras, Despesa    |
| **Opção de implantação**              | Todas  |
| **Status**                         | Preterido: o período determinado para a funcionalidade ser removida é a versão 10.0.|

### <a name="electronic-reporting-for-russia"></a>Relatório eletrônico da Rússia
Recurso para configurar formatos de arquivo.txt e.xml de declarações. 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por relatório eletrônico. |
| **Substituída por outro recurso?**   | Sim. |
| **Áreas afetadas do produto**         | Contabilidade |
| **Opção de implantação**              | Todas |
| **Status**                         | Removido a partir do Finance and Operations 8.1 com atualização de plataforma 20. |

### <a name="financial-reports-generator-for-russia"></a>Gerador de relatórios financeiros da Rússia
Uma ferramenta para configurar coleções de dados para contabilidade e relatórios de imposto e exportar dados para modelos de relatório XLS e DOC. Partes funcionais: Os dados de exportação para modelos de relatório, consultas, requisitos fixos de XLS e DOC foram removidos. 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | As peças removidas foram substituídas por relatório eletrônico. |
| **Substituída por outro recurso?**   | Sim. A interface do usuário para configuração de relatórios financeiros deve ser usada para configurar regras de coleção de dados por contas do GL ou registros de imposto. Exportar dados para vários tipos de arquivo, requisitos fixos e regras de coleção de dados de consulta devem configurados no relatório eletrônico. |
| **Áreas afetadas do produto**         | Contabilidade. |
| **Opção de implantação**              | Todas |
| **Status**                         | Removido a partir do Finance and Operations 8.1 com atualização de plataforma 20. |

### <a name="integration-with-external-providers-for-sending-electronic-reporting-through-communication-channels-for-russia"></a>Integração com provedores externos para envio de relatórios eletrônicos por meio de canais de comunicação da Rússia
Recurso exportando arquivos eletrônicos gerados de declarações para pasta para envio posterior aos provedores oficiais de relatório eletrônico, bem como importar novamente o estado.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por recurso configurável de mensagens eletrônicas. |
| **Substituída por outro recurso?**   | Sim.  |
| **Áreas afetadas do produto**         | Contabilidade, Imposto |
| **Opção de implantação**              | Todas |
| **Status**                         | Removido a partir do Finance and Operations 8.1 com atualização de plataforma 20. |


### <a name="profit-tax-register-wizard"></a>Assistente de registro de impostos de lucros
Recurso para criar modelos para novos registros de impostos de lucro. Este recurso cria objetos X++ para os novos registros, que são criados como modelos com a lógica de cálculo adicional apropriado.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O recurso não é compatível com o modelo da extensibilidade do Finance and Operations. |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Imposto |
| **Opção de implantação**              | Todas |
| **Status**                         | Removido a partir do Finance and Operations 8.1 com atualização de plataforma 20. |

### <a name="payroll-and-human-resources-for-russia"></a>Folha de pagamento e Recursos Humanos para a Rússia
O módulo específico ao país da Rússia para gerenciar as informações de administração dos funcionários, os detalhes da folha de ponto para funcionários, contabilidade de folha de pagamento e criar declarações de pagamento. 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A folha de pagamento não é incluída no foco estratégico global do portfólio do Dynamics 365. Os parceiros e ISVs estão na melhor posição para oferecer a funcionalidade de folha de pagamento que esteja em conformidade com regulamentos locais e atualizações de impostos.|
| **Substituída por outro recurso?**   | Não|
| **Áreas afetadas do produto**         | Gerenciamento da Folha de Pagamento e Recursos Humanos Russos |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: prazo alvo para a funcionalidade ser removida é um uma das futuras atualizações da versão 10.0. |

## <a name="finance-and-operations-80-with-platform-update-15"></a>Finance and Operations 8.0 com Platform update 15
Nenhum recurso foi removido ou substituído com esta versão. A atualização 15 da plataforma é cumulativa e contém recursos novos ou alterados das atualizações 13, 14 e 15 da plataforma.

## <a name="finance-and-operations-enterprise-edition-73-with-platform-update-12"></a>Finance and Operations, Enterprise Edition 7.3 com atualização de plataforma 12

### <a name="personalized-product-recommendations"></a>Recomendações de produtos personalizados 
A partir de 15 de fevereiro de 2018, os varejistas não poderão exibir recomendações personalizadas de produto em um dispositivo do ponto de venda (PDV). Para obter mais informações, consulte [Visão geral das recomendações de produto](../../../commerce/product-recommendations.md).  

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos removendo a versão atual do serviço de recomendação de produto, pois estamos remodelando esse recurso em um algoritmo melhor com recursos mais novos orientados ao varejo.  |
| **Substituída por outro recurso?**   | Não. Entretanto, depois de junho de 2018, planejamos trazer de volta este recurso para aprimorar um novo serviço de recomendação.   |
| **Áreas afetadas do produto**         | Recomendações personalizadas de produtos em PDV.                                                    |
| **Opção de implantação**              | Todas                                                                                      |
| **Status**                         |Removido em 15 de fevereiro de 2018. Isso afeta os clientes que usam o Dynamics 365 for Operations 1611 e versões posteriores.  |

### <a name="extension-of-the-list-of-electronic-reporting-er-functions"></a>Extensão da lista de funções do ER (Relatório eletrônico)
A possibilidade de introduzir funções personalizadas a serem usadas no construtor de expressões do ER (para obter mais informações, consulte [Estender a lista de funções do ER (Relatório eletrônico)](../../dev-itpro/analytics/general-electronic-reporting-formulas-list-extension.md)) não tem mais suporte. Devido a alterações de APIs do ER, a API para chamar funções internas do construtor de expressões de ER tornou-se interna e não pode ser mais estendida.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Iniciativa de selagem de código  |
| **Substituída por outro recurso?**   | Nenhum. Sempre que uma nova função interna for necessária, uma nova solicitação de extensão deverá ser encaminhada à equipe da estrutura de ER.<br><br>Como um trabalho temporário, enquanto a função solicitada está em desenvolvimento pela equipe do ER, a lógica exigida pode ser programada como método de classe de um aplicativo personalizado. Esse método pode ser acessado em uma expressão de ER como uma propriedade da fonte de dados adicional de ER do tipo **Aplicativo\classe** que se refere àquela classe de aplicativo personalizado.  |
| **Áreas afetadas do produto**         | Estrutura de relatório eletrônico                                                      |
| **Opção de implantação**              | Todas                                                                                      |
| **Status**                         | Removido a partir do Finance and Operations, Enterprise Edition 7.3.    |

### <a name="inventory-by-item-group-and-inventory-by-inventory-dimension-aging-reports"></a>Relatórios de classificação por vencimento de estoque por grupo de itens e de estoque por dimensão de estoque

Esses dois relatórios não têm mais suporte no Finance and Operations. Em vez disso, o relatório de **Classificação por vencimento de estoque** pode ser usado para melhorar a experiência do usuário.

| &nbsp;  | &nbsp; |
|--------------|-----------------------|
| **Motivo para a depreciação**       | Funcionalidade duplicada  |
| **Substituída por outro recurso?** | Sim. Os dois relatórios foram substituídos pelo relatório **Classificação por vencimento de estoque**.     |
| **Áreas afetadas do produto**       | Gerenciamento de estoque, gerenciamento de custo        |
| **Opção de implantação**        | Todas|
| **Status**                       | Preterido: Os itens de menu de dois relatórios foram removidos na versão 7.3. Porém, o código dos relatórios permanece no produto. O plano é remover o código em uma versão futura. |

### <a name="power-bi-content-packs-available-on-appsource"></a>Pacotes de conteúdo do Power BI disponíveis no AppSource
Os pacotes de conteúdo **Gerenciamento de custos**, **Desempenho financeiro** e **Desempenho do canal de varejo**, disponíveis no site do [Microsoft AppSource](https://appsource.microsoft.com), foram preteridos em consequência de atualizações do produto no Microsoft Power BI. Os formulários de administração de sistema usados para implantar esses pacotes de conteúdo no PowerBI.com também estão sendo preteridos no Finance and Operations.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Atualizações do produto no Microsoft Power BI. |
| **Substituída por outro recurso?**   | Os pacotes de conteúdo de **Gerenciamento de custos**, **Desempenho financeiro** e **Desempenho do canal de varejo**, disponíveis no site do [AppSource](https://appsource.microsoft.com), estão sendo substituídos por aplicativos analíticos que permitem integrações de solução no nível de banco de dados. Para obter mais informações sobre aplicativos analíticos, consulte [Power BI incorporado em espaços de trabalho](../../dev-itpro/analytics/embed-power-bi-workspaces.md).    |
| **Áreas afetadas do produto**         | Gerenciamento de custo, Finanças e Varejo                                                                                               |
| **Opção de implantação**              | Somente nuvem (não há mais suporte para a integração com o PowerBI.com nas implantações locais).                                                                                                            |
| **Status**                         | Preterido: O período determinado de destino para a remoção de funcionalidade é T2 de 2018.    |

### <a name="standard-ui-in-data-management-workspace"></a>Interface de usuário padrão no espaço de trabalho de gerenciamento de dados

A interface de usuário padrão no gerenciamento de dados é interface de usuário herdada, que é a interface do usuário padrão apresentada aos usuários quando eles visitam o espaço de trabalho de gerenciamento de dados.

| &nbsp;  | &nbsp; |
|------------------|-------------------------|
| **Motivo para a reprovação/remoção** | Estamos investindo no fornecimento de novas experiências de usuário na nova interface do usuário.             |
| **Substituída por outro recurso?**   | A nova Interface do usuário chamada *Exibições avançadas* está substituindo a interface do usuário antiga.            |
| **Áreas afetadas do produto**         | Espaço de trabalho de gerenciamento de dados                                                     |
| **Opção de implantação**              | Todas                                                                           |
| **Status**                         | Preterido: o período determinado para a remoção da funcionalidade é o T2 de 2018. |

### <a name="excise-sales-tax-service-tax-for-india"></a>Imposto embutido, impostos, imposto sobre serviço na Índia

Esses impostos foram incluídos no GST da Índia.

|  &nbsp;                                           |      &nbsp;                                                                   |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo para a remoção ou reprovação**       | Esses impostos foram incluídos no GST da Índia.                          |
| **Substituída por outro recurso?**            | GST da Índia                                                              |
| **Áreas afetadas do produto**                  | Imposto                                                                     |
| **Opção de implantação**                       | Todos os módulos                                                   |
| **Status**                                  | Preterido: Uma data de remoção não foi definida para esse recurso. |    

### <a name="file-validation-utility-fvu-for-india"></a>FVU (Utilitário de Validação de Arquivo) da índia

|              &nbsp;                               |      &nbsp;                                                                   |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo para a remoção ou reprovação**       | Escassez de uso do cliente                                                  |
| **Substituída por outro recurso?**            | Não                                                                      |
| **Áreas afetadas do produto**                  | Retenção de imposto da Índia                                                  |
| **Opção de implantação**                       | Todos os módulos                                                                    |
| **Status**                                  | Preterido: Uma data de remoção não foi definida para esse recurso.   |        

### <a name="tdstcs-certificate-for-india"></a>Certificado de TDS/TCS para a Índia

Os usuários podem baixar desse portal do governo.

|             &nbsp;                                |    &nbsp;                                                                     |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo para a remoção ou reprovação**       | Escassez de uso do cliente                                                  |
| **Substituída por outro recurso?**            | Não                                                                      |
| **Áreas afetadas do produto**                  | Retenção de imposto da Índia                                                  |
| **Opção de implantação**                       | Todos os módulos                                                                   |
| **Status**                                  | Preterido: Uma data de remoção não foi definida para esse recurso.     |    

### <a name="exportimport-exim-incentive-scheme-for-india"></a>Esquema de incentivos (EXIM) de exportação/importação para a Índia


|              &nbsp;                               |        &nbsp;                                                                 |
|---------------------------------------------|-------------------------------------------------------------------------|
| **Motivo para a remoção ou reprovação**       | Escassez de uso do cliente                                                  |
| **Substituída por outro recurso?**            | Não                                                                      |
| **Áreas afetadas do produto**                  | Importar e exportar                                                       |
| **Opção de implantação**                       | Todos os módulos                                                                    |
| **Status**                                  | Preterido: Uma data de remoção não foi definida para esse recurso.  |    


## <a name="dynamics-365-for-retail-72"></a>Dynamics 365 for Retail 7.2

### <a name="personalized-product-recommendations"></a>Recomendações de produtos personalizados 
A partir de 15 de fevereiro de 2018, os varejistas não poderão exibir recomendações personalizadas de produto em um dispositivo do ponto de venda (PDV). Para obter mais informações, consulte [Visão geral das recomendações de produto](../../../commerce/product-recommendations.md).  

|  &nbsp; |  &nbsp;|
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos removendo a versão atual do serviço de recomendação de produto, pois estamos remodelando esse recurso em um algoritmo melhor com recursos mais novos orientados ao varejo.  |
| **Substituída por outro recurso?**   | Não. Entretanto, depois de junho de 2018, planejamos trazer de volta este recurso para aprimorar um novo serviço de recomendação.   |
| **Áreas afetadas do produto**         | Recomendações personalizadas de produtos em PDV.                                                    |
| **Opção de implantação**              | Todas                                                                                      |
| **Status**                         |Removido em 15 de fevereiro de 2018. Isso afeta os clientes que usam o Dynamics 365 for Retail 7.2 e versões posteriores. |


## <a name="finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Finance and Operations, Enterprise Edition de julho de 2017 com atualização de plataforma 8

### <a name="currency-conversion-for-accounting-and-reporting-currencies"></a>Conversão de moeda para contabilidade e moedas do relatório

A conversão de moeda para contabilidade e moedas de relatórios foi introduzida quando o euro foi introduzido.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Uso e adição limitados da funcionalidade Copiar entidade legal como substituição.      |
| **Substituída por outro recurso?**   | Não, mas os recursos Copiar entidade legal e Configurações foram adicionados para tornar mais fácil mover-se para uma empresa que tem os principais requisitos de alteração. |
| **Áreas afetadas do produto**         | Gerenciamento financeiro     |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.   |


### <a name="warehouse-mobile-devices-portal"></a>Portal de dispositivos móveis do depósito

O portal de dispositivos móveis de depósito (WMDP) é um componente autônomo que foi criado para auto-implantação local. Não há mais suporte para este componente no Finance and Operations. Um aplicativo nativo que melhora a experiência do usuário substituiu a funcionalidade do WMDP.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Funcionalidade duplicada.       |
| **Substituída por outro recurso?**   | Sim. Este recurso foi substituído pelo Finance and Operations - Warehousing. Para obter mais informações sobre a configuração e os pré-requisitos, consulte [Visão geral da instalação e configuração do aplicativo de depósito](../../../supply-chain/warehousing/install-configure-warehousing-app.md). |
| **Áreas afetadas do produto**         | Gerenciamento de depósito, Gerenciamento de transporte     |
| **Opção de implantação**              | O portal de dispositivos móveis de depósito (WMDP) é um componente autônomo que foi criado para auto-implantação local.               |
| **Status**                         | Preterido: o período determinado para a remoção da funcionalidade é o T4 de 2019.   |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Regra avançada de correspondência de reconciliação bancária para correspondência manual

Uma regra de correspondência foi usada para selecionar e marcar um documento bancário quando os documentos foram correspondidos manualmente na planilha de reconciliação.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Uso restrito.                                                                         |
| **Substituída por outro recurso?**   | Não. Os recursos de filtragem da coluna devem ser usados para localizar documentos para a reconciliação. |
| **Áreas afetadas do produto**         | Gerenciamento de caixa e bancos                                                               |
| **Opção de implantação**              | Todas                                                                                    |
| **Status**                         | Removido em julho de 2017.                                                               |

## <a name="dynamics-365-for-operations-1611-with-platform-update-3"></a>Dynamics 365 for Operations 1611 com Platform update 3

### <a name="aeb-payment-formats-for-spain"></a>Formatos de pagamento para a Espanha AEB

Os formatos de pagamento CSB (Consejo Superior Bancario) foram usados para enviar arquivos de remessa para o banco para pagamentos de clientes e de fornecedores. O conteúdo desses formatos foi determinado pela Asociación Española de Banca. Abrange Cuaderno 19, 32, 58, 34.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                                  |
| **Substituída por outro recurso?**   | Sim, transferência de crédito de ISO20022 e os formatos de pagamento de débito direto para a Espanha |
| **Áreas afetadas do produto**         | Contas a pagar, Contas a receber                                    |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.           |

### <a name="bank-payments-transfer-for-lithuania"></a>Transferência de pagamentos bancários para Lituânia

As transferências de pagamento bancário foram geradas e impressas usando o formato de exportação de transferência de pagamento (LT) para Lituânia. O mercado lituano iniciou o uso do LITAS, o sistema bancário eletrônico, em 2005.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                        |
| **Substituída por outro recurso?**   | Sim, formato de pagamento de transferência de crédito ISO20022 para Lituânia     |
| **Áreas afetadas do produto**         | Contas a Pagar                                               |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>Formatos de pagamento de BBS Direkte Remittering para Noruega

Os formatos de pagamento de BBS Direkte Remittering incluem exportação de cobrança de pagamentos de clientes (débito direto) e importação de devolução da mensagem.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.  |
| **Substituída por outro recurso?**   | O formato de pagamento AvtaleGiro de clientes para Noruega pode ser usado para gerar mensagens de débito direto. Importação de devolução da mensagem será implementada em versões futuras. |
| **Áreas afetadas do produto**         | Contas a pagar, Contas a receber   |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.                                                                                                 |

### <a name="chart-of-accounts-tool-for-spain"></a>Ferramenta de plano de contas para Espanha

A ferramenta é usada quando um gráfico de contas na Espanha requer mudanças importantes. Os usuários podem importar um novo plano de contas no Microsoft Excel Excel ou em formato de texto e também podem importar demonstrativos financeiros.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Uso restrito                                                  |
| **Substituída por outro recurso?**   | Não                                                             |
| **Áreas afetadas do produto**         | Contabilidade                                                 |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="dom80-payment-format-for-belgium"></a>Formato de pagamento Dom80 para Bélgica

Formato de pagamento para legado da Bélgica do recolhimento de pagamentos (débito direto).

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                          |
| **Substituída por outro recurso?**   | Sim, formato de pagamento de débito direto ISO 20022 para Bélgica         |
| **Áreas afetadas do produto**         | Contas a Receber                                            |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="dtaezag-payment-formats-for-switzerland"></a>Formatos de pagamento DTA/EZAG para a Suíça

Os formatos DTA/EZAG integram-se no sistema ESR, pois eles têm número de referência. Como números de referência não são obrigatórios, esses formatos podem ser usados para processar quaisquer pagamentos de fornecedor. Esses formatos é usada por empresas que têm uma conta bancária em um local diferente “Postfinance”.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                        |
| **Substituída por outro recurso?**   | Sim, formato de pagamento de transferência de crédito ISO20022 para Suíça   |
| **Áreas afetadas do produto**         | Contas a Pagar                                               |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>Formato de pagamento de EDIFACT-DIRDEB para Áustria

Formato de pagamento para EDIFACT-DIRDEB do recolhimento de pagamentos (débito direto).

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                          |
| **Substituída por outro recurso?**   | Sim, formato de pagamento de débito direto ISO 20022 para Áustria         |
| **Áreas afetadas do produto**         | Contas a Receber                                            |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="edivat-for-belgium"></a>EDIVAT para Bélgica

EDIVAT é um padrão belga obsoleto para a declaração eletrônica por e-mail seguro. O Dynamics AX 2012 mantém a solução somente leitura para permitir o acesso aos dados históricos.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A funcionalidade não é mais usada.                           |
| **Substituída por outro recurso?**   | Não                                                             |
| **Áreas afetadas do produto**         | Contabilidade                                                 |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>formato de importação de pagamento eGiro EDIFACT CREMUL para Noruega

eGiro é baseado no padrão internacional da UN EDIFACT CREMUL(mensagem de aviso de crédito múltiplo), usado para o lançamento automático de pagamentos de cliente. No Dynamics AX, o eGiro é implementado como um formato de importação de pagamento de cliente.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                                                     |
| **Substituída por outro recurso?**   | Sim, a importação de notificação ISO20022 Camt.054. |
| **Áreas afetadas do produto**         | Contas a Receber                                                                       |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.                            |

### <a name="external-inventory-for-poland"></a>Para o estoque externo Polônia

Evidência de mercadorias obtidas de um fornecedor para vendas sem compra. Os bens manuseados em estoque externo não afetam o estoque padrão e podem ser vendidos e depois adquiridos automaticamente. Este processo criar movimentos real de estoque.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por outro recurso                                    |
| **Substituída por outro recurso?**   | Sim, a funcionalidade de remessa de entrada principal                |
| **Áreas afetadas do produto**         | Contas a pagar, gerenciamento de estoque                         |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="financial-reports-generator-for-eastern-europe"></a>Gerador de relatórios para Oriental financeiro Europa

Uma ferramenta para configurar coleções de dados para contabilidade e relatórios de imposto e exportar dados para modelos de relatório XLS e DOC

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Uso restrito                                                                            |
| **Substituída por outro recurso?**   | Não. A ferramenta será substituída por configurações de relatório eletrônico em versões futuras. |
| **Áreas afetadas do produto**         | Contabilidade                                                                           |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Importação de transações de pagamento de cliente para Finlândia

Você pode selecionar um formato de importação para pagamentos finlandeses que importa as transações de pagamento de cliente de um arquivo externo fornecido pelo banco.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                                                     |
| **Substituída por outro recurso?**   | Sim, a importação de notificação ISO20022 Camt.054. |
| **Áreas afetadas do produto**         | Contas a Receber                                                                       |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.                            |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Importação de transações de pagamento em um diário-razão para Finlândia

Um formato que é específico para a Finlândia para importar transações de contabilização na contabilidade.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                                                     |
| **Substituída por outro recurso?**   | Sim, a importação do extrato bancário ISO20022 Camt.053 usando a Reconciliação Bancária Avançada. |
| **Áreas afetadas do produto**         | Contas a Receber                                                                       |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.                            |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integração com Isabel sincronizada (CIS) para Bélgica

Isabel é a estrutura do banco eletrônico na Europa e um padrão de fatos na Bélgica.

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Integração com clientes Isabel foi interrompida.   |
| **Substituída por outro recurso?**   | Não. Os formatos de pagamento usados não são substituídos pelo formato de pagamento de transferência de crédito ISO20022 para a Bélgica. |
| **Áreas afetadas do produto**         | Contas a Pagar     |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.    |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Alterações no plano de contas e de regras contábeis para a Espanha

Este recurso é usado para as alterações no plano de contas e de regras contábeis na Espanha. Contas é mapeado para ajudar a tornar o plano de contas antigo no novo plano de contas, e compara o ano fiscal anterior com o novo ano fiscal, mesmo que foram lançados em números de contas diferentes.

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Uso restrito                                                  |
| **Substituída por outro recurso?**   | Não                                                             |
| **Áreas afetadas do produto**         | Contabilidade                                                 |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Formato de pagamento de fornecedor Fornittori de Pagamento

Formato de pagamento de legado italiano para transferências de crédito.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                          |
| **Substituída por outro recurso?**   | Sim, formato de pagamento de transferência de crédito ISO20022 para Itália         |
| **Áreas afetadas do produto**         | Contas a Pagar                                               |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="payment-export-formats-for-estonia"></a>Formatos de exportação de pagamento para Estônia

Os formatos de Telehansa e de Teleservice são usados para exportação de pagamento bancário.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                        |
| **Substituída por outro recurso?**   | Sim, formato de pagamento de transferência de crédito ISO20022 para Estônia       |
| **Áreas afetadas do produto**         | Contas a Pagar                                               |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="payment-file-archive-for-norway"></a>Arquivo morto de arquivo de pagamento para Noruega

Quando os arquivos de pagamento são geradas, o arquivo morto de arquivo arquiva automaticamente todos os arquivos criados, apesar arquivos que foram anteriormente redigidos ou lidos.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por outro recurso                                        |
| **Substituída por outro recurso?**   | Sim, trabalhos arquivados de relatórios eletrônicos                            |
| **Áreas afetadas do produto**         | Contas a pagar, contas a receber, administração da organização |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.     |

### <a name="payment-import-formats-for-estonia"></a>Formatos de importação de pagamento para Estônia

Os formatos Telehansa e TeleTeenus são usados para importação de pagamento bancário.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                                                    |
| **Substituída por outro recurso?**   | Sim, a importação de notificação do banco ISO20022 Camt.054. |
| **Áreas afetadas do produto**         | Contas a Receber                                                                        |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.                             |

### <a name="payroll-information-in-human-resources"></a>Informações da Folha de pagamento em Recursos Humanos

Informações da Folha de Pagamento em Recursos Humanos

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Essa funcionalidade foi substituída pelas páginas de folha de pagamento e Recursos humanos central.  |
| **Substituída por outro recurso?**   | **Benefícios**, **Ganhos** e outras páginas relacionadas que estavam anteriormente na Folha de Pagamento dos EUA agora fazem parte da configuração de Recursos humanos central para ajudar a suportar o processamento da folha de pagamento externa. Essa funcionalidade é acessada usando a chave de configuração **Recursos Humanos 1** \> **Folha de Pagamento**. |
| **Áreas afetadas do produto**         | Recursos Humanos, Folha de Pagamento   |
| **Status**                         | Removido a partir do Dynamics 365 for Operations versão 1611.    |

### <a name="performance-management-goal-workflow"></a>Fluxo de trabalho de meta de gerenciamento de desempenho

Gerenciamento de desempenho incluir o gerenciamento e a integração de meta com previsões resultados.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Gerenciamento de desempenho é remodelado, e o número de páginas da meta foi reduzido para simplificar o processo.                 |
| **Substituída por outro recurso?**   | Não. Metas são visíveis a gerentes através do portal de autoatendimento para gerente e podem ser alteradas e exibidas pelo gerente. |
| **Áreas afetadas do produto**         | Gerenciamento de capital humano       |
| **Status**                         | Removido a partir do Dynamics 365 for Operations versão 1611.    |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Formatos de pagamento Postgirot e Utland Postgirot para Suécia

Formatos de pagamento Postgirot e Utland Postgirot para Suécia.

|&nbsp;   |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                        |
| **Substituída por outro recurso?**   | Sim, formato de pagamento de transferência de crédito ISO20022 para Suécia        |
| **Áreas afetadas do produto**         | Contas a Pagar                                               |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="radio-frequency-identifier"></a>Identificador de radiofrequência

RFID (identificação de radiofrequência) é uma tecnologia de coleta de dados que usa etiquetas eletrônicas para armazenar dados de identificação e um leitor fora da linha de visão para capturar os dados de identificação.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Baixa utilização do cliente um conjunto de recursos limitado.   |
| **Substituída por outro recurso?**   | Não                                              |
| **Áreas afetadas do produto**         | Gerenciamento de estoque                            |
| **Status**                         | Removido a partir do Dynamics 365 for Operations 1611. |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Relatório da numeração de notas fiscais de estado para Letônia

A legislação de Letão fornece regras específicas sobre como as notas fiscais de vendas devem ser numeradas. A funcionalidade permite atribuir números das faturas de vendas específicos, com base no usuário ou no grupo de usuários. Você pode salvar e gerar um relatório ou um arquivo XML. Você também pode imprimir um relatório sobre os números de nota fiscal que são usadas.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A numeração do estado não deve ser mantida. Sobre o relatório de fatura números usados não é mais necessário. |
| **Substituída por outro recurso?**   | Não       |
| **Áreas afetadas do produto**         | Contas a Receber    |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.  |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Configurar nomes e gerente de contador geral de uma empresa para Lituânia

Nomes e gerente de contador geral de uma empresa podem ser especificados nas informações da empresa e ser usadas em impressões locais diferentes.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Substituído por outro recurso                                     |
| **Substituída por outro recurso?**   | Sim, o de instalação dos responsáveis pode ser usado para a mesma finalidade.   |
| **Áreas afetadas do produto**         | Contas a pagar, Contas a receber, Gerenciamento de caixa e bancos |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.  |

### <a name="shipping-carrier-interface"></a>Interface de transportadora

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Funcionalidade duplicada   |
| **Substituída por outro recurso?**   | Substituir parcialmente pelo Gerenciamento de transporte |
| **Áreas afetadas do produto**         | Vendas e marketing, Gerenciamento de estoque  |
| **Status**                         | Removido a partir do Dynamics 365 for Operations versão 1611.  |

### <a name="telepay-payment-formats-for-norway"></a>Formatos de pagamento para Telepay Noruega

Os formatos de pagamento Telepay incluem exportação de pagamento de fornecedor (transferência de crédito) e a coleção de pagamento de cliente (débito direto.)

|&nbsp;   |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                                                        |
| **Substituída por outro recurso?**   | Sim, formato de pagamento de transferência de crédito ISO20022 e formato de pagamento de cliente AvtaleGiro para a Noruega, bem como importação de arquivos de retorno de notificação do banco pain.002 e camt.054a. |
| **Áreas afetadas do produto**         | Contas a pagar, Contas a receber                                                          |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.                                 |

### <a name="vendor-payment-export-formats-for-finland"></a>Formatos de exportação de pagamento do fornecedor para Finlândia

Dois formatos de exportação de pagamentos estão disponíveis para a Finlândia. O LM02 (FI) é usado para pagamentos locais, e o LUM2 (FI) é usado para pagamentos estrangeiros.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os formatos de pagamento não são mais usados.                        |
| **Substituída por outro recurso?**   | Sim, formato de pagamento de transferência de crédito ISO20022 para Finlândia       |
| **Áreas afetadas do produto**         | Contas a Pagar                                               |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="warehouse-management-ii"></a>Gerenciamento de Depósito II

|  &nbsp; |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A solução Gerenciamento de depósito II (WMS II) que estava disponível no módulo **Gerenciamento de estoque** duplica a funcionalidade que está no módulo **Gerenciamento de depósito** liberada no Dynamics AX 2012 R3.                                                                         |
| **Substituída por outro recurso?**   | O módulo **Gerenciamento de depósito** liberado no AX 2012 R3, no Dynamics AX 2012 R3 CU8 e no Dynamics AX 2012 R3 CU9 substitui os recursos de Gerenciamento de depósito II. O novo módulo tem mais recursos avançados e processos de gerenciamento de depósito mais flexíveis do que os no Gerenciamento de depósito II. |
| **Áreas afetadas do produto**         | Gerenciamento de estoque, Vendas e marketing, Compras   |
| **Status**                         | Removido a partir do Dynamics 365 for Operations versão 1611.    |

### <a name="worker-reminders-in-human-resources"></a>Lembretes do trabalhador em Recursos Humanos

Informações da Folha de Pagamento em Recursos Humanos

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Baixa utilização                                                           |
| **Substituída por outro recurso?**   | Não                                                                  |
| **Áreas afetadas do produto**         | Recursos Humanos                                                     |
| **Status**                         | Removido a partir do Dynamics 365 for Operations versão 1611 |

### <a name="workflow-for-creating-goals"></a>Fluxo de trabalho para criar metas

Um fluxo de trabalho para gerenciar a criação das metas de funcionários for um de vários fluxos de trabalho que estavam disponíveis para ajudar a coordenada o processo de gerenciamento de desempenho.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O gerenciamento de desempenho foi totalmente remodelado no Finance and Operations.     |
| **Substituída por outro recurso?**   | O recurso remodelado de gerenciamento de desempenho é mais controle sobre o conteúdo de meta, medições usados para controlar o progresso e, de anexos de documentos de suporte. As metas podem ser armazenadas como modelos e então ser reutilizados. Esse recurso pode ajudá-lo meta adicionais para os funcionários configurados mais rapidamente. |
| **Áreas afetadas do produto**         | Gerenciamento de capital humano                 |
| **Status**                         | Removido a partir do Dynamics 365 for Operations versão 1611. |

## <a name="dynamics-ax-70"></a>Dynamics AX 7.0 


### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Capacidade de cancelar alterações para uma fatura do fornecedor

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Aprimoramento de desempenho        |
| **Substituída por outro recurso?**   | Não                             |
| **Áreas afetadas do produto**         | Contas a Pagar               |
| **Status**                         | Removido a partir do Dynamics AX 7.0. |

### <a name="aif-axd-and-axbc-integrations"></a>Integrações de AIF, AxD e AxBC

Na Estrutura de Integração de Aplicativos (AIF), os dados podem ser trocados com sistemas externos através da lógica comercial que é exposta como serviços. O Dynamics AX inclui serviços que são baseados em documentos e no.NET Business Connector (AxBC.) Um documento é criado usando XML. O XML inclui informações de cabeçalho adicionadas para criar uma *mensagem* que pode ser transferida para o/do Dynamics AX. Os exemplos de documentos incluem ordens de venda e ordens de compra. No entanto, quase todas as entidades, como um cliente, podem ser representadas por um documento. Os serviços baseados em documentos usam as classes **Axd \<Document\>**.

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A arquitetura de AIF e de AxDs não pode ser dimensionada a um serviço de nuvem. Houve problemas de desempenho em relação à importação em massa.                                        |
| **Substituída por outro recurso?**   | Este recurso é substituído pela estrutura de Importação/Exportação de Dados que oferece suporte a importação/exportação em massa recorrente. Para AxBC, recomendamos usar as tabelas reais. |
| **Áreas afetadas do produto**         | AxDs, AxBCs e AIF   |
| **Status**                         | Removido a partir do Dynamics AX 7.0.   |

### <a name="billing-code-rate-scripts"></a>Scripts de taxa de código de cobrança

Os scripts de cobrança eram usados para calcular taxas de cobrança para códigos de cobrança. Esses scripts exigiam desenvolvimento personalizado em C Sharp ou na linguagem de programação do Visual Basic. Na versão atual do Dynamics AX, os **scripts de taxa do código de cobrança** não têm suporte.

| &nbsp;  |&nbsp;  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O suporte aos scripts personalizados em C Sharp ou os scripts do Visual Basic não foi adicionado ao Dynamics AX 7.0. |
| **Substituída por outro recurso?**   | Não                                                                                      |
| **Áreas afetadas do produto**         | Setor público, Contas a receber                                    |
| **Status**                         | Removido a partir do Dynamics AX 7.0.                                                          |

### <a name="boms-without-bom-versions"></a>As versões sem BOM

Quando a configuração principal de **Versões da BOM** estiver desabilitada, as versões da lista de materiais (BOM) ficarão ocultas em todos os formulários e o sistema forçará um relacionamento 1:1 entre os produtos liberados e as BOMs. Na versão atual do Dynamics AX, a chave de configuração **Versões da BOM** não pode ser desativada.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O uso de uma chave de configuração para controlar as versões da BOM não é escalonado em um ambiente de nuvem. |
| **Substituída por outro recurso?**   | Não                                                                                      |
| **Áreas afetadas do produto**         | Gerenciamento de informações sobre o produto, Gerenciamento de estoque                                    |
| **Status**                         | Removido a partir do Dynamics AX 7.0.                                                          |

### <a name="brazilian-bordero"></a>Bordero brasileiro

Método de pagamento específico para brasileiras empresas

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Suporte para o método do Bordero de pagamento foi interrompido da localização brasileira |
| **Substituída por outro recurso?**   | Não   |
| **Áreas afetadas do produto**         | Contas a Pagar   |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="brazilian-sintegra-statement"></a>Demonstrativo de Sintegra brasileiro

Demonstrativo de imposto federal para impostos ICMS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Este demonstrativo não é mais aplicável em alguns estados brasileiros. |
| **Substituída por outro recurso?**   | Não. Os usuários podem usar a ferramenta de relatório eletrônica genérica para configurar o demonstrativo, se necessário, em situações específicas. |
| **Áreas afetadas do produto**         | Livros fiscais    |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.   |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Modo de contingência SCAN brasileiro para NF-e

É possível usar o modo de contingência SCAN para gerar, exportar, e importar o status de uma Nota Fiscal eletrônica de (NF-e) quando o ambiente de origem da Secretaria da Fazenda (SEFAZ) não está disponível.

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Este método de contingência não é mais aplicável em todos os estados brasileiros |
| **Substituída por outro recurso?**   | Não                                                                          |
| **Áreas afetadas do produto**         | Contas a Receber                                                         |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.              |

### <a name="business-analyzer"></a>Business Analyzer

Este aplicativo móvel permite que os usuários revisem as principais métricas de negócios.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Esta funcionalidade foi substituída por outro recurso.   |
| **Substituída por outro recurso?**   | O pacote de conteúdo Monitorar desempenho financeiro para Microsoft Power BI incluirá as principais métricas financeiras que estavam disponíveis anteriormente no Business Analyzer. |
| **Áreas afetadas do produto**         | Contabilidade      |
| **Status**                         | Preterido: O uso do Business Analyzer foi preterido.    |

### <a name="business-statistics"></a>Estatísticas comerciais

A configuração de consultas de estatísticas comerciais que podem ajudar a analisar o desempenho da organização

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Abordagem herdada de business Intelligence (BI), baixa utilização do cliente e um conjunto de recursos limitado |
| **Substituída por outro recurso?**   | Novas soluções de BI da versão atual do Dynamics AX                                      |
| **Áreas afetadas do produto**         | Compras, Contas a pagar, Vendas e marketing e Contas a receber         |
| **Status**                         | Removido a partir do Dynamics AX 7.0.                                                               |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Alterar a função de data do documento no Diário de aprovações de fatura

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Baixa utilização                                                               |
| **Substituída por outro recurso?**   | Sim. A data do documento na transação de fornecedor lançada pode ser alterada. |
| **Áreas afetadas do produto**         | Contas a Pagar                                                        |
| **Status**                         | Removido a partir do Dynamics AX 7.0.                                          |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Formato de pagamento ClieOp03 para os Países Baixos

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O formato não é mais aplicável nos Países Baixos porque foi substituído pela funcionalidade de SEPA. |
| **Substituída por outro recurso?**   | Exportação de pagamentos no SEPA  |
| **Áreas afetadas do produto**         | Todos os módulos     |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.   |

### <a name="compliance-center"></a>Centro de conformidade

O Centro de Conformidade era um site do Portal Empresarial para gerenciar os requisitos de documentação para iniciativas de conformidade relacionadas à lei Sarbanes-Oxley.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Escassez de uso do cliente. O Microsoft SharePoint inclui o mesmo recurso que estava disponível no Centro de Conformidade. |
| **Substituída por outro recurso?**   | Não   |
| **Áreas afetadas do produto**         | Conformidade e controles internos  |
| **Status**                         | Removido a partir do Dynamics AX 7.0.    |

### <a name="connector-for-microsoft-dynamics"></a>Connector para Microsoft Dynamics

Esta ferramenta era usada para integrar dados de chave do Microsoft Dynamics CRM com aplicativos do Dynamics ERP.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Esta funcionalidade foi substituída por outro recurso. |
| **Substituída por outro recurso?**   | Dataverse                                      |
| **Áreas afetadas do produto**         | Conector do Dynamics                         |
| **Status**                         | Removido a partir do Dynamics AX 7.0.                           |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Unidade de contêiner e multidimensão em estoque

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Funcionalidade duplicada |
| **Substituída por outro recurso?**   | Sim. Desde o AX 2012, essa funcionalidade foi substituída pelo conjunto de recurso de ordens de lote consolidadas. Este conjunto de recurso inclui a exibição disponível consolidada. |
| **Áreas afetadas do produto**         | Gerenciamento de informações sobre o produto, Controle de produção, Gerenciamento de estoque, Vendas e marketing  |
| **Status**                         | Removido a partir do Dynamics AX 7.0. |

### <a name="cue-group-metadata"></a>Metadados do grupo de indicação

|  &nbsp; | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os grupos de indicação eram usados para exibir uma ou mais Indicações na área do Quadro de Fatos. Houve uma retirada limitada, e também houve preocupações com desempenho, porque uma alteração de registro em um formulário pai causou uma consulta por Indicação no grupo da Indicação. |
| **Substituída por outro recurso?**   | Não      |
| **Áreas afetadas do produto**         | Todos os módulos    |
| **Status**                         | Removido a partir do Dynamics AX 7.0.  |

### <a name="cue-metadata"></a>Metadados de indicação

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os metadados de indicação foram limitados para contar ou somar informações.    |
| **Substituída por outro recurso?**   | Os metadados lado a lado foram introduzidos para oferecer mais flexibilidade para modelagem. Por exemplo, é possível modelar contas atuais, navegação e indicadores de desempenho chave (KPIs). Os metadados lado a lado de contagem são substituições diretas dos metadados da indicação. |
| **Áreas afetadas do produto**         | Todos os módulos           |
| **Status**                         | Removido a partir do Dynamics AX 7.0      |

### <a name="danish-check-format"></a>Formato de cheque dinamarquês

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Suporte ao layout do formato de cheque dinamarquês foi interrompido e o relatório foi removido da localização de DK. |
| **Substituída por outro recurso?**   | Não    |
| **Áreas afetadas do produto**         | Todos os módulos    |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.  |

### <a name="data-partitions"></a>Partições de dados

As partições de dados fornecem uma divisão lógica de dados no banco de dados do Dynamics AX.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | As partições de dados foram introduzidas no Dynamics AX 2012 R2 para permitir o isolamento de dados. Em um cenário comum, uma empresa tem subsidiárias e os dados de uma subsidiária não deverão ser visíveis a outra subsidiária, embora ambas as subsidiárias são gerenciadas pelo mesmo departamento de TI. No entanto, gerenciamento de sobrecarga em todo o programa e scripts extras eram necessários para criar novas partições e preenchê-las com dados e para fazer backup de dados de partição. Na nuvem, onde temos acesso a serviços de banco de dados de plataforma como serviço (PaaS) (Microsoft Azure SQL Database), é muito mais eficiente usar um banco de dados como o contêiner de isolamento do que fazer isolamento no programa. Independentemente de o particionamento de dados ser necessário para subsidiárias, para vários locatários ou apenas para escala, acreditamos que as situações podem ser tratadas melhor por várias instâncias do Finance and Operations. |
| **Substituída por outro recurso?**   | Os clientes que usam partições de dados deverão usar várias instâncias do Finance and Operations se a separação no nível de banco de dados for um problema crítico.    |
| **Áreas afetadas do produto**         | Todos os módulos  |
| **Status**                         | Removido a partir do Dynamics AX 7.0.  |


### <a name="database-and-file-share-storage-for-attachments"></a>Armazenamento de banco de dados e de compartilhamento de arquivos para anexos

O Dynamics AX 2012 permitia o armazenamento de anexos no banco de dados e em compartilhamentos de arquivos. Não há mais suporte para essas opções.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O armazenamento de compartilhamento de arquivos não tem mais suporte porque os ambientes hospedados na nuvem não podem se comunicar com os compartilhamentos de arquivos locais. O armazenamento de banco de dados foi substituído pelo Armazenamento de Blobs do Azure. O armazenamento de Blob do Azure é equivalente ao armazenamento no banco de dados, já que os documentos só podem ser acessados por meio de formulários de cliente do Finance and Operations. Isso oferece o benefício adicional de fornecer armazenamento que não prejudica o desempenho do banco de dados. O armazenamento de blobs é o mecanismo padrão de armazenamento para o Gerenciamento de Documentos e funciona imediatamente. |
| **Substituída por outro recurso?**   | O armazenamento de banco de dados foi substituído pelo Armazenamento de Blobs do Azure.   |
| **Áreas afetadas do produto**         | Todos os módulos  |
| **Status**                         | Removido a partir do Dynamics AX 7.0.   |

### <a name="delimitation"></a>Delimitação

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Nenhum uso da funcionalidade foi encontrado. |
| **Substituída por outro recurso?**   | Não                                     |
| **Áreas afetadas do produto**         | Horário e presença                    |
| **Status**                         | Removido a partir do Dynamics AX 7.0.         |

### <a name="desktop-client"></a>Cliente da área de trabalho

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A experiência do cliente do Dynamics AX foi remodelada para melhorar a usabilidade entre várias plataformas e dispositivos.                      |
| **Substituída por outro recurso?**   | O novo cliente Web baseia-se nos metadados do Formulário da área de trabalho e no modelo de programação que foi modificado para fornecer uma plataforma avançada da Web. |
| **Áreas afetadas do produto**         | Todos os módulos  |
| **Status**                         | Removido a partir do Dynamics AX 7.0.   |

### <a name="direct-database-connection"></a>Conexão direta do banco de dados

No Dynamics AX 2012 R3, o Retail Modern POS podia se conectar diretamente ao BD do canal de modo semelhante ao Enterprise POS. Isso ocorria além do método padrão de comunicação do Retail Modern POS que usava o Retail Server.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A conectividade direta do base de dados exigiu protocolos de segurança inferior e foi usada principalmente para atingir os níveis mais altos de desempenho. Devido aos aprimoramentos de desempenho e segurança que ocorreram no Finance and Operations, essa funcionalidade agora causa mais problemas do que resolve. |
| **Substituída por outro recurso?**   | Não. Apenas a comunicação padrão do Retail Server é suportada agora.  |
| **Áreas afetadas do produto**         | BD de canal/Retail Modern POS   |
| **Status**                         | Removido a partir do Dynamics AX 7.0.  |

### <a name="dutch-swift-mt940"></a>SWIFT MT940 holandês

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A funcionalidade genérica agora é usada em vez da funcionalidade encontrada.                    |
| **Substituída por outro recurso?**   | Sim, essa funcionalidade é substituída pela funcionalidade de reconciliação bancária Avançada. |
| **Áreas afetadas do produto**         | Todos os módulos                                                                              |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.                           |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL para Alemanha)

Essa funcionalidade forneceu a saída XBRL (eXtensible Business Reporting Language) especificamente para a taxonomia eBilanz da Alemanha.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Escassez de uso do cliente  |
| **Substituída por outro recurso?**   | Esse recurso não foi substituído por outro recurso, mas vários pacotes XBRL especializados que fornecem a funcionalidade XBRL avançada estão disponíveis para o mercado da Alemanha. |
| **Áreas afetadas do produto**         | Management Reporter      |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.  |

### <a name="enterprise-portal-client"></a>Cliente do portal empresarial

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Uma única plataforma de cliente foi fornecida.  |
| **Substituída por outro recurso?**   | O novo cliente Web baseia-se nos metadados do formulário da área de trabalho e no modelo de programação que foi modificado para fornecer uma plataforma avançada da Web. |
| **Áreas afetadas do produto**         | Todos os módulos  |
| **Status**                         | Removido a partir do Dynamics AX 7.0.   |

### <a name="environmental-sustainability"></a>Sustentabilidade ambiental

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Baixa utilização do cliente um conjunto de recursos limitado  |
| **Substituída por outro recurso?**   | Não              |
| **Áreas afetadas do produto**         | Conformidade e controles internos, Contas a pagar  |
| **Status**                         | Removido a partir do Dynamics AX 7.0. |

### <a name="form-activex-and-managed-host-controls"></a>Formulário ActiveX e Controles gerenciados por host

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O ActiveX e os controles Gerenciados por host são baseados no cliente obsoleto da área de trabalho. |
| **Substituída por outro recurso?**   | A estrutura de controle extensível oferece suporte à criação de novos controles baseados em HTML, CSS e JavaScript e é um controle de primeira classe no ambiente de ferramentas do Microsoft Visual Studio. |
| **Áreas afetadas do produto**         | Todos os módulos     |
| **Status**                         | Removido a partir do Dynamics AX 7.0.       |

### <a name="generate-prenotes-by-using-a-batch"></a>Gerar pré-registros usando um lote

A geração de pré-registros não poderá ser feita usando um lote, mas poderá ser feita por um usuário.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Não existe formulário para persistir e exibir o arquivo de pré-registro resultante quando ele for gerado usando um lote. |
| **Substituída por outro recurso?**   | Os pré-registros ainda podem ser gerados e o usuário tem controle sobre o local onde o arquivo é salvo.   |
| **Áreas afetadas do produto**         | Contas a pagar, Contas a receber, Gerenciamento de caixa e bancos  |
| **Status**                         | Removido a partir do AX 7.0.    |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Exportação de pagamento de DTAUS e importação do demonstrativo de conta da Alemanha (totais e transações)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O formato não é mais aplicável na Alemanha porque foi substituído pela funcionalidade de Área Única de Pagamentos em Euros (SEPA).                    |
| **Substituída por outro recurso?**   | Sim, esta funcionalidade foi substituída pela exportação de pagamento de SEPA e funcionalidade avançada de reconciliação bancária para importar demonstrativos de conta. |
| **Áreas afetadas do produto**         | Todos os módulos  |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="german-dtazv-payment-format-in-domestic-currency"></a>Formato de pagamento alemão DTAZV em moeda local

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O formato não é mais aplicável na Alemanha porque foi substituído pela funcionalidade de SEPA. |
| **Substituída por outro recurso?**   | Exportação de pagamentos no SEPA    |
| **Áreas afetadas do produto**         | Contas a Pagar   |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.    |

### <a name="german-mt940-import"></a>Importação MT940 alemão

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A funcionalidade genérica agora é usada em vez da funcionalidade encontrada.                    |
| **Substituída por outro recurso?**   | Sim, essa funcionalidade é substituída pela funcionalidade de reconciliação bancária Avançada. |
| **Áreas afetadas do produto**         | Todos os módulos                                                                              |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.                           |

### <a name="german-xml-eu-sales-list"></a>Lista de vendas alemã da UE - formato XML

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O formato XML para o relatório de lista de vendas da União Europeia não é mais suportado. Somente o formato de arquivo de texto ELMA5 pode ser usado para enviar o relatório de lista de vendas da UE para impostos Office alemães. |
| **Substituída por outro recurso?**   | Não         |
| **Áreas afetadas do produto**         | Imposto        |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.   |

### <a name="gl-ssrs-reports"></a>Relatórios GL SSRS

Os relatórios que incluem os seguintes itens de menu foram removidos: **Balancete de resumo**, **Balancete detalhado**, **Plano de contas**, **Trilha de auditoria**, **Saldos** e **Lista de saldos**.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os relatórios financeiros do Microsoft SQL Server Reporting Services (SSRS) foram substituídos por recursos e relatórios padrão do Management Reporter. |
| **Substituída por outro recurso?**   | Management Reporter (chamado **Relatório financeiro** na versão atual do Dynamics AX)    |
| **Áreas afetadas do produto**         | Contabilidade   |
| **Status**                         | Removido a partir do Dynamics AX 7.0.   |

### <a name="infopart-and-formpart-metadata"></a>Os metadados de InfoPart e de FormPart

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os metadados de InfoPart e de FormPart habilitaram a criação de Quadros de Fatos para dois clientes diferentes. |
| **Substituída por outro recurso?**   | Os metadados de InfoPart, que eram uma definição simplificada do formulário, foram convertidos em um Formulário através da ferramenta de atualização. Os metadados de FormPart, que faziam referência a um Formulário, foram substituídos por uma referência mais direta criada pela ferramenta de atualização. |
| **Áreas afetadas do produto**         | Todos os módulos    |
| **Status**                         | Removido a partir do Dynamics AX 7.0.        |

### <a name="main-account-list-page"></a>Página de lista da conta principal

Uma lista de contas da entidade legal e informações relacionadas a saldo

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | As informações sobre saldo estão disponíveis na página de lista **Balancete** por conta e dimensão.  |
| **Substituída por outro recurso?**   | As **Contas principais** contêm a mesma lista de contas que a página de lista **Conta principal** continha. A exibição de grade nas **Contas principais** também mostra uma exibição menor, com grade. |
| **Áreas afetadas do produto**         | Contabilidade      |
| **Status**                         | Removido a partir do Dynamics AX 7.0.    |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Relatório de fluxo de caixa bancário da Malásia e de Cingapura

Este recurso permite que o usuário imprima um relatório de fluxo de caixa que mostra as transações e os detalhes das entradas e saídas de caixa para um intervalo de datas específico para as contas bancárias selecionadas.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A mesma informação pode ser obtida da transação bancária de Consulta. |
| **Substituída por outro recurso?**   | A transação bancária de Consulta                                            |
| **Áreas afetadas do produto**         | Gerenciamento de caixa e bancos                                                |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso.          |

### <a name="mexican-cfd-electronic-invoice"></a>Fatura eletrônica CFD mexicana

Este recurso habilitou a geração da fatura eletrônica mexicana usando o método Comprobante Fiscal Digital (CFD), no qual a empresa assina a fatura, solicitando a autorização relacionada do governo. Este recurso também fornece um relatório mensal que inclui todas as faturas eletrônicas que foram emitidas no período.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O método não é mais aplicável. A geração de faturas eletrônicas usando o método CFD tornou-se obsoleta pelas autoridades fiscais e foi substituída pelo método Comprobante Fiscal Digital através de Internet (CFDI), no qual a assinatura é delegada ao provedor terceirizado (PAC). O relatório mensal foi removido, e uma opção de consulta permite que os usuários consultem transações históricas. |
| **Substituída por outro recurso?**   | Não    |
| **Áreas afetadas do produto**         | Contas a receber, Projeto   |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="mexico-realized-and-unrealized-vat"></a>IVA realizado e não realizado do México

O Dynamics AX 2012 gerenciava o IVA (imposto sobre valor agregado) não realizado usando a funcionalidade específica para o México de imposto não realizado.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Funcionalidade duplicada  |
| **Substituída por outro recurso?**   | Sim, essa funcionalidade foi substituída pela funcionalidade de imposto condicional padrão que é fornecida pelo Principal. |
| **Áreas afetadas do produto**         | Imposto   |
| **Status**                         | Preterido: Uma data de remoção não foi definida para esse recurso. |

### <a name="microsoft-outlook-integration"></a>Integração com o Microsoft Outlook


| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Esta funcionalidade foi substituída pela integração do Microsoft Exchange Server. |
| **Substituída por outro recurso?**   | Sim                                                                            |
| **Áreas afetadas do produto**         | Sales and Marketing                                                            |
| **Status**                         | Removido a partir do Dynamics AX 7.0.                                                 |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Bloqueio privado de diários de gerenciamento de estoque e depósito

Os diários de estoque e depósito não oferecem suporte à capacidade de marcar um diário como particular para um usuário selecionado. Somente o processo de bloquear diários como privados para grupos de usuários e bloquear durante a edição é suportado.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Nenhum uso da funcionalidade foi encontrado. |
| **Substituída por outro recurso?**   | Não                                     |
| **Áreas afetadas do produto**         | Gerenciamento de estoque                   |
| **Status**                         | Removido a partir do Dynamics AX 7.0.         |

### <a name="product-builder"></a>Configurador de produtos

O configurador de produtos foi usado para configurar itens dinamicamente a partir de uma ordem de venda, ordem de compra, ordem de produção, cotação de vendas, cotação de projeto ou requisito do item. Com base no modelo de produto que tinha as variáveis de modelagem, o usuário pode selecionar valores para atender às necessidades do cliente e obter uma variante de produtos que tinha uma BOM e um roteiro.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O configurador de produtos expunha o código X++ para os usuários finais e não tem suporte na versão atual do Dynamics AX. Foi removido para evitar esforços de manutenção duplicados em códigos base de sobreposição, dimensionáveis.  |
| **Substituída por outro recurso?**   | Sim. A configuração baseada em restrições foi introduzida no Dynamics AX 2012, já tendo sido anunciada a substituição do configurador de produtos em versões futuras. A tecnologia de configuração baseada em restrições foi selecionada nos produtos mestres para ativar a configuração. Para saber mais, consulte [Visão geral de configuração do produto](../../../supply-chain/pim/build-product-configuration-model.md). |
| **Áreas afetadas do produto**         | Gerenciamento de informações do produto, Vendas e marketing  |
| **Status**                         | Removido a partir do Dynamics AX 7.0.      |

### <a name="production-floor-app"></a>Aplicativo de chão de produção
Este é o aplicativo para dispositivos de tablet executando Windows 8.1 RT e Windows 8.1 Pro.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Com a mudança para um cliente baseado na Web, é possível entregar funcionalidade semelhante por meio do cliente nativo do Dynamics AX 7.0. O dispositivo Ficha de Trabalho fornece interface de usuário de chão de produção que é otimizado para fatores de formulário de toque e tablet. |
| **Substituída por outro recurso?**   | Sim. O dispositivo de ficha de trabalho, que é um componente nativo do Dynamics AX 7.0.                                                                           |
| **Áreas afetadas do produto**         | Controle de produção                                                |
| **Status**                         | Substituir: Uma data de remoção de armazenamento da Microsoft não foi definida para esse recurso ainda.                                                |


### <a name="rename-product-dimension"></a>Renomear dimensão do produto

Este recurso permite que você altere o nome de uma das três dimensões padrão do produto (tamanho, cor ou estilo) para um nome que melhor se ajuste aos requisitos de negócios. Renomear inclui todas as etiquetas nas quais o nome da dimensão do produto foi usado.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A versão atual do Dynamics AX não oferece suporte a alterações no rótulo em tempo de execução. |
| **Substituída por outro recurso?**   | Não                                                                            |
| **Áreas afetadas do produto**         | Gerenciamento de informações do produto                                                |
| **Status**                         | Removido a partir do Dynamics AX 7.0.                                                |

### <a name="retail-server-connectivity-using-http"></a>Conectividade do Retail Server usando HTTP

No Dynamics AX 2012 R3, o Retail Server podia funcionar usando comunicação HTTP (não segura). Isso ocorre além da comunicação padrão que usa HTTPS.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Devido aos requisitos de segurança, apenas a comunicação protegida usando o TLS 1.2 (ou superior, conforme disponível) é suportada agora. O instalador de autoatendimento configurará automaticamente o computador para esta comunicação. |
| **Substituída por outro recurso?**   | Não. Apenas a comunicação HTTPS padrão é suportada agora. |
| **Áreas afetadas do produto**         | Retail Server  |
| **Status**                         | Removido a partir do Dynamics AX 7.0. |

### <a name="role-center-pages"></a>Páginas do Centro de Funções

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | As páginas do Centro de Funções foram compiladas na plataforma obsoleta do Portal Empresarial, que foi substituída por uma nova plataforma de clientes Web na versão atual do Dynamics AX. |
| **Substituída por outro recurso?**   | O novo padrão do formulário Espaço de Trabalho oferece aos usuários um design centralizado do processo que fornece acesso fácil às tarefas normalmente usadas dentro desse processo.                       |
| **Áreas afetadas do produto**         | Todos os módulos    |
| **Status**                         | Removido a partir do Dynamics AX 7.0   |

### <a name="sales-tax-jurisdictions"></a>Jurisdições de impostos

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Baixa utilização do cliente um conjunto de recursos limitado |
| **Substituída por outro recurso?**   | Não                                           |
| **Áreas afetadas do produto**         | Impostos do EUA                                 |
| **Status**                         | Removido a partir do Dynamics AX 7.0.               |

### <a name="sites-services"></a>Sites Services

Os serviços de sites permitem criar os sites que estendem seus processos comerciais da Internet sem suporte de TI.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A infraestrutura do Microsoft Azure usada pelo Dynamics AX tem novos recursos que podem ser usados (por exemplo, sites do Azure). |
| **Substituída por outro recurso?**   | Não   |
| **Áreas afetadas do produto**         | Espaços de trabalho de colaboração, Recrutamento de RH, gerenciamento dos casos, solicitação de cotação, registro de fornecedor para oportunidades e campanhas.  |
| **Status**                         | Removido a partir do Dynamics AX 7.0.    |

### <a name="ssas-demand-forecasting-strategy"></a>Estratégia de previsão de demanda SSAS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O design de recurso não pode ser suportado na nova arquitetura de nuvem. |
| **Substituída por outro recurso?**   | Estratégia de previsão de demanda do Aprendizado de Máquina do Azure                           |
| **Áreas afetadas do produto**         | Planejamento Mestre                                                              |
| **Status**                         | Removido a partir do Dynamics AX 7.0.                                               |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Grupo de faturas de fornecedor excluindo detalhes de lançamento

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Baixa utilização. Essa funcionalidade foi substituída por diário de notas fiscais com a funcionalidade de fluxo de trabalho. |
| **Substituída por outro recurso?**   | Recursos do fluxo de trabalho do Diário de faturas.     |
| **Áreas afetadas do produto**         | Contas a Pagar |
| **Status**                         | Removido a partir do Dynamics AX 7.0.    |


### <a name="virtual-company-accounts"></a>Contas virtuais da empresa

Não há mais suporte para o recurso de empresas virtuais no Dynamics AX. O recurso virtual das empresas habilitou os usuários a configurar as tabelas a serem compartilhadas por um conjunto de empresas. Você pode encontrar uma descrição do recurso aqui: [Contas da empresa e contas virtuais da empresa](../../fin-ops/get-started/ax4-content-retired.md). O recurso funciona através do agrupamento de tabelas em coleções que são atribuídas a empresas virtuais, que são grupos de empresas "reais" existentes. As consultas são criadas de forma que todas as empresas na empresa virtual possam acessar os dados nas tabelas das cobranças de tabelas associadas.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | - Empresas virtuais devem ser configuradas antes que os dados sejam armazenados nas tabelas. Adaptar empresas virtuais em uma implementação existente é muito difícil.<br><br>- Como há um excesso de normalização de dados na versão atual do Dynamics AX, tem sido difícil saber o que adicionar aos conjuntos de tabela. Por exemplo, é difícil saber quais tabelas compartilhar. Todas as tabelas referenciadas de tabelas que estão em uma empresa virtual também precisam ser adicionadas. Normalização de tabela significa que até a simples difusão de dados mestres entre diversas tabelas precisa fazer parte da empresa virtual. Qualquer erro que é feito aqui gerará saídas funcionais.<br><br>- Quando uma tabela faz parte de uma empresa virtual, ela perde informações sobre a origem de dados, e apenas a empresa virtual é registrada.   |
| **Substituída por outro recurso?** | As tabelas globais podem ser usadas para criar tabelas acessíveis a todas as empresas. Atualmente, não há substituição. |   
| **Áreas afetadas do produto**       | Todos os módulos |   
| **Status**                       | Removido a partir do Dynamics AX 7.0.   |   

### <a name="windows-8-tablet-app"></a>Aplicativo para tablet com Windows 8

O aplicativo para tablet com Windows 8 fornece a funcionalidade da entrada e a aprovação de despesas.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O Finance and Operations é compatível com tablets. O aplicativo para tablet não é mais necessário.    |
| **Substituída por outro recurso?**   | Não.          |
| **Áreas afetadas do produto**         | Gerenciamento de despesas   |
| **Status**                         | Removido: esta funcionalidade só está disponível para o Dynamics AX 2012 R3. |

### <a name="workplanner"></a>Planejador de trabalho

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Baixa utilização |
| **Substituída por outro recurso?**   | Não, mas a página **Relação de perfil**, que é aberta na página **Grupos de perfil**, suporta o mesmo cenário empresarial que a página obsoleta **Planejador de trabalho**. |
| **Áreas afetadas do produto**         | Horário e presença     |
| **Status**                         | O código não foi removido. Entretanto, o formulário, JmgWorkPlanner, não foi migrado.    |

### <a name="x-financial-statements"></a>Demonstrativos financeiros X++

| &nbsp;  | &nbsp; |
|-------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| <strong>Motivo para a reprovação/remoção</strong> |                         Esta funcionalidade foi substituída por outro recurso.                         |
|  <strong>Substituída por outro recurso?</strong>  | Management Reporter (chamado <strong>Relatório financeiro</strong> na versão atual do Dynamics AX) |
|     <strong>Áreas afetadas do produto</strong>     |                                              Contabilidade                                              |
|             <strong>Status</strong>             |                                      Removido a partir do Dynamics AX 2012                                      |



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
