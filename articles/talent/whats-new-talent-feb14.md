---
title: Novidades ou alterações no Dynamics 365 for Talent (14 de fevereiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-02-14
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1db7d032eade3f996e0554e64d6ea0704a347ed8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517308"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-14-2019"></a>Novidades ou alterações no Dynamics 365 for Talent (14 de fevereiro de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve os recursos novos ou alterados no Talent.

## <a name="changes-in-attract"></a>Alterações no Attract
Correção de bug menores estão incluídas nesta versão.

## <a name="changes-in-onboarding"></a>Alterações de Integração
Correção de bug menores estão incluídas nesta versão.
 
## <a name="changes-in-core-hr"></a>Alterações no Core HR 
**Compilação 8.1.2146**

### <a name="employee-fixed-compensation-entity-doesnt-export-all-records"></a>A entidade de remuneração fixa do funcionário não exportará todos os registros
Com essa alteração, a entidade **Remuneração fixa do funcionário** agora exportará todos os registros. A entidade pode ser usada para criar e atualizar registro de remuneração fixa existente para funcionários. 

### <a name="employment-end-date-doesnt-honor-employee-preferred-time-zone-settings"></a>A data final do emprego não honra as configurações de fuso horário preferenciais do funcionário
As datas de término de emprego agora honram o fuso horário de preferência do usuário ao criar ou encerrar o emprego com uma empresa.
 
### <a name="uk-addresses-display-in-analytics-as-eastern-switzerland-addresses"></a>Endereços do Reino Unido são exibidos no Analytics como endereços no leste da Suíça
Nessa versão, uma alteração foi feita para corrigir mau alinhamento em endereços no relatório **Gerenciamento de Pessoal** "Número de funcionários por local".
 
### <a name="termination-code-is-not-populated-on-the-worker-position-assignment-record-when-ending-the-position"></a>O código de demissão não foi preenchido no registro de atribuição da posição do trabalhador quando a posição é encerrada
Uma alteração foi feita para deixar padrão o código "Motivo da demissão" ao finalizar a atribuição de posição dos funcionários.

### <a name="new-entity-created-for-job-compensation-levels"></a>Nova entidade criada para níveis de remuneração de trabalho
Uma nova entidade de estrutura de gerenciamento de dados (DMF) foi criada. A entidade ajuda na criação e atualiza para níveis de compensação, valores de mercado e informações de pesquisa para cada trabalho definido no sistema.
