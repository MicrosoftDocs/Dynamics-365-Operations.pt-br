---
title: A funcionalidade do site de carreiras no Attract
description: "Este artigo fornece uma visão geral da funcionalidade do site de carreiras voltada para o candidato no Microsoft Dynamics 365 for Talent - Attract. Ele também explica como configurar esta funcionalidade."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: pt-br
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a>A funcionalidade do site de carreiras no Attract

[!include [banner](includes/banner.md)]

Este artigo fornece uma visão geral da funcionalidade do site de carreiras voltada para o candidato no Microsoft Dynamics 365 for Talent: Attract. Ele também explica como configurar esta funcionalidade.

## <a name="overview"></a>Visão Geral

O Attract fornece um site de carreiras para cada ambiente em um locatário. Por exemplo, se uma organização tiver um ambiente de desenvolvimento e um ambiente de teste, um site de carreiras será provisionado para o ambiente de desenvolvimento e outro site de carreiras será provisionado para o ambiente de teste. Cada site de carreiras é **totalmente isolado** e tem seu próprio mecanismo de autenticação. Os trabalhos e os perfis do candidato não são compartilhados entre sites de carreiras.

Por padrão, o site de carreiras é público. Portanto, os candidatos podem exibir todos os trabalhos que estão marcados como externos sem precisar fazer logon. Entretanto, todas a outras ações exigem que os candidatos façam logon.

## <a name="career-site-management"></a>Gerenciamento do site de carreiras

Os seguintes itens no site de carreiras são controlados por configurações:

- **Nome da organização:** o nome da organização aparece na barra de navegação na parte superior do site de carreiras. Ao selecionar o nome da organização, os candidatos vão para uma página que lista todos os trabalhos abertos.
- **Logotipo organizacional:** uma imagem do logotipo organizacional aparece na parte superior esquerda do site de carreiras. Ao selecionar a imagem do logotipo, os candidatos vão para uma página que lista todos os trabalhos abertos.

Para definir os valores do nome e do logotipo da organização, entre no Attract como administrador, selecione **Centro de Administração** no menu **Configurações** (o símbolo de engrenagem) e selecione a guia **Informações sobre a empresa**.

> [!NOTE]
> A imagem de logotipo que aparece no site de carreiras tem uma altitude fixa de 20 pixels (px). A imagem que você adiciona no Centro de administração é ajustada. Portanto, dependendo da imagem, a largura pode mudar.

## <a name="career-site-url"></a>URL do site de carreiras

Ao [lançar um trabalho externo](./Creating-jobs-Attract.md#postings) pela primeira vez, você pode copiar o link **Solicitar** da solicitação de emprego do Attract. A URL para esse link estará neste formato: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`

A URL do site de carreiras é uma subcadeia de caracteres da URL **Solicitar**. Ela consiste em tudo até o nome da empresa. Assim, para a URL **Solicitar** precedente, a URL do site de carreiras é `https://jobs.talent.dynamics.com/jobs/<company_name>/`.

## <a name="authentication-options"></a>Opções de autenticação

Os candidatos têm as seguintes opções de logon para um site de carreiras do Attract:

- Conta pessoal:

    - LinkedIn
    - Microsoft
    - Google
    - Facebook

- Conta corporativa ou de estudante:

    - Microsoft Azure Active Directory (Azure AD)

O logon do Azure AD se destina somente a candidatos internos. Portanto, ele só funciona para candidatos internos que usam suas credenciais do Azure AD da empresa. Por exemplo, um candidato que no momento é um funcionário da Contoso Ltd deseja candidatar-se a um trabalho em uma empresa não relacionada, a Alpine Ski House. Nesse caso, o logon será malsucedido se o funcionário tentar usar suas credenciais do Azure AD da Contoso Ltd.

## <a name="create-and-maintain-a-profile"></a>Criar e manter um perfil

Após os candidatos entrarem no site de carreiras, eles podem selecionar **Meu perfil** na barra de navegação na parte superior da página para criar e manter o perfil. O perfil inclui informações pessoais, informações sobre a experiência de trabalho, detalhes de formação educacional, documentos, links e informações sobre os conjuntos de habilidades. Após um perfil ser criado, ele pode ser usado para candidatar-se a posições de interesse do candidato. Os perfis também ajudam o Attract a recomendar os trabalhos certos para candidatos.

## <a name="find-the-right-job"></a>Localize o trabalho certo

Na página de listas de trabalho, os candidatos podem procurar para um trabalho específico inserindo termos da pesquisa. A funcionalidade de pesquisa procura os termos da pesquisa em cargos e descrições de trabalho e mostra os trabalhos relevantes como resultados. Os candidatos podem filtrar os resultados a qualquer momento, com base no local de trabalho ou na função de trabalho.

Os candidatos também podem exibir um conjunto de trabalhos recomendados no site de carreiras. Os trabalhos que são recomendados para um um candidato se baseiam nas solicitações de emprego, nos perfis e nos currículos anteriores do candidato.

> [!NOTE]
> As recomendações de trabalho só serão mostradas se pelo menos 10 trabalhos forem lançados no site de carreiras e se o candidato preencher o perfil.

## <a name="apply-for-jobs"></a>Candidatar-se a empregos

Após os candidatos encontrarem o trabalho certo, eles podem candidatar-se usando o botão **Solicitar** na página de detalhes do trabalho. Nesse ponto, os candidatos podem criar um novo perfil ou revisar as informações do perfil existente. Os candidatos também podem carregar um currículo, conforme necessário, e enviar a solicitação de emprego.

## <a name="check-application-status"></a>Verificar o status da solicitação de emprego

Após os candidatos se candidatarem a um ou mais empregos, eles podem selecionar **Solicitações de emprego** na barra de navegação na parte superior da página para exibir as solicitações de emprego abertas e fechadas. Quando os candidatos abrem uma de suas solicitações de emprego, eles veem o estágio atual e os itens de ação pendentes que precisam concluir. Por exemplo, se um candidato precisar fornecer datas potenciais para uma entrevista pessoal, a página mostrará suas opções.

## <a name="internal-jobs"></a>Cargos internos

No momento, os cargos marcados como internos e lançados no site de carreiras do Attract não aparecem no site de carreiras. Eles só podem ser acessados por meio da URL **Solicitar** direta que pode ser copiada do aplicativo Attract.

