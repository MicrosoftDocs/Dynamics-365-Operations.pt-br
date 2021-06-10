---
title: Novidades ou alterações no Dynamics 365 Human Resources (18 de fevereiro de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 18 de fevereiro de 2020.
author: andreabichsel
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 62b5890f02b6b9598ba5a87e25745fa7633df769
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051200"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (18 de fevereiro de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.2903. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="platform-update-32"></a>Update 32 para plataforma 

A atualização de plataforma 32 já está disponível. Para obter mais informações, consulte [Novidades ou alterações na Atualização de plataforma 32 para o Finance and Operations (fevereiro de 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md).

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a>Os valores de pesquisa são lembrados no momento da alteração das opções de exibição no formulário simplificado de funcionário (383833)

O novo formulário **Trabalhador** agora lembra os valores de pesquisa quando você altera as opções de exibição e aplica as alterações.

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a>Os blocos de resumo do gerenciamento de remuneração no recurso de visualização são redirecionados para a forma incorreta (401861)

Os blocos de gerenciamento de remuneração fixa e variável agora exibem os registros corretos no novo formulário **Trabalhador**. Aplica-se somente ao recurso de visualização do formulário simplificado de funcionário. É possível habilitar esse recurso de visualização em **Gerenciamento de recursos**. Para obter mais informações, consulte [Gerenciar recursos](hr-admin-manage-features.md).

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a>Campo Status vazio para alguns registros de solicitação de licença no Dataverse (414915)

Essa alteração corrige um problema no Dataverse quando o campo **Status** em uma solicitação de licença é definido como **Revisão**. O Dataverse agora reflete o status.

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a>Análise de lacuna de habilidade só é possível para o trabalho atribuído (411390)

Agora você pode fazer uma análise de lacuna de habilidade em qualquer trabalho definido no Human Resources.

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a>A moeda do sistema não é sincronizada do Dataverse para o Human Resources em novos ambientes (418011)

A moeda do sistema no Dataverse agora pode ser sincronizada com o Human Resources.

## <a name="in-preview"></a>Em visualização

- [Recursos de visualização de licenças e ausências](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [Recursos de visualização do gerenciamento de benefícios](hr-benefits-management-overview.md)

## <a name="coming-soon"></a>Em breve

### <a name="updated-dataverse-solution"></a>Solução Dataverse atualizada

Uma nova solução de Dataverse estará disponível em breve com as seguintes alterações:

| Descrição | Troco |
| ----------------------------------------- | --- |
| Alterações de entidade do **Trabalho/Posição** | **Região de remuneração** adicionado</br>**Dimensões financeiras** adicionado |
| Alterações de entidade do **Trabalhador** | **Sequência do nome** adicionado</br>**Trabalha de casa** adicionado</br>**Idioma** adicionado</br>**Aniversário de tempo de serviço** adicionado</br>**Data de aniversário** adicionado</br>**Data original de contratação** adicionado |
| Alterações de entidade do **Emprego** | **Dimensões financeiras** adicionado</br>**Motivo da demissão** adicionado</br>**Data da demissão** renomeada de **Data de transição**</br>**Data de experiência** adicionado |
| Alterações de entidade do **Endereço do trabalhador** | **Endereço** adicionado</br>**Linha de endereço 1**, **Linha de endereço 2** e **Linha de endereço 3** marcadas para depreciação |
| Novas entidades de configuração de remuneração variável | **Tipo de plano de remuneração variável**</br>**Plano de remuneração variável**</br>**Regras de benefício proporcional diferido**</br>**Nível do plano de remuneração variável** |
| Nova entidade **Emprego do calendário do trabalhador** | **Entidade do calendário de trabalho** adicionada |
| Nova entidade **Detalhe da posição de folha de pagamento** | **Detalhe da posição de folha de pagamento** adicionado |
| Nova entidade **Bloco** | **Bloco** adicionado. A nova entidade **Título** será incluída no processo de sincronização entre Human Resources e Dataverse. Não será inicialmente referenciada de entidades **Cargo** ou **Trabalho**. |

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]