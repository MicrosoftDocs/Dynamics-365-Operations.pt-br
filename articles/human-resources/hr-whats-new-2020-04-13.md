---
title: Novidades ou alterações no Dynamics 365 Human Resources (13 de abril de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 13 de abril de 2020.
author: andreabichsel
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3b7822782fda3c20d57df96af59e18b1725e4f9f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800180"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (13 de abril de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3136. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="new-production-release-cadence"></a>Nova cadência de liberação da produção

Com o lançamento desta semana, a cadência de liberação do Human Resources passará de uma atualização semanal para uma atualização quinzenal. Para garantir o alinhamento com práticas de implantação segura e manter altos padrões de estabilidade e confiabilidade no serviço, o processo de implantação de atualizações de serviço em todas as regiões agora será uma distribuição de duas semanas. Testes e monitores adicionais serão feitos para verificar a implantação bem-sucedida em cada estágio do processo. Para obter mais informações sobre a cadência de liberação, consulte [Atualizar processo](hr-admin-setup-update-process.md).

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a>O campo Precisão de arredondamento não é editável após a especificação de um Tipo de arredondamento (435616)

Com essa alteração, o campo **Precisão de arredondamento** agora está disponível após a atualização do campo **Tipo de arredondamento**.

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a>Não é possível editar a data de término do registro da licença quando o plano de licença não possui períodos de acumulação (413628)

Agora é possível editar a data de término do registro sem receber o erro "O campo Data base da competência deve ser preenchido".

## <a name="employment-entity-doesnt-sync-to-dataverse-430834"></a>A entidade de emprego não sincroniza com o Dataverse (430834)

Essa alteração corrige um problema em que os dados do emprego não estavam sendo sincronizados com o Dataverse após a adição de dimensões financeiras. 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a>Remover entidade com vários pais para a entidade Intervalo do Calendário de Trabalho (431775)

Essa alteração remove os vários pais da entidade **Intervalo do Calendário de Trabalho**.

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a>O filtro com a função CAST não funciona na entidade Atribuição do Trabalhador da Posição da chamada do OData (431699)

Essa atualização inclui uma alteração para permitir o filtro com a função CAST no OData para a entidade **Atribuição do Trabalhador da Posição**.

## <a name="in-preview"></a>Em Visualização

## <a name="leave-suspension"></a>Sair da suspensão

Você pode suspender a licença e a ausência em Human Resources para um funcionário. Suspender licença interrompe a acumulação de licenças de licença para os tipos de licença selecionados. Se a suspensão ocorrer depois de um acúmulo ter sido processado, a suspensão da licença criará um ajuste rateado para o saldo de licença do funcionário. Para obter mais informações, consulte [Suspender licença](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Regras de postergação

Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos. Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias. Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Problemas conhecidos

## <a name="employment-details-entity"></a>Entidade Detalhes do emprego

A entidade **Detalhes de emprego** foi atualizada com os seguintes campos:

- **Frequência de Pagamento**
- **Categoria de emprego**
- **Tipo de emprego**
- **ID de EmploymentType**
- **Status de benefícios de emprego**

Os dados de configuração desses campos dependem da ativação do gerenciamento de benefícios no espaço de trabalho **Gerenciamento de recursos**. Não preencha ou atualize esses campos na entidade **Detalhes de emprego**, pois isso resultará em erros durante a importação.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>A visualização do SharePoint não funcionará em alguns ambientes

Se a visualização de documentos armazenados no SharePoint não funcionar, tente o seguinte procedimento:

1. Verifique se a conta de usuário do administrador possui um email associado ao registro do usuário. Você pode exibir essas informações na página **Usuário**. Se o email não estiver configurado, você precisará adicionar o email e o provedor com o suplemento do OData Excel. Por padrão, o endereço de email não está presente no design do Excel. Será preciso editar o design do Excel, adicionar todos os campos, aplicar e atualizar. Depois de concluir essas etapas, você pode atualizar a conta de administrador.

2. Depois que a conta de administrador tiver uma conta de email associada, entre no Human Resources com credenciais de administrador.

3. Acesse um anexo no SharePoint para iniciar a visualização do documento.

4. Entre com outra conta de usuário que tenha acesso a anexos e verifique se a visualização funciona conforme o esperado.

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]