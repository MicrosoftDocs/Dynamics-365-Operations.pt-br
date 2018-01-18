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
ms.search.form: Talent
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
ms.sourcegitcommit: 6ffb97b53f522cfe8ccd8e89df854cbc557e4f1f
ms.openlocfilehash: fadc373b2c1c06987f22d4d9c20a9ab07b0c85d5
ms.contentlocale: pt-br
ms.lasthandoff: 11/20/2017

---
# <a name="provision-microsoft-dynamics-365-for-talent"></a>Provisionar Microsoft Dynamics 365 for Talent
Este tópico o orienta através do processo de provisionar um novo ambiente para Microsoft Dynamics 365 for Talent. Este tópico pressupõe que você adquiriu o Talent por meio do Provedor de Soluções na Nuvem ou do contrato de arquitetura da empresa (EA). Se você tiver uma licença existente do Microsoft Dynamics 365 que já inclua o plano do serviço do Talent e não puder concluir as etapas deste tópico, entre em contato com o Suporte.

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

    Seu novo ambiente aparece na lista de ambientes no painel de navegação à esquerda. Porém, você não pode começar a usar o ambiente enquanto o status de implantação não for atualizado para **Implantado**. Este processo normalmente leva alguns minutos. Se o provisionamento falhar, você deve contatar o suporte.

6. Selecione **Fazer logon no Talent** para usar o novo ambiente.

> [!NOTE]
> Se os requisitos finais ainda não foram aprovados, você pode implantar uma instância de teste do Talent no projeto. Você pode usar esta instância para testar a solução até que seja aprovada. Se usar o novo ambiente para teste, você deve repetir este procedimento para criar um ambiente de produção.

## <a name="create-a-new-powerapps-environment-if-required"></a>Crie um novo ambiente do PowerApps (se necessário)
1. Selecione **Gerenciar Ambientes** no LCS. Você irá para o [Centro de administração de PowerApps](https://preview.admin.powerapps.com/environments), onde você pode exibir os ambientes existentes e criar novos ambientes.
2. Selecione o botão (**+**) **Novo ambiente**.
3. Insira um nome exclusivo para o ambiente e selecione o local para implantação.

    > [!NOTE]
    > O Talent não está disponível em todas as regiões. Portanto, certifique-se de verificar a disponibilidade antes de selecionar a localização de seu ambiente.

4. Quando for perguntado se deseja criar um banco de dados, selecione **Criar banco de dados** para criar o banco de dados do Common Data Service (CDS) que deve hospedar parte de seus dados do Talent. Criando um banco de dados você também pode integrar os aplicativos do PowerApps com o Talent.
5. Será perguntado sobre o nível de acesso que deseja usar para o banco de dados. Recomendamos que você **Restringir acesso**, pois esta opção evita que os usuários do Talent acessem dados confidenciais diretamente usando um aplicativo PowerApps.
6. O banco de dados de CDS que é criado contém dados de demonstração. Esses dados de demonstração são úteis porque você pode usar a empresa dos dados de demonstração para testar ou para criar registros de tarefas ou guias de tarefas. Porém, os dados de demonstração adicionam endereços fictícios e de funcionários inativos e outras informações, ao seu ambiente de produção. Para remover dados de demonstração, siga essas etapas ao terminar de criar o banco de dados de CDS:

    > [!IMPORTANT]
    > Se você já criou um banco de dados de CDS e inseriu alguns dados de produção da empresa nele, saiba que estas etapas removem **todos** os dados do banco de dados selecionado, mesmo os dados de produção da empresa.

    1. Entre no [PowerApps](https://preview.web.powerapps.com/home) e vá para o ambiente criado na etapa 2.
    2. Selecione **Entidades**. No lado direito da página, selecione o botão reticências (**…**) e depois selecione **Limpar todos os dados**.
    3. Selecione **Excluir os dados** para confirmar que deseja remover dados. Esta ação remove todos os dados de demonstração incluídos no CDS, por padrão. Também remove todos os outros dados que foram inseridos no banco de dados selecionado.

Agora você pode usar seu novo ambiente.

