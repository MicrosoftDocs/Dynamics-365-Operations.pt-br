---
title: Estender o Talent com o Power Apps e o Power Automate
description: Este artigo descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 Talent – Attract que usam o Microsoft Power Apps e o Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: cfdf36e9486aa4853d3bf674afa73ec3a4d1c161
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529625"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a>Estender o Talent com o Power Apps e o Power Automate

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 Talent: Attract que usam o Microsoft Power Apps e o Microsoft Power Automate. Você pode importar o pacote da solução associado a cada exemplo para o seu ambiente do Power Apps. Depois, você pode usar os pacotes como orientação ou como pontos de partida para implementar cenários aplicáveis à sua organização.

> [!IMPORTANT]
> Se quiser usar os modelos e o aplicativo que estão descritos neste artigo "no estado em que se encontram", certifique-se de testá-los para garantir que cubram todos os cenários que são específicos à sua implementação.


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

No Microsoft Dynamics 365: Attract, você pode usar formulários no portal do candidato, onde os candidatos preenchem os detalhes. Também é possível inserir formulários como atividades em um modelo de trabalho.

Quando um candidato envia um formulário, o Microsoft Power Automate captura o envio do formulário, lê os dados e armazena-os na entidade do Common Data Service.

Para baixar o modelo **Power Automate – Conexão a Formulário** e a Estrutura de Entidades Personalizadas, acesse [Power Automate – Conexão a Formulário](https://go.microsoft.com/fwlink/?linkid=2081988) no Centro de Download da Microsoft.

## <a name="power-automate--sharepoint-integration"></a>Integração Power Automate – SharePoint

O modelo **Integração Power Automate – SharePoint** pode ser usado para ler dados de uma lista do Microsoft SharePoint, comparar a lista com os valores de campo para qualquer entidade do Common Data Service e enviar os resultados da comparação como um email de notificação. 

Uma organização pode precisar de um conjunto de habilidades urgentemente. Essas habilidades podem ser armazenadas no SharePoint como uma lista do SharePoint. Quando um candidato se candidatar a qualquer trabalho que exija um conjunto de habilidades que esteja listado, se houver uma correspondência significativa entre as habilidade do candidato e as habilidades que estão armazenadas no SharePoint, um email de notificação será enviado. Isso ajuda a preencher as posições urgentemente necessárias com mais rapidez, pois as notificações ajudam os recrutadores a fazer contratações de candidatos em toda a organização.

Esse modelo pode ser estendido para que possa ser usado para qualquer cenário que envolva a integração do SharePoint.

Para baixar o modelo **Integração do Power Automate – SharePoint**, acesse [Integração do Power Automate – SharePoint](https://go.microsoft.com/fwlink/?linkid=2082109) no Centro de Download da Microsoft.

## <a name="referral-app"></a>Aplicativo Referral

Você pode usar o aplicativo Referral para adicionar candidatos a um grupo de talentos compartilhado. O indicador pode inserir **Nome**, **Sobrenome**, **Email** e **URL do LinkedIn** ao enviar um candidato. Em seguida, os metadados de origem do candidato são preenchidos com as informações do indicador.

Você pode inserir este aplicativo no Autoatendimento para funcionários a fim de enviar indicações ou pode usá-lo como um hiperlink no portal corporativo e executá-lo como um aplicativo autônomo.

Para baixar o **Aplicativo Referral**, acesse a solução de extensibilidade do [Dynamics 365 Talent: aplicativo Referral](https://www.microsoft.com/download/details.aspx?id=58497) no Microsoft Download Center. Você pode importar este aplicativo e personalizá-lo para adicionar funcionalidade.

## <a name="additional-resources"></a>Recursos adicionais

[A Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[Migrar aplicativos entre locatários e ambientes](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
