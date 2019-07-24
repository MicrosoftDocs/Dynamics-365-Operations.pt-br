---
title: Novidades ou alterações no Dynamics 365 for Talent (4 de junho de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0a93ad140fb9116ffb0c486b7f3175f90859f125
ms.sourcegitcommit: 7b5ff31c0a82809641beb681510201b942932c74
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2019
ms.locfileid: "1621853"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-4-2019"></a>Novidades ou alterações no Dynamics 365 for Talent (4 de junho de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

Esta versão inclui correções de bug menores para Dynamics 365 for Talent: Attract.

## <a name="coming-soon-in-attract"></a>Em breve no Attract

### <a name="job-approvals-on-the-home-page"></a>Aprovações de trabalho na página inicial

As aprovações aparecem em uma seção **Aprovações** no painel. Os aprovadores podem analisar suas aprovações em **Atribuído a você**. Esta seção mostra a ID do trabalho, o cargo, outros aprovadores e a data em que o trabalho foi atribuído. Usuários que enviam um trabalho para aprovação podem revisar seus trabalhos em **Solicitado por você**. Esta seção mostra os aprovadores que ainda devem aprovar o trabalho enviado.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para Dynamics 365 for Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2330.

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nova página para validar dados de hierarquia de posição

A equipe de RH e os administradores podem validar a hierarquia gerencial para qualquer referência circular que tenha sido importada inadvertidamente. Você pode acessar esta nova página em **Administração organizacional \> Links \> Posições \> Validação de hierarquia de posição**.

### <a name="specify-reason-codes-on-leave-types"></a>Especifique códigos de motivo em tipos de licença

As organizações podem precisar de informações adicionais sobre solicitações de folga. Agora você pode especificar os códigos de motivo para os tipos de licença e permitir que os funcionários selecionem um código de motivo em suas solicitações de folga.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Exigir códigos de motivo para específicos tipos de licença em solicitações de folga

As organizações podem exigir códigos de motivo para tipos de licença específicos quando os funcionários enviam solicitações de folga. Essa necessidade pode existir por conta de uma política de empresa ou requisitos regulatórios. Você pode especificar que tipos de licença exigem um código de motivo e pode exigir que os funcionários informem um código de motivo para o tipo de licença em suas solicitações de folga.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Fornecer uma lista de transações de licença e de ausência para o RH

A capacidade de rastrear as folgas dos funcionários e entender como elas são calculadas não somente ajuda o RH a responder dúvidas dos funcionários, mas também ajuda a garantir que os funcionários recebam prêmios de folga precisos. Agora o RH tem uma nova exibição em transações (subsídios, competências, ajustes e solicitações), para que a equipe do RH possa ver os motivos por trás dos saldos de folgas.

### <a name="deleting-a-record-from-talent-doesnt-remove-the-record-from-common-data-service"></a>A exclusão de um registro do Talent não remove o registro do Common Data Service

Os registros que foram removidos do Talent Core HR agora também serão removidos do Common Data Service.

### <a name="variable-compensation-plan-valid-fromto-dates-arent-being-honored"></a>O plano de remuneração variável das datas iniciais e finais não está sendo liquidado

Nessa versão, você não poderá inscrever um funcionário em um plano de remuneração variável se a data inicial for anterior à data inicial do plano ou se a data final for posterior à data final do plano. 

### <a name="performance-review-comments-are-removed-when-users-select-cancel"></a>Os comentários de avaliação do desempenho são removidos quando os usuários selecionam Cancelar

Esta versão corrige um problema em que os comentários de revisão são removidos se um usuário começa a alterar um comentário, mas selecione **Cancelar**. 

## <a name="in-preview"></a>Em visualização

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Os recursos de visualização estão habilitados somente em instâncias da área restrita

Quando você provisiona uma nova instância do Talent, pode especificar se o tipo de instância é **Produção** ou **Área restrita**. As instâncias do tipo **Área restrita** permitem testes antecipados de novos recursos. Todas as instâncias do Talent existentes serão atualizadas para o tipo de instância de **Produção**. Se desejar que uma de suas instâncias existentes sejam atualizadas para o tipo de instância **Área restrita**, fale com o [Suporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar a solicitação de alteração.

Para obter mais informações sobre como as alterações são publicadas, consulte [Provisionar o Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Restringir os tipos de licença em solicitações de folga

As organizações podem oferecer muitos tipos diferentes de licenças aos funcionários. Entretanto, talvez não seja apropriado para os funcionários enviar solicitações de folga para alguns tipos de licença. Esses tipos de licença podem ser gerenciadas pelo RH. Nessa versão, você pode configurar para que tipos de licença os funcionários podem enviar solicitações de folga. 

## <a name="coming-soon-in-core-hr"></a>Em breve no Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Exiba informações estendidas de desempenho no autoatendimento de gerente

Uma nova opção permitirá que gerentes exibam o desempenho de seus relatórios diretos e de seus relatórios estendidos. Atualmente, os gerentes de linha podem atribuir e atualizar metas de desempenho e emitir novas revisões, que são cogeridas pelos funcionários. Além disso, os gerentes diretos e seus funcionários podem manter e atualizar diários de desempenho para ajudar a garantir que o processo de avaliação de desempenho corra bem. Quando essa alteração for implementada, gerentes poderão exibir e manter informações de desempenho para seus relatórios estendidos além de seus relatórios diretos. 

### <a name="print-performance-reviews"></a>Imprima avaliações de desempenho

Funcionários, gerentes e RH poderão imprimir a avaliação de desempenho de um funcionário.
