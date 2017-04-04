---
title: "Conteúdo de recrutamento de O power BI"
description: "Este tópico descreve o dynamics 365 para operações - conteúdo de recrutamento de O power BI. Explica como acessar os relatórios que são incluídos no bloco de conteúdo, além fornece informações sobre o modelo de dados e as entidades usados para construir o bloco de conteúdo."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 263934
ms.assetid: 38e6827b-0819-473c-bc47-821a1ec482b8
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: d307733193b388149f83dd420cc7003edcf7749a
ms.lasthandoff: 03/31/2017


---

# <a name="recruiting-power-bi-content"></a>Conteúdo de recrutamento de O power BI

Este tópico descreve o dynamics 365 para operações - conteúdo de recrutamento de O power BI. Explica como acessar os relatórios que são incluídos no bloco de conteúdo, além fornece informações sobre o modelo de dados e as entidades usados para construir o bloco de conteúdo.

<a name="accessing-the-content-pack"></a>Acessando o bloco de conteúdo
--------------------------

Você pode encontrar o bloco de conteúdo de recrutamento na biblioteca de ativos compartilhados em serviços (LCS) do Microsoft Dynamics lifecycle. Para obter mais informações sobre como o download do bloco de conteúdo e o seu alocação Microsoft Dynamics 365 de dados, consulte operações [conteúdo de O power BI em LCS Microsoft e seus parceiros (power-bi-content-microsoft-partners.md]).

## <a name="reports-that-are-included-in-the-content-pack"></a>Relata incluído no bloco de conteúdo
Após conectou bloco de conteúdo ao 365 para dados de operações, os relatórios aos dados da organização. Se nunca você usou o power BI Microsoft antes, você pode saber mais sobre ela em [guiado aprendizado a página do power] de BI (https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Os relatórios que são incluídos no bloco de conteúdo já os gráficos e tabelas que contêm informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório                       | Conteúdo                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Análise do candidato           | Candidatos por trabalho, para origens do candidato, por candidatos por local, e pelo número total de candidatos           |
| Status do candidato             | Candidatos por tipo e, por status e status do candidato                                                    |
| De candidato demográficos       | Candidatos por idade e por sexo, candidatos e por nível e por status educacionais                             |
| Análise de recrutamento          | Margem líquida de arrendamento, dias médio a contratação, percentual de empréstimos incorretos, e custo de recrutamento                    |
| Análise de projeto de recrutamento | Número de projetos de recrutamento, de aberturas por projeto de recrutamento, candidatos e do projeto de recrutamento |

Você pode filtrar os gráficos e os quadros nesses relatórios, gráficos e fixa e os quadros para o painel. Para obter mais informações sobre como filtragem e fixar-se o power BI, consulte para [criar e configurar um painel] (https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
O dynamics 365 para dados de operações é usado para preencher os relatórios no bloco de conteúdo de recrutamento. A tabela a seguir mostra as entidades do bloco de conteúdo será baseado.

| Entidade                          | Conteúdo                                                         | Relações com outras entidades                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Candidato de recrutamento do\_           | Candidatos, candidatos contratados, taxa de contratação de redes, e custos          | \_de recrutamento ApplicantName de recrutamento a empresa\_que\_CalendarOffset recrutamento Recuriting\_\_data de recrutamento que os GeographicLocation recrutamento demográficos\_que recrutam\_que recrutam mídia\_que recrutam\_RecruitmentProject                                |
| \_ApplicantName de recrutamento       | , Nome e sobrenome, nome completo do candidato                   | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| \_CalendarOffset de recrutamento      | Compensação do calendário a fatia de relatórios                                | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| Empresa de recrutamento do\_             | Empresas para filtrar de relatórios                                   | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| Data de recrutamento do\_                | , Semanas dias, meses, anos e                                   | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| Demográficos de recrutamento do\_        | Data de nascimento, de, gênero de origem, étnica e estado civil         | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| \_EmployedApplicant de recrutamento   | Candidato, desempenho, data inicial, tipo e do candidato           | Empresa de recrutamento do\_que\_CalendarOffset recrutamento de recrutamento a data do\_que\_GeographicLocation recrutamento de recrutar\_que ApplicantName recrutamento o\_que recrutamento o desempenho do\_de recrutar\_que recrutam mídia\_que recrutam\_RecruitmentProject          |
| Aplicativo de recrutamento do\_          | Data inicial, data final, e data de transição                        | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| \_GeographicLocation de recrutamento  | Cidade, CEP, região, estado ou província e                 | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| Trabalhos de recrutamento do\_                 | Função, tipo, título e                                        | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| Mídia de recrutamento do\_               | Origem de candidatos                                             | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| Desempenho de recrutamento do\_         | Classificação, descrição, e modelo de classificação                            | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| \_RecruitmentProject de recrutamento  | Descrição do projeto, status do projeto, e aberturas                | Candidato de recrutamento do\_que EmployedApplicant recrutamento\_que\_TerminatedApplicant recrutamento                                                                                                                                                               |
| \_TerminatedApplicant de recrutamento | Candidatos finalizados, o desempenho, e a data de demissão | Empresa de recrutamento do\_que\_CalendarOffset recrutamento de recrutamento a data do\_que\_GeographicLocation recrutamento de recrutar o desempenho do\_que o recrutamento demográficos\_que recrutam o\_que recrutamento mídia\_que recrutam\_RecruitmentProject que\_ApplicantName recrutamento |

Essas entidades foram usadas para criar medidas calculadas. Essas medidas calculadas são usadas para calcular os principais indicadores chave de desempenho (KPIs) e relatórios usados no bloco de conteúdo. Se desejar incluir cálculos adicionais nos relatórios e o painel, você pode alterar e baixar o arquivo de Recruiting.pbix de LCS. Esse arquivo é o modelo de dados padrão usado para criar blocos do conteúdo. Depois de feitas alterações, você pode criar um bloco e um painel de conteúdo organizacional que contém as informações que você adicionou.

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)



