---
title: Configurar parâmetros de licença e ausência
description: Definir parâmetros de recursos humanos para licença e ausência no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2acb8502ebcab122a0a1ff21e9f5e23931026327
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008073"
---
# <a name="configure-leave-and-absence-parameters"></a>Configurar parâmetros de licença e ausência

Antes de configurar os planos de licença e ausência no Dynamics 365 Human Resources, convém verificar as configurações de todos os parâmetros de recursos humanos relacionados, incluindo:

- Sequência numérica para solicitações de licença
- Lei de família de licença e médica (FMLA)
- Configurações de auto-atendimento para funcionário para solicitações de licença e ausência
- Parâmetros de licença e ausência

## <a name="view-and-change-human-resources-parameters"></a>Exibir e alterar parâmetros de recursos humanos

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Parâmetros de recursos humanos**.

3. Na guia **Sequências numéricas**, verifique o **Código de sequência numérica** para **ID de solicitação de licença** e faça as alterações necessárias. Esta configuração determina a sequência usada para atribuir automaticamente IDs a solicitações de licença.

4. Na guia **FMLA**, verifique as configurações de FMLA e altere conforme necessário.

5. Na guia **Autoatendimento para funcionários**, indique se os gerentes podem inserir solicitações de licença e ausência em nome de seus funcionários.

6. Na guia **Licença e ausência**, verifique as configurações e altere conforme necessário.

7. Selecione **Salvar**.

## <a name="configure-calendar-parameters"></a>Configure parâmetros de calendário.

Se você tiver habilitado o recurso de visualização do calendário de licenças e ausências, será necessário configurar parâmetros adicionais. 

[!include [banner](includes/preview-feature-leave-absence.md)]

> [!NOTE]
> Para a versão de visualização em 3 de fevereiro de 2020, somente **Solicitações de licença pendentes** estão habilitadas.

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Parâmetros de recursos humanos**.

3. Na guia **Calendário**, altere as configurações de calendário, conforme necessário.

4. Selecione **Salvar**.

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)
