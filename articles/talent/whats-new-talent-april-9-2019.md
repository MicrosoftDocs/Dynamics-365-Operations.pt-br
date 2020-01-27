---
title: Novidades ou alterações no Dynamics 365 Talent (9 de abril de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/09/2019
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
ms.search.validFrom: 2019-04-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0a4d4de6cf28e24d1265395d6440df85edf71a0d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897847"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-9-2019"></a>Novidades ou alterações no Dynamics 365 Talent (9 de abril de 2019)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integração do Lifecycle Services (LCS) com ¨Relatar um Problema¨
No Attract e no Onboard, os problemas registrados por usuários finais usando o recurso Relatar um Problema agora criam problemas de suporte automaticamente no projeto do LCS do cliente. Assim os administradores podem fazer a triagem dos problemas e enviá-los à Microsoft quando necessário. Isso é consistente com a forma como o Core HR lida com problemas de suporte do usuário final.

### <a name="relevance-search"></a>Pesquisa de relevância
Em conjuntos de talentos, agora você pode consultar o banco de dados de candidatos inteiro para verificar habilidades específicas, nomes ou a formação educacional. Não é mais preciso especificar qual seção do perfil de um candidato que você quer procurar. O Attract pesquisa o perfil inteiro e realça todas as correspondências encontradas. O Attract também pesquisa todos os documentos disponíveis de um candidato e classifica os resultados da pesquisa de maneira inteligente. Além disso, você pode filtrar os resultados por origem ou se é um de medalhista de prata. Para obter mais informações, consulte [Pesquisar e exibir perfis do candidato](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-talent-pools#search-and-view-candidate-profiles).

### <a name="prospect-recommendations"></a>Recomendação de candidato ao trabalho
O Attract pode ajudar a impulsionar o processo de fornecimento de um trabalho assim que você ativá-lo fazendo recomendações inteligentes com base no banco de dados de candidatos da organização. As recomendações incluem habilidades e informações de formação educacional identificadas ao procurar clientes potenciais relevantes. Essas recomendações serão exibidas na guia **Clientes potenciais** em um trabalho se você habilitá-la durante o processo de contratação. Para obter mais informações, consulte [Recomendações inteligentes](https://docs.microsoft.com/dynamics365/unified-operations/talent/intelligent-recommendations#prospect-recommendations).

### <a name="interviewer-availability-statuses"></a>Status de disponibilidade do entrevistador
Os agendadores de entrevistas em breve poderão exibir o status **Ausência Temporária, trabalhando de outro local** dos entrevistadores, o que ajudará a agendar horários mais adequados para estes.

### <a name="candidate-interview-experience-save-calendar-invites"></a>Experiência de entrevista do candidato: Salvar convites do calendário
Agora os candidatos podem baixar e salvar eventos de entrevista em seus calendários pessoais usando um arquivo .ics anexado ao email de resumo da entrevista enviado para o candidato.

## <a name="changes-in-onboard"></a>Alterações de Integração

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integração do Lifecycle Services (LCS) com Relatar um Problema
No Attract e no Onboard, os problemas registrados por usuários finais usando o recurso Relatar um Problema agora criam problemas de suporte automaticamente no projeto do LCS do cliente. Assim os administradores podem fazer a triagem dos problemas e enviá-los à Microsoft quando necessário. Isso é consistente com a forma como o Core HR lida com problemas de suporte do usuário final.

## <a name="changes-in-core-hr"></a>Alterações no Core HR
As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2225.

### <a name="percent-of-basis-variable-plans-load-incorrect-amount"></a>A porcentagem de planos variáveis básicos carrega valores incorretos
A versão da semana corrige um problema ao carregar prêmios de remuneração variável usando a porcentagem de planos básicos.
 
### <a name="date-picker-on-last-day-worked-doesnt-work-correctly"></a>O seletor de datas em Último dia de trabalho não funciona corretamente
Esta alteração corrige o seguinte problema: Quando os usuários editam **Data final do emprego** e selecionam a data usando o controle de calendário, um dia é adicionado à seleção.

###  <a name="limit-personnel-action-types-by-the-action-taken"></a>Limitar tipos de ação de pessoal pela ação executada
Esta alteração limita os tipos de ação que são exibidas ao executar ações específicas. Por exemplo, quando um novo cargo é solicitado, apenas as ações do novo cargo são exibidas na lista de ações para selecionar. Anteriormente eram exibidas as ações novas e de edição. 

### <a name="transferring-an-employee-with-compensation-in-a-second-legal-entity"></a>Transferir um funcionário com remuneração em uma segunda entidade legal
Esta versão permite que a remuneração seja encerrada em uma segunda entidade legal se a transferência é para uma transferência entre empresas.

### <a name="unable-to-select-compensation-for-a-future-employment-during-a-transfer"></a>Não é possível selecionar remuneração para um emprego futuro durante uma transferência
Ao transferir um funcionário para uma nova entidade legal, agora você pode definir a remuneração para a nova entidade legal durante o processo de transferência.

### <a name="user-isnt-able-to-assign-compensation-during-position-assignment"></a>O usuário não pode atribuir remuneração durante a atribuição da posição
Agora adicionar uma nova atribuição de posição permite configurar registros de remuneração fixa. 

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

###  <a name="email-support-for-alerts"></a>Suporte de email para alertas
Com a atualização de plataforma 25 do Finance and Operations, os usuários podem criar regras de alerta que enviem automaticamente notificações por email a contatos quando notificações são disparadas por um evento. 
