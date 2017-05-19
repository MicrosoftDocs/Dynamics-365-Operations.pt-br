---
title: "Recrutamento de conteúdo do Power BI"
description: "Este tópico descreve o Microsoft Dynamics 365 for Operations - Recrutando Conteúdo do Power BI. Ele explica como acessar os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 15780e7db5867a2f6a484ceb663e617345c033c2
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="recruiting-power-bi-content"></a>Recrutamento de conteúdo do Power BI

[!include[banner](../includes/banner.md)]


Este tópico descreve o Microsoft Dynamics 365 for Operations - Recrutando Conteúdo do Power BI. Ele explica como acessar os relatórios incluídos no pacote de conteúdo, além de fornecer informações sobre o modelo de dados e as entidades usados para criar o pacote de conteúdo.

<a name="accessing-the-content-pack"></a>Acessando o pacote de conteúdo
--------------------------

Você pode encontrar o pacote de conteúdo do Recrutamento na biblioteca de ativos compartilhados no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações sobre como baixar o pacote de conteúdo e conectá-lo a seus dados do Microsoft Dynamics 365 for Operations, consulte [Conteúdo do Power BI no LCS da Microsoft e seus parceiros](power-bi-content-microsoft-partners.md).

## <a name="reports-that-are-included-in-the-content-pack"></a>Relatórios incluídos no pacote de conteúdo
Após a conexão do pacote de conteúdo aos dados do Dynamics 365 for Operations, os relatórios mostrarão os dados da sua organização. Se você nunca usou o Microsoft Power BI antes, você pode saber mais sobre ele na página [Aprendizado guiado para Power BI](https://powerbi.microsoft.com/en-us/guided-learning/?WT.mc_id=PBIService_GetData). Os relatórios incluídos no pacote de conteúdo têm gráficos e tabelas que contêm informações adicionais. A tabela a seguir descreve os relatórios.

| Relatório                       | Conteúdo                                                                                               |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Análise do candidato           | Candidatos por trabalho, fontes por candidato, candidatos por local e número total de candidatos           |
| Status do candidato             | Candidatos por tipo, por status e status do candidato                                                    |
| Demográficos do candidato       | Candidatos por idade e por sexo, candidatos por nível e por status educacionais                             |
| Análise de recrutamento          | Margem líquida de arrendamento, média de dias para contratar, porcentagem de contratações ruins e custos de recrutamento                    |
| Análise de projeto de recrutamento | Número de projetos de recrutamento, aberturas para projeto de recrutamento e candidatos por projeto de recrutamento |

Você pode filtrar os gráficos e blocos nesses relatórios e fixá-los no painel. Para obter mais informações sobre como filtrar e fixar no Power BI, consulte [Criar e configurar um painel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards).

## <a name="understanding-the-data-model-and-entities"></a>Noções básicas sobre o modelo de dados e as entidades
Os dados do Microsoft Dynamics 365 for Operations são usados para preencher os relatórios no pacote de conteúdo do recrutamento. A seguinte tabela mostra as entidades nas quais o pacote de conteúdo foi baseado.

| Entidade                          | Conteúdo                                                         | Relações com outras entidades                                                                                                                                                                                                                 |
|---------------------------------|------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Recruiting\_Applicant           | Candidatos, candidatos contratados, taxa de contratação de redes e custos          | Recruiting\_ApplicantName Recruiting\_Company Recruiting\_CalendarOffset Recuriting\_Date Recruiting\_GeographicLocation Recruiting\_Demographics Recruiting\_Job Recruiting\_Media Recruiting\_RecruitmentProject                                |
| Recruiting\_ApplicantName       | Primeiro nome do candidato, sobrenome e nome completo                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_CalendarOffset      | Compensações de calendário para dividir relatórios                                | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Company             | Empresas para filtrar relatórios                                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Date                | Dias, semanas, meses e anos                                   | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Demographics        | Data de nascimento, gênero, origem étnica e estado civil         | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_EmployedApplicant   | Candidato, desempenho, data inicial e tipo de candidato           | Recruiting\_Company Recruiting\_CalendarOffset Recruiting\_Date Recruiting\_GeographicLocation Recruiting\_ApplicantName Recruiting\_Employment Recruiting\_Performance Recruiting\_Job Recruiting\_Media Recruiting\_RecruitmentProject          |
| Recruiting\_Employment          | Data inicial, data final e data de transição                        | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_GeographicLocation  | Cidade, região, CEP e estado ou província                 | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Job                 | Função, tipo e título                                        | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Media               | Fonte de candidatos                                             | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_Performance         | Classificação, descrição e modelo de classificação                            | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_RecruitmentProject  | Descrição do projeto, status do projeto e aberturas                | Recruiting\_Applicant Recruiting\_EmployedApplicant Recruiting\_TerminatedApplicant                                                                                                                                                               |
| Recruiting\_TerminatedApplicant | Candidatos finalizados, desempenho e data de demissão | Recruiting\_Company Recruiting\_CalendarOffset Recruiting\_Date Recruiting\_GeographicLocation Recruiting\_Performance Recruiting\_Demographics Recruiting\_Employment Recruiting\_Media Recruiting\_RecruitmentProject Recruiting\_ApplicantName |

Essas entidades foram usadas para criar medidas calculadas. Essas medidas calculadas são então usadas para calcular os KPIs (indicadores chave de desempenho) e os relatórios usados no pacote de conteúdo. Para incluir cálculos adicionais nos seus relatórios e painel, você pode baixar e modificar o arquivo Recruiting.pbix do LCS. Esse arquivo de trabalho é o modelo de dados padrão usado para criar o pacote de conteúdo. Após a realização de modificações, poderá criar um painel e pacote de conteúdo organizacional contendo as informações adicionadas.

## <a name="additional-resources"></a>Recursos adicionais
Estes são alguns links úteis relacionados às entidades e ao desenvolvimento de conteúdo do Power BI:

-   [Entidades de dados](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)
-   [Criando pacotes de conteúdo organizacionais](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelagem de dados por meio do Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adicionando blocos do Power BI aos espaços de trabalho](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/07/06/pinning-power-bi-reports-to-dynamics-ax-client/)





