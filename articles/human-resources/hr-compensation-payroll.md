---
title: Pronto para Pagar
description: Este tópico mostra como marcar um funcionário como pronto para pagar no Dynamics 365 Human Resources.
author: marcelbf
ms.date: 07/13/2020
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
ms.openlocfilehash: 70b3f31db459fe021caf08fe09b2e44a597294d1992ee16a69efd8745941a4bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732408"
---
# <a name="ready-to-pay"></a>Pronto para Pagar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

> [!NOTE]
> Se você quiser marcar um funcionário como pronto para pagar, será necessário primeiro habilitar a funcionalidade **integração de folha de pagamento (versão preliminar)** no gerenciamento de recursos. Para obter mais informações sobre como habilitar os recursos de visualização, consulte [Gerenciar recursos](hr-admin-manage-features.md).

Esse recurso permite que os profissionais de recursos humanos entendam quais funcionários estão prontos para o processamento da folha de pagamento e quais precisam de uma ação antes de usarem um provedor de folha de pagamento de terceiros.

## <a name="mark-employee-as-ready-to-pay"></a>Marcar funcionário como pronto para pagar

Coletar e validar as informações dos funcionários pode ser demorado e propenso a erros. Ao fornecer uma maneira de os profissionais de recursos humanos revisarem e atualizarem facilmente as informações dos funcionários, o Dynamics 365 Human Resources ajuda a reduzir o tempo gasto se preparando para processar a folha de pagamento.

Como marcar um funcionário como pronto para pagar:

1. Abra **Gerenciamento de remuneração**. Há dois blocos no espaço de trabalho 
    - **Funcionários que estão prontos para pagar**
    - **Funcionários que não estão prontos para pagar**
    ![Espaço de trabalho de gerenciamento de remuneração.](./media/hr-ready-to-pay-1-workspace.png)

2. Selecione o bloco **Funcionários que não estão prontos para pagar**.

3. Selecione os funcionários a serem validados. Na guia **Folha de Pagamento**, no grupo **Prontos para pagar**, selecione **Validar**.
    ![Validar funcionários.](./media/hr-ready-to-pay-2-validate.png)

4. Para revisar os resultados, na guia **Folha de Pagamento**, no grupo **Prontos para pagar**, selecione **Resultados**.

## <a name="validation"></a>Validação

Antes de marcar um funcionário como pronto para pagar, o sistema fará uma validação básica sobre a integridade do perfil.

![Valide os resultados.](./media/hr-ready-to-pay-3-results.png)

A tabela a seguir fornece informações sobre cada uma das validações realizadas. 

| Validação | Detalhes |
| --- | --- |
| Parâmetro de finalidade do endereço | Valida se o parâmetro **Usar a finalidade do endereço da folha de pagamento** estiver ativo. |
| Endereço da folha de pagamento | Valida se o perfil do trabalhador tiver pelo menos um endereço com a finalidade "Localização da residência de folha de pagamento" ou "Localização do trabalho da folha de pagamento" e se houver apenas um endereço por finalidade. |
| Emprego | Verifique se o trabalhador tem pelo menos um emprego (atual, anterior ou futuro). |
| Número de identificação | Valida se o parâmetro "Usar os tipos de identificação no processamento da folha de pagamento" for sim, e se o tipo de identificação indicado no parâmetro for preenchido no perfil do trabalhador. |
| Nome e sobrenome | Valida se o perfil do trabalhador for válido, verificando se os campos **Nome** e **Sobrenome** estão preenchidos.|
| Cargo | Verifique se o trabalhador tem um cargo atribuído. |
| Data de aniversário | Valida se o perfil do trabalhador for válido, verificando se o campo **Data de nascimento** está preenchido. |
| Remuneração | Verifique se o trabalhador está inscrito em um plano de remuneração fixa. |

Se uma dessas validações falhar, não será possível marcar o funcionário como pronto para pagar.

Se o campo **Pronto para pagar** for **Não**, isso é um indício de que você deve realizar uma ação para garantir que o perfil do trabalhador esteja completo. Isto não impedirá que os dados sejam expostos nas entidades de dados. 

## <a name="known-issues"></a>Problemas conhecidos

- É necessário desativar o recurso **Entrada simplificada de funcionários** no gerenciamento de recursos. Os blocos no espaço de trabalho de gerenciamento de remuneração não funcionarão corretamente se você usar esse recurso.
- No formulário do trabalhador, na guia **Folha de Pagamento**, o grupo **Prontos para pagar** está disponível para qualquer função do usuário. 

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
