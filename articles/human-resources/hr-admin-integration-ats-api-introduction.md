---
title: Introdução da API de integração do sistema de acompanhamento de candidatos
description: Este tópico descreve a API de integração do ATS (sistema de acompanhamento de candidatos) do Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 48e368fe69443a5105ddba78a887bf9159bfe52a
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125584"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a>Introdução da API de integração do sistema de acompanhamento de candidatos

Este tópico descreve a API de integração do ATS (sistema de acompanhamento de candidatos) do Dynamics 365 Human Resources. A intenção da API é habilitar integrações otimizadas entre o Dynamics 365 Human Resources e ATSs de parceria.

![Fluxo de integração do ATS](media/hr-admin-integration-ats-api-introduction-flow.png)

A experiência integrada começa no Human Resources quando um gerente de contratação cria uma solicitação de recrutamento. Quando a solicitação é ativada, o ATS recebe os detalhes da solicitação para criar um projeto de recrutamento. Ele segue o pipeline de recrutamento para selecionar e contratar um candidato para as posições. Finalmente, o ATS conclui a integração de ida e volta enviando o registro do candidato selecionado para o Human Resources. O registro de candidatos pode passar pela integração de mais validações e fluxos de trabalho para criar o registro de funcionário.

Para habilitar a integração, o Human Resources adicionou os seguintes componentes:

1.  Funcionalidade para criar uma solicitação de recrutamento.
2.  Um perfil de candidato expandido e os fluxos de trabalho relacionados.
3.  Uma API de integração que abre a nova funcionalidade para integrar aplicativos.

Para obter mais informações sobre como configurar e usar a solicitação de recrutamento e a funcionalidade do candidato, consulte [Recrutar candidatos ao trabalho](hr-personnel-recruit.md).

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Esta API foi desenvolvida com base no Microsoft Dataverse (antes conhecido como Common Data Service). Toda a interação RESTful com essa API é realizada por meio da API Web do Microsoft Dataverse, que usa OData. Essa API é um subconjunto da API Web do Dataverse. A API Web do Dataverse define características como autenticação, SLAs, lote, controle de simultaneidade e tratamento de erros.

Para obter mais informações gerais sobre a API Web do Microsoft Dataverse, consulte:

- [O que é o Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)
- [Use a API Web do Microsoft Dataverse](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)
- [Guia do desenvolvedor do Microsoft Dataverse](https://docs.microsoft.com/powerapps/developer/data-platform)

A documentação acima inclui diretrizes de detalhe e desenvolvedor sobre o uso da API Web do Dataverse, como [gerenciamento de autenticação](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [execução de operações](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [uso do Postman com a API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api) e [uso de controle de alterações ou tokens delta](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) com a API.

### <a name="option-sets"></a>Conjuntos de opções

O modelo de dados para a API de integração ATS descrito neste documento inclui conjuntos de opções que fornecem valores enumerados associados a propriedades da entidade. Para obter detalhes sobre como trabalhar com conjuntos de opções na API Web do Dataverse, consulte [Criar e atualizar conjuntos de opções usando a API Web](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets). Os conjuntos de opções são definidos para cada ambiente do Dataverse.

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Tabelas virtuais para o Human Resources no Dataverse

Os pontos de extremidade para a API de integração ATS usam os recursos da plataforma de tabela virtual do Microsoft Dataverse. Por padrão, as tabelas virtuais e os pontos de extremidade da API associados não são implantados para ambientes do Human Resources, permitindo que organizações determinem quais pontos de extremidade OData serão expostos para o ambiente. Para usar a API, as tabelas virtuais de entidades do Human Resources devem ser geradas para o ambiente. 

Para obter informações sobre como gerar as tabelas virtuais da API, consulte [Configurar tabelas virtuais do Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="data-model"></a>Modelo de dados

O modelo de dados está centrado em duas entidades principais:

- **RecruitingRequest** representa uma solicitação de um ATS para recrutar uma ou mais posições abertas. Para obter um exemplo de consulta, consulte [Exemplo de consulta para solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md).
- **CandidateToHire** representa detalhes de um candidato que aceitou uma oferta para uma posição. **Pessoa** representa o indivíduo que é o candidato. Uma pessoa pode ter várias funções na empresa, como candidato, trabalhador, funcionário ou prestador de serviço. Para obter um exemplo de consulta, consulte [Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).

O diagrama a seguir ilustra relacionamentos na API. Vários tipos têm chaves estrangeiras para outras entidades preexistentes no Human Resources que não estão ilustradas aqui. Este documento fornece informações sobre entidades específicas para recrutar cenários de integração. No entanto, há várias outras entidades na API Web do Dataverse para o Dynamics 365 Human Resources que também podem ser relevantes para sua integração. Por exemplo, você também pode precisar de detalhes sobre trabalhadores, cargos, posições ou outras entidades não definidas aqui. Muitas dessas entidades são referenciadas em relações de chave estrangeira ou propriedades de navegação.

![Modelo de dados de API de integração do ATS](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a>Recrutar solicitação, entidades relacionadas e conjuntos de opções

Exemplo de consulta: 

- [Consulta de exemplo de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-example-query.md)

Entidades:

- [Solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request.md)
- [Posição da solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-position.md)
- [Habilidade de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [Formação educacional de solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Localização da solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-location.md)

Conjuntos de opções:

- [Status de isenção de trabalho](hr-admin-integration-ats-api-job-exempt-status.md)
- [Status da posição da solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [Status da solicitação de recrutamento](hr-admin-integration-ats-api-recruiting-request-status.md)
- [Categoria de trabalho regulatório](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a>Candidato a ser contratado, entidades relacionadas e conjuntos de opções

Exemplo de consulta:

- [Exemplo de consulta de candidato a ser contratado](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

Entidades:

- [Candidatos para contratação](hr-admin-integration-ats-api-candidate-to-hire.md)
- [Pessoa](hr-admin-integration-ats-api-person.md)
- [Educação da pessoa](hr-admin-integration-ats-api-person-education.md)
- [Experiência profissional da pessoa](hr-admin-integration-ats-api-person-professional-experience.md)
- [Endereço da pessoa](hr-admin-integration-ats-api-person-address.md)
- [Contato do participante](hr-admin-integration-ats-api-party-contact.md)
- [Habilidade da pessoa](hr-admin-integration-ats-api-person-skill.md)
- [Nível de avaliação](hr-admin-integration-ats-api-rating-level.md)
- [Certificado de pessoa](hr-admin-integration-ats-api-person-certificate.md)
- [Tipo de certificado](hr-admin-integration-ats-api-certificate-type.md)
- [Triagem da pessoa](hr-admin-integration-ats-api-person-screening.md)
- [Tipos de triagem](hr-admin-integration-ats-api-screening-types.md)
- [Número de identificação da pessoa](hr-admin-integration-ats-api-person-identification-number.md)

Conjuntos de opções:

- [Resultado da integração do candidato](hr-admin-integration-ats-api-applicant-integration-result.md)
- [Em branco Sim/Não](hr-admin-integration-ats-api-blank-yes-no.md)
- [Status de conclusão](hr-admin-integration-ats-api-completion-status.md)
- [Tipo de contato](hr-admin-integration-ats-api-contact-type.md)
- [Base de crédito de educação](hr-admin-integration-ats-api-education-credit-basis.md)
- [Sexo](hr-admin-integration-ats-api-gender.md)
- [Estado civil](hr-admin-integration-ats-api-marital-status.md)
- [Meses do ano](hr-admin-integration-ats-api-months-of-year.md)
- [Não/Sim](hr-admin-integration-ats-api-no-yes.md)
- [Unidade de período](hr-admin-integration-ats-api-period-unit.md)
- [Frequência de triagem](hr-admin-integration-ats-api-screening-frequency.md)
- [Geração de frequência de triagem de](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [Tipo de nível de habilidade](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a>Consulte também

[Candidatos de trabalho de recrutamento](hr-personnel-recruit.md)<br>
[O que é o Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[Use a API Web do Microsoft Dataverse](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)<br>
[Criar e atualizar conjuntos de opções usando a API Web](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]