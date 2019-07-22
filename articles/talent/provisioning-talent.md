---
title: Provisionar o Talent
description: Este tópico o orienta através do processo de provisionar um novo ambiente para Microsoft Dynamics 365 for Talent.
author: andreabichsel
manager: AnnBe
ms.date: 05/15/2019
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
ms.openlocfilehash: c249df697553cd42eccd59d3f2c3f5f083ead1cb
ms.sourcegitcommit: 15154b0aa86110ce5fad6f63e6763103a676a1d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2019
ms.locfileid: "1624598"
---
# <a name="provision-talent"></a>Provisionar o Talent

[!include [banner](includes/banner.md)]

Este tópico o orienta através do processo de provisionar um novo ambiente de produção para Microsoft Dynamics 365 for Talent. Este tópico pressupõe que você adquiriu o Talent por meio do Provedor de Soluções na Nuvem ou do contrato de arquitetura da empresa (EA). Se você tiver uma licença existente do Microsoft Dynamics 365 que já inclua o plano do serviço do Talent e não puder concluir as etapas deste tópico, entre em contato com o Suporte.

Para começar, o administrador global deve entrar no [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) e criar um novo projeto Talent. A assistência dos representantes de Suporte ou do Dynamics Service Engineering (DSE) não é necessária, a menos que um problema de licença o impeça de provisionar o Talent

## <a name="create-an-lcs-project"></a>Criar um projeto LCS
Para usar o LCS para gerenciar seus ambientes do Talent, você deve criar primeiro um projeto LCS.

1. Entre no [LCS](https://lcs.dynamics.com/Logon/Index) usando a conta utilizada para inscrever-se no Talent.
2. Selecione o sinal de adição (**+**) para criar um projeto.
3. Selecione **Microsoft Dynamics 365 for Talent** como o nome do produto e a versão do produto.
4. Selecione a metodologia do **Dynamics 365 for Talent**.
5. Selecione **Criar**.

Para obter informações sobre como começar a usar o Talent, consulte a metodologia do **Talent** que você criou em seu novo projeto. Após finalizar a criação do projeto, conclua o seguinte procedimento para provisionar seu ambiente do Talent.

## <a name="provision-a-talent-project"></a>Provisionar um projeto do Talent
Depois de criar um projeto de LCS, você pode provisionar o Talent em um ambiente.

1. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo Talent**.
2. Indique se esta é uma instância de Área restrita ou Produção do Talent. Os recursos de visualização antecipada podem estar disponíveis em instâncias de Área restrita para permitir comentários e testes antecipados. 
    > [!NOTE]
    > O tipo de instância do Talent é separado do tipo de instância do ambiente do PowerApps, que você definiu no centro de administração do PowerApps.
3. Selecione a opção **Incluir Dados de Demonstração** se quiser que o ambiente inclua o mesmo conjunto de dados de demonstração usado na experiência de test drive do Talent. Isso é interessante para ambientes de demonstração ou de treinamento de longo prazo, e nunca deve ser usado em ambientes de produção.  Observe que você deve selecionar esta opção na implantação inicial. Não é possível atualizar uma implantação já existente depois.
4. O Talent sempre é provisionado em um ambiente Microsoft PowerApps para permitir a integração e extensibilidade do PowerApps. Leia a seção “Selecionando um ambiente do PowerApps” deste tópico antes de prosseguir. Se você ainda não tem um ambiente PowerApps, selecione Gerenciar ambientes no LCS ou vá para o Centro de administração do PowerApps. Depois, rastreie as etapas em [Criar um ambiente de PowerApps](https://docs.microsoft.com/en-us/powerapps/administrator/create-environment).

    > [!NOTE]
    > Para exibir os ambientes existentes ou criar novos ambientes, o administrador do locatário que provisiona o Talent deve ter a licença do PowerApps P2. Se sua organização não tiver uma licença de PowerApps P2, obtenha uma do CSP ou da [página de preços do PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

5. Selecione o ambiente ao qual provisionar o Talent.
6. Selecione **Sim** para concordar com os termos e começar a implantação.

    Seu novo ambiente aparece na lista de ambientes no painel de navegação à esquerda. Porém, você não pode começar a usar o ambiente enquanto o status de implantação não for atualizado para **Implantado**. Este processo normalmente leva alguns minutos. Se ocorrer uma falha no processo de provisionamento, você deve entrar em contato com o Suporte.

7. Selecione **Fazer logon no Talent** para usar o novo ambiente.

    > [!NOTE]
    > Se os requisitos finais ainda não foram aprovados, você pode implantar uma instância de teste do Talent no projeto. Você pode usar esta instância para testar a solução até que seja aprovada. Se usar o novo ambiente para teste, você deve repetir este procedimento para criar um ambiente de produção.

    > Como apenas dois ambientes de LCS são permitidos como parte da assinatura do Talent, você pode considerar a possibilidade de aproveitar um [ambiente de teste do Talent](https://dynamics.microsoft.com/en-us/talent/overview/) grátis por 60 dias. Embora um ambiente de avaliação seja propriedade do usuário que o solicitou, outros usuários podem ser convidados por meio da experiência de administração do sistema para o Core HR. Os ambientes de avaliação contêm dados fictícios que podem ser usados para explorar o programa de forma segura. Eles não devem ser usados como ambientes de produção. Observe que, quando um ambiente de avaliação expirar após 60 dias, todos os dados que estão nele serão excluídos e não poderão ser recuperados. Você pode inscrever-se para um novo ambiente de avaliação após o ambiente existente expirar.

## <a name="select-a-powerapps-environment"></a>Selecione um ambiente do PowerApps

A integração entre o Talent e os ambientes do PowerApps permite que você integre e estenda o uso dos dados do Talent usando ferramentas do PowerApps. Entender a finalidade dos ambientes PowerApps não só ajudará você a criar aplicativos para estender o Talent, mas também poderá ajudá-lo a selecionar o ambiente correto ao provisionar o Talent. Para obter mais informações sobre os ambientes do PowerApps, incluindo escopo do ambiente, acesso ao ambiente e criação e escolha do ambiente, consulte [Anunciando ambientes do PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Use as seguintes orientações ao determinar para qual ambiente do PowerApps o Talent será implantado: 

1. No LCS, selecione **Gerenciar ambientes** ou vá diretamente para o Centro de administração do PowerApps, onde você poderá exibir os ambientes existentes e criar novos.
2. Um ambiente único do Talent é mapeado para um ambiente único do PowerApps.
3. Um ambiente do PowerApps “contém" o aplicativo Talent, junto com os aplicativos PowerApps, Flow e Common Data Service correspondentes. Se o ambiente do PowerApps for excluído, os aplicativos contidos nele também serão. Ao provisionar um ambiente Talent, "Trial" ou "Production" pode ser provisionado. Escolha o tipo de ambiente baseado em como o ambiente será usado. 
4. Estratégias de teste e integração de dados devem ser consideradas, como Área restrita, UAT ou Produção. Recomendamos que você leve em consideração as várias implicações para sua implantação, pois não será fácil alterar posteriormente qual ambiente do Talent será mapeado para um ambiente do PowerApps.
5. Os seguintes ambientes do PowerApps não podem ser usados para o Talent e serão filtrados da lista de seleção no LCS:
 
    - **Ambientes padrão do PowerApps** - Embora cada locatário seja provisionado automaticamente com um ambiente padrão do PowerApps, não é recomendável usá-lo com o Talent, pois todos os usuários do locatário têm acesso ao ambiente do PowerApps e poderão corromper involuntariamente os dados de produção ao testar e explorar com integrações do PowerApps ou do Flow.
   
    - **Ambientes de versão de avaliação** - Esses ambientes são criados com uma data de vencimento e expirarão após esse tempo, resultando na remoção automática do seu ambiente e de quaisquer instâncias do Talent contidas.
   
    - **Regiões sem suporte** - No momento, o Talent tem suporte apenas nas seguintes regiões: Estados Unidos, Europa, Reino Unido ou Austrália.
  
6. Depois de determinar o ambiente correto a ser usado, você poderá continuar com o processo de provisionamento. 
 
## <a name="grant-access-to-the-environment"></a>Conceder acesso ao ambiente
Por padrão, o administrador global que criou o ambiente tem acesso a ele. Entretanto, os usuários adicionais do aplicativo devem ter acesso explicitamente. Para conceder acesso, você precisa adicionar usuários e atribuir a eles as funções adequadas no ambiente do Core HR. O administrador global que implantou Talent também deve iniciar os aplicativos Attract and Onboard para concluir a inicialização e habilitar o acesso para outros usuários do locatário.  Até que isso ocorra, outros usuários não poderão acessar os aplicativos Attract and Onboard e receberão erros de violação. Para obter mais informações, consulte [Criar novos usuários](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [Atribuir usuários a funções de segurança](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 
