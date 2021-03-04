---
title: Novidades ou alterações no Dynamics 365 Talent (28 de maio de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 29e941ddab1b2746ccd74d6e335fec7742d1391e
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529599"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-28-2019"></a>Novidades ou alterações no Dynamics 365 Talent (28 de maio de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract
Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Em breve no Attract

### <a name="job-approvals-on-home-page"></a>Aprovações de trabalho na página inicial

As aprovações aparecem em uma seção **Aprovações** no painel. Os aprovadores podem revisar suas aprovações em **Atribuída(s) a você**, que exibe a ID do trabalho, título, outros aprovadores e a data atribuída. Os usuários que enviam um trabalho para aprovação podem revisar seus trabalhos em **Solicitado por você**, que exibe os aprovadores que ainda precisam aprovar o trabalho enviado.

## <a name="changes-in-onboard"></a>Alterações de Integração
Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR
As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2319.

### <a name="common-data-service-entity-support-for-custom-fields"></a>A entidade Common Data Service oferece suporte a campos personalizados

Nessa versão, as seguintes entidades do Common Data Service agora oferecem suporte a campos personalizados: Detalhe da taxa de cálculo de benefícios, Linha de calendário de trabalho de feriados e Emprego.

### <a name="copy-position-now-includes-payroll-details"></a>A posição de cópia agora inclui detalhes da folha de pagamento
Quando você usa **Copiar posição** e selecionar todas as opções, as informações de detalhes da folha de pagamento são incluídas nas informações da cópia. 

## <a name="in-preview-in-core-hr"></a>Na visualização no Core HR

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Restringir os tipos de licença em solicitações de folga

As organizações podem oferecer muitos tipos diferentes de licenças aos funcionários. Alguns desses tipos de licença podem não ser apropriados para os funcionários enviarem uma folga e são gerenciados pelo departamento de recursos humanos (RH). Com essa versão, você pode configurar em quais tipos de licença os funcionários podem enviar solicitações de folga. 

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nova página para validar dados de hierarquia de posição

RH e administradores podem validar a hierarquia administrativa para quaisquer referências circulares que podem ter sido, inadvertidamente, importadas. Você pode acessar essa nova página em **Administração organizacional > Links > Posições > Validação de hierarquia de posição**.

### <a name="specify-reason-codes-on-leave-types"></a>Especifique códigos de motivo em tipos de licença

As organizações podem precisar de informações adicionais sobre solicitações de folga. Agora você pode especificar os códigos de motivo para os tipos de licença e permitir que os funcionários selecionem um código de motivo em suas solicitações de folga.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Exigir códigos de motivo para específicos tipos de licença em solicitações de folga

As organizações podem exigir códigos de motivo para tipos de licença específicos quando os funcionários enviam solicitações de folga. Essa necessidade pode existir por conta de uma política de empresa ou requisitos regulatórios. Você pode especificar que tipos de licença exigem um código de motivo e pode exigir que os funcionários informem um código de motivo para o tipo de licença em suas solicitações de folga.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fornecer uma lista de transações de licença e de ausência para o RH

A habilidade de rastrear as folgas dos funcionários e entender como elas são calculadas não somente ajuda o RH a responder dúvidas dos funcionários, como também ajuda a garantir que os funcionários recebam prêmios de folga precisos. Agora o RH tem uma nova exibição em transações (subsídios, competências, ajustes e solicitações), para que a equipe do RH possa ver os motivos por trás dos saldos de folgas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]