---
title: Provisionar Microsoft Dynamics 365 for Talent
description: "Este tópico o orienta através do processo de provisionar um novo ambiente para Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 1be4b41f63dd03a1d853d344fcde05e8962424e2
ms.openlocfilehash: e6266ef5890b5caaf33db76eeccfc8a7a6888a11
ms.contentlocale: pt-br
ms.lasthandoff: 03/17/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Provisionar Microsoft Dynamics 365 for Talent

[!include[banner](includes/banner.md)]

Este tópico mostra o processo de provisionamento de um novo ambiente de produção para o Microsoft Dynamics 365 for Talent. Este tópico pressupõe que você adquiriu o Talent por meio do Provedor de Soluções na Nuvem ou do contrato de arquitetura da empresa (EA). Se você tiver uma licença existente do Microsoft Dynamics 365 que já inclua o plano do serviço do Talent e não puder concluir as etapas deste tópico, entre em contato com o Suporte.

Para começar, o administrador global deve entrar no [Microsoft Dynamics Lifecycle Services](http://lcs.dynamics.com) (LCS) e criar um novo projeto Talent. A assistência dos representantes de Suporte ou do Dynamics Service Engineering (DSE) não é necessária, a menos que um problema de licença o impeça de provisionar o Talent

## <a name="create-an-lcs-project"></a>Criar um projeto LCS
Para usar o LCS para gerenciar seus ambientes do Talent, você deve criar primeiro um projeto LCS.

1. Entre no [LCS](https://lcs.dynamics.com/Logon/Index) usando a conta utilizada para inscrever-se no Talent.
2. Selecione o sinal de adição (**+**) para criar um projeto.
3. Selecione **Microsoft Dynamics 365 for Talent** como o nome do produto e a versão do produto.
4. Selecione a metodologia **Dynamics 365 for Talent**.
5. Selecione **Criar**.

Para obter informações sobre como começar a usar o Talent, consulte a metodologia do **Talent** que você criou em seu novo projeto. Após finalizar a criação do projeto, conclua o seguinte procedimento para provisionar seu ambiente do Talent.

## <a name="provision-a-talent-project"></a>Provisionar um projeto do Talent
Depois de criar um projeto de LCS, você pode provisionar o Talent em um ambiente.

1. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo Talent**.
2. O Talent sempre é provisionado em um ambiente Microsoft PowerApps para permitir a integração e extensibilidade do PowerApps. Se você ainda não tiver um ambiente de PowerApps, siga as etapas da seção "Criar um novo ambiente do PowerApps (se necessário)" deste tópico, antes de continuar.

    > [!NOTE]
    > Para exibir os ambientes existentes ou criar novos ambientes, o administrador do locatário que provisiona o Talent deve ter a licença do PowerApps P2. Se sua organização não tiver uma licença de PowerApps P2, obtenha uma do CSP ou da [página de preços do PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

3. Selecione **Adicionar** e depois o ambiente para provisionar o Talent.
4. Selecione **Sim** para concordar com os termos e começar a implantação.

    Seu novo ambiente aparece na lista de ambientes no painel de navegação à esquerda. Porém, você não pode começar a usar o ambiente enquanto o status de implantação não for atualizado para **Implantado**. Este processo normalmente leva alguns minutos. Se ocorrer uma falha no processo de provisionamento, você deve entrar em contato com o Suporte.

6. Selecione **Fazer logon no Talent** para usar o novo ambiente.

> [!NOTE]
> Se os requisitos finais ainda não foram aprovados, você pode implantar uma instância de teste do Talent no projeto. Você pode usar esta instância para testar a solução até que seja aprovada. Se usar o novo ambiente para teste, você deve repetir este procedimento para criar um ambiente de produção.

> [!NOTE]
> Os ambientes do Talent que são provisionados por meio do LCS não contêm dados de demonstração configurados para tarefas de Recursos humanos (RH) ou dados específicos para o Talent. Se você requer um ambiente que contenha dados de demonstração, recomendamos que você se inscreva para uma [Avaliação grátis do Talent por 60 dias](https://dynamics.microsoft.com/en-us/talent/overview/). Embora um ambiente de avaliação seja propriedade do usuário que o solicitou, outros usuários podem ser convidados por meio da experiência de administração do sistema para o Core HR. Os ambientes de avaliação contêm dados fictícios que podem ser usados para explorar o programa de forma segura. Eles não devem ser usados como ambientes de produção. Observe que, quando o ambiente de avaliação expirar após 60 dias, todos os dados nele serão excluídos e não poderão ser recuperados. Você pode inscrever-se para um novo ambiente de avaliação após o ambiente existente expirar.

## <a name="create-a-new-powerapps-environment-if-required"></a>Crie um novo ambiente do PowerApps (se necessário)
A integração entre o Talent e os ambientes do PowerApps permite que você integre e estenda o uso dos dados do Talent usando ferramentas do PowerApps. A compreensão da finalidade dos ambientes do PowerApps ajudará você a criar aplicativos que atendam às suas necessidades de estender o Talent. Para obter mais informações sobre os ambientes do PowerApps, incluindo escopo do ambiente, acesso ao ambiente e criação e escolha do ambiente, consulte [Anunciando ambientes do PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). Embora cada locatário seja provisionado automaticamente com um ambiente do PowerApps padrão, talvez esse não seja o melhor ambiente para ser usado na sua implantação do Talent. Estratégias de teste e de integração de dados devem ser consideradas nessa etapa. Por isso, recomendamos que você leve em consideração as implicações que podem impactar sua implantação, pois não será fácil alterar algumas decisões posteriormente. 

Embora cada locatário seja provisionado automaticamente com um ambiente do PowerApps padrão, talvez esse não seja o melhor ambiente para ser usado na sua implantação do Talent. Estratégias de integração e de testes de dados devem ser consideradas nessa etapa. Portanto, recomendamos que você leve em consideração todas as implicações para sua implementação, pois não será fácil alterar o ambiente do PowerApps posteriormente.

1. No LCS, selecione **Gerenciar ambientes**. Você será levado para o [Centro de Administração do PowerApps](https://preview.admin.powerapps.com/environments), onde você pode visualizar os ambientes existentes e criar novos ambientes.
2. Selecione **Novo ambiente**.
3. Insira um nome exclusivo para o ambiente e selecione o local para implantação.

    > [!NOTE]
    > O Talent não está disponível em todas as regiões. Portanto, certifique-se de verificar a disponibilidade antes de selecionar a localização de seu ambiente.

4. Quando for perguntado se deseja criar um banco de dados, selecione **Criar banco de dados** para criar o banco de dados do Common Data Service (CDS) que deve hospedar parte de seus dados do Talent. Criando um banco de dados você também pode integrar os aplicativos do PowerApps com o Talent.
5. Você deverá informar o nível de acesso para ser usado no banco de dados. Recomendamos que você **Restringir acesso**, pois esta opção evita que os usuários do Talent acessem dados confidenciais diretamente usando um aplicativo PowerApps.
6. O banco de dados do CDS que é criado contém dados de demonstração que adicionam endereços fictícios e funcionários inativos, entre outras informações, ao seu ambiente de produção. Para remover dados de demonstração, siga essas etapas ao terminar de criar o banco de dados de CDS:

    > [!IMPORTANT]
    > Se você já criou um banco de dados do CDS e inseriu nele dados de produção da empresa, saiba que estas etapas removem **todos** os dados do banco de dados selecionado, mesmo os dados de produção da empresa.

    1. Entre no [PowerApps](https://preview.web.powerapps.com/home).
    2. Na lista suspensa do canto superior direito, selecione o ambiente criado na etapa 2.
    3. No painel de navegação à direita, expanda **Common Data Service** e, em seguida, selecione **Entidades**.
    4. No lado direito da página, selecione o botão reticências (**…**) e depois selecione **Limpar todos os dados**.
    5. Selecione **Excluir os dados** para confirmar que deseja remover dados. Esta ação remove todos os dados de demonstração incluídos no CDS, por padrão. Também remove todos os outros dados que foram inseridos no banco de dados selecionado.

Agora você pode usar seu novo ambiente.

## <a name="grant-access-to-the-environment"></a>Conceder acesso ao ambiente
Por padrão, o administrador global que criou o ambiente tem acesso a ele. Entretanto, os usuários adicionais do aplicativo devem ter acesso explicitamente. Para conceder acesso, [adicione usuários](../dev-itpro/sysadmin/tasks/create-new-users.md) e [atribua as funções adequadas a eles](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) no ambiente do Core HR. Você também deve adicionar esses usuários ao ambiente do PowerApps, para que eles possam acessar os aplicativos do Attract e Onboard. O procedimento é descrito aqui. Se você precisar de ajuda para concluir as etapas, consulte a postagem do blog [Apresentando o centro de administração do PowerApps](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/).

Esse procedimento será concluído pelo administrador global que implantou o ambiente do Talent.

1. Abra o [Centro de Administração do PowerApps](https://preview.admin.powerapps.com/environments).
2. Selecione os ambientes adequados:
3. Na guia **Segurança**, adicione os usuários necessários à função **Criador de Ambiente**.

Observe que essa etapa final, em que você adiciona usuários ao ambiente do PowerApps, é temporária. Com o tempo, ela será concluída automaticamente conforme os usuários forem adicionados ao Core HR.

