---
title: Novidades ou alterações no Dynamics 365 Human Resources (3 de abril de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 3 de abril de 2020.
author: andreabichsel
manager: tfehr
ms.date: 04/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b00ef61cdd7ceac6c6f57187a0e6c98e94c8cb71
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127912"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-3-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (3 de abril de 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3111. Os números entre parênteses em alguns cabeçalhos referem-se aos números de suporte do Lifecycle Services (LCS) para referência.

## <a name="features-that-are-generally-available-the-week-of-april-6"></a>Recursos que estão geralmente disponíveis na semana de 6 de abril

- **Recursos de licença e ausência** - Para obter mais informações, consulte [Visão geral de licença e ausência](hr-leave-and-absence-overview.md).

- **Recursos de gerenciamento de benefícios** - Para obter mais informações, consulte [Visão geral do gerenciamento de benefícios](hr-benefits-management-overview.md).

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Os limites do ambiente do Human Resources agora são baseados em licenciamento atualizado (394595)

O limite em relação ao número de ambientes por projeto no LCS mudou. O limite anterior era de dois ambientes. O limite em relação ao número de ambientes de produção e área restrita que você pode criar para Human Resources no LCS agora se baseia no licenciamento atualizado. Agora você pode criar quantos ambientes forem necessários por projeto do LCS, dependendo do número de licenças adquiridas. O novo licenciamento, atualizado em 1º de fevereiro de 2020, permite que os clientes adquiram ambientes adicionais. Para obter mais informações sobre requisitos de licenciamento para ambientes adicionais, consulte [Guia de licenciamento do Dynamics 365](https://dynamics.microsoft.com/pricing/#HumanResources).
 
## <a name="error-when-trying-to-delete-a-questionnaire-428603"></a>Erro ao tentar excluir um questionário (428603)

A atualização desta semana corrige um problema no qual o seguinte erro é exibido ao tentar excluir um questionário:

Um par X++ TTSBEGIN/TTSCOMMIT desbalanceado foi detectado.

## <a name="performance-journal-and-professional-certificates-security-issue-428499"></a>Problema de segurança do diário de desempenho e certificados profissionais (428499)

Essa alteração limita a visibilidade de diários de desempenho e certificados profissionais com base nas empresas às quais eles têm acesso. 

## <a name="the-abbreviation-for-quebec-and-manitoba-387510"></a>A abreviação de Quebec e Manitoba (387510)

Os dados iniciais foram atualizados para refletir a abreviação correta para Manitoba e Quebec.

## <a name="new-entities-available-in-data-management-framework"></a>Novas entidades disponíveis na Estrutura de gerenciamento de dados

As entidades a seguir agora estão disponíveis. Se você não vir essas entidades listadas na lista de entidades, use a opção **Atualizar entidades** em **Parâmetros de estrutura > Configurações de entidade > Atualizar lista de entidade**.

 - V2 da transação bancária de licença e ausência
 - V2 da inscrição para licença e ausência
 - V2 da camada do plano de licença e ausência
 - V2 do plano de licença e ausência

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>A solução do Dataverse agora está disponível com as seguintes alterações:

| descrição | Troco |
| --- | --- |
| Alterações de entidade do **Trabalho/Posição** | <ul><li>**Região de remuneração** adicionado</li>|
| Entidade **Dimensão da posição do trabalho** adicionada | <ul><li>**Dimensões financeiras** adicionado</li>
| Alterações de entidade do **Trabalhador** | <ul><li>**Sequência do nome** adicionado</li><li>**Trabalha de casa** adicionado</li><li>**Idioma** adicionado</li><li>**Aniversário de tempo de serviço** adicionado</li><li>**Data de aniversário** adicionado</li><li>**Data original de contratação** adicionado</li></ul> |
| Alterações de entidade do **Emprego** | <ul><li>**Dimensões financeiras** adicionado</li><li>**Motivo da demissão** adicionado</li><li>**Data da demissão** renomeada de **Data de transição**</li><li>**Data de experiência** adicionado</li></ul> |
| Alterações de entidade do **Endereço do trabalhador** | <ul><li>**Endereço** adicionado</li><li>**Linha de endereço 1**, **Linha de endereço 2** e **Linha de endereço 3** marcadas para depreciação</li></ul> |
| Novas entidades de configuração de remuneração variável | <ul><li>**Tipo de plano de remuneração variável**</li><li>**Plano de remuneração variável**</li><li>**Regras de benefício proporcional diferido**</li><li>**Nível do plano de remuneração variável**</li></ul> |
| Nova entidade **Emprego do calendário do trabalhador** | <ul><li>**Entidade do calendário de trabalho** adicionada</li></ul> |
| Nova entidade **Detalhe da posição de folha de pagamento** | <ul><li>**Detalhe da posição de folha de pagamento** adicionado</li></ul> |
| Nova entidade **Bloco** | <ul><li>**Bloco** adicionado</li></ul>A nova entidade **Título** é incluída no Dataverse, mas não é referenciada nas entidades **Posição de trabalho** ou **Trabalho** no momento. |

> [!NOTE]
> As dimensões financeiras para as posições e o trabalho fornecem integração unidirecional para atualizações de recursos humanos para Dataverse. As atualizações de dimensões financeiras não são sincronizadas atualmente de Dataverse a Recursos Humanos.

Nas próximas semanas, essas alterações de entidade estarão disponíveis em todos os ambientes. Para instalar manualmente a solução Dataverse mais recente para recursos humanos:

1.  Vá para [Centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).

2.  Selecione **Ambientes**.

3.  Localize o ambiente que você deseja atualizar. O ambiente deve corresponder ao **Nome do ambiente** na seção **informações do Dataverse** no formulário **Sobre** em Recursos Humanos.

4.  Selecione o ambiente para exibir os detalhes do ambiente.

5.  Na barra de ação na parte superior, selecione **Gerenciar soluções**. Uma nova janela do navegador irá abrir e navegar até o **Centro de Administração do Dynamics 365** no contexto do seu ambiente.

6.  Na lista **Solução**, selecione **Ancoragem de Dynamics 365 Human Resources**.

7.  Selecione **Atualizar** para aplicar a solução mais recente.

## <a name="in-preview"></a>Em Visualização

## <a name="leave-suspension"></a>Sair da suspensão

Você pode suspender a licença e a ausência em Human Resources para um funcionário. Suspender licença interrompe a acumulação de licenças de licença para os tipos de licença selecionados. Se a suspensão ocorrer depois de um acúmulo ter sido processado, a suspensão da licença criará um ajuste rateado para o saldo de licença do funcionário. Para obter mais informações, consulte [Suspender licença](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Regras de postergação

Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos. Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias. Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).

## <a name="coming-soon"></a>Em breve

## <a name="new-production-release-cadence"></a>Nova cadência de liberação da produção

A partir de abril, a cadência de liberação do Human Resources passará de uma atualização semanal para uma atualização quinzenal. Para garantir o alinhamento com práticas de implantação segura e manter altos padrões de estabilidade e confiabilidade no serviço, o processo de implantação de atualizações de serviço em todas as regiões será uma distribuição de duas semanas. Testes e monitores adicionais serão feitos para verificar a implantação bem-sucedida em cada estágio do processo. Para obter mais informações sobre a cadência de liberação, consulte [Atualizar processo](hr-admin-setup-update-process.md).

## <a name="known-issues"></a>Problemas conhecidos

## <a name="employment-detail-entity"></a>Entidade de detalhes do emprego

A entidade **Detalhes de emprego** foi atualizada com os campos a seguir: **PayFrequency**, **ID da categoria de emprego**, **Tipo de emprego**, **ID de EmploymentType** e **Status de benefícios de emprego**. Os dados de configuração para esses campos dependem do gerenciamento de benefícios habilitado no gerenciamento de recursos. Esses campos não devem ser preenchidos nem atualizados na entidade **Detalhes de emprego**, pois isso resultará em erros durante a importação.

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