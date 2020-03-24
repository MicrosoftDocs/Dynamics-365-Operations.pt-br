---
title: Comparação de recursos de nuvem e locais
description: O tópico mostra quais recursos são suportados na Nuvem e locais.
author: sericks007
manager: AnnBe
ms.date: 03/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 89563
ms.assetid: ''
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2017-11-29
ms.dyn365.ops.version: Platform update 9
ms.openlocfilehash: 50ab5827f864b53137acb77e75055e995ea6f439
ms.sourcegitcommit: 1789a78de1cbeac19d96767812df653a191c67e9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2020
ms.locfileid: "3100273"
---
# <a name="comparison-of-cloud-and-on-premises-features"></a>Comparação de recursos de nuvem e locais

[!include [banner](../includes/banner.md)]

Esse tópico mostra comparação recursos disponíveis na nuvem versus na infraestrutura local para os seguintes aplicativos:

- [Dynamics 365 Finance](cloud-prem-comparison.md#dynamics-365-finance)
- [Dynamics 365 Supply Chain Management](cloud-prem-comparison.md#dynamics-365-supply-chain-management)
- [Dynamics 365 Commerce](cloud-prem-comparison.md#dynamics-365-commerce)
- [Dynamics 365 Human Resources](cloud-prem-comparison.md#dynamics-365-human-resources)

Informações sobre os [recursos de desenvolvimento e de administração](cloud-prem-comparison.md#development-and-administration-features) também foram incluídas.

As tabelas a seguir listam as áreas do aplicativo. O suporte à nuvem e aos locais é listado para o recurso como um todo. Onde os recursos específicos da área total forem diferentes, os recursos são listados em uma linha separada na coluna Recurso.

## <a name="dynamics-365-finance"></a>Dynamics 365 Finance

| **Área**             | **Recurso**                | **Nuvem** | **Local** |
|---------------------|-----------------------------|-----------|-----------------|
| Conformidade e certificações        |                                                                                           | Sim       | Sim             |
|                                      | Certificação do Tipo 1 SOC 1                                                                | Sim       | Não              |
| Integração e gerenciamento de dados      |                                                                                           | Sim       | Sim             
|                                      | Exportar dados para seu próprio depósito de dados                                                    | Sim       | Sim             |
|                                      | Habilitar a exportação de atualizações incrementais para uma entidade de dados                                 | Sim       | Sim              |
|                                      | Integrações de dados                                                                         | Sim       | Sim             |
| Gerenciamento de documentos                  |                                                                                           | Sim       | Sim             |
| Gerenciamento financeiro                 |                                                                                           | Sim       | Sim             |
| Ajuda                                 |                                                                                           | Sim       | Não              |
| Recursos humanos                      |                                                                                           | Sim       | Sim             |
| Inteligência                         |                                                                                           | Sim       | Sim             |
|                                      | Relatório eletrônico (ER)                                                                 | Sim       | Sim             |
|                                      | ER: integração como o LCS                                                                  | Sim       | Não              |
|                                      | ER: integração como o SharePoint                                                           | Sim       | Não              |
|                                      | ER: integração com os Serviços de configuração regulatória (RCS)                              | Sim       | Não              |
|                                      | ER: usa o sistema de arquivos local como o armazenamento das configurações de ER acessíveis pelos repositórios de ER | Não        | Sim             |
|                                      | Integração com PowerBI.com                                                              | Sim       | Não              |
|                                      | Integração ao PowerBI Desktop                                                          | Não        | Sim             |
|                                      | Espaços de trabalho analíticos                                                                     | Sim       | Não              |
|                                      | Processo de negócios do Intelligent: Recomendações                                             | Sim       | Não              |
|                                      | Criação de relatórios do Power BI com OData usando ferramentas do Power BI Desktop ou do Power Query para Excel    | Sim       | Não              |
|                                      | O SQL Server Reporting Services (SSRS) dá suporte à escala horizontal                                 | Sim       | Não              |
|                                      | A telemetria é transferida para a nuvem                                                   | Sim       | Não              |
| Lifecycle Services                   |                                                                                           | Sim       | Sim             |
|                                      | Processos de negócios configuráveis                                                           | Sim       | Não              |
| Localizações                        |                                                                                           | Sim       | Sim             |
| Aplicativo móvel, espaços de trabalho e plataforma |                                                                                           | Sim       | Sim             |
| Integração do Office                   |                                                                                           | Sim       | Sim             |
| Administração da organização          |                                                                                           | Sim       | Sim             |
| Folha de Pagamento                              |                                                                                           | Sim       | Sim             |
|                                      | Depósito direto                                                                            | Sim       | Não              |
| Gerenciamento e contabilidade do projeto    |                                                                                           | Sim       | Sim             |
| Segurança                             |                                                                                           | Sim       | Sim             |
| Gerenciamento de serviços                   |                                                                                           | Sim       | Sim             |
| Cliente web                           |                                                                                           | Sim       | Sim             |
|                                      | Gravador de tarefas - Salvar ou carregar gravações de tarefas da biblioteca de BPM                         | Sim       | Não              |
| Suporte                              |                                                                                           | Sim       | Sim             |
|                                      | Acesso ao suporte por meio do menu Ajuda e Suporte                                             | Sim       | Não              |
|                                      | Eventos de negócios                                                                           | Sim       | Sim (é necessária conectividade com a Internet ou pontos de extremidade personalizados devem ser implementados para enviar/receber eventos de negócios na intranet)              |

## <a name="dynamics-365-supply-chain-management"></a>Dynamics 365 Supply Chain Management 

| **Área**                | **Recurso**             | **Nuvem** | **Local** |
|-------------------------|-------------------|-----------|-----------------|
| Conformidade e certificações        |                                                                                           | Sim       | Sim             |
|                                      | Certificação do Tipo 1 SOC 1                                                                | Sim       | Não              |
| Contabilização de custos                      |                                                                                           | Sim       | Sim             |
|                                      | Pacote de conteúdo de contabilização de custos para Power BI                                                 | Sim       | Não              |
|                                      | Espaço de trabalho da contabilidade de custos para aplicativo móvel                                                  | Sim       | Não              |
| Gerenciamento de custo                      |                                                                                           | Sim       | Sim             |
|                                      | Pacote de conteúdo de gerenciamento de custos para Power BI                                                 | Sim       | Não              |
| Integração e gerenciamento de dados      |                                                                                           | Sim       | Sim             |
|                                      | Extensão acionada pela configuração                                                            | Sim       | Não              |
|                                      | Exportar dados para seu próprio depósito de dados                                                    | Sim       | Sim             |
|                                      | Habilitar a exportação de atualizações incrementais para uma entidade de dados                                 | Sim       | Sim              |
|                                      | Integrações de dados                                                                         | Sim       | Sim             |
| Gerenciamento de documentos                  |                                                                                           | Sim       | Sim             |
| Ajuda                                 |                                                                                           | Sim       | Não              |
| Inteligência                         |                                                                                           | Sim       | Sim             |
|                                      | Relatório eletrônico (ER)                                                                 | Sim       | Sim             |
|                                      | ER: integração como o LCS                                                                  | Sim       | Não              |
|                                      | ER: integração como o SharePoint                                                           | Sim       | Não              |
|                                      | ER: integração com os Serviços de configuração regulatória (RCS)                              | Sim       | Não              |
|                                      | ER: usa o sistema de arquivos local como o armazenamento das configurações de ER acessíveis pelos repositórios de ER | Não        | Sim             |
|                                      | Integração com PowerBI.com                                                              | Sim       | Não              |
|                                      | Integração ao PowerBI Desktop                                                          | Não        | Sim             |
|                                      | Espaços de trabalho analíticos                                                                     | Sim       | Não              |
|                                      | Processo de negócios do Intelligent: Recomendações                                             | Sim       | Não              |
|                                      | Criação de relatórios do Power BI com OData usando ferramentas do Power BI Desktop ou do Power Query para Excel    | Sim       | Não              |
|                                      | O SQL Server Reporting Services (SSRS) dá suporte à escala horizontal                                 | Sim       | Não              |
|                                      | A telemetria é transferida para a nuvem                                                   | Sim       | Não              |
| Gerenciamento de estoque                 |                                                                                           | Sim       | Sim             |
| Lifecycle Services                   |                                                                                           | Sim       | Sim             |
|                                      | Processos de negócios configuráveis                                                           | Sim       | Não              |
| Localizações                        |                                                                                           | Sim       | Sim             |
| Fabricação                        |                                                                                           | Sim       | Sim             |
| Planejamento e previsão mestre      |                                                                                           | Sim       | Sim             |
| Aplicativo móvel, espaços de trabalho e plataforma |                                                                                           | Sim       | Sim             |
| Integração do Office                   |                                                                                           | Sim       | Sim             |
| Administração da organização          |                                                                                           | Sim       | Sim             |
| Compras e fornecimento             |                                                                                           | Sim       | Sim             |
|                                      | Punch-out para catálogo externo da requisição de compra                                   | Sim       | Não              |
|                                      | Relatórios do Power BI de análise de gastos em compras                                                  | Sim       | Não              |
| Gerenciamento de informações do produto       |                                                                                           | Sim       | Sim             |
| Dados de produto mestre                  |                                                                                           | Sim       | Sim             |
| Produção                           |                                                                                           | Sim       | Sim             |
|                                      | Relatórios do Power BI de desempenho da produção                                                   | Sim       | Não              |
| Gerenciamento e contabilidade de projeto    |                                                                                           | Sim       | Sim             |
| Vendas                                |                                                                                           | Sim       | Sim             |
|                                      | Relatórios do Power BI de desempenho de vendas e lucratividade                                      | Sim       | Não              |
| Segurança                             |                                                                                           | Sim       | Sim             |
| Gerenciamento de serviços                   |                                                                                           | Sim       | Sim             |
| Gerenciamento da cadeia de fornecedores              |                                                                                           | Sim       | Sim             |
| Gerenciamento de transporte            |                                                                                           | Sim       | Sim             |
| Colaboração do fornecedor                 |                                                                                           | Sim       | Não              |
| Gerenciamento de depósito                 |                                                                                           | Sim       | Sim             |
|                                      | Aplicativo móvel de depósito                                                                      | Sim       | Sim             |
|                                      | Relatórios do Power BI de depósito                                                              | Sim       | Não              |
| Cliente web                           |                                                                                           | Sim       | Sim             |
|                                      | Gravador de tarefas - Salvar ou carregar gravações de tarefas da biblioteca de BPM                         | Sim       | Não              |
| Suporte                              |                                                                                           | Sim       | Sim             |
|                                      | Acesso ao suporte por meio do menu Ajuda e Suporte                                             | Sim       | Não              |

## <a name="dynamics-365-commerce"></a>Dynamics 365 Commerce 

Para ver uma lista de recursos disponíveis em implantações locais, consulte [Recursos do Commerce disponíveis em implantações locais](../../../retail/retail-onprem.md).

## <a name="dynamics-365-human-resources"></a>Dynamics 365 Human Resources 

| **Área**         | **Recurso**         | **Nuvem** | **Local** |
|------------------|---------------------|-----------|-----------------|
| Todas as áreas de Recursos Humanos | Todos os recursos de Recursos Humanos | Sim       | Não              |

## <a name="development-and-administration-features"></a>Recursos de desenvolvimento e administração

| **Área**                   | **Recurso**                               | **Nuvem** | **Local** |
|----------------------------|-------------------------------------------|-----------|-----------------|
| Criar e testar             |                                           | Sim       | Sim             |
| Extensibilidade              |                                           | Sim       | Sim             |
| Monitoramento e telemetria   |                                           | Sim       | Sim             |
| Compatibilidade de plataforma     |                                           | Sim       | Sim             |
| Atendimento                  |                                           | Sim       | Sim             |
|                            | Ambientes de atendimento                    | Sim       | Não              |
| Trace Parser e PerfTimer |                                           | Sim       | Não              |
| Atualizar                    |                                           | Sim       | Sim             |
|                            | Atualizar                                   | Sim       | Não              |
|                            | Atualização e suporte para versões anteriores | Sim       | Não              |
| Desenvolvimento no Visual Studio  |                                           | Sim       | Sim             |

