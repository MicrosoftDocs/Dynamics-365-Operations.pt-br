---
title: Acessar os recursos de visualização no Microsoft Dynamics 365 for Talent
description: Este tópico descreve como um administrador poderá habilitar os recursos de exibição no Microsoft Dynamics 365 for Talent e listar os recursos que estão habilitados atualmente para visualização.
author: tracykeya
manager: AnnBe
ms.date: 05/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: 6a5aa8d6ea72ec3d3910edea291c4340ab607326
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739578"
---
# <a name="manage-preview-features"></a>Gerenciar recursos de visualização

[!include[banner](../includes/banner.md)]

Como parte de liberação contínua de funcionalidades de gerenciamento de capital humano (HCM) do Microsoft Dynamics 365 for Talent, queremos que nossos clientes aproveitem novos recursos o mais rápido possível. Os administradores podem consultar e usar recursos de exibição nos ambientes. Esses recursos estão quase prontos para disponibilidade geral e passam por um teste extenso. Estamos procurando apenas um círculo final de comentários de cliente e validação antes de liberá-los para disponibilidade geral.

Este tópico descreve como você poderá habilitar os recursos de exibição, e listar os recursos que estão disponíveis atualmente para visualização. A lista será atualizada conforme os recursos são liberados para disponibilidade geral e conforme novos recursos são liberados para visualização. Nenhuma notificação é dada quando novos recursos são liberados para visualização. Os usuários começarão a ver apenas os recursos. Para obter mais informações sobre novos recursos no Talent, consulte [Novidades ou alterações no Dynamics 365 for Talent](./whats-new.md) e [Notas de versão do Dynamics 365 e da Power Platform](https://docs.microsoft.com/business-applications-release-notes).

## <a name="enable-or-disable-preview-features"></a>Habilitar ou desabilitar recursos de visualização

Para acessar os recursos de visualização, primeiro é preciso ativá-los no ambiente. A habilitação ou desabilitação de recursos de visualização é específica do ambiente.

> [!IMPORTANT]
> Ao ativar a configuração de **Recursos de visualização**, você habilita recursos de visualização para todos os usuários da organização que estão no ambiente. Ao desativar a configuração, você desabilita recursos de visualização e os torna inacessíveis a seus usuários. Os recursos de visualização limitaram o suporte em Talent. Eles podem usar menos medidas de privacidade e segurança, e elas não estão incluídas no contrato de nível de serviço (SLA) de Talent. Você não deve usar recursos de visualização para processar dados pessoais (isso é, quaisquer informações que podem identificar você), ou para processar outros dados que estão sujeitos a requisitos de conformidade regulatório.

### <a name="attract"></a>Atrair

1. Entre no Microsoft Dynamics 365 for Talent: Attract.
2. No menu **Configuração** (símbolo de engrenagem) no canto superior direito, selecione **Centro de administração**.
3. Na guia **Gerenciamento de recursos**, selecione a opção próxima a **Recursos de visualização** para que se torne azul e informe **Ativo**.

    ![Habilitar recursos de visualização no Attract](./media/attract-enable-preview-features.png)

4. Selecione ou cancele a seleção de recursos de visualização individuais. Se você não fizer nada, todos os recursos de visualização disponíveis estarão habilitados.
5. Atualize seu navegador para começar a exibir os recursos novos. Quaisquer usuários que já estão conectados verão os recursos na próxima vez que se conectarem, eles podem atualizar o navegador para consultar os recursos imediatamente.

> [!NOTE]
> Alguns recursos de visualização podem exigir configuração adicional. Siga os links ao lado do recurso de visualização para concluir a configuração dele.

### <a name="core-hr"></a>Core HR

1. Entre em Talent.
2. Selecione **Administração do sistema** e depois selecione a guia **Links**.
3. Na página **Administração do sistema**, em **Configuração**, selecione **Parâmetros do sistema**.
4. Na página **Parâmetros do sistema**, selecione a guia **Recursos de visualização**.
5. Defina a opção **Habilitar o modo de visualização para todos os usuários** como **Sim** para disponibilizar os recursos de visualização.

    ![Habilitar recursos de visualização no Core HR](./media/corehr-enable-preview-features.png)

> [!NOTE]
> Para desativar os recursos de visualização, use as mesmas etapas, mas defina a opção **Habilitar o modo de visualização para todos os usuários** como **Não**. Quando você desabilitar recursos de visualização, eles se tornam inacessíveis aos usuários, e os erros podem ocorrer em processos associados com os recursos.

### <a name="onboard"></a>Integração

Nenhum recurso de visualização está disponível atualmente para o Microsoft Dynamics 365 for Talent: Onboard.

## <a name="features-that-are-currently-in-preview"></a>Características que estão atualmente em exibição

### <a name="attract"></a>Atrair

- [Recomendação de candidato](./intelligent-recommendations.md#candidate-recommendations) – Se houver mais de dez candidatos com currículos ou perfis completos, aqueles que atenderem mais rigorosamente os requisitos de um trabalho aparecerão na seção **Candidatos a considerar** na página do trabalho.
- [Recomendação de trabalho](./intelligent-recommendations.md#job-recommendations) – Se mais de dez trabalhos forem publicados no site de carreiras, o Attract fornecerá recomendações de trabalho para clientes potenciais.
- [Integração do Broadbean](./posting-jobs-external.md#post-jobs-to-broadbean) – É possível lançar trabalhos do Attract para o Broadbean, um site externo de lançamento de trabalhos. Depois de habilitar esse recurso de visualização, você deverá concluir a configuração inserindo seu nome de usuário do Broadbean, ID do cliente e token de criptografia.
- [Análise](./analytic-reports.md) – No Hub de análise, as equipes de contratação podem visualizar as principais métricas de um único trabalho, além de métricas agregadas em todas as tarefas.
- [EEO](./activities-attract.md) – Os novos tipos de atividade permitem que você use um formulário predefinido para coletar dados de EEO (Oportunidades Iguais de Emprego) e do OFCCP (Office of Federal Contract Compliance Program) do candidato. O formulário predefinido não pode ser editado.
- [Recomendação de candidato ao trabalho](./intelligent-recommendations.md#prospect-recommendations) – O Attract analisa candidatos anteriores e candidatos atuais para fornecer uma lista de clientes potenciais que são uma boa correspondência para o seu trabalho.
- [Pesquisa de relevância](./attract-talent-pools.md#search-and-view-candidate-profiles) – Você pode pesquisar toda a sua base de dados de candidatos para habilidades específicas, nomes ou formações educacionais. O Attract pesquisa o perfil inteiro e realça todas as correspondências encontradas. O Attract também pesquisa todos os documentos disponíveis de um candidato e classifica os resultados da pesquisa de maneira inteligente.
- [Público-alvo da atividade](./whats-new-talent-march-20.md#setting-the-audience-on-activities) – Você pode definir o público-alvo de atividades (como Entrevista, Agenda ou Comentários) como **Todos os candidatos**, **Candidatos internos** ou **Candidatos externos**. Você pode fornecer atividades do cliente, como vídeos do YouTube, conteúdo da Web e formulários da Microsoft, a todos os candidatos, a apenas candidatos internos, a apenas candidatos externos ou à equipe de contratação.
- [Candidatar-se com o LinkedIn](./career-site.md#enable-applying-for-jobs-with-linkedin-profiles) – Você pode configurar uma opção em seu site de carreiras do Attract para permitir que os candidatos se inscrevam usando o LinkedIn. Esse recurso simplifica o processo de solicitação de emprego para seus candidatos, permitindo que eles usem o perfil do LinkedIn para preencher automaticamente as solicitações de emprego no seu site de carreiras.
- [Rastreamento da origem](./source-tracking.md) – O Attract rastreia a origem das solicitações de emprego dos candidatos para fornecer informações valiosas que podem ajudar a direcionar seus esforços de recrutamento. Você também pode selecionar uma origem de solicitações de emprego ao adicionar um candidato a um emprego ou a um grupo de talentos.
- [Medalhista de prata](./whats-new-talent-march-20.md#designate-silver-medalists-to-assign-high-value-applicants-for-future-positions) – Se algum candidato for uma boa opção para a sua organização, mas você não estendeu uma oferta a ele para sua posição atual, você pode designá-lo como medalhista de prata. Esse recurso ajuda a reduzir seu tempo de contratação na próxima vez que você tiver uma posição semelhante disponível.

### <a name="core-hr"></a>Core HR

- [Validar dados de hierarquia de posição](./whats-new-talent-may-13-2019.md#new-page-to-validate-position-hierarchy-data) – Você pode validar a hierarquia administrativa de quaisquer referências circulares que foram importadas inadvertidamente.
- [Especificar códigos de motivo em tipos de licença](./whats-new-talent-may-13-2019.md#specify-reason-codes-on-leave-types) – Você pode especificar códigos de motivo em tipos de licença.
- [Exigir códigos de motivo em solicitações de folga](./whats-new-talent-may-13-2019.md#require-reason-codes-for-specific-leave-types-on-time-off-requests) – Além de especificar códigos de motivo em tipos de licença, você pode exigir códigos de motivo para solicitações de folga.
- [Fornecer uma lista de transações de licença e de ausência para o RH](./whats-new-talent-may-13-2019.md#provide-a-leave-and-absence-transaction-list-for-hr) – Você pode visualizar uma lista de transações de licença e ausência para ajudar a fornecer informações sobre os saldos de folgas.

### <a name="onboard"></a>Integração

Nenhum recurso de visualização está disponível atualmente para o Onboard.

## <a name="feedback"></a>Comentários

Queremos saber sua experiência com qualquer um desses recursos de visualização. É recomendável postar regularmente seus comentários nos sites a seguir conforme você os usa ou quaisquer outros recursos:

- [Comunidade](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) Este site é um ótimo recurso onde os usuários podem discutir casos de uso, fazer perguntas e obter ajuda da comunidade.
- Conte para nós os recursos que você deseja ver no produto ou as alterações que você acha que devemos fazer nos recursos existentes. Sugira ideias de produtos nos seguintes sites:

    - [Ideias do Attract](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Ideias do Core HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    - [Ideias do Onboard](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

Não deixe de incluir dados pessoais (qualquer informação que pode te identificar) em seus comentários ou envios de análise do produto. Informações coletadas podem ser analisadas mais profundamente, e elas não serão usadas para atender a solicitações em leis aplicáveis de privacidade. Dados pessoais que são coletados separadamente nestes programas estão sujeitos à [Política de Privacidade online da Microsoft](https://privacy.microsoft.com/privacystatement).

> [!TIP]
> Marque esse tópico e o revise com frequência para se manter atualizado sobre novos lançamentos de recursos conforme os lançamos.

## <a name="see-also"></a>Consulte também

- [Experimente ou compre aplicativos do Talent](https://dynamics.microsoft.com/talent/overview/)
- [Novidades](./whats-new.md)
- [Notas de versão](https://docs.microsoft.com/business-applications-release-notes/index)
- [Obter suporte para o Talent](./talent-support.md)
