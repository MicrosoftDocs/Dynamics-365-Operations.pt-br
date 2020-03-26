---
title: Provisionar o Talent
description: Este tópico o orienta através do processo de provisionar um novo ambiente para Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.openlocfilehash: d7c4a8174007384370ae320b3874e104c04b71a5
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124695"
---
# <a name="provision-talent"></a>Provisionar o Talent

Este tópico o orienta através do processo de provisionar um novo ambiente de produção para Microsoft Dynamics 365 Talent. Este tópico pressupõe que você adquiriu o Talent por meio do Provedor de Soluções na Nuvem ou do contrato de arquitetura da empresa (EA). Se você tiver uma licença existente do Microsoft Dynamics 365 que já inclua o plano do serviço do Talent e não puder concluir as etapas deste tópico, entre em contato com o Suporte.

Para começar, o administrador global deve entrar no [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) e criar um novo projeto Talent. A assistência dos representantes de Suporte ou do Dynamics Service Engineering (DSE) não é necessária, a menos que um problema de licença o impeça de provisionar o Talent

## <a name="create-an-lcs-project"></a>Criar um projeto LCS
Para usar o LCS para gerenciar seus ambientes do Talent, você deve criar primeiro um projeto LCS.

1. Entre no [LCS](https://lcs.dynamics.com/Logon/Index) usando a conta utilizada para inscrever-se no Talent.

2. Selecione o sinal de adição (**+**) para criar um projeto.

3. Selecione **Microsoft Dynamics 365 Talent** como o nome do produto e a versão do produto.

4. Selecione a metodologia do **Dynamics 365 Talent**.

5. Selecione **Criar**. 

Para obter informações sobre como começar a usar o Talent, consulte a metodologia do **Talent** que você criou em seu novo projeto. Após finalizar a criação do projeto, conclua o seguinte procedimento para provisionar seu ambiente do Talent.

## <a name="provision-a-talent-project"></a>Provisionar um projeto do Talent

Depois de criar um projeto de LCS, você pode provisionar o Talent em um ambiente.

1. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo Talent**.

2. Indique se esta é uma instância de Área restrita ou Produção do Talent. Os recursos de visualização antecipada podem estar disponíveis em instâncias de Área restrita para permitir comentários e testes antecipados. 

    > [!NOTE]
    > O tipo de instância do Talent não pode ser alterado após definido. Verifique se o tipo de instância correto está selecionado antes de continuar.

    > [!NOTE]
    > O tipo de instância do Talent é separado do tipo de instância do ambiente do Microsoft Power Apps, que você definiu no centro de administração do Power Apps.

3. Selecione a opção **Incluir Dados de Demonstração** se quiser que o ambiente inclua o mesmo conjunto de dados de demonstração usado na experiência de test drive do Talent. Isso é interessante para ambientes de demonstração ou de treinamento de longo prazo, e nunca deve ser usado em ambientes de produção.  Observe que você deve selecionar esta opção na implantação inicial. Não é possível atualizar uma implantação já existente depois.

4. O Talent sempre é provisionado em um ambiente do Microsoft Power Apps para permitir a integração e extensibilidade do Power Apps. Leia a seção "Selecionando um ambiente do Power Apps" deste tópico antes de prosseguir. Se você ainda não tem um ambiente do Power Apps, selecione Gerenciar ambientes no LCS ou vá para o Centro de administração do Power Apps. Em seguida, siga as etapas para [Criar um ambiente do Power Apps](https://docs.microsoft.com/powerapps/administrator/create-environment).

5. Selecione o ambiente ao qual provisionar o Talent.

6. Selecione **Sim** para concordar com os termos e começar a implantação.

    Seu novo ambiente aparece na lista de ambientes no painel de navegação à esquerda. Porém, você não pode começar a usar o ambiente enquanto o status de implantação não for atualizado para **Implantado**. Este processo normalmente leva alguns minutos. Se ocorrer uma falha no processo de provisionamento, você deve entrar em contato com o Suporte.

7. Selecione **Fazer logon no Talent** para usar o novo ambiente.

    > [!NOTE]
    > Se os requisitos finais ainda não foram aprovados, você pode implantar uma instância de teste do Talent no projeto. Você pode usar esta instância para testar a solução até que seja aprovada. Se usar o novo ambiente para teste, você deve repetir este procedimento para criar um ambiente de produção.

    > Como apenas dois ambientes de LCS são permitidos como parte da assinatura do Talent, você pode considerar a possibilidade de aproveitar um [ambiente de teste do Talent](https://dynamics.microsoft.com/talent/overview/) grátis por 60 dias. Embora um ambiente de avaliação seja propriedade do usuário que o solicitou, outros usuários podem ser convidados por meio da experiência de administração do sistema para o Human Resources. Os ambientes de avaliação contêm dados fictícios que podem ser usados para explorar o programa de forma segura. Eles não devem ser usados como ambientes de produção. Observe que, quando um ambiente de avaliação expirar após 60 dias, todos os dados que estão nele serão excluídos e não poderão ser recuperados. Você pode inscrever-se para um novo ambiente de avaliação após o ambiente existente expirar.

## <a name="select-a-power-apps-environment"></a>Selecionar um ambiente do Power Apps

A integração entre os ambientes do Power Apps e Talent permite que você integre e estenda o uso dos dados do Talent usando ferramentas do Power Apps. Entender a finalidade dos ambientes do Power Apps não só ajudará você a criar aplicativos para estender o Talent, mas também poderá ajudá-lo a selecionar o ambiente correto ao provisionar o Talent. Para obter mais informações sobre os ambientes do Power Apps, incluindo escopo do ambiente, acesso ao ambiente e criação e escolha do ambiente, consulte [Anunciando ambientes do Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Use as seguintes orientações ao determinar para qual ambiente do Power Apps o Talent será implantado: 

1. No LCS, selecione **Gerenciar ambientes** ou vá diretamente para o Centro de administração do Power Apps, onde você poderá exibir os ambientes existentes e criar novos.

2. Um ambiente único do Talent é mapeado para um ambiente único do Power Apps.

3. Um ambiente do Power Apps contém o Talent, com os aplicativos correspondentes do Power Apps, Power Automate e Common Data Service. Se o ambiente do Power Apps for excluído, os aplicativos contidos nele também serão. Ao provisionar um ambiente do Talent, é possível provisionar um ambiente de **Teste** ou **Produção**. Escolha o tipo de ambiente baseado em como o ambiente será usado. 

4. Estratégias de teste e integração de dados devem ser consideradas, como Área restrita, UAT ou Produção. É recomendável levar em consideração as várias implicações para sua implantação, pois não será fácil alterar posteriormente qual ambiente do Talent será mapeado para um ambiente do Power Apps.

5. Os seguintes ambientes do Power Apps não podem ser usados para o Talent e serão filtrados na lista de seleção no LCS:
 
    - **Ambientes padrão do Power Apps** – embora cada locatário seja provisionado automaticamente com um ambiente padrão do Power Apps, não é recomendável usá-lo com o Talent, pois todos os usuários do locatário têm acesso ao ambiente do Power Apps e poderão corromper involuntariamente os dados de produção ao testar e explorar com integrações do Power Apps ou do Power Automate.
   
    - **Ambientes de versão de avaliação** - Esses ambientes são criados com uma data de vencimento e expirarão após esse tempo, resultando na remoção automática do seu ambiente e de quaisquer instâncias do Talent contidas.
   
    - **Regiões sem suporte** - No momento, o Talent tem suporte apenas nas seguintes regiões: Estados Unidos, Europa, Reino Unido, Austrália, Canadá e Ásia.
  
6. Depois de determinar o ambiente correto a ser usado, você poderá continuar com o processo de provisionamento. 
 
## <a name="grant-access-to-the-environment"></a>Conceder acesso ao ambiente

Por padrão, o administrador global que criou o ambiente tem acesso a ele. Entretanto, os usuários adicionais do aplicativo devem ter acesso explicitamente. Para conceder acesso, você precisa adicionar usuários e atribuir a eles as funções adequadas no ambiente do Human Resources. O administrador global que implantou o Talent também deve iniciar o Attract e o Onboard para concluir a inicialização e habilitar o acesso para outros usuários do locatário.  Até que isso ocorra, outros usuários não poderão acessar o Attract e o Onboard e receberão erros de violação de acesso. Para obter mais informações, consulte [Criar novos usuários](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [Atribuir usuários a funções de segurança](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
