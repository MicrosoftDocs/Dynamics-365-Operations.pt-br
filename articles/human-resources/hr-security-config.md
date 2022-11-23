---
title: Conceitos de configuração de segurança para integrações virtuais baseadas em tabelas
description: Este artigo explica uma arquitetura para a criação de uma integração entre o Microsoft Dynamics 365 Human Resources e outros sistemas.
author: twheeloc
ms.date: 11/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 219ceb0adae0cee5f74a39140ab74af9fdac1eb6
ms.sourcegitcommit: ea79bf014bbf495ac8e28db29502c8bd85a75f32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2022
ms.locfileid: "9759646"
---
# <a name="security-configuration-concepts-for-virtual-table-based-integrations"></a>Conceitos de configuração de segurança para integrações virtuais baseadas em tabelas

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve uma arquitetura para o uso de [tabelas virtuais do Microsoft Dataverse (entidades)](/dev-itpro/power-platform/virtual-entities-overview)para criar uma integração entre o Dynamics 365 Human Resources e um sistema de terceiros. O foco do artigo está na configuração de segurança e nos aspectos de autenticação e autorização necessários entre os limites do sistema para criar um sistema funcional e seguro.

## <a name="prerequisite-reference-articles"></a>Artigos de referência de pré-requisitos

Os artigos a seguir fornecem mais informações sobre os conceitos neste artigo:

- [Visão geral de entidades virtuais](/dev-itpro/power-platform/virtual-entities-overview)
- [Introdução a tabelas virtuais (entidades)](/developer/data-platform/virtual-entities/get-started-ve)
- [Usar autenticação servidor a servidor multilocatário ( Microsoft Dataverse)](/developer/data-platform/use-multi-tenant-server-server-authentication)
- [Usar autenticação OAuth com o Microsoft Dataverse (Dataverse)](/developer/data-platform/authenticate-oauth)
- [Fluxo de credenciais do cliente OAuth 2.0 na plataforma de identidade da Microsoft](/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow)
- [Autenticação e autorização](/dev-itpro/power-platform/authentication-and-authorization)

## <a name="architecture"></a>Arquitetura 

O seguinte diagrama arquitetônico mostra os principais conceitos envolvidos em uma integração que usa tabelas virtuais (entidades).

![Integração com base em tabela virtual.](./media/Hosts.jpg)

Esta é uma explicação de alguns elementos no diagrama anterior:

- **Microsoft** – a Microsoft hospeda e opera os diferentes produtos Dynamics 365 em nome de clientes.

    - **Azure Active Directory( Azure AD) locatário C** – um locatário do Azure AD que é propriedade da Microsoft. É o locatário no qual os aplicativos do Dynamics 365 estão registrados.

- **Parceiro de integração**

    - **Sistema de integração** – o sistema que está sendo integrado ao Dynamics 365. Pode ser um sistema de folha de pagamento ou qualquer sistema que dependa de dados armazenados no Dynamics 365.
    - **Adaptador** – o software ou serviço responsável por interagir com o Dynamics 365 e o sistema de integração.

        > [!NOTE]
        > Se um adaptador for usado por vários clientes Dynamics 365, a expectativa é que ele seja registrado como um aplicativo multilocatário no Azure AD.

    - Locatário A do **Azure AD** – um locatário do Azure AD que pertence ao parceiro de integração. É o locatário no qual o ID de aplicativo do adaptador está registrado.

- **Cliente mútuo** – um cliente que implementa o Dynamics 365 Human Resources e a solução do parceiro de integração.

    - **Dynamics 365 Finance ou Human Resources** – a instância específica do cliente do Dynamics 365 Finance ou Human Resources que contém os dados do cliente que o sistema de integração requer.
    - **Dataverse** – o ambiente específico do Dataverse do cliente que está conectado ao Finance ou Human Resources. O Dataverse fornece uma API Web para interação com dados do Dynamics 365.
    - Locatário B do **Azure AD** – o locatário do Azure AD do cliente. Ele funciona como o provedor de identidade (servidor de autorização) e emite tokens que autorizam os chamadores a chamar a instância do Dataverse do cliente.

## <a name="basic-request-flow"></a>Fluxo básico de solicitação

Esta seção descreve o fluxo básico de uma solicitação típica que está envolvida em uma integração. Ele faz referência ao diagrama arquitetônico anteriormente abordado neste artigo.

Uma solicitação típica requer que o adaptador consulte o Dynamics 365 para obter dados e salve e sincronize esses dados com o sistema de integração.

1. O adaptador chama a API Web do Dataverse para consultar dados relevantes.

    > [!NOTE]
    > A autenticação é um pré-requisito e a aquisição de token é uma parte principal do processo. A autenticação será descrita na seção [Autenticação e autorização em limites do sistema](#authentication-and-authorization-at-system-boundaries).

    Essa chamada é feita na API Web do Dataverse para consultar dados de aplicativos que são expostos por meio de uma tabela virtual. (Consulte "2. Sincronização inicial" e "3. Sincronização delta" no diagrama.)

2. O Dataverse trata a solicitação consultando a tabela virtual por meio do plug-in de entidade virtual ("Proxy de tabela virtual" no diagrama). A solicitação do Dataverse é encaminhada para o serviço de entidade virtual do Finance ou Human Resources a fim de consultar os dados fisicamente armazenados nos banco de dados deles.
3. O serviço de entidade virtual do Finance ou Human Resources converte a solicitação em relação à entidade virtual em uma consulta da entidade do Finance ou Human Resources que retorna a entidade virtual do Dataverse. Os dados são recuperados do banco de dados, convertidos novamente na representação da entidade do Dataverse e devolvidos ao chamador.
4. O adaptador conclui qualquer mapeamento necessário e uma conversão de dados, e faz uma chamada para o sistema de integração para persistir os dados no banco do dados do sistema de integração. (Consulte "4. Salvar dados" no diagrama.)

## <a name="authentication-and-authorization-at-system-boundaries"></a>Autenticação e autorização durante limites do sistema

A *Autenticação* valida que a identidade de um usuário ou de um aplicativo foi comprovada e confirma o usuário ou o aplicativo. A *Autorização* concede ao usuário ou ao aplicativo o direito de acessar permissões específicas no nível do aplicativo. Para obter mais informações, consulte [Autenticação e Autorização](/azure/active-directory/develop/authentication-vs-authorization).

A maioria das chamadas entre sistemas no diagrama arquitetônico, anteriormente abordadas neste artigo, envolve o adaptador. O adaptador deve autenticar-se para efetuar as seguintes chamadas:

- Chamada para o Dataverse
- A chamada para o sistema de integração

Examine os limites do sistema no diagrama. Cada solicitação da Web entre os sistemas deve ser autenticada, e as verificações de autorização no nível do aplicativo devem ser passadas antes que os dados sejam devolvidos ao chamador. Para uma solicitação de uma tabela virtual dinâmica do Dynamics 365 com respaldo do Finance ou Human Resources, as verificações de autenticação e autorização são impostas nos seguintes limites do sistema:

- A chamada entre o adaptador e o ponto de extremidade da API Web do Dataverse (OData)
- A chamada entre o plug-in da entidade virtual do Dataverse e o serviço de entidade virtual do Finance ou Human Resources

Nos dois casos, as verificações de autenticação são feitas primeiro. As verificações de autorização no nível do aplicativo são feitas para garantir que o usuário ou o aplicativo autenticado tenha os privilégios corretos no nível do aplicativo para recuperar os dados solicitados.

A autenticação para chamar o Dataverse é tratada por meio de um token de portador que deve ser incluído como um cabeçalho HTTP na solicitação da Web para o Dataverse. O adaptador deve obter um token da instância do locatário B do Azure AD. (Consulte "1. Obter token" no diagrama.) O Azure AD atua como o provedor de identidade no fluxo de autenticação.

O adaptador é autenticado ao fornecer sua identidade de aplicativo (não secreta, conforme registrado no locatário A do Azure AD) e um segredo de aplicativo ou certificado que apenas o aplicativo de adaptador possui.

Depois que o usuário ou o aplicativo for autenticado para fazer chamadas ao Dataverse, as verificações de autorização no nível do Dataverse serão realizadas em cada solicitação. Essas verificações garantem que o chamador (a identidade do aplicativo do adaptador, que está designado como "\<guid A\>" no diagrama) tenha as permissões de aplicativo apropriadas. A autorização no nível do aplicativo é gerenciada no Dataverse por meio de um usuário de aplicativo que representa o ID do aplicativo do adaptador. As permissões de nível de aplicativo são gerenciadas concedendo acesso a funções de aplicativo definidas específicas do Dataverse. Essas funções fornecem privilégios granulares para o aplicativo.

Para uma orientação mais detalhada, consulte [Usar a autenticação de servidor para servidor multilocatário](/power-apps/developer/data-platform/use-multi-tenant-server-server-authentication).

As verificações de permissão de aplicativo no nível do Dataverse são passadas, e o plug-in da entidade virtual faz uma chamada para o ponto de extremidade do serviço de entidade virtual no ambiente do Finance ou Human Resources. A autenticação de servidor para servidor (S2S) é usada para fazer essa chamada. Ela usa a identidade e o segredo que são configurados no registro de configuração da fonte de dados do Finance and Operations.

![Registro de configuração de fonte de dados do Finance and Operations no ambiente de área restrita.](./media/sandbox.jpg)

Para obter mais informações, consulte [Configurar entidades virtuais do Dataverse](/dev-itpro/power-platform/admin-reference).

A chamada do plug-in da entidade virtual do Dataverse para o Finance ou Human Resources inclui a identidade do adaptador da chamada para o Dataverse original do adaptador (a identidade designada "\<guid A\>" no diagrama arquitetônico). Se a fonte de dados da entidade virtual estiver configurada corretamente e as verificações de autenticação S2S forem passadas, o serviço de entidade virtual no Finance ou Human Resources executará a consulta no contexto do chamador original (o adaptador, \<guid A\>). As verificações de permissão de aplicativo (autorização) no nível do Finance ou Human Resources serão realizadas para garantir que o adaptador tenha os privilégios necessários para acessar as entidades de dados solicitadas por meio da consulta.

A segurança do Finance and Human Resources é gerenciada das seguintes maneiras:

1. Mapeando a identidade do adaptador (\<guid A\>) para um usuário específico do Finance ou Human Resources. Esse mapeamento é feito na página **Aplicativos do Azure Active Directory**. Para obter mais informações, consulte [Registrar seu aplicativo externo](/dev-itpro/data-entities/services-home-page.md#register-your-external-application).
2. Concedendo ao usuário do Finance ou Human Resources as funções, as obrigações e os privilégios adequados no nível do aplicativo. Para obter mais informações, consulte [Segurança baseada em função](/dev-itpro/sysadmin/role-based-security).

Se o aplicativo de adaptador (\<guid A\>) receber os privilégios necessários para acessar os dados solicitados, ocorrerão os seguintes eventos:

1. A consulta será executada.
2. Os dados serão convertidos novamente na página da entidade do Dataverse.
3. Os dados serão retornados ao adaptador.

> [!IMPORTANT]
> Durante o desenvolvimento, o adaptador pode ser executado usando um usuário do Finance ou Human Resources que tem a função de administrador. No entanto, em um ambiente de produção, o adaptador nunca deve ser executado com privilégios de Administrador.

## <a name="key-takeaways"></a>Principais considerações

Aqui estão algumas implicações importantes da arquitetura de tabela ou entidade virtual:

- A configuração de segurança para tabelas virtuais com o respaldo de Recursos Humanos é gerenciada no sistema Human Resources.
- O cliente ("Cliente mútuo" no diagrama arquitetônico anteriormente visto neste artigo) tem controle total sobre os privilégios concedidos à identidade do adaptador de integração (designado "\<guid A\>" no diagrama).
- O cliente é responsável pela configuração de segurança correta de seu ambiente de Recursos Humanos. O parceiro de integração que cria o adaptador deve fornecer orientação sobre os privilégios que o adaptador exige.
