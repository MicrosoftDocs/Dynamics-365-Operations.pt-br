---
title: Sincronizar data e hora em trabalhos de importação
description: Use fusos horários UTC em trabalhos de importação para evitar problemas com conversões de fuso horário.
author: Sunil-Garg
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c0ec805a20a525989e0133e5dffb29ce3fed39
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748660"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>Sincronizar data e hora em trabalhos de importação

[!include [banner](../includes/banner.md)]

É importante definir o fuso horário do trabalho de importação como o tempo universal coordenado (UTC). Você poderá ver datas e horas inesperadas nos dados importados se usar uma configuração diferente. Sem a configuração correta, o processo de importação converte a data UTC no formato local e, em seguida, converte-a novamente.

Essa conversão dupla causa a alteração de datas entre os aplicativos. Por exemplo, a conversão dupla pode fazer com que a data inicial de um funcionário seja diferente entre o Dynamics 365 Human Resources e Dynamics 365 Finance devido a diferenças nos fusos horários locais. A definição do trabalho de importação para o UTC resolve esse problema.

1. No Dynamics 365 Finance and Operations, selecione **Gerenciamento de dados**.

2. Selecione **Importar projetos** e então selecione o projeto.

3. Em **Formato da data de origem**, selecione **CSV-Unicode**.

   [![Alterar o formato da data de origem para UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. Altere o **Fuso horário** para o **Tempo Universal Coordenado** e altere o **Idioma** para **En-US**.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]