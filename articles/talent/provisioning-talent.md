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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: b4b54e97bdebc158adc3bc6d57a6661cd536f5fb
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Provisionar Microsoft Dynamics 365 for Talent

[!INCLUDE [banner](includes/banner.md)]

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
2. O Talent sempre é provisionado em um ambiente Microsoft PowerApps para permitir a integração e extensibilidade do PowerApps. Leia a seção “Selecionando um ambiente do PowerApps” deste tópico antes de prosseguir. 
3. Se você ainda não tiver um ambiente de PowerApps, siga as etapas da seção "Criar um novo ambiente do PowerApps (se necessário)" deste tópico, antes de continuar.

    > [!NOTE]
    > Para exibir os ambientes existentes ou criar novos ambientes, o administrador do locatário que provisiona o Talent deve ter a licença do PowerApps P2. Se sua organização não tiver uma licença de PowerApps P2, obtenha uma do CSP ou da [página de preços do PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

4. Selecione **Adicionar** e depois o ambiente para provisionar o Talent.
5. Selecione **Sim** para concordar com os termos e começar a implantação.

    Seu novo ambiente aparece na lista de ambientes no painel de navegação à esquerda. Porém, você não pode começar a usar o ambiente enquanto o status de implantação não for atualizado para **Implantado**. Este processo normalmente leva alguns minutos. Se ocorrer uma falha no processo de provisionamento, você deve entrar em contato com o Suporte.

6. Selecione **Fazer logon no Talent** para usar o novo ambiente.

> [!NOTE]
> Se os requisitos finais ainda não foram aprovados, você pode implantar uma instância de teste do Talent no projeto. Você pode usar esta instância para testar a solução até que seja aprovada. Se usar o novo ambiente para teste, você deve repetir este procedimento para criar um ambiente de produção.

> [!NOTE]
> Os ambientes do Talent que são provisionados por meio do LCS não contêm dados de demonstração configurados para tarefas de Recursos humanos (RH) ou dados específicos para o Talent. Se você requer um ambiente que contenha dados de demonstração, recomendamos que você se inscreva para uma [Avaliação grátis do Talent por 60 dias](https://dynamics.microsoft.com/en-us/talent/overview/). Embora um ambiente de avaliação seja propriedade do usuário que o solicitou, outros usuários podem ser convidados por meio da experiência de administração do sistema para o Core HR. Os ambientes de avaliação contêm dados fictícios que podem ser usados para explorar o programa de forma segura. Eles não devem ser usados como ambientes de produção. Observe que, quando o ambiente de avaliação expirar após 60 dias, todos os dados nele serão excluídos e não poderão ser recuperados. Você pode inscrever-se para um novo ambiente de avaliação após o ambiente existente expirar.

## <a name="select-a-powerapps-environment"></a>Selecione um ambiente do PowerApps

A integração entre o Talent e os ambientes do PowerApps permite que você integre e estenda o uso dos dados do Talent usando ferramentas do PowerApps. Entender a finalidade dos ambientes do PowerApps não só ajudará você a criar aplicativos para estender o Talent, mas também poderá ajudá-lo a selecionar o ambiente correto ao provisionar o Talent. Para obter mais informações sobre os ambientes do PowerApps, incluindo escopo do ambiente, acesso ao ambiente e criação e escolha do ambiente, consulte [Anunciando ambientes do PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/). 

Use as seguintes orientações ao determinar para qual ambiente do PowerApps o Talent será implantado: 
1. No LCS, selecione Gerenciar ambientes ou navegue diretamente até o Centro de Administração do PowerApps, onde você poderá exibir ambientes existentes e criar novos ambientes.
2. Um ambiente único do Talent é mapeado para um ambiente único do PowerApps.
3. Um ambiente do PowerApps “contém" o aplicativo Talent, juntamente com os aplicativos PowerApps, Flow e CDS correspondentes. Se o ambiente do PowerApps for excluído, os aplicativos contidos nele também serão.
4. Integração de dados e estratégias de testes devem ser consideradas, por exemplo: Área restrita, UAT, Produção. Portanto, recomendamos que você leve em consideração as várias implicações para sua implantação, pois não será fácil alterar qual ambiente do Talent será mapeado para um ambiente do PowerApps posteriormente.
5. Os seguintes ambientes do PowerApps não podem ser usados para o Talent e serão filtrados da lista de seleção no LCS:
 
    **Ambientes do CDS 2.0** O CDS 2.0 estará disponível publicamente em 21 de março de 2018; no entanto, o Talent ainda não oferece suporte ao CD 2.0. Embora você possa exibir e criar bancos de dados CDS 2.0 no Centro de Administração do PowerApps, eles não serão utilizáveis no Talent. A opção de usar ambientes do CDS 2.0 nas implantações do Talent estará disponível em uma data posterior.
   
   > [!Note]
   > Para diferenciar entre ambientes do CDS 1.0 e do 2.0 no portal de administração, selecione um ambiente e examine os **Detalhes**. Todos os ambientes do CDS 2.0 fazem referência ao fato de que “Você pode gerenciar essas configurações no Centro de Administração do Dynamics 365”, apontam a uma versão de instância e não têm nenhuma guia de Banco de dados. 
 
   **Ambientes padrão do PowerApps** Embora cada locatário seja provisionado automaticamente com um ambiente padrão do PowerApps, não é recomendável usá-lo com o Talent, pois todos os usuários do locatário têm acesso ao ambiente do PowerApps e poderão corromper involuntariamente os dados de produção ao testar e explorar com integrações do PowerApps ou do Flow.
   
   <strong>Ambientes de test drive</strong> Os ambientes com um nome como ‘TestDrive – alias@domain' são criados com um período de vencimento de 60 dias e expirarão após esse tempo, resultando na remoção automática do seu ambiente.
   
   **Regiões sem suporte** No momento, o Talent tem suporte apenas nas seguintes regiões: Estados Unidos, Europa ou Austrália.
  
6. Nenhuma ação específica será necessária depois que você determinar o ambiente correto a ser usado. Continue com o processo de provisionamento. 
 
## <a name="create-a-new-powerapps-environment-if-required"></a>Crie um novo ambiente do PowerApps (se necessário)

Execute um script do PowerShell para criar um novo ambiente do PowerApps para o Talent no contexto do administrador do locatário, que tem a licença do plano 2 do PowerApps. O script automatiza as seguintes etapas:


 + Criação de um ambiente do PowerApps
 + Criação de um banco de dados CDS 1.0
 + Limpe todos os dados de exemplo no banco de dados CDS 1.0


Siga estas instruções para executar o script:

1. Baixe o arquivo ProvisionCDSEnvironment.zip do seguinte local: [Scripts de ProvisionCDSEnvironment](https://go.microsoft.com/fwlink/?linkid=870436)  

2. Descompacte todo o conteúdo do arquivo ProvisionCDSEnviroinment.zip em uma pasta.

3. Execute o programa Windows PowerShell ou Windows PowerShell ISE como administrador.

   Visite o tópico [Configurar a política de execução](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) para saber mais sobre como configurar a política de execução para que os scripts possam ser executados.
  
4. No PowerShell, navegue até a pasta na qual você descompactou o arquivo e execute o seguinte comando, substituindo valores conforme direcionado abaixo:
 
   ```.\ProvisionCDSEnvironment -EnvironmentName MyNewEnvironment -Location YourLocation```

    
   **MyNewEnvironment** deve ser substituído pelo nome do ambiente. Esse nome aparecerá no LCS e ficará visível quando os usuários selecionarem qual ambiente do Talent desejam usar. 

   **YourLocation** deve ser substituído por uma das regiões com suporte para o Talent: Estados Unidos, Europa, Austrália. 

   **-Detalhado** é opcional e fornecerá informações detalhadas para enviar ao suporte caso você encontre algum problema.

5. Continue com o processo de provisionamento.
 


## <a name="grant-access-to-the-environment"></a>Conceder acesso ao ambiente
Por padrão, o administrador global que criou o ambiente tem acesso a ele. Entretanto, os usuários adicionais do aplicativo devem ter acesso explicitamente. Para conceder acesso, [adicione usuários](../dev-itpro/sysadmin/tasks/create-new-users.md) e [atribua as funções adequadas a eles](../dev-itpro/sysadmin/tasks/assign-users-security-roles.md) no ambiente do Core HR. Você também deve adicionar esses usuários ao ambiente do PowerApps, para que eles possam acessar os aplicativos do Attract e Onboard. O procedimento é descrito aqui. Se você precisar de ajuda para concluir as etapas, consulte a postagem do blog [Apresentando o centro de administração do PowerApps](https://powerapps.microsoft.com/en-us/blog/introducing-admin-center-for-powerapps/).

Esse procedimento será concluído pelo administrador global que implantou o ambiente do Talent.

1. Abra o [Centro de Administração do PowerApps](https://preview.admin.powerapps.com/environments).
2. Selecione os ambientes adequados:
3. Na guia **Segurança**, adicione os usuários necessários à função **Criador de Ambiente**.

    Observe que essa etapa final, em que você adiciona usuários ao ambiente do PowerApps, é temporária. Com o tempo, ela será concluída automaticamente conforme os usuários forem adicionados ao Core HR.

