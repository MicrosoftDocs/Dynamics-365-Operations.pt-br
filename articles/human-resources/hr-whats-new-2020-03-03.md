---
title: Novidades ou alterações no Dynamics 365 Human Resources (3 de março de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 3 de março de 2020.
author: andreabichsel
ms.date: 03/03/2020
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
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 793f47526ef828a281750c34da9d763c94971943
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790443"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-3-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (3 de março de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.2955. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>A solução do Dataverse agora está disponível com as seguintes alterações:

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

Nas próximas semanas, essas alterações de entidade estarão disponíveis em todos os ambientes. Para instalar manualmente a solução Dataverse mais recente para recursos humanos:

1.  Vá para [Centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2.  Selecione **Ambientes**.

3.  Localize o ambiente que você deseja atualizar. O ambiente deve corresponder ao **Nome do ambiente** na seção **informações do Common Data Service** no formulário **Sobre** em Recursos Humanos.

4.  Selecione o ambiente para exibir os detalhes do ambiente.

5.  Na barra de ação na parte superior, selecione **Gerenciar soluções**. Uma nova janela do navegador irá abrir e navegar até o **Centro de Administração do Dynamics 365** no contexto do seu ambiente.

6.  Na lista **Solução**, selecione **Ancoragem de Dynamics 365 Human Resources**.

7.  Selecione **Atualizar** para aplicar a solução mais recente.

## <a name="import-issues-with-the-leave-enrollment-data-entity-406082"></a>Importar saídas com a entidade de dados de registro de licença (406082)

Agora você pode inscrever um funcionário em um novo plano de licença do mesmo tipo, desde que a nova data de inscrição seja posterior à data de inscrição expirada do plano anterior.

## <a name="issue-with-exporting-contribution-rates-in-the-401k-payrollworkerenrolledbenefitdetail-entity-in-dmf-420700"></a>Problema na exportação de taxas de contribuição na entidade payrollWorkerEnrolledBenefitDetail 401k no DMF (420700)

Essa alteração corrige a funcionalidade de exportação da entidade **payrollWorkerEnrolledBenefitDetail** para refletir os valores atuais para contribuição do empregador.

## <a name="searching-in-the-streamlined-worker-form-causes-message-saying-person-field-must-be-filled-in-402525"></a>Pesquisando no formulário Trabalhador simplificado faz com que a mensagem informando que o campo Pessoa deve ser preenchido em (402525)

Ao procurar um funcionário, você não receberá mais uma mensagem dizendo que deve preencher o campo **Pessoa**.

## <a name="note-field-value-doesnt-render-on-the-add-more-skills-form-380134"></a>O valor do campo de observação não é renderizado no formulário Adicionar mais habilidades (380134)

Esta alteração corrige um problema ao personalizar o formulário **Adicionar mais habilidades** no autoatendimento para funcionário.

## <a name="multiple-fixed-compensation-plans-dont-expire-when-transferring-employees-389466"></a>Vários planos de remuneração fixa não expiram ao transferir funcionários (389466)

Com essa alteração, todos os registros de remuneração fixa ativados para a posição antiga expirarão na data de transição.

## <a name="in-preview"></a>Em visualização

Os seguintes recursos de visualização foram disponibilizados em 3 de fevereiro de 2020:

- **Recursos de exibição de licenças e ausências** - para obter mais informações, consulte [Recursos de exibição de licenças e ausências](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Recurso de visualização de gerenciamento de benefícios** - para obter mais informações, incluindo problemas conhecidos, consulte [Visão geral do gerenciamento de benefícios](hr-benefits-management-overview.md).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]