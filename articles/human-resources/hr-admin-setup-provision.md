---
title: Provisionar o Human Resources
description: Este tópico explica o processo de provisionar um novo ambiente de produção para o Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0c856bca32c3dee44469c098961d85b4d8cb70a6
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8060402"
---
# <a name="provision-human-resources"></a>Provisionar o Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este tópico explica o processo de provisionar um novo ambiente de produção para o Microsoft Dynamics 365 Human Resources. 

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar o provisionamento de um novo ambiente de produção, os seguintes pré-requisitos devem estar em vigor:

- Você adquiriu o Human Resources por meio de um Provedor de Soluções na Nuvem (CSP) ou de um contrato de arquitetura da empresa (EA). Se você tiver uma licença existente do Microsoft Dynamics 365 que já inclua o plano do serviço do Human Resources e não puder concluir as etapas deste tópico, entre em contato com o Suporte.

- O administrador global deve ter entrado no [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com) (LCS) e criado um novo projeto Human Resources. 

## <a name="provision-a-human-resources-trial-environment"></a>Provisionamento de um ambiente de teste de Recursos Humanos

Antes de provisionar sua primeira área restrita ou ambiente de produção, pode ser interessante provisionar um [ambiente de teste de Recursos Humanos](https://go.microsoft.com/fwlink/p/?LinkId=2115962) para validar a funcionalidade de Recursos Humanos. Os ambientes de avaliação contêm dados fictícios que podem ser usados para explorar o programa de forma segura. Embora um ambiente de avaliação seja propriedade do usuário que o solicitou, outros usuários podem ser convidados por meio da experiência de administração do sistema para o Human Resources. 

Os ambientes de avaliação fornecem a capacidade de avaliar a funcionalidade de recursos humanos para indivíduos que ainda não têm acesso a um ambiente de Recursos Humanos. Se você estiver provisionando um ambiente de avaliação e o usuário autenticado já tiver acesso a um ou mais ambientes de Recursos Humanos existentes, o usuário será redirecionado para o ambiente existente ou para a lista de ambientes.

Ambientes de avaliação não devem ser usados como ambientes de produção. Eles estão limitados a um período de avaliação de 30 dias. Quando um ambiente de avaliação expirar, o ambiente e todos os dados que estão nele serão excluídos e não poderão ser recuperados. O ambiente não pode ser convertido em uma área restrita ou ambiente de produção. Você pode inscrever-se para um novo ambiente de avaliação após o ambiente existente expirar.

Ao criar um ambiente de avaliação do Human Resources, um ambiente de avaliação do Power Apps também é criado no locatário e vinculado ao ambiente do Human Resources. O ambiente do Power Apps, chamado de "TestDrive", tem o mesmo período de avaliação do ambiente do Human Resources.

> [!NOTE]
> O provisionamento de um ambiente de avaliação do Human Resources falhará se o usuário autenticado não tiver permissão para criar ambientes de avaliação do Power Apps. O usuário precisa ser incluído no grupo de usuários que pode criar ambientes de avaliação no centro de administração do Power Platform. Para obter mais informações, consulte [Controlar quem pode criar e gerenciar ambientes no centro de administração do Power Platform](/power-platform/admin/control-environment-creation).

## <a name="plan-human-resources-environments"></a>Planejar ambientes do Human Resources

Antes de criar seu primeiro ambiente do Human Resources, você deve planejar cuidadosamente as necessidades ambientais do seu projeto. Uma assinatura básica do Human Resources inclui dois ambientes: um ambiente de produção e um ambiente de área restrita. Dependendo da complexidade do projeto, talvez você precise comprar ambientes adicionais de área restrita para apoiar as atividades do projeto. 

Considerações para ambientes adicionais:

- **Migração de dados**: Talvez seja necessário considerar um ambiente adicional para atividades de migração de dados para permitir que o ambiente de área restrita seja usado para fins de teste durante todo o projeto. Ter um ambiente adicional permite que as atividades de migração de dados continuem, enquanto as atividades de teste e configuração ocorrem simultaneamente em um ambiente diferente.
- **Integração**: Talvez seja preciso considerar um ambiente adicional para configurar e testar integrações. Isso pode incluir integrações nativas, como as integrações do Ceridian Dayforce LinkedIn Talent Hub, ou integrações personalizadas, como as de folha de pagamento, sistemas de rastreamento de candidatos ou sistemas e provedores de benefícios.
- **Treinamento**: Talvez você precise de um ambiente separado que seja configurado com um conjunto de dados de treinamento para treinar funcionários sobre o uso do novo sistema. 
- **Projeto multi-fase**: Talvez precise de um ambiente adicional para dar suporte a configuração, migração de dados, testes ou outras atividades em uma fase de projeto que é planejada após a ativação inicial do projeto.

 > [!IMPORTANT]
 > Ao considerar seu ambiente, recomendamos o seguinte:
 > - Use seu ambiente de produção em todo o projeto como o ambiente de configuração OURO. Isso é importante porque você não pode copiar um ambiente de área restrita em um ambiente de produção. Portanto, ao ser ativado, seu ambiente OURO é o ambiente de produção. Você concluirá as atividades de substituição nesse ambiente.</br></br>
 > - Use sua área restrita ou outro ambiente para realizar uma simulação de substituição antes da ativação. Você pode fazer isso atualizando o ambiente de produção com a configuração OURO no ambiente de área restrita.</br></br>
 > - Mantenha uma lista de verificação detalhada de substituição que inclua cada um dos pacotes de dados necessários para migrar os dados finais para o ambiente de produção durante a substituição da ativação.</br></br>
 > - Use seu ambiente de área restrita em todo o projeto como o ambiente de configuração de TESTE. Se você precisar de ambientes adicionais, sua organização poderá comprá-los por um custo adicional.</br></br>

## <a name="create-an-lcs-project"></a>Criar um projeto LCS

Para usar o LCS para gerenciar seus ambientes do Human Resources, você deve criar primeiro um projeto LCS.

1. Entre no [LCS](https://lcs.dynamics.com/Logon/Index) usando a conta utilizada para inscrever-se no Human Resources.

   > [!NOTE]
   > Para garantir o provisionamento com êxito, a conta usada para provisionar o ambiente de Recursos Humanos deve ser atribuída à função **Administrador do Sistema** ou **Personalizador do Sistema** no ambiente Power Apps associado ao ambiente de Recursos Humanos. Para obter mais informações sobre atribuição de funções de segurança no Power Platform, consulte [Configurar segurança do usuário para recursos](/power-platform/admin/database-security).

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
    
3. Selecione a opção **Incluir Dados de Demonstração**, se quiser que o ambiente inclua o mesmo conjunto de dados de demonstração usado no ambiente de Avaliação do Human Resources. Dados de demonstração são interessantes para ambientes de demonstração ou de treinamento de longo prazo, e nunca devem ser usados em ambientes de produção. Você deve selecionar esta opção na implantação inicial. Não é possível atualizar uma implantação já existente depois.

4. O Human Resources sempre é provisionado em um ambiente do Microsoft Power Apps para permitir a integração e extensibilidade do Power Apps. Leia a seção "Selecionando um ambiente do Power Apps" deste artigo antes de prosseguir. Se você ainda não tem um ambiente do Power Apps, selecione Gerenciar ambientes no LCS ou Acesse o Centro de administração do Power Apps. Em seguida, siga as etapas para [Criar um ambiente do Power Apps](/powerapps/administrator/create-environment).

5. Selecione o ambiente ao qual provisionar o Human Resources.

6. Selecione **Sim** para concordar com os termos e começar a implantação.

   Seu novo ambiente aparece na lista de ambientes no painel de navegação à esquerda. Porém, você não pode começar a usar o ambiente enquanto o status de implantação não for atualizado para **Implantado**. Este processo normalmente leva alguns minutos. Se ocorrer uma falha no processo de provisionamento, você deve entrar em contato com o Suporte.

7. Selecione **Fazer logon no Human Resources** para usar o novo ambiente.

    > [!NOTE]
    > Se os requisitos finais ainda não foram aprovados, você pode implantar uma instância de teste do Human Resources no projeto. Você pode usar esta instância para testar a solução até que seja aprovada. Se usar o novo ambiente para teste, você deve repetir este procedimento para criar um ambiente de produção.

## <a name="select-a-power-apps-environment"></a>Selecionar um ambiente do Power Apps

Você pode integrar e estender o uso de dados do Human Resources usando as ferramentas do Power Apps. Para obter mais informações sobre os ambientes do Power Apps, incluindo escopo do ambiente, acesso ao ambiente e criação e escolha do ambiente, consulte [Anunciando ambientes do Power Apps](https://powerapps.microsoft.com/blog/powerapps-environments/). 

Use as seguintes orientações ao determinar para qual ambiente do Power Apps o Human Resources será implantado: 

1. No LCS, selecione **Gerenciar ambientes**. Você também pode ir diretamente para o Centro de Administração do Power Apps, onde você pode visualizar os ambientes existentes e criar novos.

2. Um ambiente único do Human Resources é mapeado para um ambiente único do Power Apps.

3. Um ambiente do Power Apps contém o Human Resources, com os aplicativos correspondentes do Power Apps, Power Automate e Dataverse. Se o ambiente do Power Apps for excluído, os aplicativos contidos nele também serão. Ao provisionar um ambiente do Human Resources, é possível provisionar um ambiente de **Teste** ou **Produção**. Escolha o tipo de ambiente baseado em como o ambiente será usado. 

4. Estratégias de teste e integração de dados devem ser consideradas, como Área restrita, UAT ou Produção. Leve em consideração as implicações para sua implantação, pois não será fácil alterar qual ambiente do Human Resources será mapeado para um ambiente do Power Apps.

5. Os seguintes ambientes do Power Apps não podem ser usados para o Human Resources. Eles são filtrados a partir da lista de seleção dentro do LCS:
 
    - Ambientes **do Power Apps padrão** - Enquanto cada locatário é provisionado automaticamente com um ambiente do Power Apps padrão, não recomendamos usá-los com Human Resources. Todos os usuários de locatários podem acessar o ambiente do Power Apps e podem acidentalmente danificar dados de produção ao testar e explorar com integrações Power Apps ou Power Automate.
   
    - **Ambientes de avaliação** - Esses ambientes são criados com uma data de validade. Após o vencimento, seu ambiente e quaisquer instâncias do Human Resources contidas nele serão removidos automaticamente.
   
    - **Geografias sem suporte** - o ambiente deve estar em uma geografia com suporte. Para obter mais informações, consulte [Geografias com suporte](hr-admin-setup-provision.md#supported-geographies).

6. Recursos de gravação dupla para a integração de dados de Recursos Humanos com o ambiente do Power Apps só poderão ser usados se a opção **Habilitar aplicativos do Dynamics 365** estiver selecionada para o ambiente. Consulte a [Home page da gravação dupla](../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md) para obter mais informações sobre gravação dupla.

    > [!NOTE]
    > A opção **Habilitar aplicativos do Dynamics 365** deve ser selecionada quando o ambiente do Power Apps é criado. Se a opção não estiver selecionada no momento do provisionamento, não será possível usar a gravação dupla para integrar dados entre o Dynamics 365 Human Resources e o ambiente Power Apps ou instalar aplicativos do Dynamics 365, como o Dynamics 365 Sales e o Field Service, no ambiente. Esta opção não é reversível. Para obter mais informações, consulte [Algumas considerações importantes ao criar um novo ambiente](//power-platform/admin/create-environment#some-important-considerations-when-creating-a-new-environment) no site de documentação do Power Platform.

7. Depois de determinar o ambiente correto a ser usado, você poderá continuar com o processo de provisionamento. 

### <a name="supported-geographies"></a>Geografias com suporte

Os Recursos Humanos atualmente dá suporte às seguintes geografias:

- Estados Unidos
- Europa
- Reino Unido
- Austrália
- Canadá
- Ásia 

Ao criar um ambiente de Recursos Humanos, selecione um ambiente do Power Apps para associar ao ambiente de Recursos Humanos. O ambiente de Recursos Humanos é provisionado na mesma geografia do Azure que o ambiente do Power Apps selecionado. Você pode selecionar onde o ambiente de Recursos Humanos e o banco de dados residem fisicamente, selecionando a geografia ao criar o ambiente do Power Apps que será associado ao ambiente de Recursos Humanos.

Você pode selecionar a *geografia* do Azure na qual o ambiente é provisionado, mas não pode selecionar a *região* específica do Azure. A automação determina a região específica na geografia na qual o ambiente é criado para otimizar o balanceamento de carga e o desempenho. Você pode encontrar informações sobre geografias e regiões do Azure na documentação sobre [geografias do Azure](https://azure.microsoft.com/global-infrastructure/geographies).

Os dados para o ambiente de Recursos Humanos sempre estarão contidos na geografia do Azure na qual foram criados. No entanto, nem sempre eles estarão contidos na mesma região do Azure. Para fins de recuperação de desastre, os dados serão replicados na região principal do Azure e em uma região de failover secundária na geografia.

 > [!NOTE]
 > Não há suporte à migração de um ambiente de Human Resources de uma região do Azure para outra.

## <a name="grant-access-to-the-environment"></a>Conceder acesso ao ambiente

Por padrão, o administrador global que criou o ambiente tem acesso a ele. Os usuários adicionais do aplicativo devem ter acesso explicitamente. Você deve adicionar usuários e atribuir a eles as funções adequadas no ambiente do Human Resources. Para obter mais informações, consulte [Criar novos usuários](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [Atribuir usuários a funções de segurança](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
