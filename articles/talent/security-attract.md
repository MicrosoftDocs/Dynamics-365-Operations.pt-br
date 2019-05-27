---
title: Gerenciamento de segurança e funções no Attract
description: Este tópico fornece informações sobre a função de segurança no Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 03/08/2019
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
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 9c0f9d3304b1b15aa84fd1a296267d606bf9c59d
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517330"
---
# <a name="security-and-role-management-in-attract"></a>Gerenciamento de segurança e funções no Attract

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Talent: Attract usa segurança baseada em função. Em outras palavras, o acesso não é oferecido a usuários individuais, mas às funções de segurança que os usuários usam. Um usuário atribuído a uma função de segurança tem acesso ao conjunto do privilégio associado a essa função.

Attract fornece cinco funções de usuário básicas:

- Administrador
- Gerente de Contratação
- Recrutador
- Entrevistador
- Somente leitura

A função Administrador é a única função que tem permissão para adicionar outros usuários e modificar as permissões.

- **Adicionar** – Em centros de administração, na guia **Permissões de usuário** , selecione **Atribuição de funções**, pesquise pelo usuário a ser adicionado e depois atribua permissões a esse usuário.
- **Editar** – Procure o usuário, ou encontre o usuário na lista, e selecione **Editar** para mudar suas permissões.
- **Excluir** – Se você excluir as permissões de um usuário, você não remove o usuário do sistema. Entretanto, você delimita o acesso do usuário e privilégios no Attract. Por exemplo, Hilda foi atribuída à função de gerente de contratação, e ela está adicionada a um trabalho como um gerente de contratação. Se Hilda for removida posteriormente de uma função de gerente de contratação, ela permanece uma gerente de contratação no trabalho e ainda tem acesso a esse trabalho. Entretanto, ela não pode criar outros trabalhos.

As seções a seguir fornecem uma descrição de alto nível de cada função. As tabelas mais para frente no tópico fornecem informações mais detalhadas.

> [!NOTE]
> Alguns recursos estão disponíveis apenas com o suplemento de contratação abrangente do Attract.

## <a name="administrator"></a>Administrador

Os usuários atribuídos à função de Administrador podem acessar e alterar todos os dados no Attract. Os administradores podem criar, ler, excluir e atualizar dados. Também têm acesso ao centro admin, onde pode configurar o solicitação de emprego do Attract e configurar informações do usuário. Recomendamos que pelo menos um indivíduo seja atribuído à função Administrador. Por padrão, o ambiente de admin no Microsoft PowerApps é definido como um admin no Attract. Caso você se inscreveu para a versão de avaliação do Attract, a função de Administrador será atribuída automaticamente. Atualmente, para criar trabalhos, os usuários com a função de Administrador também devem ter a função de recrutamento ou a função de gerente de projeto.

## <a name="hiring-manager"></a>Gerente de Contratação

Os usuários atribuídos à função de gerente de projeto podem criar trabalhos e o trabalho de atualização criado anteriormente. Os gerentes de projeto podem realizar apenas um conjunto limitado de ações em um trabalho e nas aplicações que são associadas com esse trabalho. Somente os usuários atribuídos à função de gerente de contratação podem ser adicionados a uma equipe de contratação como gerentes de contratação.

## <a name="recruiter-role"></a>Função do recrutador

Os usuários atribuídos à função de recrutamento têm privilégios completos de leitura, criação, atualização e exclusão dos trabalhos para os trabalhos que criaram. Eles também privilégios completos de criação, leitura, atualização e exclusão para as aplicações que estão associadas com trabalhos que possuem. Somente os usuários atribuídos à função de recrutador podem ser adicionados a uma equipe de contratação como recrutadores.

## <a name="interviewer"></a>Entrevistador

Qualquer usuário que tenha uma conta do Microsoft Azure Active Directory (Azure AD) na organização pode ser adicionado a uma equipe de contratação como um entrevistador. Os usuários atribuídos à função de entrevistador podem exibir os detalhes do trabalho e os dados do candidato para trabalhos que estejam na equipe de contratação. Para esses trabalhos, os entrevistadores também podem fazer recomendações de contratação e fornecer comentários sobre candidatos. Entretanto, eles não podem atualizar detalhes de trabalho ou dados do candidato.

## <a name="read-only"></a>Somente leitura

Os usuários atribuídos à função somente leitura têm acesso somente leitura a todos os dados no ambiente do Attract. Entretanto, eles não podem criar ou editar os dados.

## <a name="find-out-which-roles-you-have"></a>Descubra quais funções você tem

1.  No Attract, clique no ponto de interrogação (**?**) no canto superior direito da página.

2.  Clique em **Sobre**.

    Você verá quais funções tem no Attract na janela exibida:

    ![Exibir seu tipo de licença do Attract](media/attract-license-types.png)
    
## <a name="delegated-roles"></a>Funções delegadas

Para cada trabalho no qual estiverem na equipe de contratação, os recrutadores e gerentes de contratação podem designar um ou mais destinados para eles mesmos. Entretanto, não podem designar destinados para outros contratos de contratação em equipe.

Os representantes têm os mesmos privilégios que a pessoa que os designou. Por exemplo, se o gerente de contratação designa um representante para si mesmo para um trabalho, o representante terá os mesmos privilégios que o gerente de contratação desse trabalho. Os representantes podem não remover outros delegados de suas equipes. Também podem não remover contatos que os designaram como delegados.

## <a name="job-details-and-actions"></a>Detalhes e ações de trabalho

Os usuários que tem a função de recrutador ou de gerente de contratação podem criar trabalhos. Estes privilégios aplicam-se aos detalhes do trabalho e às ações que podem ser realizadas em trabalhos.

| Dados ou ação    | Recrutador | Gerente de Contratação | Entrevistador |
|-------------------|-----------|----------------|-------------|
| Detalhes do Trabalho       | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Somente leitura |
| Equipe de contratação       | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Somente leitura |
| Lançamento de trabalho       | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Somente leitura | Somente leitura |
| Processar           | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Somente leitura |
| Adicionar candidatos    | Adicione candidatos para trabalho onde o usuário está na equipe de contratação | Adicione candidatos para trabalho onde o usuário está na equipe de contratação | Não permitido |
| Adicionar potenciais candidatos     | Adicione candidatos em potencial para trabalho onde o usuário está na equipe de contratação | Uma opção de configuração na [configuração de atividade de candidato em potencial](./activities-attract.md#prospect-activity) controla se os entrevistadores podem exibir e adicionar candidatos em potencial. | Não permitido |
| Ativar trabalho      | Ativa trabalhos onde o usuário está na equipe de contratação | Ativa trabalhos onde o usuário está na equipe de contratação | Não permitido |
| Fechar emprego         | Fecha trabalhos onde o usuário está na equipe de contratação | Não permitido | Não permitido |
| Excluir trabalho        | Exclui trabalhos onde o usuário está na equipe de contratação | Somente se o candidato não foi adicionado aos trabalhos | Não permitido |
| Excluir candidatos | Exclui candidatos se o usuário está na equipe de contratação | Não permitido | Não permitido |

## <a name="application-details-and-actions"></a>Detalhes e ações de aplicação

Os privilégios a seguir aplicam-se aos dados específicos do trabalho para candidatos e as ações que podem ser realizadas nas aplicações.

| Dados ou ação          | Recrutador | Gerente de Contratação | Entrevistador |
|-------------------------|-----------|----------------|-------------|
| Documentos de candidatura   | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Somente leitura |
| Arquivos de aplicação       | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Crie, ler, atualizar e excluir para trabalhos em que o usuário está participando da equipe de contratação | Somente leitura|
| Atividade de aplicação    | Exibir, se o usuário estiver em equipe de contratação | Exibir, se o usuário estiver em equipe de contratação | Somente leitura |
| Comentários sobre a aplicação    | Adicione e exibe todos os comentários se o usuário estiver na equipe de contratação | Adicione e exibe todos os comentários se o usuário estiver na equipe de contratação | Possível adicionar comentários\*\* |
| Rejeitar aplicação      | Pode rejeitar se o usuário estiver em equipe de contratação | Não permitido | Não permitido |
| Avançar estágio           | Pode rejeitar se o usuário estiver em equipe de contratação | Pode avançar se o usuário estiver em equipe de contratação | Não permitido |
| Lançar gerenciamento de ofertas | Pode iniciar o gerenciamento oferta | Há uma opção de configuração na oferta da atividade. | Não permitido |


\*\* Uma configuração de opção na [configuração de atividade de comentários](./activities-attract.md) controla se os entrevistadores podem ver os comentários uns dos outros.


## <a name="process-templates"></a>Modelos de processo

Os seguintes privilégios aplicam-se aos modelos de processo de contratação. A capacidade de membro de equipe de criar e editar modelos é configurada no **Gerenciamento de modelo** na central de administração. Se o gerenciamento do modelo é ativado, os recrutadores e gerentes de contratação podem criar e editar seus próprios modelos de processo. Se o gerenciamento do modelo for desativado, apenas os administradores podem criar e editar modelos de processo. A tabela a seguir supõe que o gerenciamento do modelo foi ativado.

| Dados              | Recrutador                                           | Gerente de Contratação                                      | Entrevistador |
|-------------------|-----------------------------------------------------|-----------------------------------------------------|-------------|
| Modelos de processo | Privilégios completos para os modelos que o usuário cria | Privilégios completos para os modelos que o usuário cria | Sem acesso   |

## <a name="email-and-email-templates"></a>E-mail e modelos de e-mail

Estes privilégios aplicam-se aos modelos de e-mail e às ações que podem ser realizadas em e-mails. Apenas os administradores podem criar e editar modelos de e-mail.

| Dados ou ação     | Recrutador          | Gerente de Contratação     | Entrevistador |
|--------------------|--------------------|--------------------|-------------|
| Modelos de email    | Acesso somente leitura   | Acesso somente leitura   | Sem acesso   |
| Enviar email         | Envio por atividade  | Envio por atividade  | Sem acesso   |
| Editar conteúdo de e-mail | Editar conteúdo de e-mail | Editar conteúdo de e-mail | Sem acesso   |

## <a name="talent-pools"></a>Grupos de talentos

Estes privilégio aplica-se a grupos do Talent. Grupos de talento são visíveis apenas às pessoas que os criaram, a menos que essa pessoa escolha compartilhá-los. A pesquisa do candidato pode ser usada para pesquisar candidatos que não foram adicionados a um grupo denominado.

| Dados ou ação   | Recrutador                                       | Gerente de Contratação                                  | Entrevistador |
|------------------|-------------------------------------------------|-------------------------------------------------|-------------|
| Grupo nomeado       | Privilégios completos para os grupos que o usuário cria | Privilégios completos para os grupos que o usuário cria | Sem acesso   |
| Compartilhar grupo       | Somente grupos que o usuário cria                | Somente grupos que o usuário cria                | Sem acesso   |
| Pesquisa do candidato | Recursos completos de pesquisa                        | Recursos completos de pesquisa                        | Sem acesso   |

## <a name="candidates"></a>Candidatos

Candidatos são os contatos que foram adicionados a um grupo de talento, mas não estão associados a uma posição.

| Dados                        | Recrutador                        | Gerente de Contratação                   | Entrevistador |
|-----------------------------|----------------------------------|----------------------------------|-------------|
| Perfil - detalhes do candidato | Criar, ler, atualizar e excluir | Criar, ler, atualizar e excluir | Sem acesso   |
| Documentos                   | Criar, ler, atualizar e excluir | Criar, ler, atualizar e excluir | Sem acesso   |
