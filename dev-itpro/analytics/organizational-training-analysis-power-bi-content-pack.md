---
title: "Conteúdo organizacional do power BI de treinamento"
description: "Este tópico descreve o dynamics 365 para operações - conteúdo organizacional do power BI de treinamento. Acessar explica como o bloco de conteúdo, além descreve o modelo de dados e as entidades usados para construir o bloco de conteúdo."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263874
ms.assetid: 45dbba14-aba6-4571-be0d-5d1aba3515d9
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 104164f8ffd0d2bc3a64bf15d2fb5213234046ce
ms.lasthandoff: 03/31/2017


---

# <a name="organizational-training-power-bi-content"></a>Conteúdo organizacional do power BI de treinamento

Este tópico descreve o dynamics 365 para operações - conteúdo organizacional do power BI de treinamento. Acessar explica como o bloco de conteúdo, além descreve o modelo de dados e as entidades usados para construir o bloco de conteúdo.

<a name="accessing-the-content-pack"></a>Acessando o bloco de conteúdo
--------------------------

Você pode encontrar o bloco organizacional de conteúdo de treinamento na biblioteca de ativos compartilhados em serviços (LCS) do Microsoft Dynamics lifecycle. Para obter mais informações sobre como o download do bloco de conteúdo e o seu alocação Microsoft Dynamics 365 de dados, consulte operações [conteúdo de O power BI em LCS Microsoft e seus parceiros (power-bi-content-microsoft-partners.md]).

## <a name="reports-that-are-included-in-the-content-pack"></a>Relata incluído no bloco de conteúdo
Após conectou bloco de conteúdo ao 365 para dados de operações, os relatórios aos dados da organização. Se nunca você usou o power BI Microsoft antes, você pode saber mais sobre ela em [guiado aprendizado a página do power] de BI (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Os relatórios que são incluídos no bloco de conteúdo já os gráficos e tabelas que contêm informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório          | Conteúdo                                                                    |
|-----------------|-----------------------------------------------------------------------------|
| Análise de curso | Registro por local, participantes de cursos, por status e lista de registro |
| Tipos de curso    | Tipos de cursos por habilidade                                                       |

Você pode filtrar os gráficos e os quadros nesses relatórios, gráficos e fixa e os quadros para o painel. Para obter mais informações sobre como filtragem e fixar-se o power BI, consulte para [criar e configurar um painel] (https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
O dynamics 365 para dados de operações é usado para preencher os relatórios no bloco organizacional de conteúdo de treinamento. A tabela a seguir mostra as entidades do bloco de conteúdo será baseado.

| Entidade                    | Conteúdo                                                         | Relações com outras entidades                                                                                                                                                                  |
|---------------------------|------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \_CalendarOffset treinamento  | Compensação do calendário a fatia de relatórios                                | \_CourseAgenda treinamento que treina\_CourseAttendees                                                                                                                                                   |
| Empresa do\_de treinamento         | Empresas para filtrar de relatórios                                   | \_CourseAgenda treinamento que treina\_CourseAttendees                                                                                                                                                   |
| \_curso de treinamento          | Curso, descrição, nome do instrutor, local, status e sala, | \_CourseAgenda treinamento que treina\_CourseAttendees que treina\_CourseSkill                                                                                                                             |
| \_CourseAgenda treinamento    | Agenda, curso, além inicial e hora final                          | Empresa do\_de treinamento que treina\_CalendarOffset que treina a data do\_que o curso treina\_                                                                                                                         |
| \_CourseAttendees treinamento | Nome, status, trabalho, e a data de registro                         | Empresa do\_de treinamento que treina\_CalendarOffset que a data treina\_que os treina demográficos\_que treinam o\_que o curso treina\_que treina\_WorkerName que treina\_WorkerTitle que treina a posição do\_de treinamento de trabalho\_ |
| \_CourseSkill treinamento     | Habilidades, tipo de habilidade, e nível                                     | \_curso de treinamento                                                                                                                                                                                   |
| Data do\_de treinamento            | , Semanas dias, meses, anos e                                   | \_CourseAgenda treinamento que treina\_CourseAttendees                                                                                                                                                   |
| Demográficos\_de treinamento    | Data de nascimento, de, gênero de origem, étnica e estado civil         | \_CourseAgenda treinamento que treina\_CourseAttendees                                                                                                                                                   |
| Aplicativo do\_de treinamento      | Data inicial, data final, e data de transição                        | \_CourseAgenda treinamento que treina\_CourseAttendees                                                                                                                                                   |
| Trabalho do\_de treinamento             | Função, tipo, título e                                        | \_CourseAgenda treinamento que treina\_CourseAttendees                                                                                                                                                   |
| Cargo do\_de treinamento        | Título, posição, e equivalente (FTE) horário integral                  | \_CourseAgenda treinamento que treina\_CourseAttendees                                                                                                                                                   |
| \_WorkerName treinamento      | Nome, nome e sobrenome, concluída                             | \_CourseAttendees treinamento                                                                                                                                                                          |
| \_WorkerTitle treinamento     | Título e data de precedência                                         | \_CourseAttendees treinamento                                                                                                                                                                          |

Essas entidades foram usadas para criar medidas calculadas no modelo de dados. Essas medidas calculadas são usadas para calcular os principais indicadores chave de desempenho (KPIs) e relatórios usados no bloco de conteúdo. Se desejar incluir cálculos adicionais nos relatórios e o painel, você pode alterar e baixar o arquivo de Training.pbix de LCS. Esse arquivo é o modelo de dados padrão usado para criar blocos do conteúdo. Depois de feitas alterações, você pode criar um bloco e um painel de conteúdo organizacional que contém as informações que você adicionou.

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



