---
title: "Acessar os recursos de visualização no Dynamics 365 for Talent"
description: "Este tópico descreve como um administrador poderá habilitar os recursos de exibição, e listar os recursos que estão habilitados atualmente para visualização."
author: rschloma
manager: AnnBe
ms.date: 04/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.translationtype: HT
ms.sourcegitcommit: 2e5dd8f852ac1a6c2997a50a60f03db6adfd218c
ms.openlocfilehash: 5500bfc1cdd1949d301ae82fad5506dfdbeb59f3
ms.contentlocale: pt-br
ms.lasthandoff: 05/01/2018

---

# <a name="access-preview-features-in-dynamics-365-for-talent"></a>Acessar os recursos de visualização no Dynamics 365 for Talent 

[!include[banner](../includes/banner.md)]

Como parte de liberação contínua de funcionalidades de produto, queremos que nossos clientes aproveitem novos recursos o mais rápido possível. Os administradores podem consultar e usar recursos de exibição nos ambientes. Esses recursos estão quase prontos para disponibilidade geral e passam por um teste extenso. Estamos procurando apenas um círculo final de comentários de cliente e validação antes de lançarmos eles.

Este tópico descreve como um administrador poderá habilitar os recursos de exibição, e listar os recursos que estão disponíveis atualmente para visualização. A lista será atualizada conforme os recursos são liberados para disponibilidade geral e conforme novos recursos são liberados para visualização. Nenhuma notificação é dada quando novos recursos são liberados para visualização. Os usuários começarão a ver apenas os recursos.

## <a name="enable-or-disable-preview-features"></a>Habilitar ou desabilitar recursos de visualização

Você pode usar a configuração **Visualizar recursos** no Microsoft Dynamics 365 do centro de admin de Talent para Habilitar ou Desabilitar recursos de exibição. Por padrão, a configuração será desativada. A ação de habilitar ou desabilitar recursos de visualização é específica do ambiente.

> [!IMPORTANT]
> Ao ativar a configuração de **Recursos de visualização**, você habilita recursos de visualização para todos os usuários da organização que estão no ambiente. Ao desativar a configuração, você desabilita recursos de visualização e os torna inacessíveis a seus usuários. Os recursos de visualização limitaram o suporte em Talent. Eles podem usar menos medidas de privacidade e segurança, e elas não estão incluídas no contrato de nível de serviço de Talent. Você não deve usar recursos de visualização para processar dados pessoais (isso é, quaisquer informações que podem identificar você), ou para processar outros dados que estão sujeitos a requisitos de conformidade regulatório.

### <a name="enable-or-disable-preview-features-for-your-organization"></a>Habilitar ou desabilitar recursos de exibição da organização

#### <a name="attract"></a>Attract

1. Entre no Microsoft Dynamics 365 for Talent: Attract.
2. No menu **Configuração** (símbolo de engrenagem) no canto superior direito, selecione **Configurações de admin**.
3. Na guia **Gerenciamento de recursos**, selecione a opção próxima a **Recursos de visualização** para que se torne azul.
4. Atualize seu navegador para começar a exibir os recursos novos. (Quaisquer usuários que já estão conectados verão os recursos na próxima vez que se conectarem, eles podem atualizar o navegador para consultar os recursos imediatamente.)

#### <a name="core-hr"></a>Core HR

1. Entre em Talent. O espaço de trabalho dos recursos humanos abrirá, e nele você concluirá as etapas restantes. 
2. Selecione **Administração de sistema \> Vincular parâmetros de sistema**.
3. Na página **Parâmetros do sistema**, na guia **Recursos de visualização**, defina a opção **Habilitar o modo de visualização para todos os usuários** como **Sim** para tornar os recursos de visualização disponíveis.

> [!NOTE]
> Para desabilitar recursos de visualização, siga as mesmas etapas básicas. Quando você desabilitar recursos de visualização, eles se tornam inacessíveis aos usuários, e os erros podem ocorrer em processos associados com os recursos.

## <a name="features-that-are-currently-in-preview"></a>Características que estão atualmente em exibição

### <a name="attract"></a>Attract

- **Modelos de trabalho** – Agora você pode criar modelos de contratação de processo. Os usuários já podem personalizar o processo de contratação para determinado cargo. No entanto, agora eles podem criar modelos para o processo e selecionar o modelo apropriado quando um trabalho específico é criado. Portanto, este recurso ajuda a aerodinâmica do processo de configuração de trabalho.
- **Site de carreira** – A versão atual do site de carreira apenas lista todas as posições abertas. Entretanto, mais recursos serão adicionados ao site no futuro. Trabalhos podem ser marcados como internos ou externos. Os usuários internos que se conectam ao site verão trabalhos internos e externos. Entretanto, usuários que não forem interno e usuário que não estiverem logados verão apenas trabalhos externos.
- **Anúncio de emprego** – Agora você pode postar empregos no site de carreira.
- **Postagem de trabalho no LinkedIn** – Agora você pode postar empregos no LinkedIn.

    > [!NOTE]
    > Trabalhos que são lançados estão visíveis somente para clientes que assinam um ou vários produtos de emprego do LinkedIn. Caso contrário, os clientes veem um trabalho apenas se eles procurarem explicitamente por ele. Há um atraso quando os trabalhos são postados no LinkedIn. Um trabalho pode levar algumas horas para aparecer depois de ser postado do Attract.

- **Aplicação de candidato** – Os candidatos internos e externos agora podem se candidatar diretamente da página de trabalho no site de carreira.
- **Avaliações** – Como parte do processo de contratação configurável, seja para um trabalho específico ou quando um modelo de trabalho é utilizado, agora usuários têm acesso a um novo tipo da atividade **Avaliação**. Eles podem usar o projeto: aplicativo "Gauge" no Talent para criar avaliações básicas que eles podem enviar aos candidatos. Projeto: "Gauge" também está em visualização pública. Os provedores adicionais serão adicionados no futuro.
- **Projeto: "Gauge"** – Projeto: "Gauge" em um aplicativo em Talent que permite que os usuários criam avaliações simples ou pesquisas.
- **Gerenciamento de oferta** – Os usuários agora podem criar cartas de oferta de modelos que incluam espaços reservados. Conforme os candidatos avançam para o estágio de oferta, os gerentes de recrutadores e contratantes podem usar a ferramenta de oferta para preparar uma oferta formal de candidato por meio de templates, enviar a oferta para aprovação interna, e, finalmente, enviar a oferta para o candidato para assinatura. Muitos recursos novos serão adicionados à ferramenta de oferta ao longo do tempo, e o recurso de exibição será atualizado com essas funcionalidades quando estivermos prontos para o liberar para visualização.

### <a name="core-hr"></a>Core HR

- **Abrir inscrição** – Os benefícios de Abrir inscrição são oferecer aos funcionários uma experiência autodidata para seleção de seus benefícios. Os administradores de recursos humanos (HR) podem definir o processo inicial do registro de benefícios para sua organização, e a experiência de registro de funcionários usando uma solução guiada fácil de entender.

## <a name="feedback"></a>Comentários

Independentemente se os comentários são positivos ou negativos, desejamos saber de você sobre o uso de recursos de exibição. É recomendável postar regularmente seus comentários nos sites a seguir conforme você os usa ou quaisquer outros recursos.

- [Comunidade](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) Este site é um ótimo recurso onde os usuários podem discutir casos de uso, fazer perguntas e obter ajuda da comunidade.
- Use os sites a seguir para sugerir ideias de produto. Conte para nós os recursos que deseja ver no produto, e também quaisquer alterações que você acha que devem ser realizadas aos recursos existentes.

    - [Atrair ideias](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Core HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)

Não inclua dados pessoais (qualquer informação que pode te identificar) em seus comentários ou envios de análise do produto. Informações que são coletadas podem ser analisadas mais profundamente, e elas não serão usadas para atender a solicitações em leis aplicáveis de privacidade. Dados pessoais que são coletados separadamente nestes programas estão sujeitos à [Política de Privacidade online da Microsoft](https://privacy.microsoft.com/en-us/privacystatement).

> [!TIP]
> Marque esse tópico e o revise com frequência para se manter atualizado sobre novos lançamentos de recursos conforme os lançamos.
