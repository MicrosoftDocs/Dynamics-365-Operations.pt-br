---
title: Novidades ou alterações no Dynamics 365 for Talent (20 de março de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/20/2019
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
ms.search.validFrom: 2019-03-20
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d69294b64c841c5486d694b129cf6c0f26fd93fd
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517346"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-20-2019"></a>Novidades ou alterações no Dynamics 365 for Talent (20 de março de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="setting-the-audience-on-activities"></a>Definindo o público em atividades
As atividades no sistema agora podem ter o público definido. As atividades relacionadas a processos (como Entrevista, Agendamento, Comentários e EEO) podem ser definidas para Todos os candidatos, Candidatos internos e Candidatos externos. As atividades personalizadas, como Microsoft Forms, vídeos do YouTube e conteúdo da Web podem ser fornecidas a Todos os candidatos, Candidatos internos, Candidatos externos ou a equipe de contratação.  

### <a name="improve-career-site-job-discoverability-search-engine-optimization"></a>Aprimore a capacidade de descoberta de trabalhos do local: otimização do mecanismo de pesquisa
Este recurso permite que os rastreadores alcancem e indexem posições de trabalho no site de carreiras do Attract. Isso ajuda os candidatos a encontrar os trabalhos lançados no site de carreiras do Attract usando os mecanismos de pesquisa conhecidos.

### <a name="show-login-hint-to-candidates-who-forgot-their-credentials"></a>Mostrar a dica de logon para os candidatos que esqueceram suas credenciais
Se um candidato esquecer as credenciais sociais que usaram para se candidatar a um trabalho enquanto estiver abrindo um link que foi salvo ou enviado por email a ele, o candidato poderá ver uma dica com o nome do provedor e o nome de usuário (ofuscados). Isso ajuda-o a usar as credenciais corretas para acessar candidatura ao trabalho.

### <a name="help-internal-candidates-explore-internal-jobs"></a>Ajudar candidatos internos a explorar trabalhos internos
Foi corrigido um problema onde candidatos externos poderiam consultar o nome do recrutador ou gerente de contratação de um trabalho. Agora somente os candidatos internos podem ver os membros da equipe de contratação para um trabalho. Agora também ficou mais fácil para candidatos internos verem e candidatarem-se apenas aos cargos internos. Quando um candidato tentar acessar o link para ver ou candidatar-se apenas a um trabalho interno, ele será forçado a autenticar-se com as credenciais do Azure Active Directory. Os candidatos internos também têm capacidade de contatar o membro da equipe de contratação para expressar interesse ou saber mais sobre o trabalho. Essa funcionalidade está disponível para todos os trabalhos apenas para candidatos internos. Para obter mais informações, consulte [A funcionalidade do site de carreiras no Attract](./career-site.md).

### <a name="designate-silver-medalists-to-assign-high-value-applicants-for-future-positions"></a>Designar medalhistas de prata para atribuir candidatos de alto valor para posições futuras
Os recrutadores e os gerentes de contratação frequentemente mantêm uma lista atualizada de candidatos aptos para uma posição que não puderam receber uma oferta, pois a posição já tinha sido preenchida. Esses candidatos, chamados de medalhistas de prata, são valiosos, pois eles ajudam a reduzir o tempo de contratação quando uma posição semelhante é aberta. O Attract agora permite que os recrutadores e os gerentes de contratação designem esses medalhistas de prata à lista de candidatos se um candidato passar ao estágio de Oferta. A designação de medalhista de prata aparecerá na lista de candidatos para o trabalho, mas também na exibição de grupo de talentos quando esses candidatos forem membros de grupos do gerente de contratação ou recrutador. Adicionalmente, a designação aparecerá no histórico de trabalhos como parte do perfil de grupo de talentos de um candidato. Você pode visualizar esse recurso quando um administrador ativá-lo usando o [Gerenciamento de recursos no centro de administração](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="add-applicants-to-talent-pools"></a>Adicionar candidatos aos grupos de talentos
Agora é fácil adicionar candidatos aos grupos de talentos por meio da exibição de uma nova ação na lista dos candidatos. Selecionando o ícone **Adicionar ao grupo de talentos** , o recrutador ou gerente de contratação pode escolher na lista de grupos de talentos e adicionar facilmente os candidatos aos grupos de talentos direto da lista de candidatos a um trabalho.

### <a name="configure-whether-a-resume-is-required-to-apply-for-a-particular-job"></a>Configurar se um currículo será necessário ou não para se candidatar a um trabalho específico
Com base em comentários de clientes, os recrutadores agora podem configurar se um currículo, na forma de um arquivo carregado, é necessário ou não para se candidatar a um trabalho específico. Essa configuração é parte da atividade da candidatura, disponível no processo de contratação. Quando habilitada, todos os candidatos potenciais receberão uma solicitação para carregar um currículo quando se candidatarem a uma posição. A candidatura não será considerada completa a menos que um currículo seja carregado. Isso ajuda a reduzir o ruído no grupo de candidatos garantindo que todos os candidatos forneçam informações suficientes para permitir que o recrutador faça a triagem deles.

### <a name="candidates-can-apply-to-a-job-using-their-linkedin-profile"></a>Os candidatos podem se candidatar a um trabalho usando o perfil do LinkedIn
Os candidatos que já possuem o perfil atualizado no LinkedIn podem se candidatar a trabalhos apenas com um único clique usando esse perfil.

### <a name="track-how-a-candidate-profile-originated-in-the-system-and-where-your-applicants-discover-the-jobs-they-applied-for"></a>Rastrear como um perfil de candidato foi originado no sistema e onde os candidatos descobrem trabalhos para os quais eles se candidatam
Agora você pode descobrir um perfil de um candidato específico originado no Attract olhando a origem do perfil nos detalhes do candidato na página **Perfil** de um perfil do grupo de talentos ou candidato. De forma semelhante, você pode descobrir quantos candidatos descobriram o trabalho olhando na origem do candidato fornecida em **Atividade do candidato** no feed de atividades do candidato. Essas informações também estão disponíveis no histórico do trabalho no perfil do grupo de talentos. Quando os recrutadores ou gerentes de contratação adicionam candidatos manualmente, eles recebem uma solicitação para designar a origem do perfil dos candidatos. Quando um candidato se candidata pela primeira vez, a origem do perfil é a mesma da origem da candidatura. Você pode visualizar esse recurso quando um administrador ativá-lo usando o [Gerenciamento de recursos no centro de administração](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature). Observe que candidatos existentes e futuros candidatos não terão nenhuma informações de origem. Entretanto, os recrutadores podem adicionar essas informações manualmente.

## <a name="changes-in-onboard"></a>Alterações de Integração

Esta versão inclui correções de bug menores para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR

Alterações descritas nesta seção aplicam-se à versão número 8.1.2195

### <a name="attract-integration-throws-duplicate-record-error-for-applications"></a>A integração do Attract gera erros de registro duplicado para os candidatos
Na atualização, um problema com os registros duplicados foi corrigido. Essa saída aparece quando abre-se o espaço de trabalho **Gerenciamento de pessoal** .

### <a name="unable-to-close-form-when-editing-name-sequence"></a>Não é possível fechar o formulário ao editar-se a sequência de nome
Foram feitas alterações para corrigir um problema ao editar-se a sequência de nome no formulário do trabalhador.

## <a name="coming-soon"></a>Em breve

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Segurança de compensação avançada (fixa e variável)
Em muitas organizações, os gerentes de remuneração e benefícios só podem ter acesso a alguns tipos de registro de remuneração. Esses registros podem ser para funcionários executivos ou regionais. Com esta alteração, o RH pode gerenciar e manter os planos de remuneração para grupos de funcionários diferentes na organização. Você pode atribuir funções de segurança para planos fixos e variáveis que determinem o acesso a planos e dados de funcionário relacionados aos planos, como registros de bônus ou salário. Apenas as funções com o acesso permitido podem processar a remuneração desses funcionários.

###  <a name="email-support-for-alerts"></a>Suporte de email para alertas
Com o Platform update 24, os usuários podem criar regras de alerta que enviam automaticamente notificações por email a contatos quando enviadas para um evento.

### <a name="duplicate-employee-check-interface-changes"></a>Verificações de funcionários duplicados: alterações da interface
Com esta alteração, as duplicatas são detectadas conforme você digita nos campos de nome, e um status exibe o número de duplicatas localizado. Você pode selecionar o link fornecido para abrir uma nova página a fim de avaliar se deve usar ou não a correspondência detectada. As duplicatas não são abertas automaticamente para evitar a interrupção da entrada de dados.


