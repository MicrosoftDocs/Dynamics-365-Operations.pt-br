---
title: Introdução à API de integração da folha de pagamento
description: Este tópico descreve a API de integração da folha de pagamento do Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6d8a1cb9619a863184460a74e472af3f06934b6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058551"
---
# <a name="payroll-integration-api-introduction"></a>Introdução à API de integração da folha de pagamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este documento descreve a API de integração da folha de pagamento do Dynamics 365 Human Resources. A API permite integrações completas simplificadas entre o Human Resources e sistemas de folha de pagamento de parceiros. A experiência integrada começa em Human Resources com o perfil do funcionário, salário e dedução e informações de contribuição. Quando você contrata um funcionário e insere as informações necessárias sobre o perfil e o pagamento em Human Resources, o sistema de folha de pagamento recebe essas informações para usar ao processar a folha de pagamento. As atualizações feitas nas informações do funcionário ou do pagamento também são extraídas para uso em execuções de pagamento futuras.

![Fluxo de integração da folha de pagamento](media/hr-admin-integration-payroll-api-introduction-flow.png)

Para habilitar a integração, o Human Resources inclui os seguintes componentes:

- Funcionalidade para marcar um funcionário como pronto para pagar
- Uma API de integração que abre a nova funcionalidade para integrar aplicativos

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Esta API foi desenvolvida com base no Microsoft Dataverse (antes conhecido como Common Data Service). Toda a interação RESTful com essa API é realizada por meio da API Web do Microsoft Dataverse, que usa OData. Essa API é um subconjunto da API Web do Dataverse. A API Web do Dataverse define características como autenticação, SLAs, lote, controle de simultaneidade e tratamento de erros.

Para obter mais informações gerais sobre a API Web do Microsoft Dataverse, consulte:

- [O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)
- [Use a API Web do Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)
- [Guia do desenvolvedor do Microsoft Dataverse](/powerapps/developer/data-platform)

Esta documentação inclui detalhes e orientações para o desenvolvedor sobre o uso da API Web do Dataverse, incluindo os seguintes tópicos:

- [Autenticar para o Microsoft Dataverse com a API Web](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [Executar operações usando a API Web](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [Usar o Postman com a API Web](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [Usar o controle de alterações para sincronizar dados com sistemas externos](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Tabelas virtuais para o Human Resources no Dataverse

Os pontos de extremidade para a API de integração da folha de pagamento usam os recursos da plataforma de tabela virtual do Microsoft Dataverse. Por padrão, as tabelas virtuais e os pontos de extremidade da API associados não são implantados para ambientes do Human Resources, permitindo que organizações determinem quais pontos de extremidade OData serão expostos para o ambiente. Para usar a API, as tabelas virtuais de entidades do Human Resources devem ser geradas para o ambiente.

Para obter informações sobre como gerar as tabelas virtuais da API, consulte [Configurar tabelas virtuais do Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="data-model"></a>Modelo de dados

O diagrama a seguir ilustra relacionamentos na API. Vários tipos têm chaves estrangeiras para outras entidades preexistentes no Human Resources que não estão ilustradas aqui. Este documento fornece informações sobre entidades específicas para cenários de integração da folha de pagamento. No entanto, há várias outras entidades na API Web do Dataverse para o Human Resources que também podem ser relevantes para sua integração. Algumas dessas entidades são referenciadas em relações de chave estrangeira ou propriedades de navegação.

![Modelo de dados de API de integração da folha de pagamento](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a>Funcionário da folha de pagamento e entidades relacionadas

Entidades:

- [Funcionário da folha de pagamento](hr-admin-integration-payroll-api-payroll-employee.md)
- [Endereço do trabalhador da folha de pagamento](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [Plano de remuneração fixa da folha de pagamento](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Trabalho da posição na folha de pagamento](hr-admin-integration-payroll-api-payroll-position-job.md)
- [Posição na folha de pagamento](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a>Consulte também

[Gerar e revisar entidades da folha de pagamento](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[Configurar parâmetros do Human Resources](hr-setup-parameters.md)<br>
[Configurar parâmetros compartilhados do Human Resources](hr-setup-shared-parameters.md)<br>
[O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Use a API Web do Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]