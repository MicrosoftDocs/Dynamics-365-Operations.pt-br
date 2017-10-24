---
title: Recursos preteridos
description: "Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção."
author: sericks007
manager: AnnBe
ms.date: 07/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Platform, UnifiedOperations
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 6
ms.translationtype: HT
ms.sourcegitcommit: c73eeaaf28df8db720431d4bcd317c9721baa99d
ms.openlocfilehash: 3ebe8f2869b93050d320456ff457c0b5692c5eae
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="deprecated-features"></a>Recursos preteridos

[!include[banner](../includes/banner.md)]

Este tópico descreve os recursos que foram removidos ou que têm a remoção planejada da versão atual do Microsoft Dynamics 365 for Finance and Operations, edição Enterprise.

## <a name="features-that-have-been-deprecated-in-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-with-platform-update-8"></a>Recursos que foram substituídos no Dynamics 365 for Finance and Operations, Enterprise Edition (julho 2017) com atualização 8 da plataforma

### <a name="warehouse-mobile-devices-portal"></a>Portal de dispositivos móveis do depósito

O portal de dispositivos móveis de depósito (WMDP) é um componente autônomo que foi criado para auto-implantação local. Este componente não é mais suportado no Microsoft Dynamics 365 for Finance and Operations, edição Enterprise. Um aplicativo nativo que melhora a experiência do usuário substituiu a funcionalidade do WMDP. 

|                                  |                                                 |
|----------------------------------|-------------------------------------------------|
| **Motivo para a depreciação**       | Funcionalidade duplicada.                        |
| **Substituída por outro recurso?** | Sim. Este recurso foi substituído pelo Finance and Operations - Warehousing. Para obter informações sobre a instalação e pré-requisitos, consulte [Instalar e configurar o Microsoft Dynamics 365 for Finance and Operations - Warehousing](../../supply-chain/warehousing/install-configure-warehousing-app.md). |
| **Módulos afetados**             | Gerenciamento de depósito, Gerenciamento de transporte |

### <a name="advanced-bank-reconciliation-matching-rule-for-manual-matching"></a>Regra avançada de correspondência de reconciliação bancária para correspondência manual

Uma regra de correspondência foi usada para selecionar e marcar um documento bancário quando os documentos foram correspondidos manualmente na planilha de reconciliação.

|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Uso restrito.                                                                         |
| **Substituída por outro recurso?** | Não. Os recursos de filtragem da coluna devem ser usados para localizar documentos para a reconciliação. |
| **Módulos afetados**             | Gerenciamento de caixa e bancos                                                               |

### <a name="windows-8-tablet-app"></a>Aplicativo para tablet com Windows 8

O aplicativo para tablet com Windows 8 fornece a funcionalidade da entrada e a aprovação de despesas.

|                                  |                                                                                          |
|----------------------------------|------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | O Finance and Operations é compatível com tablets. O aplicativo para tablet não é mais necessário. |
| **Substituída por outro recurso?** | Não.                                                                                      |
| **Módulos afetados**             | Gerenciamento de despesas                                                                       |


## <a name="features-that-have-been-deprecated-in-dynamics-365-for-operations-1611-with-platform-update-3"></a>Recursos que são substituídos no Dynamics 365 for Operations com 1611 com atualização 3 de plataforma

### <a name="aeb-payment-formats-for-spain"></a>Formatos de pagamento para a Espanha AEB

Os formatos de pagamento CSB (Consejo Superior Bancario) são usados para enviar arquivos de remessa para o banco para pagamentos de clientes e pagamentos de fornecedores. O conteúdo desses formatos é determinado pela Asociación Española de Banca. Abrange Cuaderno 19, 32, 58, 34.

|                              |                                                                          |
|------------------------------|--------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                                  |
| **Substituída por outro recurso?** | Sim, transferência de crédito de ISO20022 e os formatos de pagamento de débito direto para a Espanha |
| **Módulos afetados**             | Contas a pagar, Contas a receber                                    |

### <a name="bank-payments-transfer-for-lithuania"></a>Transferência de pagamentos bancários para Lituânia

Gerenciar e imprimir transferências de pagamento bancário usando o formato de exportação de transferência de pagamento (LT) para Lituânia. O mercado lituano iniciou o uso do LITAS, o sistema bancário eletrônico, em 2005.

|                              |                                                            |
|------------------------------|------------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                    |
| **Substituída por outro recurso?** | Sim, formato de pagamento de transferência de crédito ISO20022 para Lituânia |
| **Módulos afetados**             | Contas a Pagar                                           |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>Formatos de pagamento de BBS Direkte Remittering para Noruega

Os formatos de pagamento de BBS Direkte Remittering incluem exportação de cobrança de pagamentos de clientes (débito direto) e importação de devolução da mensagem.

|                              |                                                                                                                                                                |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                                                                                                                        |
| **Substituída por outro recurso?** | O formato de pagamento AvtaleGiro de clientes para Noruega pode ser usado para gerar mensagens de débito direto. Importação de devolução da mensagem será implementada em versões futuras. |
| **Módulos afetados**             | Contas a pagar, Contas a receber                                                                                                                          |

### <a name="chart-of-accounts-tool-for-spain"></a>Ferramenta de plano de contas para Espanha

A ferramenta é usada quando um gráfico de contas na Espanha requer mudanças importantes. Os usuários podem importar um novo plano de contas no Microsoft Excel ou o formato do texto, e também podem importar demonstrativos financeiros.

|                              |                |
|------------------------------|----------------|
| **Motivo para a depreciação**       | Uso restrito  |
| **Substituída por outro recurso?** | Não             |
| **Módulos afetados**             | Contabilidade |

### <a name="dom80-payment-format-for-belgium"></a>Formato de pagamento Dom80 para Bélgica

Formato de pagamento para legado da Bélgica do recolhimento de pagamentos (débito direto).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Motivo para a depreciação**      | Os formatos de pagamento não são mais usados.                  |
| **Substituída por outro recurso?** | Sim, formato de pagamento de débito direto ISO 20022 para Bélgica |
| **Módulos afetados**            | Contas a Receber                                    |

### <a name="dtaezag-payment-formats-for-switzerland"></a>Formatos de pagamento DTA/EZAG para a Suíça

Os formatos DTA/EZAG integram-se no sistema ESR, pois eles têm número de referência. Como números de referência não são obrigatórios, esses formatos podem ser usados para processar quaisquer pagamentos de fornecedor. Esses formatos é usada por empresas que têm uma conta bancária em um local diferente “Postfinance”.

|                              |                                                              |
|------------------------------|--------------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                      |
| **Substituída por outro recurso?** | Sim, formato de pagamento de transferência de crédito ISO20022 para Suíça |
| **Módulos afetados**             | Contas a Pagar                                             |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>Formato de pagamento de EDIFACT-DIRDEB para Áustria

Formato de pagamento para EDIFACT-DIRDEB do recolhimento de pagamentos (débito direto).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                  |
| **Substituída por outro recurso?** | Sim, formato de pagamento de débito direto ISO 20022 para Áustria |
| **Módulos afetados**             | Contas a Receber                                    |

### <a name="edivat-for-belgium"></a>EDIVAT para Bélgica

EDIVAT é um padrão belga obsoleto para a declaração eletrônica por e-mail seguro. Microsoft Dynamics AX 2012 retém a solução somente leitura para habilitar o acesso aos dados históricos.

|                              |                                      |
|------------------------------|--------------------------------------|
| **Motivo para a depreciação**       | A funcionalidade não é mais usada. |
| **Substituída por outro recurso?** | Não                                   |
| **Módulos afetados**             | Contabilidade                       |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>formato de importação de pagamento eGiro EDIFACT CREMUL para Noruega

eGiro é baseado no padrão internacional da UN EDIFACT CREMUL(mensagem de aviso de crédito múltiplo), usado para o lançamento automático de pagamentos de cliente. No Microsoft Dynamics AX, eGiro é implementado como um formato de pagamento de cliente.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                                                     |
| **Substituída por outro recurso?** | Não. O formato será substituído pela ISO 20022 formatos de importação do demonstrativo nas versões futuras. |
| **Módulos afetados**             | Contas a Receber                                                                       |

### <a name="external-inventory-for-poland"></a>Para o estoque externo Polônia

Evidência de mercadorias obtidas de um fornecedor para vendas sem compra. Os bens manuseados em estoque externo, não afetando o estoque padrão, podem ser vendidos e então adquiridos automaticamente. Este processo criar movimentos real de estoque.

|                              |                                                 |
|------------------------------|-------------------------------------------------|
| **Motivo para a depreciação**       | Substituído por outro recurso                     |
| **Substituída por outro recurso?** | Sim, a funcionalidade de remessa de entrada principal |
| **Módulos afetados**             | Contas a pagar, gerenciamento de estoque          |

### <a name="financial-reports-generator-for-eastern-europe"></a>Gerador de relatórios para Oriental financeiro Europa

Uma ferramenta para configurar coleções de dados para contabilidade e relatórios de imposto e exportar dados para modelos de relatório XLS e DOC

|                              |                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Uso restrito                                                                            |
| **Substituída por outro recurso?** | Não. A ferramenta será substituída por configurações de relatório eletrônico em versões futuras. |
| **Módulos afetados**             | Contabilidade                                                                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Importação de transações de pagamento de cliente para Finlândia

Você pode selecionar um formato de importação para pagamentos finlandeses que importa as transações de pagamento de cliente de um arquivo externo fornecido pelo banco.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                                                     |
| **Substituída por outro recurso?** | Não. O formato será substituído pela ISO 20022 formatos de importação do demonstrativo nas versões futuras. |
| **Módulos afetados**             | Contas a Receber                                                                       |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>Importação de transações de pagamento em um diário-razão para Finlândia

Um formato que é específico para a Finlândia para importar transações de contabilização na contabilidade.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                                                     |
| **Substituída por outro recurso?** | Não. O formato será substituído pela ISO 20022 formatos de importação do demonstrativo nas versões futuras. |
| **Módulos afetados**             | Contas a Receber                                                                       |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integração com Isabel sincronizada (CIS) para Bélgica

Isabel é a estrutura do banco eletrônico na Europa e um padrão de fatos na Bélgica.

|                              |                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Integração com clientes Isabel foi interrompida.                                                                |
| **Substituída por outro recurso?** | Não. Os formatos de pagamento usados não são substituídos pelo formato de pagamento de transferência de crédito ISO20022 para a Bélgica. |
| **Módulos afetados**             | Contas a Pagar                                                                                                     |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>Alterações no plano de contas e de regras contábeis para a Espanha

Este recurso é usado para as alterações no plano de contas e de regras contábeis na Espanha. Contas é mapeado para ajudar a tornar o plano de contas antigo no novo plano de contas, e compara o ano fiscal anterior com o novo ano fiscal, mesmo que foram lançados em números de contas diferentes.

|                              |                |
|------------------------------|----------------|
| **Motivo para a depreciação**       | Uso restrito  |
| **Substituída por outro recurso?** | Não             |
| **Módulos afetados**             | Contabilidade |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Formato de pagamento de fornecedor Fornittori de Pagamento

Formato de pagamento de legado italiano para transferências de crédito.

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                  |
| **Substituída por outro recurso?** | Sim, formato de pagamento de transferência de crédito ISO20022 para Itália |
| **Módulos afetados**             | Contas a Pagar                                       |

### <a name="payment-export-formats-for-estonia"></a>Formatos de exportação de pagamento para Estônia

Os formatos de Telehansa e de Teleservice são usados para exportação de pagamento bancário.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Motivo para a depreciação**      | Os formatos de pagamento não são mais usados.                  |
| **Substituída por outro recurso?** | Sim, formato de pagamento de transferência de crédito ISO20022 para Estônia |
| **Módulos afetados**             | Contas a Pagar                                         |

### <a name="payment-file-archive-for-norway"></a>Arquivo morto de arquivo de pagamento para Noruega

Quando os arquivos de pagamento são geradas, o arquivo morto de arquivo arquiva automaticamente todos os arquivos criados, apesar arquivos que foram anteriormente redigidos ou lidos.

|                              |                                                                    |
|------------------------------|--------------------------------------------------------------------|
| **Motivo para a depreciação**       | Substituído por outro recurso                                        |
| **Substituída por outro recurso?** | Sim, trabalhos arquivados de relatórios eletrônicos                            |
| **Módulos afetados**             | Contas a pagar, contas a receber, administração da organização |

### <a name="payment-import-formats-for-estonia"></a>Formatos de importação de pagamento para Estônia

Os formatos Telehansa e TeleTeenus são usados para importação de pagamento bancário.

|                              |                                                                                            |
|------------------------------|--------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                                                    |
| **Substituída por outro recurso?** | Não. Os formatos são substituídos pelos formatos de importação de demonstrativo da ISO 20022 em versões futuras. |
| **Módulos afetados**             | Contas a Receber                                                                        |

### <a name="performance-management-goal-workflow"></a>Fluxo de trabalho de meta de gerenciamento de desempenho

Gerenciamento de desempenho incluir o gerenciamento e a integração de meta com previsões resultados.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Gerenciamento de desempenho é remodelado, e o número de páginas da meta foi reduzido para simplificar o processo.                 |
| **Substituída por outro recurso?** | Não. Metas são visíveis a gerentes através do portal de autoatendimento para gerente e podem ser alteradas e exibidas pelo gerente. |
| **Módulos afetados**             | Gerenciamento de capital humano                                                                                                 |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>Formatos de pagamento Postgirot e Utland Postgirot para Suécia

Formatos de pagamento Postgirot e Utland Postgirot para Suécia.

|                              |                                                         |
|------------------------------|---------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                 |
| **Substituída por outro recurso?** | Sim, formato de pagamento de transferência de crédito ISO20022 para Suécia |
| **Módulos afetados**             | Contas a Pagar                                        |

### <a name="radio-frequency-identifier"></a>Identificador de radiofrequência

RFID (identificação de radiofrequência) é uma tecnologia de coleta de dados que usa etiquetas eletrônicas para armazenar dados de identificação e um leitor fora da linha de visão para capturar os dados de identificação.

|                              |                                               |
|------------------------------|-----------------------------------------------|
| **Motivo para a depreciação**       | Baixa utilização do cliente um conjunto de recursos limitado. |
| **Substituída por outro recurso?** | Não                                            |
| **Módulos afetados**             | Gerenciamento de estoque                          |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Relatório da numeração de notas fiscais de estado para Letônia

A legislação de Letão fornece regras específicas sobre como as notas fiscais de vendas devem ser numeradas. A funcionalidade permite atribuir números das faturas de vendas específicos, com base no usuário ou no grupo de usuários. Você pode salvar e gerar um relatório ou um arquivo XML. Você também pode imprimir um relatório sobre os números de nota fiscal que são usadas.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | A numeração do estado não deve ser mantida. Sobre o relatório de fatura números usados não é mais necessário. |
| **Substituída por outro recurso?** | Não                                                                                                                       |
| **Módulos afetados**             | Contas a Receber                                                                                                      |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Configurar nomes e gerente de contador geral de uma empresa para Lituânia

Nomes e gerente de contador geral de uma empresa podem ser especificados nas informações da empresa e ser usadas em impressões locais diferentes.

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| **Motivo para a depreciação**       | Substituído por outro recurso                                     |
| **Substituída por outro recurso?** | Sim, o de instalação dos responsáveis pode ser usado para a mesma finalidade.   |
| **Módulos afetados**             | Contas a pagar, Contas a receber, Gerenciamento de caixa e bancos |

### <a name="telepay-payment-formats-for-norway"></a>Formatos de pagamento para Telepay Noruega

Os formatos de pagamento Telepay incluem exportação de pagamento de fornecedor (transferência de crédito) e a coleção de pagamento de cliente (débito direto.)

|                              |                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                                                        |
| **Substituída por outro recurso?** | Sim, formato de pagamento de transferência de crédito ISO20022 e cliente de formato de pagamento AvtaleGiro para Noruega |
| **Módulos afetados**            | Contas a pagar, Contas a receber                                                          |

### <a name="vendor-payment-export-formats-for-finland"></a>Formatos de exportação de pagamento do fornecedor para Finlândia

Dois formatos de exportação de pagamentos estão disponíveis para a Finlândia. O LM02 (FI) é usado para pagamentos locais, e o LUM2 (FI) é usado para pagamentos estrangeiros.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Motivo para a depreciação**       | Os formatos de pagamento não são mais usados.                  |
| **Substituída por outro recurso?** | Sim, formato de pagamento de transferência de crédito ISO20022 para Finlândia |
| **Módulos afetados**            | Contas a Pagar                                         |

### <a name="workflow-for-creating-goals"></a>Fluxo de trabalho para criar metas

Um fluxo de trabalho para gerenciar a criação das metas de funcionários for um de vários fluxos de trabalho que estavam disponíveis para ajudar a coordenada o processo de gerenciamento de desempenho.

|                              |                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | O gerenciamento de desempenho foi reprojetado completamente no Microsoft Dynamics 365 for Finance and Operations.                                                                                                                                                                                                                                        |
| **Substituída por outro recurso?** | O recurso remodelado de gerenciamento de desempenho é mais controle sobre o conteúdo de meta, medições usados para controlar o progresso e, de anexos de documentos de suporte. As metas podem ser armazenadas como modelos e então ser reutilizados. Esse recurso pode ajudá-lo meta adicionais para os funcionários configurados mais rapidamente. |
| **Módulos afetados**            | Gerenciamento de capital humano                                                                                                                                                                                                                                                                                                               |

## <a name="features-that-have-been-deprecated-in-dynamics-ax-70-releases"></a>Recursos que foram substituídos nas versões do Dynamics AX 7.0

### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Capacidade de cancelar alterações para uma fatura do fornecedor

|                              |                         |
|------------------------------|-------------------------|
| **Motivo para a depreciação**       | Aprimoramento de desempenho |
| **Substituída por outro recurso?** | Não                      |
| **Módulos afetados**            | Contas a Pagar        |

### <a name="aif-axd-and-axbc-integrations"></a>Integrações de AIF, AxD e AxBC

Na Estrutura de Integração de Aplicativos (AIF), os dados podem ser trocados com sistemas externos através da lógica comercial que é exposta como serviços. O Dynamics AX inclui os serviços baseados em documentos e o .NET Business Connector (AxBC.) Um documento é criado usando XML. O XML inclui informações do cabeçalho que são adicionadas para criar uma *mensagem* que pode ser transferida para dentro ou fora do Dynamics AX. Os exemplos de documentos incluem ordens de venda e ordens de compra. No entanto, quase todas as entidades, como um cliente, podem ser representadas por um documento. Os serviços baseados em documentos usam as classes **Axd &lt;*Documento*&gt;**.

|                              |                                                                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | A arquitetura de AIF e de AxDs não pode ser dimensionada a um serviço de nuvem. Houve problemas de desempenho em relação à importação em massa.                                                                               |
| **Substituída por outro recurso?** | Na versão atual do Dynamics AX, este recurso é substituído pela estrutura de Importação/Exportação de Dados que suporta importação/exportação em massa recorrente. Para AxBC, recomendamos usar as tabelas reais. |
| **Módulos afetados**             | AxDs, AxBCs e AIF                                                                                                                                                                                     |

### <a name="boms-without-bom-versions"></a>As versões sem BOM

Quando a configuração principal de **Versões da BOM** estiver desabilitada, as versões da lista de materiais (BOM) ficarão ocultas em todos os formulários e o sistema forçará um relacionamento 1:1 entre os produtos liberados e as BOMs. A principal configuração de **Versões da BOM** não pode ser desativada na versão atual do Dynamics AX.

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| **Motivo para a depreciação**      | O uso de uma chave de configuração para controlar as versões da BOM não é escalonado em um ambiente de nuvem. |
| **Substituída por outro recurso?** | Não                                                                                      |
| **Módulos afetados**            | Gerenciamento de informações sobre o produto, Gerenciamento de estoque                                    |

### <a name="brazilian-bordero"></a>Bordero brasileiro

Método de pagamento específico para brasileiras empresas

|                              |                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Suporte para o método do Bordero de pagamento foi interrompido da localização brasileira |
| **Substituída por outro recurso?** | Não                                                                                                    |
| **Módulos afetados**             | Contas a Pagar                                                                                      |

### <a name="brazilian-sintegra-statement"></a>Demonstrativo de Sintegra brasileiro

Demonstrativo de imposto federal para impostos ICMS

|                              |                                                                                                                       |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Esta declaração não é aplicável uma maior em alguns estados brasileiros.                                                     |
| **Substituída por outro recurso?** | Não. Os usuários podem usar a ferramenta de relatório eletrônica genérica para configurar o demonstrativo, se necessário, em situações específicas. |
| **Módulos afetados**             | Livros fiscais                                                                                                          |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Modo de contingência SCAN brasileiro para NF-e

É possível usar o modo de contingência SCAN para gerar, exportar, e importar o status de uma Nota Fiscal eletrônica de (NF-e) quando o ambiente de origem da Secretaria da Fazenda (SEFAZ) não está disponível.

|                              |                                                                             |
|------------------------------|-----------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Este método de contingência não é aplicável maior nos estados brasileiros |
| **Substituída por outro recurso?** | Não                                                                          |
| **Módulos afetados**             | Contas a Receber                                                         |

### <a name="business-analyzer"></a>Business Analyzer

Este aplicativo móvel permite que os usuários revisem as principais métricas de negócios.

|                              |                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Esta funcionalidade foi substituída por outro recurso.                                                                                                      |
| **Substituída por outro recurso?** | O pacote de conteúdo de desempenho financeiro do Monitor para Microsoft Power BI incluirá as principais métricas financeiras que estavam disponíveis anteriormente no Business Analyzer. |
| **Módulos afetados**             | Contabilidade                                                                                                                                                |

### <a name="business-statistics"></a>Estatísticas comerciais

A configuração de consultas de estatísticas comerciais que podem ajudar a analisar o desempenho da organização

|                              |                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Abordagem herdada de business Intelligence (BI), baixa utilização do cliente e um conjunto de recursos limitado |
| **Substituída por outro recurso?** | Novas soluções de BI da versão atual do Dynamics AX                                      |
| **Módulos afetados**             | Compras, Contas a pagar, Vendas e marketing e Contas a receber         |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>Alterar a função de data do documento no Diário de aprovações de fatura

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Baixa utilização                                                               |
| **Substituída por outro recurso?** | Sim. A data do documento na transação de fornecedor lançada pode ser alterada. |
| **Módulos afetados**             | Contas a Pagar                                                        |

### <a name="clieop03-payment-format-for-the-netherlands"></a>Formato de pagamento ClieOp03 para os Países Baixos

|                              |                                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | O formato não é mais aplicável nos Países Baixos porque foi substituído pela funcionalidade de SEPA. |
| **Substituída por outro recurso?** | Exportação de pagamentos no SEPA                                                                                       |
| **Módulos afetados**             | Tudo                                                                                                        |

### <a name="compliance-center"></a>Centro de conformidade

O Centro de Conformidade era um site do Portal Empresarial para gerenciar os requisitos de documentação para iniciativas de conformidade relacionadas à lei Sarbanes-Oxley.

|                              |                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Escassez de uso do cliente. O Microsoft SharePoint inclui o mesmo recurso que estava disponível no Centro de Conformidade. |
| **Substituída por outro recurso?** | Não                                                                                                                     |
| **Módulos afetados**             | Conformidade e controles internos                                                                                       |

### <a name="connector-for-microsoft-dynamics"></a>Connector para Microsoft Dynamics

Esta ferramenta foi usada para integrar dados básicos do Microsoft Dynamics CRM em aplicativos ERP do Microsoft Dynamics.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| **Motivo para a depreciação**       | Esta funcionalidade foi substituída por outro recurso. |
| **Substituída por outro recurso?** | Dynamics Integrator                                      |
| **Módulos afetados**             | Connector para Microsoft Dynamics                         |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Unidade de contêiner e multidimensão em estoque

|                              |                                                                                                                                                                 |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Funcionalidade duplicada                                                                                                                                         |
| **Substituída por outro recurso?** | Sim. Desde o Since AX 2012, esta funcionalidade foi substituída pelo conjunto de recurso de ordens de lote consolidado. Este conjunto de recurso inclui a exibição disponível consolidada. |
| **Módulos afetados**             | Gerenciamento de informações sobre o produto, Controle de produção, Gerenciamento de estoque, Vendas e marketing                                                                   |

### <a name="cue-group-metadata"></a>Metadados do grupo de indicação

|                              |                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os grupos de indicação eram usados para exibir uma ou mais Indicações na área do Quadro de Fatos. Houve uma retirada limitada, e também houve preocupações com desempenho, porque uma alteração de registro em um formulário pai causou uma consulta por Indicação no grupo da Indicação. |
| **Substituída por outro recurso?** | Não                                                                                                                                                                                                                            |
| **Módulos afetados**             | Tudo                                                                                                                                                                                                                           |

### <a name="cue-metadata"></a>Metadados de indicação

|                              |                                                                                                                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os metadados de indicação foram limitados para contar ou somar informações.                                                                                                                                                                                   |
| **Substituída por outro recurso?** | Os metadados lado a lado foram introduzidos para oferecer mais flexibilidade para modelagem. Por exemplo, é possível modelar contas atuais, navegação e indicadores de desempenho chave (KPIs). Os metadados lado a lado de contagem são substituições diretas dos metadados da indicação. |
| **Módulos afetados**             | Tudo                                                                                                                                                                                                                                     |

### <a name="danish-check-format"></a>Formato de cheque dinamarquês

|                              |                                                                                                                         |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Suporte ao layout do formato de cheque dinamarquês foi interrompido e o relatório foi removido da localização de DK. |
| **Substituída por outro recurso?** | Não                                                                                                                      |
| **Módulos afetados**             | Tudo                                                                                                                     |

### <a name="data-partitions"></a>Partições de dados

As partições de dados fornecem uma divisão lógica de dados no banco de dados do Microsoft Dynamics AX.

|   |   |
|---|---|
| **Motivo para a depreciação**       | Partições de dados foram introduzidas no Microsoft Dynamics AX 2012 R2 para habilitar isolamento de dados. Em um cenário comum, uma empresa tem subsidiárias e os dados de uma subsidiária não deverão ser visíveis a outra subsidiária, embora ambas as subsidiárias são gerenciadas pelo mesmo departamento de TI. No entanto, gerenciamento de sobrecarga em todo o programa e scripts extras eram necessários para criar novas partições e preenchê-las com dados e para fazer backup de dados de partição. Na nuvem, onde temos acesso a plataforma como um serviço (PaaS) de banco de dados de serviços (Microsoft Azure SQL Database), é muito mais eficiente usar um banco de dados como o contêiner de isolamento do que fazer isolamento no programa. Independentemente se o particionamento de dados é necessário para subsidiárias, para vários locatários ou apenas para escala, acreditamos que as situações podem ser tratadas melhor por vários bancos de dados ou várias instâncias do Dynamics AX. |
| **Substituída por outro recurso?** | Partições de dados serão substituídas por meio do suporte a vários bancos de dados ou instâncias do Dynamics AX em uma versão futura.    |
| **Módulos afetados**             | Todas  |

### <a name="database-and-file-share-storage-for-attachments"></a>Armazenamento de banco de dados e de compartilhamento de arquivos para anexos
O Microsoft Dynamics AX 2012 permitia o armazenamento de anexos no base de dados e em compartilhamentos de arquivos. Não há mais suporte para essas opções.

|                              |                                        |
|------------------------------|----------------------------------------|
| **Motivo para a depreciação**       | O armazenamento de compartilhamento de arquivos não tem mais suporte porque os ambientes hospedados na nuvem não podem se comunicar com os compartilhamentos de arquivos locais. O armazenamento de banco de dados foi substituído pelo Armazenamento de Blobs do Azure. O Armazenamento de Blobs do Azure é equivalente ao armazenamento no banco de dados, já que os documentos só podem ser acessados por meio de formulários de cliente do Dynamics 365 for Finance and Operations. Isso oferece o benefício adicional de fornecer armazenamento que não prejudica o desempenho do banco de dados. O armazenamento de blobs é o mecanismo padrão de armazenamento para o Gerenciamento de Documentos e funciona imediatamente. |
| **Substituída por outro recurso?** | O armazenamento de banco de dados foi substituído pelo Armazenamento de Blobs do Azure.       |
| **Módulos afetados**             | Todas                   |

### <a name="delimitation"></a>Delimitação

|                              |                                        |
|------------------------------|----------------------------------------|
| **Motivo para a depreciação**       | Nenhum uso da funcionalidade foi encontrado. |
| **Substituída por outro recurso?** | Não                                     |
| **Módulos afetados**             | Horário e presença                    |

### <a name="desktop-client"></a>Cliente da área de trabalho

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | A experiência do cliente do Dynamics AX foi remodelada para melhorar a usabilidade entre várias plataformas e dispositivos.                      |
| **Substituída por outro recurso?** | O novo cliente Web baseia-se nos metadados do Formulário da área de trabalho e no modelo de programação que foi modificado para fornecer uma plataforma avançada da Web. |
| **Módulos afetados**             | Todas                                                                                                                                    |

### <a name="direct-database-connection"></a>Conexão direta do banco de dados

No Dynamics AX 2012 R3, o Retail Modern POS pode conectar-se diretamente ao BD do canal de modo semelhante ao PDV Empresarial. Isso ocorre além do método padrão de comunicação do Retail Modern POS comunicar-se com o Retail Server.  

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | A conectividade direta do base de dados exigiu protocolos de segurança inferior e foi usada principalmente para atingir os níveis mais altos de desempenho. Devido aos aprimoramentos de desempenho e segurança que ocorreram no Finance and Operations, essa funcionalidade agora causa mais problemas do que resolve. |
| **Substituída por outro recurso?** | Não. Apenas a comunicação padrão do Retail Server é suportada agora.    |
| **Módulos afetados**             | BD de Canal/Retail Modern POS                                    |

### <a name="dutch-swift-mt940"></a>SWIFT MT940 holandês

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | A funcionalidade genérica agora é usada em vez da funcionalidade encontrada.                                                                                                                                                                 |
| **Substituída por outro recurso?** | Sim, essa funcionalidade é substituída pela funcionalidade de reconciliação bancária Avançada. |
| **Módulos afetados**             | Todas                                                                                                                                                                                                                                   |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL para Alemanha)

Essa funcionalidade forneceu a saída XBRL (eXtensible Business Reporting Language) especificamente para a taxonomia eBilanz da Alemanha.

|                              |                                                                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Escassez de uso do cliente                                                                                                                                                 |
| **Substituída por outro recurso?** | Esse recurso não foi substituído por outro recurso, mas vários pacotes XBRL especializados que fornecem a funcionalidade XBRL avançada estão disponíveis para o mercado da Alemanha. |
| **Módulos afetados**             | Management Reporter                                                                                                                                                    |

### <a name="enterprise-portal-client"></a>Cliente do portal empresarial

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Uma única plataforma de cliente foi fornecida.                                                                                            |
| **Substituída por outro recurso?** | O novo cliente Web baseia-se nos metadados do formulário da área de trabalho e no modelo de programação que foi modificado para fornecer uma plataforma avançada da Web. |
| **Módulos afetados**             | Tudo                                                                                                                                    |

### <a name="environmental-sustainability"></a>Sustentabilidade ambiental

|                              |                                                    |
|------------------------------|----------------------------------------------------|
| **Motivo para a depreciação**       | Baixa utilização do cliente um conjunto de recursos limitado       |
| **Substituída por outro recurso?** | Não                                                 |
| **Módulos afetados**             | Conformidade e controles internos, Contas a pagar |

### <a name="form-activex-and-managed-host-controls"></a>Formulário ActiveX e Controles gerenciados por host

|                              |                                                                                                                                                                                               |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | O ActiveX e os controles Gerenciados por host são baseados no cliente obsoleto da área de trabalho.                                                                                                             |
| **Substituída por outro recurso?** | A estrutura de controle extensível suporta a criação de novos controles que são baseados em HTML, CSS e JavaScript e é um controle de primeira classe no ambiente de Ferramentas do Microsoft Visual Studio. |
| **Módulos afetados**             | Tudo                                                                                                                                                                                           |

### <a name="generate-prenotes-by-using-a-batch"></a>Gerar pré-registros usando um lote

A geração de pré-registros não poderá ser feita usando um lote, mas poderá ser feita por um usuário.

|                              |                                                                                                        |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Não existe formulário para persistir e exibir o arquivo de pré-registro resultante quando ele for gerado usando um lote. |
| **Substituída por outro recurso?** | Os pré-registros ainda podem ser gerados e o usuário tem controle sobre o local onde o arquivo é salvo.   |
| **Módulos afetados**             | Contas a pagar, Contas a receber, Gerenciamento de caixa e bancos                                        |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Exportação de pagamento de DTAUS e importação do demonstrativo de conta da Alemanha (totais e transações)

|                              |                                                                                                                                                                                                                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | O formato não é mais aplicável na Alemanha porque foi substituído pela funcionalidade de Área Única de Pagamentos em Euros (SEPA).                                                                                                                                                                 |
| **Substituída por outro recurso?** | Sim, esta funcionalidade foi substituída pela exportação de pagamento de SEPA e funcionalidade avançada de reconciliação bancária para importar demonstrativos de conta. |
| **Módulos afetados**             | Todas                                                                                                                                                                                                                                                                                            |

### <a name="german-dtazv-payment-format"></a>Formato de pagamento de DTAZV alemão

|                              |                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | O formato não é mais aplicável na Alemanha porque foi substituído pela funcionalidade de SEPA. |
| **Substituída por outro recurso?** | Exportação de pagamentos no SEPA                                                                               |
| **Módulos afetados**             | Tudo                                                                                                |

### <a name="german-mt940-import"></a>Importação MT940 alemão

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | A funcionalidade genérica agora é usada em vez da funcionalidade encontrada.                                                                                                                                                                 |
| **Substituída por outro recurso?** | Sim, essa funcionalidade é substituída pela funcionalidade de reconciliação bancária Avançada. |
| **Módulos afetados**             | Todas                                                                                                                                                                                                                                   |

### <a name="german-xml-eu-sales-list"></a>Lista de vendas alemã da UE - formato XML

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | O formato XML para o relatório de lista de vendas da União Europeia não é mais suportado. Somente o formato de arquivo de texto ELMA5 pode ser usado para enviar o relatório de lista de vendas da UE para impostos Office alemães. |
| **Substituída por outro recurso?** | Não                                                                                                                                                                                 |
| **Módulos afetados**             | Imposto                                                                                                                                                                                |

### <a name="gl-ssrs-reports"></a>Relatórios GL SSRS

Os relatórios que incluem os seguintes itens de menu foram removidos: **Balancete de resumo**, **Balancete detalhado**, **Plano de contas**, **Trilha de auditoria**, **Saldos** e **Lista de saldos**.

|                              |                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os relatórios financeiros do Microsoft SQL Server Reporting Services (SSRS) foram substituídos por recursos e relatórios padrão do Management Reporter. |
| **Substituída por outro recurso?** | Management Reporter (rotulado **Relatório financeiro** na versão atual do Dynamics AX)                                                  |
| **Módulos afetados**            | Contabilidade                                                                                                                               |

### <a name="infopart-and-formpart-metadata"></a>Os metadados de InfoPart e de FormPart

|                              |                                                                                                                                                                                                                                |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Os metadados de InfoPart e de FormPart habilitaram a criação de Quadros de Fatos para dois clientes diferentes.                                                                                                                                    |
| **Substituída por outro recurso?** | Os metadados de InfoPart, que eram uma definição simplificada do formulário, foram convertidos em um Formulário através da ferramenta de atualização. Os metadados de FormPart, que faziam referência a um Formulário, foram substituídos por uma referência mais direta criada pela ferramenta de atualização. |
| **Módulos afetados**             | Tudo                                                                                                                                                                                                                            |

### <a name="main-account-list-page"></a>Página de lista da conta principal

Uma lista de contas da entidade legal e informações relacionadas a saldo

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | As informações sobre saldo estão disponíveis na página de lista **Balancete** por conta e dimensão.                                                                                      |
| **Substituída por outro recurso?** | As **Contas principais** contêm a mesma lista de contas que a página de lista **Conta principal** continha. A exibição de grade nas **Contas principais** também mostra uma exibição menor, com grade. |
| **Módulos afetados**             | Contabilidade                                                                                                                                                                     |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Relatório de fluxo de caixa bancário da Malásia e de Cingapura

Este recurso permite que o usuário imprima um relatório de fluxo de caixa que mostra as transações e os detalhes das entradas e saídas de caixa para um intervalo de datas específico para as contas bancárias selecionadas.

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| **Motivo para a depreciação**       | A mesma informação pode ser obtida da transação bancária de Consulta. |
| **Substituída por outro recurso?** | A transação bancária de Consulta                                            |
| **Módulos afetados**             | Gerenciamento de caixa e bancos                                                |

### <a name="mexican-cfd-electronic-invoice"></a>Fatura eletrônica CFD mexicana

Este recurso habilitou a geração da fatura eletrônica mexicana usando o método Comprobante Fiscal Digital (CFD), no qual a empresa assina a fatura, solicitando a autorização relacionada do governo. Este recurso também fornece um relatório mensal que inclui todas as faturas eletrônicas que foram emitidas no período.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                           |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | O método não é mais aplicável. A geração de faturas eletrônicas usando o método CFD tornou-se obsoleta pelas autoridades fiscais e foi substituída pelo método Comprobante Fiscal Digital através de Internet (CFDI), no qual a assinatura é delegada ao provedor terceirizado (PAC). O relatório mensal foi removido, e uma opção de consulta permite que os usuários consultem transações históricas. |
| **Substituída por outro recurso?** | Não                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Módulos afetados**             | Contas a receber, Projeto                                                                                                                                                                                                                                                                                                                                                                              |

### <a name="mexico-realized-and-unrealized-vat"></a>IVA realizado e não realizado do México

O Microsoft Dynamics AX 2012 gerenciou imposto sobre valor agregado (IVA) não realizado usando a funcionalidade específica de México- “imposto não realizado.”

|                              |                                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Funcionalidade duplicada                                                                                             |
| **Substituída por outro recurso?** | Sim, essa funcionalidade foi substituída pela funcionalidade de imposto condicional padrão que é fornecida pelo Principal. |
| **Módulos afetados**             | Imposto                                                                                                                 |

### <a name="microsoft-outlook-integration"></a>Integração do Microsoft Outlook

|                              |                                                                                |
|------------------------------|--------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Essa funcionalidade foi substituída pela integração do Microsoft Exchange Server. |
| **Substituída por outro recurso?** | Sim                                                                            |
| **Módulos afetados**             | Vendas e marketing                                                            |

### <a name="payroll-information-in-human-resources"></a>Informações da Folha de pagamento em Recursos Humanos

Informações da Folha de Pagamento em Recursos Humanos

|                              |                                                                                                                                                                                                                                                                                                                              |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Essa funcionalidade foi substituída pelas páginas de folha de pagamento e Recursos humanos central.                                                                                                                                                                                                                                              |
| **Substituída por outro recurso?** | **Benefícios**, **Ganhos** e outras páginas relacionadas que estavam anteriormente na Folha de Pagamento dos EUA agora fazem parte da configuração de Recursos humanos central para ajudar a suportar o processamento da folha de pagamento externa. Essa funcionalidade é acessada usando a chave de configuração **Recursos Humanos 1** &gt; **Folha de Pagamento**. |
| **Módulos afetados**             | Recursos Humanos, Folha de Pagamento                                                                                                                                                                                                                                                                                                     |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Bloqueio privado de diários de gerenciamento de estoque e depósito

Os diários de estoque e depósito não oferecem suporte à capacidade de marcar um diário como particular para um usuário selecionado. Somente o processo de bloquear diários como privados para grupos de usuários e bloquear durante a edição é suportado.

|                              |                                        |
|------------------------------|----------------------------------------|
| **Motivo para a depreciação**       | Nenhum uso da funcionalidade foi encontrado. |
| **Substituída por outro recurso?** | Não                                     |
| **Módulos afetados**             | Gerenciamento de estoque                   |

### <a name="product-builder"></a>Configurador de produtos

O configurador de produtos foi usado para configurar itens dinamicamente a partir de uma ordem de venda, ordem de compra, ordem de produção, cotação de vendas, cotação de projeto ou requisito do item. Com base no modelo de produto que tinha as variáveis de modelagem, o usuário pode selecionar valores para atender às necessidades do cliente e obter uma variante de produtos que tinha uma BOM e um roteiro.

|                              |                                                                                                                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | O configurador de produtos expôs o código X++ aos usuários finais e não há suporte na versão atual do Dynamics AX. Foi removido para evitar esforços de manutenção duplicados em códigos base de sobreposição, dimensionáveis. |
| **Substituída por outro recurso?** | Configuração do produto                                                                                                                                                                                   |
| **Módulos afetados**             | Gerenciamento de informações do produto, Vendas e marketing                                                                                                                                                     |

### <a name="rename-product-dimension"></a>Renomear dimensão do produto

Este recurso permite que você altere o nome de uma das três dimensões padrão do produto (tamanho, cor ou estilo) para um nome que melhor se ajuste aos requisitos de negócios. Renomear inclui todas as etiquetas nas quais o nome da dimensão do produto foi usado.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | A versão atual do Dynamics AX não oferece suporte a alterações de etiqueta em tempo de execução. |
| **Substituída por outro recurso?** | Não                                                                            |
| **Módulos afetados**             | Gerenciamento de informações do produto                                                |

### <a name="retail-server-connectivity-using-http"></a>Conectividade do Retail Server usando HTTP

No Dynamics AX 2012 R3, o Retail Server pode funcionar usando a comunicação HTTP (não segura). Isso ocorre além da comunicação padrão que usa HTTPS.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Devido aos requisitos de segurança, apenas a comunicação protegida usando o TLS 1.2 (ou superior, conforme disponível) é suportada agora. O instalador de autoatendimento configurará automaticamente o computador para esta comunicação. |
| **Substituída por outro recurso?** | Não. Apenas a comunicação HTTPS padrão é suportada agora.                                                                           |
| **Módulos afetados**             | Retail Server                                                |

### <a name="role-center-pages"></a>Páginas do Centro de Funções

|                              |                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | As páginas do Centro de Funções foram compiladas na plataforma obsoleta do Portal Empresarial, que foi substituída por uma nova plataforma de clientes web na versão atual do Dynamics AX. |
| **Substituída por outro recurso?** | O novo padrão do formulário Espaço de Trabalho oferece aos usuários um design centralizado do processo que fornece acesso fácil às tarefas normalmente usadas dentro desse processo.                       |
| **Módulos afetados**             | Tudo                                                                                                                                                                      |

### <a name="sales-tax-jurisdictions"></a>Jurisdições de impostos

|                              |                                              |
|------------------------------|----------------------------------------------|
| **Motivo para a depreciação**       | Baixa utilização do cliente um conjunto de recursos limitado |
| **Substituída por outro recurso?** | Não                                           |
| **Módulos afetados**             | Impostos do EUA                                 |

### <a name="shipping-carrier-interface"></a>Interface de transportadora

|                              |                                                                                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Funcionalidade duplicada                                                                                                                         |
| **Substituída por outro recurso?** | Sim, esse recurso foi substituído parcialmente pelo Gerenciamento de transporte, mas ainda não foi substituído pelo Gerenciamento de depósito (WMS I). |
| **Módulos afetados**             | Vendas e marketing, Gerenciamento de estoque                                                                                                       |

### <a name="sites-services"></a>Sites Services

Os serviços de sites permitem criar os sites que estendem seus processos comerciais da Internet sem suporte de TI.

|                              |                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | A infraestrutura do Microsoft Azure usada pelo Dynamics AX tem os novos recursos que podem ser usados em vez de excluí-lo (por exemplo, sites de Azure). |
| **Substituída por outro recurso?** | Não                                                                                                                                       |
| **Módulos afetados**             | Recrutamento de RH, gerenciamento dos casos, solicitação de cotação, registro de fornecedor                                                                  |

### <a name="ssas-demand-forecasting-strategy"></a>Estratégia de previsão de demanda SSAS

|                              |                                                                              |
|------------------------------|------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | O design de recurso não pode ser suportado na nova arquitetura de nuvem. |
| **Substituída por outro recurso?** | Estratégia de previsão de demanda do Aprendizado de Máquina do Azure                           |
| **Módulos afetados**             | Planejamento                                                                     |

### <a name="travel-requisitions"></a>Requisições de viagem

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| **Motivo para a depreciação**       | Baixa utilização, e a maioria das funcionalidades existia no Portal Empresarial. |
| **Substituída por outro recurso?** | Não                                                              |
| **Módulos afetados**             | Gerenciamento de despesas                                              |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Grupo de faturas de fornecedor excluindo detalhes de lançamento

|                              |                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Baixa utilização. Essa funcionalidade foi substituída por diário de notas fiscais com a funcionalidade de fluxo de trabalho. |
| **Substituída por outro recurso?** | Recursos do fluxo de trabalho do Diário de faturas.                                                           |
| **Módulos afetados**             | Contas a Pagar                                                                                        |

### <a name="virtual-company-accounts"></a>Contas virtuais da empresa

O recurso virtual das empresas não é mais suportado no Dynamics AX. O recurso virtual das empresas habilitou os usuários a configurar as tabelas a serem compartilhadas por um conjunto de empresas. Você pode encontrar uma descrição do recurso aqui: [Contas da empresa e contas virtuais da empresa](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). O recurso funciona através do agrupamento de tabelas em coleções que são atribuídas a empresas virtuais, que são grupos de empresas "reais" existentes. As consultas são criadas de forma que todas as empresas na empresa virtual possam acessar os dados nas tabelas das cobranças de tabelas associadas.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><b>Motivo para a depreciação</b></td>
<td><ul>
<li>Empresas virtuais devem ser configuradas antes que os dados sejam armazenados nas tabelas. Adaptar empresas virtuais em uma implementação existente é muito difícil.</li>
<li>Como há um excesso de normalização de dados na versão atual do Dynamics AX, saber o tem se tornado difícil saber quais tabelas compartilhar. Por exemplo, é difícil saber quais tabelas compartilhar. Todas as tabelas referenciadas de tabelas que estão em uma empresa virtual também precisam ser adicionadas. Normalização de tabela significa que até a simples difusão de dados mestres entre diversas tabelas precisa fazer parte da empresa virtual. Qualquer erro que é feito aqui gerará saídas funcionais.</li>
<li>Quando uma tabela faz parte de uma empresa virtual, ela perde informações sobre a fonte de dados, e apenas a empresa virtual é registrada.</li>
</ul></td>
</tr>
<tr class="even">
<td><b>Substituída por outro recurso?</b></td>
<td>As tabelas globais podem ser usadas para criar tabelas acessíveis a todas as empresas. Atualmente, não há substituição.</td>
</tr>
<tr class="odd">
<td><b>Módulos afetados</b></td>
<td>Não aplicável</td>
</tr>
</tbody>
</table>

### <a name="warehouse-management-ii"></a>Gerenciamento de depósito II

|                              |                                                                                                                                                                                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | A solução de Gerenciamento de depósito II (WMS II) que está disponível no Módulo de **Gerenciamento de estoque** duplica a funcionalidade que está no módulo de **Gerenciamento de depósito** que foi liberada no Microsoft Dynamics AX 2012 R3.                                                                         |
| **Substituída por outro recurso?** | O módulo de **Gerenciamento de depósito** que foi liberado no AX 2012 R3, no Microsoft Dynamics AX 2012 R3 CU8 e no Dynamics AX 2012 R3 CU9 substitui os recursos do Gerenciamento de depósito II. O novo módulo tem mais recursos avançados e processos de gerenciamento de depósito mais flexíveis do que os no Gerenciamento de depósito II. |
| **Módulos afetados**             | Gerenciamento de estoque, Vendas e marketing, Compras                                                                                                                                                                                                                                         |

### <a name="worker-reminders-in-human-resources"></a>Lembretes do trabalhador em Recursos Humanos

Informações da Folha de Pagamento em Recursos Humanos

|                              |                 |
|------------------------------|-----------------|
| **Motivo para a depreciação**       | Baixa utilização       |
| **Substituída por outro recurso?** | Não              |
| **Módulos afetados**             | Recursos humanos |

### <a name="workplanner"></a>Planejador de trabalho

|                              |                                                                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Baixa utilização                                                                                                                                                            |
| **Substituída por outro recurso?** | Não, mas a página **Relação de perfil**, que é aberta na página **Grupos de perfil**, suporta o mesmo cenário empresarial que a página obsoleta **Planejador de trabalho**. |
| **Módulos afetados**             | Horário e presença                                                                                                                                                  |

### <a name="x-financial-statements"></a>Demonstrativos financeiros X++

|                              |                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------|
| **Motivo para a depreciação**       | Esta funcionalidade foi substituída por outro recurso.                                    |
| **Substituída por outro recurso?** | Management Reporter (rotulado **Relatório financeiro** na versão atual do Dynamics AX) |
| **Módulos afetados**             | Contabilidade                                                                              |


