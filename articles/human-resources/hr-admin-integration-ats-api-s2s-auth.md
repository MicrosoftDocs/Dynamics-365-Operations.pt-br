---
title: Autenticação de servidor para servidor para a API de integração ATS
description: Este tópico descreve como configurar a autenticação de servidor para servidor para integrações com base na API de integração do Sistema de Acompanhamento de Candidato (ATS) do Dynamics 365 Human Resources.
author: jaredha
ms.date: 06/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ed76d22ab6b917c931220f3ba462f4f14cae207
ms.sourcegitcommit: bd684c9eb6de718573e6be5479e1832fe614d919
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "6373052"
---
# <a name="server-to-server-authentication-for-the-ats-integration-api"></a>Autenticação de servidor para servidor para a API de integração ATS

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve como configurar a autenticação de servidor para servidor para integrações de aplicativo com base na API de integração do Sistema de Acompanhamento de Candidato (ATS) do Dynamics 365 Human Resources. Existem algumas camadas de segurança que precisam ser gerenciadas para que a entidade de serviço obtenha acesso à tabela virtual do Microsoft Dataverse e aos dados associados. O usuário precisa receber acesso à tabela virtual do Dataverse no Microsoft Power Platform e acessar os dados no Dynamics 365 Human Resources.

## <a name="enable-access-to-dataverse-virtual-tables-in-power-platform"></a>Habilitar acesso a tabelas virtuais do Dataverse no Power Platform

A primeira etapa habilita o acesso às tabelas virtuais do Dataverse no Power Platform é configurar seu aplicativo no Power Platform para autenticação com base nos pontos de extremidade de tabela virtual do Dataverse. As etapas para isso são descritas no [Guia do desenvolvedor do Microsoft Dataverse](/powerapps/developer/data-platform).

  - Para registros de aplicativos de um único locatário: [use a autenticação de servidor para servidor de locatário único](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication)
  - Para registros de aplicativos de vários locatários: [use a autenticação de servidor para servidor de vários locatários](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication)

### <a name="creating-a-security-role-for-ats-integrations"></a>Criar um direito de acesso para integrações de ATS

Depois de criar o usuário do aplicativo, uma das etapas é atribuir ao usuário uma função de segurança que define o acesso que o aplicativo terá aos pontos de extremidade. Esta é a etapa 7 na [Criação de usuários de aplicativos](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication#application-user-creation) para registros de aplicativos de um único locatário e [Criar uma função de segurança](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication#create-a-security-role-for-the-application-user) para os registros de multilocatários. 

A função à qual você atribui o usuário do aplicativo deve ter acesso às entidades de dados usadas para a integração do ATS. Isso não existe inicialmente e, portanto, será necessário criar uma nova função de segurança. A nova função pode ser criada seguindo as etapas descritas em [Criar uma função de segurança](/power-platform/admin/create-edit-security-role#create-a-security-role).

Para a nova função, o acesso apropriado deve ser atribuído a, no mínimo, as seguintes entidades na guia **Entidades personalizadas** da nova função. Observe que talvez haja entidades adicionais que você precise adicionar se a integração usar dados de aplicativo mais extensivos. Depois que a nova função é criada, ela pode ser atribuída ao usuário do aplicativo.

  - Trabalhador base (mshr)
  - Candidatos para contratação (mshr)
  - Competência do certificado (mshr)
  - Tipo de certificado (mshr)
  - Empresa
  - Função de trabalho de remuneração (mshr)
  - Tipo de trabalho de remuneração (mshr)
  - País/regiões (mshr)
  - Departamento (mshr)
  - Competência de educação (mshr)
  - Nível de formação educacional (mshr)
  - Disciplinas de educação (mshr)
  - Requisitos educacionais (mshr)
  - Identificação (mshr)
  - Tipo de identificação (mshr)
  - Instituição (mshr)
  - Agência Emissora (mshr)
  - Remuneração de trabalho (mshr)
  - Trabalhos (mshr)
  - Nível de formação (mshr)
  - Contatos do participante (mshr)
  - Pessoas (mshr)
  - Endereços de pessoas (mshr)
  - Triagem da pessoa (mshr)
  - Tipo de posição (mshr)
  - Posições V2 (mshr)
  - Competência de experiência profissional (mshr)
  - Nível de avaliação (mshr)
  - Modelos de classificação (mshr)
  - Códigos de motivo (mshr)
  - Solicitação de recrutamento (mshr)
  - Localização da solicitação de recrutamento (mshr)
  - Posição da solicitação de recrutamento (mshr)
  - Habilidades de solicitação de recrutamento (mshr)
  - Tipo de triagem (mshr)
  - Competência da habilidade (mshr)
  - Habilidades (mshr)
  - Títulos (mshr)
  - Status militar (mshr)
  - Trabalhador (mshr)

## <a name="granting-application-permissions-to-human-resources-data"></a>Conceder permissões de aplicativo a dados de Recursos Humanos

A segunda etapa é garantir que o aplicativo receba as permissões apropriadas para os dados de Recursos Humanos ao associá-lo a um usuário no aplicativo de Recursos Humanos. Para um usuário de aplicativo, as chamadas de servidor para servidor por meio de tabelas virtuais do Dataverse são feitas no contexto da identidade do usuário (aplicativo) no Dataverse que está invocando a ação. Em seguida, o serviço de adaptador de tabelas virtuais pesquisa o usuário associado nos Recursos Humanos e executa a consulta no contexto desse usuário. Isso significa que um usuário deve ser criado nos Recursos Humanos com as funções corretas atribuídas a fim de fornecer acesso aos dados que o aplicativo de integração precisará.

Também será necessário atribuir as permissões corretas ao usuário de Recursos Humanos para usar dados de Recursos Humanos. A função **Candidatura de recrutamento** (HcmRecruitingIntegrator) está disponível com privilégios para as entidades primárias necessárias à integração com os dados de recrutamento. Esta função pode ser atribuída ao usuário do aplicativo na página **Usuários** para conceder o acesso apropriado aos dados. Para obter mais informações sobre as funções de segurança de Recursos Humanos, consulte [Segurança baseada em função](/fin-ops-core/dev-itpro/sysadmin/role-based-security).

### <a name="set-up-the-new-user-with-appropriate-permissions"></a>Configurar o novo usuário com as permissões apropriadas

Para configurar o novo usuário com as permissões apropriadas, siga estas etapas:

  1. Abra a página **Usuários** nos Recursos Humanos e selecione **Novo**.
  2. Insira um **ID de usuário** e um **Nome de usuário** para o novo usuário do aplicativo. Por exemplo, você pode inserir "RecruitingIntegration".

      > [!NOTE]
      > Se o aplicativo não tiver uma conta de usuário ou endereço de email do Microsoft Azure Active Directory (Azure AD) , você poderá colocar algo como "RecruitingApp" nos campos de endereço de email e provedor do usuário.

  3. Na Guia Rápida **Funções do usuário**, selecione a ação **Atribuir funções**.
  4. No painel **Atribuir funções a usuário**, selecione **Candidatura de recrutamento** e selecione **OK**.
  5. Salve o novo registro de usuário.

### <a name="link-the-new-human-resources-user-to-the-application"></a>Associar o novo usuário de Recursos Humanos ao aplicativo

Depois que o usuário for criado, um registro deverá ser criado para o aplicativo no formulário **Aplicativos do Azure Active Directory** para vincular o aplicativo ao usuário do Recursos Humanos.

  1. Abra o formulário **Aplicativos do Azure Active Directory** e selecione **Novo**.
  2. No campo **ID do Cliente**, insira a ID do cliente do usuário de aplicativo criado para o aplicativo.
  3. No campo **Nome**, insira o nome do aplicativo que será integrado.
  4. No campo **ID do usuário**, selecione o novo usuário de Recursos Humanos criado para a integração de recrutamento.
  5. Salve o novo registro.

Depois disso, o aplicativo terá acesso aos dados de Recursos Humanos, limitado somente aos dados necessários para recrutar as integrações de aplicativos.

## <a name="see-also"></a>Consulte também

[Candidatos de trabalho de recrutamento](hr-personnel-recruit.md)<br>
[O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Use a API Web do Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>
[Criar e atualizar conjuntos de opções usando a API Web](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
