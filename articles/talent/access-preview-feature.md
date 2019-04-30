---
title: Acessar os recursos de visualização no Talent
description: Este tópico descreve como um administrador poderá habilitar os recursos de exibição, e listar os recursos que estão habilitados atualmente para visualização.
author: andreabichsel
manager: AnnBe
ms.date: 04/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2018 update
ms.openlocfilehash: 060a36185641d5bb7912631b7c857c5c4331c8b7
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "856315"
---
# <a name="access-preview-features-in-talent"></a>Acessar os recursos de visualização no Talent

[!include[banner](../includes/banner.md)]

Como parte de liberação contínua de funcionalidades de produto, queremos que nossos clientes aproveitem novos recursos o mais rápido possível. Os administradores podem consultar e usar recursos de exibição nos ambientes. Esses recursos estão quase prontos para disponibilidade geral e passam por um teste extenso. Estamos procurando apenas um círculo final de comentários de cliente e validação antes de lançarmos eles.

Este tópico descreve como um administrador poderá habilitar os recursos de exibição, e listar os recursos que estão disponíveis atualmente para visualização. A lista será atualizada conforme os recursos são liberados para disponibilidade geral e conforme novos recursos são liberados para visualização. Nenhuma notificação é dada quando novos recursos são liberados para visualização. Os usuários começarão a ver apenas os recursos.

## <a name="enable-or-disable-preview-features"></a>Habilitar ou desabilitar recursos de visualização

Você pode usar a configuração **Recursos de Visualização** no centro de administração do Microsoft Dynamics 365 for Talent para habilitar ou desabilitar recursos de visualização. Por padrão, a configuração será desativada. A ação de habilitar ou desabilitar recursos de visualização é específica do ambiente.

> [!IMPORTANT]
> Ao ativar a configuração de **Recursos de visualização**, você habilita recursos de visualização para todos os usuários da organização que estão no ambiente. Ao desativar a configuração, você desabilita recursos de visualização e os torna inacessíveis a seus usuários. Os recursos de visualização limitaram o suporte em Talent. Eles podem usar menos medidas de privacidade e segurança, e elas não estão incluídas no contrato de nível de serviço de Talent. Você não deve usar recursos de visualização para processar dados pessoais (isso é, quaisquer informações que podem identificar você), ou para processar outros dados que estão sujeitos a requisitos de conformidade regulatório.

### <a name="enable-or-disable-preview-features-for-your-organization"></a>Habilitar ou desabilitar recursos de exibição da organização

#### <a name="attract"></a>Atrair

1. Entre no Microsoft Dynamics 365 for Talent: Attract.
2. No menu **Configuração** (símbolo de engrenagem) no canto superior direito, selecione **Configurações de admin**.
3. Na guia **Gerenciamento de recursos**, selecione a opção próxima a **Recursos de visualização** para que se torne azul.
4. Opcionalmente, você pode controlar recursos individuais habilitando/desabilitando recursos específicos nesta página.
5. Atualize seu navegador para começar a exibir os recursos novos. (Quaisquer usuários que já estão conectados verão os recursos na próxima vez que se conectarem, eles podem atualizar o navegador para consultar os recursos imediatamente.)

#### <a name="core-hr"></a>Core HR

1. Entre em Talent. O espaço de trabalho dos recursos humanos abrirá, e nele você concluirá as etapas restantes. 
2. Selecione **Administração de sistema \> Vincular parâmetros de sistema**.
3. Na página **Parâmetros do sistema**, na guia **Recursos de visualização**, defina a opção **Habilitar o modo de visualização para todos os usuários** como **Sim** para tornar os recursos de visualização disponíveis.

> [!NOTE]
> Para desabilitar recursos de visualização, siga as mesmas etapas básicas. Quando você desabilitar recursos de visualização, eles se tornam inacessíveis aos usuários, e os erros podem ocorrer em processos associados com os recursos.

## <a name="features-that-are-currently-in-preview"></a>Características que estão atualmente em exibição

### <a name="attract"></a>Atrair

- **Candidatos relevantes em um trabalho** – os recrutadores e gerentes de contratação podem facilmente ver quais candidatos podem ser os mais relevantes para os trabalhos entre todos os candidatos. Os 5 melhores candidatos são exibidos com base em na relevância de seu currículo/perfil para a descrição do trabalho.
- **Trabalho relevantes** – agora os candidatos veem uma lista dos outros trabalhos relevantes a eles com base em seu currículo/perfil e nas descrições de trabalho.  No momento, isso é exibido para os candidatos depois que eles se candidatam como uma sugestão de outras oportunidades.
- **Suporte a EEO/OFCCP** – os novos tipos de atividade permitem o uso de um formulário predefinido para a coleta de dados de EEO (Oportunidades Iguais de Emprego) e do OFCCP (Office of Federal Contract Compliance Program) do candidato.  Este é um formulário predefinido e não é editável.

    > [!NOTE]
    > Trabalhos que são lançados estão visíveis somente para clientes que assinam um ou vários produtos de emprego do LinkedIn. Caso contrário, os clientes veem um trabalho apenas se eles procurarem explicitamente por ele. Há um atraso quando os trabalhos são postados no LinkedIn. Um trabalho pode levar algumas horas para aparecer depois de ser postado do Attract.

- **Aplicação de candidato** – Os candidatos internos e externos agora podem se candidatar diretamente da página de trabalho no site de carreira.
- **Gerenciamento de oferta** – Os usuários agora podem criar cartas de oferta de modelos que incluam espaços reservados. Conforme os candidatos avançam para o estágio de oferta, os gerentes de recrutadores e contratantes podem usar a ferramenta de oferta para preparar uma oferta formal de candidato por meio de templates, enviar a oferta para aprovação interna, e, finalmente, enviar a oferta para o candidato para assinatura. Muitos recursos novos serão adicionados à ferramenta de oferta ao longo do tempo, e o recurso de exibição será atualizado com essas funcionalidades quando estivermos prontos para o liberar para visualização.

### <a name="core-hr"></a>Core HR

- **Abrir inscrição** – Os benefícios de Abrir inscrição são oferecer aos funcionários uma experiência autodidata para seleção de seus benefícios. Os administradores de recursos humanos (HR) podem definir o processo inicial do registro de benefícios para sua organização, e a experiência de registro de funcionários usando uma solução guiada fácil de entender.

## <a name="feedback"></a>Comentários

Independentemente se os comentários são positivos ou negativos, desejamos saber de você sobre o uso de recursos de exibição. É recomendável postar regularmente seus comentários nos sites a seguir conforme você os usa ou quaisquer outros recursos.

- [Comunidade](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) Este site é um ótimo recurso onde os usuários podem discutir casos de uso, fazer perguntas e obter ajuda da comunidade.
- Use os sites a seguir para sugerir ideias de produto. Conte para nós os recursos que deseja ver no produto, e também quaisquer alterações que você acha que devem ser realizadas aos recursos existentes.

    - [Atrair ideias](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Core HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)

Não inclua dados pessoais (qualquer informação que pode te identificar) em seus comentários ou envios de análise do produto. Informações que são coletadas podem ser analisadas mais profundamente, e elas não serão usadas para atender a solicitações em leis aplicáveis de privacidade. Dados pessoais que são coletados separadamente nestes programas estão sujeitos à [Política de Privacidade online da Microsoft](https://privacy.microsoft.com/privacystatement).

> [!TIP]
> Marque esse tópico e o revise com frequência para se manter atualizado sobre novos lançamentos de recursos conforme os lançamos.
