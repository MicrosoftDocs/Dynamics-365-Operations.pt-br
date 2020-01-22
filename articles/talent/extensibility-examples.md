---
title: Estender o Talent com o Power Apps e o Power Automate
description: Este tópico descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 Talent que usam o Microsoft Power Apps e o Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 05/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: Dynamics 365 Talent;PowerApps;Flow;Common Data Service
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
ms.openlocfilehash: 6c8a583a93c2ceb70d8c3b0e0047e2bf2047b56d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898308"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a>Estender o Talent com o Power Apps e o Power Automate

Este tópico descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 Talent que usam o Microsoft Power Apps e o Microsoft Power Automate. Você pode importar o pacote da solução associado a cada exemplo para o seu ambiente do Power Apps. Depois, você pode usar os pacotes como orientação ou como pontos de partida para implementar cenários aplicáveis à sua organização.

> [!IMPORTANT]
> Se quiser usar os modelos e o aplicativo que estão descritos neste tópico "no estado em que se encontram", certifique-se de testá-los para garantir que cubram todos os cenários que são específicos à sua implementação.


## <a name="prerequisites"></a>Pré-requisitos

- Para importar os pacotes, os usuários devem ter a permissão **Criador de Ambiente**.
- Para exportar ou importar aplicativos, os usuários devem ter uma licença do plano 2 do Power Apps ou uma licença de avaliação do plano 2 do Power Apps.

## <a name="power-automate--form-connect"></a>Power Automate – Conexão a Formulário

O modelo **Power Automate – Conexão a Formulário** pode ser usado para ler dados do Microsoft Forms e armazená-los em uma entidade do Common Data Service.

Esse método pode ser estendido para que possa ser usado em outros cenários. Eis alguns exemplos:

- Capturar avaliações de candidatos.
- Capturar resultados de questionários de cursos.
- Compilar uma biblioteca de perguntas de entrevista para os administradores de recursos humanos (RH).
- Capturar a avaliação de um candidato do processo de entrevista

No Microsoft Dynamics 365: Attract, os formulários podem aparecer no Portal do candidato, e os candidatos podem preencher os detalhes. Os formulários podem ser incorporados como atividades em um modelo de trabalho.

Quando um candidato envia um formulário, o Microsoft Power Automate captura o envio do formulário, lê os dados e armazena-os na entidade do Common Data Service.

Para baixar o modelo **Power Automate – Conexão a Formulário** e a Estrutura de Entidades Personalizadas, acesse [Power Automate – Conexão a Formulário](https://go.microsoft.com/fwlink/?linkid=2081988) no Centro de Download da Microsoft.

## <a name="initiate-and-extract-parameters-passed-to-power-apps"></a>Iniciar e Extrair Parâmetros Passados para o Power Apps

O modelo **Iniciar e Extrair Parâmetros Passados para o Power Apps** pode ser usado como ponto de partida para qualquer cenário do Power Apps que seja específico para o Attract. Ele inclui todos os parâmetros padrão que são transmitidos pelo Attract, como, **Solicitação de emprego**, **ID do Candidato**e **JobID**.

Esse modelo pode ser usado para recuperar um formulário de avaliação do candidato, de modo que um gerente de contratação possa exibir a avaliação que o candidato preencheu.

Os aplicativos criados usando o Power Apps podem ser incorporados no modelo de trabalho no Attract.

Para baixar o modelo **Iniciar e Extrair Parâmetros Passados para o Power Apps** e a Estrutura de Entidades Personalizadas, acesse [Iniciar e Extrair Parâmetros Passados para o Power Apps](https://go.microsoft.com/fwlink/?linkid=2081991) no Centro de Download da Microsoft.

## <a name="integration-with-office-365"></a>Integração ao Office 365

O aplicativo **Integração com o Office 365** pode ser usado para extrair informações da equipe para usuários conectados a partir do Microsoft Office 365. Ele faz referência aos trabalhadores no Talent para extrair detalhes de registros de entrada e de saída e gravações de exceção. Os detalhes de registros de entrada e de saída são armazenados em entidades personalizadas do Common Data Service. A suposição é que esses detalhes são preenchidas por sistemas de terceiros por meio da integração.

Esse aplicativo pode ser estendido para que possa ser usado em outros cenários. Por exemplo, ele pode ser usado para mostrar informações de férias da equipe, eventos do calendário e todos os eventos específicos da equipe.

Para baixar o aplicativo **Integração com o Office 365** e a Estrutura de Entidades Personalizadas, acesse [Integração com Office 365](https://go.microsoft.com/fwlink/?linkid=2081787) no Centro de Download da Microsoft.

## <a name="power-automate--email-notification"></a>Power Automate – Notificação por Email

O modelo **Power Automate – Notificação por Email** pode ser usado em cenários de notificação por email. Ele pode ser usado para acionar o envio de emails de notificação aos candidatos que a equipe de contratação rejeita durante qualquer estágio do processo de recrutamento.

Esse modelo pode ser estendido para controlar alterações no estágio do candidato durante o processo de recrutamento e para enviar notificações à equipe de contratação e ao candidato.

Em geral, para entidades que são armazenadas no Common Data Service, os fluxos podem ser configurados para enviar notificações de eventos que ocorrem no Core HR, no Attract ou no Onboard.

Para baixar o modelo **Power Automate – Notificação por Email** template, acesse [Power Automate – Notificação por Email](https://go.microsoft.com/fwlink/?linkid=2082103) no Centro de Download da Microsoft.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – Conectar ao SQL e executar

O modelo **Power Automate — Conectar ao SQL e executar** conecta-se ao Microsoft SQL Server e habilita a execução de consultas SQL.

Embora esse modelo tenha sido criado para ler e atualizar tabelas SQL, ele também pode ser estendido para que possa ser usado em outros cenários. Por exemplo, ele pode ser usado para preencher uma tabela de preparação no Common Data Service com registros do SQL Server e para sincronizar periodicamente a tabela de preparação usando um push incremental do SQL Server.

Para baixar o modelo **Power Automate — Conectar ao SQL e executar**, acesse [Power Automate — Conectar ao SQL e executar](https://go.microsoft.com/fwlink/?linkid=2081789) no Centro de Download da Microsoft.

## <a name="power-automate--sharepoint-integration"></a>Integração Power Automate – SharePoint

O modelo **Integração Power Automate – SharePoint** pode ser usado para ler dados de uma lista do Microsoft SharePoint, comparar a lista com os valores de campo para qualquer entidade do Common Data Service e enviar os resultados da comparação como um email de notificação. 

Uma organização pode precisar de um conjunto de habilidades urgentemente. Essas habilidades podem ser armazenadas no SharePoint como uma lista do SharePoint. Quando um candidato se candidatar a qualquer trabalho que exija um conjunto de habilidades que esteja listado, se houver uma correspondência significativa entre as habilidade do candidato e as habilidades que estão armazenadas no SharePoint, um email de notificação será enviado. Dessa forma, as posições que são necessárias urgentemente são preenchidas com mais rapidez, pois as notificações ajudam os recrutadores a entrar em contato com os candidatos e fazer contratações em toda a organização.

Esse modelo pode ser estendido para que possa ser usado para qualquer cenário que envolva a integração do SharePoint.

Para baixar o modelo **Integração do Power Automate – SharePoint**, acesse [Integração do Power Automate – SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) no Centro de Download da Microsoft.

## <a name="referral-app"></a>Aplicativo Referral
Você pode usar o aplicativo Referral para adicionar candidatos a um grupo de talentos compartilhado. O indicador pode inserir **Nome**, **Sobrenome**, **Email** e **URL do Linkedln** ao enviar um candidato. Em seguida, os metadados de origem do candidato são preenchidos com as informações do indicador.

Você pode incorporar este aplicativo no Autoatendimento para funcionários (ESS) para enviar indicações, ou pode usá-lo como um hiperlink no portal corporativo e executá-lo como um aplicativo autônomo.

Para baixar o **Aplicativo Referral**, acesse a solução de extensibilidade do [Dynamics 365 Talent: aplicativo Referral](https://www.microsoft.com/downloads/details.aspx?FamilyID=9a59c9d1-f8a1-4d4d-b768-cfc4f4eb9d0d) no Microsoft Download Center. Você pode importar este aplicativo e personalizá-lo para adicionar funcionalidade.

## <a name="additional-resources"></a>Recursos adicionais

[A Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)

[Migrar aplicativos entre locatários e ambientes](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
