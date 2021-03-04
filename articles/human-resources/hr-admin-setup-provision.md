---
title: Provisionar o Human Resources
description: Este artigo o orienta através do processo de provisionar um novo ambiente de produção para Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 106976edfa2bd7efba41887d5e8f4243b56e7b2f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527780"
---
# <a name="provision-human-resources"></a>Provisionar o Human Resources

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo o orienta através do processo de provisionar um novo ambiente de produção para Microsoft Dynamics 365 Human Resources. Este tópico pressupõe que você adquiriu o Human Resources por meio de um Provedor de Soluções na Nuvem (CSP) ou de um contrato de arquitetura da empresa (EA). Se você tiver uma licença existente do Microsoft Dynamics 365 que já inclua o plano do serviço do Human Resources e não puder concluir as etapas deste artigo, entre em contato com o Suporte.

Para começar, o administrador global deve entrar no [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) e criar um novo projeto Human Resources. A assistência dos representantes de Suporte ou do Dynamics Service Engineering (DSE) não é necessária, a menos que um problema de licença o impeça de provisionar o Human Resources.

## <a name="create-an-lcs-project"></a>Criar um projeto LCS

Para usar o LCS para gerenciar seus ambientes do Human Resources, você deve criar primeiro um projeto LCS.

1. Entre no [LCS](https://lcs.dynamics.com/Logon/Index) usando a conta utilizada para inscrever-se no Human Resources.

2. Selecione o sinal de adição (**+**) para criar um projeto.

3. Selecione **Microsoft Dynamics 365 Human Resources** como o nome do produto e a versão do produto.

4. Selecione a metodologia do **Dynamics 365 Human Resources**.

5. Selecione **Criar**.

Para obter informações sobre como começar a usar o Human Resources, consulte a metodologia do **Human Resources** que você criou em seu novo projeto. Após finalizar a criação do projeto, conclua o seguinte procedimento para provisionar seu ambiente do Human Resources.

## <a name="provision-a-human-resources-project"></a>Provisionar um projeto Human Resources

Depois de criar um projeto de LCS, você pode provisionar o Human Resources em um ambiente.

1. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**.

2. Indique se este ambiente é uma instância de Área restrita ou Produção do Human Resources. Os recursos de visualização antecipada podem estar disponíveis em instâncias de Área restrita para permitir comentários e testes antecipados.
   
    > [!NOTE]
    > O tipo de instância do Human Resources não pode ser alterado após definido. Verifique se o tipo de instância correto está selecionado antes de continuar.</br></br>
    > O tipo de instância do Human Resources é separado do tipo de instância do ambiente do Microsoft Power Apps, que você definiu no centro de administração do Power Apps.
    
3. Selecione a opção **Incluir Dados de Demonstração** se quiser que o ambiente inclua o mesmo conjunto de dados de demonstração usado na experiência de test drive do Human Resources. Dados de demonstração são interessantes para ambientes de demonstração ou de treinamento de longo prazo, e nunca devem ser usados em ambientes de produção. Você deve selecionar esta opção na implantação inicial. Não é possível atualizar uma implantação já existente depois.

4. O Human Resources sempre é provisionado em um ambiente do Microsoft Power Apps para permitir a integração e extensibilidade do Power Apps. Leia a seção "Selecionando um ambiente do Power Apps" deste artigo antes de prosseguir. Se você ainda não tem um ambiente do Power Apps, selecione Gerenciar ambientes no LCS ou vá para o Centro de administração do Power Apps. Em seguida, siga as etapas para [Criar um ambiente do Power Apps](https://docs.microsoft.com/powerapps/administrator/create-environment).

5. Selecione o ambiente ao qual provisionar o Human Resources.

6. Selecione **Sim** para concordar com os termos e começar a implantação.

   Seu novo ambiente aparece na lista de ambientes no painel de navegação à esquerda. Porém, você não pode começar a usar o ambiente enquanto o status de implantação não for atualizado para **Implantado**. Este processo normalmente leva alguns minutos. Se ocorrer uma falha no processo de provisionamento, você deve entrar em contato com o Suporte.

7. Selecione **Fazer logon no Human Resources** para usar o novo ambiente.

    > [!NOTE]
    > Se os requisitos finais ainda não foram aprovados, você pode implantar uma instância de teste do Human Resources no projeto. Você pode usar esta instância para testar a solução até que seja aprovada. Se usar o novo ambiente para teste, você deve repetir este procedimento para criar um ambiente de produção.

    > Você pode considerar o aproveitamento de um [ambiente de avaliação de recursos humanos](https://go.microsoft.com/fwlink/p/?LinkId=2115962) de 60 dias gratuitos. Embora um ambiente de avaliação seja propriedade do usuário que o solicitou, outros usuários podem ser convidados por meio da experiência de administração do sistema para o Human Resources. Os ambientes de avaliação contêm dados fictícios que podem ser usados para explorar o programa de forma segura. Eles não devem ser usados como ambientes de produção. Observe que, quando um ambiente de avaliação expirar após 60 dias, todos os dados que estão nele serão excluídos e não poderão ser recuperados. Você pode inscrever-se para um novo ambiente de avaliação após o ambiente existente expirar.

## <a name="select-a-power-apps-environment"></a>Selecionar um ambiente do Power Apps

Você pode integrar e estender o uso de dados do Human Resources usando as ferramentas do Power Apps. Para obter mais informações sobre os ambientes do Power Apps, incluindo escopo do ambiente, acesso ao ambiente e criação e escolha do ambiente, consulte [Anunciando ambientes do Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Use as seguintes orientações ao determinar para qual ambiente do Power Apps o Human Resources será implantado: 

1. No LCS, selecione **Gerenciar ambientes**. Você também pode ir diretamente para o Centro de Administração do Power Apps, onde você pode visualizar os ambientes existentes e criar novos.

2. Um ambiente único do Human Resources é mapeado para um ambiente único do Power Apps.

3. Um ambiente do Power Apps contém o Human Resources, com os aplicativos correspondentes do Power Apps, Power Automate e Common Data Service. Se o ambiente do Power Apps for excluído, os aplicativos contidos nele também serão. Ao provisionar um ambiente do Human Resources, é possível provisionar um ambiente de **Teste** ou **Produção**. Escolha o tipo de ambiente baseado em como o ambiente será usado. 

4. Estratégias de teste e integração de dados devem ser consideradas, como Área restrita, UAT ou Produção. Leve em consideração as implicações para sua implantação, pois não será fácil alterar qual ambiente do Human Resources será mapeado para um ambiente do Power Apps.

5. Você não pode usar os ambientes do Power Apps a seguir para Human Resources. Eles são filtrados a partir da lista de seleção dentro do LCS:
 
    - Ambientes **do Power Apps padrão** - Enquanto cada locatário é provisionado automaticamente com um ambiente do Power Apps padrão, não recomendamos usá-los com Human Resources. Todos os usuários de locatários podem acessar o ambiente do Power Apps e podem acidentalmente danificar dados de produção ao testar e explorar com integrações Power Apps ou Power Automate.
   
    - **Ambientes de avaliação** - Esses ambientes são criados com uma data de validade. Após o vencimento, seu ambiente e quaisquer instâncias do Human Resources contidas nele serão removidos automaticamente.
   
    - **Regiões sem suporte** - No momento, o Human Resources tem suporte apenas nas seguintes regiões: Estados Unidos, Europa, Reino Unido, Austrália, Canadá e Ásia.

    > [!NOTE]
    > O ambiente de Human Resources é provisionado na mesma região em que o ambiente Power Apps é provisionado. Não há suporte para a migração de um ambiente de Human Resources para outra região.

6. Depois de determinar o ambiente correto a ser usado, você poderá continuar com o processo de provisionamento. 
 
## <a name="grant-access-to-the-environment"></a>Conceder acesso ao ambiente

Por padrão, o administrador global que criou o ambiente tem acesso a ele. Os usuários adicionais do aplicativo devem ter acesso explicitamente. Você deve adicionar usuários e atribuir a eles as funções adequadas no ambiente do Human Resources. O administrador global que implantou o Human Resources também deve iniciar o Attract e o Onboard para concluir a inicialização e habilitar o acesso para outros usuários do locatário. Até que isso ocorra, outros usuários não poderão acessar o Attract e o Onboard e receberão erros de violação de acesso. Para obter mais informações, consulte [Criar novos usuários](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [Atribuir usuários a funções de segurança](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]