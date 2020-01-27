---
title: Novidades ou alterações no Dynamics 365 Talent (23 de abril de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/23/2019
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
ms.search.validFrom: 2019-04-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: cbafea9063844dd3f19e5828ab37632e04591f18
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897874"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-23-2019"></a>Novidades ou alterações no Dynamics 365 Talent (23 de abril de 2019)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract
Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Alterações de Integração
Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR
As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2253. Números entre parênteses referem-se a números no Lifecycle Services (LCS).

### <a name="common-data-service-entity-support-for-custom-fields"></a>A entidade Common Data Service oferece suporte a campos personalizados
Com a versão desta semana, as entidades a seguir oferecem suporte a campos personalizados: nível de compensação, opção de benefício, tipo de habilidade e região de compensação.

### <a name="additional-odata-entities-302992"></a>Entidades OData adicionais (302992)
As entidades a seguir agora são compatíveis dentro do OData: experiência profissional do trabalhador e educação do trabalhador.
   
### <a name="performance-journal-attachments-for-managers-and-employees-308248"></a>Anexos do diário de desempenho para gerentes e funcionários (308248)
Com essa versão, os anexos agora estão disponíveis para gerentes e funcionários ao criar e atualizar entradas de diário de desempenho.

### <a name="employee-rehire-flag-always-available-310047"></a>Sinalizador de recontratação de funcionário sempre disponível (310047)
A opção de recontratação de funcionário agora está disponível para atualização fora do processo de demissão. 

### <a name="cannot-change-the-name-of-my-payment-method-308815"></a>Não foi possível alterar o nome do **Meu método de pagamento** (308815)
A personalização foi habilitada para permitir que o rótulo **Meu método de pagamento** seja alterado em Autoatendimento para funcionários.

### <a name="financial-dimensions-against-a-position-cant-be-deleted-293908"></a>Dimensões financeiras em uma posição não podem ser excluídas (293908)
Dimensões financeiras agora podem se removidas ao solicitar uma alteração de uma vaga existente e dos limites entre a empresa de dimensões financeiras. 

### <a name="customer-is-unable-to-publish-back-data-into-talent-when-opening-the-data-from-excel-302955"></a>O cliente não consegue publicar dados de volta ao Talent ao abrir os dados do Excel (302955)
Esta alteração corrige um problema de publicação ao usar tabelas relacionadas.

## <a name="in-preview"></a>Em visualização

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Permitir que os códigos de motivo sejam especificados nos tipos de licença
As organizações podem precisar de informações adicionais sobre solicitações de folga. Agora você pode especificar os códigos de motivo para os tipos de licença e permitir que os funcionários selecionem um código de motivo em suas solicitações de folga.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Exigir códigos de motivo para determinados tipos de licença em solicitações de folga
As organizações podem exigir códigos de motivo para tipos de licença específicos quando os funcionários enviam pedidos de folga. Isso pode ser devido a uma diretiva da empresa ou a requisitos regulatórios. Agora você pode especificar que tipos de licença exigem um código de motivo e pode exigir que os funcionários informem um código de motivo para o tipo de licença em suas solicitações de folga.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Fornecer a lista de transações de licença e de ausência para o RH
Monitorar as folgas dos funcionários e entender como elas são calculadas não somente ajuda o RH a responder dúvidas dos funcionários, como também garante que os funcionários recebam prêmios de folga precisos. Agora o RH tem uma nova exibição em transações (subsídios, competências, ajustes e solicitações) para considerar os motivos por trás dos saldos.

## <a name="coming-soon"></a>Em breve

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Melhorias na interface de usuário para verificação de funcionários duplicados
Com esta alteração, as duplicatas são detectadas conforme você digita nos campos de nome, e um status exibe o número de duplicatas localizado. Você pode selecionar o link fornecido para abrir uma nova página a fim de avaliar se deve usar ou não a correspondência detectada. Para evitar a interrupção da entrada de dados, as duplicatas não são abertas automaticamente.
## <a name="known-issues"></a>​Problemas conhecidos​

### <a name="email-support-for-alerts"></a>Suporte de email para alertas
Com a atualização de plataforma 26 do Finance and Operations, os usuários podem criar regras de alerta que enviem automaticamente notificações por email a contatos quando notificações são disparadas por um evento.
