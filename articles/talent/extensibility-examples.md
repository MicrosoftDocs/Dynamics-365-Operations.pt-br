---
title: Estender o Talent usando o PowerApps e o Microsoft Flow — cenários de exemplo
description: Este tópico descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 for Talent que usam o Microsoft PowerApps e o Microsoft Flow.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 for Talent;PowerApps;Flow;Common Data Service
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2019-03-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: c113b0f4ab2c8e44d00fcfca3f0a6ca828a854ae
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517314"
---
# <a name="extend-talent-by-using-powerapps-and-microsoft-flow---example-scenarios"></a>Estender o Talent usando o PowerApps e o Microsoft Flow — cenários de exemplo

Este tópico descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 for Talent que usam o Microsoft PowerApps e o Microsoft Flow. Você pode importar o pacote da solução que está associado a cada exemplo para seu ambiente do PowerApps. Depois, você pode usar os pacotes como orientação ou como pontos de partida para implementar cenários aplicáveis à sua organização.

> [!IMPORTANT]
> Se quiser usar os modelos e o aplicativo que estão descritos neste tópico "no estado em que se encontram", certifique-se de testá-los para garantir que cubram todos os cenários que são específicos à sua implementação.


## <a name="prerequisites"></a>Pré-requisitos

- Para importar os pacotes, os usuários devem ter a permissão **Criador de Ambiente**.
- Para exportar ou importar aplicativos, os usuários devem ter uma licença do plano 2 do PowerApps ou uma licença de avaliação do plano 2 do PowerApps.

## <a name="flow--form-connect"></a>Flow — Form Connect

O modelo **Flow — Form Connect** pode ser usado para ler dados do Microsoft Forms e armazená-los em uma entidade do Common Data Service.

Esse método pode ser estendido para que possa ser usado em outros cenários. Eis alguns exemplos:

- Capturar avaliações de candidatos.
- Capturar resultados de questionários de cursos.
- Compilar uma biblioteca de perguntas de entrevista para os administradores de recursos humanos (RH).
- Capturar a avaliação de um candidato do processo de entrevista

No Microsoft Dynamics 365: Attract, os formulários podem aparecer no Portal do candidato, e os candidatos podem preencher os detalhes. Os formulários podem ser incorporados como atividades em um modelo de trabalho.

Quando um candidato envia um formulário, o Microsoft Flow captura o envio do formulário, lê os dados e armazena-os na entidade do Common Data Service.

Para baixar o modelo **Flow — Form Connect** e a Estrutura de Entidades Personalizadas, acesse [Flow — Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) no Centro de Download da Microsoft.

## <a name="initiate-and-extract-parameters-passed-to-powerapps"></a>Iniciar e extrair os parâmetros transmitidos para o Powerapps

O modelo **Iniciar e extrair os parâmetros transmitidos para o Powerapps** pode ser usado como ponto de partida para qualquer cenário de PowerApps que seja específico para o Attract. Ele inclui todos os parâmetros padrão que são transmitidos pelo Attract, como, **Solicitação de emprego**, **ID do Candidato**e **JobID**.

Esse modelo pode ser usado para recuperar um formulário de avaliação do candidato, de modo que um gerente de contratação possa exibir a avaliação que o candidato preencheu.

Os aplicativos criados usando o PowerApps podem ser incorporados no modelo de trabalho no Attract.

Para baixar o modelo **Iniciar e extrair os parâmetros transmitidos para o Powerapps** e a Estrutura de Entidades Personalizadas, acesse [Iniciar e extrair os parâmetros transmitidos para o Powerapps](https://go.microsoft.com/fwlink/?linkid=2081991) no Centro de Download da Microsoft.

## <a name="integration-with-office-365"></a>Integração ao Office 365

O aplicativo **Integração com o Office 365** pode ser usado para extrair informações da equipe para usuários conectados a partir do Microsoft Office 365. Ele faz referência aos trabalhadores no Talent para extrair detalhes de registros de entrada e de saída e gravações de exceção. Os detalhes de registros de entrada e de saída são armazenados em entidades personalizadas do Common Data Service. A suposição é que esses detalhes são preenchidas por sistemas de terceiros por meio da integração.

Esse aplicativo pode ser estendido para que possa ser usado em outros cenários. Por exemplo, ele pode ser usado para mostrar informações de férias da equipe, eventos do calendário e todos os eventos específicos da equipe.

Para baixar o aplicativo **Integração com o Office 365** e a Estrutura de Entidades Personalizadas, acesse [Integração com Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) no Centro de Download da Microsoft.

## <a name="flow--email-notification"></a>Flow — Notificação por email

O modelo **Flow — Notificação por email** pode ser usado em cenários de notificação por email. Ele pode ser usado para acionar o envio de emails de notificação aos candidatos que a equipe de contratação rejeita durante qualquer estágio do processo de recrutamento.

Esse modelo pode ser estendido para controlar alterações no estágio do candidato durante o processo de recrutamento e para enviar notificações à equipe de contratação e ao candidato.

Em geral, para entidades que são armazenados no Common Data Service, os fluxos podem ser configurados para enviar notificações de eventos que ocorrem no Core HR, no Attract ou no Dynamics 365 Talent: Onboard.

Para baixar o modelo **Flow — Notificação por email**, acesse [Flow — Notificação por email](https://go.microsoft.com/fwlink/?linkid=2082103) no Centro de Download da Microsoft.

## <a name="flow--sql-connect-and-execute"></a>Flow — Conectar ao SQL e executar

O modelo **Flow — Conectar ao SQL e executar** conecta-se ao Microsoft SQL Server e habilita a execução de consultas SQL.

Embora esse modelo tenha sido criado para ler e atualizar tabelas SQL, ele também pode ser estendido para que possa ser usado em outros cenários. Por exemplo, ele pode ser usado para preencher uma tabela de preparação no Common Data Service com registros do SQL Server e para sincronizar periodicamente a tabela de preparação usando um push incremental do SQL Server.

Para baixar o modelo **Flow — Conectar ao SQL e executar**, acesse [Flow — Conectar ao SQL e executar](https://go.microsoft.com/fwlink/?linkid=2081789) no Centro de Download da Microsoft.

## <a name="flow--sharepoint-integration"></a>Flow — Integração do SharePoint

O modelo **Flow — Integração do SharePoint** pode ser usado para ler dados de uma lista do Microsoft SharePoint, comparar a lista com os valores de campo para qualquer entidade do Common Data Service e enviar os resultados da comparação como um email de notificação. 

Uma organização pode precisar de um conjunto de habilidades urgentemente. Essas habilidades podem ser armazenadas no SharePoint como uma lista do SharePoint. Quando um candidato se candidatar a qualquer trabalho que exija um conjunto de habilidades que esteja listado, se houver uma correspondência significativa entre as habilidade do candidato e as habilidades que estão armazenadas no SharePoint, um email de notificação será enviado. Dessa forma, as posições que são necessárias urgentemente são preenchidas com mais rapidez, pois as notificações ajudam os recrutadores a entrar em contato com os candidatos e fazer contratações em toda a organização.

Esse modelo pode ser estendido para que possa ser usado para qualquer cenário que envolva a integração do SharePoint.

Para baixar o modelo **Flow — Integração do SharePoint**, acesse [Flow — Integração do SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) no Centro de Download da Microsoft.

## <a name="admin-console-to-manage-talent-pools"></a>Administração de console para gerenciar grupos do Talent

Ao habilitar a integração com LinkedIn, Attract cria automaticamente um grupo do Talent no LinkedIn. Quando um recrutador troca InMail com um recruta por meio do LinkedIn, Attract cria um perfil para o recruta, e o recruta se torna membro de um grupo do Talent do LinkedIn. Este aplicativo do PowerApps é útil para reorganizar candidatos em grupos do Talent com base em habilidades.

Execute esse aplicativo do PowerApps como um console do administrador para realizar as tarefas a seguir:

- Listar candidatos em um grupo de talentos
- Adicionar e remover candidatos de um grupo de talentos
- Mova candidatos de um grupo do Talent para outro
- Determine se os candidatos já são parte de um grupo do Talent antes de movê-los
- Verifique as habilidades dos candidatos antes de movê-los para outros grupos do Talent

Esse aplicativo do PowerApps usa relacionamentos muitos para muitos, então você pode usá-lo como um modelo para outros cenários onde você precisa extrair registros que têm relacionamentos muitos para muitos.

Para baixar o modelo **Console de administrador para gerenciar grupos do Talent**, acesse [Console de administração para gerenciar grupos do Talent](http://www.microsoft.com/downloads/details.aspx?FamilyID=780a5eee-0e2a-4159-9a83-009f9ccdc469) no Microsoft Download Center.

## <a name="additional-resources"></a>Recursos adicionais

[A Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[Migrar aplicativos entre locatários e ambientes](https://docs.microsoft.com/en-us/power-platform/admin/environment-and-tenant-migration)
