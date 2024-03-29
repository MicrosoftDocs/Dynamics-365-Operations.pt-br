---
title: Conteúdo do Power BI Desempenho de depósito
description: Este artigo descreve o que está incluído no conteúdo do Power BI Desempenho de depósito.
author: Mirzaab
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 272953
ms.assetid: 4e4d4323-78cf-4ffa-8d5a-05e856c33db6
ms.search.form: WHSWarehousePerformancePowerBI
ms.openlocfilehash: 82f43f45b43df864cbda8ba372dbed46d8f4c7e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289836"
---
# <a name="warehouse-performance-power-bi-content"></a>Conteúdo do Power BI Desempenho de depósito

[!include [banner](../includes/banner.md)]

Este artigo descreve o que está incluído no conteúdo do Microsoft Power BI **Desempenho de depósito**. Ele explica como acessar os relatórios do Power BI e fornece informações sobre o modelo de dados e entidades que são usados para criar o conteúdo.

## <a name="overview"></a>Visão Geral

O conteúdo do Power BI **Desempenho de depósito** foi criado para que os gerentes de depósito e operações possam monitorar métricas de estoque, entrada e saída importantes. Ele usa o gerenciamento de depósito, produto e outros dados transacionais do seu sistema, e fornece visão agregada de desempenho de depósito e uma divisão para fornecedores, grupos de produtos e produtos, e locais e depósitos.

Os gerentes de estoque podem usar o conteúdo do Power BI **Desempenho de depósito** para medir as três áreas a seguir:

- **Desempenho de entrada** – mede o desempenho do fornecedor em relação aos requerimentos do cliente (ou seja, mede o desempenho de entrega) e mede o desempenho de armazenamento a fim de que você possa identificar problemas envolvendo trabalhadores ou itens durante um período. É importante saber se os fornecedores estão entregando no prazo, com antecedência ou com atraso para determinar como o desempenho do fornecedor está afetando o desempenho do armazenamento geral. Um fornecedor que entrega fora das datas acordadas cria uma pressão extra sobre o depósito, por causa do trabalho inesperado, e pode aumentar o tempo médio de armazenamento.
- **Desempenho de remessa** – mede se o seu depósito está fazendo remessas de forma integral e no prazo para os clientes (ou seja, mede a remessa de saída e o desempenho da entrega) para que você possa identificar qualquer problema envolvendo produtos, sites, depósitos ou clientes exclusivos. Se achar que remessas a áreas ou cidades específicas estão ocorrendo com atraso, pode ser necessário prestar mais atenção ao gerenciamento de conta ou transporte.
- **Precisão do estoque do local** – a precisão do estoque é uma importante business intelligence (BI) do depósito interno. É muito importante determinar com quão precisamente você está realizando a contagem geral. No entanto, também é importante que você determine o quão preciso você é ao armazenar itens nos locais corretos e se você destaca dados de discrepância a fim de que seja possível achar posições melhores para os itens ou iniciar uma contagem total de itens específicos. (No momento, a nova funcionalidade de contagem baseada em item é fornecida como um hotfix.) Se você estiver usando esse conteúdo do Power BI para determinar a exatidão dos dados de estoque disponível por local, também poderá identificar roubos nas lojas. Você também pode determinar se qualquer local possui quantidades disponíveis que diferem dos dados de ERP (planejamento de recursos empresariais). Esses locais podem ser muito grandes ou pode ser impossível contá-los. Como alternativa, alguns dos posicionamentos físicos podem ser ruins, motivo pelo qual é difícil manter um único tipo de item em sincronia com os dados disponíveis.

## <a name="accessing-the-power-bi-content-pack"></a>Acessando o pacote de conteúdo do Power BI
O conteúdo do Power BI **Desempenho de depósito** é exibido na página **Desempenho de depósito** (**Gerenciamento de depósito** \> **Consultas e relatórios** \> **Análise de desempenho de depósito** \> **Desempenho de depósito**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas incluídas no conteúdo do Power BI
O conteúdo do Power BI **Desempenho de depósito** inclui um relatório. Esse relatório consiste em um conjunto de métricas visualizadas, como gráficos, blocos e tabelas. A tabela a seguir oferece uma visão geral das visualizações no conteúdo **CustCollectionsBICrossCompany** do Power BI.

| Página de relatório                 | Gráficos                                   | descrição |
|-----------------------------|------------------------------------------|-------------|
| Desempenho de entrada         | Total de armazenamentos                          | O número de linhas de trabalho de armazenamento processadas durante um determinado período. |
| Desempenho de entrada         | Tempo médio de armazenamento                    | O tempo médio, em horas, de todas as linhas de armazenamento de ordem de compra processadas, desde registro dos itens até o processamento da última colocação. |
| Desempenho de entrada         | Recebido com antecedência                           | O número de linhas de ordem de compra recebidas com antecedência. |
| Desempenho de entrada         | Recebido no prazo                         | O número de linhas de ordem de compra recebidas no prazo. |
| Desempenho de entrada         | Recebimento atrasado                            | O número de linhas de ordem de compra recebidas com atraso. |
| Desempenho de entrada         | No prazo por fornecedor                        | Uma exibição da porcentagem de linhas de ordem de compra recebidas de um fornecedor ou grupo de fornecedores com antecedência, no prazo ou com atraso. |
| Desempenho de entrada         | Doca para armazenamento médio de estoque (horas) | O tempo médio de armazenamento de doca para estoque em horas ao longo do tempo. |
| Desempenho de entrada         | Armazenamento médio por trabalhador               | O tempo médio, em horas, que um trabalhador leva para processamento de armazenamento de linhas de ordem de compra. |
| Desempenho de entrada         | Armazenamento médio por fornecedor          | O tempo médio de armazenamento em horas por fornecedor ou grupo de fornecedores. |
| Desempenho de entrada         | Armazenamento médio por produto         | O tempo médio de armazenamento em horas por item ou grupo de itens. |
| Precisão do estoque do local | Total da contagem                              | O número de linhas de trabalho de contagem processadas durante um determinado período. |
| Precisão do estoque do local | Taxa de discrepância                         | A taxa de discrepância total como porcentagem de todas as linhas contadas em um determinado período. |
| Precisão do estoque do local | Contagem sem discrepância                | Do número total de linhas de trabalho de contagem processadas, do número de linhas processadas sem qualquer discrepância. |
| Precisão do estoque do local | Itens contados ao longo do tempo                  | A porcentagem de itens que são contados com e sem discrepância ao longo do tempo. |
| Precisão do estoque do local | Discrepância de quantidade de itens superior a % | Uma exibição de tabela das linhas de contagem com discrepâncias que excedem uma porcentagem especificada. A tabela inclui informações sobre locais, itens, discrepância média, linhas de trabalho de contagem total contadas, número de linhas de contagem com discrepâncias do local, quantidade média contada, quantidade total esperada a ser contada e quantidade de itens real que contada. |
| Precisão do estoque do local | Contagem de itens por trabalhador                     | O desempenho da contagem dos funcionários. O desempenho é expresso como porcentagem de linhas de trabalho de contagem com e sem discrepâncias. |
| Precisão do estoque do local | Contagem de itens por site/depósito           | O desempenho de contagem pelo número de linhas de trabalho de contagem processadas por site ou depósito com e sem discrepâncias. |
| Precisão do estoque do local | Taxa de discrepância por produto              | A taxa de discrepância para desempenho de contagem. A taxa é expressa como porcentagem de linhas de trabalho de contagem processadas por item ou grupo de itens. |
| Desempenho de remessa        | Linhas enviadas                            | O número total de linhas de remessa enviadas durante um determinado período. |
| Desempenho de remessa        | Antecipada                                    | A porcentagem de linhas de remessa enviadas com antecedência. |
| Desempenho de remessa        | No prazo                                  | A porcentagem de linhas de remessa enviadas no prazo. |
| Desempenho de remessa        | Atrasada                                     | A porcentagem de linhas de remessa enviadas com atraso. |
| Desempenho de remessa        | Remessas ao longo do tempo                      | A porcentagem de linhas de remessa enviadas no prazo, com antecedência ou com atraso durante um determinado período. A linha de tendência mostra a tendência para linhas enviadas no prazo. |
| Desempenho de remessa        | Enviada com atraso por cidade                     | Uma visualização de mapa de cidades e áreas afetadas por remessas atrasadas. |
| Desempenho de remessa        | Enviada por produto                       | A porcentagem enviada com antecedência, no prazo ou com atraso por item ou grupo de itens. |
| Desempenho de remessa        | Enviada por cliente                      | A porcentagem enviada com antecedência, no prazo ou com atraso por cliente ou grupo de clientes. |
| Desempenho de remessa        | Enviada por site/depósito              | A porcentagem enviada com antecedência, no prazo ou com atraso por site ou depósito. |

## <a name="understanding-the-data-model-and-calculations"></a>Noções básicas sobre modelo de dados e cálculos
Os seguintes dados são usados para preencher as páginas de relatório no conteúdo do Power BI **Desempenho de depósito**. Esses dados são representadas como medições agregadas que foram preparadas no Repositório de entidades. O Repositório de entidades é um banco de dados do Microsoft SQL Server otimizado para análise. Para obter mais informações, consulte [Integração do Power BI com o repositório Entidade](power-bi-integration-entity-store.md).

As principais medidas agregadas a seguir são usadas como base do conteúdo.

| Página de relatório                 | Gráficos                                   | Tabelas                                | Descrições de cálculo |
|-----------------------------|------------------------------------------|---------------------------------------|--------------------------|
| Desempenho de entrada         | Total de armazenamentos                          | WHSWorkLine                           | A contagem de linhas de trabalho quando o tipo de trabalho é **colocado**. |
| Desempenho de entrada         | Tempo médio de armazenamento                    | WHSWorkLine                           | A soma de tempo máximo de linhas de trabalho dividida pela contagem de tempo máximo de linhas de trabalho, quando o tempo máximo de linhas de trabalho é a lacuna máxima entre a data de criação e conclusão do trabalho. |
| Desempenho de entrada         | Recebido com antecedência                           | WHSWorkLine                           | A contagem de linhas de trabalho quando a data de criação do trabalho é anterior à data de entrega usada. Se a data de confirmação da entrega não estiver definida, use a data de entrega padrão. |
| Desempenho de entrada         | Recebido no prazo                         | WHSWorkLine                           | A contagem de linhas de trabalho quando a data de criação do trabalho é igual à data de entrega usada. Se a data de confirmação da entrega não estiver definida, use a data de entrega padrão. |
| Desempenho de entrada         | Recebimento atrasado                            | WHSWorkLine                           | A contagem de linhas de trabalho quando a data de criação do trabalho é posterior à data de entrega usada. Se a data de confirmação da entrega não estiver definida, use a data de entrega padrão. |
| Desempenho de entrada         | No prazo por fornecedor                        | WHSWorkLine                           | Recebido com antecedência, recebido no prazo e recebido com atraso (veja as descrições apresentadas anteriormente nesta tabela). |
| Desempenho de entrada         | Doca para armazenamento médio de estoque (horas)   | WHSWorkLine                           | Tempo médio de armazenamento (veja as descrições apresentadas anteriormente nesta tabela). |
| Desempenho de entrada         | Armazenamento médio por trabalhador               | WHSWorkLine                           | Tempo médio de armazenamento (veja as descrições apresentadas anteriormente nesta tabela). |
| Desempenho de entrada         | Armazenamento médio por fornecedor          | WHSWorkLine                           | Tempo médio de armazenamento (veja as descrições apresentadas anteriormente nesta tabela). |
| Desempenho de entrada         | Armazenamento médio por produto         | WHSWorkLine                           | Tempo médio de armazenamento (veja as descrições apresentadas anteriormente nesta tabela). |
| Precisão do estoque do local | Total da contagem                              | WHSWorkLineCycleCount                 | Contagens cíclicas quando a quantidade de discrepância absoluta é igual ou superior a 0 (zero). |
| Precisão do estoque do local | Taxa de discrepância                         | WHSWorkLineCycleCount                 | Contagens cíclicas com discrepâncias, divididas pela contagem total. Considera-se que uma contagem cíclica tem discrepâncias quando a quantidade de discrepância absoluta é superior a 0 (zero). |
| Precisão do estoque do local | Contagem sem discrepância                | WHSWorkLineCycleCount                 | Contagens cíclicas quando a quantidade de discrepância absoluta é superior a 0 (zero). |
| Precisão do estoque do local | Contagem com discrepância                   | WHSWorkLineCycleCount                 | Contagens cíclicas quando a quantidade de discrepância absoluta é igual a 0 (zero). |
| Precisão do estoque do local | Itens contados ao longo do tempo                  | WHSWorkLineCycleCount                 | Contagem sem discrepância e contagem sem discrepância (Veja as descrições apresentadas anteriormente nesta tabela.) |
| Precisão do estoque do local | Discrepância de quantidade de itens superior a % | WHSWorkLineCycleCount                 | A discrepância média é a quantidade de discrepância absoluta dividida pela quantidade esperada quando a quantidade de discrepância absoluta é superior a 0 (zero). A quantidade de discrepância média é a discrepância absoluta média dividida quando a quantidade de discrepância absoluta é superior a 0 (zero). Contagem com discrepância, contagem total, quantidade esperada e quantidade contada quando a quantidade total é agrupada por item e local (veja as descrições apresentadas anteriormente nesta tabela). |
| Precisão do estoque do local | Contagem de itens por trabalhador                     | WHSWorkLineCycleCount                 | Contagem sem discrepância e contagem sem discrepância (veja as descrições apresentadas anteriormente nesta tabela). |
| Precisão do estoque do local | Contagem de itens por site/depósito           | WHSWorkLineCycleCount                 | Contagem sem discrepância e contagem sem discrepância (veja as descrições apresentadas anteriormente nesta tabela). |
| Precisão do estoque do local | Taxa de discrepância por produto              | WHSWorkLineCycleCount                 | Taxa de discrepância (veja as descrições apresentadas anteriormente nesta tabela). |
| Desempenho de remessa        | Linhas enviadas                            | SalesLine               | A contagem de linhas de venda quando as linhas de venda são enviadas. |
| Desempenho de remessa        | Antecipada                                    | CustPackingSlipOnTimeStatus           | Linhas de venda quando o status da data de remessa é **1 (Antecipada)**. Antecipado significa que a data de remessa da guia de remessa é anterior à data de remessa confirmada da linha de venda. Se a data de remessa confirmada não estiver definida, use a data de remessa solicitada. |
| Desempenho de remessa        | No prazo                                  | CustPackingSlipOnTimeStatus           | Linhas de venda quando o status da data de remessa é **2 (No prazo)**. No prazo significa que a data de remessa da guia de remessa é igual à data de remessa confirmada da linha de venda. Se a data de remessa confirmada não estiver definida, use a data de remessa solicitada. |
| Desempenho de remessa        | Atrasada                                     | CustPackingSlipOnTimeStatus           | Linhas de venda quando o status da data de remessa é **3 (Atrasada)**. Atrasada significa que a data de remessa da guia de remessa é posterior à data de remessa confirmada da linha de venda. Se a data de remessa confirmada não estiver definida, use a data de remessa solicitada. |
| Desempenho de remessa        | Remessas ao longo do tempo                      | SalesLine CustPackingSlipOnTimeStatus | Ordens que são completamente enviadas, quando a quantidade total da linha de venda é enviada, mais antecipada, no prazo e atrasada (Veja as descrições apresentadas anteriormente nesta tabela.) |
| Desempenho de remessa        | Enviada com atraso por cidade                     | CustPackingSlipOnTimeStatus           | Atrasada (veja as descrições apresentadas anteriormente nesta tabela). |
| Desempenho de remessa        | Enviada por produto                       | CustPackingSlipOnTimeStatus           | Antecipada, no prazo e atrasada (veja as descrições apresentadas anteriormente nesta tabela). |
| Desempenho de remessa        | Enviada por cliente                      | CustPackingSlipOnTimeStatus           | Antecipada, no prazo e atrasada (veja as descrições apresentadas anteriormente nesta tabela). |
| Desempenho de remessa        | Enviada por site/depósito              | CustPackingSlipOnTimeStatus           | Antecipada, no prazo e atrasada (veja as descrições apresentadas anteriormente nesta tabela). |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
