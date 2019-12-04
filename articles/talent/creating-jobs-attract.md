---
title: Criar um trabalho no Attract
description: Este tópico descreve os elementos de um trabalho no Attract. Ele também explica como criar um trabalho.
author: hasrivas
manager: AnnBe
ms.date: 07/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2018-10-24
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 9dcdbcea995285c879f91c0bff435103865cc10f
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832922"
---
# <a name="create-a-job-in-attract"></a>Criar um trabalho no Attract

[!include [banner](includes/banner.md)]

Este tópico descreve os elementos de um trabalho no Microsoft Dynamics 365 Talent: Attract. Ele também explica como criar um trabalho.

## <a name="job-creation"></a>Criação do trabalho

Os administradores, os recrutadores e os gerentes de contratação podem criar trabalhos. Ao criar um trabalho, você é solicitado a selecionar sua função no processo: gerente de contratação ou recrutador. Após selecionar uma função, você será solicitado a selecionar um modelo de processo. Se você selecionar **Ignorar**, o modelo padrão será usado. Para obter mais informações sobre modelos de processo, consulte [Criar um modelo de processo no Attract](./process-templates-attract.md).

Um trabalho no Attract tem detalhes de trabalho, uma equipe de contratação, um processo de contratação, lançamentos de trabalho e análises.

## <a name="job-details"></a>Detalhes do Trabalho

A guia **Detalhes do trabalho** contém detalhes sobre as responsabilidades e os atributos do trabalho. Os campos para o cargo, a descrição do trabalho e o local de trabalho são necessários. Os outros campos são opcionais.

Por padrão, o campo **Número de aberturas** é definido como **1**. No entanto, você pode alterar o valor. Quando uma oferta for preparada para um trabalho, o valor do campo **Número de aberturas disponíveis** será reduzido.

Se o gerenciamento de cargos estiver ativado no Centro de administração, a pesquisa **Atualizar posições** estará disponível. Essa pesquisa lê a entidade JobPosition no Common Data Service e retorna uma lista de posições que podem ser selecionadas para o trabalho. Se o número de posições selecionado exceder o número de posições abertas, você receberá um aviso. Você também receberá um aviso se uma posição for usada em vários trabalhos.

> [!NOTE]
> O gerenciamento de posições está disponível com o Complemento de Contratação Abrangente.

Dependendo das configurações da atividade Oferta do processo de contratação, um número de posição pode ser usado duas vezes em uma oferta. Para obter mais informações, consulte [Atividades nos processos de contratação](./activities-attract.md).

O Attract inclui um conjunto padrão de **Habilidades**. Essas habilidades aparecem como sugestões à medida que você digita. Você pode adicionar mais habilidades inserindo o novo texto de habilidades no campo e pressionando Enter.

O Attract inclui um conjunto padrão de **Funções de trabalho**. Você pode adicionar até três funções de trabalho a mais, inserindo a nova função de trabalho no campo e pressionando Enter.

O Attract inclui um conjunto padrão de **Indústria empresarial**. Você pode adicionar até três indústrias empresariais a mais, inserindo a indústria empresarial no campo e pressionando Enter.

## <a name="hiring-team"></a>Equipe de contratação

A guia **Equipe de contratação** contém a lista de indivíduos que estarão envolvidos no trabalho. Quando os usuários são adicionados a uma equipe de contratação, deve-se atribuir uma função a eles na equipe de contratação. A função determina os dados aos quais os usuários têm acesso e as notificações que recebem. As funções que podem ser selecionadas são **Recrutador**, **Gerente de contratação**, **Delegado** e **Entrevistador**. Para obter mais informações sobre privilégios de função, consulte o documento "Gerenciamento de funções". Os recrutadores e os gerentes de contratação podem designar um ou mais delegados para trabalhar em seu nome. Para obter mais informações sobre delegados, consulte [Gerenciamento de segurança e funções no Attract](./security-attract.md).

A equipe de contratação pode ser atualizada após o trabalho ser ativado.

## <a name="process"></a>Processar

As informações padrão sobre o processo de contratação se baseiam no modelo do processo que foi selecionado quando o trabalho foi criado. Se um modelo específico não foi selecionado naquele momento, o modelo padrão será usado. Ao definir o processo de contratação, você pode adicionar ou remover vários estágios, exceto os estágios Cliente potencial, Solicitação de Emprego e Oferta. Embora o estágio Cliente potencial não possa ser removido, ele pode ser desativado. Em cada estágio, você pode adicionar ou remover uma ou mais atividades predefinidas.

Para obter mais informações sobre as atividades que podem ser adicionadas ao processo de contratação, consulte [Atividades nos processos de contratação](./activities-attract.md).

> [!NOTE]
> O processo de contratação não pode ser atualizado após um trabalho ser ativado.

## <a name="postings"></a>Lançamentos

Após um trabalho ser ativado, ele poderá ser lançado. Somente os recrutadores e os administradores podem lançar trabalhos. O trabalho pode ser postado no Talent Careers (site de carreiras do Dynamics 365 Talent) ou no LinkedIn. A equipe do Attract trabalha continuamente para fazer parceria com os agregadores do quadro de trabalho. Essa lista se expandirá com o tempo. Quando um trabalho é lançado como somente interno, os candidatos precisam de uma conta do AAD para visualizar e se candidatar ao trabalho. Se o trabalho é listado como público, os candidatos podem visualizar e se candidatar ao trabalho usando todas as opções de autenticação. 

Para obter mais informações sobre lançamentos de trabalho, consulte [Configurar seu site de carreiras no Microsoft Dynamics 365 Talent - Attract](career-site.md).

> [!NOTE]
> A funcionalidade do lançamento de trabalho está disponível apenas com o Complemento de Contratação Abrangente para o Attract.

## <a name="activate"></a>Ativar

Depois que um trabalho é ativado, é possível lançá-lo . Os clientes potenciais e candidatos podem ser adicionados a ele. A opção para adicionar clientes potenciais a um trabalho é definida na atividade Cliente potencial no processo de contratação.

> [!NOTE]
> O processo de contratação não pode ser atualizado após um trabalho ser ativado.

## <a name="prospects-and-applicants"></a>Clientes potenciais e candidatos

A opção para adicionar clientes potenciais a um trabalho é definida nas [Atividades nos processos de contratação](./activities-attract.md#prospect-activity) no processo de contratação. Essa opção deve ser definida antes de você ativar o trabalho. Depois que um trabalho é ativado, os clientes potenciais e candidatos podem ser adicionados a ele.

## <a name="approvals"></a>Aprovações

Os trabalhos do Attract podem ser enviados para aprovação. Nem todos os trabalhos exigem aprovação. A requisição é definida em nível de modelo. Por padrão, as aprovações são desativadas no modelo. Para configurar aprovações, vá para um modelo de processo e defina o campo **Aprovação** como Padrão. Selecione esse modelo ao criar o trabalho.

Após ser salvo, um trabalho pode ser enviado para aprovação. A tabela a seguir lista o status de um documento que usa aprovações.

| Status   | Estadual                                                               |
|----------|---------------------------------------------------------------------|
| Rascunho    | O trabalho foi salvo, mas ainda não foi enviado para um fluxo de trabalho. |
| Pendente  | O trabalho foi enviado para aprovadores.                            |
| Aprovadas | O trabalho foi aprovado, mas ainda não foi ativado.            |
| Rejeitadas | O trabalho foi rejeitado e não pode ser ativado.               |
| Ativa   | O trabalho foi aprovado e ativado.                            |

Na lista de trabalhos, você pode filtrar o status dos trabalhos.

As aprovações podem ser enviadas para qualquer usuário do Microsoft Azure Active Directory (Azure AD) na empresa. As aprovações são enviadas em paralelo a todas as pessoas listadas como aprovadores. Todos os aprovadores devem aprovar o trabalho antes que ele possa avançar. Se um único aprovador rejeitar o trabalho, o status **Rejeitado** será exibido no trabalho. Após um trabalho ser aprovado, ele poderá ser ativado.

Se um usuário editar o trabalho depois que ele for aprovado, mas não ativado, o status do trabalho será redefinido como **Rascunho** e o trabalho deverá ser enviado novamente para aprovação. Depois que um trabalho aprovado for ativado, não será possível editá-lo.

As pessoas listadas como aprovadores receberão uma notificação no Attract e um email para informá-las de que há um item a ser aprovado.  No email, os aprovadores podem clicar no link para para abrir o trabalho, examinar os detalhes e aprová-lo ou rejeitá-lo. Depois que o status do trabalho for definido como **Aprovado** ou **Rejeitado**, o emissor será notificado no Attract e receberá um email. Além disso, os aprovadores receberão um email de lembrete se eles não responderem à solicitação de aprovação dentro de 24 horas.

> [!NOTE]
> Você pode criar modelos de email personalizados para Emails de aprovação. Para obter mais informações, consulte [Criando e gerenciando modelos de email](https://docs.microsoft.com/dynamics365/unified-operations/talent/email-templates).

## <a name="create-a-job"></a>Criar um trabalho

Siga estas etapas para criar um trabalho.

1. Vá para **Trabalhos**.
2. Selecione **Novo**.
3. No campo **Cargo**, insira o cargo. No campo **Função**, digite sua função.
4. No campo **Modelo**, selecione um modelo. Como alternativa, selecione **Ignorar**. Se você selecionar **Ignorar**, o modelo marcado como o modelo padrão será usado.

    Se o documento precisar passar por um processo de aprovação, selecione um modelo em que o campo **Processo de aprovação** seja definido como **Padrão**.

5. Na guia **Detalhes**, insira os detalhes do trabalho. Os campos **Título**, **Descrição do trabalho** e **Localização** são obrigatórios.
6. Selecione **Salvar**.
7. Na guia **Equipe de contratação**, adicione um gerente de contratação, um recrutador ou um entrevistador.
8. Selecione **Salvar**.
9. Na guia **Processo**, adicione ou remova estágios conforme necessário:

    - Para adicionar um estágio, selecione **+ Novo estágio**.
    - Para remover um estágio, coloque o ponteiro sobre o estágio a ser removido e selecione o botão de lixeira que aparece.

        > [!NOTE]
        > Os estágios Cliente potencial, Solicitação de emprego e Oferta não podem ser removidos.

10. Adicione ou remova atividades conforme necessário:

    - Para adicionar uma atividade, arraste-a da lista à direita para o estágio apropriado. Outra opção é clicar duas vezes na atividade e selecionar o estágio para adicioná-la.
    - Para remover uma atividade, expanda-a e depois selecione o botão de lixeira no cabeçalho da atividade.

11. Selecione **Salvar**.
12. Se você optou por usar um processo de aprovação, siga estas etapas:

    1. Selecione **+ Adicionar aprovador** e insira um usuário que tem uma conta do Azure AD. Você pode adicionar vários aprovadores.
    2. Selecione **Enviar para aprovadores**.

    O campo **Status do trabalho** do trabalho é definido como **Pendente**. Depois que o campo **Status do trabalho** mudar para **Aprovado**, o trabalho poderá ser ativado.

13. Para ativar o trabalho, selecione **Ativar**.
14. Para lançar o trabalho, vá para **Lançamentos** e selecione **Lançar Agora** site do Talent Careers ou no LinkedIn.
