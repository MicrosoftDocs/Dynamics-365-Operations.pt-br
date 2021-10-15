---
title: Pronto para Pagar
description: Este tópico mostra como marcar um funcionário como pronto para pagar no Dynamics 365 Human Resources.
author: marcelbf
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b9536a6e12b4037458910b7a2d27450ac175fd9d
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559598"
---
# <a name="ready-to-pay"></a>Pronto para Pagar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!NOTE]
> Se você quiser marcar um funcionário como pronto para pagar, será necessário primeiro habilitar a funcionalidade **integração de folha de pagamento (versão preliminar)** no gerenciamento de recursos. Para obter mais informações sobre como habilitar os recursos de visualização, consulte [Gerenciar recursos](hr-admin-manage-features.md).

Esse recurso permite que os profissionais de recursos humanos entendam quais funcionários estão prontos para o processamento da folha de pagamento e quais precisam de uma ação antes de usarem um provedor de folha de pagamento de terceiros.

## <a name="mark-employee-as-ready-to-pay"></a>Marcar funcionário como pronto para pagar

Coletar e validar as informações dos funcionários pode ser demorado e propenso a erros. Ao fornecer uma maneira de os profissionais de recursos humanos revisarem e atualizarem facilmente as informações dos funcionários, o Dynamics 365 Human Resources ajuda a reduzir o tempo gasto se preparando para processar a folha de pagamento.

Como marcar um funcionário como pronto para pagar:

1. Abra **Gerenciamento de remuneração**. Há dois blocos no espaço de trabalho: 
    - **Funcionários que estão prontos para pagar**
    - **Funcionários que não estão prontos para pagar**
    ![Espaço de trabalho de gerenciamento de remuneração.](./media/hr-ready-to-pay-1-workspace.png)

2. Selecione o bloco **Funcionários que não estão prontos para pagar**.

3. Selecione os funcionários a serem validados. Na guia **Folha de Pagamento**, no grupo **Prontos para pagar**, selecione **Validar**.
    ![Validar funcionários.](./media/hr-ready-to-pay-2-validate.png)

4. Para revisar os resultados, na guia **Folha de Pagamento**, no grupo **Prontos para pagar**, selecione **Resultados**.

## <a name="validation"></a>Validação

Antes de marcar um funcionário como pronto para pagar, o perfil do funcionário será validado para integridade.

![Valide os resultados.](./media/hr-ready-to-pay-3-results.png)

| Validação | Detalhes |
| --- | --- |
| **Parâmetro de finalidade do endereço** | Confirme que o parâmetro **Usar a finalidade do endereço da folha de pagamento** está selecionado. |
| **Endereço da folha de pagamento** | Confirme que o perfil do trabalhador tem pelo menos um endereço com a finalidade **Localização da residência de folha de pagamento** ou **Localização do trabalho da folha de pagamento** e se há apenas um endereço por finalidade. |
| **Emprego** | Confirme que o trabalhador tem pelo menos um emprego (atual, anterior ou futuro). |
| **Número de identificação** | Confirme que o campo **Usar os tipos de identificação no processamento da folha de pagamento** é **Sim** na página **Parâmetros de recursos humanos**, e se o tipo de identificação indicado no parâmetro é preenchido no perfil do trabalhador. |
| **Nome e sobrenome** | Confirma que os campos **Nome** e **Sobrenome** são preenchidos.|
| **Cargo** | Confirma que o trabalhador tem um cargo atribuído. |
| **Data de aniversário** | Confirma que o campo **Aniversário** está preenchido. |
| **Remuneração** | Confirma que o trabalhador está inscrito em um plano de remuneração fixa. |

Se uma dessas validações falhar, não será possível marcar o funcionário como pronto para pagar.

Se o campo **Pronto para pagar** for **Não**, isso é um indício de que você deve realizar uma ação para garantir que o perfil do trabalhador esteja completo. Isto não impedirá que os dados sejam expostos nas entidades de dados. 

## <a name="process-automation"></a>Automação de Processo

Você pode automatizar a validação de todos os funcionários usando a [Automação de processos](/dynamics365/fin-ops-core/dev-itpro/sysadmin/process-automation). No espaço de trabalho **Gerenciamento de remuneração**, acesse **Links** \> **Parâmetros** \> **Automações de processo**.

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
