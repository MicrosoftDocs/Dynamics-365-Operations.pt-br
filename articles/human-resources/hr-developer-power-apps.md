---
title: Estender o Talent com o Power Apps e o Power Automate
description: Este artigo descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 Human Resources que usam o Microsoft Power Apps e o Microsoft Power Automate.
author: negudava
manager: tfehr
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e6885c67f42ead34b5e10cc1b1a80a88fd2d59b9
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115357"
---
# <a name="extend-with-power-apps-and-power-automate"></a>Estender com o Power Apps e o Power Automate

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve alguns exemplos de cenários de extensibilidade para o Microsoft Dynamics 365 Human Resources que usam o Microsoft Power Apps e o Microsoft Power Automate. Você pode importar o pacote da solução associado a cada exemplo para o seu ambiente do Power Apps. Depois, você pode usar os pacotes como orientação ou como pontos de partida para implementar cenários aplicáveis à sua organização.

> [!IMPORTANT]
> Se quiser usar os modelos e aplicativos descritos neste tópico "no estado em que se encontram", certifique-se de testá-los para garantir que cubram todos os cenários que são específicos à sua implementação.

## <a name="prerequisites"></a>Pré-requisitos

- Para importar os pacotes, os usuários devem ter a permissão **Criador de Ambiente**.
- Para exportar ou importar aplicativos, os usuários devem ter uma licença do plano 2 do Power Apps ou uma licença de avaliação do plano 2 do Power Apps.

## <a name="integration-with-microsoft-365-power-automate"></a>Integração com Microsoft 365, Power Automate

O aplicativo **Integração com o Microsoft 365** pode ser usado para extrair informações da equipe para usuários conectados a partir do Microsoft 365. Ele faz referência a trabalhadores no Human Resources para extrair tipos de identificação de funcionário. Os gerentes podem verificar as datas de vencimento dos tipos de ID do funcionário. Eles também podem enviar um lembrete de email se o tipo de ID do funcionário expirar. O Power Automate integra-se ao Power Apps para enviar este lembrete. A confirmação será devolvida ao Power Apps do Power Automate quando o lembrete for enviado. Os tipos de identificação incluem a carteira do motorista, o passaporte e outros formulários aceitáveis de ID.

Você pode estender esse aplicativo para outros cenários. Por exemplo, você pode usá-lo para mostrar informações de férias da equipe, eventos do calendário e todos os eventos específicos da equipe.

Para baixar o aplicativo **Integração com o Microsoft 365, Power Automate**, vá para [Integração com o Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) no Centro de Download da Microsoft.

## <a name="power-automate--sql-connect-and-execute"></a>Power Automate – Conectar ao SQL e executar

O modelo **Power Automate — Conectar ao SQL e executar** conecta-se ao Microsoft SQL Server e habilita a execução de consultas SQL.

Embora esse modelo leia e atualize tabelas SQL, você pode estendê-las e usá-las em outros cenários. Por exemplo, você pode usá-la para preencher uma tabela de preparação no Dataverse com registros do SQL Server e para sincronizar periodicamente a tabela de preparação usando um push incremental do SQL Server.

A consulta avançada é integrada ao fluxo para habilitar a transformação de dados e o push incremental.

Para baixar o modelo **Power Automate — Conectar ao SQL e executar**, acesse [Power Automate — Conectar ao SQL e executar](https://go.microsoft.com/fwlink/?linkid=2081789) no Centro de Download da Microsoft.

## <a name="additional-resources"></a>Recursos adicionais

[A Microsoft Power Platform](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]